# DllGetClassObject

- ea: `0x180006da0`
- end: `0x180006de2`
- name: `DllGetClassObject`
- size: `66`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002f90`
- `0x180006da0`
- `0x18000a490`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax

  result = GetSignControl(rclsid, riid, ppv);
  if ( result == -2147221231 )
    return TaDllGetClassObject(rclsid, riid, ppv);
  return result;
}

```

## disassembly

```asm
0x180006da0  mov     [rsp+arg_0], rbx
0x180006da5  mov     [rsp+arg_8], rsi
0x180006daa  push    rdi
0x180006dab  sub     rsp, 20h
0x180006daf  mov     rbx, r8
0x180006db2  mov     rdi, rdx
0x180006db5  mov     rsi, rcx
0x180006db8  call    ?GetSignControl@@YAJAEBU_GUID@@0PEAPEAX@Z; GetSignControl(_GUID const &,_GUID const &,void * *)
0x180006dbd  cmp     eax, 80040111h
0x180006dc2  jnz     short loc_180006DD2
0x180006dc4  mov     r8, rbx; void **
0x180006dc7  mov     rdx, rdi; struct _GUID *
0x180006dca  mov     rcx, rsi; struct _GUID *
0x180006dcd  call    ?TaDllGetClassObject@@YAJAEBU_GUID@@0PEAPEAX@Z; TaDllGetClassObject(_GUID const &,_GUID const &,void * *)
0x180006dd2  mov     rbx, [rsp+28h+arg_0]
0x180006dd7  mov     rsi, [rsp+28h+arg_8]
0x180006ddc  add     rsp, 20h
0x180006de0  pop     rdi
0x180006de1  retn
```
