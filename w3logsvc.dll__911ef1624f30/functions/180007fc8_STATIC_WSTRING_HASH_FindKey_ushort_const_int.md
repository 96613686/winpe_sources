# STATIC_WSTRING_HASH::FindKey(ushort const *,int)

- ea: `0x180007fc8`
- end: `0x1800080c2`
- name: `?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z`
- size: `250`
- prototype: `struct STATIC_WSTRING_HASH_RECORD *__fastcall(STATIC_WSTRING_HASH *this, wchar_t *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007e20`
- `0x180008c90`

## callees

- `0x180007fc8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000807d`
- `msvcrt!_wcsicmp` at `0x18000807d`

## pseudocode

```c
struct STATIC_WSTRING_HASH_RECORD *__fastcall STATIC_WSTRING_HASH::FindKey(
        STATIC_WSTRING_HASH *this,
        wchar_t *a2,
        int a3)
{
  wchar_t v3; // ax
  const wchar_t *v5; // rdi
  __int64 v7; // rbp
  unsigned int v8; // r9d
  const unsigned __int16 *v9; // rcx
  wchar_t v10; // cx
  __int64 v11; // r14
  __int64 i; // rbx
  const wchar_t *v13; // rdx
  const wchar_t *v14; // rax
  signed __int64 v15; // rdx
  int v16; // r8d
  int v17; // ecx
  bool v18; // zf
  __int64 v19; // rax

  v3 = *a2;
  v5 = a2;
  v7 = 0;
  v8 = 0;
  if ( *((_DWORD *)this + 262) )
  {
    if ( v3 )
    {
      v9 = a2;
      do
      {
        ++v9;
        v8 = v3 + 101 * v8;
        v3 = *v9;
      }
      while ( *v9 );
    }
  }
  else
  {
    while ( v3 )
    {
      v10 = v3;
      v3 = *++a2;
      v8 = (v10 & 0xFFDF) + 101 * v8;
    }
  }
  v11 = v8 % 0x83;
  for ( i = *((_QWORD *)this + v11); i; i = *(_QWORD *)(i + 8) )
  {
    v13 = *(const wchar_t **)i;
    if ( *((_DWORD *)this + 262) )
    {
      v14 = v5;
      v15 = (char *)v13 - (char *)v5;
      do
      {
        v16 = *(const wchar_t *)((char *)v14 + v15);
        v17 = *v14 - v16;
        if ( v17 )
          break;
        ++v14;
      }
      while ( v16 );
      v18 = v17 == 0;
    }
    else
    {
      v18 = _wcsicmp(v5, v13) == 0;
    }
    if ( v18 )
      break;
    v7 = i;
  }
  if ( a3 && i )
  {
    v19 = *(_QWORD *)(i + 8);
    if ( v7 )
      *(_QWORD *)(v7 + 8) = v19;
    else
      *((_QWORD *)this + v11) = v19;
  }
  return (struct STATIC_WSTRING_HASH_RECORD *)i;
}

```

## disassembly

```asm
0x180007fc8  push    rbx
0x180007fca  push    rbp
0x180007fcb  push    rsi
0x180007fcc  push    rdi
0x180007fcd  push    r12
0x180007fcf  push    r14
0x180007fd1  push    r15
0x180007fd3  sub     rsp, 20h
0x180007fd7  movzx   eax, word ptr [rdx]
0x180007fda  xor     r12d, r12d
0x180007fdd  mov     r15d, r8d
0x180007fe0  mov     rdi, rdx
0x180007fe3  mov     rsi, rcx
0x180007fe6  mov     ebp, r12d
0x180007fe9  mov     r9d, r12d
0x180007fec  cmp     [rcx+418h], r12d
0x180007ff3  jz      short loc_18000802C
0x180007ff5  test    ax, ax
0x180007ff8  jz      short loc_180008031
0x180007ffa  mov     rcx, rdx
0x180007ffd  imul    r9d, 65h ; 'e'
0x180008001  lea     rcx, [rcx+2]
0x180008005  movzx   eax, ax
0x180008008  add     r9d, eax
0x18000800b  movzx   eax, word ptr [rcx]
0x18000800e  test    ax, ax
0x180008011  jnz     short loc_180007FFD
0x180008013  jmp     short loc_180008031
0x180008015  movzx   ecx, ax
0x180008018  lea     rdx, [rdx+2]
0x18000801c  movzx   eax, word ptr [rdx]
0x18000801f  and     ecx, 0FFDFh
0x180008025  imul    r9d, 65h ; 'e'
0x180008029  add     r9d, ecx
0x18000802c  test    ax, ax
0x18000802f  jnz     short loc_180008015
0x180008031  mov     eax, 0FA232CF3h
0x180008036  mul     r9d
0x180008039  shr     edx, 7
0x18000803c  imul    eax, edx, 83h
0x180008042  sub     r9d, eax
0x180008045  mov     r14d, r9d
0x180008048  mov     rbx, [rsi+r9*8]
0x18000804c  jmp     short loc_18000808E
0x18000804e  mov     rdx, [rbx]; String2
0x180008051  cmp     [rsi+418h], r12d
0x180008058  jz      short loc_18000807A
0x18000805a  mov     rax, rdi
0x18000805d  sub     rdx, rdi
0x180008060  movzx   ecx, word ptr [rax]
0x180008063  movzx   r8d, word ptr [rax+rdx]
0x180008068  sub     ecx, r8d
0x18000806b  jnz     short loc_180008076
0x18000806d  add     rax, 2
0x180008071  test    r8d, r8d
0x180008074  jnz     short loc_180008060
0x180008076  test    ecx, ecx
0x180008078  jmp     short loc_180008085
0x18000807a  mov     rcx, rdi; String1
0x18000807d  call    cs:__imp__wcsicmp
0x180008083  test    eax, eax
0x180008085  jz      short loc_180008093
0x180008087  mov     rbp, rbx
0x18000808a  mov     rbx, [rbx+8]
0x18000808e  test    rbx, rbx
0x180008091  jnz     short loc_18000804E
0x180008093  test    r15d, r15d
0x180008096  jz      short loc_1800080B0
0x180008098  test    rbx, rbx
0x18000809b  jz      short loc_1800080B0
0x18000809d  mov     rax, [rbx+8]
0x1800080a1  test    rbp, rbp
0x1800080a4  jz      short loc_1800080AC
0x1800080a6  mov     [rbp+8], rax
0x1800080aa  jmp     short loc_1800080B0
0x1800080ac  mov     [rsi+r14*8], rax
0x1800080b0  mov     rax, rbx
0x1800080b3  add     rsp, 20h
0x1800080b7  pop     r15
0x1800080b9  pop     r14
0x1800080bb  pop     r12
0x1800080bd  pop     rdi
0x1800080be  pop     rsi
0x1800080bf  pop     rbp
0x1800080c0  pop     rbx
0x1800080c1  retn
```
