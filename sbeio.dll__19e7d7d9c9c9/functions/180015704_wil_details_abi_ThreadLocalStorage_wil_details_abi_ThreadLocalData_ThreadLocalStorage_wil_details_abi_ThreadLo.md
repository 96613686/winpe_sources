# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180015704`
- end: `0x1800157de`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001567c`

## callees

- `0x180015704`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001575f`
- `KERNEL32!HeapFree` at `0x180015790`
- `KERNEL32!HeapFree` at `0x1800157ae`
- `KERNEL32!HeapFree` at `0x18001575f`
- `KERNEL32!HeapFree` at `0x180015790`
- `KERNEL32!HeapFree` at `0x1800157ae`
- `KERNEL32!GetProcessHeap` at `0x180015751`
- `KERNEL32!GetProcessHeap` at `0x180015782`
- `KERNEL32!GetProcessHeap` at `0x1800157a0`
- `KERNEL32!GetProcessHeap` at `0x180015751`
- `KERNEL32!GetProcessHeap` at `0x180015782`
- `KERNEL32!GetProcessHeap` at `0x1800157a0`

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
0x180015704  push    rbx
0x180015706  push    rbp
0x180015707  push    rsi
0x180015708  push    rdi
0x180015709  push    r12
0x18001570b  push    r13
0x18001570d  push    r14
0x18001570f  push    r15
0x180015711  sub     rsp, 28h
0x180015715  lea     r15, [rcx+50h]
0x180015719  mov     rdi, rcx
0x18001571c  cmp     rcx, r15
0x18001571f  jz      loc_1800157CD
0x180015725  mov     rsi, [rdi]
0x180015728  jmp     loc_1800157B4
0x18001572d  mov     r13, rsi
0x180015730  mov     r12, rsi
0x180015733  mov     rsi, [rsi+8]
0x180015737  movzx   eax, word ptr [r13+30h]
0x18001573c  mov     rbp, [r13+28h]
0x180015740  lea     r14, [rax+rax*4]
0x180015744  shl     r14, 4
0x180015748  add     r14, rbp
0x18001574b  jmp     short loc_180015779
0x18001574d  mov     rbx, [rbp+40h]
0x180015751  call    cs:__imp_GetProcessHeap
0x180015757  mov     r8, rbx; lpMem
0x18001575a  xor     edx, edx; dwFlags
0x18001575c  mov     rcx, rax; hHeap
0x18001575f  call    cs:__imp_HeapFree
0x180015765  mov     qword ptr [rbp+40h], 0
0x18001576d  mov     qword ptr [rbp+48h], 0
0x180015775  add     rbp, 50h ; 'P'
0x180015779  cmp     rbp, r14
0x18001577c  jnz     short loc_18001574D
0x18001577e  mov     rbx, [r13+28h]
0x180015782  call    cs:__imp_GetProcessHeap
0x180015788  mov     r8, rbx; lpMem
0x18001578b  xor     edx, edx; dwFlags
0x18001578d  mov     rcx, rax; hHeap
0x180015790  call    cs:__imp_HeapFree
0x180015796  xor     eax, eax
0x180015798  mov     [r13+30h], eax
0x18001579c  mov     [r13+28h], rax
0x1800157a0  call    cs:__imp_GetProcessHeap
0x1800157a6  mov     r8, r12; lpMem
0x1800157a9  xor     edx, edx; dwFlags
0x1800157ab  mov     rcx, rax; hHeap
0x1800157ae  call    cs:__imp_HeapFree
0x1800157b4  test    rsi, rsi
0x1800157b7  jnz     loc_18001572D
0x1800157bd  mov     [rdi], rsi
0x1800157c0  add     rdi, 8
0x1800157c4  cmp     rdi, r15
0x1800157c7  jnz     loc_180015725
0x1800157cd  add     rsp, 28h
0x1800157d1  pop     r15
0x1800157d3  pop     r14
0x1800157d5  pop     r13
0x1800157d7  pop     r12
0x1800157d9  pop     rdi
0x1800157da  pop     rsi
0x1800157db  pop     rbp
0x1800157dc  pop     rbx
0x1800157dd  retn
```
