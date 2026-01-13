### 🔄 Current Status: Smart Structure-Aware Chunking

The core logic is as follows:

1. **Heading-based Partitioning**
* Uses `#` through `###` as natural boundaries. Priority is given to maintaining the integrity of content under the same subheading.


2. **Contextual Inheritance & Breadcrumbs**
* **Implementation**: Each chunk automatically injects its corresponding heading path.
* **Example**: `[User Center -> API Docs -> Login API]: These are the specific parameter descriptions...`
* **Value**: Even if a chunk is retrieved in isolation, the Agent can instantly identify its semantic context via the prefix.


3. **Boundary Protection**
* **Code Block Protection**: Uses Regex to identify ````` symbols, strictly prohibiting splits within code blocks to ensure logical integrity.
* **Table Protection**: Identifies Markdown table structures to ensure a single row of data is never split across two chunks.


4. **Metadata Enrichment**
* Each chunk automatically carries tags for downstream metadata filtering, including:
* `source_file`: Original file path.
* `breadcrumb`: Heading path (Format: Filename > Parent Heading > Subheading).
* `parent_header`: Path of the parent heading.
* `heading`: Current heading title.
* `heading_level`: Heading level (1–6).
* `format`: File format (e.g., Markdown).
* `inherited_heading`: Boolean flag indicating if the heading was inherited.
