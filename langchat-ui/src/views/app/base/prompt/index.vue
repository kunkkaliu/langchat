<!--
  - Copyright (c) 2024 LangChat. TyCoding All Rights Reserved.
  -
  - Licensed under the GNU Affero General Public License, Version 3 (the "License");
  - you may not use this file except in compliance with the License.
  - You may obtain a copy of the License at
  -
  -     https://www.gnu.org/licenses/agpl-3.0.html
  -
  - Unless required by applicable law or agreed to in writing, software
  - distributed under the License is distributed on an "AS IS" BASIS,
  - WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  - See the License for the specific language governing permissions and
  - limitations under the License.
  -->

<script lang="ts" setup>
  import { useAppStore } from '@/views/app/store';

  const emit = defineEmits(['update']);
  const appStore = useAppStore();

  async function onUpdate() {
    emit('update');
  }
</script>

<template>
  <div class="h-full flex flex-col gap-2">
    <div class="p-2 flex justify-between items-center">
      <div class="text-md font-bold">Prompt 提示词</div>
    </div>
    <div class="p-4 pt-0 h-full mb-10">
      <textarea
        v-model="appStore.info.prompt"
        class="h-full w-full bg-transparent"
        @blur="onUpdate"
      ></textarea>
    </div>
  </div>
</template>

<style lang="less" scoped></style>
