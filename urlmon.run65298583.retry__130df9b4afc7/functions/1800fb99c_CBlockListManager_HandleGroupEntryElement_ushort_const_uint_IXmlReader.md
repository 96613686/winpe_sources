# CBlockListManager::_HandleGroupEntryElement(ushort const *,uint,IXmlReader *)

- ea: `0x1800fb99c`
- end: `0x1800fbe66`
- name: `?_HandleGroupEntryElement@CBlockListManager@@AEAAJPEBGIPEAUIXmlReader@@@Z`
- size: `1226`
- prototype: `__int64 __fastcall(CBlockListManager *__hidden this, LPCWSTR pszStr1, unsigned int, struct IXmlReader *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800fb4ec`

## callees

- `0x1800f62a4`
- `0x1800f9354`
- `0x1800fac68`
- `0x1800fb99c`
- `0x1800fc7e8`
- `0x18010c5e4`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fb9f9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fba7f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbad0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbb21`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbb71`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbbc1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbc0a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fb9f9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fba7f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbad0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbb21`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbb71`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbbc1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbc0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fbcb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fbcb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fbde0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fbdf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fbdff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fbe0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fbe1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fbe29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fbe37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fbde0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fbdf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fbdff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fbe0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fbe1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fbe29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fbe37`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800fbc3d`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800fbc3d`

## string_xrefs

- `0x1800fbac9`: `fwdlink`

## pseudocode

```c
__int64 __fastcall CBlockListManager::_HandleGroupEntryElement(
        CBlockListManager *this,
        LPCWSTR pszStr1,
        int a3,
        struct IXmlReader *a4)
{
  int CachedString; // ebx
  struct IXmlReaderVtbl *lpVtbl; // rax
  HRESULT v9; // eax
  bool v10; // zf
  int v11; // r8d
  struct IXmlReaderVtbl *v12; // rax
  LPWSTR *p_pv; // rdx
  struct IXmlReaderVtbl *v14; // rax
  struct IXmlReaderVtbl *v15; // rax
  struct IXmlReaderVtbl *v16; // rax
  struct IXmlReaderVtbl *v17; // rax
  struct IXmlReaderVtbl *v18; // rax
  _QWORD *v19; // rax
  LPVOID v20; // rdi
  CBlockListManager *v21; // rcx
  unsigned int v22; // eax
  const unsigned __int8 *v23; // rcx
  unsigned int v24; // [rsp+28h] [rbp-21h]
  unsigned __int8 *v25; // [rsp+30h] [rbp-19h]
  unsigned int v26; // [rsp+38h] [rbp-11h]
  LPCWSTR psz; // [rsp+40h] [rbp-9h] BYREF
  LPCWSTR pszStr1a; // [rsp+48h] [rbp-1h] BYREF
  unsigned int v29; // [rsp+50h] [rbp+7h] BYREF
  unsigned int v30; // [rsp+54h] [rbp+Bh] BYREF
  LPVOID pv; // [rsp+58h] [rbp+Fh] BYREF
  unsigned __int16 *v32; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int16 *v33; // [rsp+68h] [rbp+1Fh] BYREF
  unsigned __int16 *v34; // [rsp+70h] [rbp+27h] BYREF
  unsigned __int16 *v35; // [rsp+78h] [rbp+2Fh] BYREF
  LPWSTR ppwsz; // [rsp+80h] [rbp+37h] BYREF
  unsigned __int16 *nChar; // [rsp+B8h] [rbp+6Fh] BYREF

