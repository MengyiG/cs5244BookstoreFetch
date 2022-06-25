<template>
  <div class="category-content">
    <category-nav></category-nav>
    <category-book-list :books="books"> </category-book-list>
  </div>
</template>

<script>
import CategoryNav from "@/components/CategoryNav";
import CategoryBookList from "@/components/CategoryBookList";

export default {
  name: "categoryView",
  components: {
    CategoryNav,
    CategoryBookList,
  },
  data: function () {
    return {
      books: [
        {
          bookId: 1001,
          title:
            "It's Not You It's Him: An absolutely hilarious and feel good romantic comedy",
          imageFile: "C1.jpeg",
          author: "by Sophie Ranald",
          price: 1286,
          isPublic: true,
        },
        {
          bookId: 1002,
          title:
            "Over a God's Dead Body: A Supernatural Comedy (Wrong Gods Book 1)",
          imageFile: "C2.jpeg",
          author: "by Joel Spriggs",
          price: 1899,
          isPublic: false,
        },
        {
          bookId: 1003,
          title: "The Divine Comedy: A Dual-Language Book (English - Italian)",
          imageFile: "C3.jpeg",
          author: "by Dante Alighieri and Henry Wadsworth Longfellow",
          price: 599,
          isPublic: true,
        },
        {
          bookId: 1004,
          title: "The Divine Comedy",
          imageFile: "C4.jpeg",
          author: "by Dante Alighieri and Gustave Dore",
          price: 3274,
          isPublic: false,
        },
        {
          bookId: 1005,
          title: "Lessons in Chemistry",
          imageFile: "C5.jpeg",
          author: "by Bonnie Garmus",
          price: 699,
          isPublic: false,
        },
        {
          bookId: 1006,
          title: "That's Not Funny: How the Right Makes Comedy Work for Them",
          imageFile: "C6.jpeg",
          author: 'by Matt Sienkiewicz and Nick Marx"',
          price: 699,
          isPublic: true,
        },
      ],
    };
  },
};
</script>

<style scoped>
.category-content {
  display: flex;
  height: 78vh;
  min-height: 320pt;
}
</style>
