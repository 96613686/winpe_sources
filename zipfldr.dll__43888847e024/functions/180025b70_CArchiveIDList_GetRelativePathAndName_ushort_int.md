# CArchiveIDList::GetRelativePathAndName(ushort *,int)

- ea: `0x180025b70`
- end: `0x180025c41`
- name: `?GetRelativePathAndName@CArchiveIDList@@QEBAJPEAGH@Z`
- size: `209`
- prototype: `__int64 __fastcall(PERCEIVED *this, unsigned __int16 *, __int64, PWSTR *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ea30`
- `0x180025aac`

## callees

- `0x180010c30`
- `0x180025b70`
- `0x180036f50`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x180025bfd`
- `SHLWAPI!PathAppendW` at `0x180025bfd`
- `SHLWAPI!__imp_ualstrcpynW` at `0x180025ba7`
- `SHLWAPI!__imp_ualstrcpynW` at `0x180025bc4`
- `SHLWAPI!__imp_ualstrcpynW` at `0x180025ba7`
- `SHLWAPI!__imp_ualstrcpynW` at `0x180025bc4`

## pseudocode

```c
__int64 __fastcall CArchiveIDList::GetRelativePathAndName(PERCEIVED *this, unsigned __int16 *a2, __int64 a3, PWSTR *a4)
{
  PWSTR *v6; // r9
  WCHAR v7; // cx
  WCHAR *v8; // rax
  WCHAR pszPath[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR pszExt[264]; // [rsp+230h] [rbp-228h] BYREF

  ualstrcpynW(pszExt, this + 23, (PERCEIVEDFLAG *)0x104, a4);
  ualstrcpynW(pszPath, (PERCEIVED *)((char *)this + 2 * *((int *)this + 21) + 94), (PERCEIVEDFLAG *)0x104, v6);
  v7 = pszPath[0];
  if ( pszPath[0] )
  {
    v8 = pszPath;
    do
    {
      if ( v7 == 47 )
        *v8 = 92;
      v7 = *++v8;
    }
    while ( *v8 );
  }
  if ( PathAppendW(pszPath, pszExt) )
    return StringCchCopyW(a2, 0x104u, pszPath);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180025b70  mov     [rsp+arg_10], rbx
0x180025b75  push    rdi
0x180025b76  sub     rsp, 450h
0x180025b7d  mov     rax, cs:__security_cookie
0x180025b84  xor     rax, rsp
0x180025b87  mov     [rsp+458h+var_18], rax
0x180025b8f  mov     rdi, rdx
0x180025b92  mov     rbx, rcx
0x180025b95  lea     rdx, [rcx+5Ch]; ptype
0x180025b99  mov     r8d, 104h; pflag
0x180025b9f  lea     rcx, [rsp+458h+pszExt]; pszExt
0x180025ba7  call    cs:__imp_ualstrcpynW
0x180025bad  movsxd  rax, dword ptr [rbx+54h]
0x180025bb1  lea     rcx, [rsp+458h+pszPath]; pszExt
0x180025bb6  add     rax, 2Fh ; '/'
0x180025bba  mov     r8d, 104h; pflag
0x180025bc0  lea     rdx, [rbx+rax*2]; ptype
0x180025bc4  call    cs:__imp_ualstrcpynW
0x180025bca  movzx   ecx, [rsp+458h+pszPath]
0x180025bcf  test    cx, cx
0x180025bd2  jz      short loc_180025BF0
0x180025bd4  lea     rax, [rsp+458h+pszPath]
0x180025bd9  cmp     cx, 2Fh ; '/'
0x180025bdd  jnz     short loc_180025BE4
0x180025bdf  mov     word ptr [rax], 5Ch ; '\'
0x180025be4  add     rax, 2
0x180025be8  movzx   ecx, word ptr [rax]
0x180025beb  test    cx, cx
0x180025bee  jnz     short loc_180025BD9
0x180025bf0  lea     rdx, [rsp+458h+pszExt]; pszMore
0x180025bf8  lea     rcx, [rsp+458h+pszPath]; pszPath
0x180025bfd  call    cs:__imp_PathAppendW
0x180025c03  test    eax, eax
0x180025c05  jz      short loc_180025C1B
0x180025c07  lea     r8, [rsp+458h+pszPath]; unsigned __int16 *
0x180025c0c  mov     edx, 104h; unsigned __int64
0x180025c11  mov     rcx, rdi; unsigned __int16 *
0x180025c14  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025c19  jmp     short loc_180025C20
0x180025c1b  mov     eax, 80004005h
0x180025c20  mov     rcx, [rsp+458h+var_18]
0x180025c28  xor     rcx, rsp; StackCookie
0x180025c2b  call    __security_check_cookie
0x180025c30  mov     rbx, [rsp+458h+arg_10]
0x180025c38  add     rsp, 450h
0x180025c3f  pop     rdi
0x180025c40  retn
```
