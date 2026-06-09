# Win32ThreadPoolPostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),_OVERLAPPED *)

- ea: `0x180001aa0`
- end: `0x180001b2b`
- name: `?Win32ThreadPoolPostCompletion@@YAHKP6AXKKPEAU_OVERLAPPED@@@Z0@Z`
- size: `139`
- prototype: `__int64 __fastcall(unsigned int, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *), struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001360`

## callees

- `0x180001aa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ae7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001b1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001b1a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180001add`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180001add`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180001ab8`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180001ab8`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180001afd`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180001afd`

## pseudocode

```c
__int64 __fastcall Win32ThreadPoolPostCompletion(
        int a1,
        void (*a2)(unsigned int, unsigned int, struct _OVERLAPPED *),
        struct _OVERLAPPED *a3)
{
  _QWORD *v6; // rax
  void *v7; // rbx
  DWORD LastError; // edi

  v6 = ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)WIN32_COMPLETION_PACKET::sm_Allocator);
  v7 = v6;
  if ( v6 )
  {
    *v6 = a2;
    v6[1] = a3;
    *((_DWORD *)v6 + 4) = a1;
    if ( QueueUserWorkItem(WIN32_COMPLETION_PACKET::WorkItemCallback, v6, 0) )
      return 1;
    LastError = GetLastError();
    if ( !LastError )
      return 1;
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)WIN32_COMPLETION_PACKET::sm_Allocator, v7);
  }
  else
  {
    LastError = 8;
  }
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x180001aa0  push    rbx
0x180001aa2  push    rbp
0x180001aa3  push    rsi
0x180001aa4  push    rdi
0x180001aa5  sub     rsp, 28h
0x180001aa9  mov     ebp, ecx
0x180001aab  mov     rdi, r8
0x180001aae  mov     rcx, cs:?sm_Allocator@WIN32_COMPLETION_PACKET@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * WIN32_COMPLETION_PACKET::sm_Allocator
0x180001ab5  mov     rsi, rdx
0x180001ab8  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180001abe  mov     rbx, rax
0x180001ac1  test    rax, rax
0x180001ac4  jz      short loc_180001B13
0x180001ac6  xor     r8d, r8d; Flags
0x180001ac9  mov     [rax], rsi
0x180001acc  mov     rdx, rax; Context
0x180001acf  mov     [rax+8], rdi
0x180001ad3  lea     rcx, ?WorkItemCallback@WIN32_COMPLETION_PACKET@@CAKPEAX@Z; Function
0x180001ada  mov     [rax+10h], ebp
0x180001add  call    cs:__imp_QueueUserWorkItem
0x180001ae3  test    eax, eax
0x180001ae5  jnz     short loc_180001B05
0x180001ae7  call    cs:__imp_GetLastError
0x180001aed  mov     edi, eax
0x180001aef  test    eax, eax
0x180001af1  jz      short loc_180001B05
0x180001af3  mov     rcx, cs:?sm_Allocator@WIN32_COMPLETION_PACKET@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * WIN32_COMPLETION_PACKET::sm_Allocator
0x180001afa  mov     rdx, rbx
0x180001afd  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180001b03  jmp     short loc_180001B18
0x180001b05  mov     eax, 1
0x180001b0a  add     rsp, 28h
0x180001b0e  pop     rdi
0x180001b0f  pop     rsi
0x180001b10  pop     rbp
0x180001b11  pop     rbx
0x180001b12  retn
0x180001b13  mov     edi, 8
0x180001b18  mov     ecx, edi; dwErrCode
0x180001b1a  call    cs:__imp_SetLastError
0x180001b20  xor     eax, eax
0x180001b22  add     rsp, 28h
0x180001b26  pop     rdi
0x180001b27  pop     rsi
0x180001b28  pop     rbp
0x180001b29  pop     rbx
0x180001b2a  retn
```
