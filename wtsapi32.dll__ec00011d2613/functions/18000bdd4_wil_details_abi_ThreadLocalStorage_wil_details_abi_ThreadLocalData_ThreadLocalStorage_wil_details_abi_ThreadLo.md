# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000bdd4`
- end: `0x18000beae`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bda4`

## callees

- `0x18000bdd4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be70`

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
0x18000bdd4  push    rbx
0x18000bdd6  push    rbp
0x18000bdd7  push    rsi
0x18000bdd8  push    rdi
0x18000bdd9  push    r12
0x18000bddb  push    r13
0x18000bddd  push    r14
0x18000bddf  push    r15
0x18000bde1  sub     rsp, 28h
0x18000bde5  lea     r15, [rcx+50h]
0x18000bde9  mov     rdi, rcx
0x18000bdec  cmp     rcx, r15
0x18000bdef  jz      loc_18000BE9D
0x18000bdf5  mov     rsi, [rdi]
0x18000bdf8  jmp     loc_18000BE84
0x18000bdfd  mov     r13, rsi
0x18000be00  mov     r12, rsi
0x18000be03  mov     rsi, [rsi+8]
0x18000be07  movzx   eax, word ptr [r13+30h]
0x18000be0c  mov     rbp, [r13+28h]
0x18000be10  lea     r14, [rax+rax*4]
0x18000be14  shl     r14, 4
0x18000be18  add     r14, rbp
0x18000be1b  jmp     short loc_18000BE49
0x18000be1d  mov     rbx, [rbp+40h]
0x18000be21  call    cs:__imp_GetProcessHeap
0x18000be27  mov     r8, rbx; lpMem
0x18000be2a  xor     edx, edx; dwFlags
0x18000be2c  mov     rcx, rax; hHeap
0x18000be2f  call    cs:__imp_HeapFree
0x18000be35  mov     qword ptr [rbp+40h], 0
0x18000be3d  mov     qword ptr [rbp+48h], 0
0x18000be45  add     rbp, 50h ; 'P'
0x18000be49  cmp     rbp, r14
0x18000be4c  jnz     short loc_18000BE1D
0x18000be4e  mov     rbx, [r13+28h]
0x18000be52  call    cs:__imp_GetProcessHeap
0x18000be58  mov     r8, rbx; lpMem
0x18000be5b  xor     edx, edx; dwFlags
0x18000be5d  mov     rcx, rax; hHeap
0x18000be60  call    cs:__imp_HeapFree
0x18000be66  xor     eax, eax
0x18000be68  mov     [r13+30h], eax
0x18000be6c  mov     [r13+28h], rax
0x18000be70  call    cs:__imp_GetProcessHeap
0x18000be76  mov     r8, r12; lpMem
0x18000be79  xor     edx, edx; dwFlags
0x18000be7b  mov     rcx, rax; hHeap
0x18000be7e  call    cs:__imp_HeapFree
0x18000be84  test    rsi, rsi
0x18000be87  jnz     loc_18000BDFD
0x18000be8d  mov     [rdi], rsi
0x18000be90  add     rdi, 8
0x18000be94  cmp     rdi, r15
0x18000be97  jnz     loc_18000BDF5
0x18000be9d  add     rsp, 28h
0x18000bea1  pop     r15
0x18000bea3  pop     r14
0x18000bea5  pop     r13
0x18000bea7  pop     r12
0x18000bea9  pop     rdi
0x18000beaa  pop     rsi
0x18000beab  pop     rbp
0x18000beac  pop     rbx
0x18000bead  retn
```
