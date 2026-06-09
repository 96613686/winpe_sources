# CSLAggregationUtilsT<CEmptyType>::GetSLLicenseStatusObjects(_GUID const *,SLicenseStatusObject * *,ulong *)

- ea: `0x180021a8c`
- end: `0x180021e63`
- name: `?GetSLLicenseStatusObjects@?$CSLAggregationUtilsT@VCEmptyType@@@@SAJPEBU_GUID@@PEAPEAUSLicenseStatusObject@@PEAK@Z`
- size: `983`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800236b4`

## callees

- `0x180003520`
- `0x180004288`
- `0x18002177c`
- `0x180021a8c`
- `0x180021e6c`
- `0x180036d64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021b50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021dcf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021b50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021dcf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021de3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021de3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021b64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021b64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021bc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021c32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021df8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021e11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021e2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021bc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021c32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021df8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021e11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021e2a`
- `SLC!SLGetProductSkuInformation` at `0x180021c6c`
- `SLC!SLGetProductSkuInformation` at `0x180021c6c`
- `SLC!SLOpen` at `0x180021ade`
- `SLC!SLOpen` at `0x180021ade`
- `SLC!SLClose` at `0x180021e43`
- `SLC!SLClose` at `0x180021e43`
- `SLC!SLGetLicensingStatusInformation` at `0x180021b1a`
- `SLC!SLGetLicensingStatusInformation` at `0x180021b1a`
- `SLC!SLGetSLIDList` at `0x180021bf8`
- `SLC!SLGetSLIDList` at `0x180021bf8`

## pseudocode

```c
__int64 __fastcall CSLAggregationUtilsT<CEmptyType>::GetSLLicenseStatusObjects(__int64 a1, char **a2, UINT *a3)
{
  char *v3; // rbx
  UINT *v4; // rsi
  char **v5; // r15
  HRESULT WindowsSkuCategory; // eax
  HRESULT v7; // edi
  __int64 v8; // rcx
  SIZE_T v9; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v11; // rdx
  UINT v12; // eax
  __int64 v13; // r13
  char *v14; // rsi
  BOOL v15; // r15d
  int v16; // r12d
  unsigned int v17; // eax
  char *v18; // r9
  int v19; // ecx
  char *v20; // r14
  __int128 v21; // xmm1
  char *v22; // r8
  __int64 v23; // xmm2_8
  __int64 v24; // rdx
  char *v25; // rax
  int v26; // eax
  HANDLE v27; // rax
  HLOCAL v29; // [rsp+30h] [rbp-48h] BYREF
  HSLC phSLC; // [rsp+38h] [rbp-40h] BYREF
  int v31; // [rsp+40h] [rbp-38h]
  int v32; // [rsp+44h] [rbp-34h]
  UINT v33; // [rsp+48h] [rbp-30h]
  HLOCAL hMem; // [rsp+50h] [rbp-28h] BYREF
  HLOCAL ppLicensingStatus; // [rsp+58h] [rbp-20h] BYREF
  UINT pcbValue; // [rsp+60h] [rbp-18h] BYREF
  char *v37; // [rsp+68h] [rbp-10h]
  UINT pnStatusCount; // [rsp+C0h] [rbp+48h] BYREF
  int v39; // [rsp+C4h] [rbp+4Ch]
  char **v40; // [rsp+C8h] [rbp+50h]
  UINT *v41; // [rsp+D0h] [rbp+58h]
  UINT pnReturnIds; // [rsp+D8h] [rbp+60h] BYREF

  v41 = a3;
  v40 = a2;
  v39 = HIDWORD(a1);
  phSLC = 0;
  v3 = 0;
  ppLicensingStatus = 0;
  v4 = a3;
  pnStatusCount = 0;
  v5 = a2;
  v29 = 0;
  pcbValue = 0;
  hMem = 0;
  pnReturnIds = 0;
  v32 = 0;
  WindowsSkuCategory = SLOpen(&phSLC);
  v7 = WindowsSkuCategory;
  if ( WindowsSkuCategory < 0
    || (WindowsSkuCategory = SLGetLicensingStatusInformation(
                               phSLC,
                               &WINDOWS_SLID,
                               0,
                               0,
                               &pnStatusCount,
                               (SL_LICENSING_STATUS **)&ppLicensingStatus),
        v7 = WindowsSkuCategory,
        WindowsSkuCategory < 0) )
  {
LABEL_2:
    v8 = (unsigned int)WindowsSkuCategory;
LABEL_37:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_38;
  }
  if ( !ppLicensingStatus || !pnStatusCount )
  {
    v7 = -2147418113;
LABEL_36:
    v8 = (unsigned int)v7;
    goto LABEL_37;
  }
  v9 = 56LL * pnStatusCount;
  ProcessHeap = GetProcessHeap();
  v3 = (char *)HeapAlloc(ProcessHeap, 0, v9);
  if ( !v3 )
  {
    v7 = -2147024882;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
    v3 = 0;
    goto LABEL_38;
  }
  v11 = pnStatusCount;
  v12 = 0;
  v33 = 0;
  if ( pnStatusCount )
  {
    v37 = v3;
    while ( 1 )
    {
      v13 = v12;
      v14 = (char *)ppLicensingStatus + 40 * v12;
      if ( hMem )
      {
        LocalFree(hMem);
        hMem = 0;
      }
      v7 = SLGetSLIDList(phSLC, SL_ID_PRODUCT_SKU, (const SLID *)v14, SL_ID_PKEY, &pnReturnIds, (SLID **)&hMem);
      if ( ((v7 + 0x80000000) & 0x80000000) == 0 && v7 != -1073418222 )
        goto LABEL_36;
      v15 = 0;
      if ( v7 >= 0 )
        v15 = pnReturnIds != 0;
      if ( v29 )
      {
        LocalFree(v29);
        v29 = 0;
      }
      v31 = 0;
      v16 = 0;
      WindowsSkuCategory = SLGetProductSkuInformation(
                             phSLC,
                             (const SLID *)v14,
                             L"UXDifferentiator",
                             0,
                             &pcbValue,
                             (PBYTE *)&v29);
      v7 = WindowsSkuCategory;
      if ( WindowsSkuCategory >= 0 )
      {
        WindowsSkuCategory = CSLAggregationUtilsT<CEmptyType>::ConvertChannelStringToType((wchar_t *)v29);
        v7 = WindowsSkuCategory;
        if ( WindowsSkuCategory < 0 )
          goto LABEL_2;
        v16 = v31;
      }
      else if ( WindowsSkuCategory != -1073418222 )
      {
        goto LABEL_2;
      }
      WindowsSkuCategory = CSLAggregationUtilsT<CEmptyType>::GetWindowsSkuCategory(phSLC);
      v7 = WindowsSkuCategory;
      if ( WindowsSkuCategory < 0 )
        goto LABEL_2;
      if ( *((_DWORD *)v14 + 7) == 1074065421 )
      {
        v17 = *((_DWORD *)v14 + 6);
        if ( v17 + 30 < v17 )
        {
          v7 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          *((_DWORD *)v14 + 6) = v17 + 30;
          v7 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
        if ( v7 < 0 )
          goto LABEL_36;
      }
      v18 = v37;
      v19 = v32;
      v20 = v3;
      v21 = *((_OWORD *)v14 + 1);
      v22 = v37;
      v23 = *((_QWORD *)v14 + 4);
      v24 = 56 * v13;
      v25 = v37;
      *(_OWORD *)&v37[56 * v13] = *(_OWORD *)v14;
      *(_OWORD *)&v25[v24 + 16] = v21;
      *(_QWORD *)&v25[v24 + 32] = v23;
      *(_DWORD *)&v18[v24 + 40] = v16;
      *(_DWORD *)&v18[v24 + 44] = v19;
      *(_DWORD *)&v18[v24 + 48] = v15;
      v11 = pnStatusCount;
      v12 = v33 + 1;
      v33 = v12;
      if ( v12 >= pnStatusCount )
      {
        v4 = v41;
        v5 = v40;
        goto LABEL_32;
      }
    }
  }
  v20 = v3;
  v22 = v3;
LABEL_32:
  v26 = CSLAggregationUtilsT<CEmptyType>::SortLicenseStatusObjects(v22, v11, v22);
  v7 = v26;
  if ( v26 >= 0 )
  {
    v3 = 0;
    *v4 = pnStatusCount;
    *v5 = v20;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v26);
    v3 = v20;
  }
LABEL_38:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v3 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v3);
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v29 )
  {
    LocalFree(v29);
    v29 = 0;
  }
  if ( ppLicensingStatus )
  {
    LocalFree(ppLicensingStatus);
    ppLicensingStatus = 0;
  }
  if ( phSLC )
    SLClose(phSLC);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180021a8c  mov     [rsp-40h+arg_10], r8
