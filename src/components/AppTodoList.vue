<template>
    <div class="todos">
        <div v-for="todo in todos" :key="todo.id">
            <AutoComplete :todo="todo" ></AutoComplete>
        </div>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import AppTodoItem , {Todo} from "./AppTodoItem.vue"
// export default Vue.extend ({
//     推論型と型アサーション(dataがコンポーネントに閉じられている場合に有効)
//     data: () => ({
//         firstName: '',
//         lastName: '',
//         doneTodo: null as null | boolean,
//         todos: [] as Array<{
//             id: string,
//             task: string,
//             done: boolean
//         }>
//     })
// })


//型定義をアノテーションで付与する
// export type Todo = {
//     id: string,
//     task: string
//     done: boolean
// }

// export type Data = {
//     firstName: string,
//     lastName: string,
//     todos: Todo[]
// }

// export default Vue.extend ({
//     data: (): Data => ({//Data型を付与
//         firstName: 'Taro',
//         lastName: 'Yamada',
//         todos: []
//     })
// })

export type Data = {
    todos: Todo[]
}

export default Vue.extend({
    data: (): Data => ({
        todos: []
    }),
    components: {
        AppTodoItem
    }
})
</script>