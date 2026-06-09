# _MakeCommandString(ulong *,ushort const *,ushort const *,ShStrW &)

- ea: `0x18001f684`
- end: `0x18001f825`
- name: `?_MakeCommandString@@YAJPEAKPEBG1AEAVShStrW@@@Z`
- size: `417`
- prototype: `int __fastcall(unsigned int *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180010304`

## callees

- `0x180002568`
- `0x18000eaf0`
- `0x1800103f8`
- `0x180012550`
- `0x18001ed8c`
- `0x18001eff8`
- `0x18001f1b4`
- `0x18001f684`
- `0x18001f82c`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x18001f7d7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x18001f7d7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsLFNFileSpecW` at `0x18001f751`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsLFNFileSpecW` at `0x18001f751`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001f6e4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001f73a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001f6e4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001f73a`

## pseudocode

```c
int __fastcall _MakeCommandString(
        unsigned int *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  const unsigned __int16 *v5; // rbp
  int result; // eax
  unsigned int v9; // eax
  unsigned __int64 v10; // rsi
  bool v11; // zf
  const WCHAR *v12; // rdi
  int v13; // edi
  const WCHAR **v14; // rsi
  int v15; // eax
  const WCHAR *v16; // rdx
  __int64 v17; // rdx
  unsigned __int16 v18; // [rsp+20h] [rbp-48h] BYREF

  v5 = a3;
  if ( !a3 || !*a3 )
    v5 = L"\"%1\"";
  ShStrW::Reset((ShStrW *)a4);
  result = 1;
  if ( !a2 || !*a2 )
    return result;
  v9 = lstrlenW(a2);
  v10 = v9;
  if ( v9 )
  {
    result = ShStrW::SetSize((ShStrW *)a4, v9 + 1);
    v11 = result == 0;
    if ( result < 0 )
      goto LABEL_11;
    result = StringCchCopyNW(a4[17], *((unsigned int *)a4 + 36), a2, v10);
  }
  else
  {
    result = ResultFromKnownLastError();
  }
  v11 = result == 0;
LABEL_11:
  if ( v11 )
  {
    v12 = a4[17];
    if ( *v12 == 34 && v12[lstrlenW(v12) - 1] == 34 || (v13 = 1, !PathIsLFNFileSpecW(a4[17])) )
      v13 = 0;
    if ( (*a1 & 0x400) != 0 )
    {
      v14 = (const WCHAR **)off_1800591A0;
      v15 = 0;
      if ( off_1800591A0[0] )
      {
        while ( !v15 )
        {
          v16 = *v14++;
          v15 = _TrySubst((struct ShStrW *)a4, v16);
          if ( !*v14 )
          {
            if ( !v15 )
              goto LABEL_22;
            break;
          }
        }
        *a1 |= 0x200u;
      }
    }
LABEL_22:
    ShStrW::Trim((ShStrW *)a4);
    if ( v13 )
    {
      v17 = -1;
      do
        ++v17;
      while ( a4[17][v17] );
      if ( !(unsigned int)ShStrW::SetSize((ShStrW *)a4, (int)v17 + 3) )
        PathQuoteSpacesW(a4[17]);
    }
    v18 = 32;
    result = ShStrW::Append((ShStrW *)a4, &v18, 1u);
    if ( !result )
      return ShStrW::Append((ShStrW *)a4, v5, 0xFFFFFFFF);
  }
  return result;
}

```

## disassembly

```asm
0x18001f684  push    rbx
0x18001f686  push    rbp
0x18001f687  push    rsi
0x18001f688  push    rdi
0x18001f689  push    r14
0x18001f68b  push    r15
0x18001f68d  sub     rsp, 38h
0x18001f691  mov     rax, cs:__security_cookie
0x18001f698  xor     rax, rsp
0x18001f69b  mov     [rsp+68h+var_40], rax
0x18001f6a0  xor     r15d, r15d
0x18001f6a3  mov     rbx, r9
0x18001f6a6  mov     rbp, r8
0x18001f6a9  mov     rdi, rdx
0x18001f6ac  mov     r14, rcx
0x18001f6af  test    r8, r8
0x18001f6b2  jz      short loc_18001F6BA
0x18001f6b4  cmp     [r8], r15w
0x18001f6b8  jnz     short loc_18001F6C1
0x18001f6ba  lea     rbp, a1_1; "\"%1\""
0x18001f6c1  mov     rcx, rbx; this
0x18001f6c4  call    ?Reset@ShStrW@@QEAAXXZ; ShStrW::Reset(void)
0x18001f6c9  mov     eax, 1
0x18001f6ce  test    rdi, rdi
0x18001f6d1  jz      loc_18001F80B
0x18001f6d7  cmp     [rdi], r15w
0x18001f6db  jz      loc_18001F80B
0x18001f6e1  mov     rcx, rdi; lpString
0x18001f6e4  call    cs:__imp_lstrlenW
0x18001f6ea  mov     esi, eax
0x18001f6ec  test    eax, eax
0x18001f6ee  jnz     short loc_18001F6F7
0x18001f6f0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001f6f5  jmp     short loc_18001F71E
0x18001f6f7  lea     edx, [rsi+1]; unsigned int
0x18001f6fa  mov     rcx, rbx; this
0x18001f6fd  call    ?SetSize@ShStrW@@QEAAJK@Z; ShStrW::SetSize(ulong)
0x18001f702  test    eax, eax
0x18001f704  js      short loc_18001F720
0x18001f706  mov     edx, [rbx+90h]; unsigned __int64
0x18001f70c  mov     r9, rsi; unsigned __int64
0x18001f70f  mov     rcx, [rbx+88h]; unsigned __int16 *
0x18001f716  mov     r8, rdi; unsigned __int16 *
0x18001f719  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001f71e  test    eax, eax
0x18001f720  jnz     loc_18001F80B
0x18001f726  mov     rdi, [rbx+88h]
0x18001f72d  mov     esi, 22h ; '"'
0x18001f732  cmp     si, [rdi]
0x18001f735  jnz     short loc_18001F74A
0x18001f737  mov     rcx, rdi; lpString
0x18001f73a  call    cs:__imp_lstrlenW
0x18001f740  movsxd  rcx, eax
0x18001f743  cmp     si, [rdi+rcx*2-2]
0x18001f748  jz      short loc_18001F760
0x18001f74a  mov     rcx, [rbx+88h]; pszName
0x18001f751  call    cs:__imp_PathIsLFNFileSpecW
0x18001f757  mov     edi, 1
0x18001f75c  test    eax, eax
0x18001f75e  jnz     short loc_18001F763
0x18001f760  mov     edi, r15d
0x18001f763  test    dword ptr [r14], 400h
0x18001f76a  jz      short loc_18001F7A0
0x18001f76c  cmp     cs:off_1800591A0, r15; "USERPROFILE"
0x18001f773  lea     rsi, off_1800591A0; "USERPROFILE"
0x18001f77a  mov     eax, r15d
0x18001f77d  jz      short loc_18001F7A0
0x18001f77f  test    eax, eax
0x18001f781  jnz     short loc_18001F79B
0x18001f783  mov     rdx, [rsi]; lpString
0x18001f786  mov     rcx, rbx; this
0x18001f789  add     rsi, 8
0x18001f78d  call    ?_TrySubst@@YAHAEAVShStrW@@PEBG@Z; _TrySubst(ShStrW &,ushort const *)
0x18001f792  cmp     [rsi], r15
0x18001f795  jnz     short loc_18001F77F
0x18001f797  test    eax, eax
0x18001f799  jz      short loc_18001F7A0
0x18001f79b  bts     dword ptr [r14], 9
0x18001f7a0  mov     rcx, rbx; this
0x18001f7a3  call    ?Trim@ShStrW@@QEAAXXZ; ShStrW::Trim(void)
0x18001f7a8  test    edi, edi
0x18001f7aa  jz      short loc_18001F7DD
0x18001f7ac  mov     rax, [rbx+88h]
0x18001f7b3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001f7b7  inc     rdx
0x18001f7ba  cmp     [rax+rdx*2], r15w
0x18001f7bf  jnz     short loc_18001F7B7
0x18001f7c1  add     edx, 3; unsigned int
0x18001f7c4  mov     rcx, rbx; this
0x18001f7c7  call    ?SetSize@ShStrW@@QEAAJK@Z; ShStrW::SetSize(ulong)
0x18001f7cc  test    eax, eax
0x18001f7ce  jnz     short loc_18001F7DD
0x18001f7d0  mov     rcx, [rbx+88h]; lpsz
0x18001f7d7  call    cs:__imp_PathQuoteSpacesW
0x18001f7dd  mov     eax, 20h ; ' '
0x18001f7e2  lea     rdx, [rsp+68h+var_48]; unsigned __int16 *
0x18001f7e7  mov     rcx, rbx; this
0x18001f7ea  mov     [rsp+68h+var_48], ax
0x18001f7ef  lea     r8d, [rax-1Fh]; unsigned int
0x18001f7f3  call    ?Append@ShStrW@@QEAAJPEBGK@Z; ShStrW::Append(ushort const *,ulong)
0x18001f7f8  test    eax, eax
0x18001f7fa  jnz     short loc_18001F80B
0x18001f7fc  or      r8d, 0FFFFFFFFh; unsigned int
0x18001f800  mov     rdx, rbp; unsigned __int16 *
0x18001f803  mov     rcx, rbx; this
0x18001f806  call    ?Append@ShStrW@@QEAAJPEBGK@Z; ShStrW::Append(ushort const *,ulong)
0x18001f80b  mov     rcx, [rsp+68h+var_40]
0x18001f810  xor     rcx, rsp; StackCookie
0x18001f813  call    __security_check_cookie
0x18001f818  add     rsp, 38h
0x18001f81c  pop     r15
0x18001f81e  pop     r14
0x18001f820  pop     rdi
0x18001f821  pop     rsi
0x18001f822  pop     rbp
0x18001f823  pop     rbx
0x18001f824  retn
```
