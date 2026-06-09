# GetLaunchFlagsFromLaunchTypeAndRuntimeBehavior

- ea: `0x1800b6270`
- end: `0x1800b6473`
- name: `GetLaunchFlagsFromLaunchTypeAndRuntimeBehavior`
- size: `515`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b79f0`

## callees

- `0x18000f194`
- `0x18004a820`
- `0x1800a0a54`
- `0x1800b0e48`
- `0x1800b1104`
- `0x1800b1bec`
- `0x1800b1d08`
- `0x1800b1d40`
- `0x1800b247c`
- `0x1800b6270`
- `0x1800b74d0`
- `0x1800bd54c`
- `0x1800bd798`
- `0x1800bdd40`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b6357`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b639d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b6357`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b639d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b6324`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b63e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b6324`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b63e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800b633a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800b633a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b6297`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b6297`

## string_xrefs

- `0x1800b645b`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b63b4`: `CentennialLaunchUriForResultsTest::reason::uwp_target`
- `0x1800b640d`: `CentennialLaunchUriForResultsTest::reason::unknown_target`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetLaunchFlagsFromLaunchTypeAndRuntimeBehavior(int a1, __int64 a2)
{
  LPVOID v4; // rax
  wil::details::in1diag3 *v5; // rcx
  unsigned int v6; // esi
  __int64 v7; // rbx
  HRESULT v8; // eax
  PCWSTR StringRawBuffer; // r14
  __int64 v10; // rdi
  PCWSTR v11; // rax
  const char *v12; // rcx
  const char *v13; // r8
  char v14; // al
  const char *v15; // rcx
  const char *v16; // r8
  char v17; // al
  _BYTE v19[56]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v20; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  HSTRING newString; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v23; // [rsp+A8h] [rbp+38h] BYREF

  newString = 0;
  v4 = CoTaskMemAlloc(0x178u);
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v5);
  v23 = tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>(
          v4,
          0);
  wil::com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy>::operator=(
    &newString,
    &v23);
  wil::com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy>(&v23);
  tip2::tip_test<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::ensure_data(&newString);
  tip2::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>((struct wil::details::IFailureCallback *)v19);
  wil::com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy>(&newString);
  v6 = 0;
  if ( a1 == 3 )
  {
    if ( a2 )
    {
      v7 = a2 - 8;
      if ( a2 != 8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(a2 - 8);
      newString = 0;
      WindowsDeleteString(0);
      newString = 0;
      v8 = WindowsDuplicateString(*(HSTRING *)(a2 + 72), &newString);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFD,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v8,
          a2 - 8);
      v6 = 1;
      StringRawBuffer = WindowsGetStringRawBuffer(newString, 0);
      v10 = v20;
      v23 = v20;
      if ( v20 )
        _InterlockedIncrement((volatile signed __int32 *)(v20 + 368));
      tip2::details::shared_data<1,0,0>::begin_update(v10 + 8);
      std::wstring::assign(v10 + 304, StringRawBuffer);
      tip2::test_data_control<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::~test_data_control<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>(&v23);
      v11 = WindowsGetStringRawBuffer(newString, 0);
      if ( (unsigned __int8)IsRuntimeBehaviorUniversal(v11) )
      {
        v6 = 3;
        v12 = "CentennialLaunchUriForResultsTest::reason::uwp_target";
        v13 = "CentennialLaunchUriForResultsTest::reason::uwp_target";
        v14 = 67;
        do
        {
          ++v12;
          if ( v14 == 58 )
            v13 = v12;
          v14 = *v12;
        }
        while ( *v12 );
        tip2::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::complete_and_ignore(
          v19,
          1,
          v13);
      }
      WindowsDeleteString(newString);
      newString = 0;
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    else
    {
      v6 = 3;
      v15 = "CentennialLaunchUriForResultsTest::reason::unknown_target";
      v16 = "CentennialLaunchUriForResultsTest::reason::unknown_target";
      v17 = 67;
      do
      {
        ++v15;
        if ( v17 == 58 )
          v16 = v15;
        v17 = *v15;
      }
      while ( *v15 );
      tip2::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::complete_and_ignore(
        v19,
        2,
        v16);
    }
  }
  tip2::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::~test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>(v19);
  return v6;
}

