# _anonymous_namespace_::configureServicingPrep

- ea: `0x18000348c`
- end: `0x180003539`
- name: `_anonymous_namespace_::configureServicingPrep`
- size: `173`
- prototype: `__int64 __fastcall(HKEY, __int64, __int64, HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000370c`

## callees

- `0x180002a20`
- `0x180002c88`
- `0x18000348c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000350f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000350f`

## string_xrefs

- `0x1800034a5`: `SYSTEM\CurrentControlSet\Services\UwfServicingSvc\Servicing\Runtime`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::configureServicingPrep(HKEY a1, __int64 a2, __int64 a3, HKEY a4)
{
  unsigned int v4; // ebx
  LSTATUS v6; // eax
  int Data; // [rsp+40h] [rbp+8h] BYREF

  v4 = UwfServicingRegCopyValue(
         a1,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
         L"EnableLUA",
         a4,
         L"SYSTEM\\CurrentControlSet\\Services\\UwfServicingSvc\\Servicing\\Runtime",
         L"SavedEnableLUA");
  if ( (v4 & 0x80000000) != 0 )
  {
    UwfServicingLog(0, 1, v4, L"Entry: Failed to save LUA control info");
    return v4;
  }
  Data = 0;
  v6 = RegSetKeyValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
         L"EnableLUA",
         4u,
         &Data,
         4u);
  v4 = v6;
  if ( v6 > 0 )
    v4 = (unsigned __int16)v6 | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    UwfServicingLog(0, 1, v4, L"Entry: Failed to disable LUA");
    return v4;
  }
  return 0;
}

```

## disassembly

```asm
0x18000348c  push    rbx
0x18000348e  sub     rsp, 30h
0x180003492  lea     rax, aSavedenablelua; "SavedEnableLUA"
0x180003499  mov     qword ptr [rsp+38h+cbData], rax; unsigned __int16 *
0x18000349e  lea     r8, aEnablelua; "EnableLUA"
0x1800034a5  lea     rax, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Uw"...
0x1800034ac  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800034b3  mov     [rsp+38h+lpData], rax; unsigned __int16 *
0x1800034b8  call    ?UwfServicingRegCopyValue@@YAJPEAUHKEY__@@PEBG1011@Z; UwfServicingRegCopyValue(HKEY__ *,ushort const *,ushort const *,HKEY__ *,ushort const *,ushort const *)
0x1800034bd  mov     ebx, eax
0x1800034bf  test    eax, eax
0x1800034c1  jns     short loc_1800034DD
0x1800034c3  lea     r9, aEntryFailedToS_0; "Entry: Failed to save LUA control info"
0x1800034ca  mov     r8d, ebx
0x1800034cd  mov     edx, 1
0x1800034d2  xor     ecx, ecx
0x1800034d4  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x1800034d9  mov     eax, ebx
0x1800034db  jmp     short loc_180003533
0x1800034dd  mov     r9d, 4; dwType
0x1800034e3  mov     [rsp+38h+Data], 0
0x1800034eb  lea     rax, [rsp+38h+Data]
0x1800034f0  mov     [rsp+38h+cbData], r9d; cbData
0x1800034f5  lea     r8, aEnablelua; "EnableLUA"
0x1800034fc  mov     [rsp+38h+lpData], rax; lpData
0x180003501  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003508  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000350f  call    cs:__imp_RegSetKeyValueW
0x180003515  mov     ebx, eax
0x180003517  test    eax, eax
0x180003519  jle     short loc_180003524
0x18000351b  movzx   ebx, ax
0x18000351e  or      ebx, 80070000h
0x180003524  test    ebx, ebx
0x180003526  jns     short loc_180003531
0x180003528  lea     r9, aEntryFailedToD_0; "Entry: Failed to disable LUA"
0x18000352f  jmp     short loc_1800034CA
0x180003531  xor     eax, eax
0x180003533  add     rsp, 30h
0x180003537  pop     rbx
0x180003538  retn
```
