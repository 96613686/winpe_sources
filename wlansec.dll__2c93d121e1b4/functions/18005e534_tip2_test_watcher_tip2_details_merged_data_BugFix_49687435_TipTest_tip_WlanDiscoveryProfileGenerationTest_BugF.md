# tip2::test_watcher<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>>::test_watcher<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>>(wil::com_ptr_t<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>,wil::err_returncode_policy> &)

- ea: `0x18005e534`
- end: `0x18005e5d6`
- name: `??0?$test_watcher@V?$merged_data@U_tip_WlanDiscoveryProfileGenerationTest@TipTest@BugFix_49687435@@U123@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_WlanDiscoveryProfileGenerationTest@TipTest@BugFix_49687435@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005e368`

## callees

- `0x1800369b0`
- `0x18005e534`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e5a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e5a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::test_watcher<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>>::test_watcher<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v4; // rbx
  _QWORD *Local; // rax
  __int64 v6; // rax

  *(_QWORD *)a1 = &tip2::test_watcher<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>>::`vftable';
  v4 = a1 + 8;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = a1;
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 48) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(a1, 1);
    *(_QWORD *)v4 = Local;
    if ( Local )
    {
      *(_QWORD *)(v4 + 16) = *Local;
      *Local = v4;
      *(_DWORD *)(v4 + 24) = GetCurrentThreadId();
    }
  }
  v6 = *a2;
  *(_QWORD *)(a1 + 56) = *a2;
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 304));
  return a1;
}

```

## disassembly

```asm
0x18005e534  mov     [rsp+arg_0], rbx
0x18005e539  mov     [rsp+arg_8], rsi
0x18005e53e  push    rdi
0x18005e53f  sub     rsp, 20h
0x18005e543  mov     rsi, rdx
0x18005e546  mov     rdi, rcx
0x18005e549  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_WlanDiscoveryProfileGenerationTest@TipTest@BugFix_49687435@@U123@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>>::`vftable'
0x18005e550  mov     [rcx], rax
0x18005e553  lea     rbx, [rcx+8]
0x18005e557  mov     qword ptr [rbx], 0
0x18005e55e  mov     [rbx+8], rcx
0x18005e562  mov     qword ptr [rbx+10h], 0
0x18005e56a  mov     dword ptr [rbx+18h], 0
0x18005e571  mov     qword ptr [rbx+20h], 0
0x18005e579  mov     byte ptr [rbx+28h], 0
0x18005e57d  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18005e585  jz      short loc_18005E5AF
0x18005e587  mov     dl, 1
0x18005e589  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18005e58e  mov     [rbx], rax
0x18005e591  test    rax, rax
0x18005e594  jz      short loc_18005E5AF
0x18005e596  mov     rcx, [rax]
0x18005e599  mov     [rbx+10h], rcx
0x18005e59d  mov     [rax], rbx
0x18005e5a0  call    cs:__imp_GetCurrentThreadId
0x18005e5a7  nop     dword ptr [rax+rax+00h]
0x18005e5ac  mov     [rbx+18h], eax
0x18005e5af  mov     rax, [rsi]
0x18005e5b2  mov     [rdi+38h], rax
0x18005e5b6  test    rax, rax
0x18005e5b9  jz      short loc_18005E5C2
0x18005e5bb  lock inc dword ptr [rax+130h]
0x18005e5c2  mov     rax, rdi
0x18005e5c5  mov     rbx, [rsp+28h+arg_0]
0x18005e5ca  mov     rsi, [rsp+28h+arg_8]
0x18005e5cf  add     rsp, 20h
0x18005e5d3  pop     rdi
0x18005e5d4  retn
```