  if ( !pszStr1 || !a4 )
    return 2147942487LL;
  if ( !*((_QWORD *)this + 4) )
    return 2147947423LL;
  if ( a3 != 10 || StrCmpNICW(pszStr1, L"groupentry", 10) )
    return (unsigned int)-2147019873;
  CachedString = ((__int64 (__fastcall *)(struct IXmlReader *))a4->lpVtbl->MoveToFirstAttribute)(a4);
  if ( CachedString )
    return (unsigned int)CachedString;
  pv = 0;
  v29 = 0;
  v32 = 0;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  ppwsz = 0;
  while ( 1 )
  {
    lpVtbl = a4->lpVtbl;
    pszStr1a = 0;
    LODWORD(nChar) = 0;
    v9 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, unsigned __int16 **))lpVtbl->GetLocalName)(
           a4,
           &pszStr1a,
           &nChar);
    v10 = v9 == 0;
    if ( v9 < 0 )
      goto LABEL_41;
    v11 = (int)nChar;
    if ( (_DWORD)nChar == 9 )
    {
      if ( !StrCmpNICW(pszStr1a, L"groupname", 9) )
      {
        v12 = a4->lpVtbl;
        psz = 0;
        v9 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, unsigned int *))v12->GetValue)(a4, &psz, &v29);
        v10 = v9 == 0;
        if ( v9 >= 0 )
        {
          p_pv = (LPWSTR *)&pv;
          goto LABEL_39;
        }
        goto LABEL_41;
      }
      v11 = (int)nChar;
    }
    if ( v11 == 7 )
    {
      if ( !StrCmpNICW(pszStr1a, L"fwdlink", 7) )
      {
        v14 = a4->lpVtbl;
        psz = 0;
        v9 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, unsigned int *))v14->GetValue)(a4, &psz, &v30);
        v10 = v9 == 0;
        if ( v9 >= 0 )
        {
          p_pv = &v32;
          goto LABEL_39;
        }
        goto LABEL_41;
      }
      v11 = (int)nChar;
    }
    if ( v11 == 12 )
    {
      if ( !StrCmpNICW(pszStr1a, L"allowedgroup", 12) )
      {
        v15 = a4->lpVtbl;
        psz = 0;
        v9 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, _QWORD))v15->GetValue)(a4, &psz, 0);
        v10 = v9 == 0;
        if ( v9 >= 0 )
        {
          p_pv = &v33;
          goto LABEL_39;
        }
        goto LABEL_41;
      }
      v11 = (int)nChar;
    }
    if ( v11 == 11 )
    {
      if ( !StrCmpNICW(pszStr1a, L"latestgroup", 11) )
      {
        v16 = a4->lpVtbl;
        psz = 0;
        v9 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, _QWORD))v16->GetValue)(a4, &psz, 0);
        v10 = v9 == 0;
        if ( v9 >= 0 )
        {
          p_pv = &v34;
          goto LABEL_39;
        }
        goto LABEL_41;
      }
      v11 = (int)nChar;
    }
    if ( v11 != 9 )
      goto LABEL_35;
    if ( StrCmpNICW(pszStr1a, L"hardblock", 9) )
      break;
    v17 = a4->lpVtbl;
    psz = 0;
    v9 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, _QWORD))v17->GetValue)(a4, &psz, 0);
    v10 = v9 == 0;
    if ( v9 >= 0 )
    {
      p_pv = &v35;
      goto LABEL_39;
    }
LABEL_41:
    if ( !v10 )
      goto LABEL_44;
  }
  v11 = (int)nChar;
LABEL_35:
  if ( v11 == 11 && !StrCmpNICW(pszStr1a, L"silentblock", 11) )
  {
    v18 = a4->lpVtbl;
    psz = 0;
    v9 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, _QWORD))v18->GetValue)(a4, &psz, 0);
    v10 = v9 == 0;
    if ( v9 < 0 )
      goto LABEL_41;
    p_pv = &ppwsz;
LABEL_39:
    v9 = SHStrDupW(psz, p_pv);
    v10 = v9 == 0;
    if ( v9 >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(struct IXmlReader *))a4->lpVtbl->MoveToNextAttribute)(a4);
      v10 = v9 == 0;
    }
    goto LABEL_41;
  }
  v9 = -2147019873;
