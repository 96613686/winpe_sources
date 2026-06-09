# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180003ed0`
- end: `0x180003faa`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020b8`

## callees

- `0x180003ed0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f7a`

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
0x180003ed0  push    rbx
0x180003ed2  push    rbp
0x180003ed3  push    rsi
0x180003ed4  push    rdi
0x180003ed5  push    r12
0x180003ed7  push    r13
0x180003ed9  push    r14
0x180003edb  push    r15
0x180003edd  sub     rsp, 28h
0x180003ee1  lea     r15, [rcx+50h]
0x180003ee5  mov     rdi, rcx
0x180003ee8  cmp     rcx, r15
0x180003eeb  jz      loc_180003F99
0x180003ef1  mov     rsi, [rdi]
0x180003ef4  jmp     loc_180003F80
0x180003ef9  mov     r13, rsi
0x180003efc  mov     r12, rsi
0x180003eff  mov     rsi, [rsi+8]
0x180003f03  movzx   eax, word ptr [r13+30h]
0x180003f08  mov     rbp, [r13+28h]
0x180003f0c  lea     r14, [rax+rax*4]
0x180003f10  shl     r14, 4
0x180003f14  add     r14, rbp
0x180003f17  jmp     short loc_180003F45
0x180003f19  mov     rbx, [rbp+40h]
0x180003f1d  call    cs:__imp_GetProcessHeap
0x180003f23  mov     r8, rbx; lpMem
0x180003f26  xor     edx, edx; dwFlags
0x180003f28  mov     rcx, rax; hHeap
0x180003f2b  call    cs:__imp_HeapFree
0x180003f31  mov     qword ptr [rbp+40h], 0
0x180003f39  mov     qword ptr [rbp+48h], 0
0x180003f41  add     rbp, 50h ; 'P'
0x180003f45  cmp     rbp, r14
0x180003f48  jnz     short loc_180003F19
0x180003f4a  mov     rbx, [r13+28h]
0x180003f4e  call    cs:__imp_GetProcessHeap
0x180003f54  mov     r8, rbx; lpMem
0x180003f57  xor     edx, edx; dwFlags
0x180003f59  mov     rcx, rax; hHeap
0x180003f5c  call    cs:__imp_HeapFree
0x180003f62  xor     eax, eax
0x180003f64  mov     [r13+30h], eax
0x180003f68  mov     [r13+28h], rax
0x180003f6c  call    cs:__imp_GetProcessHeap
0x180003f72  mov     r8, r12; lpMem
0x180003f75  xor     edx, edx; dwFlags
0x180003f77  mov     rcx, rax; hHeap
0x180003f7a  call    cs:__imp_HeapFree
0x180003f80  test    rsi, rsi
0x180003f83  jnz     loc_180003EF9
0x180003f89  mov     [rdi], rsi
0x180003f8c  add     rdi, 8
0x180003f90  cmp     rdi, r15
0x180003f93  jnz     loc_180003EF1
0x180003f99  add     rsp, 28h
0x180003f9d  pop     r15
0x180003f9f  pop     r14
0x180003fa1  pop     r13
0x180003fa3  pop     r12
0x180003fa5  pop     rdi
0x180003fa6  pop     rsi
0x180003fa7  pop     rbp
0x180003fa8  pop     rbx
0x180003fa9  retn
```
