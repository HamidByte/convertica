<script setup>
import { convertersList } from '@/lib/converters'
</script>

<template>
  <section class="w-full py-6 md:py-12 lg:py-16 rounded-lg bg-gray-100 dark:bg-gray-800">
    <div class="container px-4 md:px-6">
      <div
        class="flex flex-col items-center justify-center space-y-4 text-center"
      >
        <div
          class="mx-auto grid max-w-5xl items-start gap-8 sm:grid-cols-2 md:gap-12 lg:grid-cols-3"
        >
          <div
            class="card sm:max-w-sm"
            v-for="(converter, index) in convertersList"
          >
            <div class="card-body">
              <div class="flex flex-row justify-end gap-2">
                <p v-if="converter.isNew" class="text-xs"><span class="badge badge-outline badge-secondary badge-xs ms-1 rounded-full">NEW</span></p>
              </div>
              <h5 class="card-title mb-0">
                {{ converter.title }}
              </h5>
              <div class="text-base-content/50 mb-6">
                {{ converter.description }}
              </div>
              <p class="mb-4">
                Explore a range of features and services designed to enhance
                your experience. Join us and make the most out of what we have
                to offer.
              </p>
            </div>
            <div class="card-footer text-center">
              <component
                :class="converter.isDisabled ? 'btn btn-primary btn-disabled' : 'btn btn-primary'"
                :is="converter.isDisabled ? 'span' : 'router-link'"
                :to="converter.href"
                >
                Go
                </component>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
