# CreateTlgAggregateSession

- ea: `0x1800a1e38`
- end: `0x1800a1ef5`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a1d2c`

## callees

- `0x1800a1e38`
- `0x1800a2460`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a1e52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a1e52`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1e66`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1e66`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800a1e80`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800a1e80`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a1ea2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a1ea2`

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
    if ( !a1 || !dword_1800FA148 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x1800a1e38  mov     [rsp+arg_0], rbx
0x1800a1e3d  mov     [rsp+arg_18], rsi
0x1800a1e42  push    rdi
0x1800a1e43  sub     rsp, 20h
0x1800a1e47  mov     sil, cl
0x1800a1e4a  xor     dil, dil
0x1800a1e4d  mov     [rsp+28h+arg_8], dil
0x1800a1e52  call    cs:__imp_GetProcessHeap
0x1800a1e58  mov     rcx, rax; hHeap
0x1800a1e5b  mov     edx, 8; dwFlags
0x1800a1e60  mov     r8d, 168h; dwBytes
0x1800a1e66  call    cs:__imp_HeapAlloc
0x1800a1e6c  mov     rbx, rax
0x1800a1e6f  mov     [rsp+28h+arg_10], rax
0x1800a1e74  test    rax, rax
0x1800a1e77  jz      short loc_1800A1ED3
0x1800a1e79  lea     rcx, [rax+108h]; SRWLock
0x1800a1e80  call    cs:__imp_InitializeSRWLock
0x1800a1e86  test    sil, sil
0x1800a1e89  jz      short loc_1800A1ED0
0x1800a1e8b  mov     ecx, cs:dword_1800FA148
0x1800a1e91  test    ecx, ecx
0x1800a1e93  jnz     short loc_1800A1ED3
0x1800a1e95  xor     r8d, r8d; pcbe
0x1800a1e98  mov     rdx, rbx; pv
0x1800a1e9b  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x1800a1ea2  call    cs:__imp_CreateThreadpoolTimer
0x1800a1ea8  mov     [rbx+158h], rax
0x1800a1eaf  jmp     short loc_1800A1EC6
0x1800a1eb1  mov     eax, 1
0x1800a1eb6  xchg    eax, cs:dword_1800FA148
0x1800a1ebc  mov     dil, [rsp+28h+arg_8]
0x1800a1ec1  mov     rbx, [rsp+28h+arg_10]
0x1800a1ec6  cmp     qword ptr [rbx+158h], 0
0x1800a1ece  jz      short loc_1800A1ED3
0x1800a1ed0  mov     dil, 1
0x1800a1ed3  test    dil, dil
0x1800a1ed6  jnz     short loc_1800A1EE2
0x1800a1ed8  mov     rcx, rbx; lpMem
0x1800a1edb  call    DestroyAggregateSession
0x1800a1ee0  xor     ebx, ebx
0x1800a1ee2  mov     rax, rbx
0x1800a1ee5  mov     rbx, [rsp+28h+arg_0]
0x1800a1eea  mov     rsi, [rsp+28h+arg_18]
0x1800a1eef  add     rsp, 20h
0x1800a1ef3  pop     rdi
0x1800a1ef4  retn
0x1800cb398  push    rbp
0x1800cb39a  sub     rsp, 20h
0x1800cb39e  mov     rbp, rdx
0x1800cb3a1  mov     rax, [rcx]
0x1800cb3a4  xor     ecx, ecx
0x1800cb3a6  cmp     dword ptr [rax], 0C000000Dh
0x1800cb3ac  setz    cl
0x1800cb3af  mov     eax, ecx
0x1800cb3b1  add     rsp, 20h
0x1800cb3b5  pop     rbp
0x1800cb3b6  retn
```
