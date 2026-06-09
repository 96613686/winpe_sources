# CBlockListManager::_HandleGroupEntryElement(ushort const *,uint,IXmlReader *)

- ea: `0x180106624`
- end: `0x180106b4f`
- name: `?_HandleGroupEntryElement@CBlockListManager@@AEAAJPEBGIPEAUIXmlReader@@@Z`
- size: `1323`
- prototype: `__int64 __fastcall(CBlockListManager *this, LPCWSTR pszStr1, int, struct IXmlReader *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180106118`

## callees

- `0x180100a24`
- `0x180103d88`
- `0x18010581c`
- `0x180106624`
- `0x180107524`
- `0x180118020`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106681`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18010670d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106764`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1801067bb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106811`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106867`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1801068b6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106681`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18010670d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106764`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1801067bb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106811`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106867`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1801068b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010696f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010696f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106a9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106ab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106ac9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106add`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106af1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106b05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106b19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106a9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106ab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106ac9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106add`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106af1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106b05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106b19`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1801068ef`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1801068ef`

## string_xrefs

- `0x18010675d`: `fwdlink`

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
  LPCWSTR psz; // [rsp+40h] [rbp-9h] BYREF
  LPCWSTR pszStr1a; // [rsp+48h] [rbp-1h] BYREF
  unsigned int v26; // [rsp+50h] [rbp+7h] BYREF
  unsigned int v27; // [rsp+54h] [rbp+Bh] BYREF
  LPVOID pv; // [rsp+58h] [rbp+Fh] BYREF
  unsigned __int16 *v29; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int16 *v30; // [rsp+68h] [rbp+1Fh] BYREF
  unsigned __int16 *v31; // [rsp+70h] [rbp+27h] BYREF
  unsigned __int16 *v32; // [rsp+78h] [rbp+2Fh] BYREF
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
  v26 = 0;
  v29 = 0;
  v27 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
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
        v9 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, unsigned int *))v12->GetValue)(a4, &psz, &v26);
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
        v9 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, unsigned int *))v14->GetValue)(a4, &psz, &v27);
        v10 = v9 == 0;
        if ( v9 >= 0 )
        {
          p_pv = &v29;
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
          p_pv = &v30;
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
          p_pv = &v31;
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
      p_pv = &v32;
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
    if ( pv
      && v26
      && v29
      && v27
      && (int)CHashTable<GROUP_ENTRY,unsigned short>::ContainsKey(*((_QWORD *)this + 4), (const unsigned __int16 *)pv) < 0 )
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
      CachedString = CBlockListManager::_GetCachedString((CByteHashTable **)this, (unsigned __int16 *)pv, v26, &nChar);
      if ( CachedString < 0 )
        goto LABEL_71;
      if ( !nChar )
      {
        CachedString = -2147019873;
        goto LABEL_71;
      }
      *((_QWORD *)v20 + 1) = nChar;
      psz = 0;
      CachedString = CBlockListManager::_GetCachedString((CByteHashTable **)this, v29, v27, (unsigned __int16 **)&psz);
      if ( CachedString < 0 )
        goto LABEL_71;
      if ( psz )
      {
        *(_QWORD *)v20 = psz;
        if ( !v30 || (CachedString = CBlockListManager::_StringToBool(v21, v30, (bool *)v20 + 16), CachedString >= 0) )
        {
          if ( !v31 || (CachedString = CBlockListManager::_StringToBool(v21, v31, (bool *)v20 + 17), CachedString >= 0) )
          {
            if ( !v32
              || (CachedString = CBlockListManager::_StringToBool(v21, v32, (bool *)v20 + 18), CachedString >= 0) )
            {
              if ( !ppwsz
                || (CachedString = CBlockListManager::_StringToBool(v21, ppwsz, (bool *)v20 + 19), CachedString >= 0) )
              {
                pszStr1a = (LPCWSTR)v20;
                v22 = _SizeOfString((const unsigned __int16 *)pv);
                CachedString = CByteHashTable::_AddUpdateItem(
                                 *((CByteHashTable **)this + 4),
                                 (unsigned int)&pszStr1a,
                                 v23,
                                 v22,
                                 (const unsigned __int8 *)&pszStr1a);
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
  CoTaskMemFree(v29);
  v29 = 0;
  CoTaskMemFree(v30);
  v30 = 0;
  CoTaskMemFree(v31);
  v31 = 0;
  CoTaskMemFree(v32);
  v32 = 0;
  CoTaskMemFree(ppwsz);
  return (unsigned int)CachedString;
}

```

