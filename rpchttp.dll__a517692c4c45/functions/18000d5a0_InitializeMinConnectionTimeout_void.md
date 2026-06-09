# InitializeMinConnectionTimeout(void)

- ea: `0x18000d5a0`
- end: `0x18000d6aa`
- name: `?InitializeMinConnectionTimeout@@YAJXZ`
- size: `266`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c1a0`
- `0x18001b5d0`

## callees

- `0x18000d5a0`
- `0x18001e4a4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000d5de`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d5de`
- `ADVAPI32!RegCloseKey` at `0x18000d656`
- `ADVAPI32!RegCloseKey` at `0x18000d6a0`
- `ADVAPI32!RegCloseKey` at `0x18000d656`
- `ADVAPI32!RegCloseKey` at `0x18000d6a0`
- `ADVAPI32!RegGetValueW` at `0x18000d63f`
- `ADVAPI32!RegGetValueW` at `0x18000d63f`

## pseudocode

```c
__int64 InitializeMinConnectionTimeout(void)
{
  LSTATUS v0; // eax
  unsigned int ValueW; // ebx
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  hkey = 0;
  pcbData = 0;
  pvData = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows NT\\Rpc", 0, 0x20019u, &hkey);
  if ( v0 == 2 )
    return 0;
  if ( v0 )
  {
    CompRpcpErrorAddRecord(0xDu, v0, 0xBC2u);
    return 14;
  }
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"MinimumConnectionTimeout", 0x18u, 0, &pvData, &pcbData);
  if ( ValueW == 2 )
  {
    if ( hkey )
      RegCloseKey(hkey);
    return 0;
  }
  if ( ValueW || (unsigned int)(pvData - 90) > 0x37E6 )
    CompRpcpErrorAddRecord(0xDu, ValueW, 0xBC3u);
  else
    OverrideMinimumConnectionTimeout = 1000 * pvData;
  if ( hkey )
    RegCloseKey(hkey);
  return ValueW;
}

```

## disassembly

```asm
0x18000d5a0  mov     rax, rsp
0x18000d5a3  push    rbx
0x18000d5a4  sub     rsp, 40h
0x18000d5a8  mov     qword ptr [rax+18h], 0
0x18000d5b0  mov     r9d, 20019h; samDesired
0x18000d5b6  mov     dword ptr [rax+8], 0
0x18000d5bd  xor     r8d, r8d; ulOptions
0x18000d5c0  mov     dword ptr [rax+10h], 0
0x18000d5c7  lea     rax, [rax+18h]
0x18000d5cb  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x18000d5d2  mov     [rsp+48h+phkResult], rax; phkResult
0x18000d5d7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d5de  call    cs:__imp_RegOpenKeyExW
0x18000d5e4  cmp     eax, 2
0x18000d5e7  jz      short loc_18000D65C
0x18000d5e9  test    eax, eax
0x18000d5eb  jz      short loc_18000D606
0x18000d5ed  mov     r8d, 0BC2h; unsigned __int16
0x18000d5f3  mov     edx, eax; unsigned int
0x18000d5f5  mov     ecx, 0Dh; unsigned int
0x18000d5fa  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x18000d5ff  mov     eax, 0Eh
0x18000d604  jmp     short loc_18000D65E
0x18000d606  mov     rcx, [rsp+48h+hkey]; hkey
0x18000d60b  lea     rax, [rsp+48h+arg_0]
0x18000d610  mov     [rsp+48h+pcbData], rax; pcbData
0x18000d615  lea     r8, aMinimumconnect; "MinimumConnectionTimeout"
0x18000d61c  lea     rax, [rsp+48h+arg_8]
0x18000d621  mov     [rsp+48h+arg_0], 4
0x18000d629  mov     [rsp+48h+pvData], rax; pvData
0x18000d62e  mov     r9d, 18h; dwFlags
0x18000d634  xor     edx, edx; lpSubKey
0x18000d636  mov     [rsp+48h+phkResult], 0; pdwType
0x18000d63f  call    cs:__imp_RegGetValueW
0x18000d645  mov     ebx, eax
0x18000d647  cmp     eax, 2
0x18000d64a  jnz     short loc_18000D664
0x18000d64c  mov     rcx, [rsp+48h+hkey]; hKey
0x18000d651  test    rcx, rcx
0x18000d654  jz      short loc_18000D65C
0x18000d656  call    cs:__imp_RegCloseKey
0x18000d65c  xor     eax, eax
0x18000d65e  add     rsp, 40h
0x18000d662  pop     rbx
0x18000d663  retn
0x18000d664  test    ebx, ebx
0x18000d666  jnz     short loc_18000D684
0x18000d668  mov     ecx, [rsp+48h+arg_8]
0x18000d66c  lea     eax, [rcx-5Ah]
0x18000d66f  cmp     eax, 37E6h
0x18000d674  ja      short loc_18000D684
0x18000d676  imul    eax, ecx, 3E8h
0x18000d67c  mov     cs:?OverrideMinimumConnectionTimeout@@3KA, eax; ulong OverrideMinimumConnectionTimeout
0x18000d682  jmp     short loc_18000D696
0x18000d684  mov     r8d, 0BC3h; unsigned __int16
0x18000d68a  mov     edx, ebx; unsigned int
0x18000d68c  mov     ecx, 0Dh; unsigned int
0x18000d691  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x18000d696  mov     rcx, [rsp+48h+hkey]; hKey
0x18000d69b  test    rcx, rcx
0x18000d69e  jz      short loc_18000D6A6
0x18000d6a0  call    cs:__imp_RegCloseKey
0x18000d6a6  mov     eax, ebx
0x18000d6a8  jmp     short loc_18000D65E
```
