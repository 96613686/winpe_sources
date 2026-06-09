# CStoredIdentity::SaveIdentity(void *,bool)

- ea: `0x18005bae0`
- end: `0x18005c167`
- name: `?SaveIdentity@CStoredIdentity@@EEAAJPEAX_N@Z`
- size: `1671`
- prototype: `__int64 __fastcall(CStoredIdentity *this, HANDLE hTransaction, char)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006ac0`
- `0x180007da0`
- `0x18000c050`
- `0x18000ed04`
- `0x18001426c`
- `0x1800143a4`
- `0x1800151c4`
- `0x180015860`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180023d24`
- `0x180038818`
- `0x180038968`
- `0x180038a80`
- `0x18003912c`
- `0x180039d00`
- `0x180043364`
- `0x18004d294`
- `0x180050670`
- `0x180052810`
- `0x18005b74c`
- `0x18005bae0`
- `0x18005c170`
- `0x1800aa3e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bbfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bbfb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005bd2e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005bd2e`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005bd6b`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005c0d1`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005bd6b`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005c0d1`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18005bcd1`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18005bcd1`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18005be01`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18005bf59`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18005be01`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18005bf59`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x18005beb9`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x18005beb9`

## string_xrefs

- `0x18005bb7d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\systemstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall CStoredIdentity::SaveIdentity(CStoredIdentity *this, HANDLE hTransaction, char a3)
{
  __int64 v6; // r9
  unsigned int v7; // r8d
  int v8; // eax
  signed int LastError; // eax
  __int64 CurrentUserKey; // rax
  LSTATUS v11; // eax
  HKEY v12; // rdi
  LSTATUS v13; // eax
  int v14; // eax
  const unsigned __int16 *v15; // r9
  unsigned int v16; // r8d
  LSTATUS v17; // eax
  HKEY v18; // r14
  int v19; // eax
  __int64 v20; // rcx
  int HasAnyKeyword; // eax
  const WCHAR *v22; // rdx
  LSTATUS v23; // eax
  int v24; // eax
  const unsigned __int16 **CID; // rax
  signed int v26; // edi
  int v27; // eax
  int v28; // eax
  const unsigned __int16 *v29; // r8
  int v30; // eax
  unsigned int v31; // ebx
  const unsigned __int16 *phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  const char *phkResultb; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v37[3]; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v39[3]; // [rsp+98h] [rbp-68h] BYREF
  HKEY v40[3]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v41[8]; // [rsp+C8h] [rbp-38h] BYREF
  int v42; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v43; // [rsp+D8h] [rbp-28h]
  _QWORD v44[4]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v45[80]; // [rsp+100h] [rbp+0h] BYREF
  int v46; // [rsp+160h] [rbp+60h] BYREF
  HKEY v47; // [rsp+178h] [rbp+78h] BYREF

  v46 = 0;
  v47 = 0;
  memset(v40, 0, sizeof(v40));
  memset(v37, 0, sizeof(v37));
  memset(hKey, 0, sizeof(hKey));
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpSubKey);
  memset(v39, 0, sizeof(v39));
  v42 = 0;
  v43 = 0;
  v44[0] = "CStoredIdentity::SaveIdentity";
  v44[1] = &v46;
  v44[2] = 0;
  v44[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\systemstore.cpp",
    "CStoredIdentity::SaveIdentity",
    (const char *)0x342,
    0,
    phkResult);
  if ( !*(_DWORD *)(*((_QWORD *)this + 2) - 16LL) )
  {
    LODWORD(v6) = -2147024809;
    v46 = -2147024809;
    phkResultb = "!m_pszName.IsEmpty()";
    v7 = 836;
LABEL_3:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\systemstore.cpp",
      "CStoredIdentity::SaveIdentity",
      v7,
      v6,
      phkResultb);
    goto LABEL_91;
  }
  v8 = CStoredIdentity::ProcessDefaultCertInStore(this);
  v46 = v8;
  if ( v8 < 0 )
  {
    phkResultb = "hr = ProcessDefaultCertInStore()";
    LODWORD(v6) = v8;
    v7 = 842;
    goto LABEL_3;
  }
  if ( (unsigned int)CAutoRevertToSelf::Revert((CAutoRevertToSelf *)&v42, 0) )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(&lpSubKey, L"Software\\Microsoft\\IdentityCRL\\StoredIdentities");
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, L"\\");
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, (char *)this + 16);
    CurrentUserKey = GetCurrentUserKey(v45);
    ATL::CRegKey::operator=(hKey, CurrentUserKey);
    ATL::CRegKey::Close((ATL::CRegKey *)v45);
    if ( *((_DWORD *)this + 13) || (unsigned int)CStoredIdentity::HasAnyKeyword(this, 1) )
    {
      if ( hTransaction )
      {
        v17 = RegCreateKeyTransactedW(hKey[0], lpSubKey, 0, 0, 0, 0x2001Fu, 0, &v47, 0, hTransaction, 0);
        v18 = v47;
        v37[0] = v47;
        v47 = 0;
      }
      else
      {
        v17 = ATL::CRegKey::Create((ATL::CRegKey *)v37, hKey[0], lpSubKey, 0, 0, 0x2001Fu, 0, 0);
        v18 = v37[0];
      }
      v6 = (unsigned int)v17;
      if ( v17 )
      {
        if ( v17 > 0 )
          v6 = (unsigned __int16)v17 | 0x80070000;
        v46 = v6;
        if ( (int)v6 < 0 )
        {
          v7 = 915;
          goto LABEL_21;
        }
      }
      v19 = CStoredIdentity::SaveProperties(this, v37, 1, v6);
      v46 = v19;
      if ( v19 < 0 )
      {
        phkResultb = "hr = SaveProperties(regIdKey, eGlobal)";
        LODWORD(v6) = v19;
        v7 = 917;
        goto LABEL_3;
      }
      if ( (unsigned int)CStoredIdentity::ValidateSystemAccount(this) )
      {
        HasAnyKeyword = CStoredIdentity::HasAnyKeyword(v20, 0);
        v22 = (const WCHAR *)*((_QWORD *)this + 4);
        if ( HasAnyKeyword )
        {
          if ( hTransaction )
          {
            v6 = (unsigned int)RegCreateKeyTransactedW(v18, v22, 0, 0, 0, 0x2001Fu, 0, &v47, 0, hTransaction, 0);
            v39[0] = v47;
            v47 = 0;
          }
          else
          {
            v6 = (unsigned int)ATL::CRegKey::Create((ATL::CRegKey *)v39, v18, v22, 0, 0, 0x2001Fu, 0, 0);
          }
          if ( (_DWORD)v6 )
          {
            if ( (int)v6 > 0 )
              v6 = (unsigned __int16)v6 | 0x80070000;
            v46 = v6;
            if ( (int)v6 < 0 )
            {
              v7 = 953;
              goto LABEL_21;
            }
          }
          v24 = CStoredIdentity::SaveProperties(this, v39, 0, v6);
          v46 = v24;
          if ( v24 < 0 )
          {
            phkResultb = "hr = SaveProperties(regUserKey, eLocal)";
            LODWORD(v6) = v24;
            v7 = 955;
            goto LABEL_3;
          }
        }
        else
        {
          if ( hTransaction )
          {
            v23 = RegDeleteKeyTransactedW(v18, v22, 0, 0, hTransaction, 0);
          }
          else
          {
            v23 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v37, v22);
            v18 = v37[0];
          }
          LODWORD(v6) = v23;
          if ( (v23 & 0xFFFFFFFC) != 0 || v23 == 1 )
          {
            if ( v23 > 0 )
              LODWORD(v6) = (unsigned __int16)v23 | 0x80070000;
            v46 = v6;
            if ( (int)v6 < 0 )
            {
              v7 = 935;
              goto LABEL_21;
            }
          }
        }
      }
      CID = (const unsigned __int16 **)CStoredIdentity::GetCID(this, v41);
      v26 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)v37, L"CID", *CID, 1u);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v41);
      if ( v26 )
      {
        if ( v26 > 0 )
          v26 = (unsigned __int16)v26 | 0x80070000;
        v46 = v26;
        LODWORD(v6) = v26;
        v7 = 959;
        goto LABEL_21;
      }
      v27 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v37, L"AssociatedCount", *((_DWORD *)this + 12));
      LODWORD(v6) = v27;
      if ( v27 )
      {
        if ( v27 > 0 )
          LODWORD(v6) = (unsigned __int16)v27 | 0x80070000;
        v46 = v6;
        if ( (int)v6 < 0 )
        {
          v7 = 961;
          goto LABEL_21;
        }
      }
      v28 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v37, L"AccountsCount", *((_DWORD *)this + 13));
      LODWORD(v6) = v28;
      if ( v28 )
      {
        if ( v28 > 0 )
          LODWORD(v6) = (unsigned __int16)v28 | 0x80070000;
        v46 = v6;
        if ( (int)v6 < 0 )
        {
          v7 = 963;
          goto LABEL_21;
        }
      }
      v29 = (const unsigned __int16 *)*((_QWORD *)this + 5);
      if ( *((_DWORD *)v29 - 4) )
      {
        v30 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)v37, L"LatestDPAPIKeyVersion", v29, 1u);
        LODWORD(v6) = v30;
        if ( v30 )
        {
          if ( v30 > 0 )
            LODWORD(v6) = (unsigned __int16)v30 | 0x80070000;
          v46 = v6;
          if ( (int)v6 < 0 )
          {
            v7 = 967;
            goto LABEL_21;
          }
        }
      }
      if ( !a3 )
        goto LABEL_91;
      v14 = RegFlushKey(v18);
      if ( !v14 )
        goto LABEL_91;
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      v15 = L"regIdKey.Flush() failed with error=0x%x, continuing...";
      v16 = 976;
    }
    else
    {
      if ( hTransaction )
      {
        v11 = RegOpenKeyTransactedW(
                hKey[0],
                L"Software\\Microsoft\\IdentityCRL\\StoredIdentities",
                0,
                0x2001Fu,
                &v47,
                hTransaction,
                0);
        v12 = v47;
        v40[0] = v47;
        v47 = 0;
      }
      else
      {
        v11 = ATL::CRegKey::Open(
                (ATL::CRegKey *)v40,
                hKey[0],
                L"Software\\Microsoft\\IdentityCRL\\StoredIdentities",
                0x2001Fu);
        v12 = v40[0];
      }
      LODWORD(v6) = v11;
      if ( (unsigned int)(v11 - 2) > 1 )
      {
        if ( v11 )
        {
          if ( v11 > 0 )
            LODWORD(v6) = (unsigned __int16)v11 | 0x80070000;
          v46 = v6;
          v7 = 877;
          goto LABEL_21;
        }
        v13 = RegDeleteTreeW(v12, *((LPCWSTR *)this + 2));
        LODWORD(v6) = v13;
        if ( (v13 & 0xFFFFFFFC) != 0 || v13 == 1 )
        {
          if ( v13 > 0 )
            LODWORD(v6) = (unsigned __int16)v13 | 0x80070000;
          v46 = v6;
          if ( (int)v6 < 0 )
          {
            v7 = 886;
LABEL_21:
            phkResultb = "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)";
            goto LABEL_3;
          }
        }
      }
      if ( !a3 )
        goto LABEL_91;
      v14 = RegFlushKey(v12);
      if ( !v14 )
        goto LABEL_91;
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      v15 = L"regStoredId.Flush failed with error=0x%x, continuing...";
      v16 = 896;
    }
    LODWORD(phkResulta) = v14;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\systemstore.cpp",
      v16,
      v15,
      phkResulta);
    goto LABEL_91;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v46 = LastError;
  if ( LastError >= 0 )
    v46 = -2147024891;
