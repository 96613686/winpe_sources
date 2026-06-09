# AssocCreate

- ea: `0x180008150`
- end: `0x1800081cd`
- name: `AssocCreate`
- size: `125`
- prototype: `HRESULT __stdcall(CLSID *__struct_ptr clsid, const IID *const riid, void **ppv)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001fa90`

## callees

- `0x180008150`
- `0x1800369c5`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x1800081b7`
- `SHELL32!__imp_SHCoCreateInstance` at `0x1800081b7`

## pseudocode

```c
HRESULT __stdcall AssocCreate(CLSID *clsid, const IID *const riid, void **ppv)
{
  if ( ppv && (!memcmp_0(clsid, &CLSID_QueryAssociations, 0x10u) || !memcmp_0(clsid, &IID_IQueryAssociations, 0x10u)) )
    return SHCoCreateInstance(0, &CLSID_QueryAssociations, 0, riid, ppv);
  else
    return -2147024809;
}

```

## disassembly

```asm
0x180008150  mov     [rsp+arg_0], rbx
0x180008155  mov     [rsp+arg_8], rsi
0x18000815a  push    rdi
0x18000815b  sub     rsp, 30h
0x18000815f  mov     rbx, r8
0x180008162  mov     rdi, rdx
0x180008165  mov     rsi, rcx
0x180008168  test    r8, r8
0x18000816b  jz      short loc_18000819C
0x18000816d  mov     r8d, 10h; Size
0x180008173  lea     rdx, CLSID_QueryAssociations; Buf2
0x18000817a  call    memcmp_0
0x18000817f  test    eax, eax
0x180008181  jz      short loc_1800081A3
0x180008183  mov     r8d, 10h; Size
0x180008189  lea     rdx, IID_IQueryAssociations; Buf2
0x180008190  mov     rcx, rsi; Buf1
0x180008193  call    memcmp_0
0x180008198  test    eax, eax
0x18000819a  jz      short loc_1800081A3
0x18000819c  mov     eax, 80070057h
0x1800081a1  jmp     short loc_1800081BD
0x1800081a3  mov     r9, rdi; riid
0x1800081a6  mov     [rsp+38h+ppv], rbx; ppv
0x1800081ab  xor     r8d, r8d; pUnkOuter
0x1800081ae  lea     rdx, CLSID_QueryAssociations; pclsid
0x1800081b5  xor     ecx, ecx; pszCLSID
0x1800081b7  call    cs:__imp_SHCoCreateInstance
0x1800081bd  mov     rbx, [rsp+38h+arg_0]
0x1800081c2  mov     rsi, [rsp+38h+arg_8]
0x1800081c7  add     rsp, 30h
0x1800081cb  pop     rdi
0x1800081cc  retn
```
