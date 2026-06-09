# CBlockListManager::_HandleBlockListEntryElement(ushort const *,uint,IXmlReader *,BLOCKLIST_LOAD_STATE)

- ea: `0x1800fb158`
- end: `0x1800fb4e3`
- name: `?_HandleBlockListEntryElement@CBlockListManager@@AEAAJPEBGIPEAUIXmlReader@@W4BLOCKLIST_LOAD_STATE@@@Z`
- size: `907`
- prototype: `int __high(const unsigned __int16 *, unsigned int, struct IXmlReader *, enum BLOCKLIST_LOAD_STATE)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800fb4ec`
- `0x1800fb7a0`

## callees

- `0x1800f62a4`
- `0x1800f9354`
- `0x1800faa38`
- `0x1800fac08`
- `0x1800fac40`
- `0x1800fb158`
- `0x1800fc708`
- `0x1800fc83c`
- `0x18010c5e4`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fb1aa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fb227`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fb28d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fb1aa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fb227`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fb28d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fb339`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fb339`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800fb371`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800fb43c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800fb371`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800fb43c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb40d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb4b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb40d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb4b1`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800fb262`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800fb262`

## pseudocode

```c
__int64 __fastcall CBlockListManager::_HandleBlockListEntryElement(
        __int64 a1,
        const WCHAR *a2,
        int a3,
        __int64 *a4,
        int a5)
{
  int v7; // ebx
  int v8; // r14d
  __int64 v9; // rax
  HRESULT v10; // eax
  bool v11; // zf
  int v12; // r8d
  __int64 v13; // rax
  __int64 v14; // rax
  CBlockListManager *v15; // rcx
  _OWORD *v16; // rax
  void *v17; // r15
  CBlockListManager *v18; // rcx
  int v19; // edx
  CByteHashTable *v20; // rcx
  int updated; // eax
  unsigned int v22; // eax
  const unsigned __int8 *v23; // rcx
  CBlockListManager *v24; // rcx
  int Ptr; // eax
  unsigned int v27; // [rsp+28h] [rbp-39h]
  unsigned __int8 *v28; // [rsp+30h] [rbp-31h]
  unsigned int v29; // [rsp+38h] [rbp-29h]
  LPWSTR ppwsz; // [rsp+40h] [rbp-21h] BYREF
  int nChar; // [rsp+48h] [rbp-19h] BYREF
  LPCWSTR psz; // [rsp+50h] [rbp-11h] BYREF
  GUID pclsid; // [rsp+58h] [rbp-9h] BYREF
  LPCWSTR pszStr1[2]; // [rsp+68h] [rbp+7h] BYREF

  if ( !a2 || !a4 )
    return 2147942487LL;
  if ( a3 != 14 || StrCmpNICW(a2, L"blocklistentry", 14) )
    return (unsigned int)-2147019873;
  v7 = (*(__int64 (__fastcall **)(__int64 *))(*a4 + 64))(a4);
  if ( v7 )
    return (unsigned int)v7;
  ppwsz = 0;
  v8 = 0;
  while ( 1 )
  {
    v9 = *a4;
    pszStr1[0] = 0;
    nChar = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, LPCWSTR *, int *))(v9 + 112))(a4, pszStr1, &nChar);
    v11 = v10 == 0;
    if ( v10 < 0 )
      goto LABEL_22;
    v12 = nChar;
    if ( nChar != 3 )
      goto LABEL_14;
    if ( StrCmpNICW(pszStr1[0], L"key", 3) )
      break;
    v13 = *a4;
    psz = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, LPCWSTR *, _QWORD))(v13 + 128))(a4, &psz, 0);
    v11 = v10 == 0;
    if ( v10 >= 0 )
    {
      v10 = SHStrDupW(psz, &ppwsz);
      if ( v10 >= 0 )
        goto LABEL_20;
      goto LABEL_21;
    }
LABEL_22:
    if ( !v11 )
      goto LABEL_26;
  }
  v12 = nChar;
