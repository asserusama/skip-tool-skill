# List (SwiftUI)

SkipUI supports SwiftUI `List` on Android. Use `List { ... }` with static content, `ForEach`, or `Section` for sectioned lists. Use `.listStyle(.plain)` (or other supported styles) as needed. For dynamic content, give `ForEach` stable identity (e.g. by `id: \.id` on identifiable items); avoid `ForEach(collection.indices)`. Edit actions (e.g. swipe to delete, move) are supported; see SkipUI docs for patterns. List maps to Compose `LazyColumn`/equivalent on Android.
