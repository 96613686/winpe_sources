# WamRegGlobal::ConstructFullPath(ushort const *,ulong,ushort const *,ushort * *)

- ea: `0x180004864`
- end: `0x180004941`
- name: `?ConstructFullPath@WamRegGlobal@@QEAAJPEBGK0PEAPEAG@Z`
- size: `221`
- prototype: `int(WamRegGlobal *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800021d0`
- `0x180002460`
- `0x1800029e0`
- `0x1800034b0`
- `0x180003720`
- `0x180003d80`

## callees

- `0x180001044`
- `0x180004864`
- `0x180006816`

## pseudocode

```c
__int64 __fastcall WamRegGlobal::ConstructFullPath(
        WamRegGlobal *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  __int64 v5; // rcx
  unsigned int v7; // ebx
  unsigned __int16 *v9; // r14
  __int64 v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rbp
  unsigned int v13; // eax
  void *v14; // rax
  unsigned int v15; // esi
  size_t v16; // rbx
  __int64 result; // rax

  v5 = a3 - 1;
  v7 = a3;
  v9 = 0;
  if ( a2[v5] == 92 || a2[v5] == 47 )
    v7 = a3 - 1;
  v10 = -1;
  do
    ++v10;
  while ( a4[v10] );
  if ( (_DWORD)v10 )
  {
    v11 = (unsigned int)(v10 - 1);
    if ( a4[v11] == 47 || a4[v11] == 92 )
      LODWORD(v10) = v10 - 1;
  }
  v12 = (unsigned int)v10 + v7;
  v13 = v12 + 1;
  if ( (int)v12 + 1 > v7
    && v13 > (unsigned int)v10
    && (v14 = operator new(saturated_mul(v13, 2u)), (v9 = (unsigned __int16 *)v14) != 0) )
  {
    v15 = 0;
    v16 = v7;
    memcpy_0(v14, a2, v16 * 2);
    memcpy_0(&v9[v16], a4, 2LL * (unsigned int)v10);
    v9[v12] = 0;
  }
  else
  {
    v15 = -2147024882;
  }
  result = v15;
  *a5 = v9;
  return result;
}

```

## disassembly

```asm
0x180004864  push    rbx
0x180004866  push    rbp
0x180004867  push    rsi
0x180004868  push    rdi
0x180004869  push    r12
0x18000486b  push    r13
0x18000486d  push    r14
0x18000486f  push    r15
0x180004871  sub     rsp, 28h
0x180004875  xor     r13d, r13d
0x180004878  lea     ecx, [r8-1]
0x18000487c  cmp     word ptr [rdx+rcx*2], 5Ch ; '\'
0x180004881  mov     r15, r9
0x180004884  mov     ebx, r8d
0x180004887  mov     r12, rdx
0x18000488a  mov     r14d, r13d
0x18000488d  jz      short loc_180004896
0x18000488f  cmp     word ptr [rdx+rcx*2], 2Fh ; '/'
0x180004894  jnz     short loc_180004898
0x180004896  mov     ebx, ecx
0x180004898  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000489c  mov     rdi, r8
0x18000489f  inc     rdi
0x1800048a2  cmp     [r9+rdi*2], r13w
0x1800048a7  jnz     short loc_18000489F
0x1800048a9  test    edi, edi
0x1800048ab  jz      short loc_1800048C2
0x1800048ad  lea     ecx, [rdi-1]
0x1800048b0  cmp     word ptr [r9+rcx*2], 2Fh ; '/'
0x1800048b6  jz      short loc_1800048C0
0x1800048b8  cmp     word ptr [r9+rcx*2], 5Ch ; '\'
0x1800048be  jnz     short loc_1800048C2
0x1800048c0  mov     edi, ecx
0x1800048c2  lea     ebp, [rdi+rbx]
0x1800048c5  lea     eax, [rbp+1]
0x1800048c8  cmp     eax, ebx
0x1800048ca  jbe     short loc_18000491E
0x1800048cc  cmp     eax, edi
0x1800048ce  jbe     short loc_18000491E
0x1800048d0  mov     ecx, eax
0x1800048d2  mov     eax, 2
0x1800048d7  mul     rcx
0x1800048da  cmovb   rax, r8
0x1800048de  mov     rcx, rax; Size
0x1800048e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800048e6  mov     r14, rax
0x1800048e9  test    rax, rax
0x1800048ec  jz      short loc_18000491E
0x1800048ee  mov     ecx, ebx
0x1800048f0  mov     rdx, r12; Src
0x1800048f3  mov     esi, r13d
0x1800048f6  lea     rbx, [rcx+rcx]
0x1800048fa  mov     rcx, rax; void *
0x1800048fd  mov     r8, rbx; Size
0x180004900  call    memcpy_0
0x180004905  mov     r8d, edi
0x180004908  lea     rcx, [rbx+r14]; void *
0x18000490c  add     r8, r8; Size
0x18000490f  mov     rdx, r15; Src
0x180004912  call    memcpy_0
0x180004917  mov     [r14+rbp*2], r13w
0x18000491c  jmp     short loc_180004923
0x18000491e  mov     esi, 8007000Eh
0x180004923  mov     rcx, [rsp+68h+arg_20]
0x18000492b  mov     eax, esi
0x18000492d  mov     [rcx], r14
0x180004930  add     rsp, 28h
0x180004934  pop     r15
0x180004936  pop     r14
0x180004938  pop     r13
0x18000493a  pop     r12
0x18000493c  pop     rdi
0x18000493d  pop     rsi
0x18000493e  pop     rbp
0x18000493f  pop     rbx
0x180004940  retn
```
