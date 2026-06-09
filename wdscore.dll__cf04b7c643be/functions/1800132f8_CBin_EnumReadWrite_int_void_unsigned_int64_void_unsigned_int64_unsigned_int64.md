# CBin::EnumReadWrite(int,void *,unsigned __int64,void * &,unsigned __int64 &,unsigned __int64)

- ea: `0x1800132f8`
- end: `0x1800133d9`
- name: `?EnumReadWrite@CBin@@QEAAHHPEAX_KAEAPEAXAEA_K1@Z`
- size: `225`
- prototype: `__int64 __usercall@<rax>(CBin *__hidden this@<rcx>, int@<edx>, void *@<r8>, unsigned __int64@<r9>, void **, unsigned __int64 *, unsigned __int64)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180011264`
- `0x180011914`
- `0x180011b88`
- `0x180012704`
- `0x1800128dc`
- `0x180012e78`
- `0x1800133e0`
- `0x180013b28`
- `0x180013fb4`
- `0x1800142c8`

## callees

- `0x1800132f8`
- `0x180013738`
- `0x1800274c6`

## pseudocode

```c
__int64 __fastcall CBin::EnumReadWrite(
        CBin *this,
        int a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        void **a5,
        unsigned __int64 *a6,
        unsigned __int64 a7)
{
  unsigned __int64 v8; // r12
  BOOL v10; // r15d
  __int64 result; // rax
  unsigned __int64 v13; // rax
  size_t v14; // rbx
  const void *v15; // rdx
  void *v16; // rcx
  int v17; // [rsp+78h] [rbp+10h]

  v17 = a2;
  v8 = a3;
  v10 = !*a5 || !*a6;
  while ( a4 )
  {
    if ( v10 )
    {
      result = (__int64)CBin::EnumView(this, a6, a3);
      *a5 = (void *)result;
      if ( !result )
        return result;
      a2 = v17;
    }
    else
    {
      v10 = 1;
    }
    if ( a7 )
    {
      v13 = *a6;
      if ( *a6 >= a7 )
      {
        *a6 = v13 - a7;
        *a5 = (char *)*a5 + a7;
        a7 = 0;
        goto LABEL_14;
      }
      a7 -= v13;
    }
    else
    {
LABEL_14:
      v14 = a4;
      if ( *a6 < a4 )
        v14 = *a6;
      if ( a2 )
      {
        v15 = *a5;
        v16 = (void *)v8;
      }
      else
      {
        v16 = *a5;
        v15 = (const void *)v8;
      }
      memcpy_0(v16, v15, v14);
      *a5 = (char *)*a5 + v14;
      v8 += v14;
      *a6 -= v14;
      a2 = v17;
      a4 -= v14;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800132f8  mov     [rsp+arg_8], edx
0x1800132fc  push    rbx
0x1800132fd  push    rbp
0x1800132fe  push    rsi
0x1800132ff  push    rdi
0x180013300  push    r12
0x180013302  push    r13
0x180013304  push    r14
0x180013306  push    r15
0x180013308  sub     rsp, 28h
0x18001330c  mov     r14, [rsp+68h+arg_20]
0x180013314  mov     rbp, r9
0x180013317  mov     rsi, [rsp+68h+arg_28]
0x18001331f  mov     r12, r8
0x180013322  mov     r13, rcx
0x180013325  cmp     qword ptr [r14], 0
0x180013329  jz      short loc_180013336
0x18001332b  cmp     qword ptr [rsi], 0
0x18001332f  jz      short loc_180013336
0x180013331  xor     r15d, r15d
0x180013334  jmp     short loc_18001333C
0x180013336  mov     r15d, 1
0x18001333c  mov     rdi, [rsp+68h+arg_30]
0x180013344  test    rbp, rbp
0x180013347  jz      short loc_1800133C2
0x180013349  test    r15d, r15d
0x18001334c  jz      short loc_180013367
0x18001334e  mov     rdx, rsi; unsigned __int64 *
0x180013351  mov     rcx, r13; this
0x180013354  call    ?EnumView@CBin@@QEAAPEAXAEA_K_K@Z; CBin::EnumView(unsigned __int64 &,unsigned __int64)
0x180013359  mov     [r14], rax
0x18001335c  test    rax, rax
0x18001335f  jz      short loc_1800133C0
0x180013361  mov     edx, [rsp+68h+arg_8]
0x180013365  jmp     short loc_18001336D
0x180013367  mov     r15d, 1
0x18001336d  test    rdi, rdi
0x180013370  jz      short loc_18001338A
0x180013372  mov     rax, [rsi]
0x180013375  cmp     rax, rdi
0x180013378  jnb     short loc_18001337F
0x18001337a  sub     rdi, rax
0x18001337d  jmp     short loc_180013344
0x18001337f  sub     rax, rdi
0x180013382  mov     [rsi], rax
0x180013385  add     [r14], rdi
0x180013388  xor     edi, edi
0x18001338a  cmp     [rsi], rbp
0x18001338d  mov     rbx, rbp
0x180013390  cmovb   rbx, [rsi]
0x180013394  mov     r8, rbx; Size
0x180013397  test    edx, edx
0x180013399  jz      short loc_1800133A3
0x18001339b  mov     rdx, [r14]
0x18001339e  mov     rcx, r12
0x1800133a1  jmp     short loc_1800133A9
0x1800133a3  mov     rcx, [r14]; void *
0x1800133a6  mov     rdx, r12; Src
0x1800133a9  call    memcpy_0
0x1800133ae  add     [r14], rbx
0x1800133b1  add     r12, rbx
0x1800133b4  sub     [rsi], rbx
0x1800133b7  mov     edx, [rsp+68h+arg_8]
0x1800133bb  sub     rbp, rbx
0x1800133be  jmp     short loc_180013344
0x1800133c0  jmp     short loc_1800133C7
0x1800133c2  mov     eax, 1
0x1800133c7  add     rsp, 28h
0x1800133cb  pop     r15
0x1800133cd  pop     r14
0x1800133cf  pop     r13
0x1800133d1  pop     r12
0x1800133d3  pop     rdi
0x1800133d4  pop     rsi
0x1800133d5  pop     rbp
0x1800133d6  pop     rbx
0x1800133d7  retn
```
