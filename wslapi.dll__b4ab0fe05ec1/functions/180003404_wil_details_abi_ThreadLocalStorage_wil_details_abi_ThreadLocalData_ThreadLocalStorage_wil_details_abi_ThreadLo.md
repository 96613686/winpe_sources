# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180003404`
- end: `0x1800034de`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000337c`

## callees

- `0x180003404`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000345f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003490`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000345f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003490`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003451`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003482`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003451`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003482`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034a0`

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
0x180003404  push    rbx
0x180003406  push    rbp
0x180003407  push    rsi
0x180003408  push    rdi
0x180003409  push    r12
0x18000340b  push    r13
0x18000340d  push    r14
0x18000340f  push    r15
0x180003411  sub     rsp, 28h
0x180003415  lea     r15, [rcx+50h]
0x180003419  mov     rdi, rcx
0x18000341c  cmp     rcx, r15
0x18000341f  jz      loc_1800034CD
0x180003425  mov     rsi, [rdi]
0x180003428  jmp     loc_1800034B4
0x18000342d  mov     r13, rsi
0x180003430  mov     r12, rsi
0x180003433  mov     rsi, [rsi+8]
0x180003437  movzx   eax, word ptr [r13+30h]
0x18000343c  mov     rbp, [r13+28h]
0x180003440  lea     r14, [rax+rax*4]
0x180003444  shl     r14, 4
0x180003448  add     r14, rbp
0x18000344b  jmp     short loc_180003479
0x18000344d  mov     rbx, [rbp+40h]
0x180003451  call    cs:__imp_GetProcessHeap
0x180003457  mov     r8, rbx; lpMem
0x18000345a  xor     edx, edx; dwFlags
0x18000345c  mov     rcx, rax; hHeap
0x18000345f  call    cs:__imp_HeapFree
0x180003465  mov     qword ptr [rbp+40h], 0
0x18000346d  mov     qword ptr [rbp+48h], 0
0x180003475  add     rbp, 50h ; 'P'
0x180003479  cmp     rbp, r14
0x18000347c  jnz     short loc_18000344D
0x18000347e  mov     rbx, [r13+28h]
0x180003482  call    cs:__imp_GetProcessHeap
0x180003488  mov     r8, rbx; lpMem
0x18000348b  xor     edx, edx; dwFlags
0x18000348d  mov     rcx, rax; hHeap
0x180003490  call    cs:__imp_HeapFree
0x180003496  xor     eax, eax
0x180003498  mov     [r13+30h], eax
0x18000349c  mov     [r13+28h], rax
0x1800034a0  call    cs:__imp_GetProcessHeap
0x1800034a6  mov     r8, r12; lpMem
0x1800034a9  xor     edx, edx; dwFlags
0x1800034ab  mov     rcx, rax; hHeap
0x1800034ae  call    cs:__imp_HeapFree
0x1800034b4  test    rsi, rsi
0x1800034b7  jnz     loc_18000342D
0x1800034bd  mov     [rdi], rsi
0x1800034c0  add     rdi, 8
0x1800034c4  cmp     rdi, r15
0x1800034c7  jnz     loc_180003425
0x1800034cd  add     rsp, 28h
0x1800034d1  pop     r15
0x1800034d3  pop     r14
0x1800034d5  pop     r13
0x1800034d7  pop     r12
0x1800034d9  pop     rdi
0x1800034da  pop     rsi
0x1800034db  pop     rbp
0x1800034dc  pop     rbx
0x1800034dd  retn
```
