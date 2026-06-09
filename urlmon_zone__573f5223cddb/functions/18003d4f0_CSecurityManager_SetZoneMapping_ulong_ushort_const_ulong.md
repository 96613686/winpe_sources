# CSecurityManager::SetZoneMapping(ulong,ushort const *,ulong)

- ea: `0x18003d4f0`
- end: `0x18003dcb5`
- name: `?SetZoneMapping@CSecurityManager@@UEAAJKPEBGK@Z`
- size: `1989`
- prototype: `__int64 __fastcall(CSecurityManager *__hidden this, unsigned int, LPCWSTR pwzURI, unsigned int)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001a300`
- `0x18001cb00`
- `0x18003bef0`
- `0x18003bf28`
- `0x18003d4f0`
- `0x18003e100`
- `0x18003e540`
- `0x18005c800`
- `0x18005c8d0`
- `0x18006b840`
- `0x180080488`
- `0x180083584`
- `0x1800939bc`
- `0x1800a5544`
- `0x180108988`
- `0x180109a28`
- `0x180109c0c`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!CreateUri` at `0x18003d5f1`
- `iertutil!CreateUri` at `0x18003d5f1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRChrW` at `0x18003d865`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRChrW` at `0x18003d981`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRChrW` at `0x18003d865`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRChrW` at `0x18003d981`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18003d99a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18003d99a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dbb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dbb8`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003db2e`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003db58`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003db2e`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003db58`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003dad5`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003dbe9`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003dc0d`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003dc46`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003dc66`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003dad5`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003dbe9`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003dc0d`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003dc46`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003dc66`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCreateUSKeyW` at `0x18003da93`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCreateUSKeyW` at `0x18003da93`

## pseudocode

```c
__int64 __fastcall CSecurityManager::SetZoneMapping(
        CSecurityManager *this,
        unsigned int a2,
        LPCWSTR pwzURI,
        unsigned int a4)
{
  int SecurityUrl; // edi
  __int64 v9; // rcx
  int v10; // eax
  BOOL v11; // r14d
  unsigned int v12; // r13d
  DWORD v13; // eax
  IUri *v14; // rbx
  struct IUri *v15; // rbx
  unsigned int v16; // r8d
  int v18; // edx
  int v19; // r9d
  PWSTR v20; // rdx
  __int64 v21; // rax
  __int64 v22; // r9
  unsigned int i; // r8d
  __int64 v24; // rcx
  WCHAR v25; // ax
  int v26; // eax
  bool v27; // cc
  PWSTR v28; // rdi
  PWSTR v29; // rax
  void *v30; // rdx
  int v31; // r9d
  void *v32; // r8
  void *v33; // rdi
  BOOL v34; // eax
  signed int LastError; // eax
  unsigned int v36; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned int *v37; // [rsp+38h] [rbp-C8h] BYREF
  HUSKEY v38; // [rsp+40h] [rbp-C0h]
  BOOL fIgnoreHKCU; // [rsp+48h] [rbp-B8h]
  int v40; // [rsp+4Ch] [rbp-B4h]
  int v41; // [rsp+50h] [rbp-B0h]
  HUSKEY phNewUSKey; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned int *v43; // [rsp+60h] [rbp-A0h] BYREF
  HUSKEY hUSKey; // [rsp+68h] [rbp-98h]
  int v45; // [rsp+70h] [rbp-90h]
  int v46; // [rsp+74h] [rbp-8Ch]
  int v47; // [rsp+78h] [rbp-88h]
  IUri *ppURI; // [rsp+80h] [rbp-80h] BYREF
  IUri *ppSecUri; // [rsp+88h] [rbp-78h] BYREF
  int v50; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v51; // [rsp+98h] [rbp-68h]
  _WORD *v52; // [rsp+A0h] [rbp-60h]
  int v53; // [rsp+CCh] [rbp-34h]
  char v54; // [rsp+E4h] [rbp-1Ch]
  int v55; // [rsp+F8h] [rbp-8h]
  int v56; // [rsp+580h] [rbp+480h] BYREF
  _BYTE v57[1468]; // [rsp+584h] [rbp+484h] BYREF
  WCHAR pszStart[264]; // [rsp+B40h] [rbp+A40h] BYREF

  CSharedMem::IncrementCounter((CSharedMem *)&g_SharedMem, 4u);
  if ( !*((_QWORD *)this + 12) )
  {
    v9 = *((_QWORD *)this + 11);
    if ( v9 || (v9 = *((_QWORD *)this + 10)) != 0 || (v9 = *((_QWORD *)this + 9)) != 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPCWSTR, _QWORD))(*(_QWORD *)v9 + 72LL))(v9, a2, pwzURI, a4);
      SecurityUrl = v10;
      if ( v10 != -2146697199 )
      {
        if ( !v10 )
          CSharedMem::IncrementCounter((CSharedMem *)&g_SharedMem, 0x14u);
        return (unsigned int)SecurityUrl;
      }
    }
    v11 = (a2 & 0x100) != 0 && a2 <= 0x3E7;
    ppURI = 0;
    v12 = a2 & 0xFFFFFEFF;
    ppSecUri = 0;
    if ( !v11 )
      v12 = a2;
    v13 = HelperAddUriDefaultFlags(0x3002B80u, 6u);
    SecurityUrl = CreateUri(pwzURI, v13, 0, &ppURI);
    if ( SecurityUrl < 0 )
      return (unsigned int)SecurityUrl;
    v14 = ppURI;
    SecurityUrl = CoInternetGetSecurityUrlEx(ppURI, &ppSecUri, PSU_DEFAULT, 0);
    ((void (__fastcall *)(IUri *))v14->lpVtbl->Release)(v14);
    if ( SecurityUrl < 0 )
      return (unsigned int)SecurityUrl;
    v15 = ppSecUri;
    memset_0(&v50, 0, 0x4E8u);
    SecurityUrl = ZONEMAP_COMPONENTS::Crack((ZONEMAP_COMPONENTS *)&v50, v15, v16, 1);
    if ( SecurityUrl )
      goto LABEL_18;
    memset_0(v57, 0, 0x5B0u);
    v56 = 1460;
    if ( !(unsigned int)CSecurityManager::EnsureZoneManager(this) )
    {
      ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS((ZONEMAP_COMPONENTS *)&v50);
      ((void (__fastcall *)(struct IUri *))v15->lpVtbl->Release)(v15);
      return 2147942414LL;
    }
    v18 = CSecurityManager::s_fESCEnabled;
    if ( (!v11 || v12 != 2 || CSecurityManager::s_fESCEnabled) && (a4 & 1) == 0 )
    {
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)this + 8) + 24LL))(
             *((_QWORD *)this + 8),
             v12,
             &v56) >= 0
        && (v57[1452] & 4) != 0
        && v50 != 11 )
      {
        ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS((ZONEMAP_COMPONENTS *)&v50);
        ((void (__fastcall *)(struct IUri *))v15->lpVtbl->Release)(v15);
        return 2147942405LL;
      }
      v18 = CSecurityManager::s_fESCEnabled;
    }
    if ( (v54 & 2) != 0 )
    {
      SecurityUrl = CSecurityManager::AddDeleteIPRule(this, (struct ZONEMAP_COMPONENTS *)&v50, v12, a4);
LABEL_18:
      ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS((ZONEMAP_COMPONENTS *)&v50);
      ((void (__fastcall *)(struct IUri *))v15->lpVtbl->Release)(v15);
      return (unsigned int)SecurityUrl;
    }
    if ( v55 )
    {
      ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS((ZONEMAP_COMPONENTS *)&v50);
      ((void (__fastcall *)(struct IUri *))v15->lpVtbl->Release)(v15);
      return 2147942487LL;
    }
    v37 = &CRegKey::`vftable';
    v43 = &CRegKey::`vftable';
    fIgnoreHKCU = g_bUseHKLMOnly;
    v38 = 0;
    v41 = 0;
    v40 = CSecurityManager::s_fUsePoliciesZoneMap;
    v45 = g_bUseHKLMOnly;
    hUSKey = 0;
    v47 = 0;
    v46 = CSecurityManager::s_fUsePoliciesZoneMap;
    if ( (a4 & 1) != 0 )
    {
      if ( v11 || (v19 = 0, v18) )
        v19 = 1;
      SecurityUrl = CSecurityManager::GetDomainKeyNameForDeleting(
                      (const struct ZONEMAP_COMPONENTS *)&v50,
                      pszStart,
                      (unsigned int)&CRegKey::`vftable',
                      v19);
      if ( SecurityUrl < 0 )
      {
LABEL_39:
        v43 = &CRegKey::`vftable';
        CRegKey::Close((CRegKey *)&v43);
        v37 = &CRegKey::`vftable';
        CRegKey::Close((CRegKey *)&v37);
        goto LABEL_18;
      }
      if ( CRegKey::Open((CRegKey *)&v37, *((void **)this + 14), pszStart, 0x2001Fu) == 2 )
      {
        if ( v53 == 1 && *v52 == 42 )
        {
          v20 = StrRChrW(pszStart, 0, 0x5Cu);
          if ( v20 )
          {
            v21 = -1;
            do
              ++v21;
            while ( v20[v21] );
            if ( (unsigned int)v21 > 1 && v20[1] == 42 )
            {
              v22 = (unsigned int)(v21 - 2);
              for ( i = 1; i < (unsigned int)v22; v20[v24] = v25 )
              {
                v24 = i;
                v25 = v20[i + 2];
                ++i;
              }
              v20[v22] = 0;
            }
          }
        }
        if ( CRegKey::Open((CRegKey *)&v37, *((void **)this + 14), pszStart, 0x2001Fu) == 2 )
        {
LABEL_52:
          v43 = &CRegKey::`vftable';
          CRegKey::Close((CRegKey *)&v43);
          v37 = &CRegKey::`vftable';
          CRegKey::Close((CRegKey *)&v37);
          ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS((ZONEMAP_COMPONENTS *)&v50);
          ((void (__fastcall *)(struct IUri *))v15->lpVtbl->Release)(v15);
          return 0;
        }
      }
      v26 = CRegKey::DeleteValue((CRegKey *)&v37, v51);
      SecurityUrl = v26;
      v27 = v26 <= 0;
      if ( !v26 )
      {
        v36 = 0;
        if ( !CRegKey::QuerySubKeyInfo((CRegKey *)&v37, 0, 0, &v36) && !v36 )
        {
          CRegKey::Close((CRegKey *)&v37);
          CRegKey::DeleteEmptyKey((CSecurityManager *)((char *)this + 104), pszStart);
        }
        v28 = StrRChrW(pszStart, 0, 0x5Cu);
        v29 = StrChrW(pszStart, 0x5Cu);
        if ( v28 )
        {
          if ( v29 )
          {
            if ( v28 != v29 )
            {
              *v28 = 0;
              v30 = (void *)*((_QWORD *)this + 14);
              v36 = 0;
              if ( !CRegKey::Open((CRegKey *)&v43, v30, pszStart, 0x2001Fu)
                && !CRegKey::QuerySubKeyInfo((CRegKey *)&v43, 0, 0, &v36)
                && !v36 )
              {
                CRegKey::Close((CRegKey *)&v43);
                CRegKey::DeleteEmptyKey((CSecurityManager *)((char *)this + 104), pszStart);
              }
            }
          }
        }
        goto LABEL_64;
      }
LABEL_65:
      if ( !v27 )
      {
        SecurityUrl = (unsigned __int16)v26;
LABEL_92:
        SecurityUrl |= 0x80070000;
        goto LABEL_93;
      }
      goto LABEL_93;
    }
    if ( v11 || (v31 = 0, v18) )
      v31 = 1;
    SecurityUrl = CSecurityManager::GetDomainKeyNameForAdding(
                    (const struct ZONEMAP_COMPONENTS *)&v50,
                    pszStart,
                    (unsigned int)&CRegKey::`vftable',
                    v31);
    if ( SecurityUrl < 0 )
      goto LABEL_39;
    v32 = (void *)*((_QWORD *)this + 14);
    phNewUSKey = 0;
    SecurityUrl = SHRegCreateUSKeyW(pszStart, 0x2001Fu, v32, &phNewUSKey, fIgnoreHKCU ? 8 : 2);
    if ( SecurityUrl
      || (SecurityUrl = (*((__int64 (__fastcall **)(const unsigned int **))v37 + 2))(&v37), v38 = phNewUSKey,
                                                                                            SecurityUrl) )
    {
      if ( SecurityUrl > 0 )
      {
        SecurityUrl = (unsigned __int16)SecurityUrl;
        goto LABEL_92;
      }
LABEL_93:
      v43 = &CRegKey::`vftable';
      if ( hUSKey )
      {
        SHRegCloseUSKey(hUSKey);
        hUSKey = 0;
      }
      v37 = &CRegKey::`vftable';
      if ( v38 )
      {
        SHRegCloseUSKey(v38);
        v38 = 0;
      }
      ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS((ZONEMAP_COMPONENTS *)&v50);
      ((void (__fastcall *)(struct IUri *))v15->lpVtbl->Release)(v15);
      return (unsigned int)SecurityUrl;
    }
    if ( phNewUSKey )
    {
      SHRegCloseUSKey(phNewUSKey);
      v38 = 0;
    }
    v33 = (void *)*((_QWORD *)this + 22);
    phNewUSKey = 0;
    (*((void (__fastcall **)(const unsigned int **))v37 + 2))(&v37);
    if ( v40 )
    {
      v34 = fIgnoreHKCU;
      if ( fIgnoreHKCU )
        goto LABEL_79;
      if ( !SHRegOpenUSKeyW(pszStart, 0x2001Fu, v33, &phNewUSKey, 1) )
      {
LABEL_80:
        v38 = phNewUSKey;
        v36 = 0;
        if ( !CRegKey::QueryValue((CRegKey *)&v37, &v36, v51) )
        {
          SecurityUrl = -2147024816;
          goto LABEL_93;
        }
        v26 = CRegKey::SetValue((CRegKey *)&v37, v12, v51);
        SecurityUrl = v26;
        v27 = v26 <= 0;
        if ( !v26 )
        {
LABEL_64:
          CSharedMem::IncrementCounter((CSharedMem *)&g_SharedMem, 0x14u);
          goto LABEL_52;
        }
        goto LABEL_65;
      }
    }
    v34 = fIgnoreHKCU;
LABEL_79:
    if ( SHRegOpenUSKeyW(pszStart, 0x2001Fu, v33, &phNewUSKey, v34) )
    {
      LastError = GetLastError();
      SecurityUrl = LastError;
      if ( LastError > 0 )
        SecurityUrl = (unsigned __int16)LastError | 0x80070000;
      v43 = &CRegKey::`vftable';
      if ( hUSKey )
      {
        SHRegCloseUSKey(hUSKey);
        hUSKey = 0;
      }
      v37 = &CRegKey::`vftable';
      if ( v38 )
      {
        SHRegCloseUSKey(v38);
        v38 = 0;
      }
      goto LABEL_18;
    }
    goto LABEL_80;
  }
  return (unsigned int)-2147024891;
}

