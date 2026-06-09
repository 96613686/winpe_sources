# NdrpDisableClientHarden(void)

- ea: `0x1800a8a18`
- end: `0x1800a8b0b`
- name: `?NdrpDisableClientHarden@@YAHXZ`
- size: `243`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037d80`
- `0x180038030`

## callees

- `0x18003f0e0`
- `0x1800a8a18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a8a57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a8a57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8ad3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8ad3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a8ab2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a8ab2`

## string_xrefs

- `0x1800a8a49`: `Software\Microsoft\Rpc\SystemParameter001`

## pseudocode

```c
_BOOL8 NdrpDisableClientHarden(void)
{
  RPC_STATUS v0; // ebx
  struct _LIST_ENTRY *Flink; // r8
  LSTATUS ValueW; // eax
  HKEY v3; // rcx
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  v0 = dword_1800FE838;
  if ( dword_1800FE838 == -1 )
  {
    hkey = 0;
    v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Rpc\\SystemParameter001", 0, 0x20019u, &hkey);
    if ( v0 )
    {
      v3 = 0;
      hkey = 0;
    }
    else
    {
      Flink = NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[6].Flink;
      pcbData = 4;
      pvData = 0;
      ValueW = RegGetValueW(hkey, 0, (LPCWSTR)Flink, 0x18u, 0, &pvData, &pcbData);
      v3 = hkey;
      v0 = ValueW;
    }
    if ( v3 )
      RegCloseKey(v3);
    dword_1800FE838 = v0;
    if ( !v0 )
      return 1;
    if ( v0 != 2 )
      RpcRaiseException(v0);
  }
  return v0 == 0;
}

```

## disassembly

```asm
0x1800a8a18  push    rbx
0x1800a8a1a  sub     rsp, 40h
0x1800a8a1e  mov     ebx, cs:dword_1800FE838
0x1800a8a24  cmp     ebx, 0FFFFFFFFh
0x1800a8a27  jnz     loc_1800A8AFD
0x1800a8a2d  lea     rax, [rsp+48h+hkey]
0x1800a8a32  mov     [rsp+48h+hkey], 0
0x1800a8a3b  mov     r9d, 20019h; samDesired
0x1800a8a41  mov     [rsp+48h+phkResult], rax; phkResult
0x1800a8a46  xor     r8d, r8d; ulOptions
0x1800a8a49  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Rpc\\SystemParamet"...
0x1800a8a50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a8a57  call    cs:__imp_RegOpenKeyExW
0x1800a8a5e  nop     dword ptr [rax+rax+00h]
0x1800a8a63  mov     ebx, eax
0x1800a8a65  test    eax, eax
0x1800a8a67  jnz     short loc_1800A8AC7
0x1800a8a69  mov     rax, gs:60h
0x1800a8a72  lea     r9d, [rbx+18h]; dwFlags
0x1800a8a76  xor     edx, edx; lpSubKey
0x1800a8a78  mov     rcx, [rax+18h]
0x1800a8a7c  mov     rax, [rcx+10h]
0x1800a8a80  mov     rcx, [rsp+48h+hkey]; hkey
0x1800a8a85  mov     r8, [rax+60h]; lpValue
0x1800a8a89  lea     rax, [rsp+48h+arg_0]
0x1800a8a8e  mov     [rsp+48h+pcbData], rax; pcbData
0x1800a8a93  lea     rax, [rsp+48h+arg_8]
0x1800a8a98  mov     [rsp+48h+pvData], rax; pvData
0x1800a8a9d  mov     [rsp+48h+phkResult], 0; pdwType
0x1800a8aa6  mov     [rsp+48h+arg_0], 4
0x1800a8aae  mov     [rsp+48h+arg_8], ebx
0x1800a8ab2  call    cs:__imp_RegGetValueW
0x1800a8ab9  nop     dword ptr [rax+rax+00h]
0x1800a8abe  mov     rcx, [rsp+48h+hkey]
0x1800a8ac3  mov     ebx, eax
0x1800a8ac5  jmp     short loc_1800A8ACE
0x1800a8ac7  xor     ecx, ecx; hKey
0x1800a8ac9  mov     [rsp+48h+hkey], rcx
0x1800a8ace  test    rcx, rcx
0x1800a8ad1  jz      short loc_1800A8ADF
0x1800a8ad3  call    cs:__imp_RegCloseKey
0x1800a8ada  nop     dword ptr [rax+rax+00h]
0x1800a8adf  mov     cs:dword_1800FE838, ebx
0x1800a8ae5  test    ebx, ebx
0x1800a8ae7  jz      short loc_1800A8AF6
0x1800a8ae9  cmp     ebx, 2
0x1800a8aec  jz      short loc_1800A8AFD
0x1800a8aee  mov     ecx, ebx; exception
0x1800a8af0  call    RpcRaiseException
0x1800a8af6  mov     eax, 1
0x1800a8afb  jmp     short loc_1800A8B04
0x1800a8afd  xor     eax, eax
0x1800a8aff  test    ebx, ebx
0x1800a8b01  setz    al
0x1800a8b04  add     rsp, 40h
0x1800a8b08  pop     rbx
0x1800a8b09  retn
```
