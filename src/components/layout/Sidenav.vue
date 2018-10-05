<template>
    <aside>
        <p>{{ title }}</p>

        <section>
            <div 
                v-for="(link, i) in links" 
                :key="i">
                <router-link 
                    v-if="!link.children" 
                    :to="link.to">
                    {{link.name}}
                </router-link>
                <div
                    v-else
                    @click="showChildres(link)">
                    {{link.name}}
                    <transition name="slide">
                        <div v-if="link.isShowChildren">
                            <router-link 
                                v-for="(childLink, j) in link.children"
                                :key="j"
                                :to="childLink.path">
                                {{childLink.name}}
                            </router-link>
                        </div>
                    </transition>
                </div>
            </div>
        </section>
    </aside>
</template>

<script>
export default {
  name: 'Sidenav',
  data() {
    return {
      title: 'Информационная поддержка жизненного цикла',

      links: [
        {
          name: 'Главная',
          icon: '',
          path: '/',
          children: []
        },
        {
          name: 'ИПИ в Нижегородской области',
          icon: '',
          path: '/',
          children: []
        },
        {
          name: 'Лекции',
          icon: '',
          path: '/',
          children: [
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            }
          ]
        },
        {
          name: 'Тесты',
          icon: '',
          path: '/',
          children: [
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            }
          ]
        },
        {
          name: 'Практика',
          icon: '',
          path: '/',
          children: [
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            },
            {
              name: 'Лекции',
              icon: '',
              path: '/'
            }
          ]
        }
      ]
    };
  },
  methods: {
    showChildres(link) {
      if (!link.children.length) {
        return;
      }

      this.links = this.links.map(linkInside => {
        linkInside.name === link.name
          ? (linkInside.isShowChildren = !linkInside.isShowChildren)
          : (linkInside.isShowChildren = false);
        return linkInside;
      });
    }
  }
};
</script>

<style scoped>
.slide-enter-active,
.slide-leave-active {
  transition: margin-top 0.5s ease-out, opacity 0.5s ease;
}

.slide-enter,
.slide-leave-to {
  margin-top: -20px;
  opacity: 0;
}

.slide-enter-to,
.slide-leave {
  opacity: 1;
  margin-top: 0px;
}
</style>
