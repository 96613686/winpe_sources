# ReadAuditPolicySetting(void)

- ea: `0x1800b4008`
- end: `0x1800b40d8`
- name: `?ReadAuditPolicySetting@@YAJXZ`
- size: `208`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800af218`

## callees

- `0x1800b4008`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b4046`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b4046`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b40ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b40ca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800b4093`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800b4093`

## string_xrefs

- `0x1800b4071`: `AuditCacheEnabled`

## pseudocode

```c
__int64 ReadAuditPolicySetting(void)
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  LSTATUS ValueA; // eax
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  hkey = 0;
  pvData = 0;
  pcbData = 4;
  v0 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Rpc", 0, 0x20019u, &hkey);
  if ( v0 )
  {
    v1 = 14;
    if ( v0 == 2 )
      return 1766;
  }
  else
  {
    ValueA = RegGetValueA(hkey, 0, "AuditCacheEnabled", 0x18u, 0, &pvData, &pcbData);
    if ( ValueA )
    {
      v1 = ValueA != 2 ? 0xE : 0;
    }
    else
    {
      if ( !pvData )
        g_AuditCacheEnabled = 0;
      v1 = 0;
    }
    if ( hkey )
      RegCloseKey(hkey);
  }
  return v1;
}

```

## disassembly

```asm
0x1800b4008  mov     rax, rsp
0x1800b400b  push    rbx
0x1800b400c  sub     rsp, 40h
0x1800b4010  mov     qword ptr [rax+18h], 0
0x1800b4018  mov     r9d, 20019h; samDesired
0x1800b401e  mov     dword ptr [rax+8], 0
0x1800b4025  xor     r8d, r8d; ulOptions
0x1800b4028  mov     dword ptr [rax+10h], 4
0x1800b402f  lea     rax, [rax+18h]
0x1800b4033  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Rpc"
0x1800b403a  mov     [rsp+48h+phkResult], rax; phkResult
0x1800b403f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b4046  call    cs:__imp_RegOpenKeyExA
0x1800b404c  test    eax, eax
0x1800b404e  jz      short loc_1800B4062
0x1800b4050  cmp     eax, 2
0x1800b4053  mov     ebx, 0Eh
0x1800b4058  mov     ecx, 6E6h
0x1800b405d  cmovz   ebx, ecx
0x1800b4060  jmp     short loc_1800B40D0
0x1800b4062  mov     rcx, [rsp+48h+hkey]; hkey
0x1800b4067  lea     rax, [rsp+48h+arg_8]
0x1800b406c  mov     [rsp+48h+pcbData], rax; pcbData
0x1800b4071  lea     r8, aAuditcacheenab; "AuditCacheEnabled"
0x1800b4078  lea     rax, [rsp+48h+arg_0]
0x1800b407d  mov     r9d, 18h; dwFlags
0x1800b4083  mov     [rsp+48h+pvData], rax; pvData
0x1800b4088  xor     edx, edx; lpSubKey
0x1800b408a  mov     [rsp+48h+phkResult], 0; pdwType
0x1800b4093  call    cs:__imp_RegGetValueA
0x1800b4099  test    eax, eax
0x1800b409b  jz      short loc_1800B40AD
0x1800b409d  sub     eax, 2
0x1800b40a0  mov     ebx, 0Eh
0x1800b40a5  neg     eax
0x1800b40a7  sbb     eax, eax
0x1800b40a9  and     ebx, eax
0x1800b40ab  jmp     short loc_1800B40C0
0x1800b40ad  cmp     [rsp+48h+arg_0], 0
0x1800b40b2  jnz     short loc_1800B40BE
0x1800b40b4  mov     cs:?g_AuditCacheEnabled@@3HA, 0; int g_AuditCacheEnabled
0x1800b40be  xor     ebx, ebx
0x1800b40c0  mov     rcx, [rsp+48h+hkey]; hKey
0x1800b40c5  test    rcx, rcx
0x1800b40c8  jz      short loc_1800B40D0
0x1800b40ca  call    cs:__imp_RegCloseKey
0x1800b40d0  mov     eax, ebx
0x1800b40d2  add     rsp, 40h
0x1800b40d6  pop     rbx
0x1800b40d7  retn
```
