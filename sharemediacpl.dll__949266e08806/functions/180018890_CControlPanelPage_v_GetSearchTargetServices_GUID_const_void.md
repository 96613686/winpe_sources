# CControlPanelPage::v_GetSearchTargetServices(_GUID const &,void * *)

- ea: `0x180018890`
- end: `0x1800188b4`
- name: `?v_GetSearchTargetServices@CControlPanelPage@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `36`
- prototype: `int(CControlPanelPage *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800188a9`
- `ole32!CoCreateInstance` at `0x1800188a9`

## pseudocode

```c
HRESULT __fastcall CControlPanelPage::v_GetSearchTargetServices(
        CControlPanelPage *this,
        const struct _GUID *a2,
        void **ppv)
{
  return CoCreateInstance(&CLSID_CPLSearchTargetServices, 0, 3u, a2, ppv);
}

```

## disassembly

```asm
0x180018890  sub     rsp, 38h
0x180018894  mov     r9, rdx; riid
0x180018897  mov     [rsp+38h+ppv], r8; ppv
0x18001889c  xor     edx, edx; pUnkOuter
0x18001889e  lea     rcx, CLSID_CPLSearchTargetServices; rclsid
0x1800188a5  lea     r8d, [rdx+3]; dwClsContext
0x1800188a9  call    cs:__imp_CoCreateInstance
0x1800188af  add     rsp, 38h
0x1800188b3  retn
```