LABEL_14:
  if ( v12 == 9 && !StrCmpNICW(pszStr1[0], L"entrytype", 9) )
  {
    v14 = *a4;
    *(_QWORD *)&pclsid.Data1 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD))(v14 + 128))(a4, &pclsid, 0);
    v11 = v10 == 0;
    if ( v10 < 0 )
      goto LABEL_22;
    LODWORD(psz) = 0;
    v10 = CBlockListManager::_StringToULong(v15, *(const unsigned __int16 **)&pclsid.Data1, (unsigned int *)&psz, 2u);
    v11 = v10 == 0;
    if ( v10 < 0 )
      goto LABEL_22;
    if ( !(_DWORD)psz )
    {
      v10 = -2147024362;
      goto LABEL_26;
    }
    v8 = (int)psz;
LABEL_20:
    v10 = (*(__int64 (__fastcall **)(__int64 *))(*a4 + 72))(a4);
LABEL_21:
    v11 = v10 == 0;
    goto LABEL_22;
  }
  v10 = -2147019873;
LABEL_26:
  v7 = 0;
  if ( v10 != 1 )
    v7 = v10;
  if ( v7 < 0 )
    goto LABEL_59;
  if ( !ppwsz || !v8 )
    goto LABEL_58;
  if ( a5 != 1 )
  {
    if ( a5 == 2 )
    {
      if ( v8 == 2 )
      {
        pclsid = GUID_NULL;
        if ( CLSIDFromString(ppwsz, &pclsid) < 0 )
        {
          v7 = CBlockListManager::_PartialCLSIDFromString(v24, ppwsz, &pclsid);
          if ( v7 < 0 )
            goto LABEL_59;
        }
        if ( (int)CHashTableEx<BLOCKLIST_ENTRY,_GUID,CCLSIDTrait>::ContainsKey(*(_QWORD *)(a1 + 56), &pclsid) >= 0 )
        {
          Ptr = CHashTableEx<BLOCKLIST_ENTRY,_GUID,CCLSIDTrait>::GetPtr(*(_QWORD *)(a1 + 56), &pclsid, a1 + 16);
          goto LABEL_54;
        }
      }
      else if ( v8 == 1 )
      {
        v7 = CHashTable<GROUP_ENTRY,unsigned short>::ContainsKey(*(_QWORD *)(a1 + 48));
        if ( v7 < 0 )
          goto LABEL_59;
        Ptr = CHashTable<BLOCKLIST_ENTRY,unsigned short>::GetPtr(*(_QWORD *)(a1 + 48), ppwsz, a1 + 16);
LABEL_54:
        v7 = Ptr;
        goto LABEL_59;
      }
    }
LABEL_58:
    v7 = -2147019873;
    goto LABEL_59;
  }
  v16 = CoTaskMemAlloc(0x10u);
  v17 = v16;
  if ( !v16 )
  {
    v7 = -2147024882;
    goto LABEL_59;
  }
  *v16 = 0;
  if ( v8 == 2 )
  {
    *(GUID *)pszStr1 = GUID_NULL;
    if ( CLSIDFromString(ppwsz, (LPCLSID)pszStr1) >= 0
      || (v7 = CBlockListManager::_PartialCLSIDFromString(v18, ppwsz, (struct _GUID *)pszStr1), v7 >= 0) )
    {
      if ( (int)CHashTableEx<BLOCKLIST_ENTRY,_GUID,CCLSIDTrait>::ContainsKey(*(_QWORD *)(a1 + 56), pszStr1) < 0 )
      {
        v20 = *(CByteHashTable **)(a1 + 56);
        *(_QWORD *)&pclsid.Data1 = v17;
        updated = CByteHashTable::_AddUpdateItem(
                    v20,
                    v19,
                    (const unsigned __int8 *)pszStr1,
                    0x10u,
                    (const unsigned __int8 *)&pclsid,
                    v27,
                    v28,
                    v29);
        goto LABEL_42;
      }
LABEL_43:
      v7 = -2147019873;
      goto LABEL_44;
    }
    goto LABEL_47;
  }
  if ( v8 != 1 )
  {
    v7 = -2147019873;
    goto LABEL_47;
  }
  if ( (int)CHashTable<GROUP_ENTRY,unsigned short>::ContainsKey(*(_QWORD *)(a1 + 48)) >= 0 )
    goto LABEL_43;
  *(_QWORD *)&pclsid.Data1 = v17;
  v22 = _SizeOfString(ppwsz);
  updated = CByteHashTable::_AddUpdateItem(
              *(CByteHashTable **)(a1 + 48),
              (int)&pclsid,
              v23,
              v22,
              (const unsigned __int8 *)&pclsid,
              v27,
              v28,
              v29);
