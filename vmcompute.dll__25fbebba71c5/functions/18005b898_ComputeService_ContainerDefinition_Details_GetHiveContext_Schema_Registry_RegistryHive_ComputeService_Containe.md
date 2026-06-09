# ComputeService::ContainerDefinition::Details::GetHiveContext(Schema::Registry::RegistryHive,ComputeService::ContainerDefinition::Details::OfflineHiveContext * const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18005b898`
- end: `0x18005bbe0`
- name: `?GetHiveContext@Details@ContainerDefinition@ComputeService@@YAAEAUOfflineHiveContext@123@W4RegistryHive@Registry@Schema@@QEAU4123@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@9@@Z`
- size: `840`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002f0c4`

## callees

- `0x180002f50`
- `0x180002f74`
- `0x180003388`
- `0x180006660`
- `0x18000d0ec`
- `0x180014754`
- `0x180014870`
- `0x180018bd4`
- `0x180022d10`
- `0x18002f94c`
- `0x1800343d8`
- `0x18005b898`
- `0x18007b1e4`
- `0x18007b2c8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005b9e1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005baa4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005b9e1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005baa4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005b9b8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005ba7c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005b9b8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005ba7c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18005ba03`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18005bac5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18005ba03`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18005bac5`

## string_xrefs

- `0x18005bb6d`: `onecore\vm\compute\shared\container\registrychanges.cpp`
- `0x18005bb8c`: `onecore\vm\compute\shared\container\registrychanges.cpp`
- `0x18005bbb9`: `onecore\vm\compute\shared\container\registrychanges.cpp`
- `0x18005bbcb`: `onecore\vm\compute\shared\container\registrychanges.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComputeService::ContainerDefinition::Details::GetHiveContext(
        int a1,
        __int64 a2,
        __int64 *a3,
        const WCHAR *a4)
{
  __int64 v6; // rax
  __int64 v7; // rdi
  const unsigned __int16 *const near *v9; // rdx
  unsigned __int64 v10; // r8
  const WCHAR *v11; // r8
  __int64 v12; // rax
  __int128 *v13; // rbx
  const WCHAR *v14; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v16; // rcx
  const char *v17; // r9
  const WCHAR *v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rsi
  const WCHAR *v21; // r8
  const WCHAR *v22; // rdx
  const WCHAR *v23; // rcx
  DWORD v24; // eax
  const WCHAR *v25; // rcx
  const char *v26; // r9
  const WCHAR *v27; // rcx
  LPCWSTR *v28; // rdx
  OfflineHiveLib::OfflineHive *v29; // rsi
  unsigned int v30; // [rsp+20h] [rbp-59h]
  char *v31; // [rsp+28h] [rbp-51h]
  void *v32; // [rsp+30h] [rbp-49h]
  LPCWSTR lpFileName[3]; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int64 v34; // [rsp+50h] [rbp-29h]
  PCWSTR pszMore[2]; // [rsp+58h] [rbp-21h] BYREF
  __int64 v36; // [rsp+68h] [rbp-11h]
  unsigned __int64 v37; // [rsp+70h] [rbp-9h]
  __int128 v38; // [rsp+78h] [rbp-1h] BYREF
  __int64 v39; // [rsp+88h] [rbp+Fh]
  __int64 v40; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( a1 )
  {
    switch ( a1 )
    {
      case 1:
        v6 = 40;
        break;
      case 2:
        v6 = 80;
        break;
      case 3:
        v6 = 120;
        break;
      default:
        LODWORD(v31) = a1;
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0xD6,
          (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
          (const char *)0xD,
          (unsigned int)"unsupported type: %d",
          v31);
    }
  }
  else
  {
    v6 = 0;
  }
  v7 = a2 + v6;
  if ( !*(_QWORD *)(a2 + v6) )
  {
    v38 = 0;
    v39 = 0;
    v40 = 7;
    LOWORD(v38) = 0;
    v9 = (&Schema::Registry::RegistryHive_EnumData_Names)[a1];
    *(_OWORD *)pszMore = 0;
    v36 = 0;
    v37 = 0;
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v9 + v10) );
    std::wstring::_Construct<1,unsigned short const *>((__int64)pszMore, v9, v10);
    v11 = (const WCHAR *)pszMore;
    if ( v37 > 7 )
      v11 = pszMore[0];
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(const WCHAR **)a4;
    v12 = Vml::CombineFilePath(lpFileName, a4, v11);
    v13 = (__int128 *)(v7 + 8);
    std::wstring::operator=(v7 + 8, v12);
    std::wstring::~wstring(lpFileName);
    if ( *(_QWORD *)(v7 + 32) <= 7u )
      v14 = (const WCHAR *)(v7 + 8);
    else
      v14 = *(const WCHAR **)v13;
    FileAttributesW = GetFileAttributesW(v14);
    if ( FileAttributesW != -1 && (FileAttributesW & 0x400) != 0 )
    {
      v16 = *(_QWORD *)(v7 + 32) <= 7u ? (const WCHAR *)(v7 + 8) : *(const WCHAR **)v13;
      if ( !DeleteFileW(v16) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xED,
          (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
          v17);
    }
    if ( *(_QWORD *)(v7 + 32) <= 7u )
      v18 = (const WCHAR *)(v7 + 8);
    else
      v18 = *(const WCHAR **)v13;
    if ( PathFileExistsW(v18) )
    {
      if ( &v38 != v13 )
      {
        if ( *(_QWORD *)(v7 + 32) > 7u )
          v13 = *(__int128 **)v13;
        std::wstring::_Assign<unsigned short>(&v38, v13, *(_QWORD *)(v7 + 24));
      }
    }
    else
    {
      v19 = *a3;
      v20 = a3[1];
      while ( 1 )
      {
        if ( v19 == v20 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x110,
            (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
            (const char *)2,
            v30);
        v21 = (const WCHAR *)pszMore;
        if ( v37 > 7 )
          v21 = pszMore[0];
        if ( *(_QWORD *)(v19 + 24) <= 7u )
          v22 = (const WCHAR *)v19;
        else
          v22 = *(const WCHAR **)v19;
        Vml::CombineFilePath(lpFileName, v22, v21);
        v23 = (const WCHAR *)lpFileName;
        if ( v34 > 7 )
          v23 = lpFileName[0];
        v24 = GetFileAttributesW(v23);
        if ( v24 != -1 && (v24 & 0x400) != 0 )
        {
          v25 = (const WCHAR *)lpFileName;
          if ( v34 > 7 )
            v25 = lpFileName[0];
          if ( !DeleteFileW(v25) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x103,
              (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
              v26);
        }
        v27 = (const WCHAR *)lpFileName;
        if ( v34 > 7 )
          v27 = lpFileName[0];
        if ( PathFileExistsW(v27) )
          break;
        std::wstring::~wstring(lpFileName);
        v19 += 32;
      }
      v28 = lpFileName;
      if ( v34 > 7 )
        v28 = (LPCWSTR *)lpFileName[0];
      std::wstring::_Assign<unsigned short>(&v38, v28, lpFileName[2]);
      std::wstring::~wstring(lpFileName);
    }
    v32 = operator new(0x30u);
    OfflineHiveLib::OfflineHive::OfflineHive(v32, &v38);
    v29 = *(OfflineHiveLib::OfflineHive **)v7;
    *(_QWORD *)v7 = v32;
    if ( v29 )
    {
      OfflineHiveLib::OfflineHive::~OfflineHive(v29);
      operator delete(v29, 0x30u);
    }
    std::wstring::~wstring(pszMore);
    std::wstring::~wstring(&v38);
  }
  return v7;
}

```

## disassembly

```asm
0x18005b898  push    rbp
0x18005b89a  push    rbx
0x18005b89b  push    rsi
0x18005b89c  push    rdi
0x18005b89d  push    r12
0x18005b89f  push    r14
0x18005b8a1  push    r15
0x18005b8a3  lea     rbp, [rsp-27h]
0x18005b8a8  sub     rsp, 0A0h
0x18005b8af  mov     rax, cs:__security_cookie
0x18005b8b6  xor     rax, rsp
0x18005b8b9  mov     [rbp+57h+var_38], rax
0x18005b8bd  mov     rbx, r9
0x18005b8c0  mov     r14, r8
0x18005b8c3  mov     r10, rdx
0x18005b8c6  movsxd  r9, ecx
0x18005b8c9  xor     r12d, r12d
0x18005b8cc  mov     edx, r9d
0x18005b8cf  test    ecx, ecx
0x18005b8d1  jz      short loc_18005B8F9
0x18005b8d3  sub     edx, 1
0x18005b8d6  jz      short loc_18005B8F2
0x18005b8d8  sub     edx, 1
0x18005b8db  jz      short loc_18005B8EB
0x18005b8dd  cmp     edx, 1
0x18005b8e0  jnz     loc_18005BB9E
0x18005b8e6  lea     eax, [rdx+77h]
0x18005b8e9  jmp     short loc_18005B8FC
0x18005b8eb  mov     eax, 50h ; 'P'
0x18005b8f0  jmp     short loc_18005B8FC
0x18005b8f2  mov     eax, 28h ; '('
0x18005b8f7  jmp     short loc_18005B8FC
0x18005b8f9  mov     rax, r12
0x18005b8fc  lea     rdi, [r10+rax]
0x18005b900  cmp     [rdi], r12
0x18005b903  jz      short loc_18005B927
0x18005b905  mov     rax, rdi
0x18005b908  mov     rcx, [rbp+57h+var_38]
0x18005b90c  xor     rcx, rsp; StackCookie
0x18005b90f  call    __security_check_cookie
0x18005b914  add     rsp, 0A0h
0x18005b91b  pop     r15
0x18005b91d  pop     r14
0x18005b91f  pop     r12
0x18005b921  pop     rdi
0x18005b922  pop     rsi
0x18005b923  pop     rbx
0x18005b924  pop     rbp
0x18005b925  retn
0x18005b927  xorps   xmm0, xmm0
0x18005b92a  movups  [rbp+57h+var_58], xmm0
0x18005b92e  mov     [rbp+57h+var_48], r12
0x18005b932  mov     r15d, 7
0x18005b938  mov     [rbp+57h+var_40], r15
0x18005b93c  mov     word ptr [rbp+57h+var_58], r12w
0x18005b941  lea     rdx, ?RegistryHive_EnumData_Names@Registry@Schema@@3QBQEBGB; ushort const * const near * const Schema::Registry::RegistryHive_EnumData_Names
0x18005b948  mov     rdx, [rdx+r9*8]
0x18005b94c  movups  xmmword ptr [rbp+57h+pszMore], xmm0
0x18005b950  mov     [rbp+57h+var_68], r12
0x18005b954  mov     [rbp+57h+var_60], r12
0x18005b958  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005b95c  inc     r8
0x18005b95f  cmp     [rdx+r8*2], r12w
0x18005b964  jnz     short loc_18005B95C
0x18005b966  lea     rcx, [rbp+57h+pszMore]
0x18005b96a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005b96f  nop
0x18005b970  lea     r8, [rbp+57h+pszMore]
0x18005b974  cmp     [rbp+57h+var_60], r15
0x18005b978  cmova   r8, [rbp+57h+pszMore]; pszMore
0x18005b97d  cmp     [rbx+18h], r15
0x18005b981  jbe     short loc_18005B986
0x18005b983  mov     rbx, [rbx]
0x18005b986  mov     rdx, rbx; pszPathIn
0x18005b989  lea     rcx, [rbp+57h+lpFileName]; Src
0x18005b98d  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18005b992  lea     rbx, [rdi+8]
0x18005b996  mov     rdx, rax
0x18005b999  mov     rcx, rbx
0x18005b99c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005b9a1  lea     rcx, [rbp+57h+lpFileName]
0x18005b9a5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005b9aa  cmp     [rbx+18h], r15
0x18005b9ae  jbe     short loc_18005B9B5
0x18005b9b0  mov     rcx, [rbx]
0x18005b9b3  jmp     short loc_18005B9B8
0x18005b9b5  mov     rcx, rbx; lpFileName
0x18005b9b8  call    cs:__imp_GetFileAttributesW
0x18005b9bf  nop     dword ptr [rax+rax+00h]
0x18005b9c4  cmp     eax, 0FFFFFFFFh
0x18005b9c7  jz      short loc_18005B9F5
0x18005b9c9  bt      eax, 0Ah
0x18005b9cd  jnb     short loc_18005B9F5
0x18005b9cf  cmp     [rbx+18h], r15
0x18005b9d3  jbe     short loc_18005B9DA
0x18005b9d5  mov     rcx, [rbx]
0x18005b9d8  jmp     short loc_18005B9DD
0x18005b9da  mov     rcx, rbx; lpFileName
0x18005b9dd  mov     rsi, [rbp+5Fh]
0x18005b9e1  call    cs:__imp_DeleteFileW
0x18005b9e8  nop     dword ptr [rax+rax+00h]
0x18005b9ed  test    eax, eax
0x18005b9ef  jz      loc_18005BBCB
0x18005b9f5  cmp     [rbx+18h], r15
0x18005b9f9  jbe     short loc_18005BA00
0x18005b9fb  mov     rcx, [rbx]
0x18005b9fe  jmp     short loc_18005BA03
0x18005ba00  mov     rcx, rbx; pszPath
0x18005ba03  call    cs:__imp_PathFileExistsW
0x18005ba0a  nop     dword ptr [rax+rax+00h]
0x18005ba0f  test    eax, eax
0x18005ba11  jz      short loc_18005BA3E
0x18005ba13  lea     rax, [rbp+57h+var_58]
0x18005ba17  cmp     rax, rbx
0x18005ba1a  jz      loc_18005BB14
0x18005ba20  mov     r8, [rbx+10h]
0x18005ba24  cmp     [rbx+18h], r15
0x18005ba28  jbe     short loc_18005BA2D
0x18005ba2a  mov     rbx, [rbx]
0x18005ba2d  mov     rdx, rbx
0x18005ba30  lea     rcx, [rbp+57h+var_58]
0x18005ba34  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005ba39  jmp     loc_18005BB14
0x18005ba3e  mov     rbx, [r14]
0x18005ba41  mov     rsi, [r14+8]
0x18005ba45  jmp     loc_18005BAE2
0x18005ba4a  lea     r8, [rbp+57h+pszMore]
0x18005ba4e  cmp     [rbp+57h+var_60], r15
0x18005ba52  cmova   r8, [rbp+57h+pszMore]; pszMore
0x18005ba57  cmp     [rbx+18h], r15
0x18005ba5b  jbe     short loc_18005BA62
0x18005ba5d  mov     rdx, [rbx]
0x18005ba60  jmp     short loc_18005BA65
0x18005ba62  mov     rdx, rbx; pszPathIn
0x18005ba65  lea     rcx, [rbp+57h+lpFileName]; Src
0x18005ba69  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18005ba6e  nop
0x18005ba6f  lea     rcx, [rbp+57h+lpFileName]
0x18005ba73  cmp     [rbp+57h+var_80], r15
0x18005ba77  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18005ba7c  call    cs:__imp_GetFileAttributesW
0x18005ba83  nop     dword ptr [rax+rax+00h]
0x18005ba88  cmp     eax, 0FFFFFFFFh
0x18005ba8b  jz      short loc_18005BAB8
0x18005ba8d  bt      eax, 0Ah
0x18005ba91  jnb     short loc_18005BAB8
0x18005ba93  lea     rcx, [rbp+57h+lpFileName]
0x18005ba97  cmp     [rbp+57h+var_80], r15
0x18005ba9b  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18005baa0  mov     r14, [rbp+5Fh]
0x18005baa4  call    cs:__imp_DeleteFileW
0x18005baab  nop     dword ptr [rax+rax+00h]
0x18005bab0  test    eax, eax
0x18005bab2  jz      loc_18005BB6D
0x18005bab8  lea     rcx, [rbp+57h+lpFileName]
0x18005babc  cmp     [rbp+57h+var_80], r15
0x18005bac0  cmova   rcx, [rbp+57h+lpFileName]; pszPath
0x18005bac5  call    cs:__imp_PathFileExistsW
0x18005bacc  nop     dword ptr [rax+rax+00h]
0x18005bad1  test    eax, eax
0x18005bad3  jnz     short loc_18005BAF0
0x18005bad5  lea     rcx, [rbp+57h+lpFileName]
0x18005bad9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005bade  add     rbx, 20h ; ' '
0x18005bae2  cmp     rbx, rsi
0x18005bae5  jz      loc_18005BB82
0x18005baeb  jmp     loc_18005BA4A
0x18005baf0  lea     rdx, [rbp+57h+lpFileName]
0x18005baf4  cmp     [rbp+57h+var_80], r15
0x18005baf8  cmova   rdx, [rbp+57h+lpFileName]
0x18005bafd  mov     r8, [rbp+57h+var_88]
0x18005bb01  lea     rcx, [rbp+57h+var_58]
0x18005bb05  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005bb0a  nop
0x18005bb0b  lea     rcx, [rbp+57h+lpFileName]
0x18005bb0f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005bb14  mov     r14d, 30h ; '0'
0x18005bb1a  mov     ecx, r14d; Size
0x18005bb1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005bb22  mov     rbx, rax
0x18005bb25  mov     [rbp+57h+var_A0], rax
0x18005bb29  lea     rdx, [rbp+57h+var_58]
0x18005bb2d  mov     rcx, rax
0x18005bb30  call    ??0OfflineHive@OfflineHiveLib@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; OfflineHiveLib::OfflineHive::OfflineHive(std::wstring const &,bool)
0x18005bb35  nop
0x18005bb36  mov     rsi, [rdi]
0x18005bb39  mov     [rdi], rbx
0x18005bb3c  test    rsi, rsi
0x18005bb3f  jz      short loc_18005BB55
0x18005bb41  mov     rcx, rsi; this
0x18005bb44  call    ??1OfflineHive@OfflineHiveLib@@QEAA@XZ; OfflineHiveLib::OfflineHive::~OfflineHive(void)
0x18005bb49  mov     edx, r14d; unsigned __int64
0x18005bb4c  mov     rcx, rsi; void *
0x18005bb4f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005bb54  nop
0x18005bb55  lea     rcx, [rbp+57h+pszMore]
0x18005bb59  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005bb5e  nop
0x18005bb5f  lea     rcx, [rbp+57h+var_58]
0x18005bb63  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005bb68  jmp     loc_18005B905
0x18005bb6d  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\shared\\container"...
0x18005bb74  mov     edx, 103h; void *
0x18005bb79  mov     rcx, r14; this
0x18005bb7c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005bb82  mov     rcx, [rbp+5Fh]; this
0x18005bb86  mov     r9d, 2; char *
0x18005bb8c  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\shared\\container"...
0x18005bb93  mov     edx, 110h; void *
0x18005bb98  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005bb9e  mov     rcx, [rbp+5Fh]; this
0x18005bba2  mov     dword ptr [rsp+0D0h+var_A8], r9d; char *
0x18005bba7  lea     rax, aUnsupportedTyp; "unsupported type: %d"
0x18005bbae  mov     qword ptr [rsp+0D0h+var_B0], rax; unsigned int
0x18005bbb3  mov     r9d, 0Dh; char *
0x18005bbb9  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\shared\\container"...
0x18005bbc0  mov     edx, 0D6h; void *
0x18005bbc5  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18005bbcb  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\shared\\container"...
0x18005bbd2  mov     edx, 0EDh; void *
0x18005bbd7  mov     rcx, rsi; this
0x18005bbda  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
