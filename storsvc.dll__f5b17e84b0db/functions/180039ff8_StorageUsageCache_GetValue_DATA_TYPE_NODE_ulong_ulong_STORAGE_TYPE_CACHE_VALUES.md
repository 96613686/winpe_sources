# StorageUsageCache::GetValue(_DATA_TYPE_NODE,ulong,ulong,_STORAGE_TYPE_CACHE_VALUES *)

- ea: `0x180039ff8`
- end: `0x18003a24b`
- name: `?GetValue@StorageUsageCache@@QEAAJW4_DATA_TYPE_NODE@@KKPEAU_STORAGE_TYPE_CACHE_VALUES@@@Z`
- size: `595`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800389c4`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x180012ce0`
- `0x180024638`
- `0x180030ab0`
- `0x180039ff8`
- `0x18003e95c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a21e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a21e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a1fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a20e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a1fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a20e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003a198`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003a198`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003a1db`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003a1db`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003a119`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003a119`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18003a138`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18003a138`

## string_xrefs

- `0x18003a0ce`: `CachedSizes`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorageUsageCache::GetValue(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5)
{
  __int64 v9; // rcx
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  BYTE Data[8]; // [rsp+80h] [rbp-80h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v17[137]; // [rsp+90h] [rbp-70h] BYREF
  GUID rguid; // [rsp+2B4h] [rbp+1B4h] BYREF
  WCHAR ValueName[8]; // [rsp+4F0h] [rbp+3F0h] BYREF
  OLECHAR sz[8]; // [rsp+500h] [rbp+400h] BYREF
  __int128 v21; // [rsp+510h] [rbp+410h]
  __int128 v22; // [rsp+520h] [rbp+420h]
  _OWORD v23[2]; // [rsp+530h] [rbp+430h]

  hKey = 0;
  phkResult = 0;
  memset_0(v17, 0, 0x458u);
  *(_QWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  wcscpy(ValueName, L"123");
  *(_OWORD *)sz = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v21 = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v22 = *(_OWORD *)L"000-0000-000000000000}";
  v23[0] = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)((char *)v23 + 14) = *(_OWORD *)L"000000}";
  Microsoft::WRL::Wrappers::CriticalSection::Lock(a1, &lpCriticalSection);
  *(_BYTE *)(a5 + 16) = 0;
  if ( (int)OpenStorageRegKey(HKEY_CURRENT_USER, (wchar_t *)L"CachedSizes", &hKey) >= 0 )
  {
    v17[0] = 1112;
    StorageService::GetStorageDeviceInfo(v9, 0, a3, a4, (__int64)v17);
    if ( StringFromGUID2(&rguid, sz, 39) >= 0
      && RegOpenKeyW(hKey, sz, &phkResult) >= 0
      && StringCchPrintfW(ValueName, 4u, L"%02d", a2) >= 0 )
    {
      cbData = 8;
      if ( !RegQueryValueExW(phkResult, ValueName, 0, &Type, Data, &cbData)
        && !RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, (PFILETIME)(a5 + 20)) )
      {
        *(_QWORD *)(a5 + 8) = 0;
        *(_QWORD *)a5 = *(_QWORD *)Data;
        *(_BYTE *)(a5 + 16) = 1;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( lpCriticalSection )
  {
    LeaveCriticalSection(lpCriticalSection);
    lpCriticalSection = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180039ff8  push    rbp
0x180039ffa  push    rbx
0x180039ffb  push    rsi
0x180039ffc  push    rdi
0x180039ffd  push    r12
0x180039fff  push    r14
0x18003a001  push    r15
0x18003a003  lea     rbp, [rsp-460h]
0x18003a00b  sub     rsp, 560h
0x18003a012  mov     rax, cs:__security_cookie
0x18003a019  xor     rax, rsp
0x18003a01c  mov     [rbp+490h+var_40], rax
0x18003a023  mov     r15d, r9d
0x18003a026  mov     r14d, r8d
0x18003a029  mov     esi, edx
0x18003a02b  mov     rbx, rcx
0x18003a02e  mov     rdi, [rbp+490h+arg_20]
0x18003a035  xor     r12d, r12d
0x18003a038  mov     [rsp+590h+hKey], r12
0x18003a03d  mov     [rsp+590h+phkResult], r12
0x18003a042  xor     edx, edx; Val
0x18003a044  mov     r8d, 458h; Size
0x18003a04a  lea     rcx, [rbp+490h+var_500]; void *
0x18003a04e  call    memset_0
0x18003a053  mov     qword ptr [rbp+490h+Data], r12
0x18003a057  mov     [rsp+590h+Type], r12d
0x18003a05c  mov     [rsp+590h+cbData], r12d
0x18003a061  mov     rax, 3300320031h
0x18003a06b  mov     qword ptr [rbp+490h+ValueName], rax
0x18003a072  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x18003a079  movaps  xmmword ptr [rbp+490h+sz], xmm0
0x18003a080  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x18003a087  movaps  [rbp+490h+var_80], xmm1
0x18003a08e  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x18003a095  movaps  [rbp+490h+var_70], xmm0
0x18003a09c  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x18003a0a3  movaps  xmmword ptr [rbp+490h+var_60], xmm1
0x18003a0aa  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x18003a0b1  movups  xmmword ptr [rbp+490h+var_60+0Eh], xmm0
0x18003a0b8  lea     rdx, [rbp+490h+lpCriticalSection]
0x18003a0bc  mov     rcx, rbx
0x18003a0bf  call    ?Lock@CriticalSection@Wrappers@WRL@Microsoft@@QEAA?AVSyncLockCriticalSection@Details@234@XZ; Microsoft::WRL::Wrappers::CriticalSection::Lock(void)
0x18003a0c4  nop
0x18003a0c5  mov     [rdi+10h], r12b
0x18003a0c9  lea     r8, [rsp+590h+hKey]; phkResult
0x18003a0ce  lea     rdx, aCachedsizes; "CachedSizes"
0x18003a0d5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003a0dc  call    ?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18003a0e1  test    eax, eax
0x18003a0e3  js      loc_18003A1F4
0x18003a0e9  mov     [rbp+490h+var_500], 458h
0x18003a0f0  lea     rax, [rbp+490h+var_500]
0x18003a0f4  mov     [rsp+590h+lpData], rax
0x18003a0f9  mov     r9d, r15d
0x18003a0fc  mov     r8d, r14d
0x18003a0ff  xor     edx, edx
0x18003a101  call    ?GetStorageDeviceInfo@StorageService@@QEAAJPEAXW4_STORAGE_DEVICE_TYPE@@KPEAU_STORAGE_DEVICE_INFO@@@Z; StorageService::GetStorageDeviceInfo(void *,_STORAGE_DEVICE_TYPE,ulong,_STORAGE_DEVICE_INFO *)
0x18003a106  lea     r8d, [r12+27h]; cchMax
0x18003a10b  lea     rdx, [rbp+490h+sz]; lpsz
0x18003a112  lea     rcx, [rbp+490h+rguid]; rguid
0x18003a119  call    cs:__imp_StringFromGUID2
0x18003a11f  test    eax, eax
0x18003a121  js      loc_18003A1F4
0x18003a127  lea     r8, [rsp+590h+phkResult]; phkResult
0x18003a12c  lea     rdx, [rbp+490h+sz]; lpSubKey
0x18003a133  mov     rcx, [rsp+590h+hKey]; hKey
0x18003a138  call    cs:__imp_RegOpenKeyW
0x18003a13e  test    eax, eax
0x18003a140  js      loc_18003A1F4
0x18003a146  mov     r9d, esi
0x18003a149  lea     r8, a02d; "%02d"
0x18003a150  lea     edx, [r12+4]; unsigned __int64
0x18003a155  lea     rcx, [rbp+490h+ValueName]; unsigned __int16 *
0x18003a15c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a161  test    eax, eax
0x18003a163  js      loc_18003A1F4
0x18003a169  mov     [rsp+590h+cbData], 8
0x18003a171  lea     rax, [rsp+590h+cbData]
0x18003a176  mov     [rsp+590h+lpcbData], rax; lpcbData
0x18003a17b  lea     rax, [rbp+490h+Data]
0x18003a17f  mov     [rsp+590h+lpData], rax; lpData
0x18003a184  lea     r9, [rsp+590h+Type]; lpType
0x18003a189  xor     r8d, r8d; lpReserved
0x18003a18c  lea     rdx, [rbp+490h+ValueName]; lpValueName
0x18003a193  mov     rcx, [rsp+590h+phkResult]; hKey
0x18003a198  call    cs:__imp_RegQueryValueExW
0x18003a19e  test    eax, eax
0x18003a1a0  jnz     short loc_18003A1F4
0x18003a1a2  lea     rax, [rdi+14h]
0x18003a1a6  mov     [rsp+590h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18003a1ab  mov     [rsp+590h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18003a1b0  mov     [rsp+590h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18003a1b5  mov     [rsp+590h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18003a1ba  mov     [rsp+590h+lpcValues], r12; lpcValues
0x18003a1bf  mov     [rsp+590h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18003a1c4  mov     [rsp+590h+lpcbData], r12; lpcbMaxSubKeyLen
0x18003a1c9  mov     [rsp+590h+lpData], r12; lpcSubKeys
0x18003a1ce  xor     r9d, r9d; lpReserved
0x18003a1d1  xor     r8d, r8d; lpcchClass
0x18003a1d4  xor     edx, edx; lpClass
0x18003a1d6  mov     rcx, [rsp+590h+phkResult]; hKey
0x18003a1db  call    cs:__imp_RegQueryInfoKeyW
0x18003a1e1  test    eax, eax
0x18003a1e3  jnz     short loc_18003A1F4
0x18003a1e5  mov     [rdi+8], r12
0x18003a1e9  mov     rax, qword ptr [rbp+490h+Data]
0x18003a1ed  mov     [rdi], rax
0x18003a1f0  mov     byte ptr [rdi+10h], 1
0x18003a1f4  mov     rcx, [rsp+590h+hKey]; hKey
0x18003a1f9  test    rcx, rcx
0x18003a1fc  jz      short loc_18003A204
0x18003a1fe  call    cs:__imp_RegCloseKey
0x18003a204  mov     rcx, [rsp+590h+phkResult]; hKey
0x18003a209  test    rcx, rcx
0x18003a20c  jz      short loc_18003A215
0x18003a20e  call    cs:__imp_RegCloseKey
0x18003a214  nop
0x18003a215  mov     rcx, [rbp+490h+lpCriticalSection]; lpCriticalSection
0x18003a219  test    rcx, rcx
0x18003a21c  jz      short loc_18003A228
0x18003a21e  call    cs:__imp_LeaveCriticalSection
0x18003a224  mov     [rbp+490h+lpCriticalSection], r12
0x18003a228  xor     eax, eax
0x18003a22a  mov     rcx, [rbp+490h+var_40]
0x18003a231  xor     rcx, rsp; StackCookie
0x18003a234  call    __security_check_cookie
0x18003a239  add     rsp, 560h
0x18003a240  pop     r15
0x18003a242  pop     r14
0x18003a244  pop     r12
0x18003a246  pop     rdi
0x18003a247  pop     rsi
0x18003a248  pop     rbx
0x18003a249  pop     rbp
0x18003a24a  retn
```
