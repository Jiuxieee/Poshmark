# Poshmark 前端可见接口总览（含 app.js + listingDetail.js）

> 说明：本表整合自前端打包脚本 app.*.js 与 listingDetail.*.js 中的路径构造与调用逻辑。用于前端抓取/联调参考。

---

## 目录

- [上传相关](#上传相关)
- [元数据相关](#元数据相关)
- [分享相关](#分享相关)
- [合集/专题相关](#合集专题相关)
- [商品相关](#商品相关)
- [审核相关](#审核相关)
- [报价相关](#报价相关)
- [活动/Party相关](#活动Party相关)
- [点赞相关](#点赞相关)
- [用户相关](#用户相关)
- [相似推荐相关](#相似推荐相关)
- [社交/关注相关](#社交关注相关)
- [订单相关](#订单相关)
- [认证相关](#认证相关)
- [评论相关](#评论相关)
- [风险确认相关](#风险确认相关)
- [验证相关](#验证相关)
- [通用说明](#通用说明)
- [实战模板](#实战模板)

---

## 上传相关

<details><summary>展开/折叠 上传相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `暂无说明` | **POST** | 图片上传（非 vm-rest 方式） | upload |

</details>


---

## 元数据相关

<details><summary>展开/折叠 元数据相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/metadata` | **GET** | 元入口点 | metadata |
| `/metadata/all_brands_cache` | **GET** | Brand cache | metadata |
| `/metadata/all_experience` | **GET** | 暂无说明 | metadata |
| `/metadata/brand_and_canonical_catalog_slug` | **GET** | 暂无说明 | metadata |
| `/metadata/catalog/colors` | **GET** | 暂无说明 | metadata |
| `/metadata/catalog/departments` | **GET** | 暂无说明 | metadata |
| `/metadata/domain_i18n` | **GET** | 暂无说明 | metadata |
| `/metadata/experience` | **GET** | 暂无说明 | metadata |
| `/metadata/my_size_set` | **GET** | 暂无说明 | metadata |
| `/metadata/size_chart` | **GET** | 使用“/metadata/size_chart/{id}”来获取图表信息 | metadata |
| `/vm-rest/metadata/catalog/colors` | **GET** | 获取可用颜色表 | metadata |

</details>


---

## 分享相关

<details><summary>展开/折叠 分享相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/shares` | **POST** | 使用“/posts/{postId}/shares”进行分享 | shares |

</details>


---

## 合集/专题相关

<details><summary>展开/折叠 合集/专题相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/collections/posts/all` | **GET** | 暂无说明 | collections |
| `/collections/posts/feed/summary` | **GET** | 暂无说明 | collections |

</details>


---

## 商品相关

<details><summary>展开/折叠 商品相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/posts` | **GET** | 列表条目 | posts |
| `/posts/coming_soon` | **GET** | 暂无说明 | posts |
| `/posts/comparables` | **GET** | 暂无说明 | posts |
| `/posts/deep_inventory` | **GET** | 暂无说明 | posts |
| `/posts/filtered` | **GET** | 使用筛选条件进行搜索 | posts |
| `/posts/filtered/potential_earnings` | **GET** | 暂无说明 | posts |
| `/posts/liked` | **GET** | 暂无说明 | posts |
| `/posts/liked/filtered` | **GET** | 暂无说明 | posts |
| `/posts/liked/users` | **GET** | 喜欢了某条帖子的用户（若需针对特定帖子，请使用“/append/{postId}/likes/users”格式） | posts |
| `/posts/potential_earnings` | **GET** | 暂无说明 | posts |
| `/posts/purchased` | **GET** | 暂无说明 | posts |
| `/posts/suggested/just_in` | **GET** | 暂无说明 | posts |
| `/posts/top_sold` | **GET** | 暂无说明 | posts |
| `/posts/viewed` | **GET** | 暂无说明 | posts |
| `/vm-rest/posts/{postId}` | **GET** | 获取商品详情 | posts |
| `/vm-rest/posts/{postId}/feed` | **GET** | 获取商品详情页底部动态Feed | posts |
| `/vm-rest/posts/{postId}/related/posts` | **GET** | 相似/相关商品（支持 summarize、count 参数） | related |
| `/vm-rest/posts/{postId}/similar_posts` | **GET** | 相似商品（常见 size=40） | related |
| `/vm-rest/users/my_size_category/{departmentId}/{categoryId}` | **GET** | 查找相似分类（Find similar category） | posts |

</details>


---

## 审核相关

<details><summary>展开/折叠 审核相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/moderation` | **GET** | 暂无说明 | moderation |
| `/moderation/index` | **GET** | 暂无说明 | moderation |
| `/moderation/post` | **GET** | GET /users/{userId}/moderation/post 以获取待审核详情 | moderation |
| `/moderation/store` | **GET** | 暂无说明 | moderation |
| `/moderation/store/actions` | **GET** | 暂无说明 | moderation |
| `/moderation/store/index` | **GET** | 暂无说明 | moderation |
| `/moderation/store/mutations` | **GET** | 暂无说明 | moderation |
| `/moderation_votes` | **POST** | 与 /posts/{postId}/moderation_votes/{vote} 结合使用 | moderation |
| `/vm-rest/posts/{postId}/admin_delete?reason={reason}&send_email={flag}` | **PUT** | 管理员删除商品（支持是否发邮件） | moderation |
| `/vm-rest/posts/{postId}/moderation/{reason}/{decision}` | **PUT** | 提交审核结果（reason/decision 路径参数） | moderation |
| `/vm-rest/users/{userId}/moderation/post` | **GET** | 获取审核详情（需 creator_id） | moderation |
| `/vm-rest/users/{userId}/reported/posts/{postId}` | **POST** | 举报商品（需 userId、reason） | moderation |

</details>


---

## 报价相关

<details><summary>展开/折叠 报价相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/offers/accepted` | **GET** | 暂无说明 | offers |
| `/offers/active` | **GET** | 暂无说明 | offers |
| `/offers/declined` | **GET** | 暂无说明 | offers |
| `/offers/feed` | **GET** | 暂无说明 | offers |
| `/offers/for_guest` | **GET** | 暂无说明 | offers |
| `/offers/for_me` | **GET** | 暂无说明 | offers |
| `/offers/help` | **GET** | 暂无说明 | offers |
| `/offers/my_offers` | **GET** | 暂无说明 | offers |
| `/offers/sent_to_me` | **GET** | 暂无说明 | offers |
| `/offers/sent_to_others` | **GET** | 暂无说明 | offers |
| `/offers/user` | **GET** | 暂无说明 | offers |
| `/offers/user/activity` | **GET** | 暂无说明 | offers |
| `/offers/user/counter` | **POST** | 暂无说明 | offers |
| `/offers/user/decline` | **POST** | 暂无说明 | offers |
| `/offers/user/price_suggestions` | **GET** | 暂无说明 | offers |
| `/offers/user/send` | **POST** | 暂无说明 | offers |
| `/offers_help` | **GET** | 暂无说明 | offers |
| `/vm-rest/posts/{postId}/seller_offer` | **POST** | 卖家出价（支持折扣/运费优惠） | offers |
| `/vm-rest/users/{userId}/posts/{postId}/offers` | **POST** | 买家出价（offer_amount、products、支付方式等） | offers |

</details>


---

## 活动/Party相关

<details><summary>展开/折叠 活动/Party相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/vm-rest/parties/recent?domain={us}` | **GET** | 获取近期派对列表 | parties |
| `/vm-rest/posts/{listingId}/events/{eventId}` | **DELETE** | 管理员从 Party 移除商品 | parties |

</details>


---

## 点赞相关

<details><summary>展开/折叠 点赞相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/likes` | **GET** | 暂无说明 | likes |
| `/likes/users` | **GET** | 暂无说明 | likes |
| `/likes/users/offers` | **GET** | 暂无说明 | likes |
| `/vm-rest/posts/{postId}/likes` | **DELETE** | 取消点赞 | likes |
| `/vm-rest/posts/{postId}/likes` | **POST** | 点赞商品 | likes |
| `/vm-rest/posts/{postId}/likes?count={count}&max_id={maxId}` | **GET** | 获取点赞用户分页 | likes |

</details>


---

## 用户相关

<details><summary>展开/折叠 用户相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/users/community_feed` | **GET** | 暂无说明 | users |
| `/users/filtered` | **GET** | 暂无说明 | users |
| `/users/self/certificates/retail` | **GET** | 暂无说明 | users |
| `/users/self/closet_stats` | **GET** | 暂无说明 | users |
| `/users/suggested` | **GET** | 暂无说明 | users |
| `/users/suggested/activities/feed` | **GET** | 暂无说明 | users |
| `/users/update_ui_cookie` | **POST** | 暂无说明 | users |
| `/vm-rest/users/{listerId}` | **GET** | 获取卖家信息 | users |
| `/vm-rest/users/{listerId}/posts?exp=all&base_exp=all&app_version=2.55&summarize=true&count={N}` | **GET** | 获取卖家 Closet 商品 | users |

</details>


---

## 相似推荐相关

<details><summary>展开/折叠 相似推荐相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/related/posts/feed` | **GET** | 暂无说明 | related |
| `/related/posts/just_in` | **GET** | 暂无说明 | related |

</details>


---

## 社交/关注相关

<details><summary>展开/折叠 社交/关注相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/brands/following` | **GET** | 暂无说明 | social |
| `/followers` | **GET** | 与 /users/{id}/followers 结合使用 | social |
| `/following` | **GET** | 与 /users/{id}/followers 结合使用 | social |
| `/style_tags/following` | **GET** | 暂无说明 | social |

</details>


---

## 订单相关

<details><summary>展开/折叠 订单相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/orders` | **GET** | 暂无说明 | orders |
| `/orders/filters` | **GET** | 暂无说明 | orders |
| `/orders/help` | **GET** | 暂无说明 | orders |
| `/orders/labels` | **GET** | 暂无说明 | orders |
| `/orders/notifications` | **GET** | 暂无说明 | orders |
| `/orders/returns` | **GET** | 暂无说明 | orders |

</details>


---

## 认证相关

<details><summary>展开/折叠 认证相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/auth/users/access_token` | **POST** | 更新/重新获取访问令牌 | auth |
| `/auth/users/guest_viewed_posts` | **POST** | 暂无说明 | auth |
| `/auth/users/session` | **GET** | 会话检查 | auth |

</details>


---

## 评论相关

<details><summary>展开/折叠 评论相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/comments` | **GET** | 使用 “/posts/{postId}/comments” 路径来访问特定帖子的评论. | comments |
| `/current/comments` | **GET** | 暂无说明 | comments |
| `/vm-rest/posts/{postId}/comments` | **POST** | 添加评论 | comments |
| `/vm-rest/posts/{postId}/comments/{commentId}` | **DELETE** | 删除评论 | comments |
| `/vm-rest/users/{userId}/reported/posts/{postId}/comments/{commentId}?reason={reason}` | **PUT** | 举报评论（需 userId） | comments |

</details>


---

## 风险确认相关

<details><summary>展开/折叠 风险确认相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/acknowledgements/acknowledged/comment_risk` | **PUT** | 确认评论风险提示横幅 | acknowledgements |

</details>


---

## 验证相关

<details><summary>展开/折叠 验证相关 接口清单</summary>


| 接口路径 | 请求方式 | 说明 | 英文分类 |
|---|---|---|---|
| `/validations/users/email` | **POST** | 验证电子邮件 | validations |
| `/validations/users/referral_code` | **POST** | 暂无说明 | validations |
| `/validations/users/signup` | **POST** | 暂无说明 | validations |

</details>


---

## 通用说明

- **统一前缀**：大多数接口位于 `/vm-rest`，上传类在 `/api`。

- **版本参数**：几乎所有请求需要 `?pm_version=xxxx`（以页面实际为准）。

- **鉴权/头部**：同域 `Cookie` + `X-XSRF-TOKEN`（从 `<meta id="csrftoken">` 读取），建议带 `Accept: application/json`、`app-source: web-app`。

- **占位符**：`{postId}`=商品ID，`{userId}`=用户ID（通常为 `creator_id`），`{commentId}`=评论ID。

- **错误提示**：前端会对 `PostRemovedError`、`CommentingUnderReviewError` 等做特殊处理。


---

## 实战模板

### 浏览器 `fetch` 通用封装

```js
const PMV = '2025.35.1'; // 示例，按页面实际替换
function pmFetch(path, { method='GET', body } = {}) {
  const xsrf = document.querySelector('#csrftoken')?.content || '';
  const url = path.includes('?') ? `${path}&pm_version=${PMV}` : `${path}?pm_version=${PMV}`;
  return fetch(url, {
    method,
    credentials: 'same-origin',
    headers: {
      'Accept': 'application/json',
      'X-XSRF-TOKEN': xsrf,
      ...(body ? { 'Content-Type': 'application/json' } : {})
    },
    ...(body ? { body: JSON.stringify(body) } : {})
  }).then(r => r.json());
}

// 示例：先查商品，再查审核详情
pmFetch(`/vm-rest/posts/${postId}`)
  .then(p => pmFetch(`/vm-rest/users/${p.creator_id}/moderation/post`))
  .then(console.log)
  .catch(console.error);
```


### `curl` 模板

```bash
PMV=2025.35.1 # 示例
curl -H "Accept: application/json" \
     -H "X-XSRF-TOKEN: <XSRF>" \
     -b "<your_cookie_here>" \
     "https://poshmark.com/vm-rest/posts/{postId}?pm_version=${PMV}"
```
