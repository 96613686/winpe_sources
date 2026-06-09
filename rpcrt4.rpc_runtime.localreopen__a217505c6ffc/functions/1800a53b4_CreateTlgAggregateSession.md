# CreateTlgAggregateSession

- ea: `0x1800a53b4`
- end: `0x1800a548a`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a529c`

## callees

- `0x1800a53b4`
- `0x1800a5a04`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a53ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a53ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a53e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a53e8`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800a5408`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800a5408`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a5430`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a5430`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  char v2; // di
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v5 = v4;
  if ( v4 )
  {
    InitializeSRWLock(v4 + 33);
    if ( !a1 || !dword_1800FF148 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
      v2 = 1;
  }
  if ( !v2 )
  {
    DestroyAggregateSession(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800a53b4  mov     [rsp+arg_0], rbx
0x1800a53b9  mov     [rsp+arg_18], rsi
0x1800a53be  push    rdi
0x1800a53bf  sub     rsp, 20h
0x1800a53c3  mov     sil, cl
0x1800a53c6  xor     dil, dil
0x1800a53c9  mov     [rsp+28h+arg_8], dil
0x1800a53ce  call    cs:__imp_GetProcessHeap
0x1800a53d5  nop     dword ptr [rax+rax+00h]
0x1800a53da  mov     rcx, rax; hHeap
0x1800a53dd  mov     edx, 8; dwFlags
0x1800a53e2  mov     r8d, 168h; dwBytes
0x1800a53e8  call    cs:__imp_HeapAlloc
0x1800a53ef  nop     dword ptr [rax+rax+00h]
0x1800a53f4  mov     rbx, rax
0x1800a53f7  mov     [rsp+28h+arg_10], rax
0x1800a53fc  test    rax, rax
0x1800a53ff  jz      short loc_1800A5467
0x1800a5401  lea     rcx, [rax+108h]; SRWLock
0x1800a5408  call    cs:__imp_InitializeSRWLock
0x1800a540f  nop     dword ptr [rax+rax+00h]
0x1800a5414  test    sil, sil
0x1800a5417  jz      short loc_1800A5464
0x1800a5419  mov     ecx, cs:dword_1800FF148
0x1800a541f  test    ecx, ecx
0x1800a5421  jnz     short loc_1800A5467
0x1800a5423  xor     r8d, r8d; pcbe
0x1800a5426  mov     rdx, rbx; pv
0x1800a5429  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x1800a5430  call    cs:__imp_CreateThreadpoolTimer
0x1800a5437  nop     dword ptr [rax+rax+00h]
0x1800a543c  mov     [rbx+158h], rax
0x1800a5443  jmp     short loc_1800A545A
0x1800a5445  mov     eax, 1
0x1800a544a  xchg    eax, cs:dword_1800FF148
0x1800a5450  mov     dil, [rsp+28h+arg_8]
0x1800a5455  mov     rbx, [rsp+28h+arg_10]
0x1800a545a  cmp     qword ptr [rbx+158h], 0
0x1800a5462  jz      short loc_1800A5467
0x1800a5464  mov     dil, 1
0x1800a5467  test    dil, dil
0x1800a546a  jnz     short loc_1800A5476
0x1800a546c  mov     rcx, rbx; lpMem
0x1800a546f  call    DestroyAggregateSession
0x1800a5474  xor     ebx, ebx
0x1800a5476  mov     rax, rbx
0x1800a5479  mov     rbx, [rsp+28h+arg_0]
0x1800a547e  mov     rsi, [rsp+28h+arg_18]
0x1800a5483  add     rsp, 20h
0x1800a5487  pop     rdi
0x1800a5488  retn
0x1800cfffe  push    rbp
0x1800d0000  sub     rsp, 20h
0x1800d0004  mov     rbp, rdx
0x1800d0007  mov     rax, [rcx]
0x1800d000a  xor     ecx, ecx
0x1800d000c  cmp     dword ptr [rax], 0C000000Dh
0x1800d0012  setz    cl
0x1800d0015  mov     eax, ecx
0x1800d0017  add     rsp, 20h
0x1800d001b  pop     rbp
0x1800d001c  retn
```