0x180021a91  mov     [rsp-40h+arg_8], rdx
0x180021a96  mov     qword ptr [rsp-40h+arg_0], rcx
0x180021a9b  push    rbp
0x180021a9c  push    rbx
0x180021a9d  push    rsi
0x180021a9e  push    rdi
0x180021a9f  push    r12
0x180021aa1  push    r13
0x180021aa3  push    r14
0x180021aa5  push    r15
0x180021aa7  mov     rbp, rsp
0x180021aaa  sub     rsp, 78h
0x180021aae  xor     r14d, r14d
0x180021ab1  lea     rcx, [rbp+phSLC]; phSLC
0x180021ab5  mov     [rbp+phSLC], r14
0x180021ab9  mov     ebx, r14d
0x180021abc  mov     [rbp+var_20], r14
0x180021ac0  mov     rsi, r8
0x180021ac3  mov     [rbp+arg_0], r14d
0x180021ac7  mov     r15, rdx
0x180021aca  mov     [rbp+var_48], r14
0x180021ace  mov     [rbp+pcbValue], r14d
0x180021ad2  mov     [rbp+hMem], r14
0x180021ad6  mov     [rbp+pnReturnIds], r14d
0x180021ada  mov     [rbp+var_34], r14d
0x180021ade  call    cs:__imp_SLOpen
0x180021ae5  nop     dword ptr [rax+rax+00h]
0x180021aea  mov     edi, eax
0x180021aec  test    eax, eax
0x180021aee  jns     short loc_180021AF7
0x180021af0  mov     ecx, eax
0x180021af2  jmp     loc_180021DBE
0x180021af7  mov     rcx, [rbp+phSLC]; hSLC
0x180021afb  lea     rax, [rbp+var_20]
0x180021aff  mov     [rsp+78h+ppLicensingStatus], rax; ppLicensingStatus
0x180021b04  lea     rdx, WINDOWS_SLID; pAppID
0x180021b0b  lea     rax, [rbp+arg_0]
0x180021b0f  xor     r9d, r9d; pwszRightName
0x180021b12  xor     r8d, r8d; pProductSkuId
0x180021b15  mov     [rsp+78h+pnStatusCount], rax; pnStatusCount
0x180021b1a  call    cs:__imp_SLGetLicensingStatusInformation
0x180021b21  nop     dword ptr [rax+rax+00h]
0x180021b26  mov     edi, eax
0x180021b28  test    eax, eax
0x180021b2a  js      short loc_180021AF0
0x180021b2c  mov     rax, [rbp+var_20]
0x180021b30  test    rax, rax
0x180021b33  jz      loc_180021DB7
0x180021b39  mov     r12d, 1
0x180021b3f  cmp     [rbp+arg_0], r12d
0x180021b43  jb      loc_180021DB7
0x180021b49  mov     eax, [rbp+arg_0]
0x180021b4c  imul    rbx, rax, 38h ; '8'
0x180021b50  call    cs:__imp_GetProcessHeap
0x180021b57  nop     dword ptr [rax+rax+00h]
0x180021b5c  mov     r8, rbx; dwBytes
0x180021b5f  xor     edx, edx; dwFlags
0x180021b61  mov     rcx, rax; hHeap
0x180021b64  call    cs:__imp_HeapAlloc
0x180021b6b  nop     dword ptr [rax+rax+00h]
0x180021b70  mov     rbx, rax
0x180021b73  test    rax, rax
0x180021b76  jnz     short loc_180021B8C
0x180021b78  mov     edi, 8007000Eh
0x180021b7d  mov     ecx, edi
0x180021b7f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021b84  mov     rbx, r14
0x180021b87  jmp     loc_180021DC3
0x180021b8c  mov     edx, [rbp+arg_0]
0x180021b8f  mov     eax, r14d
0x180021b92  mov     [rbp+var_30], eax
0x180021b95  test    edx, edx
0x180021b97  jz      loc_180021D82
0x180021b9d  mov     [rbp+var_10], rbx
0x180021ba1  mov     rcx, [rbp+var_20]
0x180021ba5  mov     r15d, 80000000h
0x180021bab  mov     r13d, eax
0x180021bae  lea     rax, ds:0[r13*4]
0x180021bb6  add     rax, r13
0x180021bb9  lea     rsi, [rcx+rax*8]
0x180021bbd  mov     rcx, [rbp+hMem]; hMem
0x180021bc1  test    rcx, rcx
0x180021bc4  jz      short loc_180021BD6
0x180021bc6  call    cs:__imp_LocalFree
0x180021bcd  nop     dword ptr [rax+rax+00h]
0x180021bd2  mov     [rbp+hMem], r14
0x180021bd6  mov     rcx, [rbp+phSLC]; hSLC
0x180021bda  lea     rax, [rbp+hMem]
0x180021bde  mov     [rsp+78h+ppLicensingStatus], rax; ppReturnIds
0x180021be3  mov     r9d, 4; eReturnIdType
0x180021be9  lea     rax, [rbp+pnReturnIds]
0x180021bed  mov     r8, rsi; pQueryId
0x180021bf0  mov     edx, r12d; eQueryIdType
0x180021bf3  mov     [rsp+78h+pnStatusCount], rax; pnReturnIds
0x180021bf8  call    cs:__imp_SLGetSLIDList
0x180021bff  nop     dword ptr [rax+rax+00h]
0x180021c04  mov     edi, eax
0x180021c06  add     eax, r15d
0x180021c09  test    r15d, eax
0x180021c0c  jnz     short loc_180021C1A
0x180021c0e  cmp     edi, 0C004F012h
0x180021c14  jnz     loc_180021DBC
0x180021c1a  mov     r15d, r14d
0x180021c1d  test    edi, edi
0x180021c1f  js      short loc_180021C29
0x180021c21  cmp     [rbp+pnReturnIds], r14d
0x180021c25  cmovnz  r15d, r12d
0x180021c29  mov     rcx, [rbp+var_48]; hMem
0x180021c2d  test    rcx, rcx
0x180021c30  jz      short loc_180021C42
0x180021c32  call    cs:__imp_LocalFree
0x180021c39  nop     dword ptr [rax+rax+00h]
0x180021c3e  mov     [rbp+var_48], r14
0x180021c42  mov     rcx, [rbp+phSLC]; hSLC
0x180021c46  lea     rax, [rbp+var_48]
0x180021c4a  mov     [rsp+78h+ppLicensingStatus], rax; ppbValue
0x180021c4f  lea     r8, aUxdifferentiat; "UXDifferentiator"
0x180021c56  lea     rax, [rbp+pcbValue]
0x180021c5a  mov     [rbp+var_38], r14d
0x180021c5e  xor     r9d, r9d; peDataType
0x180021c61  mov     [rsp+78h+pnStatusCount], rax; pcbValue
0x180021c66  mov     rdx, rsi; pProductSkuId
0x180021c69  mov     r12d, r14d
0x180021c6c  call    cs:__imp_SLGetProductSkuInformation
0x180021c73  nop     dword ptr [rax+rax+00h]
0x180021c78  mov     edi, eax
0x180021c7a  test    eax, eax
0x180021c7c  jns     short loc_180021C8B
0x180021c7e  cmp     eax, 0C004F012h
0x180021c83  jnz     loc_180021AF0
0x180021c89  jmp     short loc_180021CA6
0x180021c8b  mov     rcx, [rbp+var_48]; String2
0x180021c8f  lea     rdx, [rbp+var_38]
0x180021c93  call    ?ConvertChannelStringToType@?$CSLAggregationUtilsT@VCEmptyType@@@@SAJQEBGPEAW4tagE_LICENSING_CHANNEL@@@Z; CSLAggregationUtilsT<CEmptyType>::ConvertChannelStringToType(ushort const * const,tagE_LICENSING_CHANNEL *)
0x180021c98  mov     edi, eax
0x180021c9a  test    eax, eax
0x180021c9c  js      loc_180021AF0
0x180021ca2  mov     r12d, [rbp+var_38]
0x180021ca6  mov     rcx, [rbp+phSLC]; hSLC
0x180021caa  lea     r9, [rbp+var_34]
0x180021cae  mov     r8, rsi
0x180021cb1  call    ?GetWindowsSkuCategory@?$CSLAggregationUtilsT@VCEmptyType@@@@SAJPEAXPEBU_GUID@@1PEAW4E_LICENSE_CATEGORY@@@Z; CSLAggregationUtilsT<CEmptyType>::GetWindowsSkuCategory(void *,_GUID const *,_GUID const *,E_LICENSE_CATEGORY *)
0x180021cb6  mov     edi, eax
0x180021cb8  test    eax, eax
0x180021cba  js      loc_180021AF0
0x180021cc0  cmp     dword ptr [rsi+1Ch], 4004F00Dh
0x180021cc7  jnz     short loc_180021CF8
0x180021cc9  mov     eax, [rsi+18h]
0x180021ccc  lea     ecx, [rax+1Eh]
0x180021ccf  cmp     ecx, eax
0x180021cd1  jb      short loc_180021CDB
0x180021cd3  mov     [rsi+18h], ecx
0x180021cd6  mov     edi, r14d
0x180021cd9  jmp     short loc_180021CE9
0x180021cdb  mov     eax, 80070216h
0x180021ce0  mov     ecx, eax
0x180021ce2  mov     edi, eax
0x180021ce4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021ce9  mov     ecx, edi
0x180021ceb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021cf0  test    edi, edi
0x180021cf2  js      loc_180021DBC
0x180021cf8  mov     r9, [rbp+var_10]
0x180021cfc  xor     eax, eax
0x180021cfe  movups  xmm0, xmmword ptr [rsi]
0x180021d01  mov     ecx, [rbp+var_34]
0x180021d04  mov     r14, rbx
0x180021d07  movups  xmm1, xmmword ptr [rsi+10h]
0x180021d0b  mov     r8, r9
0x180021d0e  mov     [rbp+var_10], r9
0x180021d12  movsd   xmm2, qword ptr [rsi+20h]
0x180021d17  imul    rdx, r13, 38h ; '8'
0x180021d1b  test    rbx, rbx
0x180021d1e  cmovnz  rax, r9
0x180021d22  movups  xmmword ptr [rax+rdx], xmm0
0x180021d26  movups  xmmword ptr [rax+rdx+10h], xmm1
0x180021d2b  movsd   qword ptr [rax+rdx+20h], xmm2
0x180021d31  xor     eax, eax
0x180021d33  test    rbx, rbx
0x180021d36  cmovnz  rax, r9
0x180021d3a  mov     [rax+rdx+28h], r12d
0x180021d3f  xor     eax, eax
0x180021d41  test    rbx, rbx
0x180021d44  mov     r12d, 1
0x180021d4a  cmovnz  rax, r9
0x180021d4e  mov     [rax+rdx+2Ch], ecx
0x180021d52  xor     eax, eax
0x180021d54  test    rbx, rbx
0x180021d57  cmovnz  rax, r9
0x180021d5b  mov     [rax+rdx+30h], r15d
0x180021d60  mov     eax, [rbp+var_30]
0x180021d63  mov     edx, [rbp+arg_0]
0x180021d66  add     eax, r12d
0x180021d69  mov     [rbp+var_30], eax
0x180021d6c  cmp     eax, edx
0x180021d6e  jnb     short loc_180021D78
0x180021d70  xor     r14d, r14d
0x180021d73  jmp     loc_180021BA1
0x180021d78  mov     rsi, [rbp+arg_10]
0x180021d7c  mov     r15, [rbp+arg_8]
0x180021d80  jmp     short loc_180021D88
0x180021d82  mov     r14, rbx
0x180021d85  mov     r8, rbx
0x180021d88  xor     ecx, ecx
0x180021d8a  test    r14, r14
0x180021d8d  cmovnz  rcx, r8
0x180021d91  call    ?SortLicenseStatusObjects@?$CSLAggregationUtilsT@VCEmptyType@@@@CAJPEAUSLicenseStatusObject@@K@Z; CSLAggregationUtilsT<CEmptyType>::SortLicenseStatusObjects(SLicenseStatusObject *,ulong)
0x180021d96  mov     edi, eax
0x180021d98  test    eax, eax
0x180021d9a  jns     short loc_180021DAB
0x180021d9c  mov     ecx, eax
0x180021d9e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021da3  mov     rbx, r14
0x180021da6  xor     r14d, r14d
0x180021da9  jmp     short loc_180021DC3
0x180021dab  mov     eax, [rbp+arg_0]
0x180021dae  xor     ebx, ebx
0x180021db0  mov     [rsi], eax
0x180021db2  mov     [r15], r14
0x180021db5  jmp     short loc_180021DA6
0x180021db7  mov     edi, 8000FFFFh
0x180021dbc  mov     ecx, edi
0x180021dbe  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021dc3  mov     ecx, edi
0x180021dc5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021dca  test    rbx, rbx
0x180021dcd  jz      short loc_180021DEF
0x180021dcf  call    cs:__imp_GetProcessHeap
0x180021dd6  nop     dword ptr [rax+rax+00h]
0x180021ddb  mov     r8, rbx; lpMem
0x180021dde  xor     edx, edx; dwFlags
0x180021de0  mov     rcx, rax; hHeap
0x180021de3  call    cs:__imp_HeapFree
0x180021dea  nop     dword ptr [rax+rax+00h]
0x180021def  mov     rcx, [rbp+hMem]; hMem
0x180021df3  test    rcx, rcx
0x180021df6  jz      short loc_180021E08
0x180021df8  call    cs:__imp_LocalFree
0x180021dff  nop     dword ptr [rax+rax+00h]
0x180021e04  mov     [rbp+hMem], r14
0x180021e08  mov     rcx, [rbp+var_48]; hMem
0x180021e0c  test    rcx, rcx
0x180021e0f  jz      short loc_180021E21
0x180021e11  call    cs:__imp_LocalFree
0x180021e18  nop     dword ptr [rax+rax+00h]
0x180021e1d  mov     [rbp+var_48], r14
0x180021e21  mov     rcx, [rbp+var_20]; hMem
0x180021e25  test    rcx, rcx
0x180021e28  jz      short loc_180021E3A
0x180021e2a  call    cs:__imp_LocalFree
0x180021e31  nop     dword ptr [rax+rax+00h]
0x180021e36  mov     [rbp+var_20], r14
0x180021e3a  mov     rcx, [rbp+phSLC]; hSLC
0x180021e3e  test    rcx, rcx
0x180021e41  jz      short loc_180021E4F
0x180021e43  call    cs:__imp_SLClose
0x180021e4a  nop     dword ptr [rax+rax+00h]
0x180021e4f  mov     eax, edi
0x180021e51  add     rsp, 78h
0x180021e55  pop     r15
0x180021e57  pop     r14
0x180021e59  pop     r13
0x180021e5b  pop     r12
0x180021e5d  pop     rdi
0x180021e5e  pop     rsi
0x180021e5f  pop     rbx
0x180021e60  pop     rbp
0x180021e61  retn
```
