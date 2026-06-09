# DllGetClassObject

- ea: `0x180001a80`
- end: `0x180001ab8`
- name: `DllGetClassObject`
- size: `56`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001a80`
- `0x180007010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  *ppv = 0;
  if ( *(_OWORD *)rclsid == *(_OWORD *)&CLSID_WmRgSrv )
    return (**(__int64 (__fastcall ***)(CWmRgSrvFactory *, const IID *const))g_pWmRgSrvFactory)(g_pWmRgSrvFactory, riid);
  else
    return -2147221231;
}

```

## disassembly

```asm
0x180001a80  mov     qword ptr [r8], 0
0x180001a87  mov     rax, [rcx]
0x180001a8a  cmp     rax, qword ptr cs:CLSID_WmRgSrv.Data1
0x180001a91  jnz     short loc_180001AB2
0x180001a93  mov     rax, [rcx+8]
0x180001a97  cmp     rax, qword ptr cs:CLSID_WmRgSrv.Data4
0x180001a9e  jnz     short loc_180001AB2
0x180001aa0  mov     rcx, cs:?g_pWmRgSrvFactory@@3PEAVCWmRgSrvFactory@@EA; CWmRgSrvFactory * g_pWmRgSrvFactory
0x180001aa7  mov     rax, [rcx]
0x180001aaa  mov     rax, [rax]
0x180001aad  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001ab2  mov     eax, 80040111h
0x180001ab7  retn
```
