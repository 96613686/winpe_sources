# CheckDeploymentServerRole(int *)

- ea: `0x18001a594`
- end: `0x18001a634`
- name: `?CheckDeploymentServerRole@@YAKPEAH@Z`
- size: `160`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ac90`
- `0x18001ad9c`

## callees

- `0x18001a594`
- `0x18001af54`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18001a5c7`
- `ADVAPI32!RegOpenKeyExW` at `0x18001a5c7`
- `ADVAPI32!RegCloseKey` at `0x18001a61a`
- `ADVAPI32!RegCloseKey` at `0x18001a61a`
- `WdsServerCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18001a5f5`
- `WdsServerCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18001a5f5`

## string_xrefs

- `0x18001a5b7`: `Software\Microsoft\WDS\InstalledFeatures`

## pseudocode

```c
__int64 __fastcall CheckDeploymentServerRole(int *a1)
{
  unsigned int ValueBool; // ebx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  ValueBool = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WDS\\InstalledFeatures", 0, 0x20119u, &hKey);
  if ( !(unsigned int)ElValidateWin32_11(ValueBool, v3, v4, 504) )
  {
    ValueBool = CRegKey::GetValueBool((CRegKey *)&hKey, L"WdsDeploymentServer", a1);
    ElValidateWin32_11(ValueBool, v5, v6, 508);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return ValueBool;
}

```

## disassembly

```asm
0x18001a594  mov     r11, rsp
0x18001a597  mov     [r11+8], rbx
0x18001a59b  push    rdi
0x18001a59c  sub     rsp, 30h
0x18001a5a0  and     qword ptr [r11+10h], 0
0x18001a5a5  lea     rax, [r11+10h]
0x18001a5a9  mov     rdi, rcx
0x18001a5ac  mov     [r11-18h], rax
0x18001a5b0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a5b7  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\WDS\\InstalledFeat"...
0x18001a5be  mov     r9d, 20119h; samDesired
0x18001a5c4  xor     r8d, r8d; ulOptions
0x18001a5c7  call    cs:__imp_RegOpenKeyExW
0x18001a5ce  nop     dword ptr [rax+rax+00h]
0x18001a5d3  mov     ecx, eax
0x18001a5d5  mov     r9d, 1F8h
0x18001a5db  mov     ebx, eax
0x18001a5dd  call    ElValidateWin32_11
0x18001a5e2  test    eax, eax
0x18001a5e4  jnz     short loc_18001A610
0x18001a5e6  mov     r8, rdi
0x18001a5e9  lea     rdx, aWdsdeployments; "WdsDeploymentServer"
0x18001a5f0  lea     rcx, [rsp+38h+hKey]
0x18001a5f5  call    cs:__imp_?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x18001a5fc  nop     dword ptr [rax+rax+00h]
0x18001a601  mov     ecx, eax
0x18001a603  mov     r9d, 1FCh
0x18001a609  mov     ebx, eax
0x18001a60b  call    ElValidateWin32_11
0x18001a610  mov     rcx, [rsp+38h+hKey]; hKey
0x18001a615  test    rcx, rcx
0x18001a618  jz      short loc_18001A626
0x18001a61a  call    cs:__imp_RegCloseKey
0x18001a621  nop     dword ptr [rax+rax+00h]
0x18001a626  mov     eax, ebx
0x18001a628  mov     rbx, [rsp+38h+arg_0]
0x18001a62d  add     rsp, 30h
0x18001a631  pop     rdi
0x18001a632  retn
```
