# ApplicationIdentityInfo::GetProcessPath(ushort const *)

- ea: `0x180007ce0`
- end: `0x180007f38`
- name: `?GetProcessPath@ApplicationIdentityInfo@@QEBA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z`
- size: `600`
- prototype: `Microsoft::WRL::Wrappers::HString *__fastcall(__int64, Microsoft::WRL::Wrappers::HString *, const WCHAR *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180006f30`

## callees

- `0x1800060a8`
- `0x180007ce0`
- `0x180016c98`
- `0x18001d578`
- `0x180024014`
- `0x180024c0c`
- `0x180033d5c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007d62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007dc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007ddf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007ec0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007f13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007f1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007d62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007dc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007ddf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007ec0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007f13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007f1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007dea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007e08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007dea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007e08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180007d77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180007ed5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180007d77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180007ed5`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180007e61`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180007e61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f09`

## pseudocode

```c
Microsoft::WRL::Wrappers::HString *__fastcall ApplicationIdentityInfo::GetProcessPath(
        __int64 a1,
        Microsoft::WRL::Wrappers::HString *a2,
        const WCHAR *a3)
{
  const WCHAR *StringRawBuffer; // rdi
  unsigned __int64 v6; // rbp
  HRESULT v7; // eax
  HSTRING v8; // rbx
  HSTRING *ManifestedExecutable; // rdi
  const WCHAR *v10; // r15
  unsigned __int64 v11; // rbp
  __int64 v12; // rcx
  __int64 v13; // rsi
  HRESULT v14; // eax
  PWSTR v15; // rcx
  HRESULT v16; // eax
  HSTRING v18; // [rsp+28h] [rbp-50h] BYREF
  HSTRING v19; // [rsp+30h] [rbp-48h]
  HSTRING string[8]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  UINT32 length; // [rsp+80h] [rbp+8h] BYREF
  Microsoft::WRL::Wrappers::HString *v23; // [rsp+88h] [rbp+10h]
  PWSTR pszPathOut; // [rsp+98h] [rbp+20h] BYREF

  v23 = a2;
  StringRawBuffer = a3;
  *(_QWORD *)a2 = 0;
  if ( (*(_BYTE *)(a1 + 136) & 6) == 0 )
  {
    ApplicationIdentityInfo::GetPackagePath(a1, &v18);
    v8 = 0;
    v19 = 0;
    if ( !StringRawBuffer )
    {
      ManifestedExecutable = (HSTRING *)ApplicationIdentityInfo::GetManifestedExecutable(a1, string);
      WindowsDeleteString(0);
      v19 = *ManifestedExecutable;
      v8 = v19;
      *ManifestedExecutable = 0;
      WindowsDeleteString(string[0]);
      StringRawBuffer = WindowsGetStringRawBuffer(v8, 0);
    }
    length = 0;
    v10 = WindowsGetStringRawBuffer(v18, &length);
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( StringRawBuffer[v12] );
    v13 = v12 + length;
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pszPathOut,
      0,
      v13 + 2);
    v14 = PathCchCombine(pszPathOut, v13 + 2, v10, StringRawBuffer);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
        (const char *)(unsigned int)v14,
        3);
    v15 = pszPathOut;
    if ( pszPathOut )
    {
      do
        ++v11;
      while ( pszPathOut[v11] );
      if ( v11 > 0xFFFFFFFF )
      {
        v16 = -2147024362;
LABEL_23:
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x94,
            (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
            (const char *)(unsigned int)v16,
            3);
        if ( v15 )
          CoTaskMemFree(v15);
        WindowsDeleteString(v8);
        WindowsDeleteString(v18);
        return a2;
      }
      v16 = Microsoft::WRL::Wrappers::HString::Set(a2, pszPathOut, v11);
    }
    else
    {
      WindowsDeleteString(*(HSTRING *)a2);
      *(_QWORD *)a2 = 0;
      v16 = WindowsCreateString(&pszDefault, 0, (HSTRING *)a2);
    }
    v15 = pszPathOut;
    goto LABEL_23;
  }
  if ( a3 )
  {
    length = 0;
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = ULongLongToUInt(v6, &length);
    if ( v7 < 0 )
LABEL_9:
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
        (const char *)(unsigned int)v7,
        1);
    v7 = Microsoft::WRL::Wrappers::HString::Set(a2, StringRawBuffer, length);
  }
  else
  {
    WindowsDeleteString(0);
    *(_QWORD *)a2 = 0;
    v7 = WindowsCreateString(&pszDefault, 0, (HSTRING *)a2);
  }
  if ( v7 < 0 )
    goto LABEL_9;
  return a2;
}

```

