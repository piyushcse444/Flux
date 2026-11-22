1) update comfyui and download ComfyUI_PuLID_Flux_ll from extension.

2)  If your workflow uses FLUX.1, use PuLID-FLUX v0.9.1.
    If it uses FLUX.2 Klein and you’ve installed the matching custom nodes, use that project’s FLUX.2 PuLID model.

    New-Item -ItemType Directory -Force .\models\pulid | Out-Null

    hf download guozinan/PuLID pulid_flux_v0.9.1.safetensors `
    --local-dir .\models\pulid

    hf download Fayens/Pulid-Flux2 pulid_flux2_klein_v2.safetensors `
    --local-dir .\models\pulid

3) nodes to use :- 
        1) pulid flux model loader   -> PuLID pulid_flux_v0.9.1.safetensors
        2) pulid flux insight face loader ->    cpu, cuda
        3) pulid flux eva clip loader -> eva clip

        4) apply pulid flux:-

            input :-
                    1) model -> load diffusion model
                    2) pulid flux -> pulid flux model loader 
                    3) eva_clip -> pulid flux eva clip loader 
                    4) face_analysis -> pulid flux insight face loader
                    5) image -> the input image
            output :-
                    1) model -> ksampler model        
