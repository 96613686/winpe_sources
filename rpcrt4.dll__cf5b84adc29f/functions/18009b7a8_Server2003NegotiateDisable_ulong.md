# Server2003NegotiateDisable(ulong *)

- ea: `0x18009b7a8`
- end: `0x18009b86b`
- name: `?Server2003NegotiateDisable@@YAJPEAK@Z`
- size: `195`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061b24`

## callees

- `0x18009b7a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009b7ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009b7ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009b84d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009b84d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18009b83a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18009b83a`

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
0x18009b7a8  mov     rax, rsp
0x18009b7ab  mov     [rax+8], rbx
0x18009b7af  push    rdi
0x18009b7b0  sub     rsp, 40h
0x18009b7b4  mov     qword ptr [rax+20h], 0
0x18009b7bc  mov     rdi, rcx
0x18009b7bf  mov     dword ptr [rax+10h], 0
0x18009b7c6  mov     r9d, 20019h; samDesired
0x18009b7cc  mov     dword ptr [rax+18h], 4
0x18009b7d3  lea     rax, [rax+20h]
0x18009b7d7  xor     r8d, r8d; ulOptions
0x18009b7da  mov     [rsp+48h+phkResult], rax; phkResult
0x18009b7df  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x18009b7e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009b7ed  call    cs:__imp_RegOpenKeyExW
0x18009b7f4  nop     dword ptr [rax+rax+00h]
0x18009b7f9  test    eax, eax
0x18009b7fb  jz      short loc_18009B809
0x18009b7fd  mov     rbx, [rsp+48h+arg_0]
0x18009b802  add     rsp, 40h
0x18009b806  pop     rdi
0x18009b807  retn
0x18009b809  mov     rcx, [rsp+48h+hkey]; hkey
0x18009b80e  lea     rax, [rsp+48h+arg_10]
0x18009b813  mov     [rsp+48h+pcbData], rax; pcbData
0x18009b818  lea     r8, aServer2003nego; "Server2003NegotiateDisable"
0x18009b81f  lea     rax, [rsp+48h+arg_8]
0x18009b824  mov     r9d, 18h; dwFlags
0x18009b82a  mov     [rsp+48h+pvData], rax; pvData
0x18009b82f  xor     edx, edx; lpSubKey
0x18009b831  mov     [rsp+48h+phkResult], 0; pdwType
0x18009b83a  call    cs:__imp_RegGetValueA
0x18009b841  nop     dword ptr [rax+rax+00h]
0x18009b846  mov     rcx, [rsp+48h+hkey]; hKey
0x18009b84b  mov     ebx, eax
0x18009b84d  call    cs:__imp_RegCloseKey
0x18009b854  nop     dword ptr [rax+rax+00h]
0x18009b859  test    ebx, ebx
0x18009b85b  jz      short loc_18009B861
0x18009b85d  mov     eax, ebx
0x18009b85f  jmp     short loc_18009B7FD
0x18009b861  mov     eax, [rsp+48h+arg_8]
0x18009b865  mov     [rdi], eax
0x18009b867  xor     eax, eax
0x18009b869  jmp     short loc_18009B7FD
```
