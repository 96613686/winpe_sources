# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000e9f0`
- end: `0x18000eb29`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ff5c`

## callees

- `0x18000e9f0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000eafd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000eafd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000eae8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000eae8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ea79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ea79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ea05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ea05`

## string_xrefs

- `0x18000eae1`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v3; // rsi
  unsigned __int64 CurrentThreadId; // rbx
  unsigned __int64 v5; // r14
  __int64 i; // rax
  HANDLE ProcessHeap; // rbp
  _DWORD *v9; // rdi
  FARPROC ProcAddress; // rax
  signed __int64 v11; // rax
  HMODULE ModuleHandleW; // rax

  v3 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  v5 = 8 * ((CurrentThreadId >> 2) % 0xA);
  for ( i = *(_QWORD *)(v5 + v3); i; i = *(_QWORD *)(i + 8) )
  {
    if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      return (char *)(i + 16);
  }
  if ( !a2 )
    return 0;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 0, 0x18u);
  ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress) )
  {
    ((void (__fastcall *)(HANDLE, _DWORD *))ProcAddress)(ProcessHeap, v9);
  }
  if ( !v9 )
    return 0;
  *v9 = CurrentThreadId;
  v9[1] = 0;
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  do
  {
    v11 = *(_QWORD *)(v5 + v3);
    *((_QWORD *)v9 + 1) = v11;
  }
  while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + v3), (signed __int64)v9, v11) );
  return (char *)(v9 + 4);
}

```

## disassembly

```asm
0x18000e9f0  push    rbx
0x18000e9f2  push    rbp
0x18000e9f3  push    rsi
0x18000e9f4  push    rdi
0x18000e9f5  push    r14
0x18000e9f7  sub     rsp, 20h
0x18000e9fb  movzx   edi, dl
0x18000e9fe  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ea05  call    cs:__imp_GetCurrentThreadId
0x18000ea0b  mov     ebx, eax
0x18000ea0d  mov     r8d, eax
0x18000ea10  shr     r8, 2
0x18000ea14  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ea1e  mul     r8
0x18000ea21  shr     rdx, 3
0x18000ea25  lea     rcx, [rdx+rdx*4]
0x18000ea29  add     rcx, rcx
0x18000ea2c  sub     r8, rcx
0x18000ea2f  lea     r14, ds:0[r8*8]
0x18000ea37  mov     rax, [r14+rsi]
0x18000ea3b  test    rax, rax
0x18000ea3e  jnz     short loc_18000EA52
0x18000ea40  test    dil, dil
0x18000ea43  jnz     short loc_18000EA65
0x18000ea45  xor     eax, eax
0x18000ea47  add     rsp, 20h
0x18000ea4b  pop     r14
0x18000ea4d  pop     rdi
0x18000ea4e  pop     rsi
0x18000ea4f  pop     rbp
0x18000ea50  pop     rbx
0x18000ea51  retn
0x18000ea52  cmp     [rax], ebx
0x18000ea54  jnz     short loc_18000EACF
0x18000ea56  add     rax, 10h
0x18000ea5a  add     rsp, 20h
0x18000ea5e  pop     r14
0x18000ea60  pop     rdi
0x18000ea61  pop     rsi
0x18000ea62  pop     rbp
0x18000ea63  pop     rbx
0x18000ea64  retn
0x18000ea65  call    cs:__imp_GetProcessHeap
0x18000ea6b  mov     rbp, rax
0x18000ea6e  xor     edx, edx; dwFlags
0x18000ea70  mov     r8d, 18h; dwBytes
0x18000ea76  mov     rcx, rax; hHeap
0x18000ea79  call    cs:__imp_HeapAlloc
0x18000ea7f  mov     rdi, rax
0x18000ea82  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ea89  test    rax, rax
0x18000ea8c  jz      short loc_18000EAD8
0x18000ea8e  mov     rdx, rdi
0x18000ea91  mov     rcx, rbp
0x18000ea94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea99  nop
0x18000ea9a  test    rdi, rdi
0x18000ea9d  jz      short loc_18000EA45
0x18000ea9f  mov     [rdi], ebx
0x18000eaa1  xor     eax, eax
0x18000eaa3  mov     [rdi+4], eax
0x18000eaa6  mov     [rdi+8], rax
0x18000eaaa  mov     [rdi+10h], rax
0x18000eaae  xchg    ax, ax
0x18000eab0  mov     rax, [r14+rsi]
0x18000eab4  mov     [rdi+8], rax
0x18000eab8  lock cmpxchg [r14+rsi], rdi
0x18000eabe  jnz     short loc_18000EAB0
0x18000eac0  lea     rax, [rdi+10h]
0x18000eac4  add     rsp, 20h
0x18000eac8  pop     r14
0x18000eaca  pop     rdi
0x18000eacb  pop     rsi
0x18000eacc  pop     rbp
0x18000eacd  pop     rbx
0x18000eace  retn
0x18000eacf  mov     rax, [rax+8]
0x18000ead3  jmp     loc_18000EA3B
0x18000ead8  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 0; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000eadf  jnz     short loc_18000EA9A
0x18000eae1  lea     rcx, ModuleName; "ntdll.dll"
0x18000eae8  call    cs:__imp_GetModuleHandleW
0x18000eaee  test    rax, rax
0x18000eaf1  jz      short loc_18000EB0C
0x18000eaf3  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000eafa  mov     rcx, rax; hModule
0x18000eafd  call    cs:__imp_GetProcAddress
0x18000eb03  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000eb0a  jmp     short loc_18000EB13
0x18000eb0c  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000eb13  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000eb1a  test    rax, rax
0x18000eb1d  jz      loc_18000EA9A
0x18000eb23  jmp     loc_18000EA8E
```
