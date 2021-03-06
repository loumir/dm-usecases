# Mango Proposal for the `Combined Data` Case


## `4xmm_litewithsp.annot.xml`

- This the annotated version of `4xmm_lite.xml`
- Raw data are mapped on the `MANGO` model
- The annotation syntax is this proposed as `ModelInstaceInVoT`
    - One annotation block on the top of the VOTable
    - One section with all the coordinate systems
        - Standard systems (e.g. ICRS) are just named
        - Specific system (energy band, flag values) are totally described
        - All are instances of MANGO classes
    - One section with the mapping of the data table
        - One instance per parameters
        - The content of this section denotes the model structure
    - The Spectra table is joined to the Result table by the `JOIN` mechanism of `ModelInstaceInVoT`
    
** Watchout** 
- Some class names can differ from the last MANGO proposal
- It is to be noted that the semantic fields are not properly set

The demo client (`ModelInstanceInVot/python_workflow/python/client/demo/4xmm_litewithsp.py`) can generate one JSON serialization for each data row. These MANGO instance can be processed as dictionaries by any language. 
        
`4xmm_litewithsp.mangoinstance.json` contains that serialization for the first row
- Source parameters are in the `mango:MangoObject.parameters` block of the instance.
- Spectra are in the `mango:MangoObject.associatedData` block of the instance.
- This instance has been generated with the `resolve_refs` flag, the frame instances are copied into the row instance. 
