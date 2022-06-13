<template>
<header class="menu-superior">
  <div class="menu-esquerdo">
    <span> <RouterLink to="/">Home</RouterLink> </span>
    <span>|</span>
    <span> <RouterLink to="/jogadores">Jogadores</RouterLink> </span>
    <span>|</span>
    <span> <RouterLink to="/times">Times</RouterLink> </span>
  </div>
  <div class="menu-direito">
    <span>Sair</span>
  </div>
</header>
</template>
<style>
header span {
  padding: 0 20px;
 
}
a{
  color: white;
  text-decoration: none;
}
header.menu-superior {
  /*display: flex;
  align-items: center;*/
  justify-content: space-between;
}   
</style>