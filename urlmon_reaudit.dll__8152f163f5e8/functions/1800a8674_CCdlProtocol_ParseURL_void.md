# CCdlProtocol::_ParseURL(void)

- ea: `0x1800a8674`
- end: `0x1800a8b44`
- name: `?_ParseURL@CCdlProtocol@@AEAAJXZ`
- size: `1232`
- prototype: `__int64 __fastcall(CCdlProtocol *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800dd020`
- `0x1800dd0b0`

## callees

- `0x1800124b0`
- `0x180024ea0`
- `0x18002fee0`
- `0x18006c5dc`
- `0x18007e170`
- `0x1800a3dc0`
- `0x1800a8674`
- `0x1800a8b4c`
- `0x180128660`
- `0x180128720`
- `0x180129010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800a86f2`
- `msvcrt!wcschr` at `0x1800a8738`
- `msvcrt!wcschr` at `0x1800a86f2`
- `msvcrt!wcschr` at `0x1800a8738`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x1800a8914`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x1800a8914`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntA` at `0x1800a8888`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntA` at `0x1800a88c6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntA` at `0x1800a8888`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntA` at `0x1800a88c6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800a8a67`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800a8a67`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800a8ad6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800a8ad6`

## string_xrefs

- `0x1800a880b`: `clsid`
- `0x1800a8845`: `extension`
- `0x1800a8963`: `dllname`

## pseudocode

```c
__int64 __fastcall CCdlProtocol::_ParseURL(CCdlProtocol *this)
{
  const WCHAR *v2; // rbx
  wchar_t *v3; // rax
  int v4; // r12d
  __int64 v5; // rax
  const WCHAR *v6; // rcx
  const WCHAR *i; // rdx
  const WCHAR *v8; // r14
  const WCHAR *v9; // rdi
  char v10; // r9
  int v11; // eax
  const WCHAR *v12; // rcx
  const OLECHAR *v13; // rax
  int (__fastcall ***v14)(_QWORD, GUID *, LPOLESTR *); // rcx
  unsigned int started; // ebx
  __int64 v16; // rax
  __int64 v17; // rax
  LPOLESTR v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int128 v22; // [rsp+60h] [rbp-A0h]
  unsigned int v23[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h]
  __int64 v25; // [rsp+80h] [rbp-80h] BYREF
  CHAR pszSrc[272]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Str[2088]; // [rsp+1A0h] [rbp+A0h] BYREF

  *(_OWORD *)lpsz = 0;
  v22 = 0;
  v21 = 0;
  *(_QWORD *)v23 = 0;
  v24 = 0;
  StringCchCopyW(Str, 0x824u, (const unsigned __int16 *)this + 112);
  v2 = wcschr(Str, 0x3Au) + 1;
  if ( (unsigned int)StrCmpNIIW(v2, L"//", 2u) && (unsigned int)StrCmpNIIW(v2, L"\\\\", 2u) )
  {
LABEL_5:
    v4 = 0;
    v5 = -1;
    do
      ++v5;
    while ( v2[v5] );
    v6 = &v2[v5];
    for ( i = v6 - 1; i >= v2; --i )
    {
      if ( *i == 35 )
      {
        *i = 0;
        v6 = i;
        goto LABEL_12;
      }
    }
    while ( 1 )
    {
LABEL_12:
      if ( v6 < v2 )
        goto LABEL_65;
      while ( *v6 != 61 )
      {
        if ( *v6 != 59 && --v6 >= v2 )
          continue;
        if ( v6 < v2 )
          goto LABEL_65;
        break;
      }
      if ( *v6 == 59 )
        goto LABEL_65;
      *v6 = 0;
      v8 = v6;
      do
      {
        if ( ((*v8 - 59) & 0xFFFD) == 0 )
          break;
        --v8;
      }
      while ( v8 >= v2 );
      if ( *v8 == 61 )
        goto LABEL_65;
      v9 = v6 + 1;
      if ( !(unsigned int)StrCmpIIW(L"codebase", v8 + 1) )
      {
        *(_QWORD *)&v21 = v9;
        goto LABEL_44;
      }
      if ( !(unsigned int)StrCmpIIW(L"clsid", v8 + 1) )
        break;
      if ( !(unsigned int)StrCmpIIW(L"mimetype", v8 + 1) )
      {
        *((_QWORD *)&v21 + 1) = v9;
        goto LABEL_36;
      }
      if ( !(unsigned int)StrCmpIIW(L"extension", v8 + 1) )
      {
        *(_QWORD *)&v22 = v9;
        goto LABEL_36;
      }
      if ( !(unsigned int)StrCmpIIW(L"verMS", v8 + 1) )
      {
        W2A(v9, pszSrc, 260);
        v23[0] = StrToIntA(pszSrc);
        goto LABEL_44;
      }
      if ( !(unsigned int)StrCmpIIW(L"verLS", v8 + 1) )
      {
        W2A(v9, pszSrc, 260);
        v23[1] = StrToIntA(pszSrc);
        goto LABEL_44;
      }
      if ( !(unsigned int)StrCmpIIW(L"distunit", v8 + 1) )
      {
        lpsz[0] = v9;
        goto LABEL_36;
      }
      if ( (unsigned int)StrCmpIIW(L"flags", v8 + 1) )
      {
        if ( (unsigned int)StrCmpIIW(L"version", v8 + 1) )
        {
          v11 = StrCmpIIW(L"dllname", v8 + 1);
          v12 = (const WCHAR *)*((_QWORD *)&v22 + 1);
          if ( !v11 )
            v12 = v9;
          *((_QWORD *)&v22 + 1) = v12;
        }
        else
        {
          W2A(v9, pszSrc, 260);
          GetVersionFromString(pszSrc, v23, &v23[1], v10);
        }
      }
      else
      {
        LODWORD(v24) = StrToIntW(v9);
      }
LABEL_44:
      if ( v8 + 1 <= v2 )
      {
        if ( !lpsz[1] )
          goto LABEL_49;
        if ( lpsz[0] )
          goto LABEL_50;
        lpsz[0] = lpsz[1];
LABEL_49:
        if ( lpsz[0] )
        {
LABEL_50:
          v13 = lpsz[1];
          if ( !lpsz[1] )
            v13 = lpsz[0];
          lpsz[1] = v13;
        }
        if ( v4 )
        {
          v14 = (int (__fastcall ***)(_QWORD, GUID *, LPOLESTR *))*((_QWORD *)this + 6);
          v25 = 0;
          v19[0] = 0;
          if ( (**v14)(v14, &IID_IServiceProvider, v19) < 0
            || (*(int (__fastcall **)(LPOLESTR, GUID *, GUID *, __int64 *))(*(_QWORD *)v19[0] + 24LL))(
                 v19[0],
                 &IID_IInternetHostSecurityManager,
                 &IID_IInternetHostSecurityManager,
                 &v25) < 0 )
          {
            started = -2146762485;
            goto LABEL_66;
          }
          (*(void (__fastcall **)(LPOLESTR))(*(_QWORD *)v19[0] + 16LL))(v19[0]);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          v16 = *(_QWORD *)((char *)this + 5004) - *(_QWORD *)&GUID_NULL.Data1;
          if ( !v16 )
            v16 = *(_QWORD *)((char *)this + 5012) - *(_QWORD *)GUID_NULL.Data4;
          if ( !v16 )
            CLSIDFromString(lpsz[1], (LPCLSID)((char *)this + 5004));
          started = CCdlProtocol::StartDownload(this, (struct CodeDownloadDataTag *)lpsz);
        }
        else
        {
          started = -2147221020;
        }
        if ( started == -2147483638 )
          return started;
        goto LABEL_66;
      }
      v6 = v8;
      *v8 = 0;
    }
    lpsz[1] = v9;
LABEL_36:
    v4 = 1;
    goto LABEL_44;
  }
  v3 = wcschr(v2, 0x3Fu);
  if ( v3 )
  {
    v2 = v3 + 1;
    goto LABEL_5;
  }
LABEL_65:
  started = -2147221020;
LABEL_66:
  *((_DWORD *)this + 1248) = 0;
  if ( *((_QWORD *)this + 6) )
  {
    v17 = *(_QWORD *)((char *)this + 5004) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v17 )
      v17 = *(_QWORD *)((char *)this + 5012) - *(_QWORD *)GUID_NULL.Data4;
    if ( v17 )
    {
      v19[0] = 0;
      StringFromCLSID((const IID *const)((char *)this + 5004), v19);
      (*(void (__fastcall **)(_QWORD, __int64, LPOLESTR))(**((_QWORD **)this + 6) + 32LL))(
        *((_QWORD *)this + 6),
        28,
        v19[0]);
      operator delete(v19[0]);
    }
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 6) + 48LL))(
      *((_QWORD *)this + 6),
      started,
      0,
      0);
  }
  return started;
}

