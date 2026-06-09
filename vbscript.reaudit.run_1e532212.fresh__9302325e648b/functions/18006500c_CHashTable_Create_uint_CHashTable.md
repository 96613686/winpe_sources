# CHashTable::Create(uint,CHashTable * *)

- ea: `0x18006500c`
- end: `0x1800650f3`
- name: `?Create@CHashTable@@SAJIPEAPEAV1@@Z`
- size: `231`
- prototype: `__int64 __fastcall(unsigned int, struct CHashTable **)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800650fc`
- `0x180065470`
- `0x180065734`

## callees

- `0x180045490`
- `0x180064ecc`
- `0x18006500c`
- `0x18007670a`
- `0x180076746`

## import_xrefs

- `msvcrt!malloc` at `0x180065088`
- `msvcrt!malloc` at `0x1800650d0`
- `msvcrt!malloc` at `0x180065088`
- `msvcrt!malloc` at `0x1800650d0`

## pseudocode

```c
__int64 __fastcall CHashTable::Create(int a1, struct CHashTable **a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  double v6; // xmm6_8
  unsigned int v7; // eax
  size_t v8; // rdi
  void *v9; // rax
  unsigned int v10; // edx
  __int64 result; // rax
  size_t v12; // rdi
  void *v13; // rax

  v4 = operator new(0x20u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  v4[3] = 0;
  *(_DWORD *)v4 = 0;
  *((_DWORD *)v4 + 1) = a1;
  v6 = log_0((double)(a1 + 1));
  v7 = (1 << ((int)(v6 / log_0(2.0)) + 1)) - 1;
  v8 = 8LL * v7;
  *((_DWORD *)v5 + 2) = v7;
  v9 = malloc(v8);
  v5[2] = v9;
  if ( !v9 || (memset_0(v9, 0, v8), v12 = 16LL * *((unsigned int *)v5 + 1), v13 = malloc(v12), (v5[3] = v13) == 0) )
  {
    CHashTable::`scalar deleting destructor'((CHashTable *)v5, v10);
    return 2147942414LL;
  }
  memset_0(v13, 0, v12);
  result = 0;
  *a2 = (struct CHashTable *)v5;
  return result;
}

```

## disassembly

```asm
0x18006500c  mov     [rsp+arg_0], rbx
0x180065011  mov     [rsp+arg_8], rsi
0x180065016  push    rdi
0x180065017  sub     rsp, 30h
0x18006501b  mov     edi, ecx
0x18006501d  movaps  [rsp+38h+var_18], xmm6
0x180065022  mov     ecx, 20h ; ' '; Size
0x180065027  mov     rsi, rdx
0x18006502a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006502f  mov     rbx, rax
0x180065032  test    rax, rax
0x180065035  jz      short loc_18006509F
0x180065037  lea     edx, [rdi+1]
0x18006503a  mov     qword ptr [rax+18h], 0
0x180065042  xorps   xmm0, xmm0
0x180065045  mov     dword ptr [rax], 0
0x18006504b  cvtsi2sd xmm0, rdx; X
0x180065050  mov     [rax+4], edi
0x180065053  call    log_0
0x180065058  movaps  xmm6, xmm0
0x18006505b  movsd   xmm0, cs:__real@4000000000000000; X
0x180065063  call    log_0
0x180065068  divsd   xmm6, xmm0
0x18006506c  mov     eax, 1
0x180065071  cvttsd2si rcx, xmm6
0x180065076  add     ecx, eax
0x180065078  shl     eax, cl
0x18006507a  dec     eax
0x18006507c  mov     edi, eax
0x18006507e  shl     rdi, 3
0x180065082  mov     rcx, rdi; Size
0x180065085  mov     [rbx+8], eax
0x180065088  call    cs:__imp_malloc
0x18006508e  mov     [rbx+10h], rax
0x180065092  test    rax, rax
0x180065095  jnz     short loc_1800650B9
0x180065097  mov     rcx, rbx; this
0x18006509a  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x18006509f  mov     eax, 8007000Eh
0x1800650a4  mov     rbx, [rsp+38h+arg_0]
0x1800650a9  mov     rsi, [rsp+38h+arg_8]
0x1800650ae  movaps  xmm6, [rsp+38h+var_18]
0x1800650b3  add     rsp, 30h
0x1800650b7  pop     rdi
0x1800650b8  retn
0x1800650b9  mov     r8, rdi; Size
0x1800650bc  xor     edx, edx; Val
0x1800650be  mov     rcx, rax; void *
0x1800650c1  call    memset_0
0x1800650c6  mov     edi, [rbx+4]
0x1800650c9  shl     rdi, 4
0x1800650cd  mov     rcx, rdi; Size
0x1800650d0  call    cs:__imp_malloc
0x1800650d6  mov     [rbx+18h], rax
0x1800650da  test    rax, rax
0x1800650dd  jz      short loc_180065097
0x1800650df  mov     r8, rdi; Size
0x1800650e2  xor     edx, edx; Val
0x1800650e4  mov     rcx, rax; void *
0x1800650e7  call    memset_0
0x1800650ec  xor     eax, eax
0x1800650ee  mov     [rsi], rbx
0x1800650f1  jmp     short loc_1800650A4
```
