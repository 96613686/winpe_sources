# InitializeActAsWebFarm(void)

- ea: `0x18000d0cc`
- end: `0x18000d1c6`
- name: `?InitializeActAsWebFarm@@YAJXZ`
- size: `250`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b5d0`

## callees

- `0x18000d0cc`
- `0x18001e4a4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000d10a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d10a`
- `ADVAPI32!RegCloseKey` at `0x18000d182`
- `ADVAPI32!RegCloseKey` at `0x18000d1bc`
- `ADVAPI32!RegCloseKey` at `0x18000d182`
- `ADVAPI32!RegCloseKey` at `0x18000d1bc`
- `ADVAPI32!RegGetValueW` at `0x18000d16b`
- `ADVAPI32!RegGetValueW` at `0x18000d16b`

## pseudocode

```c
__int64 InitializeActAsWebFarm(void)
{
  LSTATUS v0; // eax
  LSTATUS ValueW; // eax
  unsigned int v3; // ebx
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  hkey = 0;
  pcbData = 0;
  pvData = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Rpc", 0, 0x20019u, &hkey);
  if ( v0 == 2 )
    return 0;
  if ( v0 )
  {
    CompRpcpErrorAddRecord(0xDu, v0, 0xBC2u);
    return 14;
  }
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"ActAsWebFarm", 0x18u, 0, &pvData, &pcbData);
  v3 = ValueW;
  if ( ValueW == 2 )
  {
    if ( hkey )
      RegCloseKey(hkey);
    return 0;
  }
  if ( ValueW )
    CompRpcpErrorAddRecord(0xDu, ValueW, 0xBC3u);
  else
    ActAsSeparateMachinesOnWebFarm = pvData;
  if ( hkey )
    RegCloseKey(hkey);
  return v3;
}

```

## disassembly

```asm
0x18000d0cc  mov     rax, rsp
0x18000d0cf  push    rbx
0x18000d0d0  sub     rsp, 40h
0x18000d0d4  mov     qword ptr [rax+18h], 0
0x18000d0dc  mov     r9d, 20019h; samDesired
0x18000d0e2  mov     dword ptr [rax+8], 0
0x18000d0e9  xor     r8d, r8d; ulOptions
0x18000d0ec  mov     dword ptr [rax+10h], 0
0x18000d0f3  lea     rax, [rax+18h]
0x18000d0f7  lea     rdx, SubKey; "Software\\Microsoft\\Rpc"
0x18000d0fe  mov     [rsp+48h+phkResult], rax; phkResult
0x18000d103  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d10a  call    cs:__imp_RegOpenKeyExW
0x18000d110  cmp     eax, 2
0x18000d113  jz      short loc_18000D188
0x18000d115  test    eax, eax
0x18000d117  jz      short loc_18000D132
0x18000d119  mov     r8d, 0BC2h; unsigned __int16
0x18000d11f  mov     edx, eax; unsigned int
0x18000d121  mov     ecx, 0Dh; unsigned int
0x18000d126  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x18000d12b  mov     eax, 0Eh
0x18000d130  jmp     short loc_18000D18A
0x18000d132  mov     rcx, [rsp+48h+hkey]; hkey
0x18000d137  lea     rax, [rsp+48h+arg_0]
0x18000d13c  mov     [rsp+48h+pcbData], rax; pcbData
0x18000d141  lea     r8, aActaswebfarm; "ActAsWebFarm"
0x18000d148  lea     rax, [rsp+48h+arg_8]
0x18000d14d  mov     [rsp+48h+arg_0], 4
0x18000d155  mov     [rsp+48h+pvData], rax; pvData
0x18000d15a  mov     r9d, 18h; dwFlags
0x18000d160  xor     edx, edx; lpSubKey
0x18000d162  mov     [rsp+48h+phkResult], 0; pdwType
0x18000d16b  call    cs:__imp_RegGetValueW
0x18000d171  mov     ebx, eax
0x18000d173  cmp     eax, 2
0x18000d176  jnz     short loc_18000D190
0x18000d178  mov     rcx, [rsp+48h+hkey]; hKey
0x18000d17d  test    rcx, rcx
0x18000d180  jz      short loc_18000D188
0x18000d182  call    cs:__imp_RegCloseKey
0x18000d188  xor     eax, eax
0x18000d18a  add     rsp, 40h
0x18000d18e  pop     rbx
0x18000d18f  retn
0x18000d190  test    ebx, ebx
0x18000d192  jnz     short loc_18000D1A0
0x18000d194  mov     eax, [rsp+48h+arg_8]
0x18000d198  mov     cs:?ActAsSeparateMachinesOnWebFarm@@3HA, eax; int ActAsSeparateMachinesOnWebFarm
0x18000d19e  jmp     short loc_18000D1B2
0x18000d1a0  mov     r8d, 0BC3h; unsigned __int16
0x18000d1a6  mov     edx, ebx; unsigned int
0x18000d1a8  mov     ecx, 0Dh; unsigned int
0x18000d1ad  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x18000d1b2  mov     rcx, [rsp+48h+hkey]; hKey
0x18000d1b7  test    rcx, rcx
0x18000d1ba  jz      short loc_18000D1C2
0x18000d1bc  call    cs:__imp_RegCloseKey
0x18000d1c2  mov     eax, ebx
0x18000d1c4  jmp     short loc_18000D18A
```
