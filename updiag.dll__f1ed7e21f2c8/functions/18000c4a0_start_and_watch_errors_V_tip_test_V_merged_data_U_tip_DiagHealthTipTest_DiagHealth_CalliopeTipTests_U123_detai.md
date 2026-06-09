# ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ

- ea: `0x18000c4a0`
- end: `0x18000c56f`
- name: `??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ`
- size: `207`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `9`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c9fc`
- `0x18000cb98`
- `0x18000cd28`
- `0x18000ceb8`
- `0x18000d048`
- `0x18000d1d8`
- `0x18000d368`
- `0x18000d4f8`
- `0x18000d6a0`

## callees

- `0x180005950`
- `0x18000bba4`
- `0x18000c4a0`
- `0x18000d988`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c55b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c55b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c517`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c517`

## pseudocode

```c
__int64 __fastcall tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>>(
        __int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  _QWORD *v4; // rbx
  _QWORD *Local; // rax
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  pv = 0;
  tip2::tip_test<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::start(
    &pv,
    &v9);
  *(_QWORD *)a1 = &tip2::test_watcher<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::`vftable';
  v4 = (_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = a1;
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v2) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        v3,
                        v2);
    *v4 = Local;
    if ( Local )
    {
      *(_QWORD *)(a1 + 24) = *Local;
      *Local = v4;
      *(_DWORD *)(a1 + 32) = GetCurrentThreadId();
    }
  }
  v6 = (volatile signed __int32 *)pv;
  *(_QWORD *)(a1 + 48) = pv;
  if ( v6 )
  {
    v7 = (__int64)(v6 + 72);
    _InterlockedIncrement(v6 + 72);
  }
  else
  {
    v7 = 288;
  }
  if ( v6 && _InterlockedExchangeAdd((volatile signed __int32 *)v7, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(v6);
    CoTaskMemFree((LPVOID)v6);
  }
  return a1;
}

```

## disassembly

```asm
0x18000c4a0  mov     rax, rsp
0x18000c4a3  mov     [rax+10h], rbx
0x18000c4a7  push    rdi
0x18000c4a8  sub     rsp, 30h
0x18000c4ac  mov     rdi, rcx
0x18000c4af  mov     qword ptr [rax+8], 0
0x18000c4b7  lea     rdx, [rax-18h]
0x18000c4bb  lea     rcx, [rax+8]
0x18000c4bf  call    ?start@?$tip_test@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::start(void)
0x18000c4c4  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::`vftable'
0x18000c4cb  mov     [rdi], rax
0x18000c4ce  lea     rbx, [rdi+8]
0x18000c4d2  mov     qword ptr [rbx], 0
0x18000c4d9  mov     [rbx+8], rdi
0x18000c4dd  mov     qword ptr [rbx+10h], 0
0x18000c4e5  mov     dword ptr [rbx+18h], 0
0x18000c4ec  mov     qword ptr [rbx+20h], 0
0x18000c4f4  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000c4fc  jz      short loc_18000C520
0x18000c4fe  mov     dl, 1
0x18000c500  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000c505  mov     [rbx], rax
0x18000c508  test    rax, rax
0x18000c50b  jz      short loc_18000C520
0x18000c50d  mov     rcx, [rax]
0x18000c510  mov     [rbx+10h], rcx
0x18000c514  mov     [rax], rbx
0x18000c517  call    cs:__imp_GetCurrentThreadId
0x18000c51d  mov     [rbx+18h], eax
0x18000c520  mov     rbx, [rsp+38h+pv]
0x18000c525  mov     [rdi+30h], rbx
0x18000c529  test    rbx, rbx
0x18000c52c  jz      short loc_18000C53A
0x18000c52e  lea     rcx, [rbx+120h]
0x18000c535  lock inc dword ptr [rcx]
0x18000c538  jmp     short loc_18000C53F
0x18000c53a  mov     ecx, 120h
0x18000c53f  test    rbx, rbx
0x18000c542  jz      short loc_18000C561
0x18000c544  or      eax, 0FFFFFFFFh
0x18000c547  lock xadd [rcx], eax
0x18000c54b  cmp     eax, 1
0x18000c54e  jnz     short loc_18000C561
0x18000c550  mov     rcx, rbx
0x18000c553  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000c558  mov     rcx, rbx; pv
0x18000c55b  call    cs:__imp_CoTaskMemFree
0x18000c561  mov     rax, rdi
0x18000c564  mov     rbx, [rsp+38h+arg_8]
0x18000c569  add     rsp, 30h
0x18000c56d  pop     rdi
0x18000c56e  retn
```
