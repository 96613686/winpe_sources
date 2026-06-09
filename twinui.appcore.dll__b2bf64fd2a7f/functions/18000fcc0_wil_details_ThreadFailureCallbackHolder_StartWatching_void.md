# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000fcc0`
- end: `0x18000fe4b`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `395`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `8`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006320`
- `0x18000f6d8`
- `0x18000fc9c`
- `0x18001986c`
- `0x180021544`
- `0x1800215f4`
- `0x180068054`
- `0x18006c738`

## callees

- `0x18000fcc0`
- `0x180016be8`
- `0x18002bc68`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fe08`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fe08`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fdf3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fdf3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fd38`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fd38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fd24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fd24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fce9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fce9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe3d`

## string_xrefs

- `0x18000fdec`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // rdi
  unsigned __int64 CurrentThreadId; // rsi
  unsigned __int64 v4; // r15
  __int64 i; // rcx
  HANDLE ProcessHeap; // rbp
  char *v7; // r14
  FARPROC ProcAddress; // rax
  _QWORD *v9; // rcx
  signed __int64 v10; // rax
  const struct wil::FailureInfo *v11; // rdx
  HMODULE ModuleHandleW; // rax
  _BYTE v13[216]; // [rsp+20h] [rbp-D8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v11);
  }
  v2 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = 8 * ((CurrentThreadId >> 2) % 0xA);
    for ( i = *(_QWORD *)(v4 + v2); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        v9 = (_QWORD *)(i + 16);
        goto LABEL_12;
      }
    }
    ProcessHeap = GetProcessHeap();
    v7 = (char *)HeapAlloc(ProcessHeap, 0, 0x18u);
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
      ((void (__fastcall *)(HANDLE, char *))ProcAddress)(ProcessHeap, v7);
    }
    if ( v7 )
    {
      *(_DWORD *)v7 = CurrentThreadId;
      *((_DWORD *)v7 + 1) = 0;
      *((_QWORD *)v7 + 1) = 0;
      v9 = v7 + 16;
      *((_QWORD *)v7 + 2) = 0;
      do
      {
        v10 = *(_QWORD *)(v4 + v2);
        *((_QWORD *)v7 + 1) = v10;
      }
      while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v4 + v2), (signed __int64)v7, v10) );
    }
    else
    {
      v9 = 0;
    }
LABEL_12:
    *(_QWORD *)this = v9;
    if ( v9 )
    {
      *((_QWORD *)this + 2) = *v9;
      *v9 = this;
      *((_DWORD *)this + 6) = GetCurrentThreadId();
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000fcc0  push    rbx
0x18000fcc2  push    rbp
0x18000fcc3  push    rsi
0x18000fcc4  push    rdi
0x18000fcc5  push    r14
0x18000fcc7  push    r15
0x18000fcc9  sub     rsp, 0C8h
0x18000fcd0  mov     rbx, rcx
0x18000fcd3  cmp     dword ptr [rcx+18h], 0
0x18000fcd7  jnz     loc_18000FDC2
0x18000fcdd  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000fce4  test    rdi, rdi
0x18000fce7  jz      short loc_18000FD68
0x18000fce9  call    cs:__imp_GetCurrentThreadId
0x18000fcef  mov     esi, eax
0x18000fcf1  mov     r8d, eax
0x18000fcf4  shr     r8, 2
0x18000fcf8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000fd02  mul     r8
0x18000fd05  shr     rdx, 3
0x18000fd09  lea     rcx, [rdx+rdx*4]
0x18000fd0d  add     rcx, rcx
0x18000fd10  sub     r8, rcx
0x18000fd13  lea     r15, ds:0[r8*8]
0x18000fd1b  mov     rcx, [r15+rdi]
0x18000fd1f  test    rcx, rcx
0x18000fd22  jnz     short loc_18000FD6F
0x18000fd24  call    cs:__imp_GetProcessHeap
0x18000fd2a  mov     rbp, rax
0x18000fd2d  xor     edx, edx; dwFlags
0x18000fd2f  mov     r8d, 18h; dwBytes
0x18000fd35  mov     rcx, rax; hHeap
0x18000fd38  call    cs:__imp_HeapAlloc
0x18000fd3e  mov     r14, rax
0x18000fd41  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000fd48  test    rax, rax
0x18000fd4b  jz      loc_18000FDDF
0x18000fd51  mov     rdx, r14
0x18000fd54  mov     rcx, rbp
0x18000fd57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd5c  nop
0x18000fd5d  xor     eax, eax
0x18000fd5f  test    r14, r14
0x18000fd62  jnz     short loc_18000FD99
0x18000fd64  mov     ecx, eax
0x18000fd66  jmp     short loc_18000FD77
0x18000fd68  xor     eax, eax
0x18000fd6a  mov     [rcx], rax
0x18000fd6d  jmp     short loc_18000FD83
0x18000fd6f  cmp     [rcx], esi
0x18000fd71  jnz     short loc_18000FD93
0x18000fd73  add     rcx, 10h
0x18000fd77  mov     [rbx], rcx
0x18000fd7a  test    rcx, rcx
0x18000fd7d  jnz     loc_18000FE33
0x18000fd83  add     rsp, 0C8h
0x18000fd8a  pop     r15
0x18000fd8c  pop     r14
0x18000fd8e  pop     rdi
0x18000fd8f  pop     rsi
0x18000fd90  pop     rbp
0x18000fd91  pop     rbx
0x18000fd92  retn
0x18000fd93  mov     rcx, [rcx+8]
0x18000fd97  jmp     short loc_18000FD1F
0x18000fd99  mov     [r14], esi
0x18000fd9c  mov     [r14+4], eax
0x18000fda0  mov     [r14+8], rax
0x18000fda4  lea     rcx, [r14+10h]
0x18000fda8  mov     [rcx], rax
0x18000fdab  nop     dword ptr [rax+rax+00h]
0x18000fdb0  mov     rax, [r15+rdi]
0x18000fdb4  mov     [r14+8], rax
0x18000fdb8  lock cmpxchg [r15+rdi], r14
0x18000fdbe  jnz     short loc_18000FDB0
0x18000fdc0  jmp     short loc_18000FD77
0x18000fdc2  xor     edx, edx; Val
0x18000fdc4  mov     r8d, 98h; Size
0x18000fdca  lea     rcx, [rsp+0F8h+var_D8]; void *
0x18000fdcf  call    memset_0
0x18000fdd4  lea     rcx, [rsp+0F8h+var_D8]; this
0x18000fdd9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000fddf  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 0; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000fde6  jnz     loc_18000FD5D
0x18000fdec  lea     rcx, ModuleName; "ntdll.dll"
0x18000fdf3  call    cs:__imp_GetModuleHandleW
0x18000fdf9  test    rax, rax
0x18000fdfc  jz      short loc_18000FE17
0x18000fdfe  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000fe05  mov     rcx, rax; hModule
0x18000fe08  call    cs:__imp_GetProcAddress
0x18000fe0e  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000fe15  jmp     short loc_18000FE1E
0x18000fe17  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000fe1e  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000fe25  test    rax, rax
0x18000fe28  jz      loc_18000FD5D
0x18000fe2e  jmp     loc_18000FD51
0x18000fe33  mov     rax, [rcx]
0x18000fe36  mov     [rbx+10h], rax
0x18000fe3a  mov     [rcx], rbx
0x18000fe3d  call    cs:__imp_GetCurrentThreadId
0x18000fe43  mov     [rbx+18h], eax
0x18000fe46  jmp     loc_18000FD83
```
