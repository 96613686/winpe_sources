# CWMIBinMof::DecompressBinaryMof(uchar *,uchar * *)

- ea: `0x180017cb0`
- end: `0x180017dc2`
- name: `?DecompressBinaryMof@CWMIBinMof@@QEAAJPEAEPEAPEAE@Z`
- size: `274`
- prototype: `__int64 __fastcall(CWMIBinMof *__hidden this, unsigned __int8 *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800178d8`

## callees

- `0x180017cb0`

## import_xrefs

- `msvcrt!free` at `0x180017da5`
- `msvcrt!free` at `0x180017da5`
- `msvcrt!malloc` at `0x180017d03`
- `msvcrt!malloc` at `0x180017d03`
- `wbemcomn!?Mrci1Decompress@CBaseMrciCompression@@QEAAIPEAEI0I@Z` at `0x180017d79`
- `wbemcomn!?Mrci1Decompress@CBaseMrciCompression@@QEAAIPEAEI0I@Z` at `0x180017d79`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180017d84`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180017d84`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180017d28`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180017d28`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CWMIBinMof::DecompressBinaryMof(CWMIBinMof *this, unsigned __int8 *a2, unsigned __int8 **a3)
{
  unsigned __int8 **v3; // rsi
  unsigned int v4; // r12d
  unsigned __int8 *v5; // rbx
  unsigned int v6; // r15d
  unsigned __int8 *v7; // rdi
  unsigned int v8; // ebx
  CBaseMrciCompression *v9; // r14
  unsigned int v10; // ebx
  unsigned __int8 *v12; // [rsp+38h] [rbp-40h]

  v3 = a3;
  if ( *(_QWORD *)a2 != 0x1424D4F46LL )
    return 2147749889LL;
  v4 = *((_DWORD *)a2 + 2);
  v5 = a2 + 12;
  v12 = a2 + 12;
  v6 = *((_DWORD *)a2 + 3);
  v7 = (unsigned __int8 *)malloc(v6);
  if ( v7 )
  {
    try
    {
      v9 = (CBaseMrciCompression *)CWin32DefaultArena::WbemMemAlloc(0xC510u);
    }
    catch ( ... )
    {
      v3 = a3;
      v9 = 0;
      v5 = v12;
    }
    if ( v9 )
    {
      v10 = CBaseMrciCompression::Mrci1Decompress(v9, v5 + 4, v4, v7, v6);
      CWin32DefaultArena::WbemMemFree(v9);
      if ( v10 == v6 )
      {
        *v3 = v7;
        return 0;
      }
      v8 = -2147217407;
    }
    else
    {
      v8 = -2147217402;
    }
    free(v7);
  }
  else
  {
    return (unsigned int)-2147217402;
  }
  return v8;
}

```

## disassembly

```asm
0x180017cb0  mov     [rsp+arg_10], r8
0x180017cb5  mov     [rsp+arg_0], rcx
0x180017cba  push    rbx
0x180017cbb  push    rsi
0x180017cbc  push    rdi
0x180017cbd  push    r12
0x180017cbf  push    r14
0x180017cc1  push    r15
0x180017cc3  sub     rsp, 48h
0x180017cc7  mov     rsi, r8
0x180017cca  cmp     dword ptr [rdx], 424D4F46h
0x180017cd0  jnz     loc_180017DAF
0x180017cd6  cmp     dword ptr [rdx+4], 1
0x180017cda  jnz     loc_180017DAF
0x180017ce0  mov     r12d, [rdx+8]
0x180017ce4  mov     dword ptr [rsp+78h+arg_0], r12d
0x180017cec  lea     rbx, [rdx+0Ch]
0x180017cf0  mov     [rsp+78h+var_40], rbx
0x180017cf5  mov     r15d, [rbx]
0x180017cf8  mov     [rsp+78h+arg_18], r15
0x180017d00  mov     ecx, r15d; Size
0x180017d03  call    cs:__imp_malloc
0x180017d09  mov     rdi, rax
0x180017d0c  mov     [rsp+78h+arg_8], rax
0x180017d14  test    rax, rax
0x180017d17  jnz     short loc_180017D23
0x180017d19  mov     ebx, 80041006h
0x180017d1e  jmp     loc_180017DAB
0x180017d23  mov     ecx, 0C510h
0x180017d28  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180017d2e  mov     r14, rax
0x180017d31  mov     [rsp+78h+var_48], rax
0x180017d36  jmp     short loc_180017D62
0x180017d38  mov     rsi, [rsp+78h+arg_10]
0x180017d40  mov     rdi, [rsp+78h+arg_8]
0x180017d48  mov     r14, [rsp+78h+var_48]
0x180017d4d  mov     r12d, dword ptr [rsp+78h+arg_0]
0x180017d55  mov     r15, [rsp+78h+arg_18]
0x180017d5d  mov     rbx, [rsp+78h+var_40]
0x180017d62  test    r14, r14
0x180017d65  jz      short loc_180017D9D
0x180017d67  lea     rdx, [rbx+4]
0x180017d6b  mov     [rsp+78h+var_58], r15d
0x180017d70  mov     r9, rdi
0x180017d73  mov     r8d, r12d
0x180017d76  mov     rcx, r14
0x180017d79  call    cs:__imp_?Mrci1Decompress@CBaseMrciCompression@@QEAAIPEAEI0I@Z; CBaseMrciCompression::Mrci1Decompress(uchar *,uint,uchar *,uint)
0x180017d7f  mov     ebx, eax
0x180017d81  mov     rcx, r14
0x180017d84  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180017d8a  cmp     ebx, r15d
0x180017d8d  jz      short loc_180017D96
0x180017d8f  mov     ebx, 80041001h
0x180017d94  jmp     short loc_180017DA2
0x180017d96  mov     [rsi], rdi
0x180017d99  xor     eax, eax
0x180017d9b  jmp     short loc_180017DB4
0x180017d9d  mov     ebx, 80041006h
0x180017da2  mov     rcx, rdi; Block
0x180017da5  call    cs:__imp_free
0x180017dab  mov     eax, ebx
0x180017dad  jmp     short loc_180017DB4
0x180017daf  mov     eax, 80041001h
0x180017db4  add     rsp, 48h
0x180017db8  pop     r15
0x180017dba  pop     r14
0x180017dbc  pop     r12
0x180017dbe  pop     rdi
0x180017dbf  pop     rsi
0x180017dc0  pop     rbx
0x180017dc1  retn
```
