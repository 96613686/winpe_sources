# CreateComObject(ushort const *,_GUID const &,void * *)

- ea: `0x180029420`
- end: `0x1800294ed`
- name: `?CreateComObject@@YAKPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `205`
- prototype: `unsigned int(const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180029420`
- `0x18002f3e0`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x180029471`
- `OLE32!CoCreateInstance` at `0x1800294af`
- `OLE32!CoCreateInstance` at `0x180029471`
- `OLE32!CoCreateInstance` at `0x1800294af`
- `OLE32!CoInitializeEx` at `0x18002948a`
- `OLE32!CoInitializeEx` at `0x18002948a`
- `OLE32!CLSIDFromProgID` at `0x18002944c`
- `OLE32!CLSIDFromProgID` at `0x18002944c`

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
0x180029420  mov     [rsp+arg_18], rbx
0x180029425  push    rdi
0x180029426  sub     rsp, 50h
0x18002942a  mov     rax, cs:__security_cookie
0x180029431  xor     rax, rsp
0x180029434  mov     [rsp+58h+var_18], rax
0x180029439  mov     rbx, rdx
0x18002943c  xorps   xmm0, xmm0
0x18002943f  lea     rdx, [rsp+58h+clsid]; lpclsid
0x180029444  mov     rdi, r8
0x180029447  movups  xmmword ptr [rsp+58h+clsid.Data1], xmm0
0x18002944c  call    cs:__imp_CLSIDFromProgID
0x180029453  nop     dword ptr [rax+rax+00h]
0x180029458  mov     ecx, eax
0x18002945a  test    eax, eax
0x18002945c  js      short loc_1800294C1
0x18002945e  xor     edx, edx; pUnkOuter
0x180029460  mov     [rsp+58h+ppv], rdi; ppv
0x180029465  mov     r9, rbx; riid
0x180029468  lea     rcx, [rsp+58h+clsid]; rclsid
0x18002946d  lea     r8d, [rdx+1]; dwClsContext
0x180029471  call    cs:__imp_CoCreateInstance
0x180029478  nop     dword ptr [rax+rax+00h]
0x18002947d  mov     ecx, eax
0x18002947f  cmp     eax, 800401F0h
0x180029484  jnz     short loc_1800294BD
0x180029486  xor     edx, edx; dwCoInit
0x180029488  xor     ecx, ecx; pvReserved
0x18002948a  call    cs:__imp_CoInitializeEx
0x180029491  nop     dword ptr [rax+rax+00h]
0x180029496  mov     ecx, eax
0x180029498  test    eax, eax
0x18002949a  js      short loc_1800294C1
0x18002949c  xor     edx, edx; pUnkOuter
0x18002949e  mov     [rsp+58h+ppv], rdi; ppv
0x1800294a3  mov     r9, rbx; riid
0x1800294a6  lea     rcx, [rsp+58h+clsid]; rclsid
0x1800294ab  lea     r8d, [rdx+1]; dwClsContext
0x1800294af  call    cs:__imp_CoCreateInstance
0x1800294b6  nop     dword ptr [rax+rax+00h]
0x1800294bb  mov     ecx, eax
0x1800294bd  test    ecx, ecx
0x1800294bf  jns     short loc_1800294D2
0x1800294c1  mov     eax, ecx
0x1800294c3  and     eax, 1FFF0000h
0x1800294c8  cmp     eax, 70000h
0x1800294cd  jnz     short loc_1800294D2
0x1800294cf  movzx   ecx, cx
0x1800294d2  mov     eax, ecx
0x1800294d4  mov     rcx, [rsp+58h+var_18]
0x1800294d9  xor     rcx, rsp; StackCookie
0x1800294dc  call    __security_check_cookie
0x1800294e1  mov     rbx, [rsp+58h+arg_18]
0x1800294e6  add     rsp, 50h
0x1800294ea  pop     rdi
0x1800294eb  retn
```