```

## disassembly

```asm
0x1800a8674  push    rbp
0x1800a8676  push    rbx
0x1800a8677  push    rsi
0x1800a8678  push    rdi
0x1800a8679  push    r12
0x1800a867b  push    r13
0x1800a867d  push    r14
0x1800a867f  push    r15
0x1800a8681  lea     rbp, [rsp-1108h]
0x1800a8689  mov     eax, 1208h
0x1800a868e  call    _alloca_probe
0x1800a8693  sub     rsp, rax
0x1800a8696  mov     rax, cs:__security_cookie
0x1800a869d  xor     rax, rsp
0x1800a86a0  mov     [rbp+1140h+var_50], rax
0x1800a86a7  mov     r15, rcx
0x1800a86aa  lea     r8, [rcx+0E0h]; unsigned __int16 *
0x1800a86b1  xorps   xmm0, xmm0
0x1800a86b4  lea     rcx, [rbp+1140h+Str]; unsigned __int16 *
0x1800a86bb  xor     r13d, r13d
0x1800a86be  movdqa  xmmword ptr [rsp+1240h+lpsz], xmm0
0x1800a86c4  xorps   xmm1, xmm1
0x1800a86c7  movdqa  [rsp+1240h+var_11E0], xmm0
0x1800a86cd  mov     edx, 824h; unsigned __int64
0x1800a86d2  movdqa  [rsp+1240h+var_11F0], xmm1
0x1800a86d8  mov     qword ptr [rsp+1240h+var_11D0], r13
0x1800a86dd  mov     [rsp+1240h+var_11C8], r13
0x1800a86e2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a86e7  lea     edx, [r13+3Ah]; Ch
0x1800a86eb  lea     rcx, [rbp+1140h+Str]; Str
0x1800a86f2  call    cs:__imp_wcschr
0x1800a86f9  nop     dword ptr [rax+rax+00h]
0x1800a86fe  lea     r8d, [r13+2]; cchCount2
0x1800a8702  lea     rdx, asc_18014260C; "//"
0x1800a8709  lea     rbx, [rax+2]
0x1800a870d  mov     rcx, rbx; lpString1
0x1800a8710  call    ?StrCmpNIIW@@YAHPEBG0K@Z; StrCmpNIIW(ushort const *,ushort const *,ulong)
0x1800a8715  test    eax, eax
0x1800a8717  jz      short loc_1800A8730
0x1800a8719  lea     r8d, [r13+2]; cchCount2
0x1800a871d  mov     rcx, rbx; lpString1
0x1800a8720  lea     rdx, asc_1801405A0; "\\\\"
0x1800a8727  call    ?StrCmpNIIW@@YAHPEBG0K@Z; StrCmpNIIW(ushort const *,ushort const *,ulong)
0x1800a872c  test    eax, eax
0x1800a872e  jnz     short loc_1800A8754
0x1800a8730  mov     edx, 3Fh ; '?'; Ch
0x1800a8735  mov     rcx, rbx; Str
0x1800a8738  call    cs:__imp_wcschr
0x1800a873f  nop     dword ptr [rax+rax+00h]
0x1800a8744  mov     rbx, rax
0x1800a8747  test    rax, rax
0x1800a874a  jz      loc_1800A8A97
0x1800a8750  add     rbx, 2
0x1800a8754  mov     r12d, r13d
0x1800a8757  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a875b  inc     rax
0x1800a875e  cmp     [rbx+rax*2], r13w
0x1800a8763  jnz     short loc_1800A875B
0x1800a8765  lea     rcx, [rbx+rax*2]
0x1800a8769  lea     rdx, [rcx-2]
0x1800a876d  cmp     rdx, rbx
0x1800a8770  jb      short loc_1800A8785
0x1800a8772  cmp     word ptr [rdx], 23h ; '#'
0x1800a8776  jz      short loc_1800A877E
0x1800a8778  sub     rdx, 2
0x1800a877c  jmp     short loc_1800A876D
0x1800a877e  mov     [rdx], r13w
0x1800a8782  mov     rcx, rdx
0x1800a8785  cmp     rcx, rbx
0x1800a8788  jb      loc_1800A8A97
0x1800a878e  cmp     word ptr [rcx], 3Dh ; '='
0x1800a8792  jz      short loc_1800A87AC
0x1800a8794  cmp     word ptr [rcx], 3Bh ; ';'
0x1800a8798  jz      short loc_1800A87A3
0x1800a879a  sub     rcx, 2
0x1800a879e  cmp     rcx, rbx
0x1800a87a1  jnb     short loc_1800A878E
0x1800a87a3  cmp     rcx, rbx
0x1800a87a6  jb      loc_1800A8A97
0x1800a87ac  cmp     word ptr [rcx], 3Bh ; ';'
0x1800a87b0  jz      loc_1800A8A97
0x1800a87b6  mov     [rcx], r13w
0x1800a87ba  mov     r14, rcx
0x1800a87bd  movzx   eax, word ptr [r14]
0x1800a87c1  mov     edx, 0FFFDh
0x1800a87c6  sub     ax, 3Bh ; ';'
0x1800a87ca  test    dx, ax
0x1800a87cd  jz      short loc_1800A87D8
0x1800a87cf  sub     r14, 2
0x1800a87d3  cmp     r14, rbx
0x1800a87d6  jnb     short loc_1800A87BD
0x1800a87d8  cmp     word ptr [r14], 3Dh ; '='
0x1800a87dd  jz      loc_1800A8A97
0x1800a87e3  lea     rdi, [rcx+2]
0x1800a87e7  lea     rsi, [r14+2]
0x1800a87eb  mov     rdx, rsi; lpString2
0x1800a87ee  lea     rcx, aCodebase_1; "codebase"
0x1800a87f5  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x1800a87fa  test    eax, eax
0x1800a87fc  jnz     short loc_1800A8808
0x1800a87fe  mov     qword ptr [rsp+1240h+var_11F0], rdi
0x1800a8803  jmp     loc_1800A897F
0x1800a8808  mov     rdx, rsi; lpString2
0x1800a880b  lea     rcx, aClsid; "clsid"
0x1800a8812  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x1800a8817  test    eax, eax
0x1800a8819  jnz     short loc_1800A8825
0x1800a881b  mov     [rsp+1240h+lpsz+8], rdi
0x1800a8820  jmp     loc_1800A88F3
0x1800a8825  mov     rdx, rsi; lpString2
0x1800a8828  lea     rcx, aMimetype; "mimetype"
0x1800a882f  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x1800a8834  test    eax, eax
0x1800a8836  jnz     short loc_1800A8842
0x1800a8838  mov     qword ptr [rsp+1240h+var_11F0+8], rdi
0x1800a883d  jmp     loc_1800A88F3
0x1800a8842  mov     rdx, rsi; lpString2
0x1800a8845  lea     rcx, aExtension; "extension"
0x1800a884c  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x1800a8851  test    eax, eax
0x1800a8853  jnz     short loc_1800A885F
0x1800a8855  mov     qword ptr [rsp+1240h+var_11E0], rdi
0x1800a885a  jmp     loc_1800A88F3
0x1800a885f  mov     rdx, rsi; lpString2
0x1800a8862  lea     rcx, aVerms; "verMS"
0x1800a8869  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x1800a886e  test    eax, eax
0x1800a8870  jnz     short loc_1800A889D
0x1800a8872  mov     r8d, 104h; int
0x1800a8878  lea     rdx, [rbp+1140h+pszSrc]; char *
0x1800a887c  mov     rcx, rdi; lpWideCharStr
0x1800a887f  call    ?W2A@@YAXPEBGPEADH@Z; W2A(ushort const *,char *,int)
0x1800a8884  lea     rcx, [rbp+1140h+pszSrc]; pszSrc
0x1800a8888  call    cs:__imp_StrToIntA
0x1800a888f  nop     dword ptr [rax+rax+00h]
0x1800a8894  mov     [rsp+1240h+var_11D0], eax
0x1800a8898  jmp     loc_1800A897F
0x1800a889d  mov     rdx, rsi; lpString2
0x1800a88a0  lea     rcx, aVerls; "verLS"
0x1800a88a7  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x1800a88ac  test    eax, eax
0x1800a88ae  jnz     short loc_1800A88DB
0x1800a88b0  mov     r8d, 104h; int
0x1800a88b6  lea     rdx, [rbp+1140h+pszSrc]; char *
0x1800a88ba  mov     rcx, rdi; lpWideCharStr
0x1800a88bd  call    ?W2A@@YAXPEBGPEADH@Z; W2A(ushort const *,char *,int)
0x1800a88c2  lea     rcx, [rbp+1140h+pszSrc]; pszSrc
0x1800a88c6  call    cs:__imp_StrToIntA
0x1800a88cd  nop     dword ptr [rax+rax+00h]
0x1800a88d2  mov     [rsp+1240h+var_11D0+4], eax
0x1800a88d6  jmp     loc_1800A897F
0x1800a88db  mov     rdx, rsi; lpString2
0x1800a88de  lea     rcx, aDistunit; "distunit"
0x1800a88e5  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x1800a88ea  test    eax, eax
0x1800a88ec  jnz     short loc_1800A88FE
0x1800a88ee  mov     [rsp+1240h+lpsz], rdi
0x1800a88f3  mov     r12d, 1
0x1800a88f9  jmp     loc_1800A897F
0x1800a88fe  mov     rdx, rsi; lpString2
0x1800a8901  lea     rcx, aFlags_0; "flags"
0x1800a8908  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x1800a890d  test    eax, eax
0x1800a890f  jnz     short loc_1800A8926
0x1800a8911  mov     rcx, rdi; pszSrc
0x1800a8914  call    cs:__imp_StrToIntW
0x1800a891b  nop     dword ptr [rax+rax+00h]
0x1800a8920  mov     dword ptr [rsp+1240h+var_11C8], eax
0x1800a8924  jmp     short loc_1800A897F
0x1800a8926  mov     rdx, rsi; lpString2
0x1800a8929  lea     rcx, aVersion; "version"
0x1800a8930  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x1800a8935  test    eax, eax
0x1800a8937  jnz     short loc_1800A8960
0x1800a8939  mov     r8d, 104h; int
0x1800a893f  lea     rdx, [rbp+1140h+pszSrc]; char *
0x1800a8943  mov     rcx, rdi; lpWideCharStr
0x1800a8946  call    ?W2A@@YAXPEBGPEADH@Z; W2A(ushort const *,char *,int)
0x1800a894b  lea     r8, [rsp+1240h+var_11D0+4]; unsigned int *
0x1800a8950  lea     rdx, [rsp+1240h+var_11D0]; unsigned int *
0x1800a8955  lea     rcx, [rbp+1140h+pszSrc]; lpString1
0x1800a8959  call    ?GetVersionFromString@@YAJPEBDPEAK1D@Z; GetVersionFromString(char const *,ulong *,ulong *,char)
0x1800a895e  jmp     short loc_1800A897F
0x1800a8960  mov     rdx, rsi; lpString2
0x1800a8963  lea     rcx, aDllname; "dllname"
0x1800a896a  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x1800a896f  mov     rcx, qword ptr [rsp+1240h+var_11E0+8]
0x1800a8974  test    eax, eax
0x1800a8976  cmovz   rcx, rdi
0x1800a897a  mov     qword ptr [rsp+1240h+var_11E0+8], rcx
0x1800a897f  cmp     rsi, rbx
0x1800a8982  jbe     short loc_1800A8990
0x1800a8984  mov     rcx, r14
0x1800a8987  mov     [r14], r13w
0x1800a898b  jmp     loc_1800A8785
0x1800a8990  mov     rax, [rsp+1240h+lpsz+8]
0x1800a8995  test    rax, rax
0x1800a8998  jz      short loc_1800A89A6
0x1800a899a  cmp     [rsp+1240h+lpsz], r13
0x1800a899f  jnz     short loc_1800A89AD
0x1800a89a1  mov     [rsp+1240h+lpsz], rax
0x1800a89a6  cmp     [rsp+1240h+lpsz], r13
0x1800a89ab  jz      short loc_1800A89C0
0x1800a89ad  mov     rax, [rsp+1240h+lpsz+8]
0x1800a89b2  test    rax, rax
0x1800a89b5  cmovz   rax, [rsp+1240h+lpsz]
0x1800a89bb  mov     [rsp+1240h+lpsz+8], rax
0x1800a89c0  test    r12d, r12d
0x1800a89c3  jz      loc_1800A8A84
0x1800a89c9  mov     rcx, [r15+30h]
0x1800a89cd  lea     r8, [rsp+1240h+var_1210]
0x1800a89d2  mov     [rbp+1140h+var_11C0], r13
0x1800a89d6  lea     rdx, IID_IServiceProvider
0x1800a89dd  mov     [rsp+1240h+var_1210], r13
0x1800a89e2  mov     rax, [rcx]
0x1800a89e5  mov     rax, [rax]
0x1800a89e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a89ed  test    eax, eax
0x1800a89ef  jns     short loc_1800A89FB
0x1800a89f1  mov     ebx, 800B010Bh
0x1800a89f6  jmp     loc_1800A8A9C
0x1800a89fb  mov     rcx, [rsp+1240h+var_1210]
0x1800a8a00  lea     rdx, IID_IInternetHostSecurityManager
0x1800a8a07  lea     r9, [rbp+1140h+var_11C0]
0x1800a8a0b  mov     r8, rdx
0x1800a8a0e  mov     rax, [rcx]
0x1800a8a11  mov     rax, [rax+18h]
0x1800a8a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8a1a  test    eax, eax
0x1800a8a1c  js      short loc_1800A89F1
0x1800a8a1e  mov     rcx, [rsp+1240h+var_1210]
0x1800a8a23  mov     rax, [rcx]
0x1800a8a26  mov     rax, [rax+10h]
0x1800a8a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8a2f  mov     rcx, [rbp+1140h+var_11C0]
0x1800a8a33  mov     rax, [rcx]
0x1800a8a36  mov     rax, [rax+10h]
0x1800a8a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8a3f  lea     rdx, [r15+138Ch]; pclsid
0x1800a8a46  mov     rax, [rdx]
0x1800a8a49  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800a8a50  jnz     short loc_1800A8A5D
0x1800a8a52  mov     rax, [rdx+8]
0x1800a8a56  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800a8a5d  test    rax, rax
0x1800a8a60  jnz     short loc_1800A8A73
0x1800a8a62  mov     rcx, [rsp+1240h+lpsz+8]; lpsz
0x1800a8a67  call    cs:__imp_CLSIDFromString
0x1800a8a6e  nop     dword ptr [rax+rax+00h]
0x1800a8a73  lea     rdx, [rsp+1240h+lpsz]; struct CodeDownloadDataTag *
0x1800a8a78  mov     rcx, r15; this
0x1800a8a7b  call    ?StartDownload@CCdlProtocol@@AEAAJAEAUCodeDownloadDataTag@@@Z; CCdlProtocol::StartDownload(CodeDownloadDataTag &)
0x1800a8a80  mov     ebx, eax
0x1800a8a82  jmp     short loc_1800A8A89
0x1800a8a84  mov     ebx, 800401E4h
0x1800a8a89  cmp     ebx, 8000000Ah
0x1800a8a8f  jz      loc_1800A8B1E
0x1800a8a95  jmp     short loc_1800A8A9C
0x1800a8a97  mov     ebx, 800401E4h
0x1800a8a9c  mov     [r15+1380h], r13d
0x1800a8aa3  cmp     [r15+30h], r13
0x1800a8aa7  jz      short loc_1800A8B1E
0x1800a8aa9  lea     rcx, [r15+138Ch]; rclsid
0x1800a8ab0  mov     rax, [rcx]
0x1800a8ab3  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800a8aba  jnz     short loc_1800A8AC7
0x1800a8abc  mov     rax, [rcx+8]
0x1800a8ac0  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800a8ac7  test    rax, rax
0x1800a8aca  jz      short loc_1800A8B06
0x1800a8acc  lea     rdx, [rsp+1240h+var_1210]; lplpsz
0x1800a8ad1  mov     [rsp+1240h+var_1210], r13
0x1800a8ad6  call    cs:__imp_StringFromCLSID
0x1800a8add  nop     dword ptr [rax+rax+00h]
0x1800a8ae2  mov     rcx, [r15+30h]
0x1800a8ae6  mov     edx, 1Ch
0x1800a8aeb  mov     r8, [rsp+1240h+var_1210]
0x1800a8af0  mov     rax, [rcx]
0x1800a8af3  mov     rax, [rax+20h]
0x1800a8af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8afc  mov     rcx, [rsp+1240h+var_1210]; void *
0x1800a8b01  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a8b06  mov     rcx, [r15+30h]
0x1800a8b0a  xor     r9d, r9d
0x1800a8b0d  xor     r8d, r8d
0x1800a8b10  mov     rdx, [rcx]
0x1800a8b13  mov     rax, [rdx+30h]
0x1800a8b17  mov     edx, ebx
0x1800a8b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8b1e  mov     eax, ebx
0x1800a8b20  mov     rcx, [rbp+1140h+var_50]
0x1800a8b27  xor     rcx, rsp; StackCookie
0x1800a8b2a  call    __security_check_cookie
0x1800a8b2f  add     rsp, 1208h
0x1800a8b36  pop     r15
0x1800a8b38  pop     r14
0x1800a8b3a  pop     r13
0x1800a8b3c  pop     r12
0x1800a8b3e  pop     rdi
0x1800a8b3f  pop     rsi
  ... truncated ...
```
