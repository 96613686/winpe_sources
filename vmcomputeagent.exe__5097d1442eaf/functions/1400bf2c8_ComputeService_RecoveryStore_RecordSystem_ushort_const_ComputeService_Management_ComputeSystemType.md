# ComputeService::RecoveryStore::RecordSystem(ushort const *,ComputeService::Management::ComputeSystemType)

- ea: `0x1400bf2c8`
- end: `0x1400bf3d2`
- name: `?RecordSystem@RecoveryStore@ComputeService@@YAXPEBGW4ComputeSystemType@Management@2@@Z`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400878e0`

## callees

- `0x140005360`
- `0x1400341ac`
- `0x1400beddc`
- `0x1400bee74`
- `0x1400bf2c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400bf372`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400bf389`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400bf3a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400bf372`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400bf389`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400bf3a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400bf33e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400bf33e`

## string_xrefs

- `0x1400bf3c0`: `onecore\vm\common\vml\VmRegistry.h`
- `0x1400bf333`: `ComputeSystemType`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __fastcall ComputeService::RecoveryStore::RecordSystem(const unsigned __int16 *a1)
{
  unsigned int v2; // r9d
  unsigned int v3; // eax
  unsigned int v4; // r9d
  int result; // eax
  unsigned int lpData; // [rsp+20h] [rbp-40h]
  unsigned int lpDataa; // [rsp+20h] [rbp-40h]
  struct _SECURITY_ATTRIBUTES *cbData; // [rsp+28h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES *cbDataa; // [rsp+28h] [rbp-38h]
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-28h] BYREF
  HKEY v12; // [rsp+40h] [rbp-20h] BYREF
  HKEY v13; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v13 = 0;
  ComputeService::RecoveryStore::Details::OpenComputeSystemRegKey(&v13, 0xF003Fu);
  hKey = 0;
  Vml::VmRegistryKey::Create((Vml::VmRegistryKey *)&hKey, v13, a1, v2, lpData, cbData);
  *(_DWORD *)Data = 8;
  v3 = RegSetValueExW(hKey, L"ComputeSystemType", 0, 4u, Data, 4u);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x353,
      (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
      (const char *)v3,
      lpDataa);
  v12 = 0;
  result = Vml::VmRegistryKey::Create((Vml::VmRegistryKey *)&v12, hKey, L"Resource", v4, lpDataa, cbDataa);
  if ( v12 )
  {
    result = RegCloseKey(v12);
    v12 = 0;
  }
  if ( hKey )
  {
    result = RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v13 )
    return RegCloseKey(v13);
  return result;
}

```

## disassembly

```asm
0x1400bf2c8  mov     [rsp-8+arg_8], rbx
0x1400bf2cd  push    rbp
0x1400bf2ce  mov     rbp, rsp
0x1400bf2d1  sub     rsp, 60h
0x1400bf2d5  mov     rax, cs:__security_cookie
0x1400bf2dc  xor     rax, rsp
0x1400bf2df  mov     [rbp+var_10], rax
0x1400bf2e3  mov     rbx, rcx
0x1400bf2e6  mov     [rbp+var_18], 0
0x1400bf2ee  mov     edx, 0F003Fh
0x1400bf2f3  lea     rcx, [rbp+var_18]
0x1400bf2f7  call    ?OpenComputeSystemRegKey@Details@RecoveryStore@ComputeService@@YA?AVVmRegistryKey@Vml@@K@Z; ComputeService::RecoveryStore::Details::OpenComputeSystemRegKey(ulong)
0x1400bf2fc  nop
0x1400bf2fd  mov     [rbp+hKey], 0
0x1400bf305  mov     r8, rbx; unsigned __int16 *
0x1400bf308  mov     rdx, [rbp+var_18]; HKEY
0x1400bf30c  lea     rcx, [rbp+hKey]; this
0x1400bf310  call    ?Create@VmRegistryKey@Vml@@QEAAHPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; Vml::VmRegistryKey::Create(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x1400bf315  mov     dword ptr [rbp+Data], 8
0x1400bf31c  mov     r9d, 4; dwType
0x1400bf322  mov     dword ptr [rsp+60h+cbData], r9d; struct _SECURITY_ATTRIBUTES *
0x1400bf327  lea     rax, [rbp+Data]
0x1400bf32b  mov     [rsp+60h+lpData], rax; unsigned int
0x1400bf330  xor     r8d, r8d; Reserved
0x1400bf333  lea     rdx, aComputesystemt; "ComputeSystemType"
0x1400bf33a  mov     rcx, [rbp+hKey]; hKey
0x1400bf33e  call    cs:__imp_RegSetValueExW
0x1400bf344  mov     rcx, [rbp+8]; this
0x1400bf348  test    eax, eax
0x1400bf34a  jnz     short loc_1400BF3BD
0x1400bf34c  mov     [rbp+var_20], 0
0x1400bf354  lea     r8, aResource; "Resource"
0x1400bf35b  mov     rdx, [rbp+hKey]; HKEY
0x1400bf35f  lea     rcx, [rbp+var_20]; this
0x1400bf363  call    ?Create@VmRegistryKey@Vml@@QEAAHPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; Vml::VmRegistryKey::Create(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x1400bf368  nop
0x1400bf369  mov     rcx, [rbp+var_20]; hKey
0x1400bf36d  test    rcx, rcx
0x1400bf370  jz      short loc_1400BF380
0x1400bf372  call    cs:__imp_RegCloseKey
0x1400bf378  mov     [rbp+var_20], 0
0x1400bf380  mov     rcx, [rbp+hKey]; hKey
0x1400bf384  test    rcx, rcx
0x1400bf387  jz      short loc_1400BF397
0x1400bf389  call    cs:__imp_RegCloseKey
0x1400bf38f  mov     [rbp+hKey], 0
0x1400bf397  mov     rcx, [rbp+var_18]; hKey
0x1400bf39b  test    rcx, rcx
0x1400bf39e  jz      short loc_1400BF3A6
0x1400bf3a0  call    cs:__imp_RegCloseKey
0x1400bf3a6  mov     rcx, [rbp+var_10]
0x1400bf3aa  xor     rcx, rsp; StackCookie
0x1400bf3ad  call    __security_check_cookie
0x1400bf3b2  mov     rbx, [rsp+60h+arg_8]
0x1400bf3b7  add     rsp, 60h
0x1400bf3bb  pop     rbp
0x1400bf3bc  retn
0x1400bf3bd  mov     r9d, eax; char *
0x1400bf3c0  lea     r8, aOnecoreVmCommo_14; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x1400bf3c7  mov     edx, 353h; void *
0x1400bf3cc  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
