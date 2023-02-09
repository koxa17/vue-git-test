<template>
  <div>
    <h1>Домашняя страница!</h1>
    <servise-list v-model="selected" :items="users"  v-bind="attr">
<!--      <template #selected-option="{slotProps}" >-->
<!--        <strong><el-link @click="openDialog">{{ slotProps.name }}</el-link></strong>-->
<!--        <strong><el-button @click="openDialog">{{ slotProps.name }}</el-button></strong>-->
<!--      </template>-->
      <template #selected-option-container="{slotProps}">
        <strong><el-link @click="openDialog">{{ slotProps.name }}</el-link></strong>
      </template>
    </servise-list>

    <el-dialog
        v-model="dialogVisible"
        :title='`Информация по ${selected}`'
        append-to-body
    >
      <el-form :model="form" label-width="120px">
        <el-form-item label="Activity name">
          <el-input v-model="form.name" />
        </el-form-item>
        <el-form-item label="Activity zone">
          <el-select v-model="form.region" placeholder="please select your zone">
            <el-option label="Zone one" value="shanghai" />
            <el-option label="Zone two" value="beijing" />
          </el-select>
        </el-form-item>
        <el-form-item label="Activity time">
          <el-col :span="11">
            <el-date-picker
                v-model="form.date1"
                type="date"
                placeholder="Pick a date"
                style="width: 100%"
            />
          </el-col>
          <el-col :span="2" class="text-center">
            <span class="text-gray-500">-</span>
          </el-col>
          <el-col :span="11">
            <el-time-picker
                v-model="form.date2"
                placeholder="Pick a time"
                style="width: 100%"
            />
          </el-col>
        </el-form-item>
        <el-form-item label="Instant delivery">
          <el-switch v-model="form.delivery" />
        </el-form-item>
        <el-form-item label="Activity type">
          <el-checkbox-group v-model="form.type">
            <el-checkbox label="Online activities" name="type" />
            <el-checkbox label="Promotion activities" name="type" />
            <el-checkbox label="Offline activities" name="type" />
            <el-checkbox label="Simple brand exposure" name="type" />
          </el-checkbox-group>
        </el-form-item>
        <el-form-item label="Resources">
          <el-radio-group v-model="form.resource">
            <el-radio label="Sponsor" />
            <el-radio label="Venue" />
          </el-radio-group>
        </el-form-item>
        <el-form-item label="Activity form">
          <el-input v-model="form.desc" type="textarea" />
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="onSubmit">Create</el-button>
          <el-button>Cancel</el-button>
        </el-form-item>
      </el-form>
    </el-dialog>

  </div>
</template>

<script setup>

import ServiseList from "@/components/ServiseList";
import {ref, useAttrs} from "vue";
/* eslint-disable */
const emits = defineEmits(['close'])
const dialogVisible = ref(false)
const selected = ref(false)
const users = ref([
  {
    id: 1,
    name: "Николай",
    age: 27
  },
  {
    id: 2,
    name: "Роман",
    age: 28
  },
  {
    id: 3,
    name: "Евгений",
    age: 16
  },
])
const attr = useAttrs();

function openDialog() {
  dialogVisible.value = true
}

import { reactive } from 'vue'

// do not use same name with ref
const form = reactive({
  name: '',
  region: '',
  date1: '',
  date2: '',
  delivery: false,
  type: [],
  resource: '',
  desc: '',
})

const onSubmit = () => {
  console.log('submit!')
}

</script>

<style scoped>

</style>