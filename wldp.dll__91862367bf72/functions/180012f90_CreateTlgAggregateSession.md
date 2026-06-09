# CreateTlgAggregateSession

- ea: `0x180012f90`
- end: `0x18001302e`
- name: `CreateTlgAggregateSession`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c620`

## callees

- `0x180012f90`
- `0x180013294`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180012fcb`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180012fcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012f9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012f9d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012fb1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012fb1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012fed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012fed`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v3; // rax
  RTL_SRWLOCK *v4; // rbx

  ProcessHeap = GetProcessHeap();
  v3 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v4 = v3;
  if ( !v3
    || (InitializeSRWLock(v3 + 33), a1)
    && (dword_18005ADF0 || (v4[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v4, 0)) == 0) )
  {
    DestroyAggregateSession(v4);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180012f90  mov     [rsp+arg_0], rbx
0x180012f95  push    rdi
0x180012f96  sub     rsp, 20h
0x180012f9a  movzx   edi, cl
0x180012f9d  call    cs:__imp_GetProcessHeap
0x180012fa3  mov     rcx, rax; hHeap
0x180012fa6  mov     edx, 8; dwFlags
0x180012fab  mov     r8d, 168h; dwBytes
0x180012fb1  call    cs:__imp_HeapAlloc
0x180012fb7  mov     rbx, rax
0x180012fba  mov     [rsp+28h+arg_8], rax
0x180012fbf  test    rax, rax
0x180012fc2  jz      short loc_180013016
0x180012fc4  lea     rcx, [rax+108h]; SRWLock
0x180012fcb  call    cs:__imp_InitializeSRWLock
0x180012fd1  test    dil, dil
0x180012fd4  jz      short loc_180013020
0x180012fd6  mov     eax, cs:dword_18005ADF0
0x180012fdc  test    eax, eax
0x180012fde  jnz     short loc_180013016
0x180012fe0  xor     r8d, r8d; pcbe
0x180012fe3  mov     rdx, rbx; pv
0x180012fe6  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180012fed  call    cs:__imp_CreateThreadpoolTimer
0x180012ff3  mov     [rbx+158h], rax
0x180012ffa  jmp     short loc_18001300C
0x180012ffc  mov     eax, 1
0x180013001  xchg    eax, cs:dword_18005ADF0
0x180013007  mov     rbx, [rsp+28h+arg_8]
0x18001300c  cmp     qword ptr [rbx+158h], 0
0x180013014  jnz     short loc_180013020
0x180013016  mov     rcx, rbx; lpMem
0x180013019  call    DestroyAggregateSession
0x18001301e  xor     ebx, ebx
0x180013020  mov     rax, rbx
0x180013023  mov     rbx, [rsp+28h+arg_0]
0x180013028  add     rsp, 20h
0x18001302c  pop     rdi
0x18001302d  retn
0x18003eb50  push    rbp
0x18003eb52  sub     rsp, 20h
0x18003eb56  mov     rbp, rdx
0x18003eb59  mov     rax, [rcx]
0x18003eb5c  xor     ecx, ecx
0x18003eb5e  cmp     dword ptr [rax], 0C000000Dh
0x18003eb64  setz    cl
0x18003eb67  mov     eax, ecx
0x18003eb69  add     rsp, 20h
0x18003eb6d  pop     rbp
0x18003eb6e  retn
```
