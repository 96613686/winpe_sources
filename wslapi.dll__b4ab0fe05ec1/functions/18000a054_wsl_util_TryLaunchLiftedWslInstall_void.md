# wsl::util::TryLaunchLiftedWslInstall(void)

- ea: `0x18000a054`
- end: `0x18000a442`
- name: `?TryLaunchLiftedWslInstall@util@wsl@@YAJXZ`
- size: `1006`
- prototype: `__int64 __fastcall(wsl::util *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008ea0`

## callees

- `0x180001dc0`
- `0x180002ab4`
- `0x180006968`
- `0x18000854c`
- `0x180009058`
- `0x1800094ec`
- `0x18000955c`
- `0x180009970`
- `0x1800099ec`
- `0x180009df4`
- `0x180009e88`
- `0x180009eb8`
- `0x180009fb8`
- `0x18000a054`
- `0x18000a478`
- `0x18000a4d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a083`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000a3c5`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000a3c5`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18000a2ee`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18000a2ee`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18000a0b7`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18000a0b7`

## string_xrefs

- `0x18000a1b5`: `update`

## pseudocode

```c
__int64 __fastcall wsl::util::TryLaunchLiftedWslInstall(wsl::util *this)
{
  const char *v2; // r9
  int v3; // edi
  void *v4; // rdx
  unsigned int v5; // r8d
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  const char *v12; // r9
  WCHAR *v13; // rdx
  struct _PROCESS_INFORMATION *v14; // rdx
  const char *v15; // r9
  struct _PROC_THREAD_ATTRIBUTE_LIST *v16; // rdx
  int cbSize; // [rsp+20h] [rbp-278h]
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+50h] [rbp-248h] BYREF
  _OWORD v19[2]; // [rsp+58h] [rbp-240h] BYREF
  char *v20[4]; // [rsp+78h] [rbp-220h] BYREF
  char *v21[4]; // [rsp+98h] [rbp-200h] BYREF
  char *v22[4]; // [rsp+B8h] [rbp-1E0h] BYREF
  char *v23[4]; // [rsp+D8h] [rbp-1C0h] BYREF
  char *v24[4]; // [rsp+F8h] [rbp-1A0h] BYREF
  char *v25[4]; // [rsp+118h] [rbp-180h] BYREF
  char *v26[4]; // [rsp+138h] [rbp-160h] BYREF
  _BYTE v27[8]; // [rsp+158h] [rbp-140h] BYREF
  _QWORD v28[14]; // [rsp+160h] [rbp-138h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+1D0h] [rbp-C8h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST v30; // [rsp+238h] [rbp-60h]
  HANDLE hObject; // [rsp+240h] [rbp-58h] BYREF
  LPWSTR lpCommandLine[2]; // [rsp+248h] [rbp-50h] BYREF
  __m128i si128; // [rsp+258h] [rbp-40h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+268h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  hObject = 0;
  wsl::util::OpenInstallMutex(&hObject);
  if ( GetLastError() == 183 )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    return 1;
  }
  else
  {
    if ( !SetHandleInformation(hObject, 1u, 1u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x120,
        (int)"onecore\\vm\\wsl\\lxss\\wslutil\\wslutil.cpp",
        v2);
    *(_OWORD *)lpCommandLine = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpCommandLine[0]) = 0;
    v28[0] = &wistd::__function::__func<_lambda_b184ef8228511dea446194ec32405fe9_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
    v28[13] = v28;
    v3 = wil::AdaptFixedSizeToAllocatedResult<std::wstring,256>((__int64)lpCommandLine, (__int64)v27);
    wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v27);
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, v4, v5, (const char *)(unsigned int)v3, cbSize);
    memset(v19, 0, sizeof(v19));
    std::wstring::_Construct<1,unsigned short const *>(v19, L"\\", 1);
    v6 = std::operator+<unsigned short>(v26, v19, L"wsl.exe");
    v7 = std::operator+<unsigned short>(v25, v6, L" --");
    v8 = std::operator+<unsigned short>(v24, v7, L"update");
    v9 = std::operator+<unsigned short>(v23, v8, L" --");
    v10 = std::operator+<unsigned short>(v22, v9, L"confirm");
    v11 = std::operator+<unsigned short>(v21, v10, L" --");
    std::operator+<unsigned short>(v20, v11, L"prompt-before-exit");
    std::wstring::_Append<unsigned short>(lpCommandLine);
    std::wstring::_Tidy_deallocate(v20);
    std::wstring::_Tidy_deallocate(v21);
    std::wstring::_Tidy_deallocate(v22);
    std::wstring::_Tidy_deallocate(v23);
    std::wstring::_Tidy_deallocate(v24);
    std::wstring::_Tidy_deallocate(v25);
    std::wstring::_Tidy_deallocate(v26);
    std::wstring::_Tidy_deallocate((char **)v19);
    lpAttributeList = 0;
    wsl::util::CreateProcThreadAttributeList(&lpAttributeList);
    if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20002u, &hObject, 8u, 0, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x131,
        (int)"onecore\\vm\\wsl\\lxss\\wslutil\\wslutil.cpp",
        v12);
    memset_0(&StartupInfo, 0, 0x70u);
    StartupInfo.cb = 112;
    StartupInfo.dwFlags = 1;
    StartupInfo.wShowWindow = 5;
    v30 = lpAttributeList;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    v13 = (WCHAR *)lpCommandLine;
    if ( si128.m128i_i64[1] > 7uLL )
      v13 = lpCommandLine[0];
    if ( !CreateProcessW(0, v13, 0, 0, 1, 0x80010u, 0, 0, &StartupInfo, &ProcessInformation) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x142,
        (int)"onecore\\vm\\wsl\\lxss\\wslutil\\wslutil.cpp",
        v15);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v14);
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&void wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&void wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(
      &lpAttributeList,
      v16);
    std::wstring::_Tidy_deallocate((char **)lpCommandLine);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    return 0;
  }
}

```

