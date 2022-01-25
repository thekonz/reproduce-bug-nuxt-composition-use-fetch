<script>
import { ref } from "#imports";
import { useLazyFetch } from "#app";
import axios from "axios";

export default defineComponent({
  setup(props, context) {
    const title = ref("");

    useLazyFetch("https://jsonplaceholder.typicode.com/todos/1").then(
      ({ data }) => {
        title.value = data.value.title;
      }
    );

    return () => context.slots.default({ title: title.value });
  },
});
</script>
