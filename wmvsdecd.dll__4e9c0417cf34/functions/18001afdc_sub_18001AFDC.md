# sub_18001AFDC

- ea: `0x18001afdc`
- end: `0x18001b06f`
- name: `sub_18001AFDC`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001aa4c`

## callees

- `0x18001afdc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b05a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b05a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b044`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b044`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b012`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b012`

## pseudocode

```c
__int64 sub_18001AFDC()
{
  BYTE Data[8]; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF

  *(_DWORD *)Data = -1;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Scrunch", 0, 0xF003Fu, &hKey) )
    RegSetValueExW(hKey, L"Current Post Process Mode", 0, 4u, Data, 4u);
  if ( hKey )
    RegCloseKey(hKey);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18001afdc  sub     rsp, 48h
0x18001afe0  lea     rax, [rsp+48h+hKey]
0x18001afe5  mov     dword ptr [rsp+48h+Data], 0FFFFFFFFh
0x18001afed  mov     r9d, 0F003Fh; samDesired
0x18001aff3  mov     [rsp+48h+phkResult], rax; phkResult
0x18001aff8  xor     r8d, r8d; ulOptions
0x18001affb  mov     [rsp+48h+hKey], 0
0x18001b004  lea     rdx, SubKey; "Software\\Microsoft\\Scrunch"
0x18001b00b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001b012  call    cs:RegOpenKeyExW
0x18001b019  nop     dword ptr [rax+rax+00h]
0x18001b01e  test    eax, eax
0x18001b020  jnz     short loc_18001B050
0x18001b022  mov     rcx, [rsp+48h+hKey]; hKey
0x18001b027  lea     r9d, [rax+4]; dwType
0x18001b02b  lea     rax, [rsp+48h+Data]
0x18001b030  mov     [rsp+48h+cbData], r9d; cbData
0x18001b035  xor     r8d, r8d; Reserved
0x18001b038  mov     [rsp+48h+phkResult], rax; lpData
0x18001b03d  lea     rdx, aCurrentPostPro; "Current Post Process Mode"
0x18001b044  call    cs:RegSetValueExW
0x18001b04b  nop     dword ptr [rax+rax+00h]
0x18001b050  mov     rcx, [rsp+48h+hKey]; hKey
0x18001b055  test    rcx, rcx
0x18001b058  jz      short loc_18001B066
0x18001b05a  call    cs:RegCloseKey
0x18001b061  nop     dword ptr [rax+rax+00h]
0x18001b066  or      eax, 0FFFFFFFFh
0x18001b069  add     rsp, 48h
0x18001b06d  retn
```