LABEL_91:
  v31 = v46;
  CTraceFuncW<long>::~CTraceFuncW<long>(v44);
  CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&v42);
  ATL::CRegKey::Close((ATL::CRegKey *)v39);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpSubKey);
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  ATL::CRegKey::Close((ATL::CRegKey *)v37);
  ATL::CRegKey::Close((ATL::CRegKey *)v40);
  return v31;
}

```

## disassembly

```asm
0x18005bae0  mov     [rsp-8+arg_8], rbx
0x18005bae5  push    rbp
0x18005bae6  push    rsi
0x18005bae7  push    rdi
0x18005bae8  push    r12
0x18005baea  push    r13
0x18005baec  push    r14
0x18005baee  push    r15
0x18005baf0  lea     rbp, [rsp-20h]
0x18005baf5  sub     rsp, 120h
0x18005bafc  mov     r15b, r8b
0x18005baff  mov     rdi, rdx
0x18005bb02  mov     rsi, rcx
0x18005bb05  xor     r12d, r12d
0x18005bb08  mov     [rbp+50h+arg_0], r12d
0x18005bb0c  mov     [rbp+50h+arg_18], r12
0x18005bb10  mov     [rbp+50h+var_A0], r12
0x18005bb14  mov     [rbp+50h+var_98], r12
0x18005bb18  mov     [rbp+50h+var_90], r12
0x18005bb1c  mov     [rsp+150h+var_E8], r12
0x18005bb21  mov     [rsp+150h+var_E0], r12
0x18005bb26  mov     [rsp+150h+var_D8], r12
0x18005bb2b  mov     [rbp+50h+hKey], r12
0x18005bb2f  mov     [rbp+50h+var_C8], r12
0x18005bb33  mov     [rbp+50h+var_C0], r12
0x18005bb37  lea     rcx, [rsp+150h+lpSubKey]
0x18005bb3c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005bb41  nop
0x18005bb42  mov     [rbp+50h+var_B8], r12
0x18005bb46  mov     [rbp+50h+var_B0], r12
0x18005bb4a  mov     [rbp+50h+var_A8], r12
0x18005bb4e  mov     [rbp+50h+var_80], r12d
0x18005bb52  mov     [rbp+50h+var_78], r12
0x18005bb56  lea     rbx, aCstoredidentit_20; "CStoredIdentity::SaveIdentity"
0x18005bb5d  mov     [rbp+50h+var_70], rbx
0x18005bb61  lea     rax, [rbp+50h+arg_0]
0x18005bb65  mov     [rbp+50h+var_68], rax
0x18005bb69  mov     [rbp+50h+var_60], r12
0x18005bb6d  mov     [rbp+50h+var_58], r12
0x18005bb71  xor     r9d, r9d; unsigned int
0x18005bb74  mov     r8d, 342h; char *
0x18005bb7a  mov     rdx, rbx; char *
0x18005bb7d  lea     r13, aOnecoreuapDsEx_40; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18005bb84  mov     rcx, r13; this
0x18005bb87  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18005bb8c  nop
0x18005bb8d  lea     r14, [rsi+10h]
0x18005bb91  mov     rax, [r14]
0x18005bb94  cmp     [rax-10h], r12d
0x18005bb98  jnz     short loc_18005BBC6
0x18005bb9a  mov     r9d, 80070057h; int
0x18005bba0  mov     [rbp+50h+arg_0], r9d
0x18005bba4  lea     rax, aMPsznameIsempt; "!m_pszName.IsEmpty()"
0x18005bbab  mov     [rsp+150h+phkResult], rax; char *
0x18005bbb0  mov     r8d, 344h; unsigned int
0x18005bbb6  mov     rdx, rbx; char *
0x18005bbb9  mov     rcx, r13; char *
0x18005bbbc  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18005bbc1  jmp     loc_18005C100
0x18005bbc6  mov     rcx, rsi; this
0x18005bbc9  call    ?ProcessDefaultCertInStore@CStoredIdentity@@AEAAJXZ; CStoredIdentity::ProcessDefaultCertInStore(void)
0x18005bbce  mov     [rbp+50h+arg_0], eax
0x18005bbd1  test    eax, eax
0x18005bbd3  jns     short loc_18005BBEC
0x18005bbd5  lea     rcx, aHrProcessdefau; "hr = ProcessDefaultCertInStore()"
0x18005bbdc  mov     [rsp+150h+phkResult], rcx
0x18005bbe1  mov     r9d, eax
0x18005bbe4  mov     r8d, 34Ah
0x18005bbea  jmp     short loc_18005BBB6
0x18005bbec  xor     edx, edx; int
0x18005bbee  lea     rcx, [rbp+50h+var_80]; this
0x18005bbf2  call    ?Revert@CAutoRevertToSelf@@QEAAHH@Z; CAutoRevertToSelf::Revert(int)
0x18005bbf7  test    eax, eax
0x18005bbf9  jnz     short loc_18005BC24
0x18005bbfb  call    cs:__imp_GetLastError
0x18005bc01  test    eax, eax
0x18005bc03  jle     short loc_18005BC0D
0x18005bc05  movzx   eax, ax
0x18005bc08  or      eax, 80070000h
0x18005bc0d  mov     [rbp+50h+arg_0], eax
0x18005bc10  test    eax, eax
0x18005bc12  js      loc_18005C100
0x18005bc18  mov     [rbp+50h+arg_0], 80070005h
0x18005bc1f  jmp     loc_18005C100
0x18005bc24  lea     rbx, aSoftwareMicros_20; "Software\\Microsoft\\IdentityCRL\\Store"...
0x18005bc2b  mov     rdx, rbx
0x18005bc2e  lea     rcx, [rsp+150h+lpSubKey]
0x18005bc33  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18005bc38  lea     rdx, SubBlock; "\\"
0x18005bc3f  lea     rcx, [rsp+150h+lpSubKey]
0x18005bc44  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18005bc49  mov     rdx, r14
0x18005bc4c  lea     rcx, [rsp+150h+lpSubKey]
0x18005bc51  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x18005bc56  lea     rcx, [rbp+50h+var_50]
0x18005bc5a  call    ?GetCurrentUserKey@@YA?AVCRegKey@ATL@@XZ; GetCurrentUserKey(void)
0x18005bc5f  mov     rdx, rax
0x18005bc62  lea     rcx, [rbp+50h+hKey]
0x18005bc66  call    ??4CRegKey@ATL@@QEAAAEAV01@AEAV01@@Z; ATL::CRegKey::operator=(ATL::CRegKey &)
0x18005bc6b  lea     rcx, [rbp+50h+var_50]; this
0x18005bc6f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18005bc74  cmp     [rsi+34h], r12d
0x18005bc78  jnz     loc_18005BD92
0x18005bc7e  mov     edx, 1
0x18005bc83  mov     rcx, rsi
0x18005bc86  call    ?HasAnyKeyword@CStoredIdentity@@QEAAHW4PropertyScope@@@Z; CStoredIdentity::HasAnyKeyword(PropertyScope)
0x18005bc8b  test    eax, eax
0x18005bc8d  jnz     loc_18005BD92
0x18005bc93  mov     r9d, 2001Fh; unsigned int
0x18005bc99  test    rdi, rdi
0x18005bc9c  jnz     short loc_18005BCB4
0x18005bc9e  mov     r8, rbx; unsigned __int16 *
0x18005bca1  mov     rdx, [rbp+50h+hKey]; HKEY
0x18005bca5  lea     rcx, [rbp+50h+var_A0]; this
0x18005bca9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18005bcae  mov     rdi, [rbp+50h+var_A0]
0x18005bcb2  jmp     short loc_18005BCE3
0x18005bcb4  mov     [rsp+150h+pExtendedParemeter], r12; pExtendedParemeter
0x18005bcb9  mov     [rsp+150h+hTransaction], rdi; hTransaction
0x18005bcbe  lea     rax, [rbp+50h+arg_18]
0x18005bcc2  mov     [rsp+150h+phkResult], rax; phkResult
0x18005bcc7  xor     r8d, r8d; ulOptions
0x18005bcca  mov     rdx, rbx; lpSubKey
0x18005bccd  mov     rcx, [rbp+50h+hKey]; hKey
0x18005bcd1  call    cs:__imp_RegOpenKeyTransactedW
0x18005bcd7  mov     rdi, [rbp+50h+arg_18]
0x18005bcdb  mov     [rbp+50h+var_A0], rdi
0x18005bcdf  mov     [rbp+50h+arg_18], r12
0x18005bce3  mov     r9d, eax
0x18005bce6  lea     eax, [rax-2]
0x18005bce9  mov     ebx, 80070000h
0x18005bcee  cmp     eax, 1
0x18005bcf1  jbe     short loc_18005BD5F
0x18005bcf3  test    r9d, r9d
0x18005bcf6  jz      short loc_18005BD28
0x18005bcf8  jle     short loc_18005BD01
0x18005bcfa  movzx   r9d, r9w
0x18005bcfe  or      r9d, ebx
0x18005bd01  mov     [rbp+50h+arg_0], r9d
0x18005bd05  test    r9d, r9d
0x18005bd08  jns     short loc_18005BD5F
0x18005bd0a  mov     r8d, 36Dh
0x18005bd10  lea     rax, aHrHresultFromW_19; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x18005bd17  mov     [rsp+150h+phkResult], rax
0x18005bd1c  lea     rdx, aCstoredidentit_20; "CStoredIdentity::SaveIdentity"
0x18005bd23  jmp     loc_18005BBB9
0x18005bd28  mov     rdx, [r14]; lpSubKey
0x18005bd2b  mov     rcx, rdi; hKey
0x18005bd2e  call    cs:__imp_RegDeleteTreeW
0x18005bd34  mov     r9d, eax
0x18005bd37  test    eax, 0FFFFFFFCh
0x18005bd3c  jnz     short loc_18005BD43
0x18005bd3e  cmp     eax, 1
0x18005bd41  jnz     short loc_18005BD5F
0x18005bd43  test    eax, eax
0x18005bd45  jle     short loc_18005BD4E
0x18005bd47  movzx   r9d, ax
0x18005bd4b  or      r9d, ebx
0x18005bd4e  mov     [rbp+50h+arg_0], r9d
0x18005bd52  test    r9d, r9d
0x18005bd55  jns     short loc_18005BD5F
0x18005bd57  mov     r8d, 376h
0x18005bd5d  jmp     short loc_18005BD10
0x18005bd5f  test    r15b, r15b
0x18005bd62  jz      loc_18005C100
0x18005bd68  mov     rcx, rdi; hKey
0x18005bd6b  call    cs:__imp_RegFlushKey
0x18005bd71  test    eax, eax
0x18005bd73  jz      loc_18005C100
0x18005bd79  jle     short loc_18005BD80
0x18005bd7b  movzx   eax, ax
0x18005bd7e  or      eax, ebx
0x18005bd80  lea     r9, aRegstoredidFlu; "regStoredId.Flush failed with error=0x%"...
0x18005bd87  mov     r8d, 380h
0x18005bd8d  jmp     loc_18005C0EF
0x18005bd92  xor     r9d, r9d; unsigned __int16 *
0x18005bd95  test    rdi, rdi
0x18005bd98  jnz     short loc_18005BDCB
0x18005bd9a  mov     [rsp+150h+var_118], r12; unsigned int *
0x18005bd9f  mov     [rsp+150h+pExtendedParemeter], r12; LPSECURITY_ATTRIBUTES
0x18005bda4  mov     dword ptr [rsp+150h+hTransaction], 2001Fh; REGSAM
0x18005bdac  mov     dword ptr [rsp+150h+phkResult], r12d; DWORD
0x18005bdb1  mov     r8, [rsp+150h+lpSubKey]; lpSubKey
0x18005bdb6  mov     rdx, [rbp+50h+hKey]; hKey
0x18005bdba  lea     rcx, [rsp+150h+var_E8]; this
0x18005bdbf  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18005bdc4  mov     r14, [rsp+150h+var_E8]
0x18005bdc9  jmp     short loc_18005BE14
0x18005bdcb  mov     [rsp+150h+var_100], r12; pExtendedParemeter
0x18005bdd0  mov     [rsp+150h+var_108], rdi; hTransaction
0x18005bdd5  mov     [rsp+150h+lpdwDisposition], r12; lpdwDisposition
0x18005bdda  lea     rax, [rbp+50h+arg_18]
0x18005bdde  mov     [rsp+150h+var_118], rax; phkResult
0x18005bde3  mov     [rsp+150h+pExtendedParemeter], r12; lpSecurityAttributes
0x18005bde8  mov     dword ptr [rsp+150h+hTransaction], 2001Fh; samDesired
0x18005bdf0  mov     dword ptr [rsp+150h+phkResult], r12d; dwOptions
0x18005bdf5  xor     r8d, r8d; Reserved
0x18005bdf8  mov     rdx, [rsp+150h+lpSubKey]; lpSubKey
0x18005bdfd  mov     rcx, [rbp+50h+hKey]; hKey
0x18005be01  call    cs:__imp_RegCreateKeyTransactedW
0x18005be07  mov     r14, [rbp+50h+arg_18]
0x18005be0b  mov     [rsp+150h+var_E8], r14
0x18005be10  mov     [rbp+50h+arg_18], r12
0x18005be14  mov     r9d, eax
0x18005be17  mov     ebx, 80070000h
0x18005be1c  test    eax, eax
0x18005be1e  jz      short loc_18005BE3D
0x18005be20  jle     short loc_18005BE29
0x18005be22  movzx   r9d, r9w
0x18005be26  or      r9d, ebx
0x18005be29  mov     [rbp+50h+arg_0], r9d
0x18005be2d  test    r9d, r9d
0x18005be30  jns     short loc_18005BE3D
0x18005be32  mov     r8d, 393h
0x18005be38  jmp     loc_18005BD10
0x18005be3d  mov     r8d, 1
0x18005be43  lea     rdx, [rsp+150h+var_E8]
0x18005be48  mov     rcx, rsi
0x18005be4b  call    ?SaveProperties@CStoredIdentity@@AEAAJAEAVCRegKey@ATL@@W4PropertyScope@@@Z; CStoredIdentity::SaveProperties(ATL::CRegKey &,PropertyScope)
0x18005be50  mov     [rbp+50h+arg_0], eax
0x18005be53  test    eax, eax
0x18005be55  jns     short loc_18005BE71
0x18005be57  lea     rcx, aHrSaveproperti_0; "hr = SaveProperties(regIdKey, eGlobal)"
0x18005be5e  mov     [rsp+150h+phkResult], rcx
0x18005be63  mov     r9d, eax
0x18005be66  mov     r8d, 395h
0x18005be6c  jmp     loc_18005BD1C
0x18005be71  mov     rcx, rsi; this
0x18005be74  call    ?ValidateSystemAccount@CStoredIdentity@@AEAAHXZ; CStoredIdentity::ValidateSystemAccount(void)
0x18005be79  test    eax, eax
0x18005be7b  jz      loc_18005BFC0
0x18005be81  xor     edx, edx
0x18005be83  call    ?HasAnyKeyword@CStoredIdentity@@QEAAHW4PropertyScope@@@Z; CStoredIdentity::HasAnyKeyword(PropertyScope)
0x18005be88  mov     rdx, [rsi+20h]; unsigned __int16 *
0x18005be8c  test    eax, eax
0x18005be8e  jnz     short loc_18005BEF6
0x18005be90  test    rdi, rdi
0x18005be93  jnz     short loc_18005BEA6
0x18005be95  lea     rcx, [rsp+150h+var_E8]; this
0x18005be9a  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18005be9f  mov     r14, [rsp+150h+var_E8]
0x18005bea4  jmp     short loc_18005BEBF
0x18005bea6  mov     [rsp+150h+hTransaction], r12; pExtendedParameter
0x18005beab  mov     [rsp+150h+phkResult], rdi; hTransaction
0x18005beb0  xor     r9d, r9d; Reserved
0x18005beb3  xor     r8d, r8d; samDesired
0x18005beb6  mov     rcx, r14; hKey
0x18005beb9  call    cs:__imp_RegDeleteKeyTransactedW
0x18005bebf  mov     r9d, eax
0x18005bec2  test    eax, 0FFFFFFFCh
0x18005bec7  jnz     short loc_18005BED2
0x18005bec9  cmp     eax, 1
0x18005becc  jnz     loc_18005BFC0
0x18005bed2  test    r9d, r9d
0x18005bed5  jle     short loc_18005BEDE
0x18005bed7  movzx   r9d, r9w
0x18005bedb  or      r9d, ebx
0x18005bede  mov     [rbp+50h+arg_0], r9d
0x18005bee2  test    r9d, r9d
0x18005bee5  jns     loc_18005BFC0
0x18005beeb  mov     r8d, 3A7h
0x18005bef1  jmp     loc_18005BD10
0x18005bef6  xor     r9d, r9d; unsigned __int16 *
0x18005bef9  test    rdi, rdi
0x18005befc  jnz     short loc_18005BF29
0x18005befe  mov     [rsp+150h+var_118], r12; unsigned int *
0x18005bf03  mov     [rsp+150h+pExtendedParemeter], r12; LPSECURITY_ATTRIBUTES
0x18005bf08  mov     dword ptr [rsp+150h+hTransaction], 2001Fh; REGSAM
0x18005bf10  mov     dword ptr [rsp+150h+phkResult], r12d; DWORD
0x18005bf15  mov     r8, rdx; lpSubKey
0x18005bf18  mov     rdx, r14; hKey
0x18005bf1b  lea     rcx, [rbp+50h+var_B8]; this
0x18005bf1f  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18005bf24  mov     r9d, eax
0x18005bf27  jmp     short loc_18005BF6E
0x18005bf29  mov     [rsp+150h+var_100], r12; pExtendedParemeter
0x18005bf2e  mov     [rsp+150h+var_108], rdi; hTransaction
0x18005bf33  mov     [rsp+150h+lpdwDisposition], r12; lpdwDisposition
0x18005bf38  lea     rax, [rbp+50h+arg_18]
0x18005bf3c  mov     [rsp+150h+var_118], rax; phkResult
0x18005bf41  mov     [rsp+150h+pExtendedParemeter], r12; lpSecurityAttributes
0x18005bf46  mov     dword ptr [rsp+150h+hTransaction], 2001Fh; samDesired
0x18005bf4e  mov     dword ptr [rsp+150h+phkResult], r12d; dwOptions
0x18005bf53  xor     r8d, r8d; Reserved
0x18005bf56  mov     rcx, r14; hKey
0x18005bf59  call    cs:__imp_RegCreateKeyTransactedW
0x18005bf5f  mov     r9d, eax
0x18005bf62  mov     rax, [rbp+50h+arg_18]
0x18005bf66  mov     [rbp+50h+var_B8], rax
0x18005bf6a  mov     [rbp+50h+arg_18], r12
0x18005bf6e  test    r9d, r9d
0x18005bf71  jz      short loc_18005BF90
0x18005bf73  jle     short loc_18005BF7C
0x18005bf75  movzx   r9d, r9w
0x18005bf79  or      r9d, ebx
0x18005bf7c  mov     [rbp+50h+arg_0], r9d
0x18005bf80  test    r9d, r9d
0x18005bf83  jns     short loc_18005BF90
0x18005bf85  mov     r8d, 3B9h
0x18005bf8b  jmp     loc_18005BD10
  ... truncated ...
```