## disassembly

```asm
0x180007ce0  mov     rax, rsp
0x180007ce3  mov     [rax+10h], rdx
0x180007ce7  push    rbx
0x180007ce8  push    rbp
0x180007ce9  push    rsi
0x180007cea  push    rdi
0x180007ceb  push    r12
0x180007ced  push    r14
0x180007cef  push    r15
0x180007cf1  sub     rsp, 40h
0x180007cf5  mov     rdi, r8
0x180007cf8  mov     r14, rdx
0x180007cfb  mov     rsi, rcx
0x180007cfe  xor     r12d, r12d
0x180007d01  mov     [rax-58h], r12d
0x180007d05  mov     [rdx], r12
0x180007d08  mov     dword ptr [rax-58h], 1
0x180007d0f  test    byte ptr [rcx+88h], 6
0x180007d16  jz      loc_180007D9F
0x180007d1c  test    r8, r8
0x180007d1f  jz      short loc_180007D60
0x180007d21  mov     [rax+8], r12d
0x180007d25  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180007d2c  inc     rbp
0x180007d2f  cmp     word ptr [r8+rbp*2], 0
0x180007d35  jnz     short loc_180007D2C
0x180007d37  lea     rdx, [rsp+78h+length]; unsigned int *
0x180007d3f  mov     rcx, rbp; unsigned __int64
0x180007d42  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180007d47  test    eax, eax
0x180007d49  js      short loc_180007D85
0x180007d4b  mov     r8d, [rsp+78h+length]; unsigned int
0x180007d53  mov     rdx, rdi; unsigned __int16 *
0x180007d56  mov     rcx, r14; this
0x180007d59  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180007d5e  jmp     short loc_180007D7D
0x180007d60  xor     ecx, ecx; string
0x180007d62  call    cs:__imp_WindowsDeleteString
0x180007d68  mov     [r14], r12
0x180007d6b  mov     r8, r14; string
0x180007d6e  xor     edx, edx; length
0x180007d70  lea     rcx, pszDefault; sourceString
0x180007d77  call    cs:__imp_WindowsCreateString
0x180007d7d  test    eax, eax
0x180007d7f  jns     loc_180007F25
0x180007d85  mov     rcx, [rsp+78h]; this
0x180007d8a  mov     r9d, eax; char *
0x180007d8d  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180007d94  mov     edx, 7Eh ; '~'; void *
0x180007d99  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007d9f  lea     rdx, [rsp+78h+var_50]
0x180007da4  call    ?GetPackagePath@ApplicationIdentityInfo@@QEBA?AVHString@Wrappers@WRL@Microsoft@@XZ; ApplicationIdentityInfo::GetPackagePath(void)
0x180007da9  nop
0x180007daa  mov     rbx, r12
0x180007dad  mov     [rsp+78h+var_48], rbx
0x180007db2  test    rdi, rdi
0x180007db5  jnz     short loc_180007DF3
0x180007db7  lea     rdx, [rsp+78h+string]
0x180007dbc  mov     rcx, rsi
0x180007dbf  call    ?GetManifestedExecutable@ApplicationIdentityInfo@@QEBA?AVHString@Wrappers@WRL@Microsoft@@XZ; ApplicationIdentityInfo::GetManifestedExecutable(void)
0x180007dc4  mov     rdi, rax
0x180007dc7  xor     ecx, ecx; string
0x180007dc9  call    cs:__imp_WindowsDeleteString
0x180007dcf  mov     rbx, [rdi]
0x180007dd2  mov     [rsp+78h+var_48], rbx
0x180007dd7  mov     [rdi], r12
0x180007dda  mov     rcx, [rsp+78h+string]; string
0x180007ddf  call    cs:__imp_WindowsDeleteString
0x180007de5  xor     edx, edx; length
0x180007de7  mov     rcx, rbx; string
0x180007dea  call    cs:__imp_WindowsGetStringRawBuffer
0x180007df0  mov     rdi, rax
0x180007df3  mov     [rsp+78h+length], r12d
0x180007dfb  lea     rdx, [rsp+78h+length]; length
0x180007e03  mov     rcx, [rsp+78h+var_50]; string
0x180007e08  call    cs:__imp_WindowsGetStringRawBuffer
0x180007e0e  mov     r15, rax
0x180007e11  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180007e18  mov     rcx, rbp
0x180007e1b  nop     dword ptr [rax+rax+00h]
0x180007e20  inc     rcx
0x180007e23  cmp     word ptr [rdi+rcx*2], 0
0x180007e28  jnz     short loc_180007E20
0x180007e2a  mov     esi, [rsp+78h+length]
0x180007e31  add     rsi, rcx
0x180007e34  lea     r8, [rsi+2]
0x180007e38  xor     edx, edx
0x180007e3a  lea     rcx, [rsp+78h+pszPathOut]
0x180007e42  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180007e47  mov     [rsp+78h+var_58], 3; int
0x180007e4f  mov     r9, rdi; pszMore
0x180007e52  mov     r8, r15; pszPathIn
0x180007e55  lea     rdx, [rsi+2]; cchPathOut
0x180007e59  mov     rcx, [rsp+78h+pszPathOut]; pszPathOut
0x180007e61  call    cs:__imp_PathCchCombine
0x180007e67  test    eax, eax
0x180007e69  jns     short loc_180007E85
0x180007e6b  mov     rcx, [rsp+78h]; this
0x180007e70  mov     r9d, eax; char *
0x180007e73  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180007e7a  mov     edx, 93h; void *
0x180007e7f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007e85  mov     rcx, [rsp+78h+pszPathOut]
0x180007e8d  test    rcx, rcx
0x180007e90  jz      short loc_180007EBD
0x180007e92  inc     rbp
0x180007e95  cmp     word ptr [rcx+rbp*2], 0
0x180007e9a  jnz     short loc_180007E92
0x180007e9c  mov     eax, 0FFFFFFFFh
0x180007ea1  cmp     rbp, rax
0x180007ea4  ja      short loc_180007EB6
0x180007ea6  mov     r8d, ebp; unsigned int
0x180007ea9  mov     rdx, rcx; unsigned __int16 *
0x180007eac  mov     rcx, r14; this
0x180007eaf  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180007eb4  jmp     short loc_180007EDB
0x180007eb6  mov     eax, 80070216h
0x180007ebb  jmp     short loc_180007EE3
0x180007ebd  mov     rcx, [r14]; string
0x180007ec0  call    cs:__imp_WindowsDeleteString
0x180007ec6  mov     [r14], r12
0x180007ec9  mov     r8, r14; string
0x180007ecc  xor     edx, edx; length
0x180007ece  lea     rcx, pszDefault; sourceString
0x180007ed5  call    cs:__imp_WindowsCreateString
0x180007edb  mov     rcx, [rsp+78h+pszPathOut]; pv
0x180007ee3  mov     r10, [rsp+78h]
0x180007ee8  test    eax, eax
0x180007eea  jns     short loc_180007F04
0x180007eec  mov     r9d, eax; char *
0x180007eef  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180007ef6  mov     edx, 94h; void *
0x180007efb  mov     rcx, r10; this
0x180007efe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007f04  test    rcx, rcx
0x180007f07  jz      short loc_180007F10
0x180007f09  call    cs:__imp_CoTaskMemFree
0x180007f0f  nop
0x180007f10  mov     rcx, rbx; string
0x180007f13  call    cs:__imp_WindowsDeleteString
0x180007f19  nop
0x180007f1a  mov     rcx, [rsp+78h+var_50]; string
0x180007f1f  call    cs:__imp_WindowsDeleteString
0x180007f25  mov     rax, r14
0x180007f28  add     rsp, 40h
0x180007f2c  pop     r15
0x180007f2e  pop     r14
0x180007f30  pop     r12
0x180007f32  pop     rdi
0x180007f33  pop     rsi
0x180007f34  pop     rbp
0x180007f35  pop     rbx
0x180007f36  retn
```
