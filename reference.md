# Reference
## Brains
<details><summary><code>client.brains.<a href="src/livingbrain/brains/client.py">list</a>() -> typing.List[Brain]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List every brain owned by the calling subject, most recently updated first.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.brains.list()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.brains.<a href="src/livingbrain/brains/client.py">create</a>(...) -> Brain</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new brain for the calling subject. A brain is an isolated knowledge vault: every capture, page, and connection belongs to exactly one brain. The `x-subject-id` header determines who owns it.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.brains.create(
    name="Customer Memory",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `str` — User-facing name of the brain
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Optional description
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.brains.<a href="src/livingbrain/brains/client.py">bulk_stats</a>(...) -> typing.Dict[str, BrainStats]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Aggregate counts for many brains in one round trip. Pass a comma-separated `ids` list; brains the caller cannot access are omitted rather than erroring.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.brains.bulk_stats()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ids:** `typing.Optional[str]` — Comma-separated brain ids, e.g. `ids=a,b,c`. Unowned ids are omitted.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.brains.<a href="src/livingbrain/brains/client.py">get</a>(...) -> Brain</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a single brain by ID, including its name, description, and brief settings.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.brains.get(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.brains.<a href="src/livingbrain/brains/client.py">remove</a>(...) -> DeleteResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently delete a brain along with all of its pages, sources, connections, and change history. This cannot be undone.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.brains.remove(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.brains.<a href="src/livingbrain/brains/client.py">update</a>(...) -> Brain</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a brain's mutable fields, such as its name or description. Omitted fields are left unchanged.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.brains.update(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — New name
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — New description
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.brains.<a href="src/livingbrain/brains/client.py">stats</a>(...) -> BrainStats</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Aggregate counts for a single brain — pages, sources, connections, and unacknowledged changes. Useful for dashboard headline numbers.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.brains.stats(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.brains.<a href="src/livingbrain/brains/client.py">update_brief_settings</a>(...) -> Brain</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update the daily-brief schedule and delivery settings for a brain, including whether briefs are enabled and what time they are generated.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.brains.update_brief_settings(
    brain_id="brainId",
    brief_settings={
        "enabled": True,
        "hour_local": 7,
        "timezone": "Europe/Helsinki"
    },
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**brief_settings:** `BriefSettings` — New daily-brief settings. Replaces the existing configuration.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.brains.<a href="src/livingbrain/brains/client.py">run_brief</a>(...) -> BriefRunResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Generate this brain's daily brief immediately instead of waiting for its scheduled run. Returns the brief content once generation completes.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.brains.run_brief(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Captures
<details><summary><code>client.captures.<a href="src/livingbrain/captures/client.py">capture</a>(...) -> IngestSource</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Push a single item into a brain for ingestion. Accepts notes, URLs, raw text, chat transcripts, and PDF/DOCX/PPTX documents. Capture is asynchronous: this returns an ingest source whose `status` you can poll or receive via webhook.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain, CaptureRequestKind
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.captures.capture(
    brain_id="brainId",
    kind=CaptureRequestKind.NOTE,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request:** `CaptureRequest` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.captures.<a href="src/livingbrain/captures/client.py">capture_batch</a>(...) -> CaptureBatchResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Push many captures in a single request. Each item is processed independently, so a malformed entry fails on its own without rejecting the whole batch.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain, CaptureRequestKind
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.captures.capture_batch(
    brain_id="brainId",
    items=[
        {
            "kind": CaptureRequestKind.NOTE,
            "content": "First note"
        },
        {
            "kind": CaptureRequestKind.NOTE,
            "content": "Second note"
        }
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**items:** `typing.List[CaptureRequest]` — Captures to ingest
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.captures.<a href="src/livingbrain/captures/client.py">capture_chat_turn</a>(...) -> CaptureChatTurnResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Submit a single chat turn for worthiness classification. The service decides whether the turn contains durable knowledge and only captures it if so, which keeps conversational filler out of the brain.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment
from livingbrain.captures import CaptureChatTurnRequestSender

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.captures.capture_chat_turn(
    brain_id="brainId",
    text="I just closed the Series A, focus shifts to hiring engineers.",
    sender=CaptureChatTurnRequestSender.USER,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**text:** `str` — Raw chat turn text
    
</dd>
</dl>

<dl>
<dd>

**sender:** `CaptureChatTurnRequestSender` — Who produced the turn
    
</dd>
</dl>

<dl>
<dd>

**agent_name:** `typing.Optional[str]` — Agent display name for classifier context
    
</dd>
</dl>

<dl>
<dd>

**origin_ref:** `typing.Optional[str]` — Idempotency key for the turn (e.g. chat:<id>:<ts>)
    
</dd>
</dl>

<dl>
<dd>

**source:** `typing.Optional[Source]` — Opaque provenance
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.captures.<a href="src/livingbrain/captures/client.py">list_sources</a>(...) -> SourceList</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List ingest sources for a brain, optionally filtered by processing status. Use this to surface an ingestion queue or to find sources that failed to compile.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.captures.list_sources(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**status:** `typing.Optional[ListSourcesCapturesRequestStatus]` 
    
</dd>
</dl>

<dl>
<dd>

**ids:** `typing.Optional[str]` — Comma-separated source ids for a targeted lookup (e.g. resolving a page’s source refs regardless of age)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.captures.<a href="src/livingbrain/captures/client.py">retry_source</a>(...) -> SourceRetryResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retry compiling an ingest source that previously failed. Only sources in a failed state can be retried.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.captures.retry_source(
    brain_id="brainId",
    source_id="sourceId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**source_id:** `str` — Ingest source id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.captures.<a href="src/livingbrain/captures/client.py">remove_source</a>(...) -> DeleteResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete an ingest source. Pages already derived from the source are retained unless you delete them separately.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.captures.remove_source(
    brain_id="brainId",
    source_id="sourceId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**source_id:** `str` — Ingest source id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Workspace
<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">search_pages</a>(...) -> typing.List[SearchResult]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Search pages using combined semantic and keyword matching. Results are ranked by relevance and include a snippet showing why each page matched.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.search_pages(
    brain_id="brainId",
    query="what does the customer care about?",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**query:** `str` — Search query
    
</dd>
</dl>

<dl>
<dd>

**top_k:** `typing.Optional[int]` — Max results
    
</dd>
</dl>

<dl>
<dd>

**min_similarity:** `typing.Optional[float]` — Minimum similarity (0-1)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">index</a>(...) -> typing.List[IndexEntry]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return a compact index of the brain's top pages, formatted for injection into an LLM prompt. This is the intended way to give an agent working context without sending the whole brain.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.index(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">graph</a>(...) -> Graph</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return a renderable subgraph of nodes and edges for visualizing how the brain's pages relate. Use `nodeLimit` to keep the payload small enough to draw.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.graph(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**node_limit:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">list_pages</a>(...) -> PageList</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List pages in a brain with offset pagination. Filter by bucket or status, and optionally include deprecated pages that are normally hidden.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.list_pages(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**include_deprecated:** `typing.Optional[bool]` 
    
</dd>
</dl>

<dl>
<dd>

**include_archived:** `typing.Optional[bool]` — Include archived pages in the results. Archived pages are hidden from lists and search by default.
    
</dd>
</dl>

<dl>
<dd>

**bucket:** `typing.Optional[ListPagesWorkspaceRequestBucket]` 
    
</dd>
</dl>

<dl>
<dd>

**status:** `typing.Optional[ListPagesWorkspaceRequestStatus]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">buckets</a>(...) -> typing.Dict[str, int]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return per-bucket page counts for the brain — the fastest way to render bucket navigation with badges.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.buckets(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">get_page</a>(...) -> Page</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Read a single page by slug. This bumps the page's `lastReferencedAt`, which feeds the brain health score — use it when a human or agent actually consumes the content.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.get_page(
    brain_id="brainId",
    slug="slug",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**slug:** `str` — Page slug
    
</dd>
</dl>

<dl>
<dd>

**include_deprecated:** `typing.Optional[bool]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">delete_permanently</a>(...) -> PageDeleteResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently delete a page and every record that depends on it, including its versions and connections. This cannot be undone.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment
from livingbrain.workspace import DeletePermanentlyWorkspaceRequestPermanent

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.delete_permanently(
    brain_id="brainId",
    slug="slug",
    permanent=DeletePermanentlyWorkspaceRequestPermanent.TRUE,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**slug:** `str` — Page slug
    
</dd>
</dl>

<dl>
<dd>

**permanent:** `DeletePermanentlyWorkspaceRequestPermanent` — Explicit irreversible-deletion confirmation
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">page_versions</a>(...) -> typing.List[PageVersion]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List a page's version history, newest first. Every content edit and automated recompile produces a version.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.page_versions(
    brain_id="brainId",
    slug="slug",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**slug:** `str` — Page slug
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">page_connections</a>(...) -> PageConnections</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List the connections attached to a single page, with the related page inlined on each connection.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.page_connections(
    brain_id="brainId",
    slug="slug",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**slug:** `str` — Page slug
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">edit_content</a>(...) -> Page</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Manually overwrite a page's content. This creates a new version, so the previous content stays retrievable through the version history.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.edit_content(
    brain_id="brainId",
    slug="slug",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**slug:** `str` — Page slug
    
</dd>
</dl>

<dl>
<dd>

**title:** `typing.Optional[str]` — Human-readable title.
    
</dd>
</dl>

<dl>
<dd>

**summary:** `typing.Optional[str]` — Short generated summary of the content.
    
</dd>
</dl>

<dl>
<dd>

**body:** `typing.Optional[str]` — New page content. Replaces the existing body and creates a new version.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">move_bucket</a>(...) -> Page</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Move a page into a different bucket. Buckets are the brain's top-level organizational grouping.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment
from livingbrain.workspace import MovePageBucketRequestBucket

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.move_bucket(
    brain_id="brainId",
    slug="slug",
    bucket=MovePageBucketRequestBucket.INBOX,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**slug:** `str` — Page slug
    
</dd>
</dl>

<dl>
<dd>

**bucket:** `MovePageBucketRequestBucket` — Top-level grouping the page belongs to.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">pin</a>(...) -> Page</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Pin or unpin a page. Pinned pages are prioritized in the prompt index and are exempt from deprecation.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.pin(
    brain_id="brainId",
    slug="slug",
    pinned=True,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**slug:** `str` — Page slug
    
</dd>
</dl>

<dl>
<dd>

**pinned:** `bool` — Pin or unpin
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">rename</a>(...) -> Page</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Rename a page's title and slug. Existing connections follow the page, but any external references to the old slug will break.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.rename(
    brain_id="brainId",
    slug="slug",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**slug:** `str` — Page slug
    
</dd>
</dl>

<dl>
<dd>

**title:** `typing.Optional[str]` — Human-readable title.
    
</dd>
</dl>

<dl>
<dd>

**new_slug:** `typing.Optional[str]` — New URL-safe slug. External references to the old slug will stop resolving.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">archive</a>(...) -> Page</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Archive a page. Archived pages are hidden from lists and search until restored, but their content, versions, and connections are kept. Use `restore` to bring the page back.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.archive(
    brain_id="brainId",
    slug="slug",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**slug:** `str` — Page slug
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">restore</a>(...) -> Page</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Restore an archived page and return it to active status, so it reappears in lists and search.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.restore(
    brain_id="brainId",
    slug="slug",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**slug:** `str` — Page slug
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">recover</a>(...) -> Page</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Recover a deprecated page and return it to active status.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.recover(
    brain_id="brainId",
    slug="slug",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**slug:** `str` — Page slug
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">resolve</a>(...) -> Page</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Resolve a contested page. A page becomes contested when newly captured material contradicts what the page already asserts; resolving records which version wins.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.resolve(
    brain_id="brainId",
    slug="slug",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**slug:** `str` — Page slug
    
</dd>
</dl>

<dl>
<dd>

**resolution:** `typing.Optional[str]` — Resolution note
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">reviewed</a>(...) -> Page</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Legacy alias for recovering a deprecated page. Prefer `recover` in new code; this endpoint is retained for backwards compatibility.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.reviewed(
    brain_id="brainId",
    slug="slug",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**slug:** `str` — Page slug
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">changes</a>(...) -> ChangeList</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List change-feed events with offset pagination. This is the primary way to sync an external system: poll with `since`, or filter to `unackedOnly` to build an inbox.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.changes(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**unacked_only:** `typing.Optional[bool]` 
    
</dd>
</dl>

<dl>
<dd>

**page_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**since:** `typing.Optional[str]` — ISO timestamp
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">ack_change</a>(...) -> ChangeEvent</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Acknowledge a single change event, removing it from unacknowledged views.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.ack_change(
    brain_id="brainId",
    change_id="changeId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**change_id:** `str` — Change event id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">ack_all</a>(...) -> AckAllResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Acknowledge every outstanding change event in one call, and return how many were cleared.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.ack_all(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">list_connections</a>(...) -> ConnectionList</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List connections across the whole brain with offset pagination. Filter by strength, or restrict to connections the user has not yet dismissed.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.list_connections(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**unacked_only:** `typing.Optional[bool]` 
    
</dd>
</dl>

<dl>
<dd>

**strength:** `typing.Optional[ListConnectionsWorkspaceRequestStrength]` — Minimum strength (inclusive)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">ack_connection</a>(...) -> Connection</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Dismiss a connection so it stops appearing in unacknowledged views. The connection itself is preserved.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.ack_connection(
    brain_id="brainId",
    connection_id="connectionId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**connection_id:** `str` — Connection id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">get_score</a>(...) -> BrainScore</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return the brain's health score with its contributing factors and metrics. The score reflects coverage, freshness, and connectedness.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.get_score(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">score_history</a>(...) -> ScoreHistory</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return the score trend over a time range, including the delta versus the start of the period.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.score_history(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**range:** `typing.Optional[ScoreHistoryWorkspaceRequestRange]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">score_suggestions</a>(...) -> ScoreSuggestions</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return concrete, ranked suggestions for raising the brain's health score, derived from whichever factors are currently weakest.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.score_suggestions(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">get_profile</a>(...) -> typing.Optional[BrainProfile]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return the brain profile — the standing directives and context that shape how the brain interprets and organizes new captures.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.get_profile(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">update_profile</a>(...) -> BrainProfile</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update the brain profile's directives. These take effect on subsequent captures, not retroactively.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.update_profile(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**who_they_are:** `typing.Optional[str]` — Who the subject is. Omit to leave unchanged.
    
</dd>
</dl>

<dl>
<dd>

**what_they_do:** `typing.Optional[str]` — What the subject works on. Omit to leave unchanged.
    
</dd>
</dl>

<dl>
<dd>

**focus:** `typing.Optional[str]` — Current focus. Omit to leave unchanged.
    
</dd>
</dl>

<dl>
<dd>

**goals:** `typing.Optional[str]` — Current goals. Omit to leave unchanged.
    
</dd>
</dl>

<dl>
<dd>

**current_projects:** `typing.Optional[str]` — Projects in flight. Omit to leave unchanged.
    
</dd>
</dl>

<dl>
<dd>

**stuck_on:** `typing.Optional[str]` — Known blockers. Omit to leave unchanged.
    
</dd>
</dl>

<dl>
<dd>

**vault_organization:** `typing.Optional[str]` — Organization preference. Omit to leave unchanged.
    
</dd>
</dl>

<dl>
<dd>

**directives:** `typing.Optional[ProfileDirectives]` — Standing instructions. Omit to leave unchanged.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">profile_suggestions</a>(...) -> ProfileSuggestions</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Suggest profile fields inferred from what the brain already contains. Best-effort: returns an empty set when there is not yet enough signal.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.profile_suggestions(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.workspace.<a href="src/livingbrain/workspace/client.py">export_markdown</a>(...) -> MarkdownExport</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export the entire brain as a single markdown bundle, suitable for backup or for handing to another tool.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.workspace.export_markdown(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**include_deprecated:** `typing.Optional[bool]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Webhooks
<details><summary><code>client.webhooks.<a href="src/livingbrain/webhooks/client.py">list</a>() -> typing.List[WebhookSubscription]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all webhook subscriptions for the calling subject. Signing secrets are not included.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.webhooks.list()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.webhooks.<a href="src/livingbrain/webhooks/client.py">create</a>(...) -> CreateWebhookResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Register a webhook endpoint and receive its signing secret. The secret is returned only on creation — store it immediately, as it cannot be retrieved again.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.webhooks.create(
    url="https://your-app.com/webhooks/living-brain",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**url:** `str` — HTTPS endpoint to deliver events to
    
</dd>
</dl>

<dl>
<dd>

**events:** `typing.Optional[typing.List[CreateWebhookRequestEventsItem]]` — Event types to subscribe to; empty = all
    
</dd>
</dl>

<dl>
<dd>

**secret:** `typing.Optional[str]` — Signing secret to use for this subscription. When omitted a random secret is generated and returned once. Hosts that verify deliveries against a pre-configured secret (e.g. an env var) should pass it here so signatures match. Write-only: never returned on reads.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.webhooks.<a href="src/livingbrain/webhooks/client.py">remove</a>(...) -> DeleteResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a webhook subscription. Deliveries stop immediately.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.webhooks.remove(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Webhook subscription id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.webhooks.<a href="src/livingbrain/webhooks/client.py">update</a>(...) -> WebhookSubscription</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a webhook subscription's URL or subscribed event types. The signing secret is unchanged.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.webhooks.update(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Webhook subscription id
    
</dd>
</dl>

<dl>
<dd>

**url:** `typing.Optional[str]` — New delivery URL. Omit to leave unchanged.
    
</dd>
</dl>

<dl>
<dd>

**events:** `typing.Optional[typing.List[UpdateWebhookRequestEventsItem]]` — New event list. Replaces the existing subscription set. Omit to leave unchanged.
    
</dd>
</dl>

<dl>
<dd>

**active:** `typing.Optional[bool]` — Set false to pause deliveries without deleting the subscription.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Telegram
<details><summary><code>client.telegram.<a href="src/livingbrain/telegram/client.py">status</a>(...) -> typing.Optional[TelegramConnection]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return the current Telegram bot connection status for a brain, including the connected bot's username when one is linked.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.telegram.status(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.telegram.<a href="src/livingbrain/telegram/client.py">connect</a>(...) -> TelegramConnection</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Connect a Telegram bot to a brain so messages sent to the bot are captured automatically.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.telegram.connect(
    brain_id="brainId",
    bot_token="123456:ABC-DEF...",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**bot_token:** `str` — BotFather bot token to connect to this brain
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.telegram.<a href="src/livingbrain/telegram/client.py">disconnect</a>(...) -> TelegramDisconnectResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Disconnect the Telegram bot from a brain. Already-captured messages are retained.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.telegram.disconnect(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Slack
<details><summary><code>client.slack.<a href="src/livingbrain/slack/client.py">status</a>(...) -> SlackStatus</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return every Slack workspace installed for a brain along with its channel bindings. Use the installation IDs returned here to list channels or create bindings.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.slack.status(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.slack.<a href="src/livingbrain/slack/client.py">start_oauth</a>(...) -> SlackOAuthStartResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a signed Slack OAuth installation URL for a brain. Redirect the user to `authorizationUrl`; Slack sends them back to your redirect URL with a `code` and `state` to pass to `confirmOauth`. The signed state expires at `expiresAt`.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.slack.start_oauth(
    brain_id="brainId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.slack.<a href="src/livingbrain/slack/client.py">confirm_oauth</a>(...) -> SlackOAuthConfirmResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Complete a Slack installation by exchanging the `code` and `state` Slack returned to your redirect URL. Returns the new installation ID.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.slack.confirm_oauth(
    brain_id="brainId",
    code="code",
    state="state",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**code:** `str` — Slack authorization code
    
</dd>
</dl>

<dl>
<dd>

**state:** `str` — Signed OAuth state
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.slack.<a href="src/livingbrain/slack/client.py">channels</a>(...) -> typing.List[SlackChannel]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List the channels visible to the Living Brain bot in a Slack installation. `isMember` tells you whether the bot has already been added to the channel.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.slack.channels(
    brain_id="brainId",
    installation_id="installationId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**installation_id:** `str` — Slack installation id returned by the status endpoint
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.slack.<a href="src/livingbrain/slack/client.py">bind</a>(...) -> SlackBinding</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Connect a Slack channel to a brain so it receives brain notifications. Configure which notifications it receives with `updateBinding`.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.slack.bind(
    brain_id="brainId",
    installation_id="installationId",
    channel_id="C0123456789",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**installation_id:** `str` — Slack installation id
    
</dd>
</dl>

<dl>
<dd>

**channel_id:** `str` — Slack channel id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.slack.<a href="src/livingbrain/slack/client.py">unbind</a>(...) -> SlackDisconnectResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Disconnect a single Slack channel from a brain. The Slack installation and any other bindings are unaffected.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.slack.unbind(
    brain_id="brainId",
    binding_id="bindingId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**binding_id:** `str` — Slack channel binding id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.slack.<a href="src/livingbrain/slack/client.py">update_binding</a>(...) -> SlackBinding</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update which notifications a bound Slack channel receives — daily briefs, new connections, and page changes. Omitted fields are left unchanged.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.slack.update_binding(
    brain_id="brainId",
    binding_id="bindingId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**binding_id:** `str` — Slack channel binding id
    
</dd>
</dl>

<dl>
<dd>

**notify_briefs:** `typing.Optional[bool]` — Receive daily summary of brain updates
    
</dd>
</dl>

<dl>
<dd>

**notify_connections:** `typing.Optional[bool]` — Get notified when strong new connections are discovered
    
</dd>
</dl>

<dl>
<dd>

**notify_changes:** `typing.Optional[bool]` — Get notified when pages are updated with new knowledge
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.slack.<a href="src/livingbrain/slack/client.py">disconnect_installation</a>(...) -> SlackDisconnectResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Disconnect a Slack workspace from a brain and remove all of its channel bindings.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from livingbrain import LivingBrain
from livingbrain.environment import LivingBrainEnvironment

client = LivingBrain(
    api_key="<value>",
    subject_id="<x-subject-id>",
    environment=LivingBrainEnvironment.PRODUCTION,
)

client.slack.disconnect_installation(
    brain_id="brainId",
    installation_id="installationId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**brain_id:** `str` — Brain id
    
</dd>
</dl>

<dl>
<dd>

**installation_id:** `str` — Slack installation id
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

