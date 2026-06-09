# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180015308`
- end: `0x1800153e2`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180015280`

## callees

- `0x180015308`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180015355`
- `KERNEL32!GetProcessHeap` at `0x180015386`
- `KERNEL32!GetProcessHeap` at `0x1800153a4`
- `KERNEL32!GetProcessHeap` at `0x180015355`
- `KERNEL32!GetProcessHeap` at `0x180015386`
- `KERNEL32!GetProcessHeap` at `0x1800153a4`
- `KERNEL32!HeapFree` at `0x180015363`
- `KERNEL32!HeapFree` at `0x180015394`
- `KERNEL32!HeapFree` at `0x1800153b2`
- `KERNEL32!HeapFree` at `0x180015363`
- `KERNEL32!HeapFree` at `0x180015394`
- `KERNEL32!HeapFree` at `0x1800153b2`

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
0x180015308  push    rbx
0x18001530a  push    rbp
0x18001530b  push    rsi
0x18001530c  push    rdi
0x18001530d  push    r12
0x18001530f  push    r13
0x180015311  push    r14
0x180015313  push    r15
0x180015315  sub     rsp, 28h
0x180015319  lea     r15, [rcx+50h]
0x18001531d  mov     rdi, rcx
0x180015320  cmp     rcx, r15
0x180015323  jz      loc_1800153D1
0x180015329  mov     rsi, [rdi]
0x18001532c  jmp     loc_1800153B8
0x180015331  mov     r13, rsi
0x180015334  mov     r12, rsi
0x180015337  mov     rsi, [rsi+8]
0x18001533b  movzx   eax, word ptr [r13+30h]
0x180015340  mov     rbp, [r13+28h]
0x180015344  lea     r14, [rax+rax*4]
0x180015348  shl     r14, 4
0x18001534c  add     r14, rbp
0x18001534f  jmp     short loc_18001537D
0x180015351  mov     rbx, [rbp+40h]
0x180015355  call    cs:__imp_GetProcessHeap
0x18001535b  mov     r8, rbx; lpMem
0x18001535e  xor     edx, edx; dwFlags
0x180015360  mov     rcx, rax; hHeap
0x180015363  call    cs:__imp_HeapFree
0x180015369  mov     qword ptr [rbp+40h], 0
0x180015371  mov     qword ptr [rbp+48h], 0
0x180015379  add     rbp, 50h ; 'P'
0x18001537d  cmp     rbp, r14
0x180015380  jnz     short loc_180015351
0x180015382  mov     rbx, [r13+28h]
0x180015386  call    cs:__imp_GetProcessHeap
0x18001538c  mov     r8, rbx; lpMem
0x18001538f  xor     edx, edx; dwFlags
0x180015391  mov     rcx, rax; hHeap
0x180015394  call    cs:__imp_HeapFree
0x18001539a  xor     eax, eax
0x18001539c  mov     [r13+30h], eax
0x1800153a0  mov     [r13+28h], rax
0x1800153a4  call    cs:__imp_GetProcessHeap
0x1800153aa  mov     r8, r12; lpMem
0x1800153ad  xor     edx, edx; dwFlags
0x1800153af  mov     rcx, rax; hHeap
0x1800153b2  call    cs:__imp_HeapFree
0x1800153b8  test    rsi, rsi
0x1800153bb  jnz     loc_180015331
0x1800153c1  mov     [rdi], rsi
0x1800153c4  add     rdi, 8
0x1800153c8  cmp     rdi, r15
0x1800153cb  jnz     loc_180015329
0x1800153d1  add     rsp, 28h
0x1800153d5  pop     r15
0x1800153d7  pop     r14
0x1800153d9  pop     r13
0x1800153db  pop     r12
0x1800153dd  pop     rdi
0x1800153de  pop     rsi
0x1800153df  pop     rbp
0x1800153e0  pop     rbx
0x1800153e1  retn
```
