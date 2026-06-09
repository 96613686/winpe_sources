# CWebCrawler::CheckFrame(IUnknown *,ushort * *,unsigned __int64,ulong *)

- ea: `0x18001e670`
- end: `0x18001e722`
- name: `?CheckFrame@CWebCrawler@@KAJPEAUIUnknown@@PEAPEAG_KPEAK@Z`
- size: `178`
- prototype: `__int64 __fastcall(struct IUnknown *, unsigned __int16 **, unsigned __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001e670`
- `0x180029280`
- `0x180029310`

## import_xrefs

- `SHLWAPI!UrlCombineW` at `0x18001e6cf`
- `SHLWAPI!UrlCombineW` at `0x18001e6cf`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e6de`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e6de`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e6ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e6ef`

## pseudocode

```c
__int64 __fastcall CWebCrawler::CheckFrame(
        struct IUnknown *a1,
        unsigned __int16 **a2,
        const WCHAR *a3,
        unsigned int *a4)
{
  const WCHAR *v5; // rdx
  unsigned __int16 *v6; // rdi
  __int64 result; // rax
  DWORD pcchCombined[4]; // [rsp+30h] [rbp-1078h] BYREF
  WCHAR pszCombined[2088]; // [rsp+40h] [rbp-1068h] BYREF

  pcchCombined[0] = 2084;
  if ( !a2 )
    return 2147500037LL;
  v5 = *a2;
  if ( !v5 )
    return 2147500037LL;
  if ( !a1 )
    return 2147500037LL;
  if ( !a3 )
    return 2147500037LL;
  if ( UrlCombineW(a3, v5, pszCombined, pcchCombined, 0) < 0 )
    return 2147500037LL;
  v6 = SysAllocString(pszCombined);
  if ( !v6 )
    return 2147500037LL;
  SysFreeString(*a2);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x18001e670  mov     [rsp+arg_0], rbx
0x18001e675  push    rdi
0x18001e676  mov     eax, 10A0h
0x18001e67b  call    _alloca_probe
0x18001e680  sub     rsp, rax
0x18001e683  mov     rax, cs:__security_cookie
0x18001e68a  xor     rax, rsp
0x18001e68d  mov     [rsp+10A8h+var_18], rax
0x18001e695  mov     [rsp+10A8h+pcchCombined], 824h
0x18001e69d  mov     rax, r8
0x18001e6a0  mov     rbx, rdx
0x18001e6a3  test    rdx, rdx
0x18001e6a6  jz      short loc_18001E6FC
0x18001e6a8  mov     rdx, [rdx]; pszRelative
0x18001e6ab  test    rdx, rdx
0x18001e6ae  jz      short loc_18001E6FC
0x18001e6b0  test    rcx, rcx
0x18001e6b3  jz      short loc_18001E6FC
0x18001e6b5  test    rax, rax
0x18001e6b8  jz      short loc_18001E6FC
0x18001e6ba  lea     r9, [rsp+10A8h+pcchCombined]; pcchCombined
0x18001e6bf  mov     [rsp+10A8h+dwFlags], 0; dwFlags
0x18001e6c7  lea     r8, [rsp+10A8h+pszCombined]; pszCombined
0x18001e6cc  mov     rcx, rax; pszBase
0x18001e6cf  call    cs:__imp_UrlCombineW
0x18001e6d5  test    eax, eax
0x18001e6d7  js      short loc_18001E6FC
0x18001e6d9  lea     rcx, [rsp+10A8h+pszCombined]; psz
0x18001e6de  call    cs:__imp_SysAllocString
0x18001e6e4  mov     rdi, rax
0x18001e6e7  test    rax, rax
0x18001e6ea  jz      short loc_18001E6FC
0x18001e6ec  mov     rcx, [rbx]; bstrString
0x18001e6ef  call    cs:__imp_SysFreeString
0x18001e6f5  xor     eax, eax
0x18001e6f7  mov     [rbx], rdi
0x18001e6fa  jmp     short loc_18001E701
0x18001e6fc  mov     eax, 80004005h
0x18001e701  mov     rcx, [rsp+10A8h+var_18]
0x18001e709  xor     rcx, rsp; StackCookie
0x18001e70c  call    __security_check_cookie
0x18001e711  mov     rbx, [rsp+10A8h+arg_0]
0x18001e719  add     rsp, 10A0h
0x18001e720  pop     rdi
0x18001e721  retn
```
