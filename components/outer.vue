<script>
import {
  defineComponent,
  useFetch,
  ref,
  onMounted,
  useContext,
} from "@nuxtjs/composition-api";
import axios from "axios";

export default defineComponent({
  setup(props, context) {
    const title = ref("");

    const { fetch } = useFetch(async () => {
      const { data } = await axios.get(
        "https://jsonplaceholder.typicode.com/todos/1"
      );
      title.value = data.title;
    });

    fetch();

    return () => context.slots.default({ title: title.value });
  },
});
</script>