LABEL_42:
  v7 = updated;
LABEL_44:
  if ( v7 < 0 )
LABEL_47:
    CoTaskMemFree(v17);
LABEL_59:
  CoTaskMemFree(ppwsz);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800fb158  push    rbp
0x1800fb15a  push    rbx
0x1800fb15b  push    rsi
0x1800fb15c  push    rdi
0x1800fb15d  push    r14
0x1800fb15f  push    r15
0x1800fb161  lea     rbp, [rsp-27h]
0x1800fb166  sub     rsp, 88h
0x1800fb16d  mov     rax, cs:__security_cookie
0x1800fb174  xor     rax, rsp
0x1800fb177  mov     [rbp+4Fh+var_38], rax
0x1800fb17b  mov     r15, r9
0x1800fb17e  mov     rax, rdx
0x1800fb181  mov     rsi, rcx
0x1800fb184  test    rdx, rdx
0x1800fb187  jz      loc_1800FB4C2
0x1800fb18d  test    r9, r9
0x1800fb190  jz      loc_1800FB4C2
0x1800fb196  cmp     r8d, 0Eh
0x1800fb19a  jnz     loc_1800FB4B9
0x1800fb1a0  lea     rdx, aBlocklistentry; "blocklistentry"
0x1800fb1a7  mov     rcx, rax; pszStr1
0x1800fb1aa  call    cs:__imp_StrCmpNICW
0x1800fb1b0  test    eax, eax
0x1800fb1b2  jnz     loc_1800FB4B9
0x1800fb1b8  mov     rax, [r15]
0x1800fb1bb  mov     rcx, r15
0x1800fb1be  mov     rax, [rax+40h]
0x1800fb1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb1c7  mov     ebx, eax
0x1800fb1c9  test    eax, eax
0x1800fb1cb  jnz     loc_1800FB4BE
0x1800fb1d1  mov     [rbp+4Fh+ppwsz], 0
0x1800fb1d9  xor     r14d, r14d
0x1800fb1dc  mov     rax, [r15]
0x1800fb1df  lea     r8, [rbp+4Fh+nChar]
0x1800fb1e3  lea     rdx, [rbp+4Fh+pszStr1]
0x1800fb1e7  mov     [rbp+4Fh+pszStr1], 0
0x1800fb1ef  mov     rcx, r15
0x1800fb1f2  mov     [rbp+4Fh+nChar], 0
0x1800fb1f9  mov     rax, [rax+70h]
0x1800fb1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb202  mov     edi, 8007139Fh
0x1800fb207  test    eax, eax
0x1800fb209  js      loc_1800FB2F5
0x1800fb20f  mov     r8d, [rbp+4Fh+nChar]; nChar
0x1800fb213  lea     eax, [r8+1]
0x1800fb217  cmp     eax, 4
0x1800fb21a  jnz     short loc_1800FB275
0x1800fb21c  mov     rcx, [rbp+4Fh+pszStr1]; pszStr1
0x1800fb220  lea     rdx, aKey; "key"
0x1800fb227  call    cs:__imp_StrCmpNICW
0x1800fb22d  test    eax, eax
0x1800fb22f  jnz     short loc_1800FB271
0x1800fb231  mov     rax, [r15]
0x1800fb234  lea     rdx, [rbp+4Fh+psz]
0x1800fb238  xor     r8d, r8d
0x1800fb23b  mov     [rbp+4Fh+psz], 0
0x1800fb243  mov     rcx, r15
0x1800fb246  mov     rax, [rax+80h]
0x1800fb24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb252  test    eax, eax
0x1800fb254  js      loc_1800FB2F5
0x1800fb25a  mov     rcx, [rbp+4Fh+psz]; psz
0x1800fb25e  lea     rdx, [rbp+4Fh+ppwsz]; ppwsz
0x1800fb262  call    cs:__imp_SHStrDupW
0x1800fb268  test    eax, eax
0x1800fb26a  jns     short loc_1800FB2E4
0x1800fb26c  jmp     loc_1800FB2F3
0x1800fb271  mov     r8d, [rbp+4Fh+nChar]; nChar
0x1800fb275  lea     eax, [r8+1]
0x1800fb279  cmp     eax, 0Ah
0x1800fb27c  jnz     loc_1800FB304
0x1800fb282  mov     rcx, [rbp+4Fh+pszStr1]; pszStr1
0x1800fb286  lea     rdx, aEntrytype; "entrytype"
0x1800fb28d  call    cs:__imp_StrCmpNICW
0x1800fb293  test    eax, eax
0x1800fb295  jnz     short loc_1800FB304
0x1800fb297  mov     rax, [r15]
0x1800fb29a  lea     rdx, [rbp+4Fh+pclsid]
0x1800fb29e  xor     r8d, r8d
0x1800fb2a1  mov     qword ptr [rbp+4Fh+pclsid.Data1], 0
0x1800fb2a9  mov     rcx, r15
0x1800fb2ac  mov     rax, [rax+80h]
0x1800fb2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb2b8  test    eax, eax
0x1800fb2ba  js      short loc_1800FB2F5
0x1800fb2bc  mov     rdx, qword ptr [rbp+4Fh+pclsid.Data1]; unsigned __int16 *
0x1800fb2c0  lea     r8, [rbp+4Fh+psz]; unsigned int *
0x1800fb2c4  mov     r9d, 2; unsigned int
0x1800fb2ca  mov     dword ptr [rbp+4Fh+psz], 0
0x1800fb2d1  call    ?_StringToULong@CBlockListManager@@AEAAJPEBGPEAKK@Z; CBlockListManager::_StringToULong(ushort const *,ulong *,ulong)
0x1800fb2d6  test    eax, eax
0x1800fb2d8  js      short loc_1800FB2F5
0x1800fb2da  mov     eax, dword ptr [rbp+4Fh+psz]
0x1800fb2dd  test    eax, eax
0x1800fb2df  jz      short loc_1800FB2FD
0x1800fb2e1  mov     r14d, eax
0x1800fb2e4  mov     rax, [r15]
0x1800fb2e7  mov     rcx, r15
0x1800fb2ea  mov     rax, [rax+48h]
0x1800fb2ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb2f3  test    eax, eax
0x1800fb2f5  jz      loc_1800FB1DC
0x1800fb2fb  jmp     short loc_1800FB306
0x1800fb2fd  mov     eax, 80070216h
0x1800fb302  jmp     short loc_1800FB306
0x1800fb304  mov     eax, edi
0x1800fb306  xor     ebx, ebx
0x1800fb308  cmp     eax, 1
0x1800fb30b  cmovnz  ebx, eax
0x1800fb30e  test    ebx, ebx
0x1800fb310  js      loc_1800FB4AD
0x1800fb316  cmp     [rbp+4Fh+ppwsz], 0
0x1800fb31b  jz      loc_1800FB4AB
0x1800fb321  test    r14d, r14d
0x1800fb324  jz      loc_1800FB4AB
0x1800fb32a  cmp     [rbp+4Fh+arg_20], 1
0x1800fb32e  jnz     loc_1800FB418
0x1800fb334  mov     ecx, 10h; cb
0x1800fb339  call    cs:__imp_CoTaskMemAlloc
0x1800fb33f  mov     r15, rax
0x1800fb342  test    rax, rax
0x1800fb345  jnz     short loc_1800FB351
0x1800fb347  mov     ebx, 8007000Eh
0x1800fb34c  jmp     loc_1800FB4AD
0x1800fb351  xorps   xmm0, xmm0
0x1800fb354  movups  xmmword ptr [rax], xmm0
0x1800fb357  cmp     r14d, 2
0x1800fb35b  jnz     short loc_1800FB3BC
0x1800fb35d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800fb364  mov     rcx, [rbp+4Fh+ppwsz]; lpsz
0x1800fb368  lea     rdx, [rbp+4Fh+pszStr1]; pclsid
0x1800fb36c  movdqu  xmmword ptr [rbp+4Fh+pszStr1], xmm0
0x1800fb371  call    cs:__imp_CLSIDFromString
0x1800fb377  test    eax, eax
0x1800fb379  jns     short loc_1800FB38E
0x1800fb37b  mov     rdx, [rbp+4Fh+ppwsz]; unsigned __int16 *
0x1800fb37f  lea     r8, [rbp+4Fh+pszStr1]; struct _GUID *
0x1800fb383  call    ?_PartialCLSIDFromString@CBlockListManager@@AEAAJPEBGPEAU_GUID@@@Z; CBlockListManager::_PartialCLSIDFromString(ushort const *,_GUID *)
0x1800fb388  mov     ebx, eax
0x1800fb38a  test    eax, eax
0x1800fb38c  js      short loc_1800FB40A
0x1800fb38e  mov     rcx, [rsi+38h]
0x1800fb392  lea     rdx, [rbp+4Fh+pszStr1]
0x1800fb396  call    ?ContainsKey@?$CHashTableEx@UBLOCKLIST_ENTRY@@U_GUID@@VCCLSIDTrait@@@@QEBAJPEBU_GUID@@@Z; CHashTableEx<BLOCKLIST_ENTRY,_GUID,CCLSIDTrait>::ContainsKey(_GUID const *)
0x1800fb39b  test    eax, eax
0x1800fb39d  jns     short loc_1800FB3FC
0x1800fb39f  mov     rcx, [rsi+38h]
0x1800fb3a3  lea     rax, [rbp+4Fh+pclsid]
0x1800fb3a7  mov     [rsp+0B0h+var_90], rax
0x1800fb3ac  lea     r8, [rbp+4Fh+pszStr1]
0x1800fb3b0  mov     qword ptr [rbp+4Fh+pclsid.Data1], r15
0x1800fb3b4  mov     r9d, 10h
0x1800fb3ba  jmp     short loc_1800FB3F3
0x1800fb3bc  cmp     r14d, 1
0x1800fb3c0  jnz     short loc_1800FB408
0x1800fb3c2  mov     rdx, [rbp+4Fh+ppwsz]
0x1800fb3c6  mov     rcx, [rsi+30h]
0x1800fb3ca  call    ?ContainsKey@?$CHashTable@UGROUP_ENTRY@@G@@QEBAJPEBG@Z; CHashTable<GROUP_ENTRY,ushort>::ContainsKey(ushort const *)
0x1800fb3cf  test    eax, eax
0x1800fb3d1  jns     short loc_1800FB3FC
0x1800fb3d3  mov     rcx, [rbp+4Fh+ppwsz]; unsigned __int16 *
0x1800fb3d7  mov     qword ptr [rbp+4Fh+pclsid.Data1], r15
0x1800fb3db  call    ?_SizeOfString@@YAIPEBG@Z; _SizeOfString(ushort const *)
0x1800fb3e0  lea     rdx, [rbp+4Fh+pclsid]; int
0x1800fb3e4  mov     r8, rcx; unsigned __int8 *
0x1800fb3e7  mov     rcx, [rsi+30h]; this
0x1800fb3eb  mov     r9d, eax; unsigned int
0x1800fb3ee  mov     [rsp+0B0h+var_90], rdx; unsigned __int8 *
0x1800fb3f3  call    ?_AddUpdateItem@CByteHashTable@@AEAAJHPEBEI0IPEAEI@Z; CByteHashTable::_AddUpdateItem(int,uchar const *,uint,uchar const *,uint,uchar *,uint)
0x1800fb3f8  mov     ebx, eax
0x1800fb3fa  jmp     short loc_1800FB3FE
0x1800fb3fc  mov     ebx, edi
0x1800fb3fe  test    ebx, ebx
0x1800fb400  jns     loc_1800FB4AD
0x1800fb406  jmp     short loc_1800FB40A
0x1800fb408  mov     ebx, edi
0x1800fb40a  mov     rcx, r15; pv
0x1800fb40d  call    cs:__imp_CoTaskMemFree
0x1800fb413  jmp     loc_1800FB4AD
0x1800fb418  cmp     [rbp+4Fh+arg_20], 2
0x1800fb41c  jnz     loc_1800FB4AB
0x1800fb422  cmp     r14d, 2
0x1800fb426  jnz     short loc_1800FB47F
0x1800fb428  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800fb42f  mov     rcx, [rbp+4Fh+ppwsz]; lpsz
0x1800fb433  lea     rdx, [rbp+4Fh+pclsid]; pclsid
0x1800fb437  movdqu  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x1800fb43c  call    cs:__imp_CLSIDFromString
0x1800fb442  test    eax, eax
0x1800fb444  jns     short loc_1800FB459
0x1800fb446  mov     rdx, [rbp+4Fh+ppwsz]; unsigned __int16 *
0x1800fb44a  lea     r8, [rbp+4Fh+pclsid]; struct _GUID *
0x1800fb44e  call    ?_PartialCLSIDFromString@CBlockListManager@@AEAAJPEBGPEAU_GUID@@@Z; CBlockListManager::_PartialCLSIDFromString(ushort const *,_GUID *)
0x1800fb453  mov     ebx, eax
0x1800fb455  test    eax, eax
0x1800fb457  js      short loc_1800FB4AD
0x1800fb459  mov     rcx, [rsi+38h]
0x1800fb45d  lea     rdx, [rbp+4Fh+pclsid]
0x1800fb461  call    ?ContainsKey@?$CHashTableEx@UBLOCKLIST_ENTRY@@U_GUID@@VCCLSIDTrait@@@@QEBAJPEBU_GUID@@@Z; CHashTableEx<BLOCKLIST_ENTRY,_GUID,CCLSIDTrait>::ContainsKey(_GUID const *)
0x1800fb466  test    eax, eax
0x1800fb468  js      short loc_1800FB4AB
0x1800fb46a  mov     rcx, [rsi+38h]
0x1800fb46e  lea     r8, [rsi+10h]
0x1800fb472  lea     rdx, [rbp+4Fh+pclsid]
0x1800fb476  call    ?GetPtr@?$CHashTableEx@UBLOCKLIST_ENTRY@@U_GUID@@VCCLSIDTrait@@@@QEBAJPEBU_GUID@@PEAPEAUBLOCKLIST_ENTRY@@@Z; CHashTableEx<BLOCKLIST_ENTRY,_GUID,CCLSIDTrait>::GetPtr(_GUID const *,BLOCKLIST_ENTRY * *)
0x1800fb47b  mov     ebx, eax
0x1800fb47d  jmp     short loc_1800FB4AD
0x1800fb47f  cmp     r14d, 1
0x1800fb483  jnz     short loc_1800FB4AB
0x1800fb485  mov     rdx, [rbp+4Fh+ppwsz]
0x1800fb489  mov     rcx, [rsi+30h]
0x1800fb48d  call    ?ContainsKey@?$CHashTable@UGROUP_ENTRY@@G@@QEBAJPEBG@Z; CHashTable<GROUP_ENTRY,ushort>::ContainsKey(ushort const *)
0x1800fb492  mov     ebx, eax
0x1800fb494  test    eax, eax
0x1800fb496  js      short loc_1800FB4AD
0x1800fb498  mov     rdx, [rbp+4Fh+ppwsz]
0x1800fb49c  lea     r8, [rsi+10h]
0x1800fb4a0  mov     rcx, [rsi+30h]
0x1800fb4a4  call    ?GetPtr@?$CHashTable@UBLOCKLIST_ENTRY@@G@@QEBAJPEBGPEAPEAUBLOCKLIST_ENTRY@@@Z; CHashTable<BLOCKLIST_ENTRY,ushort>::GetPtr(ushort const *,BLOCKLIST_ENTRY * *)
0x1800fb4a9  jmp     short loc_1800FB47B
0x1800fb4ab  mov     ebx, edi
0x1800fb4ad  mov     rcx, [rbp+4Fh+ppwsz]; pv
0x1800fb4b1  call    cs:__imp_CoTaskMemFree
0x1800fb4b7  jmp     short loc_1800FB4BE
0x1800fb4b9  mov     ebx, 8007139Fh
0x1800fb4be  mov     eax, ebx
0x1800fb4c0  jmp     short loc_1800FB4C7
0x1800fb4c2  mov     eax, 80070057h
0x1800fb4c7  mov     rcx, [rbp+4Fh+var_38]
0x1800fb4cb  xor     rcx, rsp; StackCookie
0x1800fb4ce  call    __security_check_cookie
0x1800fb4d3  add     rsp, 88h
0x1800fb4da  pop     r15
0x1800fb4dc  pop     r14
0x1800fb4de  pop     rdi
0x1800fb4df  pop     rsi
0x1800fb4e0  pop     rbx
0x1800fb4e1  pop     rbp
0x1800fb4e2  retn
```
