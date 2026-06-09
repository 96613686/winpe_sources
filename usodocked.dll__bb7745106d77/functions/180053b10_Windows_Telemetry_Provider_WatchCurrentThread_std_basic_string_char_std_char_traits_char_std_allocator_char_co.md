# Windows::Telemetry::Provider::WatchCurrentThread(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180053b10`
- end: `0x180053c0f`
- name: `?WatchCurrentThread@Provider@Telemetry@Windows@@UEAA?AV?$unique_ptr@VContinuation@Telemetry@SystemInterface@@U?$default_delete@VContinuation@Telemetry@SystemInterface@@@std@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007dfc`
- `0x180016180`
- `0x180041470`
- `0x180041c1c`
- `0x18004fab8`
- `0x180053b10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053bf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053bf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053be3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053be3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053ba0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053ba0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall Windows::Telemetry::Provider::WatchCurrentThread(__int64 a1, __int64 *a2, _QWORD *a3)
{
  _QWORD *v3; // rbx
  __int64 v5; // rcx
  __int64 *Local; // rax
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  int v10; // [rsp+28h] [rbp-58h] BYREF
  _QWORD *v11; // [rsp+30h] [rbp-50h]
  LPVOID lpMem; // [rsp+38h] [rbp-48h]
  char v13; // [rsp+40h] [rbp-40h]
  _QWORD v14[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v15; // [rsp+58h] [rbp-28h]
  DWORD CurrentThreadId; // [rsp+60h] [rbp-20h]
  int *v17; // [rsp+68h] [rbp-18h]
  char v18; // [rsp+70h] [rbp-10h]
  void *v19; // [rsp+A0h] [rbp+20h]

  v3 = a3;
  if ( a3[3] > 0xFu )
    v3 = (_QWORD *)*a3;
  v13 = 0;
  v10 = 0;
  v11 = v3;
  lpMem = 0;
  v14[0] = 0;
  v14[1] = Windows::Telemetry::Base::Instance();
  v15 = 0;
  CurrentThreadId = 0;
  v17 = &v10;
  v18 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         v5,
                         1);
    v14[0] = Local;
    if ( Local )
    {
      v15 = *Local;
      *Local = (__int64)v14;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  else
  {
    v14[0] = 0;
  }
  v19 = operator new(0x58u);
  *a2 = Windows::Telemetry::Continuation::Continuation((__int64)v19, (__int64)&v10);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v14);
  if ( v13 )
  {
    v7 = lpMem;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  return a2;
}

```

## disassembly

```asm
0x180053b10  mov     [rsp-8+arg_0], rbx
0x180053b15  mov     [rsp-8+arg_8], rdi
0x180053b1a  push    rbp
0x180053b1b  mov     rbp, rsp
0x180053b1e  sub     rsp, 80h
0x180053b25  mov     rbx, r8
0x180053b28  mov     rdi, rdx
0x180053b2b  cmp     qword ptr [r8+18h], 0Fh
0x180053b30  jbe     short loc_180053B35
0x180053b32  mov     rbx, [r8]
0x180053b35  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x180053b3a  mov     [rbp+var_40], 0
0x180053b3e  mov     [rbp+var_58], 0
0x180053b45  mov     [rbp+var_50], rbx
0x180053b49  mov     [rbp+lpMem], 0
0x180053b51  mov     [rbp+var_38], 0
0x180053b59  mov     [rbp+var_30], rax
0x180053b5d  mov     [rbp+var_28], 0
0x180053b65  mov     [rbp+var_20], 0
0x180053b6c  lea     rax, [rbp+var_58]
0x180053b70  mov     [rbp+var_18], rax
0x180053b74  mov     [rbp+var_10], 0
0x180053b78  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180053b80  jz      short loc_180053BAB
0x180053b82  mov     dl, 1
0x180053b84  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180053b89  mov     [rbp+var_38], rax
0x180053b8d  test    rax, rax
0x180053b90  jz      short loc_180053BB3
0x180053b92  mov     rcx, [rax]
0x180053b95  mov     [rbp+var_28], rcx
0x180053b99  lea     rcx, [rbp+var_38]
0x180053b9d  mov     [rax], rcx
0x180053ba0  call    cs:__imp_GetCurrentThreadId
0x180053ba6  mov     [rbp+var_20], eax
0x180053ba9  jmp     short loc_180053BB3
0x180053bab  mov     [rbp+var_38], 0
0x180053bb3  mov     ecx, 58h ; 'X'; Size
0x180053bb8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053bbd  mov     [rbp+arg_10], rax
0x180053bc1  lea     rdx, [rbp+var_58]
0x180053bc5  mov     rcx, rax
0x180053bc8  call    ??0Continuation@Telemetry@Windows@@QEAA@$$QEAVActivityThreadWatcher@wil@@@Z; Windows::Telemetry::Continuation::Continuation(wil::ActivityThreadWatcher &&)
0x180053bcd  mov     [rdi], rax
0x180053bd0  lea     rcx, [rbp+var_38]; this
0x180053bd4  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180053bd9  cmp     [rbp+var_40], 0
0x180053bdd  jz      short loc_180053BF7
0x180053bdf  mov     rbx, [rbp+lpMem]
0x180053be3  call    cs:__imp_GetProcessHeap
0x180053be9  mov     r8, rbx; lpMem
0x180053bec  xor     edx, edx; dwFlags
0x180053bee  mov     rcx, rax; hHeap
0x180053bf1  call    cs:__imp_HeapFree
0x180053bf7  mov     rax, rdi
0x180053bfa  lea     r11, [rsp+80h+var_s0]
0x180053c02  mov     rbx, [r11+10h]
0x180053c06  mov     rdi, [r11+18h]
0x180053c0a  mov     rsp, r11
0x180053c0d  pop     rbp
0x180053c0e  retn
```
