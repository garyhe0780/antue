<template>
  <atu-dropdown>
    <a class="ant-dropdown-link">Hover me <atu-icon type="down" /></a>
    <atu-menu slot="overlay">
      <atu-menu-item index="1">
        <a target="_blank" rel="noopener noreferrer" href="#dropdown">1st menu item</a>
      </atu-menu-item>
      <atu-menu-item index="2">
        <a target="_blank" rel="noopener noreferrer" href="#dropdown">2nd menu item</a>
      </atu-menu-item>
      <atu-menu-item index="3">
        <a target="_blank" rel="noopener noreferrer" href="#dropdown">3rd menu item</a>
      </atu-menu-item>
    </atu-menu>
  </atu-dropdown>
</template>

<script>
import AtuDropdown from '@/dropdown'
import AtuIcon from '@/icon'
import AtuMenu from '@/menu'
const AtuMenuItem = AtuMenu.Item

export default {
  components: {
    AtuMenu,
    AtuIcon,
    AtuMenuItem,
    AtuDropdown
  }
}
</script>
