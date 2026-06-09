# CSettings::LoadSettings(wchar_t const *,wchar_t const *,_WER_CONSENT)

- ea: `0x18000c504`
- end: `0x18000cb13`
- name: `?LoadSettings@CSettings@@QEAAJPEB_W0W4_WER_CONSENT@@@Z`
- size: `1551`
- prototype: `__int64 __fastcall(CSettings *__hidden this, const wchar_t *, const wchar_t *, enum _WER_CONSENT)`
- caller_count: `12`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ac40`
- `0x180033030`
- `0x180046150`
- `0x18004d05c`
- `0x180068718`
- `0x180069500`
- `0x18006baf0`
- `0x18006cc20`
- `0x18006d080`
- `0x18006d360`
- `0x18006df10`
- `0x1800754b4`

## callees

- `0x18000ad98`
- `0x18000c504`
- `0x18000cb20`
- `0x18000cb80`
- `0x18000da00`
- `0x18000ee6c`
- `0x18001c044`
- `0x18002219c`
- `0x18002a0f4`
- `0x18006499c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ca2b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ca2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c6b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c72f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c7af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c916`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c971`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ca5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000caf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c6b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c72f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c7af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c916`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c971`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ca5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000caf0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c6e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c754`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c7db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c839`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c948`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c996`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c9f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c6e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c754`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c7db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c839`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c948`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c996`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c9f1`

## string_xrefs

- `0x18000c563`: `BrokerUp`

## pseudocode

```c
__int64 __fastcall CSettings::LoadSettings(CSettings *this, const wchar_t *a2, const wchar_t *a3, enum _WER_CONSENT a4)
{
  HKEY v4; // r14
  const wchar_t *v7; // rax
  const wchar_t *v8; // r8
  __int64 v9; // rdx
  CSettings *v10; // rcx
  unsigned int i; // esi
  int v12; // edi
  unsigned int j; // esi
  HKEY v14; // rcx
  unsigned int v15; // r8d
  unsigned int *v16; // r9
  HKEY v17; // rcx
  CRegSetting *v18; // rdi
  bool v19; // zf
  _BYTE *v20; // rsi
  unsigned int v21; // r8d
  unsigned int *v22; // r9
  unsigned int DwordData; // eax
  HKEY v24; // rcx
  unsigned int v25; // r8d
  unsigned int *v26; // r9
  HKEY v27; // rcx
  HKEY v28; // rsi
  __int64 k; // rdi
  unsigned int m; // esi
  int v31; // r15d
  __int64 v32; // r12
  __int64 v33; // rdi
  char v34; // al
  HKEY v35; // rcx
  unsigned int v36; // r8d
  unsigned int *v37; // r9
  HKEY v38; // rcx
  __int64 v39; // rdx
  unsigned int v40; // r8d
  unsigned int *v41; // r9
  LSTATUS v42; // eax
  bool v43; // sf
  bool v44; // cc
  LSTATUS ValueW; // eax
  int v46; // edi
  unsigned int DWORD; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-A9h]
  unsigned int phkResulta; // [rsp+20h] [rbp-A9h]
  unsigned int phkResultb; // [rsp+20h] [rbp-A9h]
  unsigned int phkResultc; // [rsp+20h] [rbp-A9h]
  unsigned int phkResultd; // [rsp+20h] [rbp-A9h]
  bool pvData; // [rsp+28h] [rbp-A1h]
  bool pvDataa; // [rsp+28h] [rbp-A1h]
  _DWORD v56[2]; // [rsp+40h] [rbp-89h]
  const wchar_t *v57; // [rsp+48h] [rbp-81h]
  const wchar_t *v58; // [rsp+50h] [rbp-79h]
  _DWORD v59[2]; // [rsp+58h] [rbp-71h]
  __int64 v60; // [rsp+60h] [rbp-69h]
  int v61; // [rsp+68h] [rbp-61h]
  const wchar_t *v62; // [rsp+70h] [rbp-59h]
  const wchar_t *v63; // [rsp+78h] [rbp-51h]
  int v64; // [rsp+80h] [rbp-49h]
  __int64 v65; // [rsp+88h] [rbp-41h]
  int v66; // [rsp+90h] [rbp-39h]
  const wchar_t *v67; // [rsp+98h] [rbp-31h]
  const wchar_t *v68; // [rsp+A0h] [rbp-29h]
  int v69; // [rsp+A8h] [rbp-21h]
  __int64 v70; // [rsp+B0h] [rbp-19h]
  int v71; // [rsp+B8h] [rbp-11h]
  const wchar_t *v72; // [rsp+C0h] [rbp-9h]
  const wchar_t *v73; // [rsp+C8h] [rbp-1h]
  int v74; // [rsp+D0h] [rbp+7h]
  __int64 v75; // [rsp+D8h] [rbp+Fh]
  DWORD pcbData; // [rsp+130h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+138h] [rbp+6Fh] BYREF
  HKEY hkey; // [rsp+140h] [rbp+77h] BYREF
  int v79; // [rsp+148h] [rbp+7Fh] BYREF

  v4 = 0;
  hKey = 0;
  v7 = 0;
  if ( a3 )
  {
    v7 = UtilPathTail(a3);
    if ( !v7 )
      v7 = v8;
  }
  v63 = v7;
  v57 = L"Consent";
  v9 = 0;
  v68 = v7;
  v62 = L"ExcludedApplications";
  v56[0] = 0;
  v67 = L"DebugApplications";
  v10 = 0;
  v58 = a2;
  v59[0] = 4;
  v60 = 1;
  v61 = 9;
  v64 = 13;
  v65 = 0;
  v66 = 0;
  v69 = 14;
  v70 = 0;
  v71 = 0;
  v72 = L"BrokerUp";
  v73 = a2;
  v74 = 22;
  v75 = 0;
  *((_DWORD *)this + 1275) = 1;
  *((_DWORD *)this + 1274) = a4;
  do
  {
    ++v9;
    *(_QWORD *)((char *)v10 + (_QWORD)this + 16) = *(_QWORD *)((char *)v10 + (_QWORD)this + 8);
    *(_WORD *)((char *)v10 + (_QWORD)this) = 0;
    *(_QWORD *)((char *)v10 + (_QWORD)this + 96) = 0;
    v10 = (CSettings *)((char *)v10 + 104);
  }
  while ( v9 != 49 );
  for ( i = 0; i < 0xF; ++i )
  {
    v12 = CRegSetting::Initialize(
            (char *)this + 104 * (unsigned int)dword_1800B49D8[10 * i],
            *((unsigned int *)&CSettings::allHiveSettings + 10 * i),
            *((_QWORD *)&off_1800B49C8 + 5 * i));
    if ( v12 < 0 )
      goto LABEL_62;
  }
  for ( j = 0; j < 4; ++j )
  {
    if ( *(_QWORD *)&v59[10 * j - 2] )
    {
      v12 = CRegSetting::Initialize(
              (char *)this + 104 * (unsigned int)v59[10 * j],
              (unsigned int)v56[10 * j],
              (&v57)[5 * j]);
      if ( v12 < 0 )
        goto LABEL_62;
    }
  }
  CSettings::CreatePerUserDefaultConsent(v10);
  v14 = hKey;
  hKey = 0;
  if ( v14 )
    RegCloseKey(v14);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
          0,
          0x20119u,
          &hKey) )
    CRegSetting::Load(hKey, this, v15, v16, phkResult);
  v17 = hKey;
  v18 = (CSettings *)((char *)this + 208);
  v19 = *((_BYTE *)this + 208) == 0;
  v20 = (char *)this + 104;
  hKey = 0;
  *((_BYTE *)this + 5108) = v19;
  *((_BYTE *)this + 5109) = *((_BYTE *)this + 104) == 0;
  if ( v17 )
    RegCloseKey(v17);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\Windows Error Reporting", 0, 0x20119u, &hKey) )
    CRegSetting::Load(hKey, this, v21, v22, phkResulta);
  *((_DWORD *)this + 1278) = CRegSetting::GetDwordData(v18);
  DwordData = CRegSetting::GetDwordData((CSettings *)((char *)this + 104));
  v24 = hKey;
  hKey = 0;
  *((_BYTE *)this + 5110) = DwordData == 1;
  *((_BYTE *)this + 5106) = *(_BYTE *)v18;
  *((_BYTE *)this + 5107) = *v20;
  if ( v24 )
    RegCloseKey(v24);
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
          0,
          0x20119u,
          &hKey) )
    CRegSetting::Load(hKey, this, v25, v26, phkResultb);
  v27 = hKey;
  *((_BYTE *)this + 5104) = *(_BYTE *)v18;
  *((_BYTE *)this + 5105) = *v20;
  hKey = 0;
  if ( v27 )
    RegCloseKey(v27);
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\Windows Error Reporting", 0, 0x20119u, &hKey) )
  {
    v28 = hKey;
    for ( k = 0; k != 49; ++k )
      CRegSetting::Load((CSettings *)((char *)this + 104 * k), v28, 0x100u);
  }
  for ( m = 0; m < 0x1E; ++m )
  {
    v4 = (HKEY)(&off_1800B4C30)[5 * m];
    if ( v4 )
    {
      v31 = *((_DWORD *)&CSettings::adminSettings + 10 * m);
      v32 = qword_1800B4C40[5 * m];
      v33 = 104LL * (unsigned int)dword_1800B4C38[10 * m];
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               (char *)this + v33 + 32,
                               *((void **)&off_1800B4C28 + 5 * m))
        || (v34 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                    (char *)this + v33 + 64,
                    v4),
            v4 = 0,
            !v34) )
      {
        v12 = -2147467259;
        goto LABEL_62;
      }
      *(_QWORD *)((char *)this + v33 + 16) = *(_QWORD *)((char *)this + v33 + 8);
      *(_WORD *)((char *)this + v33) = 256;
      *(_DWORD *)((char *)this + v33 + 4) = v31;
      *(_QWORD *)((char *)this + v33 + 96) = v32;
    }
  }
  v35 = hKey;
  hKey = v4;
  if ( v35 )
    RegCloseKey(v35);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
          0,
          0x20119u,
          &hKey) )
    CRegSetting::Load(hKey, this, v36, v37, phkResultc);
  v38 = hKey;
  hKey = v4;
  if ( v38 )
    RegCloseKey(v38);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\Windows Error Reporting", 0, 0x20119u, &hKey) )
    CRegSetting::Load(hKey, this, v40, v41, phkResultd);
  LOBYTE(v39) = a2 != 0;
  *((_DWORD *)this + 1275) = CSettings::ComputeConsent(this, v39);
  v79 = (int)v4;
  pcbData = 4;
  hkey = v4;
  v42 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\SQMClient", 0, 0x101u, &hkey);
  v43 = v42 < 0;
  v44 = v42 <= 0;
  if ( !v42 )
  {
    ValueW = RegGetValueW(hkey, 0, L"MSFTInternal", 0x10u, (LPDWORD)v4, &v79, &pcbData);
    v43 = ValueW < 0;
    v44 = ValueW <= 0;
    if ( !ValueW )
      goto LABEL_54;
  }
  if ( !v44 )
    v43 = 1;
  if ( v43 )
  {
    v46 = (int)v4;
    v79 = (int)v4;
  }
  else
  {
LABEL_54:
    v46 = v79;
  }
  if ( hkey )
    RegCloseKey(hkey);
  *((_DWORD *)this + 1279) = v46;
  if ( !v46 )
    *((_DWORD *)this + 1279) = UtilRegGetDWORD(
                                 HKEY_LOCAL_MACHINE,
                                 L"SOFTWARE\\Microsoft\\SQMClient",
                                 L"MSFTInternal",
                                 0,
                                 (bool *)v4,
                                 pvData);
  DWORD = UtilRegGetDWORD(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Policies\\Microsoft\\SQMClient",
            L"IsTest",
            0,
            (bool *)v4,
            pvData);
  *((_DWORD *)this + 1280) = DWORD;
  if ( !DWORD )
    *((_DWORD *)this + 1280) = UtilRegGetDWORD(
                                 HKEY_LOCAL_MACHINE,
                                 L"SOFTWARE\\Microsoft\\SQMClient",
                                 L"IsTest",
                                 0,
                                 (bool *)v4,
                                 pvDataa);
  v12 = (int)v4;
