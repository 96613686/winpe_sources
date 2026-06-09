# GetMaxRpcSize(void)

- ea: `0x18005bdac`
- end: `0x18005be5b`
- name: `?GetMaxRpcSize@@YAXXZ`
- size: `175`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800258b4`

## callees

- `0x18005bdac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18005bde9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18005bde9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005be49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005be49`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18005be2a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18005be2a`

## pseudocode

```c
void GetMaxRpcSize(void)
{
  unsigned int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  hkey = 0;
  pvData = 0;
  pcbData = 4;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Rpc", 0, 0x20019u, &hkey) )
  {
    if ( !RegGetValueA(hkey, 0, "MaxRpcSize", 0x18u, 0, &pvData, &pcbData) )
      gMaxRpcSize = pvData;
    RegCloseKey(hkey);
  }
}

```

## disassembly

```asm
0x18005bdac  mov     rax, rsp
0x18005bdaf  sub     rsp, 48h
0x18005bdb3  mov     qword ptr [rax+18h], 0
0x18005bdbb  mov     r9d, 20019h; samDesired
0x18005bdc1  mov     dword ptr [rax+8], 0
0x18005bdc8  xor     r8d, r8d; ulOptions
0x18005bdcb  mov     dword ptr [rax+10h], 4
0x18005bdd2  lea     rax, [rax+18h]
0x18005bdd6  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Rpc"
0x18005bddd  mov     [rsp+48h+phkResult], rax; phkResult
0x18005bde2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005bde9  call    cs:__imp_RegOpenKeyExA
0x18005bdf0  nop     dword ptr [rax+rax+00h]
0x18005bdf5  test    eax, eax
0x18005bdf7  jnz     short loc_18005BE55
0x18005bdf9  mov     rcx, [rsp+48h+hkey]; hkey
0x18005bdfe  lea     rax, [rsp+48h+arg_8]
0x18005be03  mov     [rsp+48h+pcbData], rax; pcbData
0x18005be08  lea     r8, Value; "MaxRpcSize"
0x18005be0f  lea     rax, [rsp+48h+arg_0]
0x18005be14  mov     r9d, 18h; dwFlags
0x18005be1a  mov     [rsp+48h+pvData], rax; pvData
0x18005be1f  xor     edx, edx; lpSubKey
0x18005be21  mov     [rsp+48h+phkResult], 0; pdwType
0x18005be2a  call    cs:__imp_RegGetValueA
0x18005be31  nop     dword ptr [rax+rax+00h]
0x18005be36  test    eax, eax
0x18005be38  jnz     short loc_18005BE44
0x18005be3a  mov     eax, [rsp+48h+arg_0]
0x18005be3e  mov     cs:?gMaxRpcSize@@3KA, eax; ulong gMaxRpcSize
0x18005be44  mov     rcx, [rsp+48h+hkey]; hKey
0x18005be49  call    cs:__imp_RegCloseKey
0x18005be50  nop     dword ptr [rax+rax+00h]
0x18005be55  add     rsp, 48h
0x18005be59  retn
```
