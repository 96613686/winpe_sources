# IsSharingEnabled

- ea: `0x180031fd4`
- end: `0x18003206d`
- name: `IsSharingEnabled`
- size: `153`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800326c0`
- `0x180032ad0`

## callees

- `0x180031fd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003205e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003205e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003200e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003200e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003204a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003204a`

## pseudocode

```c
__int64 IsSharingEnabled()
{
  unsigned int v0; // ebx
  int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v0 = 0;
  hKey = 0;
  Type = 0;
  Data = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Telephony\\Server",
          0,
          0xF003Fu,
          &hKey) )
  {
    cbData = 4;
    Data = 1;
    if ( !RegQueryValueExW(hKey, L"DisableSharing", 0, &Type, (LPBYTE)&Data, &cbData) )
      LOBYTE(v0) = Data == 0;
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x180031fd4  push    rbp
0x180031fd6  push    rbx
0x180031fd7  mov     rbp, rsp
0x180031fda  sub     rsp, 38h
0x180031fde  xor     ebx, ebx
0x180031fe0  mov     [rbp+hKey], 0
0x180031fe8  lea     rax, [rbp+hKey]
0x180031fec  mov     [rbp+Type], ebx
0x180031fef  mov     r9d, 0F003Fh; samDesired
0x180031ff5  mov     [rbp+Data], ebx
0x180031ff8  xor     r8d, r8d; ulOptions
0x180031ffb  mov     [rsp+38h+phkResult], rax; phkResult
0x180032000  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180032007  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003200e  call    cs:__imp_RegOpenKeyExW
0x180032014  test    eax, eax
0x180032016  jnz     short loc_180032064
0x180032018  mov     rcx, [rbp+hKey]; hKey
0x18003201c  lea     rax, [rbp+cbData]
0x180032020  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180032025  lea     r9, [rbp+Type]; lpType
0x180032029  lea     rax, [rbp+Data]
0x18003202d  mov     [rbp+cbData], 4
0x180032034  xor     r8d, r8d; lpReserved
0x180032037  mov     [rsp+38h+phkResult], rax; lpData
0x18003203c  lea     rdx, aDisablesharing; "DisableSharing"
0x180032043  mov     [rbp+Data], 1
0x18003204a  call    cs:__imp_RegQueryValueExW
0x180032050  test    eax, eax
0x180032052  jnz     short loc_18003205A
0x180032054  cmp     [rbp+Data], ebx
0x180032057  setz    bl
0x18003205a  mov     rcx, [rbp+hKey]; hKey
0x18003205e  call    cs:__imp_RegCloseKey
0x180032064  mov     eax, ebx
0x180032066  add     rsp, 38h
0x18003206a  pop     rbx
0x18003206b  pop     rbp
0x18003206c  retn
```