LABEL_44:
  CachedString = 0;
  if ( v9 != 1 )
    CachedString = v9;
  if ( CachedString >= 0 )
  {
    if ( pv && v29 && v32 && v30 && (int)CHashTable<GROUP_ENTRY,unsigned short>::ContainsKey(*((_QWORD *)this + 4)) < 0 )
    {
      v19 = CoTaskMemAlloc(0x18u);
      v20 = v19;
      if ( !v19 )
      {
        CachedString = -2147024882;
        goto LABEL_73;
      }
      nChar = 0;
      *(_OWORD *)v19 = 0;
      v19[2] = 0;
      CachedString = CBlockListManager::_GetCachedString(this, (const unsigned __int16 *)pv, v29, &nChar);
      if ( CachedString < 0 )
        goto LABEL_71;
      if ( !nChar )
      {
        CachedString = -2147019873;
        goto LABEL_71;
      }
      *((_QWORD *)v20 + 1) = nChar;
      psz = 0;
      CachedString = CBlockListManager::_GetCachedString(this, v32, v30, (unsigned __int16 **)&psz);
      if ( CachedString < 0 )
        goto LABEL_71;
      if ( psz )
      {
        *(_QWORD *)v20 = psz;
        if ( !v33 || (CachedString = CBlockListManager::_StringToBool(v21, v33, (bool *)v20 + 16), CachedString >= 0) )
        {
          if ( !v34 || (CachedString = CBlockListManager::_StringToBool(v21, v34, (bool *)v20 + 17), CachedString >= 0) )
          {
            if ( !v35
              || (CachedString = CBlockListManager::_StringToBool(v21, v35, (bool *)v20 + 18), CachedString >= 0) )
            {
              if ( !ppwsz
                || (CachedString = CBlockListManager::_StringToBool(v21, ppwsz, (bool *)v20 + 19), CachedString >= 0) )
              {
                pszStr1a = (LPCWSTR)v20;
                v22 = _SizeOfString((const unsigned __int16 *)pv);
                CachedString = CByteHashTable::_AddUpdateItem(
                                 *((CByteHashTable **)this + 4),
                                 (int)&pszStr1a,
                                 v23,
                                 v22,
                                 (const unsigned __int8 *)&pszStr1a,
                                 v24,
                                 v25,
                                 v26);
                goto LABEL_68;
              }
            }
          }
        }
        goto LABEL_71;
      }
      CachedString = -2147019873;
LABEL_68:
      if ( CachedString < 0 )
LABEL_71:
        CoTaskMemFree(v20);
    }
    else
    {
      CachedString = -2147019873;
    }
  }
LABEL_73:
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v32);
  v32 = 0;
  CoTaskMemFree(v33);
  v33 = 0;
  CoTaskMemFree(v34);
  v34 = 0;
  CoTaskMemFree(v35);
  v35 = 0;
  CoTaskMemFree(ppwsz);
  return (unsigned int)CachedString;
}

