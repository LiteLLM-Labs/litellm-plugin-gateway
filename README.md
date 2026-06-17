# litellm-plugin-gateway

Experimental: LiteLLM with plugin architecture. Toggle between AI Gateway and any registered plugin from the sidebar dropdown.

## Files changed vs upstream litellm

- `litellm/proxy/plugin_routes.py` - Plugin registry, `/api/plugins` endpoint, reverse proxy `/plugin-proxy/{name}/*`
- `ui/.../PluginModeContext.tsx` - Mode switcher state + fetches plugin key
- `ui/.../leftnav.tsx` - Mode switcher dropdown at top of sidebar
- `ui/.../layout.tsx` - Renders iframe when mode = plugin
- `lap/` - Agent platform: plugin manifest endpoint + token auto-auth

## Config

```yaml
general_settings:
  plugins:
    - name: litellm-platform-plugin
      display_name: Agent Control Plane
      url: "http://localhost:3210"
      plugin_key: "sk-local"
```

Full fork: https://github.com/krrish-berri-2/litellm
