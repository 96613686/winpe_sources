# CBlockListManager::_HandleBlockListEntryElement(ushort const *,uint,IXmlReader *,BLOCKLIST_LOAD_STATE)

- ea: `0x180105d50`
- end: `0x180106112`
- name: `?_HandleBlockListEntryElement@CBlockListManager@@AEAAJPEBGIPEAUIXmlReader@@W4BLOCKLIST_LOAD_STATE@@@Z`
- size: `962`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, int, __int64 *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180106118`
- `0x1801063f8`

## callees

- `0x180100a24`
- `0x180103d88`
- `0x1801055dc`
- `0x1801057bc`
- `0x1801057f4`
- `0x180105d50`
- `0x180107444`
- `0x18010757c`
- `0x180118020`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180105da2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180105e25`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180105e97`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180105da2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180105e25`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180105e97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180105f49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180105f49`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180105f87`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18010605e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180105f87`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18010605e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106029`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801060d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106029`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801060d9`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180105e66`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180105e66`

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
  unsigned int v19; // edx
  CByteHashTable *v20; // rcx
  int updated; // eax
  unsigned int v22; // eax
  const unsigned __int8 *v23; // rcx
  CBlockListManager *v24; // rcx
  int Ptr; // eax
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
        v7 = CHashTable<GROUP_ENTRY,unsigned short>::ContainsKey(*(_QWORD *)(a1 + 48), ppwsz);
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
                    (const unsigned __int8 *)&pclsid);
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
  if ( (int)CHashTable<GROUP_ENTRY,unsigned short>::ContainsKey(*(_QWORD *)(a1 + 48), ppwsz) >= 0 )
    goto LABEL_43;
  *(_QWORD *)&pclsid.Data1 = v17;
  v22 = _SizeOfString(ppwsz);
  updated = CByteHashTable::_AddUpdateItem(
              *(CByteHashTable **)(a1 + 48),
              (unsigned int)&pclsid,
              v23,
              v22,
              (const unsigned __int8 *)&pclsid);
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
0x180105d50  push    rbp
0x180105d52  push    rbx
0x180105d53  push    rsi
0x180105d54  push    rdi
0x180105d55  push    r14
0x180105d57  push    r15
0x180105d59  lea     rbp, [rsp-27h]
0x180105d5e  sub     rsp, 88h
0x180105d65  mov     rax, cs:__security_cookie
0x180105d6c  xor     rax, rsp
0x180105d6f  mov     [rbp+4Fh+var_38], rax
0x180105d73  mov     r15, r9
0x180105d76  mov     rax, rdx
0x180105d79  mov     rsi, rcx
0x180105d7c  test    rdx, rdx
0x180105d7f  jz      loc_1801060F0
0x180105d85  test    r9, r9
0x180105d88  jz      loc_1801060F0
0x180105d8e  cmp     r8d, 0Eh
0x180105d92  jnz     loc_1801060E7
0x180105d98  lea     rdx, aBlocklistentry; "blocklistentry"
0x180105d9f  mov     rcx, rax; pszStr1
0x180105da2  call    cs:__imp_StrCmpNICW
0x180105da9  nop     dword ptr [rax+rax+00h]
0x180105dae  test    eax, eax
0x180105db0  jnz     loc_1801060E7
0x180105db6  mov     rax, [r15]
0x180105db9  mov     rcx, r15
0x180105dbc  mov     rax, [rax+40h]
0x180105dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105dc5  mov     ebx, eax
0x180105dc7  test    eax, eax
0x180105dc9  jnz     loc_1801060EC
0x180105dcf  mov     [rbp+4Fh+ppwsz], 0
0x180105dd7  xor     r14d, r14d
0x180105dda  mov     rax, [r15]
0x180105ddd  lea     r8, [rbp+4Fh+nChar]
0x180105de1  lea     rdx, [rbp+4Fh+pszStr1]
0x180105de5  mov     [rbp+4Fh+pszStr1], 0
0x180105ded  mov     rcx, r15
0x180105df0  mov     [rbp+4Fh+nChar], 0
0x180105df7  mov     rax, [rax+70h]
0x180105dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105e00  mov     edi, 8007139Fh
0x180105e05  test    eax, eax
0x180105e07  js      loc_180105F05
0x180105e0d  mov     r8d, [rbp+4Fh+nChar]; nChar
0x180105e11  lea     eax, [r8+1]
0x180105e15  cmp     eax, 4
0x180105e18  jnz     short loc_180105E7F
0x180105e1a  mov     rcx, [rbp+4Fh+pszStr1]; pszStr1
0x180105e1e  lea     rdx, aKey; "key"
0x180105e25  call    cs:__imp_StrCmpNICW
0x180105e2c  nop     dword ptr [rax+rax+00h]
0x180105e31  test    eax, eax
0x180105e33  jnz     short loc_180105E7B
0x180105e35  mov     rax, [r15]
0x180105e38  lea     rdx, [rbp+4Fh+psz]
0x180105e3c  xor     r8d, r8d
0x180105e3f  mov     [rbp+4Fh+psz], 0
0x180105e47  mov     rcx, r15
0x180105e4a  mov     rax, [rax+80h]
0x180105e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105e56  test    eax, eax
0x180105e58  js      loc_180105F05
0x180105e5e  mov     rcx, [rbp+4Fh+psz]; psz
0x180105e62  lea     rdx, [rbp+4Fh+ppwsz]; ppwsz
0x180105e66  call    cs:__imp_SHStrDupW
0x180105e6d  nop     dword ptr [rax+rax+00h]
0x180105e72  test    eax, eax
0x180105e74  jns     short loc_180105EF4
0x180105e76  jmp     loc_180105F03
0x180105e7b  mov     r8d, [rbp+4Fh+nChar]; nChar
0x180105e7f  lea     eax, [r8+1]
0x180105e83  cmp     eax, 0Ah
0x180105e86  jnz     loc_180105F14
0x180105e8c  mov     rcx, [rbp+4Fh+pszStr1]; pszStr1
0x180105e90  lea     rdx, aEntrytype; "entrytype"
0x180105e97  call    cs:__imp_StrCmpNICW
0x180105e9e  nop     dword ptr [rax+rax+00h]
0x180105ea3  test    eax, eax
0x180105ea5  jnz     short loc_180105F14
0x180105ea7  mov     rax, [r15]
0x180105eaa  lea     rdx, [rbp+4Fh+pclsid]
0x180105eae  xor     r8d, r8d
0x180105eb1  mov     qword ptr [rbp+4Fh+pclsid.Data1], 0
0x180105eb9  mov     rcx, r15
0x180105ebc  mov     rax, [rax+80h]
0x180105ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105ec8  test    eax, eax
0x180105eca  js      short loc_180105F05
0x180105ecc  mov     rdx, qword ptr [rbp+4Fh+pclsid.Data1]; unsigned __int16 *
0x180105ed0  lea     r8, [rbp+4Fh+psz]; unsigned int *
0x180105ed4  mov     r9d, 2; unsigned int
0x180105eda  mov     dword ptr [rbp+4Fh+psz], 0
0x180105ee1  call    ?_StringToULong@CBlockListManager@@AEAAJPEBGPEAKK@Z; CBlockListManager::_StringToULong(ushort const *,ulong *,ulong)
0x180105ee6  test    eax, eax
0x180105ee8  js      short loc_180105F05
0x180105eea  mov     eax, dword ptr [rbp+4Fh+psz]
0x180105eed  test    eax, eax
0x180105eef  jz      short loc_180105F0D
0x180105ef1  mov     r14d, eax
0x180105ef4  mov     rax, [r15]
0x180105ef7  mov     rcx, r15
0x180105efa  mov     rax, [rax+48h]
0x180105efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105f03  test    eax, eax
0x180105f05  jz      loc_180105DDA
0x180105f0b  jmp     short loc_180105F16
0x180105f0d  mov     eax, 80070216h
0x180105f12  jmp     short loc_180105F16
0x180105f14  mov     eax, edi
0x180105f16  xor     ebx, ebx
0x180105f18  cmp     eax, 1
0x180105f1b  cmovnz  ebx, eax
0x180105f1e  test    ebx, ebx
0x180105f20  js      loc_1801060D5
0x180105f26  cmp     [rbp+4Fh+ppwsz], 0
0x180105f2b  jz      loc_1801060D3
0x180105f31  test    r14d, r14d
0x180105f34  jz      loc_1801060D3
0x180105f3a  cmp     [rbp+4Fh+arg_20], 1
0x180105f3e  jnz     loc_18010603A
0x180105f44  mov     ecx, 10h; cb
0x180105f49  call    cs:__imp_CoTaskMemAlloc
0x180105f50  nop     dword ptr [rax+rax+00h]
0x180105f55  mov     r15, rax
0x180105f58  test    rax, rax
0x180105f5b  jnz     short loc_180105F67
0x180105f5d  mov     ebx, 8007000Eh
0x180105f62  jmp     loc_1801060D5
0x180105f67  xorps   xmm0, xmm0
0x180105f6a  movups  xmmword ptr [rax], xmm0
0x180105f6d  cmp     r14d, 2
0x180105f71  jnz     short loc_180105FD8
0x180105f73  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180105f7a  mov     rcx, [rbp+4Fh+ppwsz]; lpsz
0x180105f7e  lea     rdx, [rbp+4Fh+pszStr1]; pclsid
0x180105f82  movdqu  xmmword ptr [rbp+4Fh+pszStr1], xmm0
0x180105f87  call    cs:__imp_CLSIDFromString
0x180105f8e  nop     dword ptr [rax+rax+00h]
0x180105f93  test    eax, eax
0x180105f95  jns     short loc_180105FAA
0x180105f97  mov     rdx, [rbp+4Fh+ppwsz]; unsigned __int16 *
0x180105f9b  lea     r8, [rbp+4Fh+pszStr1]; struct _GUID *
0x180105f9f  call    ?_PartialCLSIDFromString@CBlockListManager@@AEAAJPEBGPEAU_GUID@@@Z; CBlockListManager::_PartialCLSIDFromString(ushort const *,_GUID *)
0x180105fa4  mov     ebx, eax
0x180105fa6  test    eax, eax
0x180105fa8  js      short loc_180106026
0x180105faa  mov     rcx, [rsi+38h]
0x180105fae  lea     rdx, [rbp+4Fh+pszStr1]
0x180105fb2  call    ?ContainsKey@?$CHashTableEx@UBLOCKLIST_ENTRY@@U_GUID@@VCCLSIDTrait@@@@QEBAJPEBU_GUID@@@Z; CHashTableEx<BLOCKLIST_ENTRY,_GUID,CCLSIDTrait>::ContainsKey(_GUID const *)
0x180105fb7  test    eax, eax
0x180105fb9  jns     short loc_180106018
0x180105fbb  mov     rcx, [rsi+38h]
0x180105fbf  lea     rax, [rbp+4Fh+pclsid]
0x180105fc3  mov     [rsp+0B0h+var_90], rax
0x180105fc8  lea     r8, [rbp+4Fh+pszStr1]
0x180105fcc  mov     qword ptr [rbp+4Fh+pclsid.Data1], r15
0x180105fd0  mov     r9d, 10h
0x180105fd6  jmp     short loc_18010600F
0x180105fd8  cmp     r14d, 1
0x180105fdc  jnz     short loc_180106024
0x180105fde  mov     rdx, [rbp+4Fh+ppwsz]
0x180105fe2  mov     rcx, [rsi+30h]
0x180105fe6  call    ?ContainsKey@?$CHashTable@UGROUP_ENTRY@@G@@QEBAJPEBG@Z; CHashTable<GROUP_ENTRY,ushort>::ContainsKey(ushort const *)
0x180105feb  test    eax, eax
0x180105fed  jns     short loc_180106018
0x180105fef  mov     rcx, [rbp+4Fh+ppwsz]; unsigned __int16 *
0x180105ff3  mov     qword ptr [rbp+4Fh+pclsid.Data1], r15
0x180105ff7  call    ?_SizeOfString@@YAIPEBG@Z; _SizeOfString(ushort const *)
0x180105ffc  lea     rdx, [rbp+4Fh+pclsid]; int
0x180106000  mov     r8, rcx; unsigned __int8 *
0x180106003  mov     rcx, [rsi+30h]; this
0x180106007  mov     r9d, eax; unsigned int
0x18010600a  mov     [rsp+0B0h+var_90], rdx; unsigned __int8 *
0x18010600f  call    ?_AddUpdateItem@CByteHashTable@@AEAAJHPEBEI0IPEAEI@Z; CByteHashTable::_AddUpdateItem(int,uchar const *,uint,uchar const *,uint,uchar *,uint)
0x180106014  mov     ebx, eax
0x180106016  jmp     short loc_18010601A
0x180106018  mov     ebx, edi
0x18010601a  test    ebx, ebx
0x18010601c  jns     loc_1801060D5
0x180106022  jmp     short loc_180106026
0x180106024  mov     ebx, edi
0x180106026  mov     rcx, r15; pv
0x180106029  call    cs:__imp_CoTaskMemFree
0x180106030  nop     dword ptr [rax+rax+00h]
0x180106035  jmp     loc_1801060D5
0x18010603a  cmp     [rbp+4Fh+arg_20], 2
0x18010603e  jnz     loc_1801060D3
0x180106044  cmp     r14d, 2
0x180106048  jnz     short loc_1801060A7
0x18010604a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180106051  mov     rcx, [rbp+4Fh+ppwsz]; lpsz
0x180106055  lea     rdx, [rbp+4Fh+pclsid]; pclsid
0x180106059  movdqu  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x18010605e  call    cs:__imp_CLSIDFromString
0x180106065  nop     dword ptr [rax+rax+00h]
0x18010606a  test    eax, eax
0x18010606c  jns     short loc_180106081
0x18010606e  mov     rdx, [rbp+4Fh+ppwsz]; unsigned __int16 *
0x180106072  lea     r8, [rbp+4Fh+pclsid]; struct _GUID *
0x180106076  call    ?_PartialCLSIDFromString@CBlockListManager@@AEAAJPEBGPEAU_GUID@@@Z; CBlockListManager::_PartialCLSIDFromString(ushort const *,_GUID *)
0x18010607b  mov     ebx, eax
0x18010607d  test    eax, eax
0x18010607f  js      short loc_1801060D5
0x180106081  mov     rcx, [rsi+38h]
0x180106085  lea     rdx, [rbp+4Fh+pclsid]
0x180106089  call    ?ContainsKey@?$CHashTableEx@UBLOCKLIST_ENTRY@@U_GUID@@VCCLSIDTrait@@@@QEBAJPEBU_GUID@@@Z; CHashTableEx<BLOCKLIST_ENTRY,_GUID,CCLSIDTrait>::ContainsKey(_GUID const *)
0x18010608e  test    eax, eax
0x180106090  js      short loc_1801060D3
0x180106092  mov     rcx, [rsi+38h]
0x180106096  lea     r8, [rsi+10h]
0x18010609a  lea     rdx, [rbp+4Fh+pclsid]
0x18010609e  call    ?GetPtr@?$CHashTableEx@UBLOCKLIST_ENTRY@@U_GUID@@VCCLSIDTrait@@@@QEBAJPEBU_GUID@@PEAPEAUBLOCKLIST_ENTRY@@@Z; CHashTableEx<BLOCKLIST_ENTRY,_GUID,CCLSIDTrait>::GetPtr(_GUID const *,BLOCKLIST_ENTRY * *)
0x1801060a3  mov     ebx, eax
0x1801060a5  jmp     short loc_1801060D5
0x1801060a7  cmp     r14d, 1
0x1801060ab  jnz     short loc_1801060D3
0x1801060ad  mov     rdx, [rbp+4Fh+ppwsz]
0x1801060b1  mov     rcx, [rsi+30h]
0x1801060b5  call    ?ContainsKey@?$CHashTable@UGROUP_ENTRY@@G@@QEBAJPEBG@Z; CHashTable<GROUP_ENTRY,ushort>::ContainsKey(ushort const *)
0x1801060ba  mov     ebx, eax
0x1801060bc  test    eax, eax
0x1801060be  js      short loc_1801060D5
0x1801060c0  mov     rdx, [rbp+4Fh+ppwsz]
0x1801060c4  lea     r8, [rsi+10h]
0x1801060c8  mov     rcx, [rsi+30h]
0x1801060cc  call    ?GetPtr@?$CHashTable@UBLOCKLIST_ENTRY@@G@@QEBAJPEBGPEAPEAUBLOCKLIST_ENTRY@@@Z; CHashTable<BLOCKLIST_ENTRY,ushort>::GetPtr(ushort const *,BLOCKLIST_ENTRY * *)
0x1801060d1  jmp     short loc_1801060A3
0x1801060d3  mov     ebx, edi
0x1801060d5  mov     rcx, [rbp+4Fh+ppwsz]; pv
0x1801060d9  call    cs:__imp_CoTaskMemFree
0x1801060e0  nop     dword ptr [rax+rax+00h]
0x1801060e5  jmp     short loc_1801060EC
0x1801060e7  mov     ebx, 8007139Fh
0x1801060ec  mov     eax, ebx
0x1801060ee  jmp     short loc_1801060F5
0x1801060f0  mov     eax, 80070057h
0x1801060f5  mov     rcx, [rbp+4Fh+var_38]
0x1801060f9  xor     rcx, rsp; StackCookie
0x1801060fc  call    __security_check_cookie
0x180106101  add     rsp, 88h
0x180106108  pop     r15
0x18010610a  pop     r14
0x18010610c  pop     rdi
0x18010610d  pop     rsi
0x18010610e  pop     rbx
0x18010610f  pop     rbp
0x180106110  retn
```
