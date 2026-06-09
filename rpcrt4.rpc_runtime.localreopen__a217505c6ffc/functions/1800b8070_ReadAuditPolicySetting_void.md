# ReadAuditPolicySetting(void)

- ea: `0x1800b8070`
- end: `0x1800b8153`
- name: `?ReadAuditPolicySetting@@YAJXZ`
- size: `227`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b2f34`

## callees

- `0x1800b8070`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b80ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b80ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b813e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b813e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800b8101`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800b8101`

## string_xrefs

- `0x1800b80df`: `AuditCacheEnabled`

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
0x1800b8070  mov     rax, rsp
0x1800b8073  push    rbx
0x1800b8074  sub     rsp, 40h
0x1800b8078  mov     qword ptr [rax+18h], 0
0x1800b8080  mov     r9d, 20019h; samDesired
0x1800b8086  mov     dword ptr [rax+8], 0
0x1800b808d  xor     r8d, r8d; ulOptions
0x1800b8090  mov     dword ptr [rax+10h], 4
0x1800b8097  lea     rax, [rax+18h]
0x1800b809b  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Rpc"
0x1800b80a2  mov     [rsp+48h+phkResult], rax; phkResult
0x1800b80a7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b80ae  call    cs:__imp_RegOpenKeyExA
0x1800b80b5  nop     dword ptr [rax+rax+00h]
0x1800b80ba  test    eax, eax
0x1800b80bc  jz      short loc_1800B80D0
0x1800b80be  cmp     eax, 2
0x1800b80c1  mov     ebx, 0Eh
0x1800b80c6  mov     ecx, 6E6h
0x1800b80cb  cmovz   ebx, ecx
0x1800b80ce  jmp     short loc_1800B814A
0x1800b80d0  mov     rcx, [rsp+48h+hkey]; hkey
0x1800b80d5  lea     rax, [rsp+48h+arg_8]
0x1800b80da  mov     [rsp+48h+pcbData], rax; pcbData
0x1800b80df  lea     r8, aAuditcacheenab; "AuditCacheEnabled"
0x1800b80e6  lea     rax, [rsp+48h+arg_0]
0x1800b80eb  mov     r9d, 18h; dwFlags
0x1800b80f1  mov     [rsp+48h+pvData], rax; pvData
0x1800b80f6  xor     edx, edx; lpSubKey
0x1800b80f8  mov     [rsp+48h+phkResult], 0; pdwType
0x1800b8101  call    cs:__imp_RegGetValueA
0x1800b8108  nop     dword ptr [rax+rax+00h]
0x1800b810d  test    eax, eax
0x1800b810f  jz      short loc_1800B8121
0x1800b8111  sub     eax, 2
0x1800b8114  mov     ebx, 0Eh
0x1800b8119  neg     eax
0x1800b811b  sbb     eax, eax
0x1800b811d  and     ebx, eax
0x1800b811f  jmp     short loc_1800B8134
0x1800b8121  cmp     [rsp+48h+arg_0], 0
0x1800b8126  jnz     short loc_1800B8132
0x1800b8128  mov     cs:?g_AuditCacheEnabled@@3HA, 0; int g_AuditCacheEnabled
0x1800b8132  xor     ebx, ebx
0x1800b8134  mov     rcx, [rsp+48h+hkey]; hKey
0x1800b8139  test    rcx, rcx
0x1800b813c  jz      short loc_1800B814A
0x1800b813e  call    cs:__imp_RegCloseKey
0x1800b8145  nop     dword ptr [rax+rax+00h]
0x1800b814a  mov     eax, ebx
0x1800b814c  add     rsp, 40h
0x1800b8150  pop     rbx
0x1800b8151  retn
```
