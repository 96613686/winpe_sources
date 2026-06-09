# ContainerCiCacheStart

- ea: `0x18005a8c8`
- end: `0x18005aca7`
- name: `ContainerCiCacheStart`
- size: `991`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800541c8`

## callees

- `0x180002f50`
- `0x180002f74`
- `0x180003c78`
- `0x180006660`
- `0x180014870`
- `0x180018bd4`
- `0x180024ae4`
- `0x18002f94c`
- `0x180034674`
- `0x180055760`
- `0x180055b4c`
- `0x180057898`
- `0x180057b04`
- `0x1800582a8`
- `0x18005a1b0`
- `0x18005a8c8`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18005aae0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18005aae0`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18005a9a1`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18005a9a1`
- `ntdll!RtlFreeUnicodeString` at `0x18005aa08`
- `ntdll!RtlFreeUnicodeString` at `0x18005aa08`

## string_xrefs

- `0x18005ac89`: `onecore\vm\common\vml\VmPath.h`
- `0x18005a966`: `Windows\System32\catroot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ContainerCiCacheStart(PCWSTR pszPathIn, _DWORD *a2, _QWORD *a3)
{
  char *v6; // rdi
  _QWORD *v7; // rsi
  _QWORD *v8; // rax
  int v9; // eax
  _QWORD *Files; // rbx
  const char *v11; // r9
  DWORD dwNumberOfProcessors; // esi
  DWORD i; // r15d
  void *v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rbx
  void (__fastcall ***v17)(_QWORD, __int64); // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  void (__fastcall ***v20)(_QWORD, __int64); // r8
  __int64 result; // rax
  int v22; // [rsp+20h] [rbp-F8h]
  __int128 v23; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-D0h]
  __int64 v25; // [rsp+50h] [rbp-C8h]
  struct _UNICODE_STRING *p_UnicodeString; // [rsp+58h] [rbp-C0h] BYREF
  void (__fastcall *v27)(struct CiCacheState *); // [rsp+60h] [rbp-B8h]
  __int64 Src; // [rsp+70h] [rbp-A8h] BYREF
  wchar_t **v29; // [rsp+78h] [rbp-A0h]
  struct _UNICODE_STRING UnicodeString; // [rsp+90h] [rbp-88h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+A0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  *a3 = 0;
  try
  {
    EnableUSN(pszPathIn);
    SetCatalogHints(pszPathIn);
    v6 = (char *)operator new(0x70u);
    *(_WORD *)(v6 + 109) = 0;
    v6[111] = 0;
    *(_OWORD *)v6 = 0;
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 3) = 7;
    *(_WORD *)v6 = 0;
    *((_QWORD *)v6 + 4) = 0;
    *((_QWORD *)v6 + 5) = 0;
    *((_QWORD *)v6 + 6) = 0;
    v7 = v6 + 56;
    *((_QWORD *)v6 + 7) = 0;
    *((_QWORD *)v6 + 8) = 0;
    *((_QWORD *)v6 + 9) = 0;
    *((_QWORD *)v6 + 10) = 0;
    *((_QWORD *)v6 + 11) = 0;
    *((_QWORD *)v6 + 12) = 0;
    *((_DWORD *)v6 + 26) = 0;
    v6[108] = 0;
    v8 = (_QWORD *)Vml::CombineFilePath(
                     &Src,
                     pszPathIn,
                     L"Windows\\System32\\catroot\\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}");
    if ( v8[3] > 7u )
      v8 = (_QWORD *)*v8;
    UnicodeString = 0;
    v9 = RtlDosPathNameToNtPathName_U_WithStatus(v8, &UnicodeString, 0, 0);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x29E,
        (unsigned int)"onecore\\vm\\common\\vml\\VmPath.h",
        (const char *)(unsigned int)v9,
        v22);
    p_UnicodeString = &UnicodeString;
    LOBYTE(v27) = 1;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      (__int64)&v23,
      UnicodeString.Buffer,
      (unsigned __int64)UnicodeString.Length >> 1);
    RtlFreeUnicodeString(&UnicodeString);
    std::wstring::operator=(v6, &v23);
    std::wstring::~wstring(&v23);
    std::wstring::~wstring(&Src);
    Src = 5;
    v29 = off_18008AE20;
    *(_QWORD *)&UnicodeString.Length = 5;
    UnicodeString.Buffer = (PWSTR)off_18008AE48;
    Files = (_QWORD *)FindFiles(&v23, pszPathIn, &UnicodeString, &Src, 1);
    if ( v7 != Files )
    {
      std::vector<std::wstring>::_Tidy(v6 + 56);
      *v7 = *Files;
      *((_QWORD *)v6 + 8) = Files[1];
      *((_QWORD *)v6 + 9) = Files[2];
      *Files = 0;
      Files[1] = 0;
      Files[2] = 0;
    }
    std::vector<std::wstring>::_Tidy(&v23);
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetSystemInfo(&SystemInfo);
    dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
    if ( SystemInfo.dwNumberOfProcessors >= 4 )
    {
      dwNumberOfProcessors = 4;
    }
    else if ( SystemInfo.dwNumberOfProcessors <= 1 )
    {
      dwNumberOfProcessors = 1;
    }
    for ( i = 0; i < dwNumberOfProcessors; ++i )
    {
      v23 = 0;
      v24 = 0;
      p_UnicodeString = (struct _UNICODE_STRING *)v6;
      v27 = CacheFiles;
      v14 = operator new(0x120u);
      *(_QWORD *)&UnicodeString.Length = v14;
      memset_0(v14, 0, 0x120u);
      v15 = std::_Task_async_state<void>::_Task_async_state<void>((__int64)v14, &p_UnicodeString);
      v16 = v15;
      *(_QWORD *)&v23 = v15;
      BYTE8(v23) = 0;
      LOBYTE(v24) = 0;
      if ( !v15 )
        std::_Throw_future_error2(4);
      Src = v15;
      LOBYTE(v29) = 1;
      _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 8), 0xFFFFFFFF) == 1 )
      {
        v17 = *(void (__fastcall ****)(_QWORD, __int64))(v15 + 200);
        if ( v17 )
          (**v17)(v17, v15);
        else
          (**(void (__fastcall ***)(__int64, __int64))v15)(v15, 1);
      }
      v18 = *((_QWORD *)v6 + 5);
      if ( v18 == *((_QWORD *)v6 + 6) )
      {
        std::vector<std::future<void>>::_Emplace_reallocate<std::future<void>>(v6 + 32, v18, &Src);
        v19 = Src;
      }
      else
      {
        v19 = 0;
        *(_QWORD *)v18 = v16;
        *(_BYTE *)(v18 + 8) = 1;
        *((_QWORD *)v6 + 5) += 16LL;
      }
      if ( v19 && _InterlockedExchangeAdd((volatile signed __int32 *)(v19 + 8), 0xFFFFFFFF) == 1 )
      {
        v20 = *(void (__fastcall ****)(_QWORD, __int64))(v19 + 200);
        if ( v20 )
          (**v20)(*(_QWORD *)(v19 + 200), v19);
        else
          (**(void (__fastcall ***)(__int64, __int64))v19)(v19, 1);
      }
    }
    *a2 = (__int64)(*((_QWORD *)v6 + 8) - *((_QWORD *)v6 + 7)) >> 5;
    *a3 = v6;
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1C7,
                           (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x18005a8c8  push    rbx
0x18005a8ca  push    rsi
0x18005a8cb  push    rdi
0x18005a8cc  push    r12
0x18005a8ce  push    r13
0x18005a8d0  push    r14
0x18005a8d2  push    r15
0x18005a8d4  sub     rsp, 0E0h
0x18005a8db  mov     rax, cs:__security_cookie
0x18005a8e2  xor     rax, rsp
0x18005a8e5  mov     [rsp+118h+var_48], rax
0x18005a8ed  mov     r12, r8
0x18005a8f0  mov     r13, rdx
0x18005a8f3  mov     rbx, rcx
0x18005a8f6  xor     r14d, r14d
0x18005a8f9  mov     [r8], r14
0x18005a8fc  call    ?EnableUSN@@YAXPEBG@Z; EnableUSN(ushort const *)
0x18005a901  mov     rcx, rbx; pszPathIn
0x18005a904  call    ?SetCatalogHints@@YAXPEBG@Z; SetCatalogHints(ushort const *)
0x18005a909  lea     ecx, [r14+70h]; Size
0x18005a90d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a912  mov     rdi, rax
0x18005a915  xor     eax, eax
0x18005a917  mov     [rdi+6Dh], ax
0x18005a91b  mov     [rdi+6Fh], al
0x18005a91e  xorps   xmm0, xmm0
0x18005a921  movups  xmmword ptr [rdi], xmm0
0x18005a924  mov     [rdi+10h], r14
0x18005a928  mov     qword ptr [rdi+18h], 7
0x18005a930  mov     [rdi], r14w
0x18005a934  mov     [rdi+20h], r14
0x18005a938  mov     [rdi+28h], r14
0x18005a93c  mov     [rdi+30h], r14
0x18005a940  lea     rsi, [rdi+38h]
0x18005a944  mov     [rsi], r14
0x18005a947  mov     [rsi+8], r14
0x18005a94b  mov     [rsi+10h], r14
0x18005a94f  mov     [rdi+50h], r14
0x18005a953  mov     [rdi+58h], rax
0x18005a957  mov     [rdi+60h], rax
0x18005a95b  mov     [rdi+68h], eax
0x18005a95e  mov     [rdi+6Ch], al
0x18005a961  mov     [rsp+118h+var_E8], rdi
0x18005a966  lea     r8, aWindowsSystem3_7; "Windows\\System32\\catroot\\{F750E6C3-3"...
0x18005a96d  mov     rdx, rbx; pszPathIn
0x18005a970  lea     rcx, [rsp+118h+Src]; Src
0x18005a975  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18005a97a  nop
0x18005a97b  cmp     qword ptr [rax+18h], 7
0x18005a980  jbe     short loc_18005A985
0x18005a982  mov     rax, [rax]
0x18005a985  xorps   xmm0, xmm0
0x18005a988  movups  xmmword ptr [rsp+118h+UnicodeString.Length], xmm0
0x18005a990  xor     r9d, r9d
0x18005a993  xor     r8d, r8d
0x18005a996  lea     rdx, [rsp+118h+UnicodeString]
0x18005a99e  mov     rcx, rax
0x18005a9a1  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18005a9a8  nop     dword ptr [rax+rax+00h]
0x18005a9ad  mov     rcx, [rsp+118h]; this
0x18005a9b5  test    eax, eax
0x18005a9b7  js      loc_18005AC86
0x18005a9bd  lea     rax, [rsp+118h+UnicodeString]
0x18005a9c5  mov     [rsp+118h+var_C0], rax
0x18005a9ca  mov     byte ptr [rsp+118h+var_B8], 1
0x18005a9cf  xorps   xmm0, xmm0
0x18005a9d2  movups  [rsp+118h+var_E0], xmm0
0x18005a9d7  mov     [rsp+118h+var_D0], r14
0x18005a9dc  mov     [rsp+118h+var_C8], r14
0x18005a9e1  movzx   r8d, [rsp+118h+UnicodeString.Length]
0x18005a9ea  shr     r8, 1
0x18005a9ed  mov     rdx, [rsp+118h+UnicodeString.Buffer]
0x18005a9f5  lea     rcx, [rsp+118h+var_E0]
0x18005a9fa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005a9ff  nop
0x18005aa00  lea     rcx, [rsp+118h+UnicodeString]; UnicodeString
0x18005aa08  call    cs:__imp_RtlFreeUnicodeString
0x18005aa0f  nop     dword ptr [rax+rax+00h]
0x18005aa14  lea     rdx, [rsp+118h+var_E0]
0x18005aa19  mov     rcx, rdi
0x18005aa1c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005aa21  lea     rcx, [rsp+118h+var_E0]
0x18005aa26  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005aa2b  nop
0x18005aa2c  lea     rcx, [rsp+118h+Src]
0x18005aa31  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005aa36  mov     ecx, 5
0x18005aa3b  mov     [rsp+118h+Src], rcx
0x18005aa40  lea     rax, off_18008AE20; "dll"
0x18005aa47  mov     [rsp+118h+var_A0], rax
0x18005aa4c  mov     qword ptr [rsp+118h+UnicodeString.Length], rcx
0x18005aa54  lea     rax, off_18008AE48; "Windows\\System32"
0x18005aa5b  mov     [rsp+118h+UnicodeString.Buffer], rax
0x18005aa63  mov     byte ptr [rsp+118h+var_F8], 1
0x18005aa68  lea     r9, [rsp+118h+Src]
0x18005aa6d  lea     r8, [rsp+118h+UnicodeString]
0x18005aa75  mov     rdx, rbx
0x18005aa78  lea     rcx, [rsp+118h+var_E0]
0x18005aa7d  call    ?FindFiles@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGV?$span@QEBG$0?0@gsl@@1_N@Z; FindFiles(ushort const *,gsl::span<ushort const * const,-1>,gsl::span<ushort const * const,-1>,bool)
0x18005aa82  mov     rbx, rax
0x18005aa85  cmp     rsi, rax
0x18005aa88  jz      short loc_18005AAB3
0x18005aa8a  mov     rcx, rsi
0x18005aa8d  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18005aa92  mov     rcx, [rbx]
0x18005aa95  mov     [rsi], rcx
0x18005aa98  mov     rcx, [rbx+8]
0x18005aa9c  mov     [rsi+8], rcx
0x18005aaa0  mov     rcx, [rbx+10h]
0x18005aaa4  mov     [rsi+10h], rcx
0x18005aaa8  mov     [rbx], r14
0x18005aaab  mov     [rbx+8], r14
0x18005aaaf  mov     [rbx+10h], r14
0x18005aab3  lea     rcx, [rsp+118h+var_E0]
0x18005aab8  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18005aabd  xorps   xmm0, xmm0
0x18005aac0  movups  xmmword ptr [rsp+118h+SystemInfo], xmm0
0x18005aac8  movups  xmmword ptr [rsp+118h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18005aad0  movups  xmmword ptr [rsp+118h+SystemInfo.dwNumberOfProcessors], xmm0
0x18005aad8  lea     rcx, [rsp+118h+SystemInfo]; lpSystemInfo
0x18005aae0  call    cs:__imp_GetSystemInfo
0x18005aae7  nop     dword ptr [rax+rax+00h]
0x18005aaec  mov     esi, [rsp+118h+SystemInfo.dwNumberOfProcessors]
0x18005aaf3  cmp     esi, 4
0x18005aaf6  jnb     short loc_18005AB04
0x18005aaf8  cmp     esi, 1
0x18005aafb  ja      short loc_18005AB09
0x18005aafd  mov     esi, 1
0x18005ab02  jmp     short loc_18005AB09
0x18005ab04  mov     esi, 4
0x18005ab09  mov     r15d, r14d
0x18005ab0c  cmp     r15d, esi
0x18005ab0f  jnb     loc_18005AC46
0x18005ab15  xorps   xmm0, xmm0
0x18005ab18  xor     eax, eax
0x18005ab1a  movups  [rsp+118h+var_E0], xmm0
0x18005ab1f  mov     [rsp+118h+var_D0], rax
0x18005ab24  mov     [rsp+118h+var_C0], rdi
0x18005ab29  lea     rax, ?CacheFiles@@YAXPEAUCiCacheState@@@Z; CacheFiles(CiCacheState *)
0x18005ab30  mov     [rsp+118h+var_B8], rax
0x18005ab35  mov     ecx, 120h; Size
0x18005ab3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005ab3f  mov     rbx, rax
0x18005ab42  mov     qword ptr [rsp+118h+UnicodeString.Length], rax
0x18005ab4a  xor     edx, edx; Val
0x18005ab4c  mov     r8d, 120h; Size
0x18005ab52  mov     rcx, rax; void *
0x18005ab55  call    memset_0
0x18005ab5a  lea     rdx, [rsp+118h+var_C0]
0x18005ab5f  mov     rcx, rbx
0x18005ab62  call    ??$?0V?$_Fake_no_copy_callable_adapter@A6AXPEAUCiCacheState@@@ZPEAU1@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@A6AXPEAUCiCacheState@@@ZPEAU1@@1@@Z; std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<void (&)(CiCacheState *),CiCacheState *> &&)
0x18005ab67  mov     rbx, rax
0x18005ab6a  mov     qword ptr [rsp+118h+var_E0], rax
0x18005ab6f  mov     byte ptr [rsp+118h+var_E0+8], r14b
0x18005ab74  mov     byte ptr [rsp+118h+var_D0], r14b
0x18005ab79  test    rax, rax
0x18005ab7c  jz      loc_18005AC9B
0x18005ab82  mov     [rsp+118h+Src], rax
0x18005ab87  mov     byte ptr [rsp+118h+var_A0], 1
0x18005ab8c  lock inc dword ptr [rax+8]
0x18005ab90  or      eax, 0FFFFFFFFh
0x18005ab93  lock xadd [rbx+8], eax
0x18005ab98  cmp     eax, 1
0x18005ab9b  jnz     short loc_18005ABCD
0x18005ab9d  mov     rcx, [rbx+0C8h]
0x18005aba4  test    rcx, rcx
0x18005aba7  jz      short loc_18005ABB9
0x18005aba9  mov     rax, [rcx]
0x18005abac  mov     rdx, rbx
0x18005abaf  mov     rax, [rax]
0x18005abb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005abb7  jmp     short loc_18005ABCD
0x18005abb9  mov     rax, [rbx]
0x18005abbc  mov     edx, 1
0x18005abc1  mov     rcx, rbx
0x18005abc4  mov     rax, [rax]
0x18005abc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005abcc  nop
0x18005abcd  mov     rdx, [rdi+28h]
0x18005abd1  cmp     rdx, [rdi+30h]
0x18005abd5  jz      short loc_18005ABE7
0x18005abd7  xor     ecx, ecx
0x18005abd9  mov     [rdx], rbx
0x18005abdc  mov     byte ptr [rdx+8], 1
0x18005abe0  add     qword ptr [rdi+28h], 10h
0x18005abe5  jmp     short loc_18005ABFA
0x18005abe7  lea     r8, [rsp+118h+Src]
0x18005abec  lea     rcx, [rdi+20h]
0x18005abf0  call    ??$_Emplace_reallocate@V?$future@X@std@@@?$vector@V?$future@X@std@@V?$allocator@V?$future@X@std@@@2@@std@@AEAAPEAV?$future@X@1@QEAV21@$$QEAV21@@Z; std::vector<std::future<void>>::_Emplace_reallocate<std::future<void>>(std::future<void> * const,std::future<void> &&)
0x18005abf5  mov     rcx, [rsp+118h+Src]
0x18005abfa  xor     r14d, r14d
0x18005abfd  test    rcx, rcx
0x18005ac00  jz      short loc_18005AC3E
0x18005ac02  or      eax, 0FFFFFFFFh
0x18005ac05  lock xadd [rcx+8], eax
0x18005ac0a  cmp     eax, 1
0x18005ac0d  jnz     short loc_18005AC3E
0x18005ac0f  mov     r8, [rcx+0C8h]
0x18005ac16  test    r8, r8
0x18005ac19  jz      short loc_18005AC2E
0x18005ac1b  mov     rax, [r8]
0x18005ac1e  mov     rdx, rcx
0x18005ac21  mov     rcx, r8
0x18005ac24  mov     rax, [rax]
0x18005ac27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac2c  jmp     short loc_18005AC3E
0x18005ac2e  mov     rax, [rcx]
0x18005ac31  mov     edx, 1
0x18005ac36  mov     rax, [rax]
0x18005ac39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac3e  inc     r15d
0x18005ac41  jmp     loc_18005AB0C
0x18005ac46  mov     rax, [rdi+40h]
0x18005ac4a  sub     rax, [rdi+38h]
0x18005ac4e  sar     rax, 5
0x18005ac52  mov     [r13+0], eax
0x18005ac56  mov     [r12], rdi
0x18005ac5a  xor     eax, eax
0x18005ac5c  jmp     short loc_18005AC62
0x18005ac5e  mov     eax, dword ptr [rsp+118h+var_E8]
0x18005ac62  mov     rcx, [rsp+118h+var_48]
0x18005ac6a  xor     rcx, rsp; StackCookie
0x18005ac6d  call    __security_check_cookie
0x18005ac72  add     rsp, 0E0h
0x18005ac79  pop     r15
0x18005ac7b  pop     r14
0x18005ac7d  pop     r13
0x18005ac7f  pop     r12
0x18005ac81  pop     rdi
0x18005ac82  pop     rsi
0x18005ac83  pop     rbx
0x18005ac84  retn
0x18005ac86  mov     r9d, eax; char *
0x18005ac89  lea     r8, aOnecoreVmCommo_1; "onecore\\vm\\common\\vml\\VmPath.h"
0x18005ac90  mov     edx, 29Eh; void *
0x18005ac95  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18005ac9b  mov     ecx, 4
0x18005aca0  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```
