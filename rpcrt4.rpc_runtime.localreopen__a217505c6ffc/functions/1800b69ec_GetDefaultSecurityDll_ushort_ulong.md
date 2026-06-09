# GetDefaultSecurityDll(ushort *,ulong)

- ea: `0x1800b69ec`
- end: `0x1800b6aea`
- name: `?GetDefaultSecurityDll@@YAJPEAGK@Z`
- size: `254`
- prototype: `__int64 __fastcall(unsigned __int16 *Src, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057ff4`

## callees

- `0x18002e750`
- `0x1800b69ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b6a33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b6a33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6a8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6ab3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6a8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6ab3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b6a74`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b6a74`

## string_xrefs

- `0x1800b6a25`: `System\CurrentControlSet\Control\SecurityProviders`
- `0x1800b6a57`: `ClientDll`

## pseudocode

```c
__int64 __fastcall GetDefaultSecurityDll(unsigned __int16 *Src, DWORD a2)
{
  LSTATUS v3; // eax
  bool v4; // zf
  LSTATUS ValueW; // edi
  unsigned __int16 *v7; // rbx
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  pcbData = a2;
  hkey = 0;
  if ( DefaultSecurityDLLRead )
    return 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\SecurityProviders", 0, 0x20019u, &hkey);
  if ( v3 )
  {
    v4 = v3 == 2;
    goto LABEL_6;
  }
  ValueW = RegGetValueW(hkey, 0, L"ClientDll", 2u, 0, Src, &pcbData);
  if ( ValueW )
  {
    RegCloseKey(hkey);
    v4 = ValueW == 2;
LABEL_6:
    if ( !v4 )
      return 1747;
    goto LABEL_10;
  }
  v7 = DuplicateString(Src);
  RegCloseKey(hkey);
  if ( v7 )
  {
    DefaultSecurityDLL = v7;
LABEL_10:
    DefaultSecurityDLLRead = 1;
    return 0;
  }
  return 14;
}

```

## disassembly

```asm
0x1800b69ec  mov     rax, rsp
0x1800b69ef  mov     [rax+8], rbx
0x1800b69f3  mov     [rax+10h], edx
0x1800b69f6  push    rdi
0x1800b69f7  sub     rsp, 40h
0x1800b69fb  cmp     cs:?DefaultSecurityDLLRead@@3HA, 0; int DefaultSecurityDLLRead
0x1800b6a02  mov     rbx, rcx
0x1800b6a05  mov     qword ptr [rax+18h], 0
0x1800b6a0d  jnz     loc_1800B6AD5
0x1800b6a13  lea     rax, [rax+18h]
0x1800b6a17  mov     r9d, 20019h; samDesired
0x1800b6a1d  xor     r8d, r8d; ulOptions
0x1800b6a20  mov     [rsp+48h+phkResult], rax; phkResult
0x1800b6a25  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Sec"...
0x1800b6a2c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b6a33  call    cs:__imp_RegOpenKeyExW
0x1800b6a3a  nop     dword ptr [rax+rax+00h]
0x1800b6a3f  test    eax, eax
0x1800b6a41  jz      short loc_1800B6A48
0x1800b6a43  cmp     eax, 2
0x1800b6a46  jmp     short loc_1800B6A9A
0x1800b6a48  mov     rcx, [rsp+48h+hkey]; hkey
0x1800b6a4d  lea     rax, [rsp+48h+arg_8]
0x1800b6a52  mov     [rsp+48h+pcbData], rax; pcbData
0x1800b6a57  lea     r8, aClientdll; "ClientDll"
0x1800b6a5e  mov     [rsp+48h+pvData], rbx; pvData
0x1800b6a63  mov     r9d, 2; dwFlags
0x1800b6a69  xor     edx, edx; lpSubKey
0x1800b6a6b  mov     [rsp+48h+phkResult], 0; pdwType
0x1800b6a74  call    cs:__imp_RegGetValueW
0x1800b6a7b  nop     dword ptr [rax+rax+00h]
0x1800b6a80  mov     edi, eax
0x1800b6a82  test    eax, eax
0x1800b6a84  jz      short loc_1800B6AA3
0x1800b6a86  mov     rcx, [rsp+48h+hkey]; hKey
0x1800b6a8b  call    cs:__imp_RegCloseKey
0x1800b6a92  nop     dword ptr [rax+rax+00h]
0x1800b6a97  cmp     edi, 2
0x1800b6a9a  jz      short loc_1800B6ACB
0x1800b6a9c  mov     eax, 6D3h
0x1800b6aa1  jmp     short loc_1800B6AD7
0x1800b6aa3  mov     rcx, rbx; Src
0x1800b6aa6  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x1800b6aab  mov     rcx, [rsp+48h+hkey]; hKey
0x1800b6ab0  mov     rbx, rax
0x1800b6ab3  call    cs:__imp_RegCloseKey
0x1800b6aba  nop     dword ptr [rax+rax+00h]
0x1800b6abf  test    rbx, rbx
0x1800b6ac2  jz      short loc_1800B6AE3
0x1800b6ac4  mov     cs:?DefaultSecurityDLL@@3PEAGEA, rbx; ushort * DefaultSecurityDLL
0x1800b6acb  mov     cs:?DefaultSecurityDLLRead@@3HA, 1; int DefaultSecurityDLLRead
0x1800b6ad5  xor     eax, eax
0x1800b6ad7  mov     rbx, [rsp+48h+arg_0]
0x1800b6adc  add     rsp, 40h
0x1800b6ae0  pop     rdi
0x1800b6ae1  retn
0x1800b6ae3  mov     eax, 0Eh
0x1800b6ae8  jmp     short loc_1800B6AD7
```
