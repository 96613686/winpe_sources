# CreateTlgAggregateSession

- ea: `0x180011c1c`
- end: `0x180011cd9`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d32c`

## callees

- `0x180011c1c`
- `0x180011f9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180011c64`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180011c64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011c4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011c4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011c36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011c36`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011c86`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011c86`

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
    if ( !a1 || !dword_180045EC4 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180011c1c  mov     [rsp+arg_0], rbx
0x180011c21  mov     [rsp+arg_18], rsi
0x180011c26  push    rdi
0x180011c27  sub     rsp, 20h
0x180011c2b  mov     sil, cl
0x180011c2e  xor     dil, dil
0x180011c31  mov     [rsp+28h+arg_8], dil
0x180011c36  call    cs:__imp_GetProcessHeap
0x180011c3c  mov     rcx, rax; hHeap
0x180011c3f  mov     edx, 8; dwFlags
0x180011c44  mov     r8d, 168h; dwBytes
0x180011c4a  call    cs:__imp_HeapAlloc
0x180011c50  mov     rbx, rax
0x180011c53  mov     [rsp+28h+arg_10], rax
0x180011c58  test    rax, rax
0x180011c5b  jz      short loc_180011CB7
0x180011c5d  lea     rcx, [rax+108h]; SRWLock
0x180011c64  call    cs:__imp_InitializeSRWLock
0x180011c6a  test    sil, sil
0x180011c6d  jz      short loc_180011CB4
0x180011c6f  mov     ecx, cs:dword_180045EC4
0x180011c75  test    ecx, ecx
0x180011c77  jnz     short loc_180011CB7
0x180011c79  xor     r8d, r8d; pcbe
0x180011c7c  mov     rdx, rbx; pv
0x180011c7f  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180011c86  call    cs:__imp_CreateThreadpoolTimer
0x180011c8c  mov     [rbx+158h], rax
0x180011c93  jmp     short loc_180011CAA
0x180011c95  mov     eax, 1
0x180011c9a  xchg    eax, cs:dword_180045EC4
0x180011ca0  mov     dil, [rsp+28h+arg_8]
0x180011ca5  mov     rbx, [rsp+28h+arg_10]
0x180011caa  cmp     qword ptr [rbx+158h], 0
0x180011cb2  jz      short loc_180011CB7
0x180011cb4  mov     dil, 1
0x180011cb7  test    dil, dil
0x180011cba  jnz     short loc_180011CC6
0x180011cbc  mov     rcx, rbx; lpMem
0x180011cbf  call    DestroyAggregateSession
0x180011cc4  xor     ebx, ebx
0x180011cc6  mov     rax, rbx
0x180011cc9  mov     rbx, [rsp+28h+arg_0]
0x180011cce  mov     rsi, [rsp+28h+arg_18]
0x180011cd3  add     rsp, 20h
0x180011cd7  pop     rdi
0x180011cd8  retn
0x18003783c  push    rbp
0x18003783e  sub     rsp, 20h
0x180037842  mov     rbp, rdx
0x180037845  mov     rax, [rcx]
0x180037848  xor     ecx, ecx
0x18003784a  cmp     dword ptr [rax], 0C000000Dh
0x180037850  setz    cl
0x180037853  mov     eax, ecx
0x180037855  add     rsp, 20h
0x180037859  pop     rbp
0x18003785a  retn
```
