# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800071cc`
- end: `0x1800072a6`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000716c`

## callees

- `0x1800071cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007227`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007258`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007276`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007227`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007258`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007276`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007219`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000724a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007268`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007219`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000724a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007268`

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
0x1800071cc  push    rbx
0x1800071ce  push    rbp
0x1800071cf  push    rsi
0x1800071d0  push    rdi
0x1800071d1  push    r12
0x1800071d3  push    r13
0x1800071d5  push    r14
0x1800071d7  push    r15
0x1800071d9  sub     rsp, 28h
0x1800071dd  lea     r15, [rcx+50h]
0x1800071e1  mov     rdi, rcx
0x1800071e4  cmp     rcx, r15
0x1800071e7  jz      loc_180007295
0x1800071ed  mov     rsi, [rdi]
0x1800071f0  jmp     loc_18000727C
0x1800071f5  mov     r13, rsi
0x1800071f8  mov     r12, rsi
0x1800071fb  mov     rsi, [rsi+8]
0x1800071ff  movzx   eax, word ptr [r13+30h]
0x180007204  mov     rbp, [r13+28h]
0x180007208  lea     r14, [rax+rax*4]
0x18000720c  shl     r14, 4
0x180007210  add     r14, rbp
0x180007213  jmp     short loc_180007241
0x180007215  mov     rbx, [rbp+40h]
0x180007219  call    cs:__imp_GetProcessHeap
0x18000721f  mov     r8, rbx; lpMem
0x180007222  xor     edx, edx; dwFlags
0x180007224  mov     rcx, rax; hHeap
0x180007227  call    cs:__imp_HeapFree
0x18000722d  mov     qword ptr [rbp+40h], 0
0x180007235  mov     qword ptr [rbp+48h], 0
0x18000723d  add     rbp, 50h ; 'P'
0x180007241  cmp     rbp, r14
0x180007244  jnz     short loc_180007215
0x180007246  mov     rbx, [r13+28h]
0x18000724a  call    cs:__imp_GetProcessHeap
0x180007250  mov     r8, rbx; lpMem
0x180007253  xor     edx, edx; dwFlags
0x180007255  mov     rcx, rax; hHeap
0x180007258  call    cs:__imp_HeapFree
0x18000725e  xor     eax, eax
0x180007260  mov     [r13+30h], eax
0x180007264  mov     [r13+28h], rax
0x180007268  call    cs:__imp_GetProcessHeap
0x18000726e  mov     r8, r12; lpMem
0x180007271  xor     edx, edx; dwFlags
0x180007273  mov     rcx, rax; hHeap
0x180007276  call    cs:__imp_HeapFree
0x18000727c  test    rsi, rsi
0x18000727f  jnz     loc_1800071F5
0x180007285  mov     [rdi], rsi
0x180007288  add     rdi, 8
0x18000728c  cmp     rdi, r15
0x18000728f  jnz     loc_1800071ED
0x180007295  add     rsp, 28h
0x180007299  pop     r15
0x18000729b  pop     r14
0x18000729d  pop     r13
0x18000729f  pop     r12
0x1800072a1  pop     rdi
0x1800072a2  pop     rsi
0x1800072a3  pop     rbp
0x1800072a4  pop     rbx
0x1800072a5  retn
```
