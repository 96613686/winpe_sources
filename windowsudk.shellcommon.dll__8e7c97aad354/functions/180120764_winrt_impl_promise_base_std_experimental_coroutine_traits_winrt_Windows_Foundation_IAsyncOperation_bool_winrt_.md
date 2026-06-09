# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::WindowsUdk::Storage::DestinationList::implementation::AutomaticDestinationListStorage *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::unhandled_exception(void)

- ea: `0x180120764`
- end: `0x1801207fe`
- name: `?unhandled_exception@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUAutomaticDestinationListStorage@implementation@DestinationList@Storage@WindowsUdk@4@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXXZ`
- size: `154`
- prototype: ``
- caller_count: `100`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18048256b`
- `0x18048299e`
- `0x180482afc`
- `0x1804833ed`
- `0x180483955`
- `0x1804847a3`
- `0x1804859b7`
- `0x180485b79`
- `0x180486143`
- `0x180486602`
- `0x1804869a3`
- `0x180486df6`
- `0x180486fea`
- `0x180487113`
- `0x180487297`
- `0x1804878f4`
- `0x1804879d3`
- `0x180487d5c`
- `0x1804881cb`
- `0x18048861c`
- `0x1804889ae`
- `0x180488fc9`
- `0x1804892c3`
- `0x180489570`
- `0x180489916`
- `0x180489a23`
- `0x180489e59`
- `0x18048a592`
- `0x18048a686`
- `0x18048ab02`
- `0x18048b2cf`
- `0x18048b7aa`
- `0x18048b8fa`
- `0x18048b9b7`
- `0x18048c10b`
- `0x18048c7b5`
- `0x18048ce74`
- `0x18048d17a`
- `0x18048d3a3`
- `0x18048d81d`
- `0x18048dbfb`
- `0x18048de4a`
- `0x18048df3b`
- `0x18048ef04`
- `0x18048f094`
- `0x18048f396`
- `0x18048fbdc`
- `0x180491626`
- `0x180492f98`
- `0x1804933a5`

## callees

- `0x180120764`
- `0x18015e123`
- `0x18015e13b`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1801207e6`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1801207e6`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18012079e`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18012079e`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1801207d1`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1801207d1`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801207ad`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801207ad`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801207b8`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801207b8`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180120793`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180120793`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::WindowsUdk::Storage::DestinationList::implementation::AutomaticDestinationListStorage *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::unhandled_exception(
        RTL_SRWLOCK *a1)
{
  __int128 v2; // [rsp+20h] [rbp-18h] BYREF
  RTL_SRWLOCK *SRWLock; // [rsp+48h] [rbp+10h]

  SRWLock = a1 + 9;
  WINRT_IMPL_AcquireSRWLockExclusive(a1 + 9);
  v2 = 0;
  __ExceptionPtrCreate(&v2);
  __ExceptionPtrCurrentException(&v2);
  __ExceptionPtrAssign(&a1[7], &v2);
  __ExceptionPtrDestroy(&v2);
  v2 = 0;
  __ExceptionPtrCopy(&v2, &a1[7]);
  try
  {
    __ExceptionPtrRethrow(&v2);
  }
  catch ( winrt::hresult_canceled )
  {
    std::_Atomic_storage<enum winrt::Windows::Foundation::AsyncStatus,4>::store(&a1[12], 2);
  }
  catch ( ... )
  {
    std::_Atomic_storage<enum winrt::Windows::Foundation::AsyncStatus,4>::store(&a1[12], 3);
  }
  ReleaseSRWLockExclusive_0(SRWLock);
}

```

## disassembly

```asm
0x180120764  mov     [rsp+arg_0], rcx
0x180120769  push    rbx
0x18012076a  sub     rsp, 30h
0x18012076e  mov     rbx, rcx
0x180120771  add     rcx, 48h ; 'H'; SRWLock
0x180120775  mov     [rsp+38h+SRWLock], rcx
0x18012077a  mov     [rsp+38h+arg_10], rcx
0x18012077f  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180120784  nop
0x180120785  xorps   xmm0, xmm0
0x180120788  movdqu  [rsp+38h+var_18], xmm0
0x18012078e  lea     rcx, [rsp+38h+var_18]
0x180120793  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180120799  lea     rcx, [rsp+38h+var_18]
0x18012079e  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1801207a4  lea     rdx, [rsp+38h+var_18]
0x1801207a9  lea     rcx, [rbx+38h]
0x1801207ad  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1801207b3  lea     rcx, [rsp+38h+var_18]
0x1801207b8  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1801207be  nop
0x1801207bf  xorps   xmm0, xmm0
0x1801207c2  movdqu  [rsp+38h+var_18], xmm0
0x1801207c8  lea     rdx, [rbx+38h]
0x1801207cc  lea     rcx, [rsp+38h+var_18]
0x1801207d1  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1801207d7  lea     rax, [rsp+38h+var_18]
0x1801207dc  mov     [rsp+38h+arg_18], rax
0x1801207e1  lea     rcx, [rsp+38h+var_18]
0x1801207e6  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1801207ec  nop
0x1801207ed  jmp     short $+2
0x1801207ef  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x1801207f4  add     rsp, 30h
0x1801207f8  pop     rbx
0x1801207f9  jmp     ReleaseSRWLockExclusive_0
```
