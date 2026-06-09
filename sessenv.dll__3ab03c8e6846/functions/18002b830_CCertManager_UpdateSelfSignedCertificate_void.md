# CCertManager::UpdateSelfSignedCertificate(void)

- ea: `0x18002b830`
- end: `0x18002c3c0`
- name: `?UpdateSelfSignedCertificate@CCertManager@@AEAAJXZ`
- size: `2960`
- prototype: `__int64 __fastcall(CCertManager *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800033e0`

## callees

- `0x1800013a4`
- `0x180003f30`
- `0x180004a50`
- `0x180017b94`
- `0x18001a280`
- `0x18001a2ec`
- `0x18001a8d0`
- `0x18002a0b4`
- `0x18002a414`
- `0x18002afd0`
- `0x18002b454`
- `0x18002b830`
- `0x18003e520`
- `0x18003ebac`
- `0x18003eec8`
- `0x18003efa8`
- `0x18003f0b0`
- `0x1800402cc`
- `0x18004325c`
- `0x18004330c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bcb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bcfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bdfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bcb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bcfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bdfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be40`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b8d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c022`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c15a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b8d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c022`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c15a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002c096`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002c096`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c074`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c1bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c074`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c1bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b9a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c0d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c1ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b9a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c0d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c1ff`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002bacb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002bacb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002bef8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002bef8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18002bf49`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18002bf49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf84`
- `CRYPT32!CertFreeCertificateContext` at `0x18002bfca`
- `CRYPT32!CertFreeCertificateContext` at `0x18002bfca`
- `CRYPT32!CertCloseStore` at `0x18002be5f`
- `CRYPT32!CertCloseStore` at `0x18002be5f`
- `CRYPT32!CertFindCertificateInStore` at `0x18002be32`
- `CRYPT32!CertFindCertificateInStore` at `0x18002be32`
- `CRYPT32!CertOpenStore` at `0x18002bde8`
- `CRYPT32!CertOpenStore` at `0x18002bde8`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18002beac`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18002beac`
- `ncrypt!NCryptFreeObject` at `0x18002bfbc`
- `ncrypt!NCryptFreeObject` at `0x18002bfbc`
- `ncrypt!NCryptIsKeyHandle` at `0x18002bfa3`
- `ncrypt!NCryptIsKeyHandle` at `0x18002bfa3`
- `CRYPTSP!CryptAcquireContextW` at `0x18002bca5`
- `CRYPTSP!CryptAcquireContextW` at `0x18002bcf0`
- `CRYPTSP!CryptAcquireContextW` at `0x18002bd35`
- `CRYPTSP!CryptAcquireContextW` at `0x18002bca5`
- `CRYPTSP!CryptAcquireContextW` at `0x18002bcf0`
- `CRYPTSP!CryptAcquireContextW` at `0x18002bd35`
- `CRYPTSP!CryptReleaseContext` at `0x18002bd65`
- `CRYPTSP!CryptReleaseContext` at `0x18002bfb4`
- `CRYPTSP!CryptReleaseContext` at `0x18002bd65`
- `CRYPTSP!CryptReleaseContext` at `0x18002bfb4`

## string_xrefs

- `0x18002c182`: `Reg.OpenKey failed: 0x%x in %s`
- `0x18002b8fa`: `pReg->OpenKey failed: 0x%x in %s`
- `0x18002c04a`: `pReg->OpenKey failed: 0x%x in %s`
- `0x18002b8f0`: `CCertManager::GetHashFromTheRegistry`
- `0x18002b945`: `CCertManager::GetHashFromTheRegistry`
- `0x18002ba01`: `UpdateSelfSignedCertificate`
- `0x18002baf8`: `UpdateSelfSignedCertificate`
- `0x18002bbca`: `UpdateSelfSignedCertificate`
- `0x18002c103`: `UpdateSelfSignedCertificate`
- `0x18002c22a`: `UpdateSelfSignedCertificate`
- `0x18002c31a`: `UpdateSelfSignedCertificate`
- `0x18002ba25`: `GetHashFromTheRegistry`
- `0x18002bb08`: `GetSelfSignedCertStoreName`
- `0x18002c236`: `GetSelfSignedCertStoreName`
- `0x18002bbda`: `IsCurrentCertificateNeedsUpdate`
- `0x18002c303`: `sessenv.dll`
- `0x18002c10f`: `PutHashInTheRegistry`
- `0x18002c0b6`: `CCertManager::PutHashInTheRegistry`
- `0x18002c08d`: `pReg->WriteRegBinary failed: 0x%x in %s`
- `0x18002c0af`: `pReg->DeleteValue failed: 0x%x in %s`
- `0x18002b94f`: `pReg->ReadRegBinary failed: 0x%x in %s`
- `0x18002c1dd`: `CCertManager::SetSelfSignedCertStoreName`
- `0x18002c1d6`: `Reg.WriteRegString failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCertManager::UpdateSelfSignedCertificate(unsigned __int16 **this)
{
  int v2; // r12d
  unsigned int v3; // r15d
  unsigned __int16 *v4; // rsi
  __int64 v5; // r13
  LSTATUS v6; // eax
  signed int IsCurrentCertificateNeedsUpdate; // ebx
  const struct std::nothrow_t *v8; // rdx
  int Reg; // eax
  unsigned int v10; // ecx
  CCertManager *v11; // rcx
  int v12; // edi
  int SelfSignedCertStoreName; // eax
  unsigned int v14; // r8d
  unsigned __int16 *v15; // r14
  unsigned int v16; // edi
  signed int LastError; // eax
  bool v18; // sf
  signed int v19; // eax
  signed int v20; // ebx
  signed int v21; // eax
  DWORD v22; // eax
  const wchar_t *v23; // rax
  HCERTSTORE v24; // rdi
  const CERT_CONTEXT *CertificateInStore; // r14
  signed int v26; // eax
  signed int v27; // ebx
  signed int v28; // eax
  NCRYPT_HANDLE v29; // r15
  struct _ACL *v30; // rbx
  struct _SECURITY_DESCRIPTOR *SecurityDescriptor; // rax
  struct _SECURITY_DESCRIPTOR *v32; // rsi
  const unsigned __int16 *v33; // rcx
  void *SIDForAccount; // rax
  void *v35; // rdi
  struct _ACL *v36; // rbx
  DWORD v37; // edi
  LSTATUS v38; // eax
  HKEY v39; // rcx
  LSTATUS v40; // eax
  LSTATUS v41; // eax
  const char *v42; // rax
  __int16 *v43; // rdx
  LSTATUS v44; // eax
  HKEY v45; // rcx
  unsigned __int16 v46; // dx
  LSTATUS v47; // eax
  CCertManager *v48; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  HCRYPTPROV hProv; // [rsp+50h] [rbp-B0h] BYREF
  HCRYPTPROV phProv; // [rsp+58h] [rbp-A8h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+60h] [rbp-A0h] BYREF
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  signed int v56; // [rsp+6Ch] [rbp-94h] BYREF
  void *pvPara; // [rsp+70h] [rbp-90h] BYREF
  DWORD pdwKeySpec; // [rsp+78h] [rbp-88h] BYREF
  WINBOOL bDaclPresent[2]; // [rsp+80h] [rbp-80h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+88h] [rbp-78h] BYREF
  __int128 pvFindPara; // [rsp+98h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-50h] BYREF
  char *v63; // [rsp+C0h] [rbp-40h]
  int v64; // [rsp+C8h] [rbp-38h]
  int v65; // [rsp+CCh] [rbp-34h]
  const char *v66; // [rsp+D0h] [rbp-30h]
  __int64 v67; // [rsp+D8h] [rbp-28h]
  const char *v68; // [rsp+E0h] [rbp-20h]
  __int64 v69; // [rsp+E8h] [rbp-18h]
  signed int *v70; // [rsp+F0h] [rbp-10h]
  __int64 v71; // [rsp+F8h] [rbp-8h]
  const char *v72; // [rsp+100h] [rbp+0h]
  __int64 v73; // [rsp+108h] [rbp+8h]
  WCHAR szContainer[4]; // [rsp+110h] [rbp+10h] BYREF
  void *Block; // [rsp+118h] [rbp+18h]
  int v76; // [rsp+120h] [rbp+20h]
  HKEY hKey; // [rsp+128h] [rbp+28h] BYREF
  __int64 v78; // [rsp+130h] [rbp+30h]
  BYTE Data[24]; // [rsp+138h] [rbp+38h] BYREF
  unsigned __int8 v80[16]; // [rsp+150h] [rbp+50h] BYREF
  int v81; // [rsp+160h] [rbp+60h]

  *(_QWORD *)&EventDescriptor.Id = this;
  cbData = 20;
  pvFindPara = 0;
  v2 = 0;
  v3 = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  v4 = 0;
  pvPara = 0;
  pdwKeySpec = 0;
  *(_QWORD *)szContainer = &CRegistry::`vftable';
  Block = 0;
  v76 = 0;
  hKey = 0;
  v5 = -1;
  v78 = -1;
  phProv = 0;
  bDaclDefaulted = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
         0,
         0x20019u,
         &hKey);
  IsCurrentCertificateNeedsUpdate = v6;
  if ( v6 )
  {
    hKey = 0;
    if ( v6 > 0 )
      IsCurrentCertificateNeedsUpdate = (unsigned __int16)v6 | 0x80070000;
  }
  if ( IsCurrentCertificateNeedsUpdate >= 0 )
  {
    Reg = CRegistry::ReadReg(
            (CRegistry *)szContainer,
            L"SelfSignedCertificate",
            (unsigned __int8 **)&phProv,
            (unsigned int *)&bDaclDefaulted,
            3u);
    IsCurrentCertificateNeedsUpdate = Reg;
    if ( Reg > 0 )
      IsCurrentCertificateNeedsUpdate = (unsigned __int16)Reg | 0x80070000;
    if ( IsCurrentCertificateNeedsUpdate >= 0 )
    {
      if ( bDaclDefaulted == 20 )
      {
        v10 = 0;
        v8 = (const struct std::nothrow_t *)phProv;
        while ( !*(_BYTE *)(v10 + phProv) )
        {
          if ( ++v10 >= 0x14 )
          {
            IsCurrentCertificateNeedsUpdate = -2147024894;
            goto LABEL_17;
          }
        }
        *(_OWORD *)v80 = *(_OWORD *)phProv;
        v81 = *(_DWORD *)(phProv + 16);
      }
      else
      {
        IsCurrentCertificateNeedsUpdate = -2147024883;
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "pReg->ReadRegBinary failed: 0x%x in %s",
        IsCurrentCertificateNeedsUpdate,
        "CCertManager::GetHashFromTheRegistry");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "pReg->OpenKey failed: 0x%x in %s",
      IsCurrentCertificateNeedsUpdate,
      "CCertManager::GetHashFromTheRegistry");
  }
LABEL_17:
  *(_QWORD *)szContainer = &CRegistry::`vftable';
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v11 = (CCertManager *)Block;
  if ( Block )
    operator delete(Block);
  v76 = 0;
  Block = 0;
  if ( IsCurrentCertificateNeedsUpdate < 0 )
  {
    if ( IsCurrentCertificateNeedsUpdate != -2147024894 && IsCurrentCertificateNeedsUpdate != -2147024883 )
    {
      if ( (unsigned int)dword_180084170 > 3 )
      {
        v56 = IsCurrentCertificateNeedsUpdate;
        v72 = "UpdateSelfSignedCertificate";
        v73 = 28;
        v70 = &v56;
        v71 = 4;
        v68 = "GetHashFromTheRegistry";
        v69 = 23;
        v66 = "Warning HResult failed";
        v67 = 23;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 3;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_180084178;
        UserData.Size = *(unsigned __int16 *)off_180084178;
        UserData.Reserved = 2;
        v63 = byte_1800794F9;
        v64 = 57;
        v65 = 1;
        pfCallerFreeProvOrNCryptKey = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
      }
      goto LABEL_141;
    }
    v12 = 0;
  }
  else
  {
    v12 = 1;
  }
  v56 = v12;
  SelfSignedCertStoreName = CCertManager::GetSelfSignedCertStoreName(v11, (unsigned __int16 **)&pvPara);
  IsCurrentCertificateNeedsUpdate = SelfSignedCertStoreName;
  if ( SelfSignedCertStoreName < 0 )
  {
    if ( (unsigned int)dword_180084170 > 3 )
    {
      phProv = (HCRYPTPROV)"UpdateSelfSignedCertificate";
      v56 = SelfSignedCertStoreName;
      hProv = (HCRYPTPROV)"GetSelfSignedCertStoreName";
      *(_QWORD *)bDaclPresent = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)&dword_180084170,
        (unsigned int)byte_1800794A9,
        0,
        0,
        (__int64)bDaclPresent,
        (__int64)&hProv,
        (__int64)&v56,
        (__int64)&phProv);
    }
    v4 = (unsigned __int16 *)pvPara;
    goto LABEL_141;
  }
  v4 = (unsigned __int16 *)pvPara;
  if ( v12 )
  {
    IsCurrentCertificateNeedsUpdate = CCertManager::IsCurrentCertificateNeedsUpdate(
                                        (CCertManager *)this,
                                        v80,
                                        v14,
                                        (const unsigned __int16 *)pvPara,
                                        0,
                                        1,
                                        0xB0u,
                                        0x1Eu,
                                        &pfCallerFreeProvOrNCryptKey,
                                        (int *)&pdwKeySpec);
    if ( IsCurrentCertificateNeedsUpdate < 0 )
    {
      if ( (unsigned int)dword_180084170 > 3 )
      {
        phProv = (HCRYPTPROV)"UpdateSelfSignedCertificate";
        pdwKeySpec = IsCurrentCertificateNeedsUpdate;
        hProv = (HCRYPTPROV)"IsCurrentCertificateNeedsUpdate";
        pvPara = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (unsigned int)&dword_180084170,
          (unsigned int)&dword_180079464,
          0,
          0,
          (__int64)&pvPara,
          (__int64)&hProv,
          (__int64)&pdwKeySpec,
          (__int64)&phProv);
      }
      goto LABEL_141;
    }
    v3 = pfCallerFreeProvOrNCryptKey;
    if ( !pfCallerFreeProvOrNCryptKey )
      goto LABEL_141;
  }
  v15 = this[202];
  v16 = 1;
  while ( 1 )
  {
    IsCurrentCertificateNeedsUpdate = StringCbPrintfW(szContainer, 0x1Au, L"TSSecKeySet%d", v16);
    if ( IsCurrentCertificateNeedsUpdate < 0 )
      goto LABEL_138;
    phProv = 0;
    if ( CryptAcquireContextW(&phProv, szContainer, L"Microsoft Enhanced Cryptographic Provider v1.0", 1u, 0x30u) )
      break;
    LastError = GetLastError();
    v18 = LastError < 0;
    if ( LastError > 0 )
      v18 = 1;
    if ( !v18 )
      break;
    hProv = 0;
    if ( CryptAcquireContextW(&hProv, szContainer, L"Microsoft Enhanced Cryptographic Provider v1.0", 1u, 0x20u) )
      goto LABEL_50;
    v19 = GetLastError();
    v20 = v19;
    if ( v19 > 0 )
      v20 = (unsigned __int16)v19 | 0x80070000;
    if ( v20 != -2146893802 )
      goto LABEL_51;
    if ( CryptAcquireContextW(&hProv, szContainer, L"Microsoft Enhanced Cryptographic Provider v1.0", 1u, 0x28u) )
    {
LABEL_50:
      v20 = 0;
    }
    else
    {
      v21 = GetLastError();
      v20 = v21;
      if ( v21 > 0 )
        v20 = (unsigned __int16)v21 | 0x80070000;
    }
LABEL_51:
    if ( hProv )
      CryptReleaseContext(hProv, 0);
    if ( v20 < 0 && (int)++v16 <= 9 )
      continue;
    break;
  }
  IsCurrentCertificateNeedsUpdate = RDP_GetGenericSelfSignedCertificate(v15, v4, szContainer, phkResult, Data, &cbData);
  if ( IsCurrentCertificateNeedsUpdate < 0 )
  {
LABEL_138:
    MicrosoftTelemetryAssertTriggeredArgs("sessenv.dll", (unsigned int)IsCurrentCertificateNeedsUpdate, v3);
    if ( (unsigned int)dword_180084170 > 3 )
    {
      *(_QWORD *)&EventDescriptor.Id = "UpdateSelfSignedCertificate";
      bDaclPresent[0] = IsCurrentCertificateNeedsUpdate;
      phProv = (HCRYPTPROV)"TsCryptGetSelfSignedCertificate";
      hProv = (HCRYPTPROV)"Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)&dword_180084170,
        (unsigned int)&byte_18007941F,
        0,
        0,
        (__int64)&hProv,
        (__int64)&phProv,
        (__int64)bDaclPresent,
        (__int64)&EventDescriptor);
    }
    CCertManager::SecLogFailure(1u, 0xC0000421, IsCurrentCertificateNeedsUpdate);
  }
  else
  {
    v22 = cbData;
    if ( cbData != 20 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v22 = cbData;
    }
    LODWORD(pvFindPara) = v22;
    *((_QWORD *)&pvFindPara + 1) = Data;
    v23 = L"MY";
    if ( v4 )
      v23 = v4;
    v24 = CertOpenStore("System", 0, 0, 0x2C000u, v23);
    if ( v24 )
    {
      CertificateInStore = CertFindCertificateInStore(v24, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
      if ( CertificateInStore )
      {
        v27 = 0;
      }
      else
      {
        v28 = GetLastError();
        v27 = v28;
        if ( v28 > 0 )
          v27 = (unsigned __int16)v28 | 0x80070000;
      }
      CertCloseStore(v24, 0);
    }
    else
    {
      CertificateInStore = 0;
      v26 = GetLastError();
      v27 = v26;
      if ( v26 > 0 )
        v27 = (unsigned __int16)v26 | 0x80070000;
    }
    if ( v27 < 0 )
    {
LABEL_89:
      if ( CertificateInStore )
        CertFreeCertificateContext(CertificateInStore);
    }
    else
    {
      hProv = 0;
      pdwKeySpec = 0;
      pfCallerFreeProvOrNCryptKey = 0;
      v2 = 0;
      if ( CertificateInStore )
      {
        v2 = CryptAcquireCertificatePrivateKey(
               CertificateInStore,
               0x10044u,
               0,
               &hProv,
               &pdwKeySpec,
               &pfCallerFreeProvOrNCryptKey);
        if ( v2 )
        {
          v29 = hProv;
          v30 = 0;
          v2 = 0;
          SecurityDescriptor = TsCryptGetSecurityDescriptor(hProv);
          v32 = SecurityDescriptor;
          if ( SecurityDescriptor )
          {
            phProv = 0;
            bDaclDefaulted = 0;
            bDaclPresent[0] = 0;
            if ( GetSecurityDescriptorDacl(SecurityDescriptor, bDaclPresent, (PACL *)&phProv, &bDaclDefaulted) )
              v30 = (struct _ACL *)phProv;
            else
              phProv = 0;
            if ( v30 )
            {
              SIDForAccount = TsCryptGetSIDForAccount(v33);
              v35 = SIDForAccount;
              if ( SIDForAccount )
              {
                v36 = TsCryptAddSidToAcl(v30, SIDForAccount);
                if ( v36 )
                {
                  LOWORD(bDaclDefaulted) = 0;
                  bDaclPresent[0] = 0;
                  if ( GetSecurityDescriptorControl(
                         v32,
                         (PSECURITY_DESCRIPTOR_CONTROL)&bDaclDefaulted,
                         (LPDWORD)bDaclPresent) )
                  {
                    v2 = TsCryptSetSecurityDescriptorDacl(v29, v36, ((unsigned __int16)bDaclDefaulted >> 12) & 1);
                  }
                  LocalFree(v36);
                }
                LocalFree(v35);
              }
            }
            LocalFree(v32);
          }
          v4 = (unsigned __int16 *)pvPara;
        }
        if ( pfCallerFreeProvOrNCryptKey && hProv )
        {
          if ( NCryptIsKeyHandle(hProv) )
            NCryptFreeObject(hProv);
          else
            CryptReleaseContext(hProv, 0);
        }
        goto LABEL_89;
      }
    }
    if ( !v2 )
    {
      IsCurrentCertificateNeedsUpdate = -2147024891;
LABEL_134:
      CCertManager::SecLogFailure(1u, 0xC0000422, IsCurrentCertificateNeedsUpdate);
      TsCryptDeleteCertificate(v4, Data, cbData);
      goto LABEL_141;
    }
    v37 = cbData;
    *(_QWORD *)szContainer = &CRegistry::`vftable';
    Block = 0;
    v76 = 0;
    hKey = 0;
    v78 = -1;
    v38 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
            0,
            0x20006u,
            &hKey);
    IsCurrentCertificateNeedsUpdate = v38;
    if ( v38 )
    {
      v39 = 0;
      hKey = 0;
      if ( v38 > 0 )
        IsCurrentCertificateNeedsUpdate = (unsigned __int16)v38 | 0x80070000;
    }
    else
    {
      v39 = hKey;
    }
    if ( IsCurrentCertificateNeedsUpdate >= 0 )
    {
      if ( v37 )
      {
        v40 = RegSetValueExW(v39, L"SelfSignedCertificate", 0, 3u, Data, v37);
        IsCurrentCertificateNeedsUpdate = v40;
        if ( v40 > 0 )
          IsCurrentCertificateNeedsUpdate = (unsigned __int16)v40 | 0x80070000;
        if ( IsCurrentCertificateNeedsUpdate < 0 )
          _DbgPrintMessage(
            8,
            "pReg->WriteRegBinary failed: 0x%x in %s",
            (unsigned int)IsCurrentCertificateNeedsUpdate,
            "CCertManager::PutHashInTheRegistry");
      }
      else
      {
        v41 = RegDeleteValueW(v39, L"SelfSignedCertificate");
        IsCurrentCertificateNeedsUpdate = v41;
        if ( v41 > 0 )
          IsCurrentCertificateNeedsUpdate = (unsigned __int16)v41 | 0x80070000;
        if ( IsCurrentCertificateNeedsUpdate < 0 )
          _DbgPrintMessage(
            8,
            "pReg->DeleteValue failed: 0x%x in %s",
            (unsigned int)IsCurrentCertificateNeedsUpdate,
            "CCertManager::PutHashInTheRegistry");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "pReg->OpenKey failed: 0x%x in %s",
        (unsigned int)IsCurrentCertificateNeedsUpdate,
        "CCertManager::PutHashInTheRegistry");
    }
    *(_QWORD *)szContainer = &CRegistry::`vftable';
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( Block )
      operator delete(Block);
    if ( IsCurrentCertificateNeedsUpdate < 0 )
    {
      if ( (unsigned int)dword_180084170 <= 3 )
        goto LABEL_134;
      phProv = (HCRYPTPROV)"UpdateSelfSignedCertificate";
      v42 = "PutHashInTheRegistry";
      v43 = word_1800793DA;
LABEL_133:
      hProv = (HCRYPTPROV)v42;
      pvPara = "Warning HResult failed";
      bDaclPresent[0] = IsCurrentCertificateNeedsUpdate;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)&dword_180084170,
        (_DWORD)v43,
        0,
        0,
        (__int64)&pvPara,
        (__int64)&hProv,
        (__int64)bDaclPresent,
        (__int64)&phProv);
      goto LABEL_134;
    }
    *(_QWORD *)szContainer = &CRegistry::`vftable';
    Block = 0;
    v76 = 0;
    hKey = 0;
    v78 = -1;
    v44 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
            0,
            0x20006u,
            &hKey);
    IsCurrentCertificateNeedsUpdate = v44;
    if ( v44 )
    {
      v45 = 0;
      hKey = 0;
      if ( v44 > 0 )
        IsCurrentCertificateNeedsUpdate = (unsigned __int16)v44 | 0x80070000;
    }
    else
    {
      v45 = hKey;
    }
    if ( IsCurrentCertificateNeedsUpdate >= 0 )
    {
      do
        ++v5;
      while ( v4[v5] );
      v47 = RegSetValueExW(v45, L"SelfSignedCertStore", 0, 1u, (const BYTE *)v4, 2 * v5 + 2);
      IsCurrentCertificateNeedsUpdate = v47;
      if ( v47 > 0 )
        IsCurrentCertificateNeedsUpdate = (unsigned __int16)v47 | 0x80070000;
      if ( IsCurrentCertificateNeedsUpdate < 0 )
        _DbgPrintMessage(
          8,
          "Reg.WriteRegString failed: 0x%x in %s",
          (unsigned int)IsCurrentCertificateNeedsUpdate,
          "CCertManager::SetSelfSignedCertStoreName");
    }
    else
    {
      _DbgPrintMessage(
        8,
        "Reg.OpenKey failed: 0x%x in %s",
        (unsigned int)IsCurrentCertificateNeedsUpdate,
        "CCertManager::SetSelfSignedCertStoreName");
    }
    *(_QWORD *)szContainer = &CRegistry::`vftable';
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v48 = (CCertManager *)Block;
    if ( Block )
      operator delete(Block);
    if ( IsCurrentCertificateNeedsUpdate < 0 )
    {
      if ( (unsigned int)dword_180084170 <= 3 )
        goto LABEL_134;
      phProv = (HCRYPTPROV)"UpdateSelfSignedCertificate";
      v42 = "GetSelfSignedCertStoreName";
      v43 = (__int16 *)byte_180079395;
      goto LABEL_133;
    }
    if ( v56 )
      TsCryptDeleteCertificate(v4, v80, 20);
    CCertManager::SecLogEvent(
      v48,
      v46,
      0xC0000420,
      *(const unsigned __int16 **)(*(_QWORD *)&EventDescriptor.Id + 1616LL),
      Data,
      cbData);
  }
