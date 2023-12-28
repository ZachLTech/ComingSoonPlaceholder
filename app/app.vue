<template>
  <head>
    <title>Coming Soon</title>
  </head>
  <body class="overflow-hidden cursor-none bg-[url('~/assets/img/ComingSoonBackground.png')] bg-left-bottom">
    <div class="h-screen">
      <TopBar />
      <div v-if="$viewport.isLessThan('tablet')" class="h-[80%]">
        <HeroMobile />
      </div>
      <div v-else class="h-[80%]">
        <CustomCursor />
        <CursorGlow />
        <Hero />
      </div>
    </div>
  </body>
</template>