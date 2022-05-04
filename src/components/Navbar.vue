<template>
  <!-- Responsive navbar-->
  <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
    <div class="container">
      <a class="navbar-brand" href="#!">SMAN 9 Lutra</a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Home</a>
          </li>
          <li class="nav-item"><a class="nav-link" href="#surat">SK</a></li>
          <li class="nav-item">
            <a class="nav-link" href="#pengumuman">Pengumuman</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#keterangan">Keterangan</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>
<style scoped>
nav {
  position: fixed;
  width: 100%;
  z-index: 1;
}
</style>