LABEL_62:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000c504  push    rbp
0x18000c506  push    rbx
0x18000c507  push    rsi
0x18000c508  push    rdi
0x18000c509  push    r12
0x18000c50b  push    r13
0x18000c50d  push    r14
0x18000c50f  push    r15
0x18000c511  lea     rbp, [rsp-1Fh]
0x18000c516  sub     rsp, 0E8h
0x18000c51d  xor     r14d, r14d
0x18000c520  mov     r13, rdx
0x18000c523  mov     [rbp+57h+hKey], r14
0x18000c527  mov     rbx, rcx
0x18000c52a  mov     eax, r14d
0x18000c52d  test    r8, r8
0x18000c530  jz      short loc_18000C541
0x18000c532  mov     rcx, r8; wchar_t *
0x18000c535  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x18000c53a  test    rax, rax
0x18000c53d  cmovz   rax, r8
0x18000c541  lea     rcx, aConsent; "Consent"
0x18000c548  mov     [rbp+57h+var_A8], rax
0x18000c54c  mov     [rsp+120h+var_D8], rcx
0x18000c551  mov     rdx, r14
0x18000c554  lea     rcx, aExcludedapplic; "ExcludedApplications"
0x18000c55b  mov     [rbp+57h+var_80], rax
0x18000c55f  mov     [rbp+57h+var_B0], rcx
0x18000c563  lea     rax, aBrokerup; "BrokerUp"
0x18000c56a  lea     rcx, aDebugapplicati; "DebugApplications"
0x18000c571  mov     [rsp+120h+var_E0], r14d
0x18000c576  mov     [rbp+57h+var_88], rcx
0x18000c57a  mov     rcx, r14
0x18000c57d  mov     [rbp+57h+var_D0], r13
0x18000c581  mov     [rbp+57h+var_C8], 4
0x18000c588  mov     [rbp+57h+var_C0], 1
0x18000c590  mov     [rbp+57h+var_B8], 9
0x18000c597  mov     [rbp+57h+var_A0], 0Dh
0x18000c59e  mov     [rbp+57h+var_98], r14
0x18000c5a2  mov     [rbp+57h+var_90], r14d
0x18000c5a6  mov     [rbp+57h+var_78], 0Eh
0x18000c5ad  mov     [rbp+57h+var_70], r14
0x18000c5b1  mov     [rbp+57h+var_68], r14d
0x18000c5b5  mov     [rbp+57h+var_60], rax
0x18000c5b9  mov     [rbp+57h+var_58], r13
0x18000c5bd  mov     [rbp+57h+var_50], 16h
0x18000c5c4  mov     [rbp+57h+var_48], r14
0x18000c5c8  mov     dword ptr [rbx+13ECh], 1
0x18000c5d2  mov     [rbx+13E8h], r9d
0x18000c5d9  mov     rax, [rbx+rcx+8]
0x18000c5de  inc     rdx
0x18000c5e1  mov     [rbx+rcx+10h], rax
0x18000c5e6  mov     [rbx+rcx], r14w
0x18000c5eb  mov     [rbx+rcx+60h], r14
0x18000c5f0  lea     rcx, [rcx+68h]; this
0x18000c5f4  cmp     rdx, 31h ; '1'
0x18000c5f8  jnz     short loc_18000C5D9
0x18000c5fa  mov     esi, r14d
0x18000c5fd  lea     r10, __ImageBase
0x18000c604  cmp     esi, 0Fh
0x18000c607  jnb     short loc_18000C656
0x18000c609  mov     eax, esi
0x18000c60b  lea     rdx, [rax+rax*4]
0x18000c60f  mov     eax, ds:rva dword_1800B49D8[r10+rdx*8]
0x18000c617  mov     r9, ds:rva off_1800B49D0[r10+rdx*8]; "DontSendAdditionalData" ...
0x18000c61f  mov     r8, ds:rva off_1800B49C8[r10+rdx*8]
0x18000c627  imul    rcx, rax, 68h ; 'h'
0x18000c62b  mov     rax, ds:rva qword_1800B49E0[r10+rdx*8]
0x18000c633  mov     edx, ds:rva ?allHiveSettings@CSettings@@0QBUSETTING@1@B[r10+rdx*8]; CSettings::SETTING const near * const CSettings::allHiveSettings ...
0x18000c63b  add     rcx, rbx
0x18000c63e  mov     [rsp+120h+phkResult], rax
0x18000c643  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x18000c648  mov     edi, eax
0x18000c64a  test    eax, eax
0x18000c64c  js      loc_18000CAE7
0x18000c652  inc     esi
0x18000c654  jmp     short loc_18000C5FD
0x18000c656  mov     esi, r14d
0x18000c659  cmp     esi, 4
0x18000c65c  jnb     short loc_18000C69F
0x18000c65e  mov     eax, esi
0x18000c660  lea     rdx, [rax+rax*4]
0x18000c664  mov     r9, [rbp+rdx*8+57h+var_D0]
0x18000c669  test    r9, r9
0x18000c66c  jz      short loc_18000C69B
0x18000c66e  mov     eax, [rbp+rdx*8+57h+var_C8]
0x18000c672  mov     r8, [rsp+rdx*8+120h+var_D8]
0x18000c677  imul    rcx, rax, 68h ; 'h'
0x18000c67b  mov     rax, [rbp+rdx*8+57h+var_C0]
0x18000c680  mov     edx, [rsp+rdx*8+120h+var_E0]
0x18000c684  add     rcx, rbx
0x18000c687  mov     [rsp+120h+phkResult], rax
0x18000c68c  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x18000c691  mov     edi, eax
0x18000c693  test    eax, eax
0x18000c695  js      loc_18000CAE7
0x18000c69b  inc     esi
0x18000c69d  jmp     short loc_18000C659
0x18000c69f  call    ?CreatePerUserDefaultConsent@CSettings@@AEAAJXZ; CSettings::CreatePerUserDefaultConsent(void)
0x18000c6a4  mov     rcx, [rbp+57h+hKey]; hKey
0x18000c6a8  mov     [rbp+57h+hKey], r14
0x18000c6ac  test    rcx, rcx
0x18000c6af  jz      short loc_18000C6BD
0x18000c6b1  call    cs:__imp_RegCloseKey
0x18000c6b8  nop     dword ptr [rax+rax+00h]
0x18000c6bd  lea     rax, [rbp+57h+hKey]
0x18000c6c1  mov     r12d, 20119h
0x18000c6c7  mov     r15, 0FFFFFFFF80000002h
0x18000c6ce  mov     [rsp+120h+phkResult], rax; unsigned int
0x18000c6d3  mov     r9d, r12d; samDesired
0x18000c6d6  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x18000c6dd  mov     rcx, r15; hKey
0x18000c6e0  xor     r8d, r8d; ulOptions
0x18000c6e3  call    cs:__imp_RegOpenKeyExW
0x18000c6ea  nop     dword ptr [rax+rax+00h]
0x18000c6ef  test    eax, eax
0x18000c6f1  jnz     short loc_18000C6FF
0x18000c6f3  mov     rcx, [rbp+57h+hKey]; HKEY
0x18000c6f7  mov     rdx, rbx; struct CRegSetting *
0x18000c6fa  call    ?Load@CRegSetting@@SAJPEAUHKEY__@@QEAV1@KPEAKK@Z; CRegSetting::Load(HKEY__ *,CRegSetting * const,ulong,ulong *,ulong)
0x18000c6ff  mov     rcx, [rbp+57h+hKey]; hKey
0x18000c703  lea     rdi, [rbx+0D0h]
0x18000c70a  cmp     [rdi], r14b
0x18000c70d  lea     rsi, [rbx+68h]
0x18000c711  mov     [rbp+57h+hKey], r14
0x18000c715  setz    al
0x18000c718  mov     [rbx+13F4h], al
0x18000c71e  cmp     [rsi], r14b
0x18000c721  setz    al
0x18000c724  mov     [rbx+13F5h], al
0x18000c72a  test    rcx, rcx
0x18000c72d  jz      short loc_18000C73B
0x18000c72f  call    cs:__imp_RegCloseKey
0x18000c736  nop     dword ptr [rax+rax+00h]
0x18000c73b  lea     rax, [rbp+57h+hKey]
0x18000c73f  mov     r9d, r12d; samDesired
0x18000c742  xor     r8d, r8d; ulOptions
0x18000c745  mov     [rsp+120h+phkResult], rax; unsigned int
0x18000c74a  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\Windows E"...
0x18000c751  mov     rcx, r15; hKey
0x18000c754  call    cs:__imp_RegOpenKeyExW
0x18000c75b  nop     dword ptr [rax+rax+00h]
0x18000c760  test    eax, eax
0x18000c762  jnz     short loc_18000C770
0x18000c764  mov     rcx, [rbp+57h+hKey]; HKEY
0x18000c768  mov     rdx, rbx; struct CRegSetting *
0x18000c76b  call    ?Load@CRegSetting@@SAJPEAUHKEY__@@QEAV1@KPEAKK@Z; CRegSetting::Load(HKEY__ *,CRegSetting * const,ulong,ulong *,ulong)
0x18000c770  mov     rcx, rdi; this
0x18000c773  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18000c778  mov     rcx, rsi; this
0x18000c77b  mov     [rbx+13F8h], eax
0x18000c781  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18000c786  mov     rcx, [rbp+57h+hKey]; hKey
0x18000c78a  cmp     eax, 1
0x18000c78d  mov     [rbp+57h+hKey], r14
0x18000c791  setz    al
0x18000c794  mov     [rbx+13F6h], al
0x18000c79a  mov     al, [rdi]
0x18000c79c  mov     [rbx+13F2h], al
0x18000c7a2  mov     al, [rsi]
0x18000c7a4  mov     [rbx+13F3h], al
0x18000c7aa  test    rcx, rcx
0x18000c7ad  jz      short loc_18000C7BB
0x18000c7af  call    cs:__imp_RegCloseKey
0x18000c7b6  nop     dword ptr [rax+rax+00h]
0x18000c7bb  lea     rax, [rbp+57h+hKey]
0x18000c7bf  mov     r15, 0FFFFFFFF80000001h
0x18000c7c6  mov     rcx, r15; hKey
0x18000c7c9  mov     [rsp+120h+phkResult], rax; unsigned int
0x18000c7ce  mov     r9d, r12d; samDesired
0x18000c7d1  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x18000c7d8  xor     r8d, r8d; ulOptions
0x18000c7db  call    cs:__imp_RegOpenKeyExW
0x18000c7e2  nop     dword ptr [rax+rax+00h]
0x18000c7e7  test    eax, eax
0x18000c7e9  jnz     short loc_18000C7F7
0x18000c7eb  mov     rcx, [rbp+57h+hKey]; HKEY
0x18000c7ef  mov     rdx, rbx; struct CRegSetting *
0x18000c7f2  call    ?Load@CRegSetting@@SAJPEAUHKEY__@@QEAV1@KPEAKK@Z; CRegSetting::Load(HKEY__ *,CRegSetting * const,ulong,ulong *,ulong)
0x18000c7f7  mov     al, [rdi]
0x18000c7f9  mov     rcx, [rbp+57h+hKey]; hKey
0x18000c7fd  mov     [rbx+13F0h], al
0x18000c803  mov     al, [rsi]
0x18000c805  mov     [rbx+13F1h], al
0x18000c80b  mov     [rbp+57h+hKey], r14
0x18000c80f  test    rcx, rcx
0x18000c812  jz      short loc_18000C820
0x18000c814  call    cs:__imp_RegCloseKey
0x18000c81b  nop     dword ptr [rax+rax+00h]
0x18000c820  lea     rax, [rbp+57h+hKey]
0x18000c824  mov     r9d, r12d; samDesired
0x18000c827  xor     r8d, r8d; ulOptions
0x18000c82a  mov     [rsp+120h+phkResult], rax; phkResult
0x18000c82f  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\Windows E"...
0x18000c836  mov     rcx, r15; hKey
0x18000c839  call    cs:__imp_RegOpenKeyExW
0x18000c840  nop     dword ptr [rax+rax+00h]
0x18000c845  test    eax, eax
0x18000c847  jnz     short loc_18000C86E
0x18000c849  mov     rsi, [rbp+57h+hKey]
0x18000c84d  mov     rdi, r14
0x18000c850  imul    rcx, rdi, 68h ; 'h'
0x18000c854  mov     r8d, 100h; unsigned int
0x18000c85a  mov     rdx, rsi; HKEY
0x18000c85d  add     rcx, rbx; this
0x18000c860  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x18000c865  inc     rdi
0x18000c868  cmp     rdi, 31h ; '1'
0x18000c86c  jnz     short loc_18000C850
0x18000c86e  mov     esi, r14d
0x18000c871  cmp     esi, 1Eh
0x18000c874  jnb     loc_18000C909
0x18000c87a  mov     eax, esi
0x18000c87c  lea     r8, __ImageBase
0x18000c883  lea     rdx, [rax+rax*4]
0x18000c887  mov     r14, ds:rva off_1800B4C30[r8+rdx*8]; "DisableArchive" ...
0x18000c88f  test    r14, r14
0x18000c892  jz      short loc_18000C8F8
0x18000c894  mov     eax, ds:rva dword_1800B4C38[r8+rdx*8]
0x18000c89c  lea     rcx, [rbx+20h]
0x18000c8a0  mov     r15d, ds:rva ?adminSettings@CSettings@@0QBUSETTING@1@B[r8+rdx*8]; CSettings::SETTING const near * const CSettings::adminSettings ...
0x18000c8a8  mov     r12, ds:rva qword_1800B4C40[r8+rdx*8]
0x18000c8b0  mov     rdx, ds:rva off_1800B4C28[r8+rdx*8]
0x18000c8b8  imul    rdi, rax, 68h ; 'h'
0x18000c8bc  add     rcx, rdi
0x18000c8bf  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18000c8c4  test    al, al
0x18000c8c6  jz      short loc_18000C8FF
0x18000c8c8  lea     rcx, [rbx+40h]
0x18000c8cc  mov     rdx, r14
0x18000c8cf  add     rcx, rdi
0x18000c8d2  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18000c8d7  xor     r14d, r14d
0x18000c8da  test    al, al
0x18000c8dc  jz      short loc_18000C8FF
0x18000c8de  mov     rax, [rdi+rbx+8]
0x18000c8e3  mov     [rdi+rbx+10h], rax
0x18000c8e8  mov     word ptr [rdi+rbx], 100h
0x18000c8ee  mov     [rdi+rbx+4], r15d
0x18000c8f3  mov     [rdi+rbx+60h], r12
0x18000c8f8  inc     esi
0x18000c8fa  jmp     loc_18000C871
0x18000c8ff  mov     edi, 80004005h
0x18000c904  jmp     loc_18000CAE7
0x18000c909  mov     rcx, [rbp+57h+hKey]; hKey
0x18000c90d  mov     [rbp+57h+hKey], r14
0x18000c911  test    rcx, rcx
0x18000c914  jz      short loc_18000C922
0x18000c916  call    cs:__imp_RegCloseKey
0x18000c91d  nop     dword ptr [rax+rax+00h]
0x18000c922  lea     rax, [rbp+57h+hKey]
0x18000c926  mov     r12d, 20119h
0x18000c92c  mov     r15, 0FFFFFFFF80000002h
0x18000c933  mov     [rsp+120h+phkResult], rax; unsigned int
0x18000c938  mov     r9d, r12d; samDesired
0x18000c93b  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x18000c942  mov     rcx, r15; hKey
0x18000c945  xor     r8d, r8d; ulOptions
0x18000c948  call    cs:__imp_RegOpenKeyExW
0x18000c94f  nop     dword ptr [rax+rax+00h]
0x18000c954  test    eax, eax
0x18000c956  jnz     short loc_18000C964
0x18000c958  mov     rcx, [rbp+57h+hKey]; HKEY
0x18000c95c  mov     rdx, rbx; struct CRegSetting *
0x18000c95f  call    ?Load@CRegSetting@@SAJPEAUHKEY__@@QEAV1@KPEAKK@Z; CRegSetting::Load(HKEY__ *,CRegSetting * const,ulong,ulong *,ulong)
0x18000c964  mov     rcx, [rbp+57h+hKey]; hKey
0x18000c968  mov     [rbp+57h+hKey], r14
0x18000c96c  test    rcx, rcx
0x18000c96f  jz      short loc_18000C97D
0x18000c971  call    cs:__imp_RegCloseKey
0x18000c978  nop     dword ptr [rax+rax+00h]
0x18000c97d  lea     rax, [rbp+57h+hKey]
0x18000c981  mov     r9d, r12d; samDesired
0x18000c984  xor     r8d, r8d; ulOptions
0x18000c987  mov     [rsp+120h+phkResult], rax; unsigned int
0x18000c98c  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\Windows E"...
0x18000c993  mov     rcx, r15; hKey
0x18000c996  call    cs:__imp_RegOpenKeyExW
0x18000c99d  nop     dword ptr [rax+rax+00h]
0x18000c9a2  test    eax, eax
0x18000c9a4  jnz     short loc_18000C9B2
0x18000c9a6  mov     rcx, [rbp+57h+hKey]; HKEY
0x18000c9aa  mov     rdx, rbx; struct CRegSetting *
0x18000c9ad  call    ?Load@CRegSetting@@SAJPEAUHKEY__@@QEAV1@KPEAKK@Z; CRegSetting::Load(HKEY__ *,CRegSetting * const,ulong,ulong *,ulong)
0x18000c9b2  test    r13, r13
0x18000c9b5  mov     rcx, rbx
0x18000c9b8  setnz   dl
0x18000c9bb  call    ?ComputeConsent@CSettings@@AEBA?AW4_CONSENT_SETTING@@_N@Z; CSettings::ComputeConsent(bool)
0x18000c9c0  mov     [rbx+13ECh], eax
0x18000c9c6  lea     rdx, aSoftwarePolici_1; "SOFTWARE\\Policies\\Microsoft\\SQMClien"...
0x18000c9cd  lea     rax, [rbp+57h+hkey]
0x18000c9d1  mov     [rbp+57h+arg_18], r14d
0x18000c9d5  mov     r9d, 101h; samDesired
0x18000c9db  mov     [rsp+120h+phkResult], rax; phkResult
0x18000c9e0  xor     r8d, r8d; ulOptions
0x18000c9e3  mov     [rbp+57h+arg_0], 4
0x18000c9ea  mov     rcx, r15; hKey
0x18000c9ed  mov     [rbp+57h+hkey], r14
0x18000c9f1  call    cs:__imp_RegOpenKeyExW
0x18000c9f8  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
