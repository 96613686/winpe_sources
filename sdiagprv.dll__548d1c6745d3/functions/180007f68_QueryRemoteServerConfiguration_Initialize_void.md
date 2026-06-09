# QueryRemoteServerConfiguration::Initialize(void)

- ea: `0x180007f68`
- end: `0x180008069`
- name: `?Initialize@QueryRemoteServerConfiguration@@AEAAJXZ`
- size: `257`
- prototype: `__int64 __fastcall(BYTE *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006cd0`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x180007e2c`
- `0x180007f68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007fa0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007fdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007fa0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007fdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000803d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008056`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000803d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008056`

## string_xrefs

- `0x180008009`: `QueryRemoteServerConfiguration::Initialize`
- `0x180008020`: `QueryRemoteServerConfiguration::Initialize`

## pseudocode

```c
__int64 __fastcall QueryRemoteServerConfiguration::Initialize(BYTE *this)
{
  int DWORDValue; // ebx
  QueryRemoteServerConfiguration *v3; // rcx
  const unsigned __int16 *v4; // r8
  __int64 v5; // rdx
  QueryRemoteServerConfiguration *v6; // rcx
  const unsigned __int16 *v7; // r8
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp+18h] BYREF

  DWORDValue = 0;
  hKey = 0;
  phkResult = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\ScriptedDiagnosticsProvider\\Policy",
         0,
         0x20019u,
         &hKey)
    || (DWORDValue = QueryRemoteServerConfiguration::GetDWORDValue(v3, hKey, v4, this + 8), DWORDValue >= 0) )
  {
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\ScriptedDiagnosticsProvider\\Policy",
            0,
            0x20019u,
            &phkResult) )
      DWORDValue = QueryRemoteServerConfiguration::GetDWORDValue(v6, phkResult, v7, this + 12);
  }
  if ( DWORDValue )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v6, v5, "QueryRemoteServerConfiguration::Initialize", (unsigned int)DWORDValue);
  }
  else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
  {
    McTemplateU0s_EventWriteTransfer(v6, SDIAGPRV_EVENT_DEBUG_SUCCESS, "QueryRemoteServerConfiguration::Initialize");
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)DWORDValue;
}

```

## disassembly

```asm
0x180007f68  mov     r11, rsp
0x180007f6b  mov     [r11+8], rbx
0x180007f6f  push    rdi
0x180007f70  sub     rsp, 30h
0x180007f74  mov     rdi, rcx
0x180007f77  lea     rax, [r11+10h]
0x180007f7b  xor     ebx, ebx
0x180007f7d  mov     [r11-18h], rax
0x180007f81  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007f88  mov     [r11+10h], rbx
0x180007f8c  mov     r9d, 20019h; samDesired
0x180007f92  mov     [r11+18h], rbx
0x180007f96  xor     r8d, r8d; ulOptions
0x180007f99  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180007fa0  call    cs:__imp_RegOpenKeyExW
0x180007fa6  test    eax, eax
0x180007fa8  jnz     short loc_180007FBE
0x180007faa  mov     rdx, [rsp+38h+hKey]; HKEY
0x180007faf  lea     r9, [rdi+8]; unsigned int *
0x180007fb3  call    ?GetDWORDValue@QueryRemoteServerConfiguration@@AEAAJQEAUHKEY__@@PEBGPEAK@Z; QueryRemoteServerConfiguration::GetDWORDValue(HKEY__ * const,ushort const *,ulong *)
0x180007fb8  mov     ebx, eax
0x180007fba  test    eax, eax
0x180007fbc  js      short loc_180007FF9
0x180007fbe  lea     rax, [rsp+38h+arg_10]
0x180007fc3  mov     r9d, 20019h; samDesired
0x180007fc9  xor     r8d, r8d; ulOptions
0x180007fcc  mov     [rsp+38h+phkResult], rax; phkResult
0x180007fd1  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\ScriptedD"...
0x180007fd8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007fdf  call    cs:__imp_RegOpenKeyExW
0x180007fe5  test    eax, eax
0x180007fe7  jnz     short loc_180007FF9
0x180007fe9  mov     rdx, [rsp+38h+arg_10]; HKEY
0x180007fee  lea     r9, [rdi+0Ch]; unsigned int *
0x180007ff2  call    ?GetDWORDValue@QueryRemoteServerConfiguration@@AEAAJQEAUHKEY__@@PEBGPEAK@Z; QueryRemoteServerConfiguration::GetDWORDValue(HKEY__ * const,ushort const *,ulong *)
0x180007ff7  mov     ebx, eax
0x180007ff9  test    ebx, ebx
0x180007ffb  jz      short loc_180008017
0x180007ffd  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008004  jz      short loc_180008033
0x180008006  mov     r9d, ebx
0x180008009  lea     r8, aQueryremoteser_2; "QueryRemoteServerConfiguration::Initial"...
0x180008010  call    McTemplateU0sq_EventWriteTransfer
0x180008015  jmp     short loc_180008033
0x180008017  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000801e  jz      short loc_180008033
0x180008020  lea     r8, aQueryremoteser_2; "QueryRemoteServerConfiguration::Initial"...
0x180008027  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000802e  call    McTemplateU0s_EventWriteTransfer
0x180008033  mov     rcx, [rsp+38h+hKey]; hKey
0x180008038  test    rcx, rcx
0x18000803b  jz      short loc_18000804C
0x18000803d  call    cs:__imp_RegCloseKey
0x180008043  mov     [rsp+38h+hKey], 0
0x18000804c  mov     rcx, [rsp+38h+arg_10]; hKey
0x180008051  test    rcx, rcx
0x180008054  jz      short loc_18000805C
0x180008056  call    cs:__imp_RegCloseKey
0x18000805c  mov     eax, ebx
0x18000805e  mov     rbx, [rsp+38h+arg_0]
0x180008063  add     rsp, 30h
0x180008067  pop     rdi
0x180008068  retn
```
