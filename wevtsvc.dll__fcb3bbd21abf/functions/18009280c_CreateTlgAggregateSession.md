# CreateTlgAggregateSession

- ea: `0x18009280c`
- end: `0x1800928c9`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180092700`

## callees

- `0x18009280c`
- `0x1800d1e24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009283a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009283a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092826`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092826`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180092876`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180092876`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180092854`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180092854`

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
    if ( !a1 || !dword_1801116A0 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x18009280c  mov     [rsp+arg_0], rbx
0x180092811  mov     [rsp+arg_18], rsi
0x180092816  push    rdi
0x180092817  sub     rsp, 20h
0x18009281b  mov     sil, cl
0x18009281e  xor     dil, dil
0x180092821  mov     [rsp+28h+arg_8], dil
0x180092826  call    cs:__imp_GetProcessHeap
0x18009282c  mov     rcx, rax; hHeap
0x18009282f  mov     edx, 8; dwFlags
0x180092834  mov     r8d, 168h; dwBytes
0x18009283a  call    cs:__imp_HeapAlloc
0x180092840  mov     rbx, rax
0x180092843  mov     [rsp+28h+arg_10], rax
0x180092848  test    rax, rax
0x18009284b  jz      short loc_1800928A7
0x18009284d  lea     rcx, [rax+108h]; SRWLock
0x180092854  call    cs:__imp_InitializeSRWLock
0x18009285a  test    sil, sil
0x18009285d  jz      short loc_1800928A4
0x18009285f  mov     ecx, cs:dword_1801116A0
0x180092865  test    ecx, ecx
0x180092867  jnz     short loc_1800928A7
0x180092869  xor     r8d, r8d; pcbe
0x18009286c  mov     rdx, rbx; pv
0x18009286f  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180092876  call    cs:__imp_CreateThreadpoolTimer
0x18009287c  mov     [rbx+158h], rax
0x180092883  jmp     short loc_18009289A
0x180092885  mov     eax, 1
0x18009288a  xchg    eax, cs:dword_1801116A0
0x180092890  mov     dil, [rsp+28h+arg_8]
0x180092895  mov     rbx, [rsp+28h+arg_10]
0x18009289a  cmp     qword ptr [rbx+158h], 0
0x1800928a2  jz      short loc_1800928A7
0x1800928a4  mov     dil, 1
0x1800928a7  test    dil, dil
0x1800928aa  jnz     short loc_1800928B6
0x1800928ac  mov     rcx, rbx; lpMem
0x1800928af  call    DestroyAggregateSession
0x1800928b4  xor     ebx, ebx
0x1800928b6  mov     rax, rbx
0x1800928b9  mov     rbx, [rsp+28h+arg_0]
0x1800928be  mov     rsi, [rsp+28h+arg_18]
0x1800928c3  add     rsp, 20h
0x1800928c7  pop     rdi
0x1800928c8  retn
0x1800d9697  push    rbp
0x1800d9699  sub     rsp, 20h
0x1800d969d  mov     rbp, rdx
0x1800d96a0  mov     rax, [rcx]
0x1800d96a3  xor     ecx, ecx
0x1800d96a5  cmp     dword ptr [rax], 0C000000Dh
0x1800d96ab  setz    cl
0x1800d96ae  mov     eax, ecx
0x1800d96b0  add     rsp, 20h
0x1800d96b4  pop     rbp
0x1800d96b5  retn
```
