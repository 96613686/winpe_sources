# SDiagPrviCreateXmlDocument(IXMLDOMDocument * *)

- ea: `0x180002bf0`
- end: `0x180002cd9`
- name: `?SDiagPrviCreateXmlDocument@@YAJPEAPEAUIXMLDOMDocument@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002f24`
- `0x180008f00`
- `0x18000d748`

## callees

- `0x180002bf0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002c3a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002c3a`

## pseudocode

```c
__int64 __fastcall SDiagPrviCreateXmlDocument(struct IXMLDOMDocument **a1)
{
  HRESULT v2; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = 0;
  if ( a1 )
  {
    *a1 = 0;
    v2 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, &ppv);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
      if ( v2 >= 0 )
      {
        v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 560LL))(ppv, 0);
        if ( v2 >= 0 )
        {
          v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0);
          if ( v2 >= 0 )
            v2 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IXMLDOMDocument **))ppv)(
                   ppv,
                   &IID_IXMLDOMDocument,
                   a1);
        }
      }
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180002bf0  mov     [rsp+arg_8], rbx
0x180002bf5  push    rdi
0x180002bf6  sub     rsp, 30h
0x180002bfa  mov     [rsp+38h+arg_0], 0
0x180002c03  mov     rdi, rcx
0x180002c06  test    rcx, rcx
0x180002c09  jnz     short loc_180002C15
0x180002c0b  mov     ebx, 80070057h
0x180002c10  jmp     loc_180002CCC
0x180002c15  xor     edx, edx; pUnkOuter
0x180002c17  mov     qword ptr [rcx], 0
0x180002c1e  lea     rax, [rsp+38h+arg_0]
0x180002c23  lea     r9, IID_IXMLDOMDocument2; riid
0x180002c2a  mov     [rsp+38h+ppv], rax; ppv
0x180002c2f  lea     rcx, CLSID_DOMDocument60; rclsid
0x180002c36  lea     r8d, [rdx+1]; dwClsContext
0x180002c3a  call    cs:__imp_CoCreateInstance
0x180002c40  mov     ebx, eax
0x180002c42  test    eax, eax
0x180002c44  js      short loc_180002CB6
0x180002c46  mov     rcx, [rsp+38h+arg_0]
0x180002c4b  xor     edx, edx
0x180002c4d  mov     rax, [rcx]
0x180002c50  mov     rax, [rax+1F8h]
0x180002c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c5c  mov     ebx, eax
0x180002c5e  test    eax, eax
0x180002c60  js      short loc_180002CB6
0x180002c62  mov     rcx, [rsp+38h+arg_0]
0x180002c67  xor     edx, edx
0x180002c69  mov     rax, [rcx]
0x180002c6c  mov     rax, [rax+230h]
0x180002c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c78  mov     ebx, eax
0x180002c7a  test    eax, eax
0x180002c7c  js      short loc_180002CB6
0x180002c7e  mov     rcx, [rsp+38h+arg_0]
0x180002c83  xor     edx, edx
0x180002c85  mov     rax, [rcx]
0x180002c88  mov     rax, [rax+220h]
0x180002c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c94  mov     ebx, eax
0x180002c96  test    eax, eax
0x180002c98  js      short loc_180002CB6
0x180002c9a  mov     rcx, [rsp+38h+arg_0]
0x180002c9f  lea     rdx, IID_IXMLDOMDocument
0x180002ca6  mov     r8, rdi
0x180002ca9  mov     rax, [rcx]
0x180002cac  mov     rax, [rax]
0x180002caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cb4  mov     ebx, eax
0x180002cb6  mov     rcx, [rsp+38h+arg_0]
0x180002cbb  test    rcx, rcx
0x180002cbe  jz      short loc_180002CCC
0x180002cc0  mov     rax, [rcx]
0x180002cc3  mov     rax, [rax+10h]
0x180002cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ccc  mov     eax, ebx
0x180002cce  mov     rbx, [rsp+38h+arg_8]
0x180002cd3  add     rsp, 30h
0x180002cd7  pop     rdi
0x180002cd8  retn
```
