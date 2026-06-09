# KEGetSamRpcPwdChangePBKDF2Iterations

- ea: `0x1800176b0`
- end: `0x180017773`
- name: `KEGetSamRpcPwdChangePBKDF2Iterations`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800079c8`

## callees

- `0x1800176b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001773c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001773c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800176f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800176f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017767`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017767`

## pseudocode

```c
LSTATUS __fastcall KEGetSamRpcPwdChangePBKDF2Iterations(_QWORD *a1)
{
  LSTATUS result; // eax
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  HKEY hkey; // [rsp+58h] [rbp+10h] BYREF
  __int64 pvData; // [rsp+60h] [rbp+18h] BYREF

  pvData = 0;
  pcbData = 0;
  hkey = 0;
  *a1 = 10000;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\SAM", 0, 0x20019u, &hkey);
  if ( !result )
  {
    pcbData = 4;
    result = RegGetValueW(hkey, 0, L"PBKDF2Iterations", 0x10u, 0, &pvData, &pcbData);
    if ( !result )
    {
      result = pvData - 5000;
      if ( (unsigned __int64)(pvData - 5000) <= 0xF2EB8 )
        *a1 = pvData;
    }
  }
  if ( hkey )
    return RegCloseKey(hkey);
  return result;
}

```

## disassembly

```asm
0x1800176b0  mov     rax, rsp
0x1800176b3  push    rbx
0x1800176b4  sub     rsp, 40h
0x1800176b8  mov     qword ptr [rax+18h], 0
0x1800176c0  mov     rbx, rcx
0x1800176c3  mov     dword ptr [rax+8], 0
0x1800176ca  mov     r9d, 20019h; samDesired
0x1800176d0  mov     qword ptr [rax+10h], 0
0x1800176d8  lea     rax, [rax+10h]
0x1800176dc  mov     qword ptr [rcx], 2710h
0x1800176e3  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\SAM"
0x1800176ea  xor     r8d, r8d; ulOptions
0x1800176ed  mov     [rsp+48h+phkResult], rax; phkResult
0x1800176f2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800176f9  call    cs:__imp_RegOpenKeyExW
0x1800176ff  test    eax, eax
0x180017701  jnz     short loc_18001775D
0x180017703  mov     rcx, [rsp+48h+hkey]; hkey
0x180017708  lea     rax, [rsp+48h+arg_0]
0x18001770d  mov     [rsp+48h+pcbData], rax; pcbData
0x180017712  lea     r8, aPbkdf2iteratio; "PBKDF2Iterations"
0x180017719  lea     rax, [rsp+48h+arg_10]
0x18001771e  mov     [rsp+48h+arg_0], 4
0x180017726  mov     [rsp+48h+pvData], rax; pvData
0x18001772b  mov     r9d, 10h; dwFlags
0x180017731  xor     edx, edx; lpSubKey
0x180017733  mov     [rsp+48h+phkResult], 0; pdwType
0x18001773c  call    cs:__imp_RegGetValueW
0x180017742  test    eax, eax
0x180017744  jnz     short loc_18001775D
0x180017746  mov     rcx, [rsp+48h+arg_10]
0x18001774b  lea     rax, [rcx-1388h]
0x180017752  cmp     rax, 0F2EB8h
0x180017758  ja      short loc_18001775D
0x18001775a  mov     [rbx], rcx
0x18001775d  mov     rcx, [rsp+48h+hkey]; hKey
0x180017762  test    rcx, rcx
0x180017765  jz      short loc_18001776D
0x180017767  call    cs:__imp_RegCloseKey
0x18001776d  add     rsp, 40h
0x180017771  pop     rbx
0x180017772  retn
```
