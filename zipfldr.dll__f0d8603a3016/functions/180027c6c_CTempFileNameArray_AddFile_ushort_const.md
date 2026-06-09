# CTempFileNameArray::_AddFile(ushort const *)

- ea: `0x180027c6c`
- end: `0x180027d83`
- name: `?_AddFile@CTempFileNameArray@@AEAAJPEBG@Z`
- size: `279`
- prototype: `int(CTempFileNameArray *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800200e4`
- `0x180027a40`

## callees

- `0x18001fcd0`
- `0x180020344`
- `0x180027c6c`
- `0x180036f50`
- `0x180037958`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180027cc0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180027cc0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180027cd3`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180027cd3`

## pseudocode

```c
__int64 __fastcall CTempFileNameArray::_AddFile(HDSA *this, const unsigned __int16 *a2)
{
  unsigned int v4; // edi
  HDSA v5; // rax
  DWORD FileAttributesW; // eax
  __int64 v7; // rax
  _WORD *v8; // r9
  __int64 v9; // r8
  _WORD *v10; // rcx
  int inserted; // eax
  unsigned int v12; // ecx
  _BYTE pitem[528]; // [rsp+20h] [rbp-238h] BYREF

  v4 = -2147024882;
  if ( this[7] || (v5 = DSA_Create(520, 4), (this[7] = v5) != 0) )
  {
    FileAttributesW = GetFileAttributesW(a2);
    if ( FileAttributesW != -1 )
      SetFileAttributesW(a2, FileAttributesW | 1);
    memset_0(pitem, 0, 0x208u);
    v7 = 2147483646;
    v8 = pitem;
    v9 = 260;
    do
    {
      if ( !v7 )
        break;
      if ( !*a2 )
        break;
      *v8++ = *a2++;
      --v7;
      --v9;
    }
    while ( v9 );
    v10 = v8 - 1;
    if ( v9 )
      v10 = v8;
    *v10 = 0;
    if ( v9 )
    {
      inserted = DSA_InsertItem(this[7], 0x7FFFFFFF, pitem);
      v12 = 0;
      if ( inserted == -1 )
        return (unsigned int)-2147024882;
      return v12;
    }
    else
    {
      return (unsigned int)-2147024774;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180027c6c  mov     [rsp+arg_10], rbx
0x180027c71  push    rbp
0x180027c72  push    rsi
0x180027c73  push    rdi
0x180027c74  sub     rsp, 240h
0x180027c7b  mov     rax, cs:__security_cookie
0x180027c82  xor     rax, rsp
0x180027c85  mov     [rsp+258h+var_28], rax
0x180027c8d  mov     rax, [rcx+38h]
0x180027c91  xor     ebp, ebp
0x180027c93  mov     rbx, rdx
0x180027c96  mov     rsi, rcx
0x180027c99  mov     edi, 8007000Eh
0x180027c9e  test    rax, rax
0x180027ca1  jnz     short loc_180027CBD
0x180027ca3  lea     edx, [rax+4]; cItemGrow
0x180027ca6  mov     ecx, 208h; cbItem
0x180027cab  call    DSA_Create
0x180027cb0  mov     [rsi+38h], rax
0x180027cb4  test    rax, rax
0x180027cb7  jz      loc_180027D5E
0x180027cbd  mov     rcx, rbx; lpFileName
0x180027cc0  call    cs:__imp_GetFileAttributesW
0x180027cc6  cmp     eax, 0FFFFFFFFh
0x180027cc9  jz      short loc_180027CD9
0x180027ccb  or      eax, 1
0x180027cce  mov     rcx, rbx; lpFileName
0x180027cd1  mov     edx, eax; dwFileAttributes
0x180027cd3  call    cs:__imp_SetFileAttributesW
0x180027cd9  xor     edx, edx; Val
0x180027cdb  lea     rcx, [rsp+258h+pitem]; void *
0x180027ce0  mov     r8d, 208h; Size
0x180027ce6  call    memset_0
0x180027ceb  mov     eax, 7FFFFFFEh
0x180027cf0  lea     r9, [rsp+258h+pitem]
0x180027cf5  mov     r8d, 104h
0x180027cfb  test    rax, rax
0x180027cfe  jz      short loc_180027D1D
0x180027d00  movzx   ecx, word ptr [rbx]
0x180027d03  test    cx, cx
0x180027d06  jz      short loc_180027D1D
0x180027d08  mov     [r9], cx
0x180027d0c  add     rbx, 2
0x180027d10  add     r9, 2
0x180027d14  dec     rax
0x180027d17  sub     r8, 1
0x180027d1b  jnz     short loc_180027CFB
0x180027d1d  mov     rax, r8
0x180027d20  lea     rcx, [r9-2]
0x180027d24  neg     rax
0x180027d27  sbb     edx, edx
0x180027d29  not     edx
0x180027d2b  and     edx, 8007007Ah
0x180027d31  test    r8, r8
0x180027d34  cmovnz  rcx, r9
0x180027d38  mov     [rcx], bp
0x180027d3b  jz      short loc_180027D5C
0x180027d3d  mov     rcx, [rsi+38h]; hdsa
0x180027d41  lea     r8, [rsp+258h+pitem]; pitem
0x180027d46  mov     edx, 7FFFFFFFh; i
0x180027d4b  call    DSA_InsertItem
0x180027d50  cmp     eax, 0FFFFFFFFh
0x180027d53  mov     ecx, ebp
0x180027d55  cmovz   ecx, edi
0x180027d58  mov     edi, ecx
0x180027d5a  jmp     short loc_180027D5E
0x180027d5c  mov     edi, edx
0x180027d5e  mov     eax, edi
0x180027d60  mov     rcx, [rsp+258h+var_28]
0x180027d68  xor     rcx, rsp; StackCookie
0x180027d6b  call    __security_check_cookie
0x180027d70  mov     rbx, [rsp+258h+arg_10]
0x180027d78  add     rsp, 240h
0x180027d7f  pop     rdi
0x180027d80  pop     rsi
0x180027d81  pop     rbp
0x180027d82  retn
```