## disassembly

```asm
0x18000a054  mov     r11, rsp
0x18000a057  push    rdi
0x18000a058  sub     rsp, 290h
0x18000a05f  mov     rax, cs:__security_cookie
0x18000a066  xor     rax, rsp
0x18000a069  mov     [rsp+298h+var_18], rax
0x18000a071  mov     qword ptr [r11-58h], 0
0x18000a079  lea     rcx, [r11-58h]
0x18000a07d  call    ?OpenInstallMutex@util@wsl@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; wsl::util::OpenInstallMutex(void)
0x18000a082  nop
0x18000a083  call    cs:__imp_GetLastError
0x18000a089  cmp     eax, 0B7h
0x18000a08e  jnz     short loc_18000A0A7
0x18000a090  lea     rcx, [rsp+298h+hObject]
0x18000a098  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a09d  mov     eax, 1
0x18000a0a2  jmp     loc_18000A428
0x18000a0a7  mov     edx, 1; dwMask
0x18000a0ac  mov     r8d, edx; dwFlags
0x18000a0af  mov     rcx, [rsp+298h+hObject]; hObject
0x18000a0b7  call    cs:__imp_SetHandleInformation
0x18000a0bd  test    eax, eax
0x18000a0bf  jnz     short loc_18000A0DA
0x18000a0c1  mov     rcx, [rsp+298h]; this
0x18000a0c9  lea     r8, aOnecoreVmWslLx_0; "onecore\\vm\\wsl\\lxss\\wslutil\\wsluti"...
0x18000a0d0  mov     edx, 120h; void *
0x18000a0d5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000a0da  xorps   xmm0, xmm0
0x18000a0dd  movups  xmmword ptr [rsp+298h+lpCommandLine], xmm0
0x18000a0e5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000a0ed  movdqu  [rsp+298h+var_40], xmm1
0x18000a0f6  xor     eax, eax
0x18000a0f8  mov     word ptr [rsp+298h+lpCommandLine], ax
0x18000a100  lea     rax, ??_7?$__func@V_lambda_b184ef8228511dea446194ec32405fe9_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_b184ef8228511dea446194ec32405fe9_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18000a107  mov     [rsp+298h+var_138], rax
0x18000a10f  lea     rax, [rsp+298h+var_138]
0x18000a117  mov     [rsp+298h+var_D0], rax
0x18000a11f  lea     rdx, [rsp+298h+var_140]
0x18000a127  lea     rcx, [rsp+298h+lpCommandLine]
0x18000a12f  call    ??$AdaptFixedSizeToAllocatedResult@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0BAA@@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<std::wstring,256>(std::wstring &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x18000a134  mov     edi, eax
0x18000a136  lea     rcx, [rsp+298h+var_140]
0x18000a13e  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x18000a143  mov     rcx, [rsp+298h]; this
0x18000a14b  test    edi, edi
0x18000a14d  jns     short loc_18000A157
0x18000a14f  mov     r9d, edi; char *
0x18000a152  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a157  xorps   xmm0, xmm0
0x18000a15a  movups  [rsp+298h+var_240], xmm0
0x18000a15f  xorps   xmm1, xmm1
0x18000a162  movdqu  [rsp+298h+var_230], xmm1
0x18000a168  mov     r8d, 1
0x18000a16e  lea     rdx, asc_18000F140; "\\"
0x18000a175  lea     rcx, [rsp+298h+var_240]
0x18000a17a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000a17f  nop
0x18000a180  lea     r8, aWslExe; "wsl.exe"
0x18000a187  lea     rdx, [rsp+298h+var_240]
0x18000a18c  lea     rcx, [rsp+298h+var_160]
0x18000a194  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18000a199  nop
0x18000a19a  lea     rdi, asc_18000F120; " --"
0x18000a1a1  mov     r8, rdi
0x18000a1a4  mov     rdx, rax
0x18000a1a7  lea     rcx, [rsp+298h+var_180]
0x18000a1af  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18000a1b4  nop
0x18000a1b5  lea     r8, aUpdate; "update"
0x18000a1bc  mov     rdx, rax
0x18000a1bf  lea     rcx, [rsp+298h+var_1A0]
0x18000a1c7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18000a1cc  nop
0x18000a1cd  mov     r8, rdi
0x18000a1d0  mov     rdx, rax
0x18000a1d3  lea     rcx, [rsp+298h+var_1C0]
0x18000a1db  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18000a1e0  nop
0x18000a1e1  lea     r8, aConfirm; "confirm"
0x18000a1e8  mov     rdx, rax
0x18000a1eb  lea     rcx, [rsp+298h+var_1E0]
0x18000a1f3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18000a1f8  nop
0x18000a1f9  mov     r8, rdi
0x18000a1fc  mov     rdx, rax
0x18000a1ff  lea     rcx, [rsp+298h+var_200]
0x18000a207  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18000a20c  nop
0x18000a20d  lea     r8, aPromptBeforeEx; "prompt-before-exit"
0x18000a214  mov     rdx, rax
0x18000a217  lea     rcx, [rsp+298h+var_220]
0x18000a21c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18000a221  nop
0x18000a222  mov     r8, [rax+10h]
0x18000a226  cmp     qword ptr [rax+18h], 7
0x18000a22b  jbe     short loc_18000A230
0x18000a22d  mov     rax, [rax]
0x18000a230  mov     rdx, rax
0x18000a233  lea     rcx, [rsp+298h+lpCommandLine]; Src
0x18000a23b  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000a240  nop
0x18000a241  lea     rcx, [rsp+298h+var_220]
0x18000a246  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a24b  nop
0x18000a24c  lea     rcx, [rsp+298h+var_200]
0x18000a254  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a259  nop
0x18000a25a  lea     rcx, [rsp+298h+var_1E0]
0x18000a262  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a267  nop
0x18000a268  lea     rcx, [rsp+298h+var_1C0]
0x18000a270  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a275  nop
0x18000a276  lea     rcx, [rsp+298h+var_1A0]
0x18000a27e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a283  nop
0x18000a284  lea     rcx, [rsp+298h+var_180]
0x18000a28c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a291  nop
0x18000a292  lea     rcx, [rsp+298h+var_160]
0x18000a29a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a29f  nop
0x18000a2a0  lea     rcx, [rsp+298h+var_240]
0x18000a2a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a2aa  mov     [rsp+298h+lpAttributeList], 0
0x18000a2b3  lea     rcx, [rsp+298h+lpAttributeList]
0x18000a2b8  call    ?CreateProcThreadAttributeList@util@wsl@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6AXPEAU1@@Z$1?DeleteProcThreadAttributeList@util@wsl@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; wsl::util::CreateProcThreadAttributeList(ulong)
0x18000a2bd  nop
0x18000a2be  mov     [rsp+298h+lpReturnSize], 0; lpReturnSize
0x18000a2c7  mov     [rsp+298h+lpPreviousValue], 0; lpPreviousValue
0x18000a2d0  mov     [rsp+298h+cbSize], 8; cbSize
0x18000a2d9  lea     r9, [rsp+298h+hObject]; lpValue
0x18000a2e1  xor     edx, edx; dwFlags
0x18000a2e3  mov     r8d, 20002h; Attribute
0x18000a2e9  mov     rcx, [rsp+298h+lpAttributeList]; lpAttributeList
0x18000a2ee  call    cs:__imp_UpdateProcThreadAttribute
0x18000a2f4  mov     rcx, [rsp+298h]; this
0x18000a2fc  test    eax, eax
0x18000a2fe  jnz     short loc_18000A311
0x18000a300  lea     r8, aOnecoreVmWslLx_0; "onecore\\vm\\wsl\\lxss\\wslutil\\wsluti"...
0x18000a307  mov     edx, 131h; void *
0x18000a30c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000a311  mov     edi, 70h ; 'p'
0x18000a316  mov     r8d, edi; Size
0x18000a319  xor     edx, edx; Val
0x18000a31b  lea     rcx, [rsp+298h+StartupInfo]; void *
0x18000a323  call    memset_0
0x18000a328  mov     [rsp+298h+StartupInfo.cb], edi
0x18000a32f  mov     [rsp+298h+StartupInfo.dwFlags], 1
0x18000a33a  lea     eax, [rdi-6Bh]
0x18000a33d  mov     [rsp+298h+StartupInfo.wShowWindow], ax
0x18000a345  mov     rax, [rsp+298h+lpAttributeList]
0x18000a34a  mov     [rsp+298h+var_60], rax
0x18000a352  xorps   xmm0, xmm0
0x18000a355  xor     eax, eax
0x18000a357  movups  xmmword ptr [rsp+298h+ProcessInformation.hProcess], xmm0
0x18000a35f  mov     qword ptr [rsp+298h+ProcessInformation.dwProcessId], rax
0x18000a367  lea     rdx, [rsp+298h+lpCommandLine]
0x18000a36f  cmp     qword ptr [rsp+298h+var_40+8], 7
0x18000a378  cmova   rdx, [rsp+298h+lpCommandLine]; lpCommandLine
0x18000a381  lea     rax, [rsp+298h+ProcessInformation]
0x18000a389  mov     [rsp+298h+lpProcessInformation], rax; lpProcessInformation
0x18000a38e  lea     rax, [rsp+298h+StartupInfo]
0x18000a396  mov     [rsp+298h+lpStartupInfo], rax; lpStartupInfo
0x18000a39b  mov     [rsp+298h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18000a3a4  mov     [rsp+298h+lpReturnSize], 0; lpEnvironment
0x18000a3ad  mov     dword ptr [rsp+298h+lpPreviousValue], 80010h; dwCreationFlags
0x18000a3b5  mov     dword ptr [rsp+298h+cbSize], 1; bInheritHandles
0x18000a3bd  xor     r9d, r9d; lpThreadAttributes
0x18000a3c0  xor     r8d, r8d; lpProcessAttributes
0x18000a3c3  xor     ecx, ecx; lpApplicationName
0x18000a3c5  call    cs:__imp_CreateProcessW
0x18000a3cb  mov     rcx, [rsp+298h]; this
0x18000a3d3  test    eax, eax
0x18000a3d5  jnz     short loc_18000A3E9
0x18000a3d7  lea     r8, aOnecoreVmWslLx_0; "onecore\\vm\\wsl\\lxss\\wslutil\\wsluti"...
0x18000a3de  mov     edx, 142h; void *
0x18000a3e3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000a3e9  lea     rcx, [rsp+298h+ProcessInformation]; this
0x18000a3f1  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x18000a3f6  nop
0x18000a3f7  lea     rcx, [rsp+298h+lpAttributeList]
0x18000a3fc  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6AXPEAU1@@Z$1?DeleteProcThreadAttributeList@util@wsl@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18000a401  nop
0x18000a402  lea     rcx, [rsp+298h+lpCommandLine]
0x18000a40a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a40f  nop
0x18000a410  lea     rcx, [rsp+298h+hObject]
0x18000a418  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a41d  xor     eax, eax
0x18000a41f  jmp     short loc_18000A428
0x18000a421  mov     eax, dword ptr [rsp+298h+hObject]
0x18000a428  mov     rcx, [rsp+298h+var_18]
0x18000a430  xor     rcx, rsp; StackCookie
0x18000a433  call    __security_check_cookie
0x18000a438  add     rsp, 290h
0x18000a43f  pop     rdi
0x18000a440  retn
```
