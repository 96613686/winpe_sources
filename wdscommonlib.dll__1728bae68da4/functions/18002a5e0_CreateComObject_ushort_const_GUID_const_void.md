# CreateComObject(ushort const *,_GUID const &,void * *)

- ea: `0x18002a5e0`
- end: `0x18002a6ad`
- name: `?CreateComObject@@YAKPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `205`
- prototype: `unsigned int(const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002a5e0`
- `0x180030390`

## import_xrefs

- `OLE32!CLSIDFromProgID` at `0x18002a60c`
- `OLE32!CLSIDFromProgID` at `0x18002a60c`
- `OLE32!CoInitializeEx` at `0x18002a64a`
- `OLE32!CoInitializeEx` at `0x18002a64a`
- `OLE32!CoCreateInstance` at `0x18002a631`
- `OLE32!CoCreateInstance` at `0x18002a66f`
- `OLE32!CoCreateInstance` at `0x18002a631`
- `OLE32!CoCreateInstance` at `0x18002a66f`

## pseudocode

```c
__int64 __fastcall CreateComObject(const unsigned __int16 *a1, const struct _GUID *a2, void **a3)
{
  HRESULT v5; // ecx
  GUID clsid; // [rsp+30h] [rbp-28h] BYREF

  clsid = 0;
  v5 = CLSIDFromProgID(a1, &clsid);
  if ( v5 >= 0 )
  {
    v5 = CoCreateInstance(&clsid, 0, 1u, a2, a3);
    if ( v5 != -2147221008 )
      goto LABEL_5;
    v5 = CoInitializeEx(0, 0);
    if ( v5 >= 0 )
    {
      v5 = CoCreateInstance(&clsid, 0, 1u, a2, a3);
LABEL_5:
      if ( v5 >= 0 )
        return (unsigned int)v5;
    }
  }
  if ( (v5 & 0x1FFF0000) == 0x70000 )
    return (unsigned __int16)v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002a5e0  mov     [rsp+arg_18], rbx
0x18002a5e5  push    rdi
0x18002a5e6  sub     rsp, 50h
0x18002a5ea  mov     rax, cs:__security_cookie
0x18002a5f1  xor     rax, rsp
0x18002a5f4  mov     [rsp+58h+var_18], rax
0x18002a5f9  mov     rbx, rdx
0x18002a5fc  xorps   xmm0, xmm0
0x18002a5ff  lea     rdx, [rsp+58h+clsid]; lpclsid
0x18002a604  mov     rdi, r8
0x18002a607  movups  xmmword ptr [rsp+58h+clsid.Data1], xmm0
0x18002a60c  call    cs:__imp_CLSIDFromProgID
0x18002a613  nop     dword ptr [rax+rax+00h]
0x18002a618  mov     ecx, eax
0x18002a61a  test    eax, eax
0x18002a61c  js      short loc_18002A681
0x18002a61e  xor     edx, edx; pUnkOuter
0x18002a620  mov     [rsp+58h+ppv], rdi; ppv
0x18002a625  mov     r9, rbx; riid
0x18002a628  lea     rcx, [rsp+58h+clsid]; rclsid
0x18002a62d  lea     r8d, [rdx+1]; dwClsContext
0x18002a631  call    cs:__imp_CoCreateInstance
0x18002a638  nop     dword ptr [rax+rax+00h]
0x18002a63d  mov     ecx, eax
0x18002a63f  cmp     eax, 800401F0h
0x18002a644  jnz     short loc_18002A67D
0x18002a646  xor     edx, edx; dwCoInit
0x18002a648  xor     ecx, ecx; pvReserved
0x18002a64a  call    cs:__imp_CoInitializeEx
0x18002a651  nop     dword ptr [rax+rax+00h]
0x18002a656  mov     ecx, eax
0x18002a658  test    eax, eax
0x18002a65a  js      short loc_18002A681
0x18002a65c  xor     edx, edx; pUnkOuter
0x18002a65e  mov     [rsp+58h+ppv], rdi; ppv
0x18002a663  mov     r9, rbx; riid
0x18002a666  lea     rcx, [rsp+58h+clsid]; rclsid
0x18002a66b  lea     r8d, [rdx+1]; dwClsContext
0x18002a66f  call    cs:__imp_CoCreateInstance
0x18002a676  nop     dword ptr [rax+rax+00h]
0x18002a67b  mov     ecx, eax
0x18002a67d  test    ecx, ecx
0x18002a67f  jns     short loc_18002A692
0x18002a681  mov     eax, ecx
0x18002a683  and     eax, 1FFF0000h
0x18002a688  cmp     eax, 70000h
0x18002a68d  jnz     short loc_18002A692
0x18002a68f  movzx   ecx, cx
0x18002a692  mov     eax, ecx
0x18002a694  mov     rcx, [rsp+58h+var_18]
0x18002a699  xor     rcx, rsp; StackCookie
0x18002a69c  call    __security_check_cookie
0x18002a6a1  mov     rbx, [rsp+58h+arg_18]
0x18002a6a6  add     rsp, 50h
0x18002a6aa  pop     rdi
0x18002a6ab  retn
```
