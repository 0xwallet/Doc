# 介绍

什么是阿波罗客户端, 它能做什么?

阿波罗客户端是使用 GraphQL 来构造客户端应用的最佳方式. 这个客户端被设计成能够帮助你很快地构造一个从 GraphQL 获取数据的 UI, 并且可以用于任何的 JavaScript 前端. 这个客户端是:

- 可移植的: 你可以把它放到一个现有的 app 里面.
- 通用的: 阿波罗适用于任何编译配置, 任何 GraphQL 服务器 和 任何 GraphQL schema.
- 可观测和易懂的: 清晰地知道应用中正在发生什么.
- 为交互应用而生: 应用的用户做出修改然后立刻看到反应.
- 小巧灵活: 你不会得到你不需要的东西.
- 社区驱动: 阿波罗是社区驱动的, 并且适用于多种场景.

# 为什么选择 Apollo 客户端来管理数据?

数据管理不应该是一件难事! 如果你在思考如何简化对React应用中远程和本地数据的管理, 那么你就选对地方了. 通过我们的实际实例应用 Pupstagram, 你会学到 Apollo 的只能缓存和声明式的数据获取方法, 能够帮助你更快的而且写更少的代码. 让我们开始吧! 🚀

# 声明式数据获取

通过 Apollo 的声明式方式来获取数据, 所有的数据搜索逻辑, 载入过程和错误状态, 以及对 UI 的更新全都包含在一个单独的 Query 组件中. 这使得你的 Query 组件和表现层的组件结合起来非常容易! 让我们看看 React Apollo 中它是什么样子的:

```js
const Feed = () => (
  <Query query={GET_DOGS}>
    {({ loading, error, data }) => {
      if (error) return <Error />
      if (loading || !data) return <Fetching />;

      return <DogList dogs={data.dogs} />
    }}
  </Query>
)
```