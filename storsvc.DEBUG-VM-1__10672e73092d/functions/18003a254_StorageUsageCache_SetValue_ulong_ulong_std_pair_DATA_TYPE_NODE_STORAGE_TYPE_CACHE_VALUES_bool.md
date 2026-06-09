# StorageUsageCache::SetValue(ulong,ulong,std::pair<_DATA_TYPE_NODE,_STORAGE_TYPE_CACHE_VALUES> &,bool)

- ea: `0x18003a254`
- end: `0x18003a456`
- name: `?SetValue@StorageUsageCache@@QEAAJKKAEAU?$pair@W4_DATA_TYPE_NODE@@U_STORAGE_TYPE_CACHE_VALUES@@@std@@_N@Z`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800386f0`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x180012ce0`
- `0x180024638`
- `0x180030ab0`
- `0x18003a254`
- `0x18003e95c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a428`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a428`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a3f7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a3f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a407`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a417`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a407`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a417`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003a3cb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003a3cb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003a362`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003a362`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003a381`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003a381`

## string_xrefs

- `0x18003a314`: `CachedSizes`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorageUsageCache::SetValue(__int64 a1, unsigned int a2, unsigned int a3, const BYTE *a4, char a5)
{
  __int64 v9; // rcx
  LSTATUS v10; // eax
  bool v11; // sf
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v16[137]; // [rsp+50h] [rbp-B0h] BYREF
  GUID rguid; // [rsp+274h] [rbp+174h] BYREF
  WCHAR ValueName[8]; // [rsp+4B0h] [rbp+3B0h] BYREF
  OLECHAR sz[8]; // [rsp+4C0h] [rbp+3C0h] BYREF
  __int128 v20; // [rsp+4D0h] [rbp+3D0h]
  __int128 v21; // [rsp+4E0h] [rbp+3E0h]
  _OWORD v22[2]; // [rsp+4F0h] [rbp+3F0h]

  memset_0(v16, 0, 0x458u);
  hKey = 0;
  phkResult = 0;
  wcscpy(ValueName, L"123");
  *(_OWORD *)sz = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v20 = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v21 = *(_OWORD *)L"000-0000-000000000000}";
  v22[0] = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)((char *)v22 + 14) = *(_OWORD *)L"000000}";
  Microsoft::WRL::Wrappers::CriticalSection::Lock(a1, lpCriticalSection);
  if ( (int)OpenStorageRegKey(HKEY_CURRENT_USER, (wchar_t *)L"CachedSizes", &hKey) >= 0 )
  {
    v16[0] = 1112;
    StorageService::GetStorageDeviceInfo(v9, 0, a2, a3, (__int64)v16);
    if ( StringFromGUID2(&rguid, sz, 39) )
    {
      v10 = RegCreateKeyW(hKey, sz, &phkResult);
      v11 = v10 < 0;
      if ( v10 > 0 )
        v11 = 1;
      if ( !v11 && StringCchPrintfW(ValueName, 4u, L"%02d", *(unsigned int *)a4) >= 0 )
      {
        if ( a5 )
          RegDeleteValueW(phkResult, ValueName);
        RegSetValueExW(phkResult, ValueName, 0, 0xBu, a4 + 8, 8u);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( lpCriticalSection[0] )
  {
    LeaveCriticalSection(lpCriticalSection[0]);
    lpCriticalSection[0] = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18003a254  push    rbp
0x18003a256  push    rbx
0x18003a257  push    rsi
0x18003a258  push    rdi
0x18003a259  push    r14
0x18003a25b  lea     rbp, [rsp-420h]
0x18003a263  sub     rsp, 520h
0x18003a26a  mov     rax, cs:__security_cookie
0x18003a271  xor     rax, rsp
0x18003a274  mov     [rbp+440h+var_30], rax
0x18003a27b  mov     rdi, r9
0x18003a27e  mov     r14d, r8d
0x18003a281  mov     esi, edx
0x18003a283  mov     rbx, rcx
0x18003a286  xor     edx, edx; Val
0x18003a288  mov     r8d, 458h; Size
0x18003a28e  lea     rcx, [rsp+540h+var_4F0]; void *
0x18003a293  call    memset_0
0x18003a298  mov     [rsp+540h+hKey], 0
0x18003a2a1  mov     [rsp+540h+phkResult], 0
0x18003a2aa  mov     rax, 3300320031h
0x18003a2b4  mov     qword ptr [rbp+440h+ValueName], rax
0x18003a2bb  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x18003a2c2  movaps  xmmword ptr [rbp+440h+sz], xmm0
0x18003a2c9  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x18003a2d0  movaps  [rbp+440h+var_70], xmm1
0x18003a2d7  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x18003a2de  movaps  [rbp+440h+var_60], xmm0
0x18003a2e5  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x18003a2ec  movaps  xmmword ptr [rbp+440h+var_50], xmm1
0x18003a2f3  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x18003a2fa  movups  xmmword ptr [rbp+440h+var_50+0Eh], xmm0
0x18003a301  lea     rdx, [rsp+540h+lpCriticalSection]
0x18003a306  mov     rcx, rbx
0x18003a309  call    ?Lock@CriticalSection@Wrappers@WRL@Microsoft@@QEAA?AVSyncLockCriticalSection@Details@234@XZ; Microsoft::WRL::Wrappers::CriticalSection::Lock(void)
0x18003a30e  nop
0x18003a30f  lea     r8, [rsp+540h+hKey]; phkResult
0x18003a314  lea     rdx, aCachedsizes; "CachedSizes"
0x18003a31b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003a322  call    ?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18003a327  test    eax, eax
0x18003a329  js      loc_18003A3FD
0x18003a32f  mov     [rsp+540h+var_4F0], 458h
0x18003a337  lea     rax, [rsp+540h+var_4F0]
0x18003a33c  mov     [rsp+540h+lpData], rax
0x18003a341  mov     r9d, r14d
0x18003a344  mov     r8d, esi
0x18003a347  xor     edx, edx
0x18003a349  call    ?GetStorageDeviceInfo@StorageService@@QEAAJPEAXW4_STORAGE_DEVICE_TYPE@@KPEAU_STORAGE_DEVICE_INFO@@@Z; StorageService::GetStorageDeviceInfo(void *,_STORAGE_DEVICE_TYPE,ulong,_STORAGE_DEVICE_INFO *)
0x18003a34e  mov     r8d, 27h ; '''; cchMax
0x18003a354  lea     rdx, [rbp+440h+sz]; lpsz
0x18003a35b  lea     rcx, [rbp+440h+rguid]; rguid
0x18003a362  call    cs:__imp_StringFromGUID2
0x18003a368  test    eax, eax
0x18003a36a  jz      loc_18003A3FD
0x18003a370  lea     r8, [rsp+540h+phkResult]; phkResult
0x18003a375  lea     rdx, [rbp+440h+sz]; lpSubKey
0x18003a37c  mov     rcx, [rsp+540h+hKey]; hKey
0x18003a381  call    cs:__imp_RegCreateKeyW
0x18003a387  test    eax, eax
0x18003a389  jle     short loc_18003A395
0x18003a38b  movzx   eax, ax
0x18003a38e  or      eax, 80070000h
0x18003a393  test    eax, eax
0x18003a395  js      short loc_18003A3FD
0x18003a397  mov     r9d, [rdi]
0x18003a39a  lea     r8, a02d; "%02d"
0x18003a3a1  mov     edx, 4; unsigned __int64
0x18003a3a6  lea     rcx, [rbp+440h+ValueName]; unsigned __int16 *
0x18003a3ad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a3b2  test    eax, eax
0x18003a3b4  js      short loc_18003A3FD
0x18003a3b6  cmp     [rbp+440h+arg_20], 0
0x18003a3bd  jz      short loc_18003A3D1
0x18003a3bf  lea     rdx, [rbp+440h+ValueName]; lpValueName
0x18003a3c6  mov     rcx, [rsp+540h+phkResult]; hKey
0x18003a3cb  call    cs:__imp_RegDeleteValueW
0x18003a3d1  lea     rax, [rdi+8]
0x18003a3d5  mov     [rsp+540h+cbData], 8; cbData
0x18003a3dd  mov     [rsp+540h+lpData], rax; lpData
0x18003a3e2  mov     r9d, 0Bh; dwType
0x18003a3e8  xor     r8d, r8d; Reserved
0x18003a3eb  lea     rdx, [rbp+440h+ValueName]; lpValueName
0x18003a3f2  mov     rcx, [rsp+540h+phkResult]; hKey
0x18003a3f7  call    cs:__imp_RegSetValueExW
0x18003a3fd  mov     rcx, [rsp+540h+hKey]; hKey
0x18003a402  test    rcx, rcx
0x18003a405  jz      short loc_18003A40D
0x18003a407  call    cs:__imp_RegCloseKey
0x18003a40d  mov     rcx, [rsp+540h+phkResult]; hKey
0x18003a412  test    rcx, rcx
0x18003a415  jz      short loc_18003A41E
0x18003a417  call    cs:__imp_RegCloseKey
0x18003a41d  nop
0x18003a41e  mov     rcx, [rsp+540h+lpCriticalSection]; lpCriticalSection
0x18003a423  test    rcx, rcx
0x18003a426  jz      short loc_18003A437
0x18003a428  call    cs:__imp_LeaveCriticalSection
0x18003a42e  mov     [rsp+540h+lpCriticalSection], 0
0x18003a437  xor     eax, eax
0x18003a439  mov     rcx, [rbp+440h+var_30]
0x18003a440  xor     rcx, rsp; StackCookie
0x18003a443  call    __security_check_cookie
0x18003a448  add     rsp, 520h
0x18003a44f  pop     r14
0x18003a451  pop     rdi
0x18003a452  pop     rsi
0x18003a453  pop     rbx
0x18003a454  pop     rbp
0x18003a455  retn
```
