# TSGetRegParams(HKEY__ *)

- ea: `0x18000a2bc`
- end: `0x18000a3d5`
- name: `?TSGetRegParams@@YAXPEAUHKEY__@@@Z`
- size: `281`
- prototype: `void __fastcall(HKEY)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017a40`
- `0x180017c30`

## callees

- `0x1800091a4`
- `0x18000a2bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a39d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a3be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a39d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a3be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a387`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a387`

## string_xrefs

- `0x18000a2da`: `UseCachedCRLOnlyAndIgnoreRevocationUnknownErrors`
- `0x18000a342`: `AllowEncryptionOracle`

## pseudocode

```c
void __fastcall TSGetRegParams(HKEY a1)
{
  HKEY v1; // rbx
  LSTATUS v2; // eax
  unsigned int v3; // r8d
  HKEY v4; // rdx
  _QWORD v5[3]; // [rsp+30h] [rbp-29h] BYREF
  int v6; // [rsp+48h] [rbp-11h]
  const wchar_t *v7; // [rsp+50h] [rbp-9h]
  unsigned int *v8; // [rsp+58h] [rbp-1h]
  __int64 v9; // [rsp+60h] [rbp+7h]
  int v10; // [rsp+68h] [rbp+Fh]
  const wchar_t *v11; // [rsp+70h] [rbp+17h]
  unsigned int *v12; // [rsp+78h] [rbp+1Fh]
  __int64 v13; // [rsp+80h] [rbp+27h]
  int v14; // [rsp+88h] [rbp+2Fh]
  const wchar_t *v15; // [rsp+90h] [rbp+37h]
  unsigned int *v16; // [rsp+98h] [rbp+3Fh]
  __int64 v17; // [rsp+A0h] [rbp+47h]
  int v18; // [rsp+A8h] [rbp+4Fh]
  HKEY hKey; // [rsp+C0h] [rbp+67h] BYREF

  v1 = g_hKeyParams;
  v5[0] = L"UseCachedCRLOnlyAndIgnoreRevocationUnknownErrors";
  hKey = 0;
  v6 = 1;
  v5[1] = &g_bTSParamCacheCRLandIgnoreUnknown;
  v10 = 1;
  v7 = L"IgnoreTSServerAuthEKU";
  v14 = 1;
  v8 = &g_bIgnoreTSAuthEKU;
  v11 = L"DisableLoopback";
  v12 = &g_bTSDisableLoopback;
  v15 = L"AllowEncryptionOracle";
  v16 = &g_dwEncryptionOracle;
  v17 = 1;
  v18 = 1;
  v5[2] = 0;
  v9 = 0;
  v13 = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\CredSSP\\Parameters",
         0,
         0x20019u,
         &hKey);
  v4 = hKey;
  if ( v2 && hKey )
  {
    RegCloseKey(hKey);
    v4 = 0;
    hKey = 0;
  }
  TSGetRegistryDwords(v1, v4, v3, (struct _TSPKG_REG_PARAMETER *)v5);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18000a2bc  mov     [rsp-8+arg_8], rbx
0x18000a2c1  mov     [rsp-8+hKey], rcx
0x18000a2c6  push    rbp
0x18000a2c7  lea     rbp, [rsp-57h]
0x18000a2cc  sub     rsp, 0B0h
0x18000a2d3  mov     rbx, cs:?g_hKeyParams@@3PEAUHKEY__@@EA; HKEY__ * g_hKeyParams
0x18000a2da  lea     rax, aUsecachedcrlon; "UseCachedCRLOnlyAndIgnoreRevocationUnkn"...
0x18000a2e1  mov     [rbp+57h+var_80], rax
0x18000a2e5  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000a2ec  mov     ecx, 1
0x18000a2f1  mov     [rbp+57h+hKey], 0
0x18000a2f9  lea     rax, ?g_bTSParamCacheCRLandIgnoreUnknown@@3KA; ulong g_bTSParamCacheCRLandIgnoreUnknown
0x18000a300  mov     [rbp+57h+var_68], ecx
0x18000a303  mov     [rbp+57h+var_78], rax
0x18000a307  mov     r9d, 20019h; samDesired
0x18000a30d  lea     rax, aIgnoretsserver; "IgnoreTSServerAuthEKU"
0x18000a314  mov     [rbp+57h+var_48], ecx
0x18000a317  mov     [rbp+57h+var_60], rax
0x18000a31b  xor     r8d, r8d; ulOptions
0x18000a31e  lea     rax, ?g_bIgnoreTSAuthEKU@@3KA; ulong g_bIgnoreTSAuthEKU
0x18000a325  mov     [rbp+57h+var_28], ecx
0x18000a328  mov     [rbp+57h+var_58], rax
0x18000a32c  lea     rax, aDisableloopbac; "DisableLoopback"
0x18000a333  mov     [rbp+57h+var_40], rax
0x18000a337  lea     rax, ?g_bTSDisableLoopback@@3KA; ulong g_bTSDisableLoopback
0x18000a33e  mov     [rbp+57h+var_38], rax
0x18000a342  lea     rax, aAllowencryptio; "AllowEncryptionOracle"
0x18000a349  mov     [rbp+57h+var_20], rax
0x18000a34d  lea     rax, ?g_dwEncryptionOracle@@3KA; ulong g_dwEncryptionOracle
0x18000a354  mov     [rbp+57h+var_18], rax
0x18000a358  lea     rax, [rbp+57h+hKey]
0x18000a35c  mov     [rbp+57h+var_10], rcx
0x18000a360  mov     [rbp+57h+var_8], ecx
0x18000a363  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a36a  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18000a36f  mov     [rbp+57h+var_70], 0
0x18000a377  mov     [rbp+57h+var_50], 0
0x18000a37f  mov     [rbp+57h+var_30], 0
0x18000a387  call    cs:__imp_RegOpenKeyExW
0x18000a38d  mov     rdx, [rbp+57h+hKey]
0x18000a391  test    eax, eax
0x18000a393  jz      short loc_18000A3A9
0x18000a395  test    rdx, rdx
0x18000a398  jz      short loc_18000A3A9
0x18000a39a  mov     rcx, rdx; hKey
0x18000a39d  call    cs:__imp_RegCloseKey
0x18000a3a3  xor     edx, edx; HKEY
0x18000a3a5  mov     [rbp+57h+hKey], rdx
0x18000a3a9  lea     r9, [rbp+57h+var_80]; struct _TSPKG_REG_PARAMETER *
0x18000a3ad  mov     rcx, rbx; hKey
0x18000a3b0  call    ?TSGetRegistryDwords@@YAJPEAUHKEY__@@0KPEAU_TSPKG_REG_PARAMETER@@@Z; TSGetRegistryDwords(HKEY__ *,HKEY__ *,ulong,_TSPKG_REG_PARAMETER *)
0x18000a3b5  mov     rcx, [rbp+57h+hKey]; hKey
0x18000a3b9  test    rcx, rcx
0x18000a3bc  jz      short loc_18000A3C4
0x18000a3be  call    cs:__imp_RegCloseKey
0x18000a3c4  mov     rbx, [rsp+0B0h+arg_8]
0x18000a3cc  add     rsp, 0B0h
0x18000a3d3  pop     rbp
0x18000a3d4  retn
```
