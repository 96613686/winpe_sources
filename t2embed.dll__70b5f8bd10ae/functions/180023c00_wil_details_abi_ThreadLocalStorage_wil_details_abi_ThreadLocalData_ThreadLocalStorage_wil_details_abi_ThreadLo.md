# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180023c00`
- end: `0x180023cda`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180023bd0`

## callees

- `0x180023c00`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180023c5b`
- `KERNEL32!HeapFree` at `0x180023c8c`
- `KERNEL32!HeapFree` at `0x180023caa`
- `KERNEL32!HeapFree` at `0x180023c5b`
- `KERNEL32!HeapFree` at `0x180023c8c`
- `KERNEL32!HeapFree` at `0x180023caa`
- `KERNEL32!GetProcessHeap` at `0x180023c4d`
- `KERNEL32!GetProcessHeap` at `0x180023c7e`
- `KERNEL32!GetProcessHeap` at `0x180023c9c`
- `KERNEL32!GetProcessHeap` at `0x180023c4d`
- `KERNEL32!GetProcessHeap` at `0x180023c7e`
- `KERNEL32!GetProcessHeap` at `0x180023c9c`

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
0x180023c00  push    rbx
0x180023c02  push    rbp
0x180023c03  push    rsi
0x180023c04  push    rdi
0x180023c05  push    r12
0x180023c07  push    r13
0x180023c09  push    r14
0x180023c0b  push    r15
0x180023c0d  sub     rsp, 28h
0x180023c11  lea     r15, [rcx+50h]
0x180023c15  mov     rdi, rcx
0x180023c18  cmp     rcx, r15
0x180023c1b  jz      loc_180023CC9
0x180023c21  mov     rsi, [rdi]
0x180023c24  jmp     loc_180023CB0
0x180023c29  mov     r13, rsi
0x180023c2c  mov     r12, rsi
0x180023c2f  mov     rsi, [rsi+8]
0x180023c33  movzx   eax, word ptr [r13+30h]
0x180023c38  mov     rbp, [r13+28h]
0x180023c3c  lea     r14, [rax+rax*4]
0x180023c40  shl     r14, 4
0x180023c44  add     r14, rbp
0x180023c47  jmp     short loc_180023C75
0x180023c49  mov     rbx, [rbp+40h]
0x180023c4d  call    cs:__imp_GetProcessHeap
0x180023c53  mov     r8, rbx; lpMem
0x180023c56  xor     edx, edx; dwFlags
0x180023c58  mov     rcx, rax; hHeap
0x180023c5b  call    cs:__imp_HeapFree
0x180023c61  mov     qword ptr [rbp+40h], 0
0x180023c69  mov     qword ptr [rbp+48h], 0
0x180023c71  add     rbp, 50h ; 'P'
0x180023c75  cmp     rbp, r14
0x180023c78  jnz     short loc_180023C49
0x180023c7a  mov     rbx, [r13+28h]
0x180023c7e  call    cs:__imp_GetProcessHeap
0x180023c84  mov     r8, rbx; lpMem
0x180023c87  xor     edx, edx; dwFlags
0x180023c89  mov     rcx, rax; hHeap
0x180023c8c  call    cs:__imp_HeapFree
0x180023c92  xor     eax, eax
0x180023c94  mov     [r13+30h], eax
0x180023c98  mov     [r13+28h], rax
0x180023c9c  call    cs:__imp_GetProcessHeap
0x180023ca2  mov     r8, r12; lpMem
0x180023ca5  xor     edx, edx; dwFlags
0x180023ca7  mov     rcx, rax; hHeap
0x180023caa  call    cs:__imp_HeapFree
0x180023cb0  test    rsi, rsi
0x180023cb3  jnz     loc_180023C29
0x180023cb9  mov     [rdi], rsi
0x180023cbc  add     rdi, 8
0x180023cc0  cmp     rdi, r15
0x180023cc3  jnz     loc_180023C21
0x180023cc9  add     rsp, 28h
0x180023ccd  pop     r15
0x180023ccf  pop     r14
0x180023cd1  pop     r13
0x180023cd3  pop     r12
0x180023cd5  pop     rdi
0x180023cd6  pop     rsi
0x180023cd7  pop     rbp
0x180023cd8  pop     rbx
0x180023cd9  retn
```
