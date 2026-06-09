# NCoreLibrary::TString::Update(ushort const *)

- ea: `0x140012d4c`
- end: `0x140012e7e`
- name: `?Update@TString@NCoreLibrary@@QEAAJPEBG@Z`
- size: `306`
- prototype: `__int64 __fastcall(NCoreLibrary::TString *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x140012bf8`

## callees

- `0x140001b90`
- `0x140001b9c`
- `0x140012d4c`

## pseudocode

```c
__int64 __fastcall NCoreLibrary::TString::Update(void **this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // r14
  __int64 v4; // rdi
  unsigned __int64 v5; // rdi
  __int16 *v6; // rax
  __int16 *v7; // rsi
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int16 *v10; // rcx

  v2 = a2;
  if ( !a2 )
  {
    v8 = 0;
    if ( *this != &NCoreLibrary::TString::gszNullState && *this != word_14002174A )
      operator delete(*this);
    *this = &NCoreLibrary::TString::gszNullState;
    return v8;
  }
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = v4 + 1;
  v6 = (__int16 *)operator new[](saturated_mul(v5, 2u));
  v7 = v6;
  if ( v6 )
  {
    v8 = -2147024809;
    if ( !v5 )
      goto LABEL_14;
    if ( v5 <= 0x7FFFFFFF )
    {
      v9 = 2147483646;
      do
      {
        if ( !v9 )
          break;
        if ( !*v2 )
          break;
        *v6++ = *v2++;
        --v9;
        --v5;
      }
      while ( v5 );
      v10 = v6 - 1;
      if ( v5 )
        v10 = v6;
      v8 = v5 == 0 ? 0x8007007A : 0;
      *v10 = 0;
LABEL_14:
      if ( (v8 & 0x80000000) == 0 )
      {
        if ( *this != &NCoreLibrary::TString::gszNullState && *this != word_14002174A )
          operator delete(*this);
        *this = v7;
        v7 = 0;
        goto LABEL_23;
      }
      goto LABEL_21;
    }
    *v6 = 0;
  }
  else
  {
    v8 = -2147024882;
  }
LABEL_21:
  if ( v7 != (__int16 *)&NCoreLibrary::TString::gszNullState && v7 != word_14002174A )
LABEL_23:
    operator delete(v7);
  return v8;
}

```

## disassembly

```asm
0x140012d4c  push    rbx
0x140012d4e  push    rbp
0x140012d4f  push    rsi
0x140012d50  push    rdi
0x140012d51  push    r14
0x140012d53  push    r15
0x140012d55  sub     rsp, 28h
0x140012d59  xor     ebp, ebp
0x140012d5b  mov     r14, rdx
0x140012d5e  mov     r15, rcx
0x140012d61  test    rdx, rdx
0x140012d64  jz      loc_140012E4A
0x140012d6a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140012d6e  mov     rdi, rcx
0x140012d71  inc     rdi
0x140012d74  cmp     [rdx+rdi*2], bp
0x140012d78  jnz     short loc_140012D71
0x140012d7a  inc     rdi
0x140012d7d  mov     eax, 2
0x140012d82  mul     rdi
0x140012d85  cmovb   rax, rcx
0x140012d89  mov     rcx, rax; unsigned __int64
0x140012d8c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140012d91  mov     rsi, rax
0x140012d94  test    rax, rax
0x140012d97  jz      loc_140012E23
0x140012d9d  mov     ebx, 80070057h
0x140012da2  test    rdi, rdi
0x140012da5  jz      short loc_140012DF2
0x140012da7  cmp     rdi, 7FFFFFFFh
0x140012dae  ja      short loc_140012E1E
0x140012db0  mov     ecx, 7FFFFFFEh
0x140012db5  test    rcx, rcx
0x140012db8  jz      short loc_140012DD7
0x140012dba  movzx   edx, word ptr [r14]
0x140012dbe  test    dx, dx
0x140012dc1  jz      short loc_140012DD7
0x140012dc3  mov     [rax], dx
0x140012dc6  add     r14, 2
0x140012dca  add     rax, 2
0x140012dce  dec     rcx
0x140012dd1  sub     rdi, 1
0x140012dd5  jnz     short loc_140012DB5
0x140012dd7  test    rdi, rdi
0x140012dda  lea     rcx, [rax-2]
0x140012dde  cmovnz  rcx, rax
0x140012de2  neg     rdi
0x140012de5  sbb     ebx, ebx
0x140012de7  not     ebx
0x140012de9  and     ebx, 8007007Ah
0x140012def  mov     [rcx], bp
0x140012df2  test    ebx, ebx
0x140012df4  js      short loc_140012E28
0x140012df6  lea     rdi, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x140012dfd  cmp     [r15], rdi
0x140012e00  jz      short loc_140012E16
0x140012e02  lea     rax, word_14002174A
0x140012e09  cmp     [r15], rax
0x140012e0c  jz      short loc_140012E16
0x140012e0e  mov     rcx, [r15]; Block
0x140012e11  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140012e16  mov     [r15], rsi
0x140012e19  mov     rsi, rbp
0x140012e1c  jmp     short loc_140012E40
0x140012e1e  mov     [rax], bp
0x140012e21  jmp     short loc_140012E28
0x140012e23  mov     ebx, 8007000Eh
0x140012e28  lea     rdi, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x140012e2f  cmp     rsi, rdi
0x140012e32  jz      short loc_140012E6F
0x140012e34  lea     rax, word_14002174A
0x140012e3b  cmp     rsi, rax
0x140012e3e  jz      short loc_140012E6F
0x140012e40  mov     rcx, rsi; Block
0x140012e43  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140012e48  jmp     short loc_140012E6F
0x140012e4a  lea     rdi, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x140012e51  mov     ebx, ebp
0x140012e53  cmp     [rcx], rdi
0x140012e56  jz      short loc_140012E6C
0x140012e58  lea     rax, word_14002174A
0x140012e5f  cmp     [rcx], rax
0x140012e62  jz      short loc_140012E6C
0x140012e64  mov     rcx, [rcx]; Block
0x140012e67  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140012e6c  mov     [r15], rdi
0x140012e6f  mov     eax, ebx
0x140012e71  add     rsp, 28h
0x140012e75  pop     r15
0x140012e77  pop     r14
0x140012e79  pop     rdi
0x140012e7a  pop     rsi
0x140012e7b  pop     rbp
0x140012e7c  pop     rbx
0x140012e7d  retn
```
