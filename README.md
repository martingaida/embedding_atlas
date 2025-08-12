# Pinecone Embedding Atlas: Interactive Vector Visualization

This notebook demonstrates how to:
- Set up and connect to Pinecone vector database with flexible namespace support
- Fetch and process vectors from default, specific, or all namespaces
- Create interactive visualizations using the [**Embedding Atlas**](https://apple.github.io/embedding-atlas/)
- Compute text projections and display embedding relationships
- Handle large-scale vector operations with batch processing

## Prerequisites
- Pinecone API key and index setup
- Environment variables configured in `.env` file (see `.env.example`)
- Required Python packages installed
- Vectors already stored in your Pinecone index

# Namespace configuration (optional)
```bash
PINECONE_NAMESPACE=""        # Default: empty string (default namespace)
#PINECONE_NAMESPACE="all"     # Fetch from all namespaces
#PINECONE_NAMESPACE="prod"    # Fetch from specific namespace

# Limit number of vectors to fetch
MAX_COUNT=1000               # Set to integer or leave unset/set to None for all vectors
```

## Notebook Structure
1. **Package Installation** - Install required dependencies
2. **Environment Setup** - Load configuration and validate settings
3. **Pinecone Connection** - Initialize client and verify index access
4. **Namespace Configuration** - Set up flexible namespace handling
5. **Vector Retrieval** - Retrieve vectors from configured namespaces
6. **Data Processing** - Convert vectors to DataFrame for analysis
7. **Basic Visualization** - Create EmbeddingAtlasWidget without projections
8. **Text Projection** - Compute and visualize embedding projections
9. **Advanced Visualization** - Interactive widget with full functionality

## Key Features

### Flexible Namespace Support
- **Default**: Fetch from default namespace (empty string)
- **All**: Fetch from all available namespaces
- **Specific**: Fetch from a named namespace
- Automatic fallback to default if specified namespace doesn't exist

### Batch Processing
- Efficient fetching of large vector collections
- Configurable batch sizes for optimal performance
- Progress tracking with detailed logging

### Interactive Visualizations
- Table view of vector metadata
- Charts and statistics
- 2D embedding projections
- Text-based similarity exploration

## Important Notes

**Widget Loading**: If you see "Widgets require us to download supporting files from a 3rd party website", click `OK` to enable the interactive visualizations.

**Performance**: For large datasets, consider setting `MAX_COUNT` to limit the number of vectors processed initially.

**Namespace Strategy**: 
- Use `""` (default) for development and testing
- Use specific namespaces for production data separation
- Use `"all"` for comprehensive analysis across all data

## Troubleshooting

- **No vectors found**: Verify your index contains data and namespace configuration is correct
- **Connection errors**: Check your API key and network connectivity
- **Widget not loading**: Ensure you have the latest version of `embedding-atlas` installed
- **Memory issues**: Reduce `MAX_COUNT` or process data in smaller batches

Ready to explore your vector database? Let's get started! 🚀