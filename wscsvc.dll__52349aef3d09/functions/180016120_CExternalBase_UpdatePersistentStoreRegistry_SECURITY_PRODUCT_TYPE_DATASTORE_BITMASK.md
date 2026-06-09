# CExternalBase::UpdatePersistentStoreRegistry(_SECURITY_PRODUCT_TYPE,_DATASTORE_BITMASK)

- ea: `0x180016120`
- end: `0x180016813`
- name: `?UpdatePersistentStoreRegistry@CExternalBase@@QEAAJW4_SECURITY_PRODUCT_TYPE@@W4_DATASTORE_BITMASK@@@Z`
- size: `1779`
- prototype: `__int64 __fastcall(__int64, int, char)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180008e88`
- `0x180015bf0`
- `0x180036adc`

## callees

- `0x180016120`
- `0x180016ae8`
- `0x180018ab0`
- `0x18001f97c`
- `0x1800202e8`
- `0x180027ee4`
- `0x180029158`
- `0x1800296d4`
- `0x180029e74`
- `0x180037960`
- `0x18003fbf2`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016274`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016274`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800163b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800163f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800163b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800163f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800162df`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016625`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001669f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016751`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800167cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800162df`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016625`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001669f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016751`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800167cb`

## string_xrefs

- `0x1800161e2`: `SOFTWARE\Microsoft\Security Center\Provider\Av`
- `0x180016497`: `admin\wsc\src\client\service\wscsvclib\externalbase.cpp`
- `0x180016572`: `admin\wsc\src\client\service\wscsvclib\externalbase.cpp`
- `0x18001655f`: `SOFTWARE\Microsoft\Security Center\Provider\Fw`

## pseudocode

```c
__int64 __fastcall CExternalBase::UpdatePersistentStoreRegistry(__int64 a1, int a2, char a3)
{
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rdx
  unsigned int v8; // esi
  const WCHAR *v9; // rdi
  BYTE **v10; // rax
  int v11; // eax
  unsigned int v12; // edi
  LSTATUS v13; // eax
  LSTATUS v14; // r14d
  HKEY v15; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  const BYTE *v28; // rcx
  LSTATUS v29; // r14d
  const BYTE *v30; // rcx
  LSTATUS v31; // r14d
  const BYTE *v32; // rcx
  LSTATUS v33; // r14d
  void **v34; // rcx
  LSTATUS v35; // ebx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  char v41; // [rsp+60h] [rbp-A0h] BYREF
  void *Block[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v43; // [rsp+98h] [rbp-68h]
  unsigned __int64 v44; // [rsp+A0h] [rbp-60h]
  BYTE *v45[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v47; // [rsp+C0h] [rbp-40h]
  BYTE *v48[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v49; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v50; // [rsp+E0h] [rbp-20h]
  BYTE *lpData[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v52; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v53; // [rsp+100h] [rbp+0h]
  WCHAR SubKey[264]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  *(_DWORD *)Data = *(_DWORD *)(a1 + 80);
  v53 = 7;
  v52 = 0;
  LOWORD(lpData[0]) = 0;
  v50 = 7;
  v49 = 0;
  LOWORD(v48[0]) = 0;
  v47 = 7;
  v46 = 0;
  LOWORD(v45[0]) = 0;
  v44 = 7;
  v43 = 0;
  LOWORD(Block[0]) = 0;
  v5 = lambda_5190e6ea1bae239ca2f9bafce766553d_::_lambda_5190e6ea1bae239ca2f9bafce766553d_(
         (unsigned int)&v41,
         (unsigned int)lpData,
         a1,
         (unsigned int)v48,
         (__int64)v45,
         (__int64)Block);
  v6 = wil::ResultFromException__lambda_5190e6ea1bae239ca2f9bafce766553d___(v5);
  v8 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D0,
      (unsigned int)"admin\\wsc\\src\\client\\service\\wscsvclib\\externalbase.cpp",
      (const char *)(unsigned int)v6,
      dwOptions);
    LOBYTE(v17) = 1;
    std::wstring::_Tidy(Block, v17, 0);
    LOBYTE(v18) = 1;
    std::wstring::_Tidy(v45, v18, 0);
    LOBYTE(v19) = 1;
    std::wstring::_Tidy(v48, v19, 0);
    LOBYTE(v20) = 1;
    std::wstring::_Tidy(lpData, v20, 0);
    return v8;
  }
  else
  {
    if ( !a2 )
    {
      v9 = L"SOFTWARE\\Microsoft\\Security Center\\Provider\\Av";
      goto LABEL_4;
    }
    if ( a2 == 1 )
    {
      v9 = L"SOFTWARE\\Microsoft\\Security Center\\Provider\\Fw";
LABEL_4:
      memset_0(SubKey, 0, 0x208u);
      if ( v53 < 8 )
        v10 = lpData;
      else
        v10 = (BYTE **)lpData[0];
      v11 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", v9, v10);
      v12 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2DB,
          (unsigned int)"admin\\wsc\\src\\client\\service\\wscsvclib\\externalbase.cpp",
          (const char *)(unsigned int)v11,
          dwOptionsa);
        LOBYTE(v24) = 1;
        std::wstring::_Tidy(Block, v24, 0);
        LOBYTE(v25) = 1;
        std::wstring::_Tidy(v45, v25, 0);
        LOBYTE(v26) = 1;
        std::wstring::_Tidy(v48, v26, 0);
        LOBYTE(v27) = 1;
        std::wstring::_Tidy(lpData, v27, 0);
        return v12;
      }
      dwDisposition = 2;
      hKey = 0;
      v13 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
      v12 = v13;
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            (unsigned int)WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids,
            (unsigned int)SubKey,
            v13);
        }
        if ( (int)v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
        v15 = hKey;
        if ( !hKey )
          goto LABEL_17;
LABEL_16:
        RegCloseKey(v15);
LABEL_17:
        if ( v44 >= 8 )
          operator delete(Block[0]);
        LOWORD(Block[0]) = 0;
        v43 = 0;
        v44 = 7;
        if ( v47 >= 8 )
          operator delete(v45[0]);
        LOWORD(v45[0]) = 0;
        v46 = 0;
        v47 = 7;
        if ( v50 >= 8 )
          operator delete(v48[0]);
        LOWORD(v48[0]) = 0;
        v49 = 0;
        v50 = 7;
        if ( v53 >= 8 )
          operator delete(lpData[0]);
        return v12;
      }
      v12 = 0;
      if ( dwDisposition == 1 )
      {
        a3 = -1;
      }
      else if ( (a3 & 1) == 0 )
      {
        goto LABEL_10;
      }
      v28 = (const BYTE *)lpData;
      if ( v53 >= 8 )
        v28 = lpData[0];
      v29 = RegSetValueExW(hKey, L"GUID", 0, 1u, v28, 2 * v52);
      if ( v29 )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids, SubKey);
        }
        if ( v29 > 0 )
          v12 = (unsigned __int16)v29 | 0x80070000;
        else
          v12 = v29;
      }
LABEL_10:
      if ( (a3 & 2) != 0 )
      {
        v30 = (const BYTE *)v48;
        if ( v50 >= 8 )
          v30 = v48[0];
        v31 = RegSetValueExW(hKey, L"DISPLAYNAME", 0, 1u, v30, 2 * v49);
        if ( v31 )
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids, SubKey);
          }
          if ( v31 > 0 )
            v12 = (unsigned __int16)v31 | 0x80070000;
          else
            v12 = v31;
        }
      }
      if ( (a3 & 4) != 0 )
      {
        v14 = RegSetValueExW(hKey, L"STATE", 0, 4u, Data, 4u);
        if ( v14 )
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids, SubKey);
          }
          if ( v14 > 0 )
            v12 = (unsigned __int16)v14 | 0x80070000;
          else
            v12 = v14;
        }
      }
      if ( (a3 & 8) != 0 )
      {
        v32 = (const BYTE *)v45;
        if ( v47 >= 8 )
          v32 = v45[0];
        v33 = RegSetValueExW(hKey, L"PRODUCTEXE", 0, 1u, v32, 2 * v46);
        if ( v33 )
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids, SubKey);
          }
          if ( v33 > 0 )
            v12 = (unsigned __int16)v33 | 0x80070000;
          else
            v12 = v33;
        }
      }
      if ( (a3 & 0x10) != 0 )
      {
        v34 = Block;
        if ( v44 >= 8 )
          v34 = (void **)Block[0];
        v35 = RegSetValueExW(hKey, L"REPORTINGEXE", 0, 1u, (const BYTE *)v34, 2 * v43);
        if ( v35 )
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids, SubKey);
          }
          if ( v35 > 0 )
            v12 = (unsigned __int16)v35 | 0x80070000;
          else
            v12 = v35;
        }
      }
      v15 = hKey;
      if ( !hKey )
        goto LABEL_17;
      goto LABEL_16;
    }
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids);
    }
    LOBYTE(v7) = 1;
    std::wstring::_Tidy(Block, v7, 0);
    LOBYTE(v21) = 1;
    std::wstring::_Tidy(v45, v21, 0);
    LOBYTE(v22) = 1;
    std::wstring::_Tidy(v48, v22, 0);
    LOBYTE(v23) = 1;
    std::wstring::_Tidy(lpData, v23, 0);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180016120  mov     [rsp-8+arg_10], rbx
0x180016125  mov     [rsp-8+arg_18], rsi
0x18001612a  push    rbp
0x18001612b  push    rdi
0x18001612c  push    r15
0x18001612e  lea     rbp, [rsp-230h]
0x180016136  sub     rsp, 330h
0x18001613d  mov     rax, cs:__security_cookie
0x180016144  xor     rax, rsp
0x180016147  mov     [rbp+240h+var_20], rax
0x18001614e  mov     eax, [rcx+50h]
0x180016151  lea     r9, [rbp+240h+var_278]
0x180016155  xor     r15d, r15d
0x180016158  mov     dword ptr [rsp+340h+Data], eax
0x18001615c  lea     rax, [rbp+240h+Block]
0x180016160  mov     [rbp+240h+var_240], 7
0x180016168  mov     qword ptr [rsp+340h+samDesired], rax
0x18001616d  mov     ebx, r8d
0x180016170  lea     rax, [rbp+240h+var_298]
0x180016174  mov     [rbp+240h+var_248], r15
0x180016178  mov     r8, rcx
0x18001617b  mov     qword ptr [rsp+340h+dwOptions], rax; int
0x180016180  mov     edi, edx
0x180016182  mov     word ptr [rbp+240h+lpData], r15w
0x180016187  lea     rdx, [rbp+240h+lpData]
0x18001618b  mov     [rbp+240h+var_260], 7
0x180016193  lea     rcx, [rsp+340h+var_2E0]
0x180016198  mov     [rbp+240h+var_268], r15
0x18001619c  mov     word ptr [rbp+240h+var_278], r15w
0x1800161a1  mov     [rbp+240h+var_280], 7
0x1800161a9  mov     [rbp+240h+var_288], r15
0x1800161ad  mov     word ptr [rbp+240h+var_298], r15w
0x1800161b2  mov     [rbp+240h+var_2A0], 7
0x1800161ba  mov     [rbp+240h+var_2A8], r15
0x1800161be  mov     word ptr [rbp+240h+Block], r15w
0x1800161c3  call    _lambda_5190e6ea1bae239ca2f9bafce766553d____lambda_5190e6ea1bae239ca2f9bafce766553d_
0x1800161c8  mov     rcx, rax
0x1800161cb  call    wil__ResultFromException__lambda_5190e6ea1bae239ca2f9bafce766553d___
0x1800161d0  mov     esi, eax
0x1800161d2  test    eax, eax
0x1800161d4  js      loc_180016490
0x1800161da  test    edi, edi
0x1800161dc  jnz     loc_1800164EA
0x1800161e2  lea     rdi, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Security Center\\P"...
0x1800161e9  xor     edx, edx; Val
0x1800161eb  lea     rcx, [rbp+240h+SubKey]; void *
0x1800161ef  mov     r8d, 208h; Size
0x1800161f5  call    memset_0
0x1800161fa  cmp     [rbp+240h+var_240], 8
0x1800161ff  jb      loc_1800163BF
0x180016205  mov     rax, [rbp+240h+lpData]
0x180016209  mov     r9, rdi
0x18001620c  mov     qword ptr [rsp+340h+dwOptions], rax; int
0x180016211  lea     r8, aSS; "%s\\%s"
0x180016218  mov     edx, 104h; unsigned __int64
0x18001621d  lea     rcx, [rbp+240h+SubKey]; unsigned __int16 *
0x180016221  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016226  mov     edi, eax
0x180016228  test    eax, eax
0x18001622a  js      loc_18001656B
0x180016230  lea     rax, [rsp+340h+dwDisposition]
0x180016235  mov     [rsp+340h+dwDisposition], 2
0x18001623d  mov     [rsp+340h+lpdwDisposition], rax; lpdwDisposition
0x180016242  lea     rdx, [rbp+240h+SubKey]; lpSubKey
0x180016246  lea     rax, [rsp+340h+hKey]
0x18001624b  mov     [rsp+340h+hKey], r15
0x180016250  mov     [rsp+340h+phkResult], rax; phkResult
0x180016255  xor     r9d, r9d; lpClass
0x180016258  mov     [rsp+340h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18001625d  xor     r8d, r8d; Reserved
0x180016260  mov     [rsp+340h+samDesired], 2001Fh; samDesired
0x180016268  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001626f  mov     [rsp+340h+dwOptions], r15d; dwOptions
0x180016274  call    cs:__imp_RegCreateKeyExW
0x18001627a  mov     edi, eax
0x18001627c  test    eax, eax
0x18001627e  jnz     loc_1800163C8
0x180016284  cmp     [rsp+340h+dwDisposition], 1
0x180016289  lea     rsi, WPP_GLOBAL_Control
0x180016290  mov     [rsp+340h+arg_8], r14
0x180016298  mov     edi, r15d
0x18001629b  jz      loc_1800165EF
0x1800162a1  test    bl, 1
0x1800162a4  jnz     loc_1800165F4
0x1800162aa  test    bl, 2
0x1800162ad  jnz     loc_18001666E
0x1800162b3  test    bl, 4
0x1800162b6  jz      short loc_1800162F0
0x1800162b8  mov     rcx, [rsp+340h+hKey]; hKey
0x1800162bd  lea     rax, [rsp+340h+Data]
0x1800162c2  mov     [rsp+340h+samDesired], 4; cbData
0x1800162ca  lea     rdx, aState; "STATE"
0x1800162d1  mov     r9d, 4; dwType
0x1800162d7  mov     qword ptr [rsp+340h+dwOptions], rax; lpData
0x1800162dc  xor     r8d, r8d; Reserved
0x1800162df  call    cs:__imp_RegSetValueExW
0x1800162e5  mov     r14d, eax
0x1800162e8  test    eax, eax
0x1800162ea  jnz     loc_1800166E8
0x1800162f0  test    bl, 8
0x1800162f3  jnz     loc_180016720
0x1800162f9  mov     r14, [rsp+340h+arg_8]
0x180016301  test    bl, 10h
0x180016304  jnz     loc_18001679A
0x18001630a  mov     rcx, [rsp+340h+hKey]; hKey
0x18001630f  test    rcx, rcx
0x180016312  jnz     loc_1800163B4
0x180016318  cmp     [rbp+240h+var_2A0], 8
0x18001631d  jb      short loc_180016328
0x18001631f  mov     rcx, [rbp+240h+Block]; Block
0x180016323  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016328  cmp     [rbp+240h+var_280], 8
0x18001632d  mov     word ptr [rbp+240h+Block], r15w
0x180016332  mov     [rbp+240h+var_2A8], r15
0x180016336  mov     [rbp+240h+var_2A0], 7
0x18001633e  jb      short loc_180016349
0x180016340  mov     rcx, [rbp+240h+var_298]; Block
0x180016344  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016349  cmp     [rbp+240h+var_260], 8
0x18001634e  mov     word ptr [rbp+240h+var_298], r15w
0x180016353  mov     [rbp+240h+var_288], r15
0x180016357  mov     [rbp+240h+var_280], 7
0x18001635f  jb      short loc_18001636A
0x180016361  mov     rcx, [rbp+240h+var_278]; Block
0x180016365  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001636a  cmp     [rbp+240h+var_240], 8
0x18001636f  mov     word ptr [rbp+240h+var_278], r15w
0x180016374  mov     [rbp+240h+var_268], r15
0x180016378  mov     [rbp+240h+var_260], 7
0x180016380  jb      short loc_18001638B
0x180016382  mov     rcx, [rbp+240h+lpData]; Block
0x180016386  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001638b  mov     eax, edi
0x18001638d  mov     rcx, [rbp+240h+var_20]
0x180016394  xor     rcx, rsp; StackCookie
0x180016397  call    __security_check_cookie
0x18001639c  lea     r11, [rsp+340h+var_10]
0x1800163a4  mov     rbx, [r11+30h]
0x1800163a8  mov     rsi, [r11+38h]
0x1800163ac  mov     rsp, r11
0x1800163af  pop     r15
0x1800163b1  pop     rdi
0x1800163b2  pop     rbp
0x1800163b3  retn
0x1800163b4  call    cs:__imp_RegCloseKey
0x1800163ba  jmp     loc_180016318
0x1800163bf  lea     rax, [rbp+240h+lpData]
0x1800163c3  jmp     loc_180016209
0x1800163c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163cf  lea     rsi, WPP_GLOBAL_Control
0x1800163d6  cmp     rcx, rsi
0x1800163d9  jnz     loc_1800165C3
0x1800163df  test    edi, edi
0x1800163e1  jg      short loc_1800163FC
0x1800163e3  mov     rcx, [rsp+340h+hKey]; hKey
0x1800163e8  test    rcx, rcx
0x1800163eb  jz      loc_180016318
0x1800163f1  call    cs:__imp_RegCloseKey
0x1800163f7  jmp     loc_180016318
0x1800163fc  movzx   edi, di
0x1800163ff  or      edi, 80070000h
0x180016405  jmp     short loc_1800163E3
0x180016407  test    r14d, r14d
0x18001640a  jg      short loc_180016414
0x18001640c  mov     edi, r14d
0x18001640f  jmp     loc_1800162AA
0x180016414  movzx   edi, r14w
0x180016418  or      edi, 80070000h
0x18001641e  jmp     loc_1800162AA
0x180016423  test    r14d, r14d
0x180016426  jg      short loc_180016430
0x180016428  mov     edi, r14d
0x18001642b  jmp     loc_1800162B3
0x180016430  movzx   edi, r14w
0x180016434  or      edi, 80070000h
0x18001643a  jmp     loc_1800162B3
0x18001643f  test    r14d, r14d
0x180016442  jg      short loc_18001644C
0x180016444  mov     edi, r14d
0x180016447  jmp     loc_1800162F0
0x18001644c  movzx   edi, r14w
0x180016450  or      edi, 80070000h
0x180016456  jmp     loc_1800162F0
0x18001645b  test    r14d, r14d
0x18001645e  jg      short loc_180016468
0x180016460  mov     edi, r14d
0x180016463  jmp     loc_1800162F9
0x180016468  movzx   edi, r14w
0x18001646c  or      edi, 80070000h
0x180016472  jmp     loc_1800162F9
0x180016477  test    ebx, ebx
0x180016479  jg      short loc_180016482
0x18001647b  mov     edi, ebx
0x18001647d  jmp     loc_18001630A
0x180016482  movzx   edi, bx
0x180016485  or      edi, 80070000h
0x18001648b  jmp     loc_18001630A
0x180016490  mov     rcx, [rbp+248h]; this
0x180016497  lea     r8, aAdminWscSrcCli_0; "admin\\wsc\\src\\client\\service\\wscsv"...
0x18001649e  mov     r9d, esi; char *
0x1800164a1  mov     edx, 2D0h; void *
0x1800164a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800164ab  xor     r8d, r8d
0x1800164ae  lea     rcx, [rbp+240h+Block]
0x1800164b2  mov     dl, 1
0x1800164b4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800164b9  xor     r8d, r8d
0x1800164bc  lea     rcx, [rbp+240h+var_298]
0x1800164c0  mov     dl, 1
0x1800164c2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800164c7  xor     r8d, r8d
0x1800164ca  lea     rcx, [rbp+240h+var_278]
0x1800164ce  mov     dl, 1
0x1800164d0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800164d5  xor     r8d, r8d
0x1800164d8  lea     rcx, [rbp+240h+lpData]
0x1800164dc  mov     dl, 1
0x1800164de  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800164e3  mov     eax, esi
0x1800164e5  jmp     loc_18001638D
0x1800164ea  cmp     edi, 1
0x1800164ed  jz      short loc_18001655F
0x1800164ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800164f6  lea     rsi, WPP_GLOBAL_Control
0x1800164fd  cmp     rcx, rsi
0x180016500  jz      short loc_18001651D
0x180016502  test    byte ptr [rcx+1Ch], 1
0x180016506  jz      short loc_18001651D
0x180016508  mov     rcx, [rcx+10h]
0x18001650c  lea     r8, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids
0x180016513  mov     edx, 0Fh
0x180016518  call    WPP_SF_
0x18001651d  xor     r8d, r8d
0x180016520  lea     rcx, [rbp+240h+Block]
0x180016524  mov     dl, 1
0x180016526  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001652b  xor     r8d, r8d
0x18001652e  lea     rcx, [rbp+240h+var_298]
0x180016532  mov     dl, 1
0x180016534  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016539  xor     r8d, r8d
0x18001653c  lea     rcx, [rbp+240h+var_278]
0x180016540  mov     dl, 1
0x180016542  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016547  xor     r8d, r8d
0x18001654a  lea     rcx, [rbp+240h+lpData]
0x18001654e  mov     dl, 1
0x180016550  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016555  mov     eax, 80070057h
0x18001655a  jmp     loc_18001638D
0x18001655f  lea     rdi, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Security Center\\P"...
0x180016566  jmp     loc_1800161E9
0x18001656b  mov     rcx, [rbp+248h]; this
0x180016572  lea     r8, aAdminWscSrcCli_0; "admin\\wsc\\src\\client\\service\\wscsv"...
0x180016579  mov     r9d, edi; char *
0x18001657c  mov     edx, 2DBh; void *
0x180016581  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016586  xor     r8d, r8d
0x180016589  lea     rcx, [rbp+240h+Block]
0x18001658d  mov     dl, 1
0x18001658f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016594  xor     r8d, r8d
0x180016597  lea     rcx, [rbp+240h+var_298]
0x18001659b  mov     dl, 1
0x18001659d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800165a2  xor     r8d, r8d
0x1800165a5  lea     rcx, [rbp+240h+var_278]
0x1800165a9  mov     dl, 1
0x1800165ab  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800165b0  xor     r8d, r8d
0x1800165b3  lea     rcx, [rbp+240h+lpData]
0x1800165b7  mov     dl, 1
0x1800165b9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800165be  jmp     loc_18001638B
0x1800165c3  test    byte ptr [rcx+1Ch], 1
0x1800165c7  jz      loc_1800163DF
0x1800165cd  mov     rcx, [rcx+10h]
0x1800165d1  lea     r9, [rbp+240h+SubKey]
0x1800165d5  mov     edx, 10h
0x1800165da  mov     [rsp+340h+dwOptions], edi
0x1800165de  lea     r8, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids
0x1800165e5  call    WPP_SF_Sd
0x1800165ea  jmp     loc_1800163DF
0x1800165ef  mov     ebx, 0FFFFFFFFh
0x1800165f4  cmp     [rbp+240h+var_240], 8
0x1800165f9  lea     rcx, [rbp+240h+lpData]
0x1800165fd  mov     eax, dword ptr [rbp+240h+var_248]
0x180016600  lea     rdx, aGuid; "GUID"
0x180016607  cmovnb  rcx, [rbp+240h+lpData]
0x18001660c  mov     r9d, 1; dwType
0x180016612  add     eax, eax
0x180016614  xor     r8d, r8d; Reserved
0x180016617  mov     [rsp+340h+samDesired], eax; cbData
0x18001661b  mov     qword ptr [rsp+340h+dwOptions], rcx; lpData
0x180016620  mov     rcx, [rsp+340h+hKey]; hKey
0x180016625  call    cs:__imp_RegSetValueExW
0x18001662b  mov     r14d, eax
0x18001662e  test    eax, eax
0x180016630  jz      loc_1800162AA
0x180016636  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
