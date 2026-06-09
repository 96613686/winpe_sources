# CSmartSession::SafeCopyString(ushort const *,ushort * *)

- ea: `0x18000daa0`
- end: `0x18000dc72`
- name: `?SafeCopyString@CSmartSession@@AEAAJPEBGPEAPEAG@Z`
- size: `466`
- prototype: `__int64 __fastcall(CSmartSession *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800038c0`
- `0x1800045d0`

## callees

- `0x180005b40`
- `0x18000daa0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db12`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc3d`

## string_xrefs

- `0x18000dc2e`: `StringCchCopy failed: 0x%x in %s`
- `0x18000dbca`: `CSmartSession::SafeCopyString`
- `0x18000dbe9`: `CSmartSession::SafeCopyString`
- `0x18000dc22`: `CSmartSession::SafeCopyString`
- `0x18000dc50`: `CSmartSession::SafeCopyString`

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
0x18000daa0  push    rbx
0x18000daa2  push    rbp
0x18000daa3  push    r15
0x18000daa5  sub     rsp, 20h
0x18000daa9  mov     r15, r8
0x18000daac  mov     rbx, rdx
0x18000daaf  test    rdx, rdx
0x18000dab2  jz      loc_18000DBB7
0x18000dab8  mov     [rsp+38h+arg_8], rdi
0x18000dabd  test    r8, r8
0x18000dac0  jz      loc_18000DBC5
0x18000dac6  mov     [rsp+38h+arg_0], rsi
0x18000dacb  mov     ecx, 7FFFFFFFh
0x18000dad0  mov     rax, rdx
0x18000dad3  cmp     word ptr [rax], 0
0x18000dad7  jz      short loc_18000DAE3
0x18000dad9  add     rax, 2
0x18000dadd  sub     rcx, 1
0x18000dae1  jnz     short loc_18000DAD3
0x18000dae3  xor     ebp, ebp
0x18000dae5  mov     edi, 80070057h
0x18000daea  test    rcx, rcx
0x18000daed  mov     esi, edi
0x18000daef  cmovnz  esi, ebp
0x18000daf2  jz      loc_18000DC50
0x18000daf8  mov     esi, 7FFFFFFFh
0x18000dafd  mov     [rsp+38h+arg_10], r14
0x18000db02  sub     rsi, rcx
0x18000db05  mov     ecx, 40h ; '@'; uFlags
0x18000db0a  lea     rdx, ds:2[rsi*2]; uBytes
0x18000db12  call    cs:__imp_LocalAlloc
0x18000db19  nop     dword ptr [rax+rax+00h]
0x18000db1e  mov     r14, rax
0x18000db21  test    rax, rax
0x18000db24  jz      loc_18000DBE9
0x18000db2a  lea     rcx, [rsi+1]
0x18000db2e  test    rcx, rcx
0x18000db31  jz      loc_18000DC13
0x18000db37  cmp     rcx, 7FFFFFFFh
0x18000db3e  ja      loc_18000DC0E
0x18000db44  mov     eax, 7FFFFFFEh
0x18000db49  mov     rdx, r14
0x18000db4c  nop     dword ptr [rax+00h]
0x18000db50  test    rax, rax
0x18000db53  jz      short loc_18000DB74
0x18000db55  movzx   r8d, word ptr [rbx]
0x18000db59  test    r8w, r8w
0x18000db5d  jz      short loc_18000DB74
0x18000db5f  mov     [rdx], r8w
0x18000db63  add     rbx, 2
0x18000db67  add     rdx, 2
0x18000db6b  dec     rax
0x18000db6e  sub     rcx, 1
0x18000db72  jnz     short loc_18000DB50
0x18000db74  test    rcx, rcx
0x18000db77  lea     rax, [rdx-2]
0x18000db7b  mov     r8d, 8007007Ah
0x18000db81  cmovnz  rax, rdx
0x18000db85  cmovnz  r8d, ebp
0x18000db89  mov     [rax], bp
0x18000db8c  mov     edi, r8d
0x18000db8f  test    r8d, r8d
0x18000db92  js      loc_18000DC22
0x18000db98  mov     [r15], r14
0x18000db9b  mov     eax, r8d
0x18000db9e  mov     r14, [rsp+38h+arg_10]
0x18000dba3  mov     rsi, [rsp+38h+arg_0]
0x18000dba8  mov     rdi, [rsp+38h+arg_8]
0x18000dbad  add     rsp, 20h
0x18000dbb1  pop     r15
0x18000dbb3  pop     rbp
0x18000dbb4  pop     rbx
0x18000dbb5  retn
0x18000dbb7  xor     ebp, ebp
0x18000dbb9  mov     eax, ebp
0x18000dbbb  add     rsp, 20h
0x18000dbbf  pop     r15
0x18000dbc1  pop     rbp
0x18000dbc2  pop     rbx
0x18000dbc3  retn
0x18000dbc5  mov     edi, 80070057h
0x18000dbca  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x18000dbd1  mov     r8d, edi
0x18000dbd4  lea     rdx, aInvalidParamet; "Invalid parameter failed: 0x%x in %s"
0x18000dbdb  mov     ecx, 8; int
0x18000dbe0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dbe5  mov     eax, edi
0x18000dbe7  jmp     short loc_18000DBA8
0x18000dbe9  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x18000dbf0  mov     r8d, 8007000Eh
0x18000dbf6  lea     rdx, aMidlUserAlloca; "MIDL_user_allocate failed: 0x%x in %s"
0x18000dbfd  mov     ecx, 8; int
0x18000dc02  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dc07  mov     eax, 8007000Eh
0x18000dc0c  jmp     short loc_18000DB9E
0x18000dc0e  mov     r8d, edi
0x18000dc11  jmp     short loc_18000DC1F
0x18000dc13  mov     r8d, edi
0x18000dc16  test    rcx, rcx
0x18000dc19  jz      loc_18000DB8C
0x18000dc1f  mov     [rax], bp
0x18000dc22  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x18000dc29  mov     ecx, 8; int
0x18000dc2e  lea     rdx, aStringcchcopyF_0; "StringCchCopy failed: 0x%x in %s"
0x18000dc35  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dc3a  mov     rcx, r14; hMem
0x18000dc3d  call    cs:__imp_LocalFree
0x18000dc44  nop     dword ptr [rax+rax+00h]
0x18000dc49  mov     eax, edi
0x18000dc4b  jmp     loc_18000DB9E
0x18000dc50  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x18000dc57  mov     r8d, esi
0x18000dc5a  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x18000dc61  mov     ecx, 8; int
0x18000dc66  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dc6b  mov     eax, esi
0x18000dc6d  jmp     loc_18000DBA3
```
