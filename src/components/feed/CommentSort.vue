<template>
  <q-btn
    class="text-capitalize"
    flat
    :icon-right="biChevronExpand"
    :label="t('sort.comment.' + sort)"
  >
    <q-menu>
      <q-list style="min-width: 100px">
        <q-item clickable v-close-popup @click="onSort('NEW_COMMENT')">
          <q-item-section side>
            <q-icon :name="laFireSolid" />
          </q-item-section>
          <q-item-section>
            <q-item-label>{{ t('sort.comment.NEW_COMMENT') }}</q-item-label>
            <q-item-label caption>{{ t('sort.comment.NEW_COMMENT_DESC') }}</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable v-close-popup @click="onSort('TOP_COMMENT')">
          <q-item-section side>
            <q-icon :name="laRocketSolid" />
          </q-item-section>
          <q-item-section>
            <q-item-label>{{ t('sort.comment.TOP_COMMENT') }}</q-item-label>
            <q-item-label caption>{{ t('sort.comment.NEW_COMMENT_DESC') }}</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable v-close-popup @click="onSort('ALL_COMMENT')">
          <q-item-section side>
            <q-icon :name="laHourglassEndSolid" />
          </q-item-section>
          <q-item-section>
            <q-item-label>{{ t('sort.comment.ALL_COMMENT') }}</q-item-label>
            <q-item-label caption>{{ t('sort.comment.ALL_COMMENT_DESC') }}</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-menu>
  </q-btn>
</template>

<script setup lang="ts">
import { useLang } from '@/composables/useLang';
import type { CommentSortType } from '@/types/models';
import { biChevronExpand } from '@quasar/extras/bootstrap-icons';
import { laFireSolid, laHourglassEndSolid, laRocketSolid } from '@quasar/extras/line-awesome';
import { ref } from 'vue';

const { t } = useLang();
const sort = ref<CommentSortType>('NEW_COMMENT');
const onSort = (s: CommentSortType) => {
  sort.value = s;
};
</script>
