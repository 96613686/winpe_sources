# CSmartSession::SafeCopyString(ushort const *,ushort * *)

- ea: `0x18000bf20`
- end: `0x18000c0e0`
- name: `?SafeCopyString@CSmartSession@@AEAAJPEBGPEAPEAG@Z`
- size: `448`
- prototype: `__int64 __fastcall(CSmartSession *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800053f0`
- `0x180006040`

## callees

- `0x180007890`
- `0x18000bf20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bf92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bf92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c0b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c0b1`

## string_xrefs

- `0x18000c0a2`: `StringCchCopy failed: 0x%x in %s`
- `0x18000c03e`: `CSmartSession::SafeCopyString`
- `0x18000c05d`: `CSmartSession::SafeCopyString`
- `0x18000c096`: `CSmartSession::SafeCopyString`
- `0x18000c0be`: `CSmartSession::SafeCopyString`

## pseudocode

```c
__int64 __fastcall CSmartSession::SafeCopyString(
        CSmartSession *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  const unsigned __int16 *v4; // rbx
  __int64 v5; // rcx
  const unsigned __int16 *v6; // rax
  unsigned int v7; // edi
  __int64 v8; // rsi
  _WORD *v9; // rax
  _WORD *v10; // r14
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  _WORD *v13; // rdx
  _WORD *v14; // rax
  int v15; // r8d

  v4 = a2;
  if ( !a2 )
    return 0;
  if ( !a3 )
  {
    _DbgPrintMessage(8, "Invalid parameter failed: 0x%x in %s", -2147024809, "CSmartSession::SafeCopyString");
    return 2147942487LL;
  }
  v5 = 0x7FFFFFFF;
  v6 = a2;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  v7 = -2147024809;
  if ( !v5 )
  {
    _DbgPrintMessage(8, "StringCchLength failed: 0x%x in %s", -2147024809, "CSmartSession::SafeCopyString");
    return 2147942487LL;
  }
  v8 = 0x7FFFFFFF - v5;
  v9 = LocalAlloc(0x40u, 2 * (0x7FFFFFFF - v5) + 2);
  v10 = v9;
  if ( !v9 )
  {
    _DbgPrintMessage(8, "MIDL_user_allocate failed: 0x%x in %s", -2147024882, "CSmartSession::SafeCopyString");
    return 2147942414LL;
  }
  v11 = v8 + 1;
  if ( v8 == -1 )
  {
    v15 = -2147024809;
  }
  else
  {
    if ( v11 > 0x7FFFFFFF )
    {
      v15 = -2147024809;
      *v9 = 0;
      goto LABEL_26;
    }
    v12 = 2147483646;
    v13 = v10;
    do
    {
      if ( !v12 )
        break;
      if ( !*v4 )
        break;
      *v13++ = *v4++;
      --v12;
      --v11;
    }
    while ( v11 );
    v14 = v13 - 1;
    v15 = -2147024774;
    if ( v11 )
    {
      v14 = v13;
      v15 = 0;
    }
    *v14 = 0;
  }
  v7 = v15;
  if ( v15 < 0 )
  {
LABEL_26:
    _DbgPrintMessage(8, "StringCchCopy failed: 0x%x in %s", v15, "CSmartSession::SafeCopyString");
    LocalFree(v10);
    return v7;
  }
  *a3 = v10;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000bf20  push    rbx
0x18000bf22  push    rbp
0x18000bf23  push    r15
0x18000bf25  sub     rsp, 20h
0x18000bf29  mov     r15, r8
0x18000bf2c  mov     rbx, rdx
0x18000bf2f  test    rdx, rdx
0x18000bf32  jz      loc_18000C02C
0x18000bf38  mov     [rsp+38h+arg_8], rdi
0x18000bf3d  test    r8, r8
0x18000bf40  jz      loc_18000C039
0x18000bf46  mov     [rsp+38h+arg_0], rsi
0x18000bf4b  mov     ecx, 7FFFFFFFh
0x18000bf50  mov     rax, rdx
0x18000bf53  cmp     word ptr [rax], 0
0x18000bf57  jz      short loc_18000BF63
0x18000bf59  add     rax, 2
0x18000bf5d  sub     rcx, 1
0x18000bf61  jnz     short loc_18000BF53
0x18000bf63  xor     ebp, ebp
0x18000bf65  mov     edi, 80070057h
0x18000bf6a  test    rcx, rcx
0x18000bf6d  mov     esi, edi
0x18000bf6f  cmovnz  esi, ebp
0x18000bf72  jz      loc_18000C0BE
0x18000bf78  mov     esi, 7FFFFFFFh
0x18000bf7d  mov     [rsp+38h+arg_10], r14
0x18000bf82  sub     rsi, rcx
0x18000bf85  mov     ecx, 40h ; '@'; uFlags
0x18000bf8a  lea     rdx, ds:2[rsi*2]; uBytes
0x18000bf92  call    cs:__imp_LocalAlloc
0x18000bf98  mov     r14, rax
0x18000bf9b  test    rax, rax
0x18000bf9e  jz      loc_18000C05D
0x18000bfa4  lea     rcx, [rsi+1]
0x18000bfa8  test    rcx, rcx
0x18000bfab  jz      loc_18000C087
0x18000bfb1  cmp     rcx, 7FFFFFFFh
0x18000bfb8  ja      loc_18000C082
0x18000bfbe  mov     eax, 7FFFFFFEh
0x18000bfc3  mov     rdx, r14
0x18000bfc6  test    rax, rax
0x18000bfc9  jz      short loc_18000BFEA
0x18000bfcb  movzx   r8d, word ptr [rbx]
0x18000bfcf  test    r8w, r8w
0x18000bfd3  jz      short loc_18000BFEA
0x18000bfd5  mov     [rdx], r8w
0x18000bfd9  add     rbx, 2
0x18000bfdd  add     rdx, 2
0x18000bfe1  dec     rax
0x18000bfe4  sub     rcx, 1
0x18000bfe8  jnz     short loc_18000BFC6
0x18000bfea  test    rcx, rcx
0x18000bfed  lea     rax, [rdx-2]
0x18000bff1  mov     r8d, 8007007Ah
0x18000bff7  cmovnz  rax, rdx
0x18000bffb  cmovnz  r8d, ebp
0x18000bfff  mov     [rax], bp
0x18000c002  mov     edi, r8d
0x18000c005  test    r8d, r8d
0x18000c008  js      loc_18000C096
0x18000c00e  mov     [r15], r14
0x18000c011  mov     eax, r8d
0x18000c014  mov     r14, [rsp+38h+arg_10]
0x18000c019  mov     rsi, [rsp+38h+arg_0]
0x18000c01e  mov     rdi, [rsp+38h+arg_8]
0x18000c023  add     rsp, 20h
0x18000c027  pop     r15
0x18000c029  pop     rbp
0x18000c02a  pop     rbx
0x18000c02b  retn
0x18000c02c  xor     ebp, ebp
0x18000c02e  mov     eax, ebp
0x18000c030  add     rsp, 20h
0x18000c034  pop     r15
0x18000c036  pop     rbp
0x18000c037  pop     rbx
0x18000c038  retn
0x18000c039  mov     edi, 80070057h
0x18000c03e  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x18000c045  mov     r8d, edi
0x18000c048  lea     rdx, aInvalidParamet; "Invalid parameter failed: 0x%x in %s"
0x18000c04f  mov     ecx, 8; int
0x18000c054  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c059  mov     eax, edi
0x18000c05b  jmp     short loc_18000C01E
0x18000c05d  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x18000c064  mov     r8d, 8007000Eh
0x18000c06a  lea     rdx, aMidlUserAlloca; "MIDL_user_allocate failed: 0x%x in %s"
0x18000c071  mov     ecx, 8; int
0x18000c076  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c07b  mov     eax, 8007000Eh
0x18000c080  jmp     short loc_18000C014
0x18000c082  mov     r8d, edi
0x18000c085  jmp     short loc_18000C093
0x18000c087  mov     r8d, edi
0x18000c08a  test    rcx, rcx
0x18000c08d  jz      loc_18000C002
0x18000c093  mov     [rax], bp
0x18000c096  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x18000c09d  mov     ecx, 8; int
0x18000c0a2  lea     rdx, aStringcchcopyF_0; "StringCchCopy failed: 0x%x in %s"
0x18000c0a9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c0ae  mov     rcx, r14; hMem
0x18000c0b1  call    cs:__imp_LocalFree
0x18000c0b7  mov     eax, edi
0x18000c0b9  jmp     loc_18000C014
0x18000c0be  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x18000c0c5  mov     r8d, esi
0x18000c0c8  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x18000c0cf  mov     ecx, 8; int
0x18000c0d4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c0d9  mov     eax, esi
0x18000c0db  jmp     loc_18000C019
```
