# CBlockListManager::_HandleVersionEntryElement(ushort const *,uint,IXmlReader *)

- ea: `0x1800fbe6c`
- end: `0x1800fc267`
- name: `?_HandleVersionEntryElement@CBlockListManager@@AEAAJPEBGIPEAUIXmlReader@@@Z`
- size: `1019`
- prototype: `__int64 __fastcall(CBlockListManager *__hidden this, LPCWSTR pszStr1, unsigned int, struct IXmlReader *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800fb4ec`

## callees

- `0x1800f62a4`
- `0x1800f9354`
- `0x1800fac68`
- `0x1800fbe6c`
- `0x18010c740`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbecb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbf4d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbf9e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbfef`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fc039`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbecb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbf4d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbf9e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fbfef`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fc039`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fc20a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fc218`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fc226`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fc234`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fc20a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fc218`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fc226`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fc234`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800fc06c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800fc06c`

## pseudocode

```c
__int64 __fastcall CBlockListManager::_HandleVersionEntryElement(
        CBlockListManager *this,
        LPCWSTR pszStr1,
        int a3,
        struct IXmlReader *a4)
{
  int Value; // ebx
  struct IXmlReaderVtbl *lpVtbl; // rax
  HRESULT v9; // eax
  bool v10; // zf
  int v11; // r8d
  struct IXmlReaderVtbl *v12; // rax
  LPWSTR *p_pv; // rdx
  struct IXmlReaderVtbl *v14; // rax
  struct IXmlReaderVtbl *v15; // rax
  struct IXmlReaderVtbl *v16; // rax
  unsigned int v17; // ebx
  unsigned int v18; // esi
  __int64 *v19; // r12
  __int64 v20; // r12
  __int64 v21; // r15
  unsigned int v22; // eax
  unsigned __int8 **v23; // r9
  int *v24; // [rsp+20h] [rbp-60h]
  LPCWSTR psz; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR pszStr1a; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v28; // [rsp+54h] [rbp-2Ch] BYREF
  unsigned int v29; // [rsp+58h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int16 *v31; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int16 *v32; // [rsp+70h] [rbp-10h] BYREF
  LPWSTR ppwsz; // [rsp+78h] [rbp-8h] BYREF
  unsigned __int16 *nChar; // [rsp+B8h] [rbp+38h] BYREF

  if ( !pszStr1 || !a4 )
    return 2147942487LL;
  if ( !*((_QWORD *)this + 2) )
    return 2147947423LL;
  if ( a3 != 12 || StrCmpNICW(pszStr1, L"versionentry", 12) )
    return (unsigned int)-2147019873;
  Value = ((__int64 (__fastcall *)(struct IXmlReader *))a4->lpVtbl->MoveToFirstAttribute)(a4);
  if ( Value )
    return (unsigned int)Value;
  pv = 0;
  v27 = 0;
  v31 = 0;
  v28 = 0;
  v32 = 0;
  v29 = 0;
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
      goto LABEL_31;
    v11 = (int)nChar;
    if ( (_DWORD)nChar == 14 )
    {
      if ( !StrCmpNICW(pszStr1a, L"productversion", 14) )
      {
        v12 = a4->lpVtbl;
        psz = 0;
        v9 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, unsigned int *))v12->GetValue)(a4, &psz, &v27);
        v10 = v9 == 0;
        if ( v9 >= 0 )
        {
          p_pv = (LPWSTR *)&pv;
          goto LABEL_29;
        }
        goto LABEL_31;
      }
      v11 = (int)nChar;
    }
    if ( v11 == 11 )
    {
      if ( !StrCmpNICW(pszStr1a, L"fileversion", 11) )
      {
        v14 = a4->lpVtbl;
        psz = 0;
        v9 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, unsigned int *))v14->GetValue)(a4, &psz, &v28);
        v10 = v9 == 0;
        if ( v9 >= 0 )
        {
          p_pv = &v31;
          goto LABEL_29;
        }
        goto LABEL_31;
      }
      v11 = (int)nChar;
    }
    if ( v11 != 8 )
      goto LABEL_25;
    if ( StrCmpNICW(pszStr1a, L"filename", 8) )
      break;
    v15 = a4->lpVtbl;
    psz = 0;
    v9 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, unsigned int *))v15->GetValue)(a4, &psz, &v29);
    v10 = v9 == 0;
    if ( v9 >= 0 )
    {
      p_pv = &v32;
      goto LABEL_29;
    }
LABEL_31:
    if ( !v10 )
      goto LABEL_34;
  }
  v11 = (int)nChar;
LABEL_25:
  if ( v11 == 9 && !StrCmpNICW(pszStr1a, L"groupname", 9) )
  {
    v16 = a4->lpVtbl;
    psz = 0;
    v9 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, _QWORD))v16->GetValue)(a4, &psz, 0);
    v10 = v9 == 0;
    if ( v9 < 0 )
      goto LABEL_31;
    p_pv = &ppwsz;
LABEL_29:
    v9 = SHStrDupW(psz, p_pv);
    v10 = v9 == 0;
    if ( v9 >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(struct IXmlReader *))a4->lpVtbl->MoveToNextAttribute)(a4);
      v10 = v9 == 0;
    }
    goto LABEL_31;
  }
  v9 = -2147019873;
LABEL_34:
  Value = 0;
  if ( v9 != 1 )
    Value = v9;
  if ( Value >= 0 )
  {
    if ( !pv || !v31 || !v32 || !ppwsz || !v27 || !v28 || !v29 )
      goto LABEL_57;
    v17 = *((_DWORD *)this + 147);
    v18 = v17 + 1;
    if ( v17 + 1 < v17 )
    {
      Value = -2147024362;
    }
    else
    {
      v19 = (__int64 *)*((_QWORD *)this + 2);
      if ( v18 > *((_DWORD *)v19 + 2) )
      {
        Value = -2147024785;
      }
      else
      {
        v20 = *v19;
        if ( (int)CHashTable<GROUP_ENTRY,unsigned short>::ContainsKey(*((_QWORD *)this + 4)) < 0 )
          goto LABEL_57;
        v21 = 32LL * v17;
        v22 = _SizeOfString(ppwsz);
        Value = CByteHashTable::_GetValue(
                  *((CByteHashTable **)this + 4),
                  (const unsigned __int8 *)ppwsz,
                  v22,
                  v23,
                  v24,
                  (unsigned __int8 *)(v21 + v20 + 24),
                  8);
        if ( Value >= 0 )
        {
          nChar = 0;
          Value = CBlockListManager::_GetCachedString(this, (const unsigned __int16 *)pv, v27, &nChar);
          if ( Value >= 0 )
          {
            if ( nChar )
            {
              *(_QWORD *)(v21 + v20) = nChar;
              psz = 0;
              Value = CBlockListManager::_GetCachedString(this, v31, v28, (unsigned __int16 **)&psz);
              if ( Value < 0 )
                goto LABEL_58;
              if ( psz )
              {
                *(_QWORD *)(v21 + v20 + 8) = psz;
                pszStr1a = 0;
                Value = CBlockListManager::_GetCachedString(this, v32, v29, (unsigned __int16 **)&pszStr1a);
                if ( Value < 0 )
                  goto LABEL_58;
                if ( pszStr1a )
                {
                  *(_QWORD *)(v21 + v20 + 16) = pszStr1a;
                  *((_DWORD *)this + 147) = v18;
                  goto LABEL_58;
                }
              }
            }
LABEL_57:
            Value = -2147019873;
          }
        }
      }
    }
  }
LABEL_58:
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v31);
  v31 = 0;
  CoTaskMemFree(v32);
  v32 = 0;
  CoTaskMemFree(ppwsz);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x1800fbe6c  mov     [rsp-28h+arg_0], rbx
