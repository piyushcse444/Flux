1) model name :- kpsss34/FHDR_Uncensored

2) downlaod -> text_encoder, vae and any of the model (FHDR_ComfyUI-Q4_K_M.gguf, FHDR_ComfyUI-Q8_0.gguf, FHDR_ComfyUI.safetensors) and t5xxl_fp16.safetensors (text encoder)

3) put FHDR_ComfyUI.safetensors inside /model/diffusion_model or gguf in /model/unet and load with load diffusion model node.

4) put text_encoder and t5xxl_fp16.safetensors in /model/text_encoder and load with load clip(dual)

5) put vae in /model/vae and load with load vae
