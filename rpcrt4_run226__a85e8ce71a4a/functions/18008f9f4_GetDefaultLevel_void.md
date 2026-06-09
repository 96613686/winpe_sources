# GetDefaultLevel(void)

- ea: `0x18008f9f4`
- end: `0x18008fab9`
- name: `?GetDefaultLevel@@YAHXZ`
- size: `197`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008f9c8`

## callees

- `0x18008f9f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18008fa31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18008fa31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fa86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fa98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fa86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fa98`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18008fa6c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18008fa6c`

## string_xrefs

- `0x18008fa1e`: `Software\Microsoft\Rpc\SecurityService`

## pseudocode

```c
__int64 GetDefaultLevel(void)
{
  LSTATUS ValueA; // eax
  unsigned int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  hkey = 0;
  pvData = 0;
  pcbData = 4;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Rpc\\SecurityService", 0, 0x20019u, &hkey) )
    return 0;
  ValueA = RegGetValueA(hkey, 0, "DefaultAuthLevel", 0x18u, 0, &pvData, &pcbData);
  if ( (unsigned int)(ValueA - 1011) > 1 )
  {
    if ( ValueA )
    {
      RegCloseKey(hkey);
      return 0;
    }
    if ( pvData - 2 <= 4 )
      DefaultAuthLevel = pvData;
  }
  RegCloseKey(hkey);
  return 1;
}

```

## disassembly

```asm
0x18008f9f4  mov     rax, rsp
0x18008f9f7  sub     rsp, 48h
0x18008f9fb  mov     qword ptr [rax+18h], 0
0x18008fa03  mov     r9d, 20019h; samDesired
0x18008fa09  mov     dword ptr [rax+8], 0
0x18008fa10  xor     r8d, r8d; ulOptions
0x18008fa13  mov     dword ptr [rax+10h], 4
0x18008fa1a  lea     rax, [rax+18h]
0x18008fa1e  lea     rdx, SubKey; "Software\\Microsoft\\Rpc\\SecurityServi"...
0x18008fa25  mov     [rsp+48h+phkResult], rax; phkResult
0x18008fa2a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008fa31  call    cs:__imp_RegOpenKeyExA
0x18008fa37  test    eax, eax
0x18008fa39  jnz     short loc_18008FA8C
0x18008fa3b  mov     rcx, [rsp+48h+hkey]; hkey
0x18008fa40  lea     rax, [rsp+48h+arg_8]
0x18008fa45  mov     [rsp+48h+pcbData], rax; pcbData
0x18008fa4a  lea     r8, aDefaultauthlev; "DefaultAuthLevel"
0x18008fa51  lea     rax, [rsp+48h+arg_0]
0x18008fa56  mov     r9d, 18h; dwFlags
0x18008fa5c  mov     [rsp+48h+pvData], rax; pvData
0x18008fa61  xor     edx, edx; lpSubKey
0x18008fa63  mov     [rsp+48h+phkResult], 0; pdwType
0x18008fa6c  call    cs:__imp_RegGetValueA
0x18008fa72  lea     ecx, [rax-3F3h]
0x18008fa78  cmp     ecx, 1
0x18008fa7b  jbe     short loc_18008FA93
0x18008fa7d  test    eax, eax
0x18008fa7f  jz      short loc_18008FAA5
0x18008fa81  mov     rcx, [rsp+48h+hkey]; hKey
0x18008fa86  call    cs:__imp_RegCloseKey
0x18008fa8c  xor     eax, eax
0x18008fa8e  add     rsp, 48h
0x18008fa92  retn
0x18008fa93  mov     rcx, [rsp+48h+hkey]; hKey
0x18008fa98  call    cs:__imp_RegCloseKey
0x18008fa9e  mov     eax, 1
0x18008faa3  jmp     short loc_18008FA8E
0x18008faa5  mov     edx, [rsp+48h+arg_0]
0x18008faa9  lea     ecx, [rdx-2]
0x18008faac  cmp     ecx, 4
0x18008faaf  ja      short loc_18008FA93
0x18008fab1  mov     cs:?DefaultAuthLevel@@3KA, edx; ulong DefaultAuthLevel
0x18008fab7  jmp     short loc_18008FA93
```