```

## disassembly

```asm
0x1800fb99c  mov     [rsp-8+arg_0], rbx
0x1800fb9a1  mov     [rsp-8+arg_10], rdi
0x1800fb9a6  push    rbp
0x1800fb9a7  push    r14
0x1800fb9a9  push    r15
0x1800fb9ab  lea     rbp, [rsp-47h]
0x1800fb9b0  sub     rsp, 90h
0x1800fb9b7  xor     r15d, r15d
0x1800fb9ba  mov     rdi, r9
0x1800fb9bd  mov     rax, rdx
0x1800fb9c0  mov     r14, rcx
0x1800fb9c3  test    rdx, rdx
0x1800fb9c6  jz      loc_1800FBE48
0x1800fb9cc  test    r9, r9
0x1800fb9cf  jz      loc_1800FBE48
0x1800fb9d5  cmp     [rcx+20h], r15
0x1800fb9d9  jnz     short loc_1800FB9E5
0x1800fb9db  mov     eax, 8007139Fh
0x1800fb9e0  jmp     loc_1800FBE4D
0x1800fb9e5  cmp     r8d, 0Ah
0x1800fb9e9  jnz     loc_1800FBE3F
0x1800fb9ef  lea     rdx, aGroupentry; "groupentry"
0x1800fb9f6  mov     rcx, rax; pszStr1
0x1800fb9f9  call    cs:__imp_StrCmpNICW
0x1800fb9ff  test    eax, eax
0x1800fba01  jnz     loc_1800FBE3F
0x1800fba07  mov     rax, [rdi]
0x1800fba0a  mov     rcx, rdi
0x1800fba0d  mov     rax, [rax+40h]
0x1800fba11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fba16  mov     ebx, eax
0x1800fba18  test    eax, eax
0x1800fba1a  jnz     loc_1800FBE44
0x1800fba20  mov     [rbp+57h+pv], r15
0x1800fba24  mov     [rbp+57h+var_50], r15d
0x1800fba28  mov     [rbp+57h+var_40], r15
0x1800fba2c  mov     [rbp+57h+var_4C], r15d
0x1800fba30  mov     [rbp+57h+var_38], r15
0x1800fba34  mov     [rbp+57h+var_30], r15
0x1800fba38  mov     [rbp+57h+var_28], r15
0x1800fba3c  mov     [rbp+57h+ppwsz], r15
0x1800fba40  mov     rax, [rdi]
0x1800fba43  lea     r8, [rbp+57h+nChar]
0x1800fba47  lea     rdx, [rbp+57h+pszStr1]
0x1800fba4b  mov     [rbp+57h+pszStr1], r15
0x1800fba4f  mov     rcx, rdi
0x1800fba52  mov     dword ptr [rbp+57h+nChar], r15d
0x1800fba56  mov     rax, [rax+70h]
0x1800fba5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fba5f  test    eax, eax
0x1800fba61  js      loc_1800FBC58
0x1800fba67  mov     r8d, dword ptr [rbp+57h+nChar]; nChar
0x1800fba6b  lea     eax, [r8+1]
0x1800fba6f  cmp     eax, 0Ah
0x1800fba72  jnz     short loc_1800FBABC
0x1800fba74  mov     rcx, [rbp+57h+pszStr1]; pszStr1
0x1800fba78  lea     rdx, aGroupname; "groupname"
0x1800fba7f  call    cs:__imp_StrCmpNICW
0x1800fba85  test    eax, eax
0x1800fba87  jnz     short loc_1800FBAB8
0x1800fba89  mov     rax, [rdi]
0x1800fba8c  lea     r8, [rbp+57h+var_50]
0x1800fba90  lea     rdx, [rbp+57h+psz]
0x1800fba94  mov     [rbp+57h+psz], r15
0x1800fba98  mov     rcx, rdi
0x1800fba9b  mov     rax, [rax+80h]
0x1800fbaa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbaa7  test    eax, eax
0x1800fbaa9  js      loc_1800FBC58
0x1800fbaaf  lea     rdx, [rbp+57h+pv]
0x1800fbab3  jmp     loc_1800FBC39
0x1800fbab8  mov     r8d, dword ptr [rbp+57h+nChar]; nChar
0x1800fbabc  lea     eax, [r8+1]
0x1800fbac0  cmp     eax, 8
0x1800fbac3  jnz     short loc_1800FBB0D
0x1800fbac5  mov     rcx, [rbp+57h+pszStr1]; pszStr1
0x1800fbac9  lea     rdx, aFwdlink; "fwdlink"
0x1800fbad0  call    cs:__imp_StrCmpNICW
0x1800fbad6  test    eax, eax
0x1800fbad8  jnz     short loc_1800FBB09
0x1800fbada  mov     rax, [rdi]
0x1800fbadd  lea     r8, [rbp+57h+var_4C]
0x1800fbae1  lea     rdx, [rbp+57h+psz]
0x1800fbae5  mov     [rbp+57h+psz], r15
0x1800fbae9  mov     rcx, rdi
0x1800fbaec  mov     rax, [rax+80h]
0x1800fbaf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbaf8  test    eax, eax
0x1800fbafa  js      loc_1800FBC58
0x1800fbb00  lea     rdx, [rbp+57h+var_40]
0x1800fbb04  jmp     loc_1800FBC39
0x1800fbb09  mov     r8d, dword ptr [rbp+57h+nChar]; nChar
0x1800fbb0d  lea     eax, [r8+1]
0x1800fbb11  cmp     eax, 0Dh
0x1800fbb14  jnz     short loc_1800FBB5D
0x1800fbb16  mov     rcx, [rbp+57h+pszStr1]; pszStr1
0x1800fbb1a  lea     rdx, aAllowedgroup; "allowedgroup"
0x1800fbb21  call    cs:__imp_StrCmpNICW
0x1800fbb27  test    eax, eax
0x1800fbb29  jnz     short loc_1800FBB59
0x1800fbb2b  mov     rax, [rdi]
0x1800fbb2e  lea     rdx, [rbp+57h+psz]
0x1800fbb32  xor     r8d, r8d
0x1800fbb35  mov     [rbp+57h+psz], r15
0x1800fbb39  mov     rcx, rdi
0x1800fbb3c  mov     rax, [rax+80h]
0x1800fbb43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbb48  test    eax, eax
0x1800fbb4a  js      loc_1800FBC58
0x1800fbb50  lea     rdx, [rbp+57h+var_38]
0x1800fbb54  jmp     loc_1800FBC39
0x1800fbb59  mov     r8d, dword ptr [rbp+57h+nChar]; nChar
0x1800fbb5d  lea     eax, [r8+1]
0x1800fbb61  cmp     eax, 0Ch
0x1800fbb64  jnz     short loc_1800FBBAD
0x1800fbb66  mov     rcx, [rbp+57h+pszStr1]; pszStr1
0x1800fbb6a  lea     rdx, aLatestgroup; "latestgroup"
0x1800fbb71  call    cs:__imp_StrCmpNICW
0x1800fbb77  test    eax, eax
0x1800fbb79  jnz     short loc_1800FBBA9
0x1800fbb7b  mov     rax, [rdi]
0x1800fbb7e  lea     rdx, [rbp+57h+psz]
0x1800fbb82  xor     r8d, r8d
0x1800fbb85  mov     [rbp+57h+psz], r15
0x1800fbb89  mov     rcx, rdi
0x1800fbb8c  mov     rax, [rax+80h]
0x1800fbb93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbb98  test    eax, eax
0x1800fbb9a  js      loc_1800FBC58
0x1800fbba0  lea     rdx, [rbp+57h+var_30]
0x1800fbba4  jmp     loc_1800FBC39
0x1800fbba9  mov     r8d, dword ptr [rbp+57h+nChar]; nChar
0x1800fbbad  lea     eax, [r8+1]
0x1800fbbb1  cmp     eax, 0Ah
0x1800fbbb4  jnz     short loc_1800FBBF6
0x1800fbbb6  mov     rcx, [rbp+57h+pszStr1]; pszStr1
0x1800fbbba  lea     rdx, aHardblock; "hardblock"
0x1800fbbc1  call    cs:__imp_StrCmpNICW
0x1800fbbc7  test    eax, eax
0x1800fbbc9  jnz     short loc_1800FBBF2
0x1800fbbcb  mov     rax, [rdi]
0x1800fbbce  lea     rdx, [rbp+57h+psz]
0x1800fbbd2  xor     r8d, r8d
0x1800fbbd5  mov     [rbp+57h+psz], r15
0x1800fbbd9  mov     rcx, rdi
0x1800fbbdc  mov     rax, [rax+80h]
0x1800fbbe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbbe8  test    eax, eax
0x1800fbbea  js      short loc_1800FBC58
0x1800fbbec  lea     rdx, [rbp+57h+var_28]
0x1800fbbf0  jmp     short loc_1800FBC39
0x1800fbbf2  mov     r8d, dword ptr [rbp+57h+nChar]; nChar
0x1800fbbf6  lea     eax, [r8+1]
0x1800fbbfa  cmp     eax, 0Ch
0x1800fbbfd  jnz     short loc_1800FBC60
0x1800fbbff  mov     rcx, [rbp+57h+pszStr1]; pszStr1
0x1800fbc03  lea     rdx, aSilentblock; "silentblock"
0x1800fbc0a  call    cs:__imp_StrCmpNICW
0x1800fbc10  test    eax, eax
0x1800fbc12  jnz     short loc_1800FBC60
0x1800fbc14  mov     rax, [rdi]
0x1800fbc17  lea     rdx, [rbp+57h+psz]
0x1800fbc1b  xor     r8d, r8d
0x1800fbc1e  mov     [rbp+57h+psz], r15
0x1800fbc22  mov     rcx, rdi
0x1800fbc25  mov     rax, [rax+80h]
0x1800fbc2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbc31  test    eax, eax
0x1800fbc33  js      short loc_1800FBC58
0x1800fbc35  lea     rdx, [rbp+57h+ppwsz]; ppwsz
0x1800fbc39  mov     rcx, [rbp+57h+psz]; psz
0x1800fbc3d  call    cs:__imp_SHStrDupW
0x1800fbc43  test    eax, eax
0x1800fbc45  js      short loc_1800FBC58
0x1800fbc47  mov     rax, [rdi]
0x1800fbc4a  mov     rcx, rdi
0x1800fbc4d  mov     rax, [rax+48h]
0x1800fbc51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbc56  test    eax, eax
0x1800fbc58  jz      loc_1800FBA40
0x1800fbc5e  jmp     short loc_1800FBC65
0x1800fbc60  mov     eax, 8007139Fh
0x1800fbc65  cmp     eax, 1
0x1800fbc68  mov     ebx, r15d
0x1800fbc6b  cmovnz  ebx, eax
0x1800fbc6e  test    ebx, ebx
0x1800fbc70  js      loc_1800FBDED
0x1800fbc76  mov     rdx, [rbp+57h+pv]
0x1800fbc7a  test    rdx, rdx
0x1800fbc7d  jz      loc_1800FBDE8
0x1800fbc83  cmp     [rbp+57h+var_50], r15d
0x1800fbc87  jz      loc_1800FBDE8
0x1800fbc8d  cmp     [rbp+57h+var_40], r15
0x1800fbc91  jz      loc_1800FBDE8
0x1800fbc97  cmp     [rbp+57h+var_4C], r15d
0x1800fbc9b  jz      loc_1800FBDE8
0x1800fbca1  mov     rcx, [r14+20h]
0x1800fbca5  call    ?ContainsKey@?$CHashTable@UGROUP_ENTRY@@G@@QEBAJPEBG@Z; CHashTable<GROUP_ENTRY,ushort>::ContainsKey(ushort const *)
0x1800fbcaa  test    eax, eax
0x1800fbcac  jns     loc_1800FBDE8
0x1800fbcb2  mov     ecx, 18h; cb
0x1800fbcb7  call    cs:__imp_CoTaskMemAlloc
0x1800fbcbd  mov     rdi, rax
0x1800fbcc0  test    rax, rax
0x1800fbcc3  jnz     short loc_1800FBCCF
0x1800fbcc5  mov     ebx, 8007000Eh
0x1800fbcca  jmp     loc_1800FBDED
0x1800fbccf  xorps   xmm0, xmm0
0x1800fbcd2  mov     [rbp+57h+nChar], r15
0x1800fbcd6  movups  xmmword ptr [rdi], xmm0
0x1800fbcd9  xor     eax, eax
0x1800fbcdb  lea     r9, [rbp+57h+nChar]; unsigned __int16 **
0x1800fbcdf  mov     [rdi+10h], rax
0x1800fbce3  mov     rcx, r14; this
0x1800fbce6  mov     r8d, [rbp+57h+var_50]; unsigned int
0x1800fbcea  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x1800fbcee  call    ?_GetCachedString@CBlockListManager@@AEAAJPEBGIPEAPEAG@Z; CBlockListManager::_GetCachedString(ushort const *,uint,ushort * *)
0x1800fbcf3  mov     ebx, eax
0x1800fbcf5  test    eax, eax
0x1800fbcf7  js      loc_1800FBDDD
0x1800fbcfd  mov     rax, [rbp+57h+nChar]
0x1800fbd01  test    rax, rax
0x1800fbd04  jz      loc_1800FBDD8
0x1800fbd0a  mov     [rdi+8], rax
0x1800fbd0e  lea     r9, [rbp+57h+psz]; unsigned __int16 **
0x1800fbd12  mov     r8d, [rbp+57h+var_4C]; unsigned int
0x1800fbd16  mov     rcx, r14; this
0x1800fbd19  mov     rdx, [rbp+57h+var_40]; unsigned __int16 *
0x1800fbd1d  mov     [rbp+57h+psz], r15
0x1800fbd21  call    ?_GetCachedString@CBlockListManager@@AEAAJPEBGIPEAPEAG@Z; CBlockListManager::_GetCachedString(ushort const *,uint,ushort * *)
0x1800fbd26  mov     ebx, eax
0x1800fbd28  test    eax, eax
0x1800fbd2a  js      loc_1800FBDDD
0x1800fbd30  mov     rax, [rbp+57h+psz]
0x1800fbd34  test    rax, rax
0x1800fbd37  jz      loc_1800FBDCD
0x1800fbd3d  mov     [rdi], rax
0x1800fbd40  mov     rdx, [rbp+57h+var_38]; unsigned __int16 *
0x1800fbd44  test    rdx, rdx
0x1800fbd47  jz      short loc_1800FBD5C
0x1800fbd49  lea     r8, [rdi+10h]; bool *
0x1800fbd4d  call    ?_StringToBool@CBlockListManager@@AEAAJPEBGPEA_N@Z; CBlockListManager::_StringToBool(ushort const *,bool *)
0x1800fbd52  mov     ebx, eax
0x1800fbd54  test    eax, eax
0x1800fbd56  js      loc_1800FBDDD
0x1800fbd5c  mov     rdx, [rbp+57h+var_30]; unsigned __int16 *
0x1800fbd60  test    rdx, rdx
0x1800fbd63  jz      short loc_1800FBD74
0x1800fbd65  lea     r8, [rdi+11h]; bool *
0x1800fbd69  call    ?_StringToBool@CBlockListManager@@AEAAJPEBGPEA_N@Z; CBlockListManager::_StringToBool(ushort const *,bool *)
0x1800fbd6e  mov     ebx, eax
0x1800fbd70  test    eax, eax
0x1800fbd72  js      short loc_1800FBDDD
0x1800fbd74  mov     rdx, [rbp+57h+var_28]; unsigned __int16 *
0x1800fbd78  test    rdx, rdx
0x1800fbd7b  jz      short loc_1800FBD8C
0x1800fbd7d  lea     r8, [rdi+12h]; bool *
0x1800fbd81  call    ?_StringToBool@CBlockListManager@@AEAAJPEBGPEA_N@Z; CBlockListManager::_StringToBool(ushort const *,bool *)
0x1800fbd86  mov     ebx, eax
0x1800fbd88  test    eax, eax
0x1800fbd8a  js      short loc_1800FBDDD
0x1800fbd8c  mov     rdx, [rbp+57h+ppwsz]; unsigned __int16 *
0x1800fbd90  test    rdx, rdx
0x1800fbd93  jz      short loc_1800FBDA4
0x1800fbd95  lea     r8, [rdi+13h]; bool *
0x1800fbd99  call    ?_StringToBool@CBlockListManager@@AEAAJPEBGPEA_N@Z; CBlockListManager::_StringToBool(ushort const *,bool *)
0x1800fbd9e  mov     ebx, eax
0x1800fbda0  test    eax, eax
0x1800fbda2  js      short loc_1800FBDDD
0x1800fbda4  mov     rcx, [rbp+57h+pv]; unsigned __int16 *
0x1800fbda8  mov     [rbp+57h+pszStr1], rdi
0x1800fbdac  call    ?_SizeOfString@@YAIPEBG@Z; _SizeOfString(ushort const *)
0x1800fbdb1  lea     rdx, [rbp+57h+pszStr1]; int
0x1800fbdb5  mov     r8, rcx; unsigned __int8 *
0x1800fbdb8  mov     rcx, [r14+20h]; this
0x1800fbdbc  mov     r9d, eax; unsigned int
0x1800fbdbf  mov     [rsp+0A0h+var_80], rdx; unsigned __int8 *
0x1800fbdc4  call    ?_AddUpdateItem@CByteHashTable@@AEAAJHPEBEI0IPEAEI@Z; CByteHashTable::_AddUpdateItem(int,uchar const *,uint,uchar const *,uint,uchar *,uint)
0x1800fbdc9  mov     ebx, eax
0x1800fbdcb  jmp     short loc_1800FBDD2
0x1800fbdcd  mov     ebx, 8007139Fh
0x1800fbdd2  test    ebx, ebx
0x1800fbdd4  js      short loc_1800FBDDD
0x1800fbdd6  jmp     short loc_1800FBDED
0x1800fbdd8  mov     ebx, 8007139Fh
0x1800fbddd  mov     rcx, rdi; pv
0x1800fbde0  call    cs:__imp_CoTaskMemFree
0x1800fbde6  jmp     short loc_1800FBDED
0x1800fbde8  mov     ebx, 8007139Fh
0x1800fbded  mov     rcx, [rbp+57h+pv]; pv
0x1800fbdf1  call    cs:__imp_CoTaskMemFree
0x1800fbdf7  mov     rcx, [rbp+57h+var_40]; pv
0x1800fbdfb  mov     [rbp+57h+pv], r15
0x1800fbdff  call    cs:__imp_CoTaskMemFree
0x1800fbe05  mov     rcx, [rbp+57h+var_38]; pv
0x1800fbe09  mov     [rbp+57h+var_40], r15
0x1800fbe0d  call    cs:__imp_CoTaskMemFree
0x1800fbe13  mov     rcx, [rbp+57h+var_30]; pv
0x1800fbe17  mov     [rbp+57h+var_38], r15
0x1800fbe1b  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
