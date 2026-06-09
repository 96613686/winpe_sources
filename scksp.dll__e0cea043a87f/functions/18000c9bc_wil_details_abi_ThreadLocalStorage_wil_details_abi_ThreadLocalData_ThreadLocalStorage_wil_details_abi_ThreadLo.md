# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000c9bc`
- end: `0x18000ca96`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c904`

## callees

- `0x18000c9bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca58`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        _QWORD *a1)
{
  _QWORD *v1; // r15
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  _QWORD *v4; // r13
  void *v5; // r12
  __int64 v6; // rbp
  __int64 v7; // r14
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  HANDLE v12; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v5 = v3;
      v3 = (_QWORD *)v3[1];
      v6 = v4[5];
      v7 = v6 + 80LL * *((unsigned __int16 *)v4 + 24);
      while ( v6 != v7 )
      {
        v8 = *(void **)(v6 + 64);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
        *(_QWORD *)(v6 + 64) = 0;
        *(_QWORD *)(v6 + 72) = 0;
        v6 += 80;
      }
      v10 = (void *)v4[5];
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
      *((_DWORD *)v4 + 12) = 0;
      v4[5] = 0;
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v5);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x18000c9bc  push    rbx
0x18000c9be  push    rbp
0x18000c9bf  push    rsi
0x18000c9c0  push    rdi
0x18000c9c1  push    r12
0x18000c9c3  push    r13
0x18000c9c5  push    r14
0x18000c9c7  push    r15
0x18000c9c9  sub     rsp, 28h
0x18000c9cd  lea     r15, [rcx+50h]
0x18000c9d1  mov     rdi, rcx
0x18000c9d4  cmp     rcx, r15
0x18000c9d7  jz      loc_18000CA85
0x18000c9dd  mov     rsi, [rdi]
0x18000c9e0  jmp     loc_18000CA6C
0x18000c9e5  mov     r13, rsi
0x18000c9e8  mov     r12, rsi
0x18000c9eb  mov     rsi, [rsi+8]
0x18000c9ef  movzx   eax, word ptr [r13+30h]
0x18000c9f4  mov     rbp, [r13+28h]
0x18000c9f8  lea     r14, [rax+rax*4]
0x18000c9fc  shl     r14, 4
0x18000ca00  add     r14, rbp
0x18000ca03  jmp     short loc_18000CA31
0x18000ca05  mov     rbx, [rbp+40h]
0x18000ca09  call    cs:__imp_GetProcessHeap
0x18000ca0f  mov     r8, rbx; lpMem
0x18000ca12  xor     edx, edx; dwFlags
0x18000ca14  mov     rcx, rax; hHeap
0x18000ca17  call    cs:__imp_HeapFree
0x18000ca1d  mov     qword ptr [rbp+40h], 0
0x18000ca25  mov     qword ptr [rbp+48h], 0
0x18000ca2d  add     rbp, 50h ; 'P'
0x18000ca31  cmp     rbp, r14
0x18000ca34  jnz     short loc_18000CA05
0x18000ca36  mov     rbx, [r13+28h]
0x18000ca3a  call    cs:__imp_GetProcessHeap
0x18000ca40  mov     r8, rbx; lpMem
0x18000ca43  xor     edx, edx; dwFlags
0x18000ca45  mov     rcx, rax; hHeap
0x18000ca48  call    cs:__imp_HeapFree
0x18000ca4e  xor     eax, eax
0x18000ca50  mov     [r13+30h], eax
0x18000ca54  mov     [r13+28h], rax
0x18000ca58  call    cs:__imp_GetProcessHeap
0x18000ca5e  mov     r8, r12; lpMem
0x18000ca61  xor     edx, edx; dwFlags
0x18000ca63  mov     rcx, rax; hHeap
0x18000ca66  call    cs:__imp_HeapFree
0x18000ca6c  test    rsi, rsi
0x18000ca6f  jnz     loc_18000C9E5
0x18000ca75  mov     [rdi], rsi
0x18000ca78  add     rdi, 8
0x18000ca7c  cmp     rdi, r15
0x18000ca7f  jnz     loc_18000C9DD
0x18000ca85  add     rsp, 28h
0x18000ca89  pop     r15
0x18000ca8b  pop     r14
0x18000ca8d  pop     r13
0x18000ca8f  pop     r12
0x18000ca91  pop     rdi
0x18000ca92  pop     rsi
0x18000ca93  pop     rbp
0x18000ca94  pop     rbx
0x18000ca95  retn
```
