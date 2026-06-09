# RtlStringCchCatExW

- ea: `0x180001ec0`
- end: `0x1800020cf`
- name: `RtlStringCchCatExW`
- size: `527`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int64, __int64 *, __int64, char, int)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180001190`
- `0x180004180`
- `0x1800126cc`
- `0x180014a84`
- `0x1800156c0`

## callees

- `0x180001ec0`
- `0x180002750`
- `0x1800132c0`
- `0x18001893e`

## pseudocode

```c
__int64 __fastcall RtlStringCchCatExW(_WORD *a1, unsigned __int64 a2, __int64 *a3, __int64 a4, char a5, int a6)
{
  int v6; // r15d
  unsigned __int64 v8; // r8
  __int64 v11; // r11
  int v12; // ebp
  unsigned __int64 v13; // rcx
  _WORD *v14; // rax
  unsigned int v15; // ebx
  unsigned __int64 v17; // r10
  __int64 v18; // r9
  unsigned __int64 v19; // rdx
  _WORD *v20; // rax
  _WORD *v21; // rcx
  __int64 v22; // r11
  __int64 *v23; // rax
  __int64 v24; // r10
  bool v25; // cf
  unsigned int v26; // eax
  unsigned __int64 v27; // [rsp+78h] [rbp+20h] BYREF

  v6 = a6;
  v8 = 0;
  v27 = 0;
  v11 = 2147483646;
  v12 = a6 & 0x100;
  if ( (a6 & 0x100) != 0 )
  {
    if ( (a1 || !a2) && a2 <= 0x7FFFFFFF )
    {
      v15 = 0;
      if ( a2 )
      {
        v26 = RtlStringLengthWorkerW(a1, a2, &v27);
        v8 = v27;
        v15 = v26;
      }
      goto LABEL_8;
    }
LABEL_6:
    v15 = -1073741811;
    goto LABEL_8;
  }
  if ( a2 - 1 > 0x7FFFFFFE )
    goto LABEL_6;
  v13 = a2;
  v14 = a1;
  while ( *v14 )
  {
    ++v14;
    if ( !--v13 )
      goto LABEL_6;
  }
  v8 = a2 - v13;
  v15 = 0;
LABEL_8:
  if ( (v15 & 0x80000000) != 0 )
    return v15;
  v17 = a2 - v8;
  if ( v12 )
  {
    v23 = &qword_18001C3B0;
    if ( a3 )
      v23 = a3;
    a3 = v23;
  }
  if ( (v6 & 0xFFFFE000) != 0 )
  {
    v15 = -1073741811;
  }
  else if ( v17 <= 1 )
  {
    v15 = 0;
    if ( !*(_WORD *)a3 )
      return v15;
    v15 = -2147483643;
    if ( !a1 )
      v15 = -1073741811;
  }
  else
  {
    v18 = 0;
    v19 = a2 - v8;
    v20 = &a1[v8];
    do
    {
      if ( !v11 )
        break;
      if ( !*(_WORD *)a3 )
        break;
      *v20 = *(_WORD *)a3;
      a3 = (__int64 *)((char *)a3 + 2);
      ++v20;
      --v11;
      ++v18;
      --v19;
    }
    while ( v19 );
    v21 = v20 - 1;
    v22 = v18 - 1;
    v15 = -2147483643;
    if ( v19 )
    {
      v21 = v20;
      v22 = v18;
      v15 = 0;
    }
    *v21 = 0;
    if ( v19 )
    {
      if ( (v6 & 0x200) != 0 )
      {
        v25 = v17 == v22;
        v24 = v17 - v22;
        if ( !v25 && v24 != 1 && (unsigned __int64)(2 * v24) > 2 )
          memset_0(&a1[v8 + 1 + v22], (unsigned __int8)v6, 2 * v24 - 2);
      }
      return v15;
    }
  }
  if ( (v6 & 0x1C00) != 0 && a2 )
    RtlStringExHandleOtherFlagsW(a1, 2 * a2, v8, &a5, &v27, v6);
  return v15;
}

