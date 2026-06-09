# CreateTlgAggregateSession

- ea: `0x18000af54`
- end: `0x18000b011`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: `RTL_SRWLOCK *__fastcall(char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b7d0`

## callees

- `0x18000af54`
- `0x18000b018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000af9c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000af9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af6e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000af82`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000af82`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000afbe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000afbe`

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
    if ( !a1 || !dword_180013600 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x18000af54  mov     [rsp+arg_0], rbx
0x18000af59  mov     [rsp+arg_18], rsi
0x18000af5e  push    rdi
0x18000af5f  sub     rsp, 20h
0x18000af63  mov     sil, cl
0x18000af66  xor     dil, dil
0x18000af69  mov     [rsp+28h+arg_8], dil
0x18000af6e  call    cs:__imp_GetProcessHeap
0x18000af74  mov     rcx, rax; hHeap
0x18000af77  mov     edx, 8; dwFlags
0x18000af7c  mov     r8d, 168h; dwBytes
0x18000af82  call    cs:__imp_HeapAlloc
0x18000af88  mov     rbx, rax
0x18000af8b  mov     [rsp+28h+arg_10], rax
0x18000af90  test    rax, rax
0x18000af93  jz      short loc_18000AFEF
0x18000af95  lea     rcx, [rax+108h]; SRWLock
0x18000af9c  call    cs:__imp_InitializeSRWLock
0x18000afa2  test    sil, sil
0x18000afa5  jz      short loc_18000AFEC
0x18000afa7  mov     ecx, cs:dword_180013600
0x18000afad  test    ecx, ecx
0x18000afaf  jnz     short loc_18000AFEF
0x18000afb1  xor     r8d, r8d; pcbe
0x18000afb4  mov     rdx, rbx; pv
0x18000afb7  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18000afbe  call    cs:__imp_CreateThreadpoolTimer
0x18000afc4  mov     [rbx+158h], rax
0x18000afcb  jmp     short loc_18000AFE2
0x18000afcd  mov     eax, 1
0x18000afd2  xchg    eax, cs:dword_180013600
0x18000afd8  mov     dil, [rsp+28h+arg_8]
0x18000afdd  mov     rbx, [rsp+28h+arg_10]
0x18000afe2  cmp     qword ptr [rbx+158h], 0
0x18000afea  jz      short loc_18000AFEF
0x18000afec  mov     dil, 1
0x18000afef  test    dil, dil
0x18000aff2  jnz     short loc_18000AFFE
0x18000aff4  mov     rcx, rbx; lpMem
0x18000aff7  call    DestroyAggregateSession
0x18000affc  xor     ebx, ebx
0x18000affe  mov     rax, rbx
0x18000b001  mov     rbx, [rsp+28h+arg_0]
0x18000b006  mov     rsi, [rsp+28h+arg_18]
0x18000b00b  add     rsp, 20h
0x18000b00f  pop     rdi
0x18000b010  retn
0x18000c681  push    rbp
0x18000c683  sub     rsp, 20h
0x18000c687  mov     rbp, rdx
0x18000c68a  mov     rax, [rcx]
0x18000c68d  xor     ecx, ecx
0x18000c68f  cmp     dword ptr [rax], 0C000000Dh
0x18000c695  setz    cl
0x18000c698  mov     eax, ecx
0x18000c69a  add     rsp, 20h
0x18000c69e  pop     rbp
0x18000c69f  retn
```
