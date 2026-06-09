# CSsdpCacheEntryManager::HrInitialize(void)

- ea: `0x18000bc38`
- end: `0x18000bd37`
- name: `?HrInitialize@CSsdpCacheEntryManager@@QEAAJXZ`
- size: `255`
- prototype: `__int64 __fastcall(CSsdpCacheEntryManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000a768`

## callees

- `0x18000bc38`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bcc0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bcc0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000bcab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000bcab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000bc77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000bc77`

## string_xrefs

- `0x18000bc6d`: `SYSTEM\CurrentControlSet\Services\SSDPSRV\Parameters`
- `0x18000bc8e`: `MaxCache`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntryManager::HrInitialize(CSsdpCacheEntryManager *this)
{
  __int64 v2; // r9
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF

  hKey = 0;
  Data = 4000;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "SYSTEM\\CurrentControlSet\\Services\\SSDPSRV\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( RegQueryValueExA(hKey, "MaxCache", 0, 0, (LPBYTE)&Data, &cbData) )
      Data = 4000;
    RegCloseKey(hKey);
  }
  v2 = Data;
  if ( Data <= 0xA )
  {
    v2 = 10;
    Data = 10;
  }
  if ( (unsigned int)v2 >= 0x7530 )
  {
    v2 = 30000;
    Data = 30000;
  }
  *((_DWORD *)this + 13) = v2;
  g_cMaxCache = v2;
  *((_DWORD *)this + 12) = 0;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v2);
  return 0;
}

```

## disassembly

```asm
0x18000bc38  mov     [rsp-8+arg_18], rbx
0x18000bc3d  push    rbp
0x18000bc3e  mov     rbp, rsp
0x18000bc41  sub     rsp, 30h
0x18000bc45  mov     rbx, rcx
0x18000bc48  mov     [rbp+hKey], 0
0x18000bc50  lea     rax, [rbp+hKey]
0x18000bc54  mov     [rbp+Data], 0FA0h
0x18000bc5b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bc62  mov     [rsp+30h+phkResult], rax; phkResult
0x18000bc67  mov     r9d, 20019h; samDesired
0x18000bc6d  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\SS"...
0x18000bc74  xor     r8d, r8d; ulOptions
0x18000bc77  call    cs:__imp_RegOpenKeyExA
0x18000bc7d  test    eax, eax
0x18000bc7f  jnz     short loc_18000BCC6
0x18000bc81  mov     rcx, [rbp+hKey]; hKey
0x18000bc85  lea     rax, [rbp+cbData]
0x18000bc89  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000bc8e  lea     rdx, aMaxcache; "MaxCache"
0x18000bc95  lea     rax, [rbp+Data]
0x18000bc99  mov     [rbp+cbData], 4
0x18000bca0  xor     r9d, r9d; lpType
0x18000bca3  mov     [rsp+30h+phkResult], rax; lpData
0x18000bca8  xor     r8d, r8d; lpReserved
0x18000bcab  call    cs:__imp_RegQueryValueExA
0x18000bcb1  test    eax, eax
0x18000bcb3  jz      short loc_18000BCBC
0x18000bcb5  mov     [rbp+Data], 0FA0h
0x18000bcbc  mov     rcx, [rbp+hKey]; hKey
0x18000bcc0  call    cs:__imp_RegCloseKey
0x18000bcc6  mov     r9d, [rbp+Data]
0x18000bcca  cmp     r9d, 0Ah
0x18000bcce  ja      short loc_18000BCDA
0x18000bcd0  mov     r9d, 0Ah
0x18000bcd6  mov     [rbp+Data], r9d
0x18000bcda  mov     eax, 7530h
0x18000bcdf  cmp     r9d, eax
0x18000bce2  jb      short loc_18000BCEA
0x18000bce4  mov     r9d, eax
0x18000bce7  mov     [rbp+Data], eax
0x18000bcea  mov     [rbx+34h], r9d
0x18000bcee  mov     cs:?g_cMaxCache@@3HA, r9d; int g_cMaxCache
0x18000bcf5  mov     dword ptr [rbx+30h], 0
0x18000bcfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd03  lea     rax, WPP_GLOBAL_Control
0x18000bd0a  cmp     rcx, rax
0x18000bd0d  jz      short loc_18000BD2A
0x18000bd0f  test    byte ptr [rcx+1Ch], 8
0x18000bd13  jz      short loc_18000BD2A
0x18000bd15  mov     rcx, [rcx+10h]
0x18000bd19  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000bd20  mov     edx, 3Ah ; ':'
0x18000bd25  call    WPP_SF_d
0x18000bd2a  mov     rbx, [rsp+30h+arg_18]
0x18000bd2f  xor     eax, eax
0x18000bd31  add     rsp, 30h
0x18000bd35  pop     rbp
0x18000bd36  retn
```