```

## disassembly

```asm
0x180001ec0  mov     [rsp+arg_8], rbx
0x180001ec5  mov     [rsp+arg_10], rbp
0x180001eca  mov     [rsp+arg_18], r9
0x180001ecf  push    rsi
0x180001ed0  push    r12
0x180001ed2  push    r13
0x180001ed4  push    r14
0x180001ed6  push    r15
0x180001ed8  sub     rsp, 30h
0x180001edc  mov     r15d, [rsp+58h+arg_28]
0x180001ee4  mov     rsi, r8
0x180001ee7  xor     r8d, r8d
0x180001eea  mov     ebp, r15d
0x180001eed  mov     [rsp+58h+arg_18], r8
0x180001ef2  mov     r14, rdx
0x180001ef5  mov     r12, rcx
0x180001ef8  mov     r11d, 7FFFFFFEh
0x180001efe  mov     r13d, 0C000000Dh
0x180001f04  and     ebp, 100h
0x180001f0a  jnz     loc_180002058
0x180001f10  lea     rax, [rdx-1]
0x180001f14  cmp     rax, r11
0x180001f17  ja      short loc_180001F30
0x180001f19  mov     rcx, rdx
0x180001f1c  mov     rax, r12
0x180001f1f  nop
0x180001f20  cmp     [rax], r8w
0x180001f24  jz      short loc_180001F35
0x180001f26  add     rax, 2
0x180001f2a  sub     rcx, 1
0x180001f2e  jnz     short loc_180001F20
0x180001f30  mov     ebx, r13d
0x180001f33  jmp     short loc_180001F3D
0x180001f35  mov     r8, r14
0x180001f38  sub     r8, rcx
0x180001f3b  xor     ebx, ebx
0x180001f3d  test    ebx, ebx
0x180001f3f  jns     short loc_180001F5B
0x180001f41  mov     rbp, [rsp+58h+arg_10]
0x180001f46  mov     eax, ebx
0x180001f48  mov     rbx, [rsp+58h+arg_8]
0x180001f4d  add     rsp, 30h
0x180001f51  pop     r15
0x180001f53  pop     r14
0x180001f55  pop     r13
0x180001f57  pop     r12
0x180001f59  pop     rsi
0x180001f5a  retn
0x180001f5b  mov     r10, r14
0x180001f5e  mov     [rsp+58h+arg_0], rdi
0x180001f63  sub     r10, r8
0x180001f66  lea     rdi, [r12+r8*2]
0x180001f6a  test    ebp, ebp
0x180001f6c  jnz     loc_180001FF0
0x180001f72  test    r15d, 0FFFFE000h
0x180001f79  jnz     loc_180002075
0x180001f7f  cmp     r10, 1
0x180001f83  jbe     loc_18000207A
0x180001f89  xor     r9d, r9d
0x180001f8c  mov     rdx, r10
0x180001f8f  mov     rax, rdi
0x180001f92  test    r11, r11
0x180001f95  jz      short loc_180001FB6
0x180001f97  movzx   ecx, word ptr [rsi]
0x180001f9a  test    cx, cx
0x180001f9d  jz      short loc_180001FB6
0x180001f9f  mov     [rax], cx
0x180001fa2  add     rsi, 2
0x180001fa6  add     rax, 2
0x180001faa  dec     r11
0x180001fad  inc     r9
0x180001fb0  sub     rdx, 1
0x180001fb4  jnz     short loc_180001F92
0x180001fb6  test    rdx, rdx
0x180001fb9  lea     rcx, [rax-2]
0x180001fbd  lea     r11, [r9-1]
0x180001fc1  mov     ebx, 80000005h
0x180001fc6  cmovnz  rcx, rax
0x180001fca  cmovnz  r11, r9
0x180001fce  xor     eax, eax
0x180001fd0  test    rdx, rdx
0x180001fd3  cmovnz  ebx, eax
0x180001fd6  mov     [rcx], ax
0x180001fd9  jz      loc_180002091
0x180001fdf  bt      r15d, 9
0x180001fe4  jb      short loc_180002006
0x180001fe6  mov     rdi, [rsp+58h+arg_0]
0x180001feb  jmp     loc_180001F41
0x180001ff0  test    rsi, rsi
0x180001ff3  lea     rax, qword_18001C3B0
0x180001ffa  cmovnz  rax, rsi
0x180001ffe  mov     rsi, rax
0x180002001  jmp     loc_180001F72
0x180002006  sub     r10, r11
0x180002009  cmp     r10, 1
0x18000200d  jbe     short loc_180001FE6
0x18000200f  lea     r8, [r10+r10]
0x180002013  cmp     r8, 2
0x180002017  jbe     short loc_180001FE6
0x180002019  inc     r11
0x18000201c  movzx   edx, r15b; Val
0x180002020  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180002024  lea     rcx, [rdi+r11*2]; void *
0x180002028  call    memset_0
0x18000202d  mov     rdi, [rsp+58h+arg_0]
0x180002032  jmp     loc_180001F41
0x180002037  xor     ebx, ebx
0x180002039  test    r14, r14
0x18000203c  jz      loc_180001F3D
0x180002042  lea     r8, [rsp+58h+arg_18]
0x180002047  call    RtlStringLengthWorkerW
0x18000204c  mov     r8, [rsp+58h+arg_18]
0x180002051  mov     ebx, eax
0x180002053  jmp     loc_180001F3D
0x180002058  test    r12, r12
0x18000205b  jnz     short loc_180002066
0x18000205d  test    r14, r14
0x180002060  jnz     loc_180001F30
0x180002066  cmp     r14, 7FFFFFFFh
0x18000206d  ja      loc_180001F30
0x180002073  jmp     short loc_180002037
0x180002075  mov     ebx, r13d
0x180002078  jmp     short loc_180002091
0x18000207a  xor     ebx, ebx
0x18000207c  cmp     [rsi], bx
0x18000207f  jz      loc_180001FE6
0x180002085  test    r12, r12
0x180002088  mov     ebx, 80000005h
0x18000208d  cmovz   ebx, r13d
0x180002091  test    r15d, 1C00h
0x180002098  jz      loc_180001FE6
0x18000209e  test    r14, r14
0x1800020a1  jz      loc_180001FE6
0x1800020a7  lea     rax, [rsp+58h+arg_18]
0x1800020ac  mov     [rsp+58h+var_30], r15d
0x1800020b1  lea     rdx, [r14+r14]
0x1800020b5  mov     [rsp+58h+var_38], rax
0x1800020ba  lea     r9, [rsp+58h+arg_20]
0x1800020c2  mov     rcx, r12
0x1800020c5  call    RtlStringExHandleOtherFlagsW
0x1800020ca  jmp     loc_180001FE6
```
