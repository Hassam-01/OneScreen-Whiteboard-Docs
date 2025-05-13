# Onescreen - Collaborative Whiteboard  

🚀 **Built on Agora Netless Flat & Fastboard**  

This documentation covers the custom implementation, configurations, and workarounds for the **Onescreen** collaborative whiteboard project. For complete documentation of the original open-source projects, refer to:  
- [Flat (Frontend)](https://github.com/netless-io/flat)  
- [Flat-Server (Backend)](https://github.com/netless-io/flat-server)  

---

## 📌 Key Components  
### 1. **Whiteboard (Fastboard by Agora)**  
- **Technology**: Built with [Svelte](https://svelte.dev/).  
- **Repository**: [netless-io/fastboard](https://github.com/netless-io/fastboard)  

### 2. **Agora Console Setup**  
- Requires configuration keys from [Agora Console](https://console.agora.io).  
- Steps:  
  1. Create a whiteboard project in Agora Console.  
  2. Configure keys in `development.lock.yaml` (backend) **only for local server setup**.  
  3. *Frontend-only usage can connect directly to Agora without backend keys.*  

### 3. **Running the Project** 
- navigate to cd web
- cd flat-web
- pnpm install
- pnpm start
---

### Documentation is done workspace and folder wise. Please refer to the relevant folder or readme for detailed documentation of required module.
