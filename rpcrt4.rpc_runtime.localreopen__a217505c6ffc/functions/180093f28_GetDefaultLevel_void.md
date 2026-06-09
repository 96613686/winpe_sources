# GetDefaultLevel(void)

- ea: `0x180093f28`
- end: `0x180094006`
- name: `?GetDefaultLevel@@YAHXZ`
- size: `222`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180093efc`

## callees

- `0x180093f28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180093f65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180093f65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093fc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093fdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093fc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093fdf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180093fa6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180093fa6`

## string_xrefs

- `0x180093f52`: `Software\Microsoft\Rpc\SecurityService`

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
0x180093f28  mov     rax, rsp
0x180093f2b  sub     rsp, 48h
0x180093f2f  mov     qword ptr [rax+18h], 0
0x180093f37  mov     r9d, 20019h; samDesired
0x180093f3d  mov     dword ptr [rax+8], 0
0x180093f44  xor     r8d, r8d; ulOptions
0x180093f47  mov     dword ptr [rax+10h], 4
0x180093f4e  lea     rax, [rax+18h]
0x180093f52  lea     rdx, SubKey; "Software\\Microsoft\\Rpc\\SecurityServi"...
0x180093f59  mov     [rsp+48h+phkResult], rax; phkResult
0x180093f5e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180093f65  call    cs:__imp_RegOpenKeyExA
0x180093f6c  nop     dword ptr [rax+rax+00h]
0x180093f71  test    eax, eax
0x180093f73  jnz     short loc_180093FD2
0x180093f75  mov     rcx, [rsp+48h+hkey]; hkey
0x180093f7a  lea     rax, [rsp+48h+arg_8]
0x180093f7f  mov     [rsp+48h+pcbData], rax; pcbData
0x180093f84  lea     r8, aDefaultauthlev; "DefaultAuthLevel"
0x180093f8b  lea     rax, [rsp+48h+arg_0]
0x180093f90  mov     r9d, 18h; dwFlags
0x180093f96  mov     [rsp+48h+pvData], rax; pvData
0x180093f9b  xor     edx, edx; lpSubKey
0x180093f9d  mov     [rsp+48h+phkResult], 0; pdwType
0x180093fa6  call    cs:__imp_RegGetValueA
0x180093fad  nop     dword ptr [rax+rax+00h]
0x180093fb2  lea     ecx, [rax-3F3h]
0x180093fb8  cmp     ecx, 1
0x180093fbb  jbe     short loc_180093FDA
0x180093fbd  test    eax, eax
0x180093fbf  jz      short loc_180093FF2
0x180093fc1  mov     rcx, [rsp+48h+hkey]; hKey
0x180093fc6  call    cs:__imp_RegCloseKey
0x180093fcd  nop     dword ptr [rax+rax+00h]
0x180093fd2  xor     eax, eax
0x180093fd4  add     rsp, 48h
0x180093fd8  retn
0x180093fda  mov     rcx, [rsp+48h+hkey]; hKey
0x180093fdf  call    cs:__imp_RegCloseKey
0x180093fe6  nop     dword ptr [rax+rax+00h]
0x180093feb  mov     eax, 1
0x180093ff0  jmp     short loc_180093FD4
0x180093ff2  mov     edx, [rsp+48h+arg_0]
0x180093ff6  lea     ecx, [rdx-2]
0x180093ff9  cmp     ecx, 4
0x180093ffc  ja      short loc_180093FDA
0x180093ffe  mov     cs:?DefaultAuthLevel@@3KA, edx; ulong DefaultAuthLevel
0x180094004  jmp     short loc_180093FDA
```