LABEL_141:
  if ( v4 )
    operator delete(v4, v8);
  return (unsigned int)IsCurrentCertificateNeedsUpdate;
}

```

## disassembly

```asm
0x18002b830  push    rbp
0x18002b832  push    rbx
0x18002b833  push    rsi
0x18002b834  push    rdi
0x18002b835  push    r12
0x18002b837  push    r13
0x18002b839  push    r14
0x18002b83b  push    r15
0x18002b83d  lea     rbp, [rsp-78h]
0x18002b842  sub     rsp, 178h
0x18002b849  mov     rax, cs:__security_cookie
0x18002b850  xor     rax, rsp
0x18002b853  mov     [rbp+0B0h+var_48], rax
0x18002b857  mov     r14, rcx
0x18002b85a  mov     qword ptr [rbp+0B0h+EventDescriptor.Id], rcx
0x18002b85e  mov     [rsp+1B0h+cbData], 14h
0x18002b866  xorps   xmm0, xmm0
0x18002b869  movups  [rbp+0B0h+pvFindPara], xmm0
0x18002b86d  xor     r12d, r12d
0x18002b870  mov     r15d, r12d
0x18002b873  mov     [rsp+1B0h+pfCallerFreeProvOrNCryptKey], r12d
0x18002b878  mov     esi, r12d
0x18002b87b  mov     [rsp+1B0h+pvPara], r12
0x18002b880  mov     [rsp+1B0h+pdwKeySpec], r12d
0x18002b885  lea     rdi, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18002b88c  mov     qword ptr [rbp+0B0h+szContainer], rdi
0x18002b890  mov     [rbp+0B0h+Block], r12
0x18002b894  mov     [rbp+0B0h+var_90], r12d
0x18002b898  mov     [rbp+0B0h+hKey], r12
0x18002b89c  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18002b8a3  mov     [rbp+0B0h+var_80], r13
0x18002b8a7  mov     [rsp+1B0h+phProv], r12
0x18002b8ac  mov     [rsp+1B0h+bDaclDefaulted], r12d
0x18002b8b1  lea     rax, [rbp+0B0h+hKey]
0x18002b8b5  mov     [rsp+1B0h+phkResult], rax; phkResult
0x18002b8ba  mov     r9d, 20019h; samDesired
0x18002b8c0  xor     r8d, r8d; ulOptions
0x18002b8c3  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Control\\Ter"...
0x18002b8ca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b8d1  call    cs:__imp_RegOpenKeyExW
0x18002b8d7  mov     ebx, eax
0x18002b8d9  test    eax, eax
0x18002b8db  jz      short loc_18002B8EC
0x18002b8dd  mov     [rbp+0B0h+hKey], r12
0x18002b8e1  jle     short loc_18002B8EC
0x18002b8e3  movzx   ebx, ax
0x18002b8e6  or      ebx, 80070000h
0x18002b8ec  test    ebx, ebx
0x18002b8ee  jns     short loc_18002B910
0x18002b8f0  lea     r9, aCcertmanagerGe_0; "CCertManager::GetHashFromTheRegistry"
0x18002b8f7  mov     r8d, ebx
0x18002b8fa  lea     rdx, aPregOpenkeyFai; "pReg->OpenKey failed: 0x%x in %s"
0x18002b901  mov     ecx, 8; int
0x18002b906  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b90b  jmp     loc_18002B99B
0x18002b910  mov     dword ptr [rsp+1B0h+phkResult], 3; unsigned int
0x18002b918  lea     r9, [rsp+1B0h+bDaclDefaulted]; unsigned int *
0x18002b91d  lea     r8, [rsp+1B0h+phProv]; unsigned __int8 **
0x18002b922  lea     rdx, aSelfsignedcert; "SelfSignedCertificate"
0x18002b929  lea     rcx, [rbp+0B0h+szContainer]; this
0x18002b92d  call    ?ReadReg@CRegistry@@QEAAKPEBGPEAPEAEPEAKK@Z; CRegistry::ReadReg(ushort const *,uchar * *,ulong *,ulong)
0x18002b932  mov     ebx, eax
0x18002b934  test    eax, eax
0x18002b936  jle     short loc_18002B941
0x18002b938  movzx   ebx, ax
0x18002b93b  or      ebx, 80070000h
0x18002b941  test    ebx, ebx
0x18002b943  jns     short loc_18002B962
0x18002b945  lea     r9, aCcertmanagerGe_0; "CCertManager::GetHashFromTheRegistry"
0x18002b94c  mov     r8d, ebx
0x18002b94f  lea     rdx, aPregReadregbin; "pReg->ReadRegBinary failed: 0x%x in %s"
0x18002b956  mov     ecx, 8; int
0x18002b95b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b960  jmp     short loc_18002B99B
0x18002b962  cmp     [rsp+1B0h+bDaclDefaulted], 14h
0x18002b967  jz      short loc_18002B970
0x18002b969  mov     ebx, 8007000Dh
0x18002b96e  jmp     short loc_18002B99B
0x18002b970  mov     ecx, r12d
0x18002b973  mov     rdx, [rsp+1B0h+phProv]
0x18002b978  mov     eax, ecx
0x18002b97a  cmp     byte ptr [rax+rdx], 0
0x18002b97e  jnz     short loc_18002B98E
0x18002b980  inc     ecx
0x18002b982  cmp     ecx, 14h
0x18002b985  jb      short loc_18002B978
0x18002b987  mov     ebx, 80070002h
0x18002b98c  jmp     short loc_18002B99B
0x18002b98e  movups  xmm0, xmmword ptr [rdx]
0x18002b991  movups  xmmword ptr [rbp+0B0h+var_60], xmm0
0x18002b995  mov     eax, [rdx+10h]
0x18002b998  mov     [rbp+0B0h+var_50], eax
0x18002b99b  mov     qword ptr [rbp+0B0h+szContainer], rdi
0x18002b99f  mov     rcx, [rbp+0B0h+hKey]; hKey
0x18002b9a3  test    rcx, rcx
0x18002b9a6  jz      short loc_18002B9B2
0x18002b9a8  call    cs:__imp_RegCloseKey
0x18002b9ae  mov     [rbp+0B0h+hKey], r12
0x18002b9b2  mov     rcx, [rbp+0B0h+Block]; Block
0x18002b9b6  test    rcx, rcx
0x18002b9b9  jz      short loc_18002B9C0
0x18002b9bb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002b9c0  mov     [rbp+0B0h+var_90], r12d
0x18002b9c4  mov     [rbp+0B0h+Block], r12
0x18002b9c8  test    ebx, ebx
0x18002b9ca  js      short loc_18002B9D6
0x18002b9cc  mov     edi, 1
0x18002b9d1  jmp     loc_18002BAD9
0x18002b9d6  cmp     ebx, 80070002h
0x18002b9dc  jz      loc_18002BAD6
0x18002b9e2  cmp     ebx, 8007000Dh
0x18002b9e8  jz      loc_18002BAD6
0x18002b9ee  mov     eax, cs:dword_180084170
0x18002b9f4  cmp     eax, 3
0x18002b9f7  jbe     loc_18002C391
0x18002b9fd  mov     [rsp+1B0h+var_144], ebx
0x18002ba01  lea     rax, aUpdateselfsign_0; "UpdateSelfSignedCertificate"
0x18002ba08  mov     [rbp+0B0h+var_B0], rax
0x18002ba0c  mov     [rbp+0B0h+var_A8], 1Ch
0x18002ba14  lea     rax, [rsp+1B0h+var_144]
0x18002ba19  mov     [rbp+0B0h+var_C0], rax
0x18002ba1d  mov     [rbp+0B0h+var_B8], 4
0x18002ba25  lea     rax, aGethashfromthe; "GetHashFromTheRegistry"
0x18002ba2c  mov     [rbp+0B0h+var_D0], rax
0x18002ba30  mov     [rbp+0B0h+var_C8], 17h
0x18002ba38  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002ba3f  mov     [rbp+0B0h+var_E0], rax
0x18002ba43  mov     [rbp+0B0h+var_D8], 17h
0x18002ba4b  mov     dword ptr [rbp+0B0h+EventDescriptor.Id], 0B000000h
0x18002ba52  movzx   eax, cs:word_1800794EF
0x18002ba59  mov     dword ptr [rbp+0B0h+EventDescriptor.Level], eax
0x18002ba5c  mov     [rbp+0B0h+EventDescriptor.Keyword], r12
0x18002ba60  mov     rax, cs:off_180084178
0x18002ba67  mov     [rbp+0B0h+var_100.Ptr], rax
0x18002ba6b  movzx   eax, word ptr [rax]
0x18002ba6e  mov     [rbp+0B0h+var_100.Size], eax
0x18002ba71  mov     dword ptr [rbp+0B0h+var_100.0Ch], 2
0x18002ba78  lea     rax, byte_1800794F9
0x18002ba7f  mov     [rbp+0B0h+var_F0], rax
0x18002ba83  mov     [rbp+0B0h+var_E8], 39h ; '9'
0x18002ba8a  mov     [rbp+0B0h+var_E4], 1
0x18002ba91  lea     rax, _TraceLoggingMetadataEnd
0x18002ba98  lea     rcx, _TraceLoggingMetadata
0x18002ba9f  sub     eax, ecx
0x18002baa1  mov     [rsp+1B0h+pfCallerFreeProvOrNCryptKey], eax
0x18002baa5  mov     eax, [rsp+1B0h+pfCallerFreeProvOrNCryptKey]
0x18002baa9  lea     rax, [rbp+0B0h+var_100]
0x18002baad  mov     [rsp+1B0h+UserData], rax; UserData
0x18002bab2  mov     dword ptr [rsp+1B0h+phkResult], 6; UserDataCount
0x18002baba  xor     r9d, r9d; RelatedActivityId
0x18002babd  xor     r8d, r8d; ActivityId
0x18002bac0  lea     rdx, [rbp+0B0h+EventDescriptor]; EventDescriptor
0x18002bac4  mov     rcx, cs:RegHandle; RegHandle
0x18002bacb  call    cs:__imp_EventWriteTransfer
0x18002bad1  jmp     loc_18002C391
0x18002bad6  mov     edi, r12d
0x18002bad9  mov     [rsp+1B0h+var_144], edi
0x18002badd  lea     rdx, [rsp+1B0h+pvPara]; unsigned __int16 **
0x18002bae2  call    ?GetSelfSignedCertStoreName@CCertManager@@AEAAJPEAPEAG@Z; CCertManager::GetSelfSignedCertStoreName(ushort * *)
0x18002bae7  mov     ebx, eax
0x18002bae9  test    eax, eax
0x18002baeb  jns     short loc_18002BB69
0x18002baed  mov     ecx, cs:dword_180084170
0x18002baf3  cmp     ecx, 3
0x18002baf6  jbe     short loc_18002BB5F
0x18002baf8  lea     rax, aUpdateselfsign_0; "UpdateSelfSignedCertificate"
0x18002baff  mov     [rsp+1B0h+phProv], rax
0x18002bb04  mov     [rsp+1B0h+var_144], ebx
0x18002bb08  lea     rax, aGetselfsignedc; "GetSelfSignedCertStoreName"
0x18002bb0f  mov     [rsp+1B0h+hProv], rax
0x18002bb14  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002bb1b  mov     qword ptr [rbp+0B0h+bDaclPresent], rax
0x18002bb1f  lea     rax, [rsp+1B0h+phProv]
0x18002bb24  mov     qword ptr [rsp+1B0h+var_178], rax
0x18002bb29  lea     rax, [rsp+1B0h+var_144]
0x18002bb2e  mov     [rsp+1B0h+pcbData], rax
0x18002bb33  lea     rax, [rsp+1B0h+hProv]
0x18002bb38  mov     [rsp+1B0h+UserData], rax
0x18002bb3d  lea     rax, [rbp+0B0h+bDaclPresent]
0x18002bb41  mov     [rsp+1B0h+phkResult], rax
0x18002bb46  xor     r9d, r9d
0x18002bb49  xor     r8d, r8d
0x18002bb4c  lea     rdx, byte_1800794A9
0x18002bb53  lea     rcx, dword_180084170
0x18002bb5a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002bb5f  mov     rsi, [rsp+1B0h+pvPara]
0x18002bb64  jmp     loc_18002C391
0x18002bb69  mov     rsi, [rsp+1B0h+pvPara]
0x18002bb6e  test    edi, edi
0x18002bb70  jz      loc_18002BC46
0x18002bb76  lea     rax, [rsp+1B0h+pdwKeySpec]
0x18002bb7b  mov     [rsp+1B0h+var_168], rax; int *
0x18002bb80  lea     rax, [rsp+1B0h+pfCallerFreeProvOrNCryptKey]
0x18002bb85  mov     [rsp+1B0h+var_170], rax; int *
0x18002bb8a  mov     [rsp+1B0h+var_178], 1Eh; unsigned int
0x18002bb92  mov     word ptr [rsp+1B0h+pcbData], 0B0h; unsigned __int16
0x18002bb99  mov     dword ptr [rsp+1B0h+UserData], 1; int
0x18002bba1  mov     dword ptr [rsp+1B0h+phkResult], r12d; int
0x18002bba6  mov     r9, rsi; unsigned __int16 *
0x18002bba9  lea     rdx, [rbp+0B0h+var_60]; unsigned __int8 *
0x18002bbad  mov     rcx, r14; this
0x18002bbb0  call    ?IsCurrentCertificateNeedsUpdate@CCertManager@@AEAAJPEAEKPEBGHHGKPEAH2@Z; CCertManager::IsCurrentCertificateNeedsUpdate(uchar *,ulong,ushort const *,int,int,ushort,ulong,int *,int *)
0x18002bbb5  mov     ebx, eax
0x18002bbb7  test    eax, eax
0x18002bbb9  jns     short loc_18002BC38
0x18002bbbb  mov     eax, cs:dword_180084170
0x18002bbc1  cmp     eax, 3
0x18002bbc4  jbe     loc_18002C391
0x18002bbca  lea     rax, aUpdateselfsign_0; "UpdateSelfSignedCertificate"
0x18002bbd1  mov     [rsp+1B0h+phProv], rax
0x18002bbd6  mov     [rsp+1B0h+pdwKeySpec], ebx
0x18002bbda  lea     rax, aIscurrentcerti_0; "IsCurrentCertificateNeedsUpdate"
0x18002bbe1  mov     [rsp+1B0h+hProv], rax
0x18002bbe6  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002bbed  mov     [rsp+1B0h+pvPara], rax
0x18002bbf2  lea     rax, [rsp+1B0h+phProv]
0x18002bbf7  mov     qword ptr [rsp+1B0h+var_178], rax
0x18002bbfc  lea     rax, [rsp+1B0h+pdwKeySpec]
0x18002bc01  mov     [rsp+1B0h+pcbData], rax
0x18002bc06  lea     rax, [rsp+1B0h+hProv]
0x18002bc0b  mov     [rsp+1B0h+UserData], rax
0x18002bc10  lea     rax, [rsp+1B0h+pvPara]
0x18002bc15  mov     [rsp+1B0h+phkResult], rax
0x18002bc1a  xor     r9d, r9d
0x18002bc1d  xor     r8d, r8d
0x18002bc20  lea     rdx, dword_180079464
0x18002bc27  lea     rcx, dword_180084170
0x18002bc2e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002bc33  jmp     loc_18002C391
0x18002bc38  mov     r15d, [rsp+1B0h+pfCallerFreeProvOrNCryptKey]
0x18002bc3d  test    r15d, r15d
0x18002bc40  jz      loc_18002C391
0x18002bc46  mov     r14, [r14+650h]
0x18002bc4d  mov     edi, 1
0x18002bc52  nop     dword ptr [rax+00h]
0x18002bc56  nop     word ptr [rax+rax+00000000h]
0x18002bc60  mov     r9d, edi
0x18002bc63  lea     r8, aTsseckeysetD; "TSSecKeySet%d"
0x18002bc6a  mov     edx, 1Ah; unsigned __int64
0x18002bc6f  lea     rcx, [rbp+0B0h+szContainer]; unsigned __int16 *
0x18002bc73  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bc78  mov     ebx, eax
0x18002bc7a  test    eax, eax
0x18002bc7c  js      loc_18002C2FE
0x18002bc82  mov     [rsp+1B0h+phProv], r12
0x18002bc87  mov     dword ptr [rsp+1B0h+phkResult], 30h ; '0'; dwFlags
0x18002bc8f  mov     r9d, 1; dwProvType
0x18002bc95  lea     r8, szProvider; "Microsoft Enhanced Cryptographic Provid"...
0x18002bc9c  lea     rdx, [rbp+0B0h+szContainer]; szContainer
0x18002bca0  lea     rcx, [rsp+1B0h+phProv]; phProv
0x18002bca5  call    cs:__imp_CryptAcquireContextW
0x18002bcab  test    eax, eax
0x18002bcad  jnz     loc_18002BD7A
0x18002bcb3  call    cs:__imp_GetLastError
0x18002bcb9  test    eax, eax
0x18002bcbb  jle     short loc_18002BCC7
0x18002bcbd  movzx   eax, ax
0x18002bcc0  or      eax, 80070000h
0x18002bcc5  test    eax, eax
0x18002bcc7  jns     loc_18002BD7A
0x18002bccd  mov     [rsp+1B0h+hProv], r12
0x18002bcd2  mov     dword ptr [rsp+1B0h+phkResult], 20h ; ' '; unsigned int
0x18002bcda  mov     r9d, 1; dwProvType
0x18002bce0  lea     r8, szProvider; "Microsoft Enhanced Cryptographic Provid"...
0x18002bce7  lea     rdx, [rbp+0B0h+szContainer]; szContainer
0x18002bceb  lea     rcx, [rsp+1B0h+hProv]; phProv
0x18002bcf0  call    cs:__imp_CryptAcquireContextW
0x18002bcf6  test    eax, eax
0x18002bcf8  jnz     short loc_18002BD56
0x18002bcfa  call    cs:__imp_GetLastError
0x18002bd00  mov     ebx, eax
0x18002bd02  test    eax, eax
0x18002bd04  jle     short loc_18002BD0F
0x18002bd06  movzx   ebx, ax
0x18002bd09  or      ebx, 80070000h
0x18002bd0f  cmp     ebx, 80090016h
0x18002bd15  jnz     short loc_18002BD59
0x18002bd17  mov     dword ptr [rsp+1B0h+phkResult], 28h ; '('; dwFlags
0x18002bd1f  mov     r9d, 1; dwProvType
0x18002bd25  lea     r8, szProvider; "Microsoft Enhanced Cryptographic Provid"...
0x18002bd2c  lea     rdx, [rbp+0B0h+szContainer]; szContainer
0x18002bd30  lea     rcx, [rsp+1B0h+hProv]; phProv
0x18002bd35  call    cs:__imp_CryptAcquireContextW
0x18002bd3b  test    eax, eax
0x18002bd3d  jnz     short loc_18002BD56
0x18002bd3f  call    cs:__imp_GetLastError
0x18002bd45  mov     ebx, eax
0x18002bd47  test    eax, eax
0x18002bd49  jle     short loc_18002BD59
0x18002bd4b  movzx   ebx, ax
0x18002bd4e  or      ebx, 80070000h
0x18002bd54  jmp     short loc_18002BD59
0x18002bd56  mov     ebx, r12d
0x18002bd59  mov     rcx, [rsp+1B0h+hProv]; hProv
0x18002bd5e  test    rcx, rcx
0x18002bd61  jz      short loc_18002BD6B
0x18002bd63  xor     edx, edx; dwFlags
0x18002bd65  call    cs:__imp_CryptReleaseContext
0x18002bd6b  test    ebx, ebx
0x18002bd6d  jns     short loc_18002BD7A
  ... truncated ...
```
