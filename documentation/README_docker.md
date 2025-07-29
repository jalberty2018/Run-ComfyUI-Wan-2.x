# Run ComfyUI Wan2.x with Custom nodes on [RunPod.io](https://runpod.io?ref=se4tkc5o)

## Synopsis

This project downloads models as specified in the **environment variables** set in the templates.  

- Models and loras are automatically downloaded based on the specified paths in the environment configuration.  
- Authentication credentials can be set via secrets for:  
  - **Code server** authentication (not possible to switch off) 
  - **Hugging Face** and **CivitAI** tokens for model access.  

Ensure that the required environment variables and secrets are correctly set before running the pod.
See below for options.

## Hardware Requirements  
 
- **Recommended GPUs**: L40S, L40, RTX 6000 Ada  
- **Storage**:  
  - **Volume**: 75GB (`/workspace`)  
  - **Pod Volume**: 10GB  

## Template [RunPod.io](https://runpod.io?ref=se4tkc5o)

- [template](https://runpod.io/console/deploy?template=9edjw7pg7h&ref=se4tkc5o)

## Workflows & Tutorials  

- [wan-video](https://wan.video/)
- [Wiki](https://comfyui-wiki.com/en/tutorial/advanced/wan21-video-model)
- [Enhance a Video](https://oahzxl.github.io/Enhance_A_Video/)  
- [ComfyUI 2.1](https://comfyanonymous.github.io/ComfyUI_examples/wan/)
- [ComfyUI 2.2](https://comfyanonymous.github.io/ComfyUI_examples/wan22/
- [AccVideo](https://github.com/aejion/AccVideo)
- [CausVid](https://github.com/tianweiy/CausVid)
- [NAG](https://chendaryen.github.io/NAG.github.io/)
- [vace](https://docs.comfy.org/tutorials/video/wan/vace)
- [Phantom](https://github.com/Phantom-video/Phantom)
- [FusionX Lora](https://civitai.com/models/1681541?modelVersionId=1903277)

## Workflow

- Example Text to video workflow using available custom nodes in /workspace/ComfyUI/user/default/workflows
- Open workflow from ComfyUI's interface on the left. 

## Models

### Sources  

- [Wan-Video Github](https://github.com/Wan-Video)
- [Wan-AI Huggingface](https://huggingface.co/Wan-AI)  
- [WAN-VACE Github](https://github.com/ali-vilab/VACE)
- [FusionX Huggingface](https://huggingface.co/vrgamedevgirl84/Wan14BT2VFusioniX)
- [MoviiGen Huggingface](https://huggingface.co/ZuluVision/MoviiGen1.1)
- [Fun](https://huggingface.co/collections/alibaba-pai/wan21-fun-v11-680f514c89fe7b4df9d44f17)
- [alibaba-pai](https://huggingface.co/collections/alibaba-pai/wan21-fun-67e4fb3b76ca01241eb7e334)
- [Kijai](https://huggingface.co/Kijai/WanVideo_comfy)

## Software Repositories  

### Core  

- [ComfyUI](https://github.com/comfyanonymous/ComfyUI)  
- [Code Server](https://github.com/coder/code-server)  
- [HuggingFace cli](https://huggingface.co/docs/huggingface_hub/guides/cli)


### Custom Nodes ComfyUI 

#### Full list

- [awesome-comfyui](https://awesome-comfyui.rozenlaan.site)

#### Installed

- [rgthree](https://github.com/rgthree/rgthree-comfy)  
- [Login](https://github.com/liusida/ComfyUI-Login)  
- [Manager](https://github.com/ltdrdata/ComfyUI-Manager)  
- [Video Helper Suite](https://github.com/kosinkadink/ComfyUI-VideoHelperSuite)
- [KJNodes](https://github.com/kijai/ComfyUI-KJNodes)  
- [Frame Interpolation](https://github.com/Fannovel16/ComfyUI-Frame-Interpolation)
- [TeaCache](https://github.com/welltop-cn/ComfyUI-TeaCache)
- [Wrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper)
- [StartEndFrame](https://github.com/Flow-two/ComfyUI-WanStartEndFramesNative)
- [VideoUpscale with Model](https://github.com/ShmuelRonen/ComfyUI-VideoUpscale_WithModel)
- [RES4LYF](https://github.com/ClownsharkBatwing/RES4LYF)
- [Noise](https://github.com/BlenderNeko/ComfyUI_Noise)
- [NAG](https://github.com/ChenDarYen/ComfyUI-NAG)
- [vrgamedevgirl](https://github.com/vrgamegirl19/comfyui-vrgamedevgirl)
- [controlnet_aux](https://github.com/Fannovel16/comfyui_controlnet_aux)
- [SuperUltimateVaceTools](https://github.com/bbaudio-2025/ComfyUI-SuperUltimateVaceTools)

## Environment Variables  

### **ComfyUI Arguments**  

| Token        | Environment Variable     |
|--------------|--------------------------|
| Arguments    | `COMFYUI_EXTRA_ARGUMENTS`|

### **Authentication Tokens**  

| Token        | Environment Variable |
|--------------|----------------------|
| Civitai      | `CIVITAI_TOKEN`      |
| Huggingface  | `HF_TOKEN`           |
| Code Server  | `PASSWORD`           |

### **Diffusion Models Setup Huggingface**  

| Model Type        | Model                         | Safetensors                               |
|-------------------|-------------------------------|-------------------------------------------| 
| Diffusion Model   | `HF_MODEL_DIFFUSION[1-2]`          | `HF_MODEL_DIFFUSION_MODELS_SAFETENSORS[1-2]`|
| Checkpoints       | `HF_MODEL_CHECKPOINTS`        | `HF_MODEL_CHECKPOINTS_SAFETENSORS`        |
| Text Encoders     | `HF_MODEL_TEXT_ENCODERS[1-2]` | `HF_MODEL_TEXT_ENCODERS_SAFETENSORS[1-2]` |
| Clip Vision       | `HF_MODEL_CLIP_VISION`        | `HF_MODEL_CLIP_VISION_SAFETENSORS` |
| VAE               | `HF_MODEL_VAE`                | `HF_MODEL_VAE_SAFETENSORS`                |
| Upscalers         | `HF_MODEL_UPSCALER[1-2]`      | `HF_MODEL_UPSCALER_PTH[1-2]`              |
| Loras huggingface | `HF_MODEL_LORA[1-10]`          | `HF_MODEL_LORA_SAFETENSORS[1-10]`          |

### **Diffusion Lora Setup CivitAI**  

| Model Type        | URL (download link)            |
|-------------------|--------------------------------|
| Loras civitai     | `CIVITAI_MODEL_LORA_URL[1-10]` |

## Connection options 

### Services

| Service         | Port          |
|-----------------|---------------| 
| **ComfyUI**     | `8188` (HTTP) |
| **Code Server** | `9000` (HTTP) |
| **SSH/SCP**     | `22`   (TCP)  |
 