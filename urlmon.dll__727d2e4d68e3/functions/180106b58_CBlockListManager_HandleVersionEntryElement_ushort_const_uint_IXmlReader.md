# CBlockListManager::_HandleVersionEntryElement(ushort const *,uint,IXmlReader *)

- ea: `0x180106b58`
- end: `0x180106f90`
- name: `?_HandleVersionEntryElement@CBlockListManager@@AEAAJPEBGIPEAUIXmlReader@@@Z`
- size: `1080`
- prototype: `__int64 __fastcall(CBlockListManager *__hidden this, LPCWSTR pszStr1, unsigned int, struct IXmlReader *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180106118`

## callees

- `0x180100a24`
- `0x180103d88`
- `0x18010581c`
- `0x180106b58`
- `0x180118198`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106bb7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106c3f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106c96`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106ced`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106d3d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106bb7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106c3f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106c96`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106ced`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180106d3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106f1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106f2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106f42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106f56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106f1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106f2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106f42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106f56`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180106d76`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180106d76`

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
        if ( (int)CHashTable<GROUP_ENTRY,unsigned short>::ContainsKey(*((_QWORD *)this + 4), ppwsz) < 0 )
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
          Value = CBlockListManager::_GetCachedString(
                    (CByteHashTable **)this,
                    (const unsigned __int16 *)pv,
                    v27,
                    &nChar);
          if ( Value >= 0 )
          {
            if ( nChar )
            {
              *(_QWORD *)(v21 + v20) = nChar;
              psz = 0;
              Value = CBlockListManager::_GetCachedString((CByteHashTable **)this, v31, v28, (unsigned __int16 **)&psz);
              if ( Value < 0 )
                goto LABEL_58;
              if ( psz )
              {
                *(_QWORD *)(v21 + v20 + 8) = psz;
                pszStr1a = 0;
                Value = CBlockListManager::_GetCachedString(
                          (CByteHashTable **)this,
                          v32,
                          v29,
                          (unsigned __int16 **)&pszStr1a);
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
0x180106b58  mov     [rsp-28h+arg_0], rbx
0x180106b5d  mov     [rsp-28h+arg_10], rsi
0x180106b62  push    rbp
0x180106b63  push    r12
0x180106b65  push    r13
0x180106b67  push    r14
0x180106b69  push    r15
0x180106b6b  mov     rbp, rsp
0x180106b6e  sub     rsp, 80h
0x180106b75  xor     r13d, r13d
0x180106b78  mov     rsi, r9
0x180106b7b  mov     rax, rdx
0x180106b7e  mov     r14, rcx
0x180106b81  test    rdx, rdx
0x180106b84  jz      loc_180106F6D
0x180106b8a  test    r9, r9
0x180106b8d  jz      loc_180106F6D
0x180106b93  cmp     [rcx+10h], r13
0x180106b97  jnz     short loc_180106BA3
0x180106b99  mov     eax, 8007139Fh
0x180106b9e  jmp     loc_180106F72
0x180106ba3  cmp     r8d, 0Ch
0x180106ba7  jnz     loc_180106F64
0x180106bad  lea     rdx, aVersionentry; "versionentry"
0x180106bb4  mov     rcx, rax; pszStr1
0x180106bb7  call    cs:__imp_StrCmpNICW
0x180106bbe  nop     dword ptr [rax+rax+00h]
0x180106bc3  test    eax, eax
0x180106bc5  jnz     loc_180106F64
0x180106bcb  mov     rax, [rsi]
0x180106bce  mov     rcx, rsi
0x180106bd1  mov     rax, [rax+40h]
0x180106bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106bda  mov     ebx, eax
0x180106bdc  test    eax, eax
0x180106bde  jnz     loc_180106F69
0x180106be4  mov     [rbp+pv], r13
0x180106be8  mov     [rbp+var_30], r13d
0x180106bec  mov     [rbp+var_18], r13
0x180106bf0  mov     [rbp+var_2C], r13d
0x180106bf4  mov     [rbp+var_10], r13
0x180106bf8  mov     [rbp+var_28], r13d
0x180106bfc  mov     [rbp+ppwsz], r13
0x180106c00  mov     rax, [rsi]
0x180106c03  lea     r8, [rbp+nChar]
0x180106c07  lea     rdx, [rbp+pszStr1]
0x180106c0b  mov     [rbp+pszStr1], r13
0x180106c0f  mov     rcx, rsi
0x180106c12  mov     dword ptr [rbp+nChar], r13d
0x180106c16  mov     rax, [rax+70h]
0x180106c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106c1f  test    eax, eax
0x180106c21  js      loc_180106D97
0x180106c27  mov     r8d, dword ptr [rbp+nChar]; nChar
0x180106c2b  lea     eax, [r8+1]
0x180106c2f  cmp     eax, 0Fh
0x180106c32  jnz     short loc_180106C82
0x180106c34  mov     rcx, [rbp+pszStr1]; pszStr1
0x180106c38  lea     rdx, aProductversion_0; "productversion"
0x180106c3f  call    cs:__imp_StrCmpNICW
0x180106c46  nop     dword ptr [rax+rax+00h]
0x180106c4b  test    eax, eax
0x180106c4d  jnz     short loc_180106C7E
0x180106c4f  mov     rax, [rsi]
0x180106c52  lea     r8, [rbp+var_30]
0x180106c56  lea     rdx, [rbp+psz]
0x180106c5a  mov     [rbp+psz], r13
0x180106c5e  mov     rcx, rsi
0x180106c61  mov     rax, [rax+80h]
0x180106c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106c6d  test    eax, eax
0x180106c6f  js      loc_180106D97
0x180106c75  lea     rdx, [rbp+pv]
0x180106c79  jmp     loc_180106D72
0x180106c7e  mov     r8d, dword ptr [rbp+nChar]; nChar
0x180106c82  lea     eax, [r8+1]
0x180106c86  cmp     eax, 0Ch
0x180106c89  jnz     short loc_180106CD9
0x180106c8b  mov     rcx, [rbp+pszStr1]; pszStr1
0x180106c8f  lea     rdx, aFileversion_1; "fileversion"
0x180106c96  call    cs:__imp_StrCmpNICW
0x180106c9d  nop     dword ptr [rax+rax+00h]
0x180106ca2  test    eax, eax
0x180106ca4  jnz     short loc_180106CD5
0x180106ca6  mov     rax, [rsi]
0x180106ca9  lea     r8, [rbp+var_2C]
0x180106cad  lea     rdx, [rbp+psz]
0x180106cb1  mov     [rbp+psz], r13
0x180106cb5  mov     rcx, rsi
0x180106cb8  mov     rax, [rax+80h]
0x180106cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106cc4  test    eax, eax
0x180106cc6  js      loc_180106D97
0x180106ccc  lea     rdx, [rbp+var_18]
0x180106cd0  jmp     loc_180106D72
0x180106cd5  mov     r8d, dword ptr [rbp+nChar]; nChar
0x180106cd9  lea     eax, [r8+1]
0x180106cdd  cmp     eax, 9
0x180106ce0  jnz     short loc_180106D29
0x180106ce2  mov     rcx, [rbp+pszStr1]; pszStr1
0x180106ce6  lea     rdx, aFilename_3; "filename"
0x180106ced  call    cs:__imp_StrCmpNICW
0x180106cf4  nop     dword ptr [rax+rax+00h]
0x180106cf9  test    eax, eax
0x180106cfb  jnz     short loc_180106D25
0x180106cfd  mov     rax, [rsi]
0x180106d00  lea     r8, [rbp+var_28]
0x180106d04  lea     rdx, [rbp+psz]
0x180106d08  mov     [rbp+psz], r13
0x180106d0c  mov     rcx, rsi
0x180106d0f  mov     rax, [rax+80h]
0x180106d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106d1b  test    eax, eax
0x180106d1d  js      short loc_180106D97
0x180106d1f  lea     rdx, [rbp+var_10]
0x180106d23  jmp     short loc_180106D72
0x180106d25  mov     r8d, dword ptr [rbp+nChar]; nChar
0x180106d29  lea     eax, [r8+1]
0x180106d2d  cmp     eax, 0Ah
0x180106d30  jnz     short loc_180106D9F
0x180106d32  mov     rcx, [rbp+pszStr1]; pszStr1
0x180106d36  lea     rdx, aGroupname; "groupname"
0x180106d3d  call    cs:__imp_StrCmpNICW
0x180106d44  nop     dword ptr [rax+rax+00h]
0x180106d49  test    eax, eax
0x180106d4b  jnz     short loc_180106D9F
0x180106d4d  mov     rax, [rsi]
0x180106d50  lea     rdx, [rbp+psz]
0x180106d54  xor     r8d, r8d
0x180106d57  mov     [rbp+psz], r13
0x180106d5b  mov     rcx, rsi
0x180106d5e  mov     rax, [rax+80h]
0x180106d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106d6a  test    eax, eax
0x180106d6c  js      short loc_180106D97
0x180106d6e  lea     rdx, [rbp+ppwsz]; ppwsz
0x180106d72  mov     rcx, [rbp+psz]; psz
0x180106d76  call    cs:__imp_SHStrDupW
0x180106d7d  nop     dword ptr [rax+rax+00h]
0x180106d82  test    eax, eax
0x180106d84  js      short loc_180106D97
0x180106d86  mov     rax, [rsi]
0x180106d89  mov     rcx, rsi
0x180106d8c  mov     rax, [rax+48h]
0x180106d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106d95  test    eax, eax
0x180106d97  jz      loc_180106C00
0x180106d9d  jmp     short loc_180106DA4
0x180106d9f  mov     eax, 8007139Fh
0x180106da4  cmp     eax, 1
0x180106da7  mov     ebx, r13d
0x180106daa  cmovnz  ebx, eax
0x180106dad  test    ebx, ebx
0x180106daf  js      loc_180106F16
0x180106db5  cmp     [rbp+pv], r13
0x180106db9  jz      loc_180106F11
0x180106dbf  cmp     [rbp+var_18], r13
0x180106dc3  jz      loc_180106F11
0x180106dc9  cmp     [rbp+var_10], r13
0x180106dcd  jz      loc_180106F11
0x180106dd3  mov     rdx, [rbp+ppwsz]
0x180106dd7  test    rdx, rdx
0x180106dda  jz      loc_180106F11
0x180106de0  cmp     [rbp+var_30], r13d
0x180106de4  jz      loc_180106F11
0x180106dea  cmp     [rbp+var_2C], r13d
0x180106dee  jz      loc_180106F11
0x180106df4  cmp     [rbp+var_28], r13d
0x180106df8  jz      loc_180106F11
0x180106dfe  mov     ebx, [r14+24Ch]
0x180106e05  lea     esi, [rbx+1]
0x180106e08  cmp     esi, ebx
0x180106e0a  jb      loc_180106F0A
0x180106e10  mov     r12, [r14+10h]
0x180106e14  cmp     esi, [r12+8]
0x180106e19  ja      loc_180106F03
0x180106e1f  mov     rcx, [r14+20h]
0x180106e23  mov     r12, [r12]
0x180106e27  call    ?ContainsKey@?$CHashTable@UGROUP_ENTRY@@G@@QEBAJPEBG@Z; CHashTable<GROUP_ENTRY,ushort>::ContainsKey(ushort const *)
0x180106e2c  test    eax, eax
0x180106e2e  js      loc_180106F11
0x180106e34  mov     rcx, [rbp+ppwsz]; unsigned __int16 *
0x180106e38  mov     r15d, ebx
0x180106e3b  shl     r15, 5
0x180106e3f  call    ?_SizeOfString@@YAIPEBG@Z; _SizeOfString(ushort const *)
0x180106e44  mov     rdx, [rbp+ppwsz]; unsigned __int8 *
0x180106e48  lea     rcx, [r12+18h]
0x180106e4d  add     rcx, r15
0x180106e50  mov     [rsp+80h+var_50], 8; int
0x180106e58  mov     [rsp+80h+var_58], rcx; unsigned __int8 *
0x180106e5d  mov     r8d, eax; unsigned int
0x180106e60  mov     rcx, [r14+20h]; this
0x180106e64  call    ?_GetValue@CByteHashTable@@AEBAJPEBEIPEAPEAEPEAHPEAEH@Z; CByteHashTable::_GetValue(uchar const *,uint,uchar * *,int *,uchar *,int)
0x180106e69  mov     ebx, eax
0x180106e6b  test    eax, eax
0x180106e6d  js      loc_180106F16
0x180106e73  mov     r8d, [rbp+var_30]; unsigned int
0x180106e77  lea     r9, [rbp+nChar]; unsigned __int16 **
0x180106e7b  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180106e7f  mov     rcx, r14; this
0x180106e82  mov     [rbp+nChar], r13
0x180106e86  call    ?_GetCachedString@CBlockListManager@@AEAAJPEBGIPEAPEAG@Z; CBlockListManager::_GetCachedString(ushort const *,uint,ushort * *)
0x180106e8b  mov     ebx, eax
0x180106e8d  test    eax, eax
0x180106e8f  js      loc_180106F16
0x180106e95  mov     rax, [rbp+nChar]
0x180106e99  test    rax, rax
0x180106e9c  jz      short loc_180106F11
0x180106e9e  mov     [r15+r12], rax
0x180106ea2  lea     r9, [rbp+psz]; unsigned __int16 **
0x180106ea6  mov     r8d, [rbp+var_2C]; unsigned int
0x180106eaa  mov     rcx, r14; this
0x180106ead  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x180106eb1  mov     [rbp+psz], r13
0x180106eb5  call    ?_GetCachedString@CBlockListManager@@AEAAJPEBGIPEAPEAG@Z; CBlockListManager::_GetCachedString(ushort const *,uint,ushort * *)
0x180106eba  mov     ebx, eax
0x180106ebc  test    eax, eax
0x180106ebe  js      short loc_180106F16
0x180106ec0  mov     rax, [rbp+psz]
0x180106ec4  test    rax, rax
0x180106ec7  jz      short loc_180106F11
0x180106ec9  mov     [r15+r12+8], rax
0x180106ece  lea     r9, [rbp+pszStr1]; unsigned __int16 **
0x180106ed2  mov     r8d, [rbp+var_28]; unsigned int
0x180106ed6  mov     rcx, r14; this
0x180106ed9  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x180106edd  mov     [rbp+pszStr1], r13
0x180106ee1  call    ?_GetCachedString@CBlockListManager@@AEAAJPEBGIPEAPEAG@Z; CBlockListManager::_GetCachedString(ushort const *,uint,ushort * *)
0x180106ee6  mov     ebx, eax
0x180106ee8  test    eax, eax
0x180106eea  js      short loc_180106F16
0x180106eec  mov     rax, [rbp+pszStr1]
0x180106ef0  test    rax, rax
0x180106ef3  jz      short loc_180106F11
0x180106ef5  mov     [r15+r12+10h], rax
0x180106efa  mov     [r14+24Ch], esi
0x180106f01  jmp     short loc_180106F16
0x180106f03  mov     ebx, 8007006Fh
0x180106f08  jmp     short loc_180106F16
0x180106f0a  mov     ebx, 80070216h
0x180106f0f  jmp     short loc_180106F16
0x180106f11  mov     ebx, 8007139Fh
0x180106f16  mov     rcx, [rbp+pv]; pv
0x180106f1a  call    cs:__imp_CoTaskMemFree
0x180106f21  nop     dword ptr [rax+rax+00h]
0x180106f26  mov     rcx, [rbp+var_18]; pv
0x180106f2a  mov     [rbp+pv], r13
0x180106f2e  call    cs:__imp_CoTaskMemFree
0x180106f35  nop     dword ptr [rax+rax+00h]
0x180106f3a  mov     rcx, [rbp+var_10]; pv
0x180106f3e  mov     [rbp+var_18], r13
0x180106f42  call    cs:__imp_CoTaskMemFree
0x180106f49  nop     dword ptr [rax+rax+00h]
0x180106f4e  mov     rcx, [rbp+ppwsz]; pv
0x180106f52  mov     [rbp+var_10], r13
0x180106f56  call    cs:__imp_CoTaskMemFree
0x180106f5d  nop     dword ptr [rax+rax+00h]
0x180106f62  jmp     short loc_180106F69
0x180106f64  mov     ebx, 8007139Fh
0x180106f69  mov     eax, ebx
0x180106f6b  jmp     short loc_180106F72
0x180106f6d  mov     eax, 80070057h
0x180106f72  lea     r11, [rsp+80h+var_s0]
0x180106f7a  mov     rbx, [r11+30h]
0x180106f7e  mov     rsi, [r11+40h]
0x180106f82  mov     rsp, r11
0x180106f85  pop     r15
0x180106f87  pop     r14
0x180106f89  pop     r13
0x180106f8b  pop     r12
0x180106f8d  pop     rbp
0x180106f8e  retn
```