0x1800fbe71  mov     [rsp-28h+arg_10], rsi
0x1800fbe76  push    rbp
0x1800fbe77  push    r12
0x1800fbe79  push    r13
0x1800fbe7b  push    r14
0x1800fbe7d  push    r15
0x1800fbe7f  mov     rbp, rsp
0x1800fbe82  sub     rsp, 80h
0x1800fbe89  xor     r13d, r13d
0x1800fbe8c  mov     rsi, r9
0x1800fbe8f  mov     rax, rdx
0x1800fbe92  mov     r14, rcx
0x1800fbe95  test    rdx, rdx
0x1800fbe98  jz      loc_1800FC245
0x1800fbe9e  test    r9, r9
0x1800fbea1  jz      loc_1800FC245
0x1800fbea7  cmp     [rcx+10h], r13
0x1800fbeab  jnz     short loc_1800FBEB7
0x1800fbead  mov     eax, 8007139Fh
0x1800fbeb2  jmp     loc_1800FC24A
0x1800fbeb7  cmp     r8d, 0Ch
0x1800fbebb  jnz     loc_1800FC23C
0x1800fbec1  lea     rdx, aVersionentry; "versionentry"
0x1800fbec8  mov     rcx, rax; pszStr1
0x1800fbecb  call    cs:__imp_StrCmpNICW
0x1800fbed1  test    eax, eax
0x1800fbed3  jnz     loc_1800FC23C
0x1800fbed9  mov     rax, [rsi]
0x1800fbedc  mov     rcx, rsi
0x1800fbedf  mov     rax, [rax+40h]
0x1800fbee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbee8  mov     ebx, eax
0x1800fbeea  test    eax, eax
0x1800fbeec  jnz     loc_1800FC241
0x1800fbef2  mov     [rbp+pv], r13
0x1800fbef6  mov     [rbp+var_30], r13d
0x1800fbefa  mov     [rbp+var_18], r13
0x1800fbefe  mov     [rbp+var_2C], r13d
0x1800fbf02  mov     [rbp+var_10], r13
0x1800fbf06  mov     [rbp+var_28], r13d
0x1800fbf0a  mov     [rbp+ppwsz], r13
0x1800fbf0e  mov     rax, [rsi]
0x1800fbf11  lea     r8, [rbp+nChar]
0x1800fbf15  lea     rdx, [rbp+pszStr1]
0x1800fbf19  mov     [rbp+pszStr1], r13
0x1800fbf1d  mov     rcx, rsi
0x1800fbf20  mov     dword ptr [rbp+nChar], r13d
0x1800fbf24  mov     rax, [rax+70h]
0x1800fbf28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbf2d  test    eax, eax
0x1800fbf2f  js      loc_1800FC087
0x1800fbf35  mov     r8d, dword ptr [rbp+nChar]; nChar
0x1800fbf39  lea     eax, [r8+1]
0x1800fbf3d  cmp     eax, 0Fh
0x1800fbf40  jnz     short loc_1800FBF8A
0x1800fbf42  mov     rcx, [rbp+pszStr1]; pszStr1
0x1800fbf46  lea     rdx, aProductversion_0; "productversion"
0x1800fbf4d  call    cs:__imp_StrCmpNICW
0x1800fbf53  test    eax, eax
0x1800fbf55  jnz     short loc_1800FBF86
0x1800fbf57  mov     rax, [rsi]
0x1800fbf5a  lea     r8, [rbp+var_30]
0x1800fbf5e  lea     rdx, [rbp+psz]
0x1800fbf62  mov     [rbp+psz], r13
0x1800fbf66  mov     rcx, rsi
0x1800fbf69  mov     rax, [rax+80h]
0x1800fbf70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbf75  test    eax, eax
0x1800fbf77  js      loc_1800FC087
0x1800fbf7d  lea     rdx, [rbp+pv]
0x1800fbf81  jmp     loc_1800FC068
0x1800fbf86  mov     r8d, dword ptr [rbp+nChar]; nChar
0x1800fbf8a  lea     eax, [r8+1]
0x1800fbf8e  cmp     eax, 0Ch
0x1800fbf91  jnz     short loc_1800FBFDB
0x1800fbf93  mov     rcx, [rbp+pszStr1]; pszStr1
0x1800fbf97  lea     rdx, aFileversion_1; "fileversion"
0x1800fbf9e  call    cs:__imp_StrCmpNICW
0x1800fbfa4  test    eax, eax
0x1800fbfa6  jnz     short loc_1800FBFD7
0x1800fbfa8  mov     rax, [rsi]
0x1800fbfab  lea     r8, [rbp+var_2C]
0x1800fbfaf  lea     rdx, [rbp+psz]
0x1800fbfb3  mov     [rbp+psz], r13
0x1800fbfb7  mov     rcx, rsi
0x1800fbfba  mov     rax, [rax+80h]
0x1800fbfc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbfc6  test    eax, eax
0x1800fbfc8  js      loc_1800FC087
0x1800fbfce  lea     rdx, [rbp+var_18]
0x1800fbfd2  jmp     loc_1800FC068
0x1800fbfd7  mov     r8d, dword ptr [rbp+nChar]; nChar
0x1800fbfdb  lea     eax, [r8+1]
0x1800fbfdf  cmp     eax, 9
0x1800fbfe2  jnz     short loc_1800FC025
0x1800fbfe4  mov     rcx, [rbp+pszStr1]; pszStr1
0x1800fbfe8  lea     rdx, aFilename_3; "filename"
0x1800fbfef  call    cs:__imp_StrCmpNICW
0x1800fbff5  test    eax, eax
0x1800fbff7  jnz     short loc_1800FC021
0x1800fbff9  mov     rax, [rsi]
0x1800fbffc  lea     r8, [rbp+var_28]
0x1800fc000  lea     rdx, [rbp+psz]
0x1800fc004  mov     [rbp+psz], r13
0x1800fc008  mov     rcx, rsi
0x1800fc00b  mov     rax, [rax+80h]
0x1800fc012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc017  test    eax, eax
0x1800fc019  js      short loc_1800FC087
0x1800fc01b  lea     rdx, [rbp+var_10]
0x1800fc01f  jmp     short loc_1800FC068
0x1800fc021  mov     r8d, dword ptr [rbp+nChar]; nChar
0x1800fc025  lea     eax, [r8+1]
0x1800fc029  cmp     eax, 0Ah
0x1800fc02c  jnz     short loc_1800FC08F
0x1800fc02e  mov     rcx, [rbp+pszStr1]; pszStr1
0x1800fc032  lea     rdx, aGroupname; "groupname"
0x1800fc039  call    cs:__imp_StrCmpNICW
0x1800fc03f  test    eax, eax
0x1800fc041  jnz     short loc_1800FC08F
0x1800fc043  mov     rax, [rsi]
0x1800fc046  lea     rdx, [rbp+psz]
0x1800fc04a  xor     r8d, r8d
0x1800fc04d  mov     [rbp+psz], r13
0x1800fc051  mov     rcx, rsi
0x1800fc054  mov     rax, [rax+80h]
0x1800fc05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc060  test    eax, eax
0x1800fc062  js      short loc_1800FC087
0x1800fc064  lea     rdx, [rbp+ppwsz]; ppwsz
0x1800fc068  mov     rcx, [rbp+psz]; psz
0x1800fc06c  call    cs:__imp_SHStrDupW
0x1800fc072  test    eax, eax
0x1800fc074  js      short loc_1800FC087
0x1800fc076  mov     rax, [rsi]
0x1800fc079  mov     rcx, rsi
0x1800fc07c  mov     rax, [rax+48h]
0x1800fc080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc085  test    eax, eax
0x1800fc087  jz      loc_1800FBF0E
0x1800fc08d  jmp     short loc_1800FC094
0x1800fc08f  mov     eax, 8007139Fh
0x1800fc094  cmp     eax, 1
0x1800fc097  mov     ebx, r13d
0x1800fc09a  cmovnz  ebx, eax
0x1800fc09d  test    ebx, ebx
0x1800fc09f  js      loc_1800FC206
0x1800fc0a5  cmp     [rbp+pv], r13
0x1800fc0a9  jz      loc_1800FC201
0x1800fc0af  cmp     [rbp+var_18], r13
0x1800fc0b3  jz      loc_1800FC201
0x1800fc0b9  cmp     [rbp+var_10], r13
0x1800fc0bd  jz      loc_1800FC201
0x1800fc0c3  mov     rdx, [rbp+ppwsz]
0x1800fc0c7  test    rdx, rdx
0x1800fc0ca  jz      loc_1800FC201
0x1800fc0d0  cmp     [rbp+var_30], r13d
0x1800fc0d4  jz      loc_1800FC201
0x1800fc0da  cmp     [rbp+var_2C], r13d
0x1800fc0de  jz      loc_1800FC201
0x1800fc0e4  cmp     [rbp+var_28], r13d
0x1800fc0e8  jz      loc_1800FC201
0x1800fc0ee  mov     ebx, [r14+24Ch]
0x1800fc0f5  lea     esi, [rbx+1]
0x1800fc0f8  cmp     esi, ebx
0x1800fc0fa  jb      loc_1800FC1FA
0x1800fc100  mov     r12, [r14+10h]
0x1800fc104  cmp     esi, [r12+8]
0x1800fc109  ja      loc_1800FC1F3
0x1800fc10f  mov     rcx, [r14+20h]
0x1800fc113  mov     r12, [r12]
0x1800fc117  call    ?ContainsKey@?$CHashTable@UGROUP_ENTRY@@G@@QEBAJPEBG@Z; CHashTable<GROUP_ENTRY,ushort>::ContainsKey(ushort const *)
0x1800fc11c  test    eax, eax
0x1800fc11e  js      loc_1800FC201
0x1800fc124  mov     rcx, [rbp+ppwsz]; unsigned __int16 *
0x1800fc128  mov     r15d, ebx
0x1800fc12b  shl     r15, 5
0x1800fc12f  call    ?_SizeOfString@@YAIPEBG@Z; _SizeOfString(ushort const *)
0x1800fc134  mov     rdx, [rbp+ppwsz]; unsigned __int8 *
0x1800fc138  lea     rcx, [r12+18h]
0x1800fc13d  add     rcx, r15
0x1800fc140  mov     [rsp+80h+var_50], 8; int
0x1800fc148  mov     [rsp+80h+var_58], rcx; unsigned __int8 *
0x1800fc14d  mov     r8d, eax; unsigned int
0x1800fc150  mov     rcx, [r14+20h]; this
0x1800fc154  call    ?_GetValue@CByteHashTable@@AEBAJPEBEIPEAPEAEPEAHPEAEH@Z; CByteHashTable::_GetValue(uchar const *,uint,uchar * *,int *,uchar *,int)
0x1800fc159  mov     ebx, eax
0x1800fc15b  test    eax, eax
0x1800fc15d  js      loc_1800FC206
0x1800fc163  mov     r8d, [rbp+var_30]; unsigned int
0x1800fc167  lea     r9, [rbp+nChar]; unsigned __int16 **
0x1800fc16b  mov     rdx, [rbp+pv]; unsigned __int16 *
0x1800fc16f  mov     rcx, r14; this
0x1800fc172  mov     [rbp+nChar], r13
0x1800fc176  call    ?_GetCachedString@CBlockListManager@@AEAAJPEBGIPEAPEAG@Z; CBlockListManager::_GetCachedString(ushort const *,uint,ushort * *)
0x1800fc17b  mov     ebx, eax
0x1800fc17d  test    eax, eax
0x1800fc17f  js      loc_1800FC206
0x1800fc185  mov     rax, [rbp+nChar]
0x1800fc189  test    rax, rax
0x1800fc18c  jz      short loc_1800FC201
0x1800fc18e  mov     [r15+r12], rax
0x1800fc192  lea     r9, [rbp+psz]; unsigned __int16 **
0x1800fc196  mov     r8d, [rbp+var_2C]; unsigned int
0x1800fc19a  mov     rcx, r14; this
0x1800fc19d  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x1800fc1a1  mov     [rbp+psz], r13
0x1800fc1a5  call    ?_GetCachedString@CBlockListManager@@AEAAJPEBGIPEAPEAG@Z; CBlockListManager::_GetCachedString(ushort const *,uint,ushort * *)
0x1800fc1aa  mov     ebx, eax
0x1800fc1ac  test    eax, eax
0x1800fc1ae  js      short loc_1800FC206
0x1800fc1b0  mov     rax, [rbp+psz]
0x1800fc1b4  test    rax, rax
0x1800fc1b7  jz      short loc_1800FC201
0x1800fc1b9  mov     [r15+r12+8], rax
0x1800fc1be  lea     r9, [rbp+pszStr1]; unsigned __int16 **
0x1800fc1c2  mov     r8d, [rbp+var_28]; unsigned int
0x1800fc1c6  mov     rcx, r14; this
0x1800fc1c9  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x1800fc1cd  mov     [rbp+pszStr1], r13
0x1800fc1d1  call    ?_GetCachedString@CBlockListManager@@AEAAJPEBGIPEAPEAG@Z; CBlockListManager::_GetCachedString(ushort const *,uint,ushort * *)
0x1800fc1d6  mov     ebx, eax
0x1800fc1d8  test    eax, eax
0x1800fc1da  js      short loc_1800FC206
0x1800fc1dc  mov     rax, [rbp+pszStr1]
0x1800fc1e0  test    rax, rax
0x1800fc1e3  jz      short loc_1800FC201
0x1800fc1e5  mov     [r15+r12+10h], rax
0x1800fc1ea  mov     [r14+24Ch], esi
0x1800fc1f1  jmp     short loc_1800FC206
0x1800fc1f3  mov     ebx, 8007006Fh
0x1800fc1f8  jmp     short loc_1800FC206
0x1800fc1fa  mov     ebx, 80070216h
0x1800fc1ff  jmp     short loc_1800FC206
0x1800fc201  mov     ebx, 8007139Fh
0x1800fc206  mov     rcx, [rbp+pv]; pv
0x1800fc20a  call    cs:__imp_CoTaskMemFree
0x1800fc210  mov     rcx, [rbp+var_18]; pv
0x1800fc214  mov     [rbp+pv], r13
0x1800fc218  call    cs:__imp_CoTaskMemFree
0x1800fc21e  mov     rcx, [rbp+var_10]; pv
0x1800fc222  mov     [rbp+var_18], r13
0x1800fc226  call    cs:__imp_CoTaskMemFree
0x1800fc22c  mov     rcx, [rbp+ppwsz]; pv
0x1800fc230  mov     [rbp+var_10], r13
0x1800fc234  call    cs:__imp_CoTaskMemFree
0x1800fc23a  jmp     short loc_1800FC241
0x1800fc23c  mov     ebx, 8007139Fh
0x1800fc241  mov     eax, ebx
0x1800fc243  jmp     short loc_1800FC24A
0x1800fc245  mov     eax, 80070057h
0x1800fc24a  lea     r11, [rsp+80h+var_s0]
0x1800fc252  mov     rbx, [r11+30h]
0x1800fc256  mov     rsi, [r11+40h]
0x1800fc25a  mov     rsp, r11
0x1800fc25d  pop     r15
0x1800fc25f  pop     r14
0x1800fc261  pop     r13
0x1800fc263  pop     r12
0x1800fc265  pop     rbp
0x1800fc266  retn
```
