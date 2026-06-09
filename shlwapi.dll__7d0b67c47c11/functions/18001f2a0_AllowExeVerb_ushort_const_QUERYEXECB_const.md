# _AllowExeVerb(ushort const *,QUERYEXECB const *)

- ea: `0x18001f2a0`
- end: `0x18001f362`
- name: `?_AllowExeVerb@@YAHPEBGPEBUQUERYEXECB@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct QUERYEXECB *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001fa90`

## callees

- `0x180012550`
- `0x18001f2a0`
- `0x18001f5d0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18001f30b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18001f30b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18001f317`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18001f317`

## pseudocode

```c
__int64 __fastcall _AllowExeVerb(const unsigned __int16 *a1, const struct QUERYEXECB *a2)
{
  unsigned int v4; // esi
  const WCHAR *v5; // rbx
  const WCHAR *FileNameW; // rax
  int v8[4]; // [rsp+40h] [rbp-248h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-238h] BYREF

  v8[0] = 260;
  v4 = 0;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, const unsigned __int16 *, WCHAR *, int *))(**(_QWORD **)a2 + 32LL))(
         *(_QWORD *)a2,
         *((unsigned int *)a2 + 2),
         2,
         a1,
         pszPath,
         v8) >= 0 )
  {
    v5 = (const WCHAR *)*((_QWORD *)a2 + 2);
    FileNameW = PathFindFileNameW(pszPath);
    if ( !StrCmpIW(FileNameW, v5) )
    {
      if ( (unsigned int)_IsMSIPerUserInstall(*(struct IQueryAssociations **)a2, *((_DWORD *)a2 + 2), a1) )
        return *((unsigned int *)a2 + 6);
      else
        return 1;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001f2a0  mov     [rsp+arg_10], rbx
0x18001f2a5  push    rbp
0x18001f2a6  push    rsi
0x18001f2a7  push    rdi
0x18001f2a8  sub     rsp, 270h
0x18001f2af  mov     rax, cs:__security_cookie
0x18001f2b6  xor     rax, rsp
0x18001f2b9  mov     [rsp+288h+var_28], rax
0x18001f2c1  mov     rdi, rdx
0x18001f2c4  mov     [rsp+288h+var_248], 104h
0x18001f2cc  mov     rbp, rcx
0x18001f2cf  xor     esi, esi
0x18001f2d1  mov     rcx, [rdx]
0x18001f2d4  mov     r9, rbp
0x18001f2d7  lea     rdx, [rsp+288h+var_248]
0x18001f2dc  mov     [rsp+288h+var_260], rdx
0x18001f2e1  lea     rdx, [rsp+288h+pszPath]
0x18001f2e6  mov     [rsp+288h+var_268], rdx
0x18001f2eb  lea     r8d, [rsi+2]
0x18001f2ef  mov     rax, [rcx]
0x18001f2f2  mov     edx, [rdi+8]
0x18001f2f5  mov     rax, [rax+20h]
0x18001f2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2fe  test    eax, eax
0x18001f300  js      short loc_18001F33D
0x18001f302  mov     rbx, [rdi+10h]
0x18001f306  lea     rcx, [rsp+288h+pszPath]; pszPath
0x18001f30b  call    cs:__imp_PathFindFileNameW
0x18001f311  mov     rcx, rax; psz1
0x18001f314  mov     rdx, rbx; psz2
0x18001f317  call    cs:__imp_StrCmpIW
0x18001f31d  test    eax, eax
0x18001f31f  jnz     short loc_18001F33D
0x18001f321  mov     edx, [rdi+8]; unsigned int
0x18001f324  mov     r8, rbp; unsigned __int16 *
0x18001f327  mov     rcx, [rdi]; struct IQueryAssociations *
0x18001f32a  call    ?_IsMSIPerUserInstall@@YAHPEAUIQueryAssociations@@KPEBG@Z; _IsMSIPerUserInstall(IQueryAssociations *,ulong,ushort const *)
0x18001f32f  test    eax, eax
0x18001f331  jz      short loc_18001F338
0x18001f333  mov     esi, [rdi+18h]
0x18001f336  jmp     short loc_18001F33D
0x18001f338  mov     esi, 1
0x18001f33d  mov     eax, esi
0x18001f33f  mov     rcx, [rsp+288h+var_28]
0x18001f347  xor     rcx, rsp; StackCookie
0x18001f34a  call    __security_check_cookie
0x18001f34f  mov     rbx, [rsp+288h+arg_10]
0x18001f357  add     rsp, 270h
0x18001f35e  pop     rdi
0x18001f35f  pop     rsi
0x18001f360  pop     rbp
0x18001f361  retn
```
