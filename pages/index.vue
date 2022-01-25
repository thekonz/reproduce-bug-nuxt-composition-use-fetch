<template>
  <div>
    <outer>
      <template #default="{ title }">
        <inner :title="title" />
      </template>
    </outer>
  </div>
</template>