## disassembly

```asm
0x180106624  mov     [rsp-8+arg_0], rbx
0x180106629  mov     [rsp-8+arg_10], rdi
0x18010662e  push    rbp
0x18010662f  push    r14
0x180106631  push    r15
0x180106633  lea     rbp, [rsp-47h]
0x180106638  sub     rsp, 90h
0x18010663f  xor     r15d, r15d
0x180106642  mov     rdi, r9
0x180106645  mov     rax, rdx
0x180106648  mov     r14, rcx
0x18010664b  test    rdx, rdx
0x18010664e  jz      loc_180106B30
0x180106654  test    r9, r9
0x180106657  jz      loc_180106B30
0x18010665d  cmp     [rcx+20h], r15
0x180106661  jnz     short loc_18010666D
0x180106663  mov     eax, 8007139Fh
0x180106668  jmp     loc_180106B35
0x18010666d  cmp     r8d, 0Ah
0x180106671  jnz     loc_180106B27
0x180106677  lea     rdx, aGroupentry; "groupentry"
0x18010667e  mov     rcx, rax; pszStr1
0x180106681  call    cs:__imp_StrCmpNICW
0x180106688  nop     dword ptr [rax+rax+00h]
0x18010668d  test    eax, eax
0x18010668f  jnz     loc_180106B27
0x180106695  mov     rax, [rdi]
0x180106698  mov     rcx, rdi
0x18010669b  mov     rax, [rax+40h]
0x18010669f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801066a4  mov     ebx, eax
0x1801066a6  test    eax, eax
0x1801066a8  jnz     loc_180106B2C
0x1801066ae  mov     [rbp+57h+pv], r15
0x1801066b2  mov     [rbp+57h+var_50], r15d
0x1801066b6  mov     [rbp+57h+var_40], r15
0x1801066ba  mov     [rbp+57h+var_4C], r15d
0x1801066be  mov     [rbp+57h+var_38], r15
0x1801066c2  mov     [rbp+57h+var_30], r15
0x1801066c6  mov     [rbp+57h+var_28], r15
0x1801066ca  mov     [rbp+57h+ppwsz], r15
0x1801066ce  mov     rax, [rdi]
0x1801066d1  lea     r8, [rbp+57h+nChar]
0x1801066d5  lea     rdx, [rbp+57h+pszStr1]
0x1801066d9  mov     [rbp+57h+pszStr1], r15
0x1801066dd  mov     rcx, rdi
0x1801066e0  mov     dword ptr [rbp+57h+nChar], r15d
0x1801066e4  mov     rax, [rax+70h]
0x1801066e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801066ed  test    eax, eax
0x1801066ef  js      loc_180106910
0x1801066f5  mov     r8d, dword ptr [rbp+57h+nChar]; nChar
0x1801066f9  lea     eax, [r8+1]
0x1801066fd  cmp     eax, 0Ah
0x180106700  jnz     short loc_180106750
0x180106702  mov     rcx, [rbp+57h+pszStr1]; pszStr1
0x180106706  lea     rdx, aGroupname; "groupname"
0x18010670d  call    cs:__imp_StrCmpNICW
0x180106714  nop     dword ptr [rax+rax+00h]
0x180106719  test    eax, eax
0x18010671b  jnz     short loc_18010674C
0x18010671d  mov     rax, [rdi]
0x180106720  lea     r8, [rbp+57h+var_50]
0x180106724  lea     rdx, [rbp+57h+psz]
0x180106728  mov     [rbp+57h+psz], r15
0x18010672c  mov     rcx, rdi
0x18010672f  mov     rax, [rax+80h]
0x180106736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010673b  test    eax, eax
0x18010673d  js      loc_180106910
0x180106743  lea     rdx, [rbp+57h+pv]
0x180106747  jmp     loc_1801068EB
0x18010674c  mov     r8d, dword ptr [rbp+57h+nChar]; nChar
0x180106750  lea     eax, [r8+1]
0x180106754  cmp     eax, 8
0x180106757  jnz     short loc_1801067A7
0x180106759  mov     rcx, [rbp+57h+pszStr1]; pszStr1
0x18010675d  lea     rdx, aFwdlink; "fwdlink"
0x180106764  call    cs:__imp_StrCmpNICW
0x18010676b  nop     dword ptr [rax+rax+00h]
0x180106770  test    eax, eax
0x180106772  jnz     short loc_1801067A3
0x180106774  mov     rax, [rdi]
0x180106777  lea     r8, [rbp+57h+var_4C]
0x18010677b  lea     rdx, [rbp+57h+psz]
0x18010677f  mov     [rbp+57h+psz], r15
0x180106783  mov     rcx, rdi
0x180106786  mov     rax, [rax+80h]
0x18010678d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106792  test    eax, eax
0x180106794  js      loc_180106910
0x18010679a  lea     rdx, [rbp+57h+var_40]
0x18010679e  jmp     loc_1801068EB
0x1801067a3  mov     r8d, dword ptr [rbp+57h+nChar]; nChar
0x1801067a7  lea     eax, [r8+1]
0x1801067ab  cmp     eax, 0Dh
0x1801067ae  jnz     short loc_1801067FD
0x1801067b0  mov     rcx, [rbp+57h+pszStr1]; pszStr1
0x1801067b4  lea     rdx, aAllowedgroup; "allowedgroup"
0x1801067bb  call    cs:__imp_StrCmpNICW
0x1801067c2  nop     dword ptr [rax+rax+00h]
0x1801067c7  test    eax, eax
0x1801067c9  jnz     short loc_1801067F9
0x1801067cb  mov     rax, [rdi]
0x1801067ce  lea     rdx, [rbp+57h+psz]
0x1801067d2  xor     r8d, r8d
0x1801067d5  mov     [rbp+57h+psz], r15
0x1801067d9  mov     rcx, rdi
0x1801067dc  mov     rax, [rax+80h]
0x1801067e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801067e8  test    eax, eax
0x1801067ea  js      loc_180106910
0x1801067f0  lea     rdx, [rbp+57h+var_38]
0x1801067f4  jmp     loc_1801068EB
0x1801067f9  mov     r8d, dword ptr [rbp+57h+nChar]; nChar
0x1801067fd  lea     eax, [r8+1]
0x180106801  cmp     eax, 0Ch
0x180106804  jnz     short loc_180106853
0x180106806  mov     rcx, [rbp+57h+pszStr1]; pszStr1
0x18010680a  lea     rdx, aLatestgroup; "latestgroup"
0x180106811  call    cs:__imp_StrCmpNICW
0x180106818  nop     dword ptr [rax+rax+00h]
0x18010681d  test    eax, eax
0x18010681f  jnz     short loc_18010684F
0x180106821  mov     rax, [rdi]
0x180106824  lea     rdx, [rbp+57h+psz]
0x180106828  xor     r8d, r8d
0x18010682b  mov     [rbp+57h+psz], r15
0x18010682f  mov     rcx, rdi
0x180106832  mov     rax, [rax+80h]
0x180106839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010683e  test    eax, eax
0x180106840  js      loc_180106910
0x180106846  lea     rdx, [rbp+57h+var_30]
0x18010684a  jmp     loc_1801068EB
0x18010684f  mov     r8d, dword ptr [rbp+57h+nChar]; nChar
0x180106853  lea     eax, [r8+1]
0x180106857  cmp     eax, 0Ah
0x18010685a  jnz     short loc_1801068A2
0x18010685c  mov     rcx, [rbp+57h+pszStr1]; pszStr1
0x180106860  lea     rdx, aHardblock; "hardblock"
0x180106867  call    cs:__imp_StrCmpNICW
0x18010686e  nop     dword ptr [rax+rax+00h]
0x180106873  test    eax, eax
0x180106875  jnz     short loc_18010689E
0x180106877  mov     rax, [rdi]
0x18010687a  lea     rdx, [rbp+57h+psz]
0x18010687e  xor     r8d, r8d
0x180106881  mov     [rbp+57h+psz], r15
0x180106885  mov     rcx, rdi
0x180106888  mov     rax, [rax+80h]
0x18010688f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106894  test    eax, eax
0x180106896  js      short loc_180106910
0x180106898  lea     rdx, [rbp+57h+var_28]
0x18010689c  jmp     short loc_1801068EB
0x18010689e  mov     r8d, dword ptr [rbp+57h+nChar]; nChar
0x1801068a2  lea     eax, [r8+1]
0x1801068a6  cmp     eax, 0Ch
0x1801068a9  jnz     short loc_180106918
0x1801068ab  mov     rcx, [rbp+57h+pszStr1]; pszStr1
0x1801068af  lea     rdx, aSilentblock; "silentblock"
0x1801068b6  call    cs:__imp_StrCmpNICW
0x1801068bd  nop     dword ptr [rax+rax+00h]
0x1801068c2  test    eax, eax
0x1801068c4  jnz     short loc_180106918
0x1801068c6  mov     rax, [rdi]
0x1801068c9  lea     rdx, [rbp+57h+psz]
0x1801068cd  xor     r8d, r8d
0x1801068d0  mov     [rbp+57h+psz], r15
0x1801068d4  mov     rcx, rdi
0x1801068d7  mov     rax, [rax+80h]
0x1801068de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801068e3  test    eax, eax
0x1801068e5  js      short loc_180106910
0x1801068e7  lea     rdx, [rbp+57h+ppwsz]; ppwsz
0x1801068eb  mov     rcx, [rbp+57h+psz]; psz
0x1801068ef  call    cs:__imp_SHStrDupW
0x1801068f6  nop     dword ptr [rax+rax+00h]
0x1801068fb  test    eax, eax
0x1801068fd  js      short loc_180106910
0x1801068ff  mov     rax, [rdi]
0x180106902  mov     rcx, rdi
0x180106905  mov     rax, [rax+48h]
0x180106909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010690e  test    eax, eax
0x180106910  jz      loc_1801066CE
0x180106916  jmp     short loc_18010691D
0x180106918  mov     eax, 8007139Fh
0x18010691d  cmp     eax, 1
0x180106920  mov     ebx, r15d
0x180106923  cmovnz  ebx, eax
0x180106926  test    ebx, ebx
0x180106928  js      loc_180106AB1
0x18010692e  mov     rdx, [rbp+57h+pv]
0x180106932  test    rdx, rdx
0x180106935  jz      loc_180106AAC
0x18010693b  cmp     [rbp+57h+var_50], r15d
0x18010693f  jz      loc_180106AAC
0x180106945  cmp     [rbp+57h+var_40], r15
0x180106949  jz      loc_180106AAC
0x18010694f  cmp     [rbp+57h+var_4C], r15d
0x180106953  jz      loc_180106AAC
0x180106959  mov     rcx, [r14+20h]
0x18010695d  call    ?ContainsKey@?$CHashTable@UGROUP_ENTRY@@G@@QEBAJPEBG@Z; CHashTable<GROUP_ENTRY,ushort>::ContainsKey(ushort const *)
0x180106962  test    eax, eax
0x180106964  jns     loc_180106AAC
0x18010696a  mov     ecx, 18h; cb
0x18010696f  call    cs:__imp_CoTaskMemAlloc
0x180106976  nop     dword ptr [rax+rax+00h]
0x18010697b  mov     rdi, rax
0x18010697e  test    rax, rax
0x180106981  jnz     short loc_18010698D
0x180106983  mov     ebx, 8007000Eh
0x180106988  jmp     loc_180106AB1
0x18010698d  xorps   xmm0, xmm0
0x180106990  mov     [rbp+57h+nChar], r15
0x180106994  movups  xmmword ptr [rdi], xmm0
0x180106997  xor     eax, eax
0x180106999  lea     r9, [rbp+57h+nChar]; unsigned __int16 **
0x18010699d  mov     [rdi+10h], rax
0x1801069a1  mov     rcx, r14; this
0x1801069a4  mov     r8d, [rbp+57h+var_50]; unsigned int
0x1801069a8  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x1801069ac  call    ?_GetCachedString@CBlockListManager@@AEAAJPEBGIPEAPEAG@Z; CBlockListManager::_GetCachedString(ushort const *,uint,ushort * *)
0x1801069b1  mov     ebx, eax
0x1801069b3  test    eax, eax
0x1801069b5  js      loc_180106A9B
0x1801069bb  mov     rax, [rbp+57h+nChar]
0x1801069bf  test    rax, rax
0x1801069c2  jz      loc_180106A96
0x1801069c8  mov     [rdi+8], rax
0x1801069cc  lea     r9, [rbp+57h+psz]; unsigned __int16 **
0x1801069d0  mov     r8d, [rbp+57h+var_4C]; unsigned int
0x1801069d4  mov     rcx, r14; this
0x1801069d7  mov     rdx, [rbp+57h+var_40]; unsigned __int16 *
0x1801069db  mov     [rbp+57h+psz], r15
0x1801069df  call    ?_GetCachedString@CBlockListManager@@AEAAJPEBGIPEAPEAG@Z; CBlockListManager::_GetCachedString(ushort const *,uint,ushort * *)
0x1801069e4  mov     ebx, eax
0x1801069e6  test    eax, eax
0x1801069e8  js      loc_180106A9B
0x1801069ee  mov     rax, [rbp+57h+psz]
0x1801069f2  test    rax, rax
0x1801069f5  jz      loc_180106A8B
0x1801069fb  mov     [rdi], rax
0x1801069fe  mov     rdx, [rbp+57h+var_38]; unsigned __int16 *
0x180106a02  test    rdx, rdx
0x180106a05  jz      short loc_180106A1A
0x180106a07  lea     r8, [rdi+10h]; bool *
0x180106a0b  call    ?_StringToBool@CBlockListManager@@AEAAJPEBGPEA_N@Z; CBlockListManager::_StringToBool(ushort const *,bool *)
0x180106a10  mov     ebx, eax
0x180106a12  test    eax, eax
0x180106a14  js      loc_180106A9B
0x180106a1a  mov     rdx, [rbp+57h+var_30]; unsigned __int16 *
0x180106a1e  test    rdx, rdx
0x180106a21  jz      short loc_180106A32
0x180106a23  lea     r8, [rdi+11h]; bool *
0x180106a27  call    ?_StringToBool@CBlockListManager@@AEAAJPEBGPEA_N@Z; CBlockListManager::_StringToBool(ushort const *,bool *)
0x180106a2c  mov     ebx, eax
0x180106a2e  test    eax, eax
0x180106a30  js      short loc_180106A9B
0x180106a32  mov     rdx, [rbp+57h+var_28]; unsigned __int16 *
0x180106a36  test    rdx, rdx
0x180106a39  jz      short loc_180106A4A
0x180106a3b  lea     r8, [rdi+12h]; bool *
0x180106a3f  call    ?_StringToBool@CBlockListManager@@AEAAJPEBGPEA_N@Z; CBlockListManager::_StringToBool(ushort const *,bool *)
0x180106a44  mov     ebx, eax
0x180106a46  test    eax, eax
0x180106a48  js      short loc_180106A9B
0x180106a4a  mov     rdx, [rbp+57h+ppwsz]; unsigned __int16 *
0x180106a4e  test    rdx, rdx
0x180106a51  jz      short loc_180106A62
0x180106a53  lea     r8, [rdi+13h]; bool *
0x180106a57  call    ?_StringToBool@CBlockListManager@@AEAAJPEBGPEA_N@Z; CBlockListManager::_StringToBool(ushort const *,bool *)
0x180106a5c  mov     ebx, eax
0x180106a5e  test    eax, eax
0x180106a60  js      short loc_180106A9B
0x180106a62  mov     rcx, [rbp+57h+pv]; unsigned __int16 *
0x180106a66  mov     [rbp+57h+pszStr1], rdi
0x180106a6a  call    ?_SizeOfString@@YAIPEBG@Z; _SizeOfString(ushort const *)
0x180106a6f  lea     rdx, [rbp+57h+pszStr1]; int
0x180106a73  mov     r8, rcx; unsigned __int8 *
0x180106a76  mov     rcx, [r14+20h]; this
0x180106a7a  mov     r9d, eax; unsigned int
0x180106a7d  mov     [rsp+0A0h+var_80], rdx; unsigned __int8 *
0x180106a82  call    ?_AddUpdateItem@CByteHashTable@@AEAAJHPEBEI0IPEAEI@Z; CByteHashTable::_AddUpdateItem(int,uchar const *,uint,uchar const *,uint,uchar *,uint)
0x180106a87  mov     ebx, eax
0x180106a89  jmp     short loc_180106A90
0x180106a8b  mov     ebx, 8007139Fh
0x180106a90  test    ebx, ebx
0x180106a92  js      short loc_180106A9B
0x180106a94  jmp     short loc_180106AB1
0x180106a96  mov     ebx, 8007139Fh
0x180106a9b  mov     rcx, rdi; pv
0x180106a9e  call    cs:__imp_CoTaskMemFree
0x180106aa5  nop     dword ptr [rax+rax+00h]
0x180106aaa  jmp     short loc_180106AB1
0x180106aac  mov     ebx, 8007139Fh
0x180106ab1  mov     rcx, [rbp+57h+pv]; pv
  ... truncated ...
```
