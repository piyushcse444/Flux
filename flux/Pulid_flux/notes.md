1) PuLID-Flux is a ComfyUI method for generating images that keep a person’s identity recognizable from a reference photo. 

2) It works with FLUX and is tuning-free: you don’t need to train a LoRA first. 

3) The original PuLID approach was designed to preserve identity while keeping the base model’s usual prompt-following behavior. PuLID paper

Workflow :-

    1) PuLIDFluxModelLoader  -> loads the PuLID weights (pulid_flux_v0.9.1.safetensors).
    
    2) PulidFluxEvaClipLoader and PulidFluxInsightFaceLoader ->  provide models that analyze the reference face.

    3) ApplyPulidFlux combines those face features with the FLUX model, reference image, and face analysis. The three number controls adjust how PuLID is applied; their exact meaning depends on the custom-node version.

    4) You’d feed a clear face photo into the workflow, then describe the scene, clothing, pose, or style in the prompt. PuLID tries to carry the person’s identity into that new image; it isn’t simply pasting the original face onto another picture. Results vary with the reference photo and settings, and strong identity settings can make the prompt less flexible.

    5)     

