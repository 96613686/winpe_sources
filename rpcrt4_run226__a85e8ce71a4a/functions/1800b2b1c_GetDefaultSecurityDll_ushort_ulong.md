# GetDefaultSecurityDll(ushort *,ulong)

- ea: `0x1800b2b1c`
- end: `0x1800b2c01`
- name: `?GetDefaultSecurityDll@@YAJPEAGK@Z`
- size: `229`
- prototype: `__int64 __fastcall(unsigned __int16 *Src, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800461fc`

## callees

- `0x18002d420`
- `0x1800b2b1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b2b63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b2b63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2baf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2bd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2baf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2bd1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2b9e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2b9e`

## string_xrefs

- `0x1800b2b55`: `System\CurrentControlSet\Control\SecurityProviders`
- `0x1800b2b81`: `ClientDll`

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
0x1800b2b1c  mov     rax, rsp
0x1800b2b1f  mov     [rax+8], rbx
0x1800b2b23  mov     [rax+10h], edx
0x1800b2b26  push    rdi
0x1800b2b27  sub     rsp, 40h
0x1800b2b2b  cmp     cs:?DefaultSecurityDLLRead@@3HA, 0; int DefaultSecurityDLLRead
0x1800b2b32  mov     rbx, rcx
0x1800b2b35  mov     qword ptr [rax+18h], 0
0x1800b2b3d  jnz     loc_1800B2BED
0x1800b2b43  lea     rax, [rax+18h]
0x1800b2b47  mov     r9d, 20019h; samDesired
0x1800b2b4d  xor     r8d, r8d; ulOptions
0x1800b2b50  mov     [rsp+48h+phkResult], rax; phkResult
0x1800b2b55  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Sec"...
0x1800b2b5c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b2b63  call    cs:__imp_RegOpenKeyExW
0x1800b2b69  test    eax, eax
0x1800b2b6b  jz      short loc_1800B2B72
0x1800b2b6d  cmp     eax, 2
0x1800b2b70  jmp     short loc_1800B2BB8
0x1800b2b72  mov     rcx, [rsp+48h+hkey]; hkey
0x1800b2b77  lea     rax, [rsp+48h+arg_8]
0x1800b2b7c  mov     [rsp+48h+pcbData], rax; pcbData
0x1800b2b81  lea     r8, aClientdll; "ClientDll"
0x1800b2b88  mov     [rsp+48h+pvData], rbx; pvData
0x1800b2b8d  mov     r9d, 2; dwFlags
0x1800b2b93  xor     edx, edx; lpSubKey
0x1800b2b95  mov     [rsp+48h+phkResult], 0; pdwType
0x1800b2b9e  call    cs:__imp_RegGetValueW
0x1800b2ba4  mov     edi, eax
0x1800b2ba6  test    eax, eax
0x1800b2ba8  jz      short loc_1800B2BC1
0x1800b2baa  mov     rcx, [rsp+48h+hkey]; hKey
0x1800b2baf  call    cs:__imp_RegCloseKey
0x1800b2bb5  cmp     edi, 2
0x1800b2bb8  jz      short loc_1800B2BE3
0x1800b2bba  mov     eax, 6D3h
0x1800b2bbf  jmp     short loc_1800B2BEF
0x1800b2bc1  mov     rcx, rbx; Src
0x1800b2bc4  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x1800b2bc9  mov     rcx, [rsp+48h+hkey]; hKey
0x1800b2bce  mov     rbx, rax
0x1800b2bd1  call    cs:__imp_RegCloseKey
0x1800b2bd7  test    rbx, rbx
0x1800b2bda  jz      short loc_1800B2BFA
0x1800b2bdc  mov     cs:?DefaultSecurityDLL@@3PEAGEA, rbx; ushort * DefaultSecurityDLL
0x1800b2be3  mov     cs:?DefaultSecurityDLLRead@@3HA, 1; int DefaultSecurityDLLRead
0x1800b2bed  xor     eax, eax
0x1800b2bef  mov     rbx, [rsp+48h+arg_0]
0x1800b2bf4  add     rsp, 40h
0x1800b2bf8  pop     rdi
0x1800b2bf9  retn
0x1800b2bfa  mov     eax, 0Eh
0x1800b2bff  jmp     short loc_1800B2BEF
```
