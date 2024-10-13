
<script setup>



</script>


<template>
      <div class="min-h-screen bg-base-200 p-8">
        <div class="card max-w-3xl mx-auto shadow-lg bg-white rounded-xl p-6">
        <div class="flex flex-col md:flex-row items-center md:items-start md:space-x-8 p-8 bg-white shadow-xl rounded-lg hover:shadow-2xl transition-all duration-300 ease-in-out">
        <img
        src="https://lh3.googleusercontent.com/a/ACg8ocKrDVnkyOjym1GrZ64MsCk3rkfidtm6fvCmyt86fSkBnUHAxPD9FPQcinfo4tCYe3qM1tl8ArfX7mGncc4CmBiHyoYWYwYb=s288-c-no"
        alt="Profile Picture"
        class="w-32 h-32 md:w-40 md:h-40 object-cover rounded-full shadow-lg mb-6 md:mb-0 border-4 border-primary"/>

          
          
        <div class="space-y-4 text-center md:text-left">
        <h1 class="text-3xl md:text-4xl font-extrabold text-primary">Thanathep Arreewong</h1>
        <p class="text-gray-500 text-lg">Frontend Developer</p>
          <div class="flex flex-wrap justify-center md:justify-start gap-2 md:gap-4">
            <span class="badge badge-primary px-4 py-2 text-sm md:text-lg">JavaScript  </span>
            <span class="badge badge-secondary px-4 py-2 text-sm md:text-lg">Vue.js    </span>
            <span class="badge badge-accent px-4 py-2 text-sm md:text-lg"> TailwindCSS  </span>
          </div>
        </div>
      </div>

      <hr class="my-6 border-gray-300" />

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
        <div>
          <h2 class="text-xl font-semibold">Contact Info</h2>
          <ul class="list-none mt-2 space-y-2">
            <li><strong>Email:</strong> too2008to@gmail.com</li>
            <li><strong>Phone:</strong> 086-353-6018</li>
            <li><strong>Location:</strong> Samut Sakhon, Thailand</li>
          </ul>
        </div>
        <div>
          <h2 class="text-xl font-semibold">Education</h2>
          <ul class="list-none mt-2 space-y-2">
            <li><strong>Bachelor's Degree : </strong> Computer Science</li>
            <li><strong>University : </strong> Kasetsart University</li>
            <li><strong>Graduation Year : </strong> 2025</li>
          </ul>
        </div>
      </div>

      <div class="mt-6">
        <h2 class="text-xl font-semibold">Work Experience</h2>
        <ul class="list-none mt-2 space-y-2">
          <li><strong>No experience yet</strong></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped>
img {
  transition: transform 0.3s ease;
}
img:hover {
  transform: scale(1.05);
}
</style>