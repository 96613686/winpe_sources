# CZoneIdentifier::Load(ushort const *,ulong)

- ea: `0x18006cc40`
- end: `0x18006cf9e`
- name: `?Load@CZoneIdentifier@@UEAAJPEBGK@Z`
- size: `862`
- prototype: `__int64 __fastcall(CZoneIdentifier *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800308c0`

## callees

- `0x180030880`
- `0x18006cc40`
- `0x18006cfa4`
- `0x18006d2f8`
- `0x18006d3dc`
- `0x18007d690`
- `0x18008c724`
- `0x18009a6a0`
- `0x18009e728`
- `0x1800a5bc8`
- `0x18011ba3e`
- `0x18011c010`

## import_xrefs

- `msvcrt!wcstok_s` at `0x18006ce2d`
- `msvcrt!wcstok_s` at `0x18006ce2d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006cd1b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006cd2e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006cddb`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006cf63`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006cd1b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006cd2e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006cddb`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006cf63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cda3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cda3`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntW` at `0x18006cd0c`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntW` at `0x18006cd0c`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileSectionW` at `0x18006cd8f`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileSectionW` at `0x18006cec4`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileSectionW` at `0x18006cd8f`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileSectionW` at `0x18006cec4`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18006cccb`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18006cccb`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x18006cc7f`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x18006cc7f`

## pseudocode

```c
__int64 __fastcall CZoneIdentifier::Load(CZoneIdentifier *this, const unsigned __int16 *a2)
{
  int updated; // ebx
  __int64 v5; // rcx
  wchar_t *v7; // r15
  __int64 v8; // rdx
  WCHAR *v9; // rax
  WCHAR *v10; // rbx
  const WCHAR *v11; // r9
  DWORD v12; // r14d
  WCHAR *v13; // rdi
  DWORD LastError; // eax
  unsigned int v15; // r8d
  wchar_t *v16; // rax
  __int64 v17; // rcx
  wchar_t *v18; // rsi
  __int64 v19; // rcx
  int v20; // eax
  unsigned int v21; // edi
  __int64 v22; // rax
  WCHAR *v23; // rsi
  unsigned __int64 v24; // r12
  WCHAR *v25; // rax
  unsigned int v26; // [rsp+20h] [rbp-20h] BYREF
  wchar_t *v27; // [rsp+28h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  WCHAR *v29; // [rsp+80h] [rbp+40h] BYREF
  wchar_t *Context; // [rsp+98h] [rbp+58h] BYREF

  updated = CZoneIdentifier::_UpdateFile((CZoneIdentifier *)((char *)this - 40), a2);
  if ( updated < 0 )
  {
    v8 = 697;
    goto LABEL_8;
  }
  v5 = *((_QWORD *)this + 1);
  LODWORD(v29) = 0;
  if ( !(unsigned int)PathFileExistsAndAttributesW(v5, &v29) || ((unsigned __int8)v29 & 0x10) != 0 )
    return 2147942402LL;
  v7 = (wchar_t *)((char *)this + 16);
  Context = (wchar_t *)((char *)this + 16);
  if ( *((_QWORD *)this + 2) )
  {
    CPropertyStoreHelperBase<INamedPropertyStore>::ClearPropertyStore((char *)this + 16);
    updated = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, (void **)this + 2);
    if ( updated < 0 )
    {
      v8 = 704;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
        (const char *)(unsigned int)updated,
        v26);
      return (unsigned int)updated;
    }
  }
  if ( (GetPrivateProfileIntW(L"ZoneTransfer", L"ZoneId", -1, *((LPCWSTR *)this + 1)) & 0x80000000) == 0 )
  {
    v9 = (WCHAR *)operator new[](0x1000u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v9;
    if ( v9 )
      memset_0(v9, 0, 0x1000u);
    else
      v10 = 0;
    v11 = (const WCHAR *)*((_QWORD *)this + 1);
    v12 = 2048;
    v29 = v10;
    if ( GetPrivateProfileSectionW(L"ZoneTransfer", v10, 0x800u, v11) == 2046 )
    {
      v23 = v10;
      do
      {
        v12 *= 2;
        v24 = 2LL * v12;
        if ( !is_mul_ok(v12, 2u) )
          v24 = -1;
        v25 = (WCHAR *)operator new[](v24, (const struct std::nothrow_t *)&std::nothrow);
        v10 = v25;
        if ( v25 )
          memset_0(v25, 0, v24);
        else
          v10 = 0;
        v29 = v10;
        if ( v23 )
          operator delete(v23);
        v23 = v10;
      }
      while ( GetPrivateProfileSectionW(L"ZoneTransfer", v10, v12, *((LPCWSTR *)this + 1)) == v12 - 2 );
      v7 = Context;
    }
    v13 = v10;
    LastError = GetLastError();
    if ( LastError )
    {
      updated = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x2CF, v15, (const char *)LastError, v26);
      if ( v13 )
        operator delete(v13);
      return (unsigned int)updated;
    }
    while ( *v13 )
    {
      Context = 0;
      v16 = wcstok_s(v13, L"=", &Context);
      v17 = -1;
      do
        ++v17;
      while ( v16[v17] );
      v18 = &v16[v17 + 1];
      v19 = *(_QWORD *)v7;
      v27 = v18;
      LOWORD(v26) = 31;
      v20 = (*(__int64 (__fastcall **)(__int64, wchar_t *, unsigned int *))(*(_QWORD *)v19 + 32LL))(v19, v16, &v26);
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D7,
          (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
          (const char *)(unsigned int)v20,
          v26);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v29);
        return v21;
      }
      v22 = -1;
      do
        ++v22;
      while ( v18[v22] );
      v13 = &v18[v22 + 1];
    }
    if ( v10 )
      operator delete(v10);
  }
  else
  {
    if ( !(unsigned __int8)IEConfiguration_GetBool(268435481) && !(unsigned __int8)IEConfiguration_GetBool(268435482)
      || !(unsigned __int8)IEConfiguration_GetBool(536870915) && !(unsigned __int8)IEConfiguration_GetBool(536870916) )
    {
      updated = -2147024891;
      v8 = 753;
      goto LABEL_8;
    }
    LODWORD(v29) = 0;
    updated = AskBrokerToGetZoneIdentifier((__int64)a2, (__int64)&v29);
    if ( updated < 0 )
    {
      v8 = 745;
      goto LABEL_8;
    }
    updated = CZoneIdentifier::_SetZoneId((CZoneIdentifier *)((char *)this - 40), L"ZoneId", (unsigned int)v29);
    if ( updated < 0 )
    {
      v8 = 747;
      goto LABEL_8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18006cc40  mov     [rsp-38h+arg_8], rbx
0x18006cc45  push    rbp
0x18006cc46  push    rsi
0x18006cc47  push    rdi
0x18006cc48  push    r12
0x18006cc4a  push    r13
0x18006cc4c  push    r14
0x18006cc4e  push    r15
0x18006cc50  mov     rbp, rsp
0x18006cc53  sub     rsp, 40h
0x18006cc57  mov     rdi, rcx
0x18006cc5a  mov     rsi, rdx
0x18006cc5d  add     rcx, 0FFFFFFFFFFFFFFD8h; this
0x18006cc61  call    ?_UpdateFile@CZoneIdentifier@@AEAAJPEBG@Z; CZoneIdentifier::_UpdateFile(ushort const *)
0x18006cc66  xor     r13d, r13d
0x18006cc69  mov     ebx, eax
0x18006cc6b  test    eax, eax
0x18006cc6d  js      loc_18006CEDF
0x18006cc73  mov     rcx, [rdi+8]
0x18006cc77  lea     rdx, [rbp+arg_0]
0x18006cc7b  mov     dword ptr [rbp+arg_0], r13d
0x18006cc7f  call    cs:__imp_PathFileExistsAndAttributesW
0x18006cc85  test    eax, eax
0x18006cc87  jnz     short loc_18006CCA6
0x18006cc89  mov     eax, 80070002h
0x18006cc8e  mov     rbx, [rsp+40h+arg_8]
0x18006cc96  add     rsp, 40h
0x18006cc9a  pop     r15
0x18006cc9c  pop     r14
0x18006cc9e  pop     r13
0x18006cca0  pop     r12
0x18006cca2  pop     rdi
0x18006cca3  pop     rsi
0x18006cca4  pop     rbp
0x18006cca5  retn
0x18006cca6  test    byte ptr [rbp+arg_0], 10h
0x18006ccaa  jnz     short loc_18006CC89
0x18006ccac  lea     r15, [rdi+10h]
0x18006ccb0  mov     [rbp+Context], r15
0x18006ccb4  cmp     [r15], r13
0x18006ccb7  jz      short loc_18006CCF3
0x18006ccb9  mov     rcx, r15
0x18006ccbc  call    ?ClearPropertyStore@?$CPropertyStoreHelperBase@UINamedPropertyStore@@@@QEAAXXZ; CPropertyStoreHelperBase<INamedPropertyStore>::ClearPropertyStore(void)
0x18006ccc1  mov     rdx, r15; ppv
0x18006ccc4  lea     rcx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; riid
0x18006cccb  call    cs:__imp_PSCreateMemoryPropertyStore
0x18006ccd1  mov     ebx, eax
0x18006ccd3  test    eax, eax
0x18006ccd5  jns     short loc_18006CCF3
0x18006ccd7  mov     edx, 2C0h; void *
0x18006ccdc  mov     rcx, [rbp+38h]; this
0x18006cce0  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x18006cce7  mov     r9d, ebx; char *
0x18006ccea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ccef  mov     eax, ebx
0x18006ccf1  jmp     short loc_18006CC8E
0x18006ccf3  mov     r9, [rdi+8]; lpFileName
0x18006ccf7  lea     rdx, KeyName; "ZoneId"
0x18006ccfe  or      r12, 0FFFFFFFFFFFFFFFFh
0x18006cd02  lea     rcx, AppName; "ZoneTransfer"
0x18006cd09  mov     r8d, r12d; nDefault
0x18006cd0c  call    cs:__imp_GetPrivateProfileIntW
0x18006cd12  test    eax, eax
0x18006cd14  jns     short loc_18006CD48
0x18006cd16  mov     ecx, 10000019h
0x18006cd1b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18006cd21  test    al, al
0x18006cd23  jnz     loc_18006CDD6
0x18006cd29  mov     ecx, 1000001Ah
0x18006cd2e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18006cd34  test    al, al
0x18006cd36  jnz     loc_18006CDD6
0x18006cd3c  mov     ebx, 80070005h
0x18006cd41  mov     edx, 2F1h
0x18006cd46  jmp     short loc_18006CCDC
0x18006cd48  mov     esi, 1000h
0x18006cd4d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006cd54  mov     ecx, esi; unsigned __int64
0x18006cd56  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006cd5b  mov     rbx, rax
0x18006cd5e  test    rax, rax
0x18006cd61  jz      loc_18006CE0D
0x18006cd67  mov     r8d, esi; Size
0x18006cd6a  xor     edx, edx; Val
0x18006cd6c  mov     rcx, rax; void *
0x18006cd6f  call    memset_0
0x18006cd74  mov     r9, [rdi+8]; lpFileName
0x18006cd78  lea     rcx, AppName; "ZoneTransfer"
0x18006cd7f  mov     r14d, 800h
0x18006cd85  mov     [rbp+arg_0], rbx
0x18006cd89  mov     r8d, r14d; nSize
0x18006cd8c  mov     rdx, rbx; lpReturnedString
0x18006cd8f  call    cs:__imp_GetPrivateProfileSectionW
0x18006cd95  cmp     eax, 7FEh
0x18006cd9a  jz      loc_18006CEE9
0x18006cda0  mov     rdi, rbx
0x18006cda3  call    cs:__imp_GetLastError
0x18006cda9  test    eax, eax
0x18006cdab  jz      short loc_18006CE15
0x18006cdad  mov     rcx, [rbp+38h]; this
0x18006cdb1  mov     r9d, eax; char *
0x18006cdb4  mov     edx, 2CFh; void *
0x18006cdb9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006cdbe  mov     ebx, eax
0x18006cdc0  test    rdi, rdi
0x18006cdc3  jz      loc_18006CCEF
0x18006cdc9  mov     rcx, rdi; void *
0x18006cdcc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006cdd1  jmp     loc_18006CCEF
0x18006cdd6  mov     ecx, 20000003h
0x18006cddb  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18006cde1  test    al, al
0x18006cde3  jz      loc_18006CF5E
0x18006cde9  lea     rdx, [rbp+arg_0]
0x18006cded  mov     dword ptr [rbp+arg_0], r13d
0x18006cdf1  mov     rcx, rsi
0x18006cdf4  call    _AskBrokerToGetZoneIdentifier
0x18006cdf9  mov     ebx, eax
0x18006cdfb  test    eax, eax
0x18006cdfd  jns     loc_18006CF76
0x18006ce03  mov     edx, 2E9h
0x18006ce08  jmp     loc_18006CCDC
0x18006ce0d  mov     rbx, r13
0x18006ce10  jmp     loc_18006CD74
0x18006ce15  cmp     [rdi], r13w
0x18006ce19  jz      short loc_18006CE8B
0x18006ce1b  lea     r8, [rbp+Context]; Context
0x18006ce1f  mov     [rbp+Context], r13
0x18006ce23  lea     rdx, asc_18012EBE8; "="
0x18006ce2a  mov     rcx, rdi; String
0x18006ce2d  call    cs:__imp_wcstok_s
0x18006ce33  mov     rdx, rax
0x18006ce36  mov     rcx, r12
0x18006ce39  inc     rcx
0x18006ce3c  cmp     [rax+rcx*2], r13w
0x18006ce41  jnz     short loc_18006CE39
0x18006ce43  inc     rcx
0x18006ce46  lea     r8, [rbp+var_20]
0x18006ce4a  lea     rsi, [rax+rcx*2]
0x18006ce4e  mov     rcx, [r15]
0x18006ce51  mov     eax, 1Fh
0x18006ce56  mov     [rbp+var_18], rsi
0x18006ce5a  mov     word ptr [rbp+var_20], ax
0x18006ce5e  mov     rax, [rcx]
0x18006ce61  mov     rax, [rax+20h]
0x18006ce65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ce6a  mov     edi, eax
0x18006ce6c  test    eax, eax
0x18006ce6e  js      loc_18006CF36
0x18006ce74  mov     rax, r12
0x18006ce77  inc     rax
0x18006ce7a  cmp     [rsi+rax*2], r13w
0x18006ce7f  jnz     short loc_18006CE77
0x18006ce81  lea     rdi, [rax+1]
0x18006ce85  lea     rdi, [rsi+rdi*2]
0x18006ce89  jmp     short loc_18006CE15
0x18006ce8b  test    rbx, rbx
0x18006ce8e  jz      short loc_18006CE98
0x18006ce90  mov     rcx, rbx; void *
0x18006ce93  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006ce98  xor     eax, eax
0x18006ce9a  jmp     loc_18006CC8E
0x18006ce9f  mov     [rbp+arg_0], rbx
0x18006cea3  test    rsi, rsi
0x18006cea6  jz      short loc_18006CEB0
0x18006cea8  mov     rcx, rsi; void *
0x18006ceab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006ceb0  mov     r9, [rdi+8]; lpFileName
0x18006ceb4  lea     rcx, AppName; "ZoneTransfer"
0x18006cebb  mov     r8d, r14d; nSize
0x18006cebe  mov     rdx, rbx; lpReturnedString
0x18006cec1  mov     rsi, rbx
0x18006cec4  call    cs:__imp_GetPrivateProfileSectionW
0x18006ceca  lea     ecx, [r14-2]
0x18006cece  cmp     eax, ecx
0x18006ced0  jz      short loc_18006CEF0
0x18006ced2  mov     r15, [rbp+Context]
0x18006ced6  or      r12, 0FFFFFFFFFFFFFFFFh
0x18006ceda  jmp     loc_18006CDA0
0x18006cedf  mov     edx, 2B9h
0x18006cee4  jmp     loc_18006CCDC
0x18006cee9  mov     rsi, rbx
0x18006ceec  or      r15, 0FFFFFFFFFFFFFFFFh
0x18006cef0  add     r14d, r14d
0x18006cef3  mov     eax, 2
0x18006cef8  mov     ecx, r14d
0x18006cefb  mul     rcx
0x18006cefe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006cf05  mov     r12, rax
0x18006cf08  cmovb   r12, r15
0x18006cf0c  mov     rcx, r12; unsigned __int64
0x18006cf0f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006cf14  mov     rbx, rax
0x18006cf17  test    rax, rax
0x18006cf1a  jz      short loc_18006CF2E
0x18006cf1c  mov     r8, r12; Size
0x18006cf1f  xor     edx, edx; Val
0x18006cf21  mov     rcx, rax; void *
0x18006cf24  call    memset_0
0x18006cf29  jmp     loc_18006CE9F
0x18006cf2e  mov     rbx, r13
0x18006cf31  jmp     loc_18006CE9F
0x18006cf36  mov     rcx, [rbp+38h]; this
0x18006cf3a  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x18006cf41  mov     r9d, edi; char *
0x18006cf44  mov     edx, 2D7h; void *
0x18006cf49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cf4e  lea     rcx, [rbp+arg_0]
0x18006cf52  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18006cf57  mov     eax, edi
0x18006cf59  jmp     loc_18006CC8E
0x18006cf5e  mov     ecx, 20000004h
0x18006cf63  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18006cf69  test    al, al
0x18006cf6b  jnz     loc_18006CDE9
0x18006cf71  jmp     loc_18006CD3C
0x18006cf76  mov     r8d, dword ptr [rbp+arg_0]; unsigned int
0x18006cf7a  lea     rdx, KeyName; "ZoneId"
0x18006cf81  lea     rcx, [rdi-28h]; this
0x18006cf85  call    ?_SetZoneId@CZoneIdentifier@@AEAAJPEBGK@Z; CZoneIdentifier::_SetZoneId(ushort const *,ulong)
0x18006cf8a  mov     ebx, eax
0x18006cf8c  test    eax, eax
0x18006cf8e  jns     loc_18006CE98
0x18006cf94  mov     edx, 2EBh
0x18006cf99  jmp     loc_18006CCDC
```
