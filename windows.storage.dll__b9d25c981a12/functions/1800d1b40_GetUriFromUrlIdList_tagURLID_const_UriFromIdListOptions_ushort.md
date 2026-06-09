# GetUriFromUrlIdList(tagURLID const *,UriFromIdListOptions,ushort * *)

- ea: `0x1800d1b40`
- end: `0x1800d1d75`
- name: `?GetUriFromUrlIdList@@YAJPEFBUtagURLID@@W4UriFromIdListOptions@@PEAPEAG@Z`
- size: `565`
- prototype: ``
- caller_count: `9`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d16c0`
- `0x1800d2108`
- `0x1801aa710`
- `0x1802a4c24`
- `0x1802ec1d4`
- `0x1802f5120`
- `0x1802ff118`
- `0x18033fee0`
- `0x180616db8`

## callees

- `0x180038f50`
- `0x180044320`
- `0x1800d1b40`
- `0x1800d1d80`
- `0x180264f64`
- `0x1802e9534`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!UrlCombineW` at `0x180664e83`
- `api-ms-win-core-url-l1-1-0!UrlCombineW` at `0x180664ef6`
- `api-ms-win-core-url-l1-1-0!UrlCombineW` at `0x180664e83`
- `api-ms-win-core-url-l1-1-0!UrlCombineW` at `0x180664ef6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1b9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1c51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1c85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1cb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1d27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1d64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180664eb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180664ec6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180664f2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180664f3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1b9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1c51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1c85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1cb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1d27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1d64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180664eb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180664ec6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180664f2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180664f3c`
- `SHCORE!__imp_ualstrcpynW` at `0x1800d1bc7`
- `SHCORE!__imp_ualstrcpynW` at `0x1800d1bc7`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x1800d1d55`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x1800d1d55`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetUriFromUrlIdList(unsigned __int16 *a1, int a2, _QWORD *a3)
{
  unsigned __int64 v6; // rsi
  void **cotaskmem_string_nothrow; // rax
  void *v8; // rbx
  char v9; // al
  WCHAR **v11; // rax
  WCHAR *v12; // r15
  WCHAR *v13; // r15
  HRESULT v14; // eax
  unsigned int v15; // r12d
  HRESULT v16; // eax
  unsigned int v17; // edi
  DWORD dwFlags; // [rsp+20h] [rbp-78h]
  DWORD dwFlagsb; // [rsp+20h] [rbp-78h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-78h]
  LPVOID v21[3]; // [rsp+30h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v6 = ((unsigned __int64)*a1 - 6) >> 1;
  cotaskmem_string_nothrow = (void **)wil::make_cotaskmem_string_nothrow((wil *)&pv, 0, v6);
  v8 = *cotaskmem_string_nothrow;
  v21[1] = *cotaskmem_string_nothrow;
  *cotaskmem_string_nothrow = 0;
  if ( pv )
    CoTaskMemFree(pv);
  if ( !v8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17E,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
    return 2147942414LL;
  }
  v9 = *((_BYTE *)a1 + 3);
  if ( v9 )
  {
    if ( v9 == (char)0x80 )
      ualstrcpynW(v8, a1 + 4, (unsigned int)v6);
  }
  else
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pv,
      0,
      v6);
    v13 = (WCHAR *)pv;
    if ( !pv )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
        (const char *)0x8007000ELL,
        dwFlags);
      CoTaskMemFree(v8);
      return 2147942414LL;
    }
    StringCchCopyA((char *)pv, v6, (const char *)a1 + 8);
    SHAnsiToUnicode((PCSTR)v8, v13, v6);
    CoTaskMemFree(v13);
  }
  if ( !a2 )
  {
LABEL_8:
    *a3 = v8;
    return 0;
  }
  LODWORD(pv) = v6;
  v11 = (WCHAR **)wil::make_cotaskmem_string_nothrow((wil *)v21, 0, v6);
  v12 = *v11;
  v21[2] = *v11;
  *v11 = 0;
  if ( v21[0] )
    CoTaskMemFree(v21[0]);
  if ( !v12 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
    CoTaskMemFree(v8);
    return 2147942414LL;
  }
  if ( (unsigned int)ILGetHiddenStringW(a1, 3203334146LL, v12, (unsigned int)v6) )
  {
    v14 = UrlCombineW((PCWSTR)v8, v12, (PWSTR)v8, (DWORD *)&pv, 0);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x195,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
        (const char *)(unsigned int)v14,
        dwFlagsb);
      CoTaskMemFree(v12);
      CoTaskMemFree(v8);
      return v15;
    }
    LODWORD(pv) = v6;
  }
  if ( a2 != 1
    || !(unsigned int)ILGetHiddenStringW(a1, 3203334145LL, v12, (unsigned int)v6)
    || (v16 = UrlCombineW((PCWSTR)v8, v12, (PWSTR)v8, (DWORD *)&pv, 0), v17 = v16, v16 >= 0) )
  {
    CoTaskMemFree(v12);
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19B,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
    (const char *)(unsigned int)v16,
    dwFlagsa);
  CoTaskMemFree(v12);
  CoTaskMemFree(v8);
  return v17;
}

