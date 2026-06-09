# CSsdpCacheEntryManager::HrInitialize(void)

- ea: `0x18000d6f4`
- end: `0x18000d806`
- name: `?HrInitialize@CSsdpCacheEntryManager@@QEAAJXZ`
- size: `274`
- prototype: `__int64 __fastcall(CSsdpCacheEntryManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000c078`

## callees

- `0x18000d6f4`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d788`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d788`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000d76d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000d76d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000d733`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000d733`

## string_xrefs

- `0x18000d729`: `SYSTEM\CurrentControlSet\Services\SSDPSRV\Parameters`
- `0x18000d750`: `MaxCache`

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
0x18000d6f4  mov     [rsp-8+arg_18], rbx
0x18000d6f9  push    rbp
0x18000d6fa  mov     rbp, rsp
0x18000d6fd  sub     rsp, 30h
0x18000d701  mov     rbx, rcx
0x18000d704  mov     [rbp+hKey], 0
0x18000d70c  lea     rax, [rbp+hKey]
0x18000d710  mov     [rbp+Data], 0FA0h
0x18000d717  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d71e  mov     [rsp+30h+phkResult], rax; phkResult
0x18000d723  mov     r9d, 20019h; samDesired
0x18000d729  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\SS"...
0x18000d730  xor     r8d, r8d; ulOptions
0x18000d733  call    cs:__imp_RegOpenKeyExA
0x18000d73a  nop     dword ptr [rax+rax+00h]
0x18000d73f  test    eax, eax
0x18000d741  jnz     short loc_18000D794
0x18000d743  mov     rcx, [rbp+hKey]; hKey
0x18000d747  lea     rax, [rbp+cbData]
0x18000d74b  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000d750  lea     rdx, aMaxcache; "MaxCache"
0x18000d757  lea     rax, [rbp+Data]
0x18000d75b  mov     [rbp+cbData], 4
0x18000d762  xor     r9d, r9d; lpType
0x18000d765  mov     [rsp+30h+phkResult], rax; lpData
0x18000d76a  xor     r8d, r8d; lpReserved
0x18000d76d  call    cs:__imp_RegQueryValueExA
0x18000d774  nop     dword ptr [rax+rax+00h]
0x18000d779  test    eax, eax
0x18000d77b  jz      short loc_18000D784
0x18000d77d  mov     [rbp+Data], 0FA0h
0x18000d784  mov     rcx, [rbp+hKey]; hKey
0x18000d788  call    cs:__imp_RegCloseKey
0x18000d78f  nop     dword ptr [rax+rax+00h]
0x18000d794  mov     r9d, [rbp+Data]
0x18000d798  cmp     r9d, 0Ah
0x18000d79c  ja      short loc_18000D7A8
0x18000d79e  mov     r9d, 0Ah
0x18000d7a4  mov     [rbp+Data], r9d
0x18000d7a8  mov     eax, 7530h
0x18000d7ad  cmp     r9d, eax
0x18000d7b0  jb      short loc_18000D7B8
0x18000d7b2  mov     r9d, eax
0x18000d7b5  mov     [rbp+Data], eax
0x18000d7b8  mov     [rbx+34h], r9d
0x18000d7bc  mov     cs:?g_cMaxCache@@3HA, r9d; int g_cMaxCache
0x18000d7c3  mov     dword ptr [rbx+30h], 0
0x18000d7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7d1  lea     rax, WPP_GLOBAL_Control
0x18000d7d8  cmp     rcx, rax
0x18000d7db  jz      short loc_18000D7F8
0x18000d7dd  test    byte ptr [rcx+1Ch], 8
0x18000d7e1  jz      short loc_18000D7F8
0x18000d7e3  mov     rcx, [rcx+10h]
0x18000d7e7  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000d7ee  mov     edx, 3Ah ; ':'
0x18000d7f3  call    WPP_SF_d
0x18000d7f8  mov     rbx, [rsp+30h+arg_18]
0x18000d7fd  xor     eax, eax
0x18000d7ff  add     rsp, 30h
0x18000d803  pop     rbp
0x18000d804  retn
```
