# Server2003NegotiateDisable(ulong *)

- ea: `0x180097c7c`
- end: `0x180097d2c`
- name: `?Server2003NegotiateDisable@@YAJPEAK@Z`
- size: `176`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059504`

## callees

- `0x180097c7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097cc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097cc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180097d14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180097d14`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180097d07`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180097d07`

## pseudocode

```c
LSTATUS __fastcall Server2003NegotiateDisable(unsigned int *a1)
{
  LSTATUS result; // eax
  LSTATUS ValueA; // ebx
  unsigned int pvData; // [rsp+58h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+68h] [rbp+20h] BYREF

  hkey = 0;
  pvData = 0;
  pcbData = 4;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows NT\\Rpc", 0, 0x20019u, &hkey);
  if ( !result )
  {
    ValueA = RegGetValueA(hkey, 0, "Server2003NegotiateDisable", 0x18u, 0, &pvData, &pcbData);
    RegCloseKey(hkey);
    if ( ValueA )
    {
      return ValueA;
    }
    else
    {
      *a1 = pvData;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180097c7c  mov     rax, rsp
0x180097c7f  mov     [rax+8], rbx
0x180097c83  push    rdi
0x180097c84  sub     rsp, 40h
0x180097c88  mov     qword ptr [rax+20h], 0
0x180097c90  mov     rdi, rcx
0x180097c93  mov     dword ptr [rax+10h], 0
0x180097c9a  mov     r9d, 20019h; samDesired
0x180097ca0  mov     dword ptr [rax+18h], 4
0x180097ca7  lea     rax, [rax+20h]
0x180097cab  xor     r8d, r8d; ulOptions
0x180097cae  mov     [rsp+48h+phkResult], rax; phkResult
0x180097cb3  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180097cba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180097cc1  call    cs:__imp_RegOpenKeyExW
0x180097cc7  test    eax, eax
0x180097cc9  jz      short loc_180097CD6
0x180097ccb  mov     rbx, [rsp+48h+arg_0]
0x180097cd0  add     rsp, 40h
0x180097cd4  pop     rdi
0x180097cd5  retn
0x180097cd6  mov     rcx, [rsp+48h+hkey]; hkey
0x180097cdb  lea     rax, [rsp+48h+arg_10]
0x180097ce0  mov     [rsp+48h+pcbData], rax; pcbData
0x180097ce5  lea     r8, aServer2003nego; "Server2003NegotiateDisable"
0x180097cec  lea     rax, [rsp+48h+arg_8]
0x180097cf1  mov     r9d, 18h; dwFlags
0x180097cf7  mov     [rsp+48h+pvData], rax; pvData
0x180097cfc  xor     edx, edx; lpSubKey
0x180097cfe  mov     [rsp+48h+phkResult], 0; pdwType
0x180097d07  call    cs:__imp_RegGetValueA
0x180097d0d  mov     rcx, [rsp+48h+hkey]; hKey
0x180097d12  mov     ebx, eax
0x180097d14  call    cs:__imp_RegCloseKey
0x180097d1a  test    ebx, ebx
0x180097d1c  jz      short loc_180097D22
0x180097d1e  mov     eax, ebx
0x180097d20  jmp     short loc_180097CCB
0x180097d22  mov     eax, [rsp+48h+arg_8]
0x180097d26  mov     [rdi], eax
0x180097d28  xor     eax, eax
0x180097d2a  jmp     short loc_180097CCB
```