```

## disassembly

```asm
0x1800d1b40  mov     [rsp+arg_8], rbx
0x1800d1b45  push    rbp
0x1800d1b46  push    rsi
0x1800d1b47  push    rdi
0x1800d1b48  push    r12
0x1800d1b4a  push    r13
0x1800d1b4c  push    r14
0x1800d1b4e  push    r15
0x1800d1b50  sub     rsp, 60h
0x1800d1b54  mov     rax, cs:__security_cookie
0x1800d1b5b  xor     rax, rsp
0x1800d1b5e  mov     [rsp+98h+var_48], rax
0x1800d1b63  mov     r14, r8
0x1800d1b66  mov     ebp, edx
0x1800d1b68  mov     rdi, rcx
0x1800d1b6b  movzx   esi, word ptr [rcx]
0x1800d1b6e  sub     rsi, 6
0x1800d1b72  shr     rsi, 1
0x1800d1b75  mov     r8, rsi; unsigned __int64
0x1800d1b78  xor     edx, edx; unsigned __int16 *
0x1800d1b7a  lea     rcx, [rsp+98h+pv]; this
0x1800d1b7f  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x1800d1b84  mov     rbx, [rax]
0x1800d1b87  mov     [rsp+98h+var_60], rbx
0x1800d1b8c  xor     r13d, r13d
0x1800d1b8f  mov     [rax], r13
0x1800d1b92  mov     rcx, [rsp+98h+pv]; pv
0x1800d1b97  test    rcx, rcx
0x1800d1b9a  jz      short loc_1800D1BA8
0x1800d1b9c  call    cs:__imp_CoTaskMemFree
0x1800d1ba3  nop     dword ptr [rax+rax+00h]
0x1800d1ba8  test    rbx, rbx
0x1800d1bab  jz      short loc_1800D1C02
0x1800d1bad  movzx   eax, byte ptr [rdi+3]
0x1800d1bb1  test    al, al
0x1800d1bb3  jz      loc_1800D1CEB
0x1800d1bb9  cmp     al, 80h
0x1800d1bbb  jnz     short loc_1800D1BD3
0x1800d1bbd  mov     r8d, esi
0x1800d1bc0  lea     rdx, [rdi+8]
0x1800d1bc4  mov     rcx, rbx
0x1800d1bc7  call    cs:__imp_ualstrcpynW
0x1800d1bce  nop     dword ptr [rax+rax+00h]
0x1800d1bd3  test    ebp, ebp
0x1800d1bd5  jnz     short loc_1800D1C29
0x1800d1bd7  mov     [r14], rbx
0x1800d1bda  xor     eax, eax
0x1800d1bdc  mov     rcx, [rsp+98h+var_48]
0x1800d1be1  xor     rcx, rsp; StackCookie
0x1800d1be4  call    __security_check_cookie
0x1800d1be9  mov     rbx, [rsp+98h+arg_8]
0x1800d1bf1  add     rsp, 60h
0x1800d1bf5  pop     r15
0x1800d1bf7  pop     r14
0x1800d1bf9  pop     r13
0x1800d1bfb  pop     r12
0x1800d1bfd  pop     rdi
0x1800d1bfe  pop     rsi
0x1800d1bff  pop     rbp
0x1800d1c00  retn
0x1800d1c02  mov     rcx, [rsp+98h]; this
0x1800d1c0a  mov     r9d, 8007000Eh; char *
0x1800d1c10  lea     r8, aOnecoreuapShel_154; "onecoreuap\\shell\\windows.storage\\int"...
0x1800d1c17  mov     edx, 17Eh; void *
0x1800d1c1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1c21  nop
0x1800d1c22  mov     eax, 8007000Eh
0x1800d1c27  jmp     short loc_1800D1BDC
0x1800d1c29  mov     dword ptr [rsp+98h+pv], esi
0x1800d1c2d  mov     r8, rsi; unsigned __int64
0x1800d1c30  xor     edx, edx; unsigned __int16 *
0x1800d1c32  lea     rcx, [rsp+98h+var_68]; this
0x1800d1c37  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x1800d1c3c  mov     r15, [rax]
0x1800d1c3f  mov     [rsp+98h+var_58], r15
0x1800d1c44  mov     [rax], r13
0x1800d1c47  mov     rcx, [rsp+98h+var_68]; pv
0x1800d1c4c  test    rcx, rcx
0x1800d1c4f  jz      short loc_1800D1C5D
0x1800d1c51  call    cs:__imp_CoTaskMemFree
0x1800d1c58  nop     dword ptr [rax+rax+00h]
0x1800d1c5d  test    r15, r15
0x1800d1c60  jz      short loc_1800D1C96
0x1800d1c62  mov     r9d, esi
0x1800d1c65  mov     r8, r15
0x1800d1c68  mov     edx, 0BEEF0002h
0x1800d1c6d  mov     rcx, rdi
0x1800d1c70  call    ?ILGetHiddenStringW@@YAHPEFBU_ITEMIDLIST_RELATIVE@@W4IDLHID@@PEAGK@Z; ILGetHiddenStringW(_ITEMIDLIST_RELATIVE const *,IDLHID,ushort *,ulong)
0x1800d1c75  test    eax, eax
0x1800d1c77  jnz     loc_180664E70
0x1800d1c7d  cmp     ebp, 1
0x1800d1c80  jz      short loc_1800D1CCF
0x1800d1c82  mov     rcx, r15; pv
0x1800d1c85  call    cs:__imp_CoTaskMemFree
0x1800d1c8c  nop     dword ptr [rax+rax+00h]
0x1800d1c91  jmp     loc_1800D1BD7
0x1800d1c96  mov     rcx, [rsp+98h]; this
0x1800d1c9e  mov     r9d, 8007000Eh; char *
0x1800d1ca4  lea     r8, aOnecoreuapShel_154; "onecoreuap\\shell\\windows.storage\\int"...
0x1800d1cab  mov     edx, 191h; void *
0x1800d1cb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1cb5  nop
0x1800d1cb6  mov     rcx, rbx; pv
0x1800d1cb9  call    cs:__imp_CoTaskMemFree
0x1800d1cc0  nop     dword ptr [rax+rax+00h]
0x1800d1cc5  mov     eax, 8007000Eh
0x1800d1cca  jmp     loc_1800D1BDC
0x1800d1ccf  mov     r9d, esi
0x1800d1cd2  mov     r8, r15
0x1800d1cd5  mov     edx, 0BEEF0001h
0x1800d1cda  mov     rcx, rdi
0x1800d1cdd  call    ?ILGetHiddenStringW@@YAHPEFBU_ITEMIDLIST_RELATIVE@@W4IDLHID@@PEAGK@Z; ILGetHiddenStringW(_ITEMIDLIST_RELATIVE const *,IDLHID,ushort *,ulong)
0x1800d1ce2  test    eax, eax
0x1800d1ce4  jz      short loc_1800D1C82
0x1800d1ce6  jmp     loc_180664EE3
0x1800d1ceb  mov     r8, rsi
0x1800d1cee  xor     edx, edx
0x1800d1cf0  lea     rcx, [rsp+98h+pv]
0x1800d1cf5  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800d1cfa  mov     r15, [rsp+98h+pv]
0x1800d1cff  test    r15, r15
0x1800d1d02  jnz     short loc_1800D1D3D
0x1800d1d04  mov     rcx, [rsp+98h]; this
0x1800d1d0c  mov     r9d, 8007000Eh; char *
0x1800d1d12  lea     r8, aOnecoreuapShel_154; "onecoreuap\\shell\\windows.storage\\int"...
0x1800d1d19  mov     edx, 183h; void *
0x1800d1d1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1d23  nop
0x1800d1d24  mov     rcx, rbx; pv
0x1800d1d27  call    cs:__imp_CoTaskMemFree
0x1800d1d2e  nop     dword ptr [rax+rax+00h]
0x1800d1d33  mov     eax, 8007000Eh
0x1800d1d38  jmp     loc_1800D1BDC
0x1800d1d3d  lea     r8, [rdi+8]; char *
0x1800d1d41  mov     rdx, rsi; unsigned __int64
0x1800d1d44  mov     rcx, r15; char *
0x1800d1d47  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800d1d4c  mov     r8d, esi; cwchBuf
0x1800d1d4f  mov     rdx, r15; pwszDst
0x1800d1d52  mov     rcx, rbx; pszSrc
0x1800d1d55  call    cs:__imp_SHAnsiToUnicode
0x1800d1d5c  nop     dword ptr [rax+rax+00h]
0x1800d1d61  mov     rcx, r15; pv
0x1800d1d64  call    cs:__imp_CoTaskMemFree
0x1800d1d6b  nop     dword ptr [rax+rax+00h]
0x1800d1d70  jmp     loc_1800D1BD3
0x180664e70  mov     [rsp+98h+dwFlags], r13d; int
0x180664e75  lea     r9, [rsp+98h+pv]; pcchCombined
0x180664e7a  mov     r8, rbx; pszCombined
0x180664e7d  mov     rdx, r15; pszRelative
0x180664e80  mov     rcx, rbx; pszBase
0x180664e83  call    cs:__imp_UrlCombineW
0x180664e8a  nop     dword ptr [rax+rax+00h]
0x180664e8f  mov     r12d, eax
0x180664e92  test    eax, eax
0x180664e94  jns     short loc_180664EDA
0x180664e96  mov     rcx, [rsp+98h]; this
0x180664e9e  mov     r9d, eax; char *
0x180664ea1  lea     r8, aOnecoreuapShel_154; "onecoreuap\\shell\\windows.storage\\int"...
0x180664ea8  mov     edx, 195h; void *
0x180664ead  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180664eb2  nop
0x180664eb3  mov     rcx, r15; pv
0x180664eb6  call    cs:__imp_CoTaskMemFree
0x180664ebd  nop     dword ptr [rax+rax+00h]
0x180664ec2  nop
0x180664ec3  mov     rcx, rbx; pv
0x180664ec6  call    cs:__imp_CoTaskMemFree
0x180664ecd  nop     dword ptr [rax+rax+00h]
0x180664ed2  mov     eax, r12d
0x180664ed5  jmp     loc_1800D1BDC
0x180664eda  mov     dword ptr [rsp+98h+pv], esi
0x180664ede  jmp     loc_1800D1C7D
0x180664ee3  mov     [rsp+98h+dwFlags], r13d; int
0x180664ee8  lea     r9, [rsp+98h+pv]; pcchCombined
0x180664eed  mov     r8, rbx; pszCombined
0x180664ef0  mov     rdx, r15; pszRelative
0x180664ef3  mov     rcx, rbx; pszBase
0x180664ef6  call    cs:__imp_UrlCombineW
0x180664efd  nop     dword ptr [rax+rax+00h]
0x180664f02  mov     edi, eax
0x180664f04  test    eax, eax
0x180664f06  jns     loc_1800D1C82
0x180664f0c  mov     rcx, [rsp+98h]; this
0x180664f14  mov     r9d, eax; char *
0x180664f17  lea     r8, aOnecoreuapShel_154; "onecoreuap\\shell\\windows.storage\\int"...
0x180664f1e  mov     edx, 19Bh; void *
0x180664f23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180664f28  nop
0x180664f29  mov     rcx, r15; pv
0x180664f2c  call    cs:__imp_CoTaskMemFree
0x180664f33  nop     dword ptr [rax+rax+00h]
0x180664f38  nop
0x180664f39  mov     rcx, rbx; pv
0x180664f3c  call    cs:__imp_CoTaskMemFree
0x180664f43  nop     dword ptr [rax+rax+00h]
0x180664f48  mov     eax, edi
0x180664f4a  jmp     loc_1800D1BDC
```
