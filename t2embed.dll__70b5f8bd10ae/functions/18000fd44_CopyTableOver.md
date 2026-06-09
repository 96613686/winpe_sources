# CopyTableOver

- ea: `0x18000fd44`
- end: `0x18000fe86`
- name: `CopyTableOver`
- size: `322`
- prototype: ``
- caller_count: `14`
- callee_count: `10`
- tags: ``

## callers

- `0x18000ee80`
- `0x180010448`
- `0x1800110d0`
- `0x1800119f8`
- `0x180012a18`
- `0x18001be6c`
- `0x18001d5f8`
- `0x1800281d0`
- `0x1800285cc`
- `0x180028c2c`
- `0x180028dfc`
- `0x180028f78`
- `0x18002912c`
- `0x180029228`

## callees

- `0x18000edd4`
- `0x18000fd44`
- `0x180011640`
- `0x180012020`
- `0x1800134b4`
- `0x180013514`
- `0x18001569c`
- `0x180016438`
- `0x180017eb0`
- `0x18002a590`

## pseudocode

```c
__int64 __fastcall CopyTableOver(_QWORD *a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  unsigned int TTDirectory; // r13d
  unsigned int v9; // r15d
  unsigned int v10; // edi
  __int64 result; // rax
  unsigned int v12; // ebx
  unsigned __int16 Bytes; // dx
  _WORD v14[2]; // [rsp+30h] [rbp-68h] BYREF
  unsigned int v15; // [rsp+34h] [rbp-64h] BYREF
  __int128 v16; // [rsp+38h] [rbp-60h] BYREF

  v15 = 0;
  v14[0] = 0;
  v16 = 0;
  TTDirectory = GetTTDirectory(a1, a3, &v16);
  if ( !TTDirectory )
    return 1006;
  v9 = TTTableOffset(a2, a3);
  v10 = TTTableLength(a2, a3);
  if ( !v9 )
    return 1006;
  result = ZeroLongWordAlign(a1, (unsigned int)*a4, &v15);
  if ( (_WORD)result )
    return result;
  v12 = v15;
  *((_QWORD *)&v16 + 1) = __PAIR64__(v10, v15);
  if ( !v10 )
    goto LABEL_8;
  result = CheckInOffset(a2, v9, v10);
  if ( !(_WORD)result )
  {
    result = CheckOutOffset(a1, v12);
    if ( !(_WORD)result )
    {
      Bytes = ReadBytes(a2, *a1 + v12, v9, v10);
      if ( Bytes )
        return Bytes;
LABEL_8:
      Bytes = WriteGeneric((__int64)a1, (__int64)&v16, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, TTDirectory, v14);
      if ( !Bytes )
        *a4 = v10 + v12;
      return Bytes;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000fd44  push    rbx
0x18000fd46  push    rbp
0x18000fd47  push    rsi
0x18000fd48  push    rdi
0x18000fd49  push    r12
0x18000fd4b  push    r13
0x18000fd4d  push    r14
0x18000fd4f  push    r15
0x18000fd51  sub     rsp, 58h
0x18000fd55  mov     rax, cs:__security_cookie
0x18000fd5c  xor     rax, rsp
0x18000fd5f  mov     [rsp+98h+var_50], rax
0x18000fd64  mov     rbx, r8
0x18000fd67  mov     r14, rdx
0x18000fd6a  xor     ebp, ebp
0x18000fd6c  lea     r8, [rsp+98h+var_60]
0x18000fd71  xorps   xmm0, xmm0
0x18000fd74  mov     [rsp+98h+var_64], ebp
0x18000fd78  mov     rdx, rbx
0x18000fd7b  mov     [rsp+98h+var_68], bp
0x18000fd80  mov     r12, r9
0x18000fd83  mov     rsi, rcx
0x18000fd86  movups  [rsp+98h+var_60], xmm0
0x18000fd8b  call    GetTTDirectory
0x18000fd90  mov     r13d, eax
0x18000fd93  test    eax, eax
0x18000fd95  jz      loc_18000FE63
0x18000fd9b  mov     rdx, rbx
0x18000fd9e  mov     rcx, r14
0x18000fda1  call    TTTableOffset
0x18000fda6  mov     rdx, rbx
0x18000fda9  mov     rcx, r14
0x18000fdac  mov     r15d, eax
0x18000fdaf  call    TTTableLength
0x18000fdb4  mov     edi, eax
0x18000fdb6  test    r15d, r15d
0x18000fdb9  jz      loc_18000FE63
0x18000fdbf  mov     edx, [r12]
0x18000fdc3  lea     r8, [rsp+98h+var_64]
0x18000fdc8  mov     rcx, rsi
0x18000fdcb  call    ZeroLongWordAlign
0x18000fdd0  test    ax, ax
0x18000fdd3  jnz     loc_18000FE68
0x18000fdd9  mov     ebx, [rsp+98h+var_64]
0x18000fddd  mov     dword ptr [rsp+98h+var_60+8], ebx
0x18000fde1  mov     dword ptr [rsp+98h+var_60+0Ch], edi
0x18000fde5  test    edi, edi
0x18000fde7  jz      short loc_18000FE26
0x18000fde9  mov     r8d, edi
0x18000fdec  mov     edx, r15d
0x18000fdef  mov     rcx, r14
0x18000fdf2  call    CheckInOffset
0x18000fdf7  test    ax, ax
0x18000fdfa  jnz     short loc_18000FE68
0x18000fdfc  mov     edx, ebx
0x18000fdfe  mov     rcx, rsi
0x18000fe01  call    CheckOutOffset
0x18000fe06  test    ax, ax
0x18000fe09  jnz     short loc_18000FE68
0x18000fe0b  mov     edx, ebx
0x18000fe0d  mov     r9d, edi
0x18000fe10  add     rdx, [rsi]
0x18000fe13  mov     r8d, r15d
0x18000fe16  mov     rcx, r14
0x18000fe19  call    ReadBytes
0x18000fe1e  movzx   edx, ax
0x18000fe21  test    ax, ax
0x18000fe24  jnz     short loc_18000FE5E
0x18000fe26  lea     rax, [rsp+98h+var_68]
0x18000fe2b  mov     r8d, 10h
0x18000fe31  mov     [rsp+98h+var_70], rax
0x18000fe36  lea     r9, DIRECTORY_CONTROL
0x18000fe3d  lea     rdx, [rsp+98h+var_60]
0x18000fe42  mov     [rsp+98h+var_78], r13d
0x18000fe47  mov     rcx, rsi
0x18000fe4a  call    WriteGeneric
0x18000fe4f  movzx   edx, ax
0x18000fe52  test    ax, ax
0x18000fe55  jnz     short loc_18000FE5E
0x18000fe57  lea     eax, [rdi+rbx]
0x18000fe5a  mov     [r12], eax
0x18000fe5e  movzx   eax, dx
0x18000fe61  jmp     short loc_18000FE68
0x18000fe63  mov     eax, 3EEh
0x18000fe68  mov     rcx, [rsp+98h+var_50]
0x18000fe6d  xor     rcx, rsp; StackCookie
0x18000fe70  call    __security_check_cookie
0x18000fe75  add     rsp, 58h
0x18000fe79  pop     r15
0x18000fe7b  pop     r14
0x18000fe7d  pop     r13
0x18000fe7f  pop     r12
0x18000fe81  pop     rdi
0x18000fe82  pop     rsi
0x18000fe83  pop     rbp
0x18000fe84  pop     rbx
0x18000fe85  retn
```
