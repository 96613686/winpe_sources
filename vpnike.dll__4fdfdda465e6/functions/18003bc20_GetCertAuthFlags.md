# GetCertAuthFlags

- ea: `0x18003bc20`
- end: `0x18003bdac`
- name: `GetCertAuthFlags`
- size: `396`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003bdb4`

## callees

- `0x180007590`
- `0x18003bc20`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003bce1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003bce1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bcee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bcee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003bc98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003bc98`

## string_xrefs

- `0x18003bc8a`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters\Ikev2`
- `0x18003bcb2`: `Failed to open registry key (%d)`
- `0x18003bd04`: `Failed to read cert auth flags from registry (%d)`
- `0x18003bd4f`: `Got cert auth flags from registry: %lu`

## pseudocode

```c
__int64 GetCertAuthFlags()
{
  unsigned int v0; // eax
  __int64 v1; // r8
  const wchar_t *v2; // rdx
  unsigned int v3; // ebx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v8; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v9[2044]; // [rsp+44h] [rbp-BCh] BYREF

  *(_DWORD *)Data = 0;
  v8 = 0;
  cbData = 4;
  hKey = 0;
  memset_0(v9, 0, sizeof(v9));
  v0 = RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ikev2",
         0,
         1u,
         &hKey);
  if ( v0 )
  {
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v1 = v0;
      v2 = L"Failed to open registry key (%d)";
      goto LABEL_7;
    }
    return 0;
  }
  v3 = RegQueryValueExA(hKey, "CertAuthFlags", 0, 0, Data, &cbData);
  RegCloseKey(hKey);
  if ( v3 )
  {
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v1 = v3;
      v2 = L"Failed to read cert auth flags from registry (%d)";
LABEL_7:
      LOWORD(v8) = 0;
      FormatRRASErrorString(&v8, v2, v1);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v8);
    }
    return 0;
  }
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v8) = 0;
    FormatRRASErrorString(&v8, L"Got cert auth flags from registry: %lu", *(unsigned int *)Data);
    if ( (byte_1800AA941 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v8);
  }
  return *(unsigned int *)Data;
}

```

## disassembly

```asm
0x18003bc20  mov     [rsp-8+arg_0], rbx
0x18003bc25  push    rbp
0x18003bc26  lea     rbp, [rsp-750h]
0x18003bc2e  sub     rsp, 850h
0x18003bc35  mov     rax, cs:__security_cookie
0x18003bc3c  xor     rax, rsp
0x18003bc3f  mov     [rbp+750h+var_10], rax
0x18003bc46  xor     eax, eax
0x18003bc48  mov     dword ptr [rsp+850h+Data], 0
0x18003bc50  xor     edx, edx; Val
0x18003bc52  mov     [rsp+850h+var_810], eax
0x18003bc56  mov     r8d, 7FCh; Size
0x18003bc5c  mov     [rsp+850h+cbData], 4
0x18003bc64  lea     rcx, [rsp+850h+var_80C]; void *
0x18003bc69  mov     [rsp+850h+hKey], 0
0x18003bc72  call    memset_0
0x18003bc77  lea     rax, [rsp+850h+hKey]
0x18003bc7c  mov     r9d, 1; samDesired
0x18003bc82  xor     r8d, r8d; ulOptions
0x18003bc85  mov     [rsp+850h+phkResult], rax; phkResult
0x18003bc8a  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18003bc91  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003bc98  call    cs:__imp_RegOpenKeyExA
0x18003bc9e  test    eax, eax
0x18003bca0  jz      short loc_18003BCBB
0x18003bca2  test    cs:byte_1800AA941, 8
0x18003bca9  jz      loc_18003BD3D
0x18003bcaf  mov     r8d, eax
0x18003bcb2  lea     rdx, aFailedToOpenRe; "Failed to open registry key (%d)"
0x18003bcb9  jmp     short loc_18003BD0B
0x18003bcbb  mov     rcx, [rsp+850h+hKey]; hKey
0x18003bcc0  lea     rax, [rsp+850h+cbData]
0x18003bcc5  mov     [rsp+850h+lpcbData], rax; lpcbData
0x18003bcca  lea     rdx, aCertauthflags; "CertAuthFlags"
0x18003bcd1  lea     rax, [rsp+850h+Data]
0x18003bcd6  xor     r9d, r9d; lpType
0x18003bcd9  xor     r8d, r8d; lpReserved
0x18003bcdc  mov     [rsp+850h+phkResult], rax; lpData
0x18003bce1  call    cs:__imp_RegQueryValueExA
0x18003bce7  mov     rcx, [rsp+850h+hKey]; hKey
0x18003bcec  mov     ebx, eax
0x18003bcee  call    cs:__imp_RegCloseKey
0x18003bcf4  test    ebx, ebx
0x18003bcf6  jz      short loc_18003BD41
0x18003bcf8  test    cs:byte_1800AA941, 8
0x18003bcff  jz      short loc_18003BD3D
0x18003bd01  mov     r8d, ebx
0x18003bd04  lea     rdx, aFailedToReadCe; "Failed to read cert auth flags from reg"...
0x18003bd0b  xor     ecx, ecx
0x18003bd0d  mov     word ptr [rsp+850h+var_810], cx
0x18003bd12  lea     rcx, [rsp+850h+var_810]
0x18003bd17  call    FormatRRASErrorString
0x18003bd1c  test    cs:byte_1800AA941, 8
0x18003bd23  jz      short loc_18003BD3D
0x18003bd25  lea     r8, [rsp+850h+var_810]
0x18003bd2a  lea     rdx, RasVpnIkeTraceInfo
0x18003bd31  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003bd38  call    McTemplateU0z_EventWriteTransfer
0x18003bd3d  xor     eax, eax
0x18003bd3f  jmp     short loc_18003BD8C
0x18003bd41  test    cs:byte_1800AA941, 8
0x18003bd48  jz      short loc_18003BD88
0x18003bd4a  mov     r8d, dword ptr [rsp+850h+Data]
0x18003bd4f  lea     rdx, aGotCertAuthFla; "Got cert auth flags from registry: %lu"
0x18003bd56  xor     eax, eax
0x18003bd58  lea     rcx, [rsp+850h+var_810]
0x18003bd5d  mov     word ptr [rsp+850h+var_810], ax
0x18003bd62  call    FormatRRASErrorString
0x18003bd67  test    cs:byte_1800AA941, 8
0x18003bd6e  jz      short loc_18003BD88
0x18003bd70  lea     r8, [rsp+850h+var_810]
0x18003bd75  lea     rdx, RasVpnIkeTraceInfo
0x18003bd7c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003bd83  call    McTemplateU0z_EventWriteTransfer
0x18003bd88  mov     eax, dword ptr [rsp+850h+Data]
0x18003bd8c  mov     rcx, [rbp+750h+var_10]
0x18003bd93  xor     rcx, rsp; StackCookie
0x18003bd96  call    __security_check_cookie
0x18003bd9b  mov     rbx, [rsp+850h+arg_0]
0x18003bda3  add     rsp, 850h
0x18003bdaa  pop     rbp
0x18003bdab  retn
```