```

## disassembly

```asm
0x18003d4f0  push    rbp
0x18003d4f2  push    rbx
0x18003d4f3  push    rsi
0x18003d4f4  push    rdi
0x18003d4f5  push    r12
0x18003d4f7  push    r13
0x18003d4f9  push    r14
0x18003d4fb  push    r15
0x18003d4fd  lea     rbp, [rsp-0C68h]
0x18003d505  sub     rsp, 0D68h
0x18003d50c  mov     rax, cs:__security_cookie
0x18003d513  xor     rax, rsp
0x18003d516  mov     [rbp+0CA0h+var_50], rax
0x18003d51d  mov     ebx, edx
0x18003d51f  mov     rsi, rcx
0x18003d522  mov     edx, 4; unsigned int
0x18003d527  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x18003d52e  mov     r15d, r9d
0x18003d531  mov     r12, r8
0x18003d534  call    ?IncrementCounter@CSharedMem@@QEAAHK@Z; CSharedMem::IncrementCounter(ulong)
0x18003d539  cmp     qword ptr [rsi+60h], 0
0x18003d53e  jz      short loc_18003D54A
0x18003d540  mov     edi, 80070005h
0x18003d545  jmp     loc_18003DC8F
0x18003d54a  mov     rcx, [rsi+58h]
0x18003d54e  test    rcx, rcx
0x18003d551  jnz     short loc_18003D565
0x18003d553  mov     rcx, [rsi+50h]
0x18003d557  test    rcx, rcx
0x18003d55a  jnz     short loc_18003D565
0x18003d55c  mov     rcx, [rsi+48h]
0x18003d560  test    rcx, rcx
0x18003d563  jz      short loc_18003D59E
0x18003d565  mov     rax, [rcx]
0x18003d568  mov     r9d, r15d
0x18003d56b  mov     r8, r12
0x18003d56e  mov     edx, ebx
0x18003d570  mov     rax, [rax+48h]
0x18003d574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d579  mov     edi, eax
0x18003d57b  cmp     eax, 800C0011h
0x18003d580  jz      short loc_18003D59E
0x18003d582  test    eax, eax
0x18003d584  jnz     loc_18003DC8F
0x18003d58a  lea     edx, [rax+14h]; unsigned int
0x18003d58d  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x18003d594  call    ?IncrementCounter@CSharedMem@@QEAAHK@Z; CSharedMem::IncrementCounter(ulong)
0x18003d599  jmp     loc_18003DC8F
0x18003d59e  bt      ebx, 8
0x18003d5a2  jnb     short loc_18003D5B4
0x18003d5a4  cmp     ebx, 3E7h
0x18003d5aa  ja      short loc_18003D5B4
0x18003d5ac  mov     r14d, 1
0x18003d5b2  jmp     short loc_18003D5B7
0x18003d5b4  xor     r14d, r14d
0x18003d5b7  mov     r13d, ebx
0x18003d5ba  mov     [rbp+0CA0h+ppURI], 0
0x18003d5c2  btr     r13d, 8
0x18003d5c7  mov     [rbp+0CA0h+ppSecUri], 0
0x18003d5cf  test    r14d, r14d
0x18003d5d2  mov     edx, 6; unsigned int
0x18003d5d7  mov     ecx, 3002B80h; unsigned int
0x18003d5dc  cmovz   r13d, ebx
0x18003d5e0  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x18003d5e5  mov     edx, eax; dwFlags
0x18003d5e7  lea     r9, [rbp+0CA0h+ppURI]; ppURI
0x18003d5eb  mov     rcx, r12; pwzURI
0x18003d5ee  xor     r8d, r8d; dwReserved
0x18003d5f1  call    cs:__imp_CreateUri
0x18003d5f8  nop     dword ptr [rax+rax+00h]
0x18003d5fd  xor     r12d, r12d
0x18003d600  mov     edi, eax
0x18003d602  test    eax, eax
0x18003d604  js      loc_18003DC8F
0x18003d60a  mov     rbx, [rbp+0CA0h+ppURI]
0x18003d60e  lea     r8d, [r12+1]; psuAction
0x18003d613  mov     rcx, rbx; pUri
0x18003d616  lea     rdx, [rbp+0CA0h+ppSecUri]; ppSecUri
0x18003d61a  xor     r9d, r9d; dwReserved
0x18003d61d  call    CoInternetGetSecurityUrlEx
0x18003d622  mov     edi, eax
0x18003d624  mov     rcx, rbx
0x18003d627  mov     rax, [rbx]
0x18003d62a  mov     rax, [rax+10h]
0x18003d62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d633  test    edi, edi
0x18003d635  js      loc_18003DC8F
0x18003d63b  mov     rbx, [rbp+0CA0h+ppSecUri]
0x18003d63f  lea     rcx, [rbp+0CA0h+var_D10]; void *
0x18003d643  xor     edx, edx; Val
0x18003d645  mov     r8d, 4E8h; Size
0x18003d64b  call    memset_0
0x18003d650  lea     r9d, [r12+1]; int
0x18003d655  mov     rdx, rbx; struct IUri *
0x18003d658  lea     rcx, [rbp+0CA0h+var_D10]; this
0x18003d65c  call    ?Crack@ZONEMAP_COMPONENTS@@QEAAJPEAUIUri@@KH@Z; ZONEMAP_COMPONENTS::Crack(IUri *,ulong,int)
0x18003d661  mov     edi, eax
0x18003d663  test    eax, eax
0x18003d665  jz      short loc_18003D67C
0x18003d667  lea     rcx, [rbp+0CA0h+var_D10]; this
0x18003d66b  call    ??1ZONEMAP_COMPONENTS@@QEAA@XZ; ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS(void)
0x18003d670  mov     rcx, [rbx]
0x18003d673  mov     rax, [rcx+10h]
0x18003d677  jmp     loc_18003DC87
0x18003d67c  xor     edx, edx; Val
0x18003d67e  lea     rcx, [rbp+0CA0h+var_81C]; void *
0x18003d685  mov     r8d, 5B0h; Size
0x18003d68b  call    memset_0
0x18003d690  mov     rcx, rsi; this
0x18003d693  mov     [rbp+0CA0h+var_820], 5B4h
0x18003d69d  call    ?EnsureZoneManager@CSecurityManager@@IEAAHXZ; CSecurityManager::EnsureZoneManager(void)
0x18003d6a2  test    eax, eax
0x18003d6a4  jnz     short loc_18003D6C8
0x18003d6a6  lea     rcx, [rbp+0CA0h+var_D10]; this
0x18003d6aa  call    ??1ZONEMAP_COMPONENTS@@QEAA@XZ; ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS(void)
0x18003d6af  mov     rax, [rbx]
0x18003d6b2  mov     rcx, rbx
0x18003d6b5  mov     rax, [rax+10h]
0x18003d6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6be  mov     eax, 8007000Eh
0x18003d6c3  jmp     loc_18003DC91
0x18003d6c8  mov     edx, cs:?s_fESCEnabled@CSecurityManager@@0HA; int CSecurityManager::s_fESCEnabled
0x18003d6ce  test    r14d, r14d
0x18003d6d1  jz      short loc_18003D6DD
0x18003d6d3  cmp     r13d, 2
0x18003d6d7  jnz     short loc_18003D6DD
0x18003d6d9  test    edx, edx
0x18003d6db  jz      short loc_18003D738
0x18003d6dd  test    r15b, 1
0x18003d6e1  jnz     short loc_18003D738
0x18003d6e3  mov     rcx, [rsi+40h]
0x18003d6e7  lea     r8, [rbp+0CA0h+var_820]
0x18003d6ee  mov     edx, r13d
0x18003d6f1  mov     rax, [rcx]
0x18003d6f4  mov     rax, [rax+18h]
0x18003d6f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6fd  test    eax, eax
0x18003d6ff  js      short loc_18003D732
0x18003d701  test    [rbp+0CA0h+var_270], 4
0x18003d708  jz      short loc_18003D732
0x18003d70a  cmp     [rbp+0CA0h+var_D10], 0Bh
0x18003d70e  jz      short loc_18003D732
0x18003d710  lea     rcx, [rbp+0CA0h+var_D10]; this
0x18003d714  call    ??1ZONEMAP_COMPONENTS@@QEAA@XZ; ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS(void)
0x18003d719  mov     rax, [rbx]
0x18003d71c  mov     rcx, rbx
0x18003d71f  mov     rax, [rax+10h]
0x18003d723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d728  mov     eax, 80070005h
0x18003d72d  jmp     loc_18003DC91
0x18003d732  mov     edx, cs:?s_fESCEnabled@CSecurityManager@@0HA; int CSecurityManager::s_fESCEnabled
0x18003d738  test    [rbp+0CA0h+var_CBC], 2
0x18003d73c  jz      short loc_18003D757
0x18003d73e  mov     r9d, r15d; unsigned int
0x18003d741  lea     rdx, [rbp+0CA0h+var_D10]; struct ZONEMAP_COMPONENTS *
0x18003d745  mov     r8d, r13d; unsigned int
0x18003d748  mov     rcx, rsi; this
0x18003d74b  call    ?AddDeleteIPRule@CSecurityManager@@IEAAJPEAVZONEMAP_COMPONENTS@@KK@Z; CSecurityManager::AddDeleteIPRule(ZONEMAP_COMPONENTS *,ulong,ulong)
0x18003d750  mov     edi, eax
0x18003d752  jmp     loc_18003D667
0x18003d757  cmp     [rbp+0CA0h+var_CA8], r12d
0x18003d75b  jz      short loc_18003D77F
0x18003d75d  lea     rcx, [rbp+0CA0h+var_D10]; this
0x18003d761  call    ??1ZONEMAP_COMPONENTS@@QEAA@XZ; ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS(void)
0x18003d766  mov     rax, [rbx]
0x18003d769  mov     rcx, rbx
0x18003d76c  mov     rax, [rax+10h]
0x18003d770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d775  mov     eax, 80070057h
0x18003d77a  jmp     loc_18003DC91
0x18003d77f  mov     ecx, cs:?g_bUseHKLMOnly@@3HA; int g_bUseHKLMOnly
0x18003d785  lea     r8, ??_7CRegKey@@6B@; unsigned int
0x18003d78c  mov     eax, cs:?s_fUsePoliciesZoneMap@CSecurityManager@@0HA; int CSecurityManager::s_fUsePoliciesZoneMap
0x18003d792  mov     [rsp+0DA0h+var_D68], r8
0x18003d797  mov     [rsp+0DA0h+var_D40], r8
0x18003d79c  mov     [rsp+0DA0h+fIgnoreHKCU], ecx
0x18003d7a0  mov     [rsp+0DA0h+var_D60], r12
0x18003d7a5  mov     [rsp+0DA0h+var_D50], r12d
0x18003d7aa  mov     [rsp+0DA0h+var_D54], eax
0x18003d7ae  mov     [rsp+0DA0h+var_D30], ecx
0x18003d7b2  mov     [rsp+0DA0h+hUSKey], r12
0x18003d7b7  mov     [rsp+0DA0h+var_D28], r12d
0x18003d7bc  mov     [rsp+0DA0h+var_D2C], eax
0x18003d7c0  test    r15b, 1
0x18003d7c4  jz      loc_18003DA37
0x18003d7ca  test    r14d, r14d
0x18003d7cd  jnz     short loc_18003D7D6
0x18003d7cf  mov     r9d, r12d
0x18003d7d2  test    edx, edx
0x18003d7d4  jz      short loc_18003D7DC
0x18003d7d6  mov     r9d, 1; int
0x18003d7dc  lea     rdx, [rbp+0CA0h+pszStart]; unsigned __int16 *
0x18003d7e3  lea     rcx, [rbp+0CA0h+var_D10]; struct ZONEMAP_COMPONENTS *
0x18003d7e7  call    ?GetDomainKeyNameForDeleting@CSecurityManager@@KAJPEBVZONEMAP_COMPONENTS@@PEAGKH@Z; CSecurityManager::GetDomainKeyNameForDeleting(ZONEMAP_COMPONENTS const *,ushort *,ulong,int)
0x18003d7ec  mov     edi, eax
0x18003d7ee  test    eax, eax
0x18003d7f0  jns     short loc_18003D81C
0x18003d7f2  lea     rsi, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x18003d7f9  lea     rcx, [rsp+0DA0h+var_D40]; this
0x18003d7fe  mov     [rsp+0DA0h+var_D40], rsi
0x18003d803  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x18003d808  lea     rcx, [rsp+0DA0h+var_D68]; this
0x18003d80d  mov     [rsp+0DA0h+var_D68], rsi
0x18003d812  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x18003d817  jmp     loc_18003D667
0x18003d81c  mov     rdx, [rsi+70h]; void *
0x18003d820  lea     r8, [rbp+0CA0h+pszStart]; unsigned __int16 *
0x18003d827  mov     r14d, 2001Fh
0x18003d82d  lea     rcx, [rsp+0DA0h+var_D68]; this
0x18003d832  mov     r9d, r14d; unsigned int
0x18003d835  call    ?Open@CRegKey@@UEAAJPEAXPEBGK@Z; CRegKey::Open(void *,ushort const *,ulong)
0x18003d83a  mov     r13d, 5Ch ; '\'
0x18003d840  cmp     eax, 2
0x18003d843  jnz     loc_18003D91F
0x18003d849  cmp     [rbp+0CA0h+var_CD4], 1
0x18003d84d  jnz     short loc_18003D8BE
0x18003d84f  mov     rax, [rbp+0CA0h+var_D00]
0x18003d853  cmp     word ptr [rax], 2Ah ; '*'
0x18003d857  jnz     short loc_18003D8BE
0x18003d859  mov     r8d, r13d; wMatch
0x18003d85c  lea     rcx, [rbp+0CA0h+pszStart]; pszStart
0x18003d863  xor     edx, edx; pszEnd
0x18003d865  call    cs:__imp_StrRChrW
0x18003d86c  nop     dword ptr [rax+rax+00h]
0x18003d871  mov     rdx, rax
0x18003d874  test    rax, rax
0x18003d877  jz      short loc_18003D8BE
0x18003d879  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003d87d  inc     rax
0x18003d880  cmp     [rdx+rax*2], r12w
0x18003d885  jnz     short loc_18003D87D
0x18003d887  cmp     eax, 1
0x18003d88a  jbe     short loc_18003D8BE
0x18003d88c  cmp     word ptr [rdx+2], 2Ah ; '*'
0x18003d891  jnz     short loc_18003D8BE
0x18003d893  lea     r9d, [rax-2]
0x18003d897  mov     r8d, 1
0x18003d89d  cmp     r9d, r8d
0x18003d8a0  jbe     short loc_18003D8B9
0x18003d8a2  mov     ecx, r8d
0x18003d8a5  lea     eax, [r8+2]
0x18003d8a9  movzx   eax, word ptr [rdx+rax*2]
0x18003d8ad  inc     r8d
0x18003d8b0  mov     [rdx+rcx*2], ax
0x18003d8b4  cmp     r8d, r9d
0x18003d8b7  jb      short loc_18003D8A2
0x18003d8b9  mov     [rdx+r9*2], r12w
0x18003d8be  mov     rdx, [rsi+70h]; void *
0x18003d8c2  lea     r8, [rbp+0CA0h+pszStart]; unsigned __int16 *
0x18003d8c9  mov     r9d, r14d; unsigned int
0x18003d8cc  lea     rcx, [rsp+0DA0h+var_D68]; this
0x18003d8d1  call    ?Open@CRegKey@@UEAAJPEAXPEBGK@Z; CRegKey::Open(void *,ushort const *,ulong)
0x18003d8d6  cmp     eax, 2
0x18003d8d9  jnz     short loc_18003D91F
0x18003d8db  lea     rsi, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x18003d8e2  lea     rcx, [rsp+0DA0h+var_D40]; this
0x18003d8e7  mov     [rsp+0DA0h+var_D40], rsi
0x18003d8ec  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x18003d8f1  lea     rcx, [rsp+0DA0h+var_D68]; this
0x18003d8f6  mov     [rsp+0DA0h+var_D68], rsi
0x18003d8fb  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x18003d900  lea     rcx, [rbp+0CA0h+var_D10]; this
0x18003d904  call    ??1ZONEMAP_COMPONENTS@@QEAA@XZ; ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS(void)
0x18003d909  mov     rax, [rbx]
0x18003d90c  mov     rcx, rbx
0x18003d90f  mov     rax, [rax+10h]
0x18003d913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d918  xor     eax, eax
0x18003d91a  jmp     loc_18003DC91
0x18003d91f  mov     rdx, [rbp+0CA0h+var_D08]; unsigned __int16 *
0x18003d923  lea     rcx, [rsp+0DA0h+var_D68]; this
0x18003d928  call    ?DeleteValue@CRegKey@@QEAAJPEBG@Z; CRegKey::DeleteValue(ushort const *)
0x18003d92d  mov     edi, eax
0x18003d92f  test    eax, eax
0x18003d931  jnz     loc_18003DA29
0x18003d937  lea     r9, [rsp+0DA0h+var_D70]; unsigned int *
0x18003d93c  mov     [rsp+0DA0h+var_D70], r12d
0x18003d941  xor     r8d, r8d; unsigned int *
0x18003d944  lea     rcx, [rsp+0DA0h+var_D68]; this
0x18003d949  xor     edx, edx; unsigned int *
0x18003d94b  call    ?QuerySubKeyInfo@CRegKey@@QEAAJPEAK00@Z; CRegKey::QuerySubKeyInfo(ulong *,ulong *,ulong *)
0x18003d950  test    eax, eax
0x18003d952  jnz     short loc_18003D975
0x18003d954  cmp     [rsp+0DA0h+var_D70], r12d
0x18003d959  jnz     short loc_18003D975
0x18003d95b  lea     rcx, [rsp+0DA0h+var_D68]; this
0x18003d960  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x18003d965  lea     rdx, [rbp+0CA0h+pszStart]; unsigned __int16 *
0x18003d96c  lea     rcx, [rsi+68h]; this
0x18003d970  call    ?DeleteEmptyKey@CRegKey@@QEAAJPEBG@Z; CRegKey::DeleteEmptyKey(ushort const *)
0x18003d975  mov     r8d, r13d; wMatch
0x18003d978  lea     rcx, [rbp+0CA0h+pszStart]; pszStart
0x18003d97f  xor     edx, edx; pszEnd
0x18003d981  call    cs:__imp_StrRChrW
0x18003d988  nop     dword ptr [rax+rax+00h]
0x18003d98d  mov     edx, r13d; wMatch
0x18003d990  lea     rcx, [rbp+0CA0h+pszStart]; pszStart
0x18003d997  mov     rdi, rax
0x18003d99a  call    cs:__imp_StrChrW
0x18003d9a1  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
