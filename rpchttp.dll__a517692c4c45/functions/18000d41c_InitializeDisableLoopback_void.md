# InitializeDisableLoopback(void)

- ea: `0x18000d41c`
- end: `0x18000d4f4`
- name: `?InitializeDisableLoopback@@YAJXZ`
- size: `216`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c8c0`
- `0x18001b5d0`

## callees

- `0x18000d41c`
- `0x18001e4a4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000d45a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d45a`
- `ADVAPI32!RegCloseKey` at `0x18000d485`
- `ADVAPI32!RegCloseKey` at `0x18000d485`
- `ADVAPI32!RegGetValueW` at `0x18000d4cc`
- `ADVAPI32!RegGetValueW` at `0x18000d4cc`

## pseudocode

```c
__int64 InitializeDisableLoopback(void)
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  LSTATUS ValueW; // eax
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  hKey = 0;
  pcbData = 0;
  pvData = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Rpc", 0, 0x20019u, &hKey);
  if ( v0 )
  {
    CompRpcpErrorAddRecord(0xDu, v0, 0xFFAu);
LABEL_3:
    v1 = 14;
    goto LABEL_4;
  }
  pcbData = 4;
  ValueW = RegGetValueW(hKey, 0, L"DisableTcpLoopbackToNpfsMapping", 0x18u, 0, &pvData, &pcbData);
  v1 = ValueW;
  if ( ValueW )
  {
    if ( ValueW == 2 )
      v1 = 0;
  }
  else
  {
    if ( !pvData )
      goto LABEL_3;
    HTTP2DisableLoopbackNPFS = 1;
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x18000d41c  mov     rax, rsp
0x18000d41f  push    rbx
0x18000d420  sub     rsp, 40h
0x18000d424  mov     qword ptr [rax+18h], 0
0x18000d42c  mov     r9d, 20019h; samDesired
0x18000d432  mov     dword ptr [rax+8], 0
0x18000d439  xor     r8d, r8d; ulOptions
0x18000d43c  mov     dword ptr [rax+10h], 0
0x18000d443  lea     rax, [rax+18h]
0x18000d447  lea     rdx, SubKey; "Software\\Microsoft\\Rpc"
0x18000d44e  mov     [rsp+48h+phkResult], rax; phkResult
0x18000d453  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d45a  call    cs:__imp_RegOpenKeyExW
0x18000d460  test    eax, eax
0x18000d462  jz      short loc_18000D493
0x18000d464  mov     r8d, 0FFAh; unsigned __int16
0x18000d46a  mov     edx, eax; unsigned int
0x18000d46c  mov     ecx, 0Dh; unsigned int
0x18000d471  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x18000d476  mov     ebx, 0Eh
0x18000d47b  mov     rcx, [rsp+48h+hKey]; hKey
0x18000d480  test    rcx, rcx
0x18000d483  jz      short loc_18000D48B
0x18000d485  call    cs:__imp_RegCloseKey
0x18000d48b  mov     eax, ebx
0x18000d48d  add     rsp, 40h
0x18000d491  pop     rbx
0x18000d492  retn
0x18000d493  mov     rcx, [rsp+48h+hKey]; hkey
0x18000d498  lea     rax, [rsp+48h+arg_0]
0x18000d49d  mov     [rsp+48h+pcbData], rax; pcbData
0x18000d4a2  lea     r8, aDisabletcploop; "DisableTcpLoopbackToNpfsMapping"
0x18000d4a9  lea     rax, [rsp+48h+arg_8]
0x18000d4ae  mov     [rsp+48h+arg_0], 4
0x18000d4b6  mov     [rsp+48h+pvData], rax; pvData
0x18000d4bb  mov     r9d, 18h; dwFlags
0x18000d4c1  xor     edx, edx; lpSubKey
0x18000d4c3  mov     [rsp+48h+phkResult], 0; pdwType
0x18000d4cc  call    cs:__imp_RegGetValueW
0x18000d4d2  mov     ebx, eax
0x18000d4d4  test    eax, eax
0x18000d4d6  jz      short loc_18000D4E1
0x18000d4d8  cmp     eax, 2
0x18000d4db  jnz     short loc_18000D47B
0x18000d4dd  xor     ebx, ebx
0x18000d4df  jmp     short loc_18000D47B
0x18000d4e1  cmp     [rsp+48h+arg_8], 0
0x18000d4e6  jz      short loc_18000D476
0x18000d4e8  mov     cs:?HTTP2DisableLoopbackNPFS@@3HA, 1; int HTTP2DisableLoopbackNPFS
0x18000d4f2  jmp     short loc_18000D47B
```
