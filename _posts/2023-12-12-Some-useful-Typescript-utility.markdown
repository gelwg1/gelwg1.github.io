---
layout: post
title:  "Some useful Typescript utility"
date:   2023-12-12 12:03:0 +0700
categories: [Coding, Typescript]
---
## Partial<Type>
  Constructs a type with all properties of Type set to optional. This utility will return a type that represents all subsets of a given type.

  Example: 

  {% highlight typescript %}
  interface Todo {
    title: string;
    description: string;
  }
   
  function updateTodo(todo: Todo, fieldsToUpdate: Partial<Todo>) {
    return { ...todo, ...fieldsToUpdate };
  }
   
  const todo1 = {
    title: "organize desk",
    description: "clear clutter",
  };
   
  const todo2 = updateTodo(todo1, {
    description: "throw out trash",
  });
  {% endhighlight %}
## Required<Type>
  Simply the opposite of Partial.
  Example: 
  {% highlight typescript %}
  interface Props {
    a?: number;
    b?: string;
  }
   
  const obj: Props = { a: 5 };
   
  const obj2: Required<Props> = { a: 5 };
  {% endhighlight %}
## Omit<Type, Keys>
  Lấy hết loại trừ 1 key.
  Constructs a type by picking all properties from Type and then removing Keys (string literal or union of string literals). The opposite of Pick.
{% highlight typescript %}
  interface Todo {
  title: string;
  description: string;
  completed: boolean;
  createdAt: number;
  }
  type TodoInfo = Omit<Todo, "completed" | "createdAt">;
   
  const todoInfo: TodoInfo = {
    title: "Pick up kids",
    description: "Kindergarten closes at 5pm",
  };
   
  todoInfo;
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
