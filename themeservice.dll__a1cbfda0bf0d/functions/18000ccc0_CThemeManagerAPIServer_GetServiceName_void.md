# CThemeManagerAPIServer::GetServiceName(void)

- ea: `0x18000ccc0`
- end: `0x18000ccc8`
- name: `?GetServiceName@CThemeManagerAPIServer@@MEAAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *__fastcall(CThemeManagerAPIServer *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
const unsigned __int16 *__fastcall CThemeManagerAPIServer::GetServiceName(CThemeManagerAPIServer *this)
{
  return L"Themes";
}

```

## disassembly

```asm
0x18000ccc0  lea     rax, ?s_szName@CThemeManagerService@@0QBGB; "Themes"
0x18000ccc7  retn
```
