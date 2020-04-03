<template>
    <div class="todo">
        {{myTask}}
    </div>
</template>

<script lang='ts'>
import Vue, { PropType } from 'vue';
export type Todo = {
    id: string,
    task: string
    done: boolean
}

//props型の親コンポーネントに提供する
//*template内部でも加工禁物、コンパイルエラーをすり抜けてしまう。
export default Vue.extend ({
    props: {
        todo: Object as PropType<Todo>
    },
    computed: {
        myTask(): string {
            return this.todo.task
        }
    }
})
</script>