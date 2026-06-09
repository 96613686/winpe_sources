# tip2::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>,wil::err_returncode_policy> &)

- ea: `0x18000f9c0`
- end: `0x18000fa5b`
- name: `??0?$test_watcher@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000eb50`
- `0x180010f28`

## callees

- `0x180006e80`
- `0x18000f9c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fa2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fa2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v2; // rsi
  __int64 v4; // rbx
  _QWORD *Local; // rax
  __int64 v6; // rax

  v2 = a2;
  *(_QWORD *)a1 = &tip2::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::`vftable';
  v4 = a1 + 8;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = a1;
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 48) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(a2) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        a1,
                        a2);
    *(_QWORD *)v4 = Local;
    if ( Local )
    {
      *(_QWORD *)(v4 + 16) = *Local;
      *Local = v4;
      *(_DWORD *)(v4 + 24) = GetCurrentThreadId();
    }
  }
  v6 = *v2;
  *(_QWORD *)(a1 + 56) = *v2;
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 280));
  return a1;
}

```

## disassembly

```asm
0x18000f9c0  mov     [rsp+arg_0], rbx
0x18000f9c5  mov     [rsp+arg_8], rsi
0x18000f9ca  push    rdi
0x18000f9cb  sub     rsp, 20h
0x18000f9cf  mov     rsi, rdx
0x18000f9d2  mov     rdi, rcx
0x18000f9d5  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::`vftable'
0x18000f9dc  mov     [rcx], rax
0x18000f9df  lea     rbx, [rcx+8]
0x18000f9e3  mov     qword ptr [rbx], 0
0x18000f9ea  mov     [rbx+8], rcx
0x18000f9ee  mov     qword ptr [rbx+10h], 0
0x18000f9f6  mov     dword ptr [rbx+18h], 0
0x18000f9fd  mov     qword ptr [rbx+20h], 0
0x18000fa05  mov     byte ptr [rbx+28h], 0
0x18000fa09  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000fa11  jz      short loc_18000FA35
0x18000fa13  mov     dl, 1
0x18000fa15  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000fa1a  mov     [rbx], rax
0x18000fa1d  test    rax, rax
0x18000fa20  jz      short loc_18000FA35
0x18000fa22  mov     rcx, [rax]
0x18000fa25  mov     [rbx+10h], rcx
0x18000fa29  mov     [rax], rbx
0x18000fa2c  call    cs:__imp_GetCurrentThreadId
0x18000fa32  mov     [rbx+18h], eax
0x18000fa35  mov     rax, [rsi]
0x18000fa38  mov     [rdi+38h], rax
0x18000fa3c  test    rax, rax
0x18000fa3f  jz      short loc_18000FA48
0x18000fa41  lock inc dword ptr [rax+118h]
0x18000fa48  mov     rax, rdi
0x18000fa4b  mov     rbx, [rsp+28h+arg_0]
0x18000fa50  mov     rsi, [rsp+28h+arg_8]
0x18000fa55  add     rsp, 20h
0x18000fa59  pop     rdi
0x18000fa5a  retn
```