```

## disassembly

```asm
0x1800b6270  mov     [rsp-18h+arg_0], rbx
0x1800b6275  mov     [rsp-18h+arg_8], rsi
0x1800b627a  push    rbp
0x1800b627b  push    rdi
0x1800b627c  push    r14
0x1800b627e  mov     rbp, rsp
0x1800b6281  sub     rsp, 70h
0x1800b6285  mov     rdi, rdx
0x1800b6288  mov     ebx, ecx
0x1800b628a  mov     [rbp+newString], 0
0x1800b6292  mov     ecx, 178h; cb
0x1800b6297  call    cs:__imp_CoTaskMemAlloc
0x1800b629d  test    rax, rax
0x1800b62a0  jz      loc_1800B646D
0x1800b62a6  xor     edx, edx
0x1800b62a8  mov     rcx, rax
0x1800b62ab  call    ??0?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>(_GUID *)
0x1800b62b0  mov     [rbp+arg_18], rax
0x1800b62b4  lea     rdx, [rbp+arg_18]
0x1800b62b8  lea     rcx, [rbp+newString]
0x1800b62bc  call    ??4?$com_ptr_t@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy> &&)
0x1800b62c1  lea     rcx, [rbp+arg_18]
0x1800b62c5  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy>(void)
0x1800b62ca  lea     rcx, [rbp+newString]
0x1800b62ce  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::ensure_data(void)
0x1800b62d3  mov     rdx, rax
0x1800b62d6  lea     rcx, [rbp+var_40]; struct wil::details::IFailureCallback *
0x1800b62da  call    ??0?$test_watcher@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy> &)
0x1800b62df  lea     rcx, [rbp+newString]
0x1800b62e3  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy>(void)
0x1800b62e8  nop
0x1800b62e9  xor     esi, esi
0x1800b62eb  cmp     ebx, 3
0x1800b62ee  jnz     loc_1800B6438
0x1800b62f4  test    rdi, rdi
0x1800b62f7  jz      loc_1800B6408
0x1800b62fd  lea     rbx, [rdi-8]
0x1800b6301  mov     [rbp+var_50], rbx
0x1800b6305  test    rbx, rbx
0x1800b6308  jz      short loc_1800B631A
0x1800b630a  mov     rax, [rbx]
0x1800b630d  mov     rcx, rbx
0x1800b6310  mov     rax, [rax+8]
0x1800b6314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6319  nop
0x1800b631a  mov     [rbp+newString], 0
0x1800b6322  xor     ecx, ecx; string
0x1800b6324  call    cs:__imp_WindowsDeleteString
0x1800b632a  mov     [rbp+newString], 0
0x1800b6332  lea     rdx, [rbp+newString]; newString
0x1800b6336  mov     rcx, [rdi+48h]; string
0x1800b633a  call    cs:__imp_WindowsDuplicateString
0x1800b6340  mov     rcx, [rbp+18h]; this
0x1800b6344  test    eax, eax
0x1800b6346  js      loc_1800B6458
0x1800b634c  mov     esi, 1
0x1800b6351  xor     edx, edx; length
0x1800b6353  mov     rcx, [rbp+newString]; string
0x1800b6357  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b635d  mov     r14, rax
0x1800b6360  mov     rdi, [rbp+var_8]
0x1800b6364  mov     [rbp+arg_18], rdi
0x1800b6368  test    rdi, rdi
0x1800b636b  jz      short loc_1800B6374
0x1800b636d  lock inc dword ptr [rdi+170h]
0x1800b6374  lea     rcx, [rdi+8]
0x1800b6378  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x1800b637d  nop
0x1800b637e  lea     rcx, [rdi+130h]
0x1800b6385  mov     rdx, r14
0x1800b6388  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800b638d  nop
0x1800b638e  lea     rcx, [rbp+arg_18]
0x1800b6392  call    ??1?$test_data_control@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::~test_data_control<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>(void)
0x1800b6397  xor     edx, edx; length
0x1800b6399  mov     rcx, [rbp+newString]; string
0x1800b639d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b63a3  mov     rcx, rax
0x1800b63a6  call    IsRuntimeBehaviorUniversal
0x1800b63ab  test    al, al
0x1800b63ad  jz      short loc_1800B63DF
0x1800b63af  mov     esi, 3
0x1800b63b4  lea     rcx, aCentenniallaun; "CentennialLaunchUriForResultsTest::reas"...
0x1800b63bb  mov     r8, rcx
0x1800b63be  mov     al, 43h ; 'C'
0x1800b63c0  inc     rcx
0x1800b63c3  cmp     al, 3Ah ; ':'
0x1800b63c5  jnz     short loc_1800B63CA
0x1800b63c7  mov     r8, rcx
0x1800b63ca  mov     al, [rcx]
0x1800b63cc  test    al, al
0x1800b63ce  jnz     short loc_1800B63C0
0x1800b63d0  mov     edx, 1
0x1800b63d5  lea     rcx, [rbp+var_40]
0x1800b63d9  call    ?complete_and_ignore@?$test_watcher@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::complete_and_ignore(ushort,char const *)
0x1800b63de  nop
0x1800b63df  mov     rcx, [rbp+newString]; string
0x1800b63e3  call    cs:__imp_WindowsDeleteString
0x1800b63e9  mov     [rbp+newString], 0
0x1800b63f1  test    rbx, rbx
0x1800b63f4  jz      short loc_1800B6406
0x1800b63f6  mov     rax, [rbx]
0x1800b63f9  mov     rcx, rbx
0x1800b63fc  mov     rax, [rax+10h]
0x1800b6400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6405  nop
0x1800b6406  jmp     short loc_1800B6438
0x1800b6408  mov     esi, 3
0x1800b640d  lea     rcx, aCentenniallaun_0; "CentennialLaunchUriForResultsTest::reas"...
0x1800b6414  mov     r8, rcx
0x1800b6417  mov     al, 43h ; 'C'
0x1800b6419  inc     rcx
0x1800b641c  cmp     al, 3Ah ; ':'
0x1800b641e  jnz     short loc_1800B6423
0x1800b6420  mov     r8, rcx
0x1800b6423  mov     al, [rcx]
0x1800b6425  test    al, al
0x1800b6427  jnz     short loc_1800B6419
0x1800b6429  mov     edx, 2
0x1800b642e  lea     rcx, [rbp+var_40]
0x1800b6432  call    ?complete_and_ignore@?$test_watcher@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::complete_and_ignore(ushort,char const *)
0x1800b6437  nop
0x1800b6438  lea     rcx, [rbp+var_40]
0x1800b643c  call    ??1?$test_watcher@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::~test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>(void)
0x1800b6441  mov     eax, esi
0x1800b6443  lea     r11, [rsp+70h+var_s0]
0x1800b6448  mov     rbx, [r11+20h]
0x1800b644c  mov     rsi, [r11+28h]
0x1800b6450  mov     rsp, r11
0x1800b6453  pop     r14
0x1800b6455  pop     rdi
0x1800b6456  pop     rbp
0x1800b6457  retn
0x1800b6458  mov     r9d, eax; char *
0x1800b645b  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800b6462  mov     edx, 0FDh; void *
0x1800b6467  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b646d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
