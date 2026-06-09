# ListVerifier::VerifyValue(char const *,ulong,ulong,ulong)

- ea: `0x18000b4f4`
- end: `0x18000b619`
- name: `?VerifyValue@ListVerifier@@QEAAJPEBDKKK@Z`
- size: `293`
- prototype: `__int64 __fastcall(ListVerifier *this, char *, unsigned int, char, char)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800099e0`
- `0x180009a50`
- `0x18000abd0`
- `0x18000ac20`

## callees

- `0x180001234`
- `0x180001274`
- `0x180002578`
- `0x18000adec`
- `0x18000b4f4`
- `0x18000dc00`

## pseudocode

```c
__int64 __fastcall ListVerifier::VerifyValue(ListVerifier *this, char *a2, unsigned int a3, char a4, char a5)
{
  __int64 v9; // rsi
  __int64 v10; // rdi
  unsigned int v11; // edx
  unsigned int v13; // eax
  unsigned int v14; // esi
  void *v15; // rax
  void *v16; // rbp
  const void *v17; // rdx

  if ( *((_DWORD *)this + 1) )
  {
    v9 = *((_QWORD *)this + 1);
    v10 = 0;
    while ( (unsigned int)HttpProcessor::Compare(
                            a2,
                            a3,
                            *(char *const *)(v9 + 24 * v10),
                            *(_DWORD *)(v9 + 24 * v10 + 8),
                            a4) )
    {
      v10 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v10 >= *((_DWORD *)this + 1) )
        goto LABEL_5;
    }
    if ( *(_DWORD *)(v9 + 24 * v10 + 16) && (a5 & 2) == 0 )
    {
      v11 = -805306343;
      goto LABEL_10;
    }
    *(_DWORD *)(v9 + 24 * v10 + 16) = 1;
    v13 = *((_DWORD *)this + 4);
    if ( *((_DWORD *)this + 5) != v13 )
      goto LABEL_20;
    if ( v13 )
    {
      if ( v13 > 0x7FFFFFFF )
        return 0;
      v14 = 2 * v13;
    }
    else
    {
      v14 = 4;
    }
    v15 = operator new(saturated_mul(v14, 4u));
    v16 = v15;
    if ( v15 )
    {
      v17 = (const void *)*((_QWORD *)this + 3);
      if ( v17 )
      {
        memcpy_0(v15, v17, 4LL * *((unsigned int *)this + 4));
        operator delete(*((void **)this + 3));
      }
      *((_DWORD *)this + 4) = v14;
      *((_QWORD *)this + 3) = v16;
LABEL_20:
      *(_DWORD *)(*((_QWORD *)this + 3) + 4LL * (unsigned int)(*((_DWORD *)this + 5))++) = v10;
    }
  }
  else
  {
LABEL_5:
    if ( (a5 & 1) != 0 )
    {
      v11 = -805306342;
LABEL_10:
      Trace::Error(-2089418750, v11, a3, a2);
      return 2205548546LL;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000b4f4  push    rbx
0x18000b4f6  push    rbp
0x18000b4f7  push    rsi
0x18000b4f8  push    rdi
0x18000b4f9  push    r12
0x18000b4fb  push    r14
0x18000b4fd  push    r15
0x18000b4ff  sub     rsp, 30h
0x18000b503  cmp     dword ptr [rcx+4], 0
0x18000b507  mov     r12d, r9d
0x18000b50a  mov     ebp, r8d
0x18000b50d  mov     r14, rdx
0x18000b510  mov     rbx, rcx
0x18000b513  jbe     short loc_18000B542
0x18000b515  mov     rsi, [rcx+8]
0x18000b519  xor     edi, edi
0x18000b51b  lea     r15, [rdi+rdi*2]
0x18000b51f  mov     dword ptr [rsp+68h+var_48], r12d; char
0x18000b524  mov     r9d, [rsi+r15*8+8]; unsigned int
0x18000b529  mov     edx, ebp; unsigned int
0x18000b52b  mov     r8, [rsi+r15*8]; char *
0x18000b52f  mov     rcx, r14; char *
0x18000b532  call    ?Compare@HttpProcessor@@SAHQEADK0KK@Z; HttpProcessor::Compare(char * const,ulong,char * const,ulong,ulong)
0x18000b537  test    eax, eax
0x18000b539  jz      short loc_18000B557
0x18000b53b  inc     edi
0x18000b53d  cmp     edi, [rbx+4]
0x18000b540  jb      short loc_18000B51B
0x18000b542  test    byte ptr [rsp+68h+arg_20], 1
0x18000b54a  jz      loc_18000B608
0x18000b550  mov     edx, 0D000001Ah
0x18000b555  jmp     short loc_18000B56E
0x18000b557  cmp     dword ptr [rsi+r15*8+10h], 0
0x18000b55d  jz      short loc_18000B587
0x18000b55f  test    byte ptr [rsp+68h+arg_20], 2
0x18000b567  jnz     short loc_18000B587
0x18000b569  mov     edx, 0D0000019h; unsigned int
0x18000b56e  mov     ebx, 83760002h
0x18000b573  mov     r8d, ebp
0x18000b576  mov     ecx, ebx; int
0x18000b578  mov     r9, r14
0x18000b57b  call    ?Error@Trace@@SAJJKZZ; Trace::Error(long,ulong,...)
0x18000b580  mov     eax, ebx
0x18000b582  jmp     loc_18000B60A
0x18000b587  mov     dword ptr [rsi+r15*8+10h], 1
0x18000b590  mov     eax, [rbx+10h]
0x18000b593  cmp     [rbx+14h], eax
0x18000b596  jnz     short loc_18000B5FB
0x18000b598  mov     edx, 4
0x18000b59d  test    eax, eax
0x18000b59f  jnz     short loc_18000B5A5
0x18000b5a1  mov     esi, edx
0x18000b5a3  jmp     short loc_18000B5AF
0x18000b5a5  cmp     eax, 7FFFFFFFh
0x18000b5aa  ja      short loc_18000B608
0x18000b5ac  lea     esi, [rax+rax]
0x18000b5af  mov     ecx, esi
0x18000b5b1  mov     rax, rdx
0x18000b5b4  mul     rcx
0x18000b5b7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b5be  cmovb   rax, rcx
0x18000b5c2  mov     rcx, rax; Size
0x18000b5c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b5ca  mov     rbp, rax
0x18000b5cd  test    rax, rax
0x18000b5d0  jz      short loc_18000B608
0x18000b5d2  mov     rdx, [rbx+18h]; Src
0x18000b5d6  test    rdx, rdx
0x18000b5d9  jz      short loc_18000B5F4
0x18000b5db  mov     r8d, [rbx+10h]
0x18000b5df  mov     rcx, rax; void *
0x18000b5e2  shl     r8, 2; Size
0x18000b5e6  call    memcpy_0
0x18000b5eb  mov     rcx, [rbx+18h]; Block
0x18000b5ef  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b5f4  mov     [rbx+10h], esi
0x18000b5f7  mov     [rbx+18h], rbp
0x18000b5fb  mov     ecx, [rbx+14h]
0x18000b5fe  mov     rax, [rbx+18h]
0x18000b602  mov     [rax+rcx*4], edi
0x18000b605  inc     dword ptr [rbx+14h]
0x18000b608  xor     eax, eax
0x18000b60a  add     rsp, 30h
0x18000b60e  pop     r15
0x18000b610  pop     r14
0x18000b612  pop     r12
0x18000b614  pop     rdi
0x18000b615  pop     rsi
0x18000b616  pop     rbp
0x18000b617  pop     rbx
0x18000b618  retn
```
