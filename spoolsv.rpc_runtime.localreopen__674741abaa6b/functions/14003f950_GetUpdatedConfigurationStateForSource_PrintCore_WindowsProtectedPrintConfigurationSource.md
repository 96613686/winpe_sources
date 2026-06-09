# GetUpdatedConfigurationStateForSource(PrintCore::WindowsProtectedPrintConfigurationSource)

- ea: `0x14003f950`
- end: `0x14003fa89`
- name: `?GetUpdatedConfigurationStateForSource@@YA?AW4WindowsProtectedPrintConfigurationState@PrintCore@@W4WindowsProtectedPrintConfigurationSource@2@@Z`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14003fdb0`

## callees

- `0x14001748c`
- `0x140031720`
- `0x14003f950`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14003f9a9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14003f9a9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14003fa0c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14003fa0c`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x14003fa55`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x14003fa55`

## string_xrefs

- `0x14003f9d3`: `Resetting WPP configuration...`
- `0x14003f9ca`: `GetUpdatedConfigurationStateForSource`
- `0x14003fa26`: `GetUpdatedConfigurationStateForSource`
- `0x14003fa6f`: `GetUpdatedConfigurationStateForSource`
- `0x14003fa1c`: `Failed to update WPP configuration reset count in registry. Error %d`
- `0x14003fa36`: `Max WPP configuration reset count reached. Disabling WPP...`
- `0x14003fa68`: `Failed to delete WPP configuration reset count from registry. Error %d`
- `0x14003f9bc`: `Failed to read WPP configuration reset count from registry. Error %d`
- `0x14003f989`: `ConfigurationResetCount`
- `0x14003f9f0`: `ConfigurationResetCount`
- `0x14003fa42`: `ConfigurationResetCount`

## pseudocode

```c
__int64 __fastcall GetUpdatedConfigurationStateForSource(int a1)
{
  unsigned int v1; // ebx
  unsigned int ValueW; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD v7; // [rsp+58h] [rbp+10h] BYREF

  v1 = 2;
  if ( !a1 )
  {
    Data = 0;
    v7 = 4;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Policies\\Microsoft\\Windows NT\\Printers\\WPP",
               L"ConfigurationResetCount",
               0x10u,
               0,
               &Data,
               &v7);
    if ( (ValueW & 0xFFFFFFFD) != 0 )
    {
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "GetUpdatedConfigurationStateForSource",
        L"Failed to read WPP configuration reset count from registry. Error %d",
        ValueW);
      return 0;
    }
    if ( Data >= 5 )
    {
      SpoolerServiceTelemetry::WriteDbgTraceInfo(
        "GetUpdatedConfigurationStateForSource",
        L"Max WPP configuration reset count reached. Disabling WPP...");
      v1 = 0;
      v4 = RegDeleteKeyValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\Windows NT\\Printers\\WPP",
             L"ConfigurationResetCount");
      if ( v4 )
        SpoolerServiceTelemetry::WriteDbgTraceError(
          "GetUpdatedConfigurationStateForSource",
          L"Failed to delete WPP configuration reset count from registry. Error %d",
          v4);
    }
    else
    {
      SpoolerServiceTelemetry::WriteDbgTraceInfo(
        "GetUpdatedConfigurationStateForSource",
        L"Resetting WPP configuration...");
      ++Data;
      v3 = RegSetKeyValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\Windows NT\\Printers\\WPP",
             L"ConfigurationResetCount",
             4u,
             &Data,
             4u);
      if ( v3 )
      {
        SpoolerServiceTelemetry::WriteDbgTraceError(
          "GetUpdatedConfigurationStateForSource",
          L"Failed to update WPP configuration reset count in registry. Error %d",
          v3);
        return 0;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x14003f950  mov     r11, rsp
0x14003f953  mov     [r11+18h], rbx
0x14003f957  push    rbp
0x14003f958  sub     rsp, 40h
0x14003f95c  mov     ebx, 2
0x14003f961  test    ecx, ecx
0x14003f963  jnz     loc_14003FA7B
0x14003f969  lea     rax, [r11+10h]
0x14003f96d  mov     [rsp+48h+Data], ecx
0x14003f971  mov     [r11-18h], rax
0x14003f975  lea     r9d, [rbx+0Eh]; dwFlags
0x14003f979  lea     rax, [r11+8]
0x14003f97d  mov     [rsp+48h+arg_8], 4
0x14003f985  mov     [r11-20h], rax
0x14003f989  lea     r8, aConfigurationr; "ConfigurationResetCount"
0x14003f990  mov     rbp, 0FFFFFFFF80000002h
0x14003f997  mov     qword ptr [r11-28h], 0
0x14003f99f  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows "...
0x14003f9a6  mov     rcx, rbp; hkey
0x14003f9a9  call    cs:__imp_RegGetValueW
0x14003f9b0  nop     dword ptr [rax+rax+00h]
0x14003f9b5  test    eax, 0FFFFFFFDh
0x14003f9ba  jz      short loc_14003F9C5
0x14003f9bc  lea     rdx, aFailedToReadWp; "Failed to read WPP configuration reset "...
0x14003f9c3  jmp     short loc_14003FA23
0x14003f9c5  cmp     [rsp+48h+Data], 5
0x14003f9ca  lea     rcx, aGetupdatedconf; "GetUpdatedConfigurationStateForSource"
0x14003f9d1  jnb     short loc_14003FA36
0x14003f9d3  lea     rdx, aResettingWppCo; "Resetting WPP configuration..."
0x14003f9da  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14003f9df  inc     [rsp+48h+Data]
0x14003f9e3  lea     rax, [rsp+48h+Data]
0x14003f9e8  mov     [rsp+48h+cbData], 4; cbData
0x14003f9f0  lea     r8, aConfigurationr; "ConfigurationResetCount"
0x14003f9f7  mov     r9d, 4; dwType
0x14003f9fd  mov     [rsp+48h+lpData], rax; lpData
0x14003fa02  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows "...
0x14003fa09  mov     rcx, rbp; hKey
0x14003fa0c  call    cs:__imp_RegSetKeyValueW
0x14003fa13  nop     dword ptr [rax+rax+00h]
0x14003fa18  test    eax, eax
0x14003fa1a  jz      short loc_14003FA7B
0x14003fa1c  lea     rdx, aFailedToUpdate; "Failed to update WPP configuration rese"...
0x14003fa23  mov     r8d, eax
0x14003fa26  lea     rcx, aGetupdatedconf; "GetUpdatedConfigurationStateForSource"
0x14003fa2d  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003fa32  xor     ebx, ebx
0x14003fa34  jmp     short loc_14003FA7B
0x14003fa36  lea     rdx, aMaxWppConfigur; "Max WPP configuration reset count reach"...
0x14003fa3d  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14003fa42  lea     r8, aConfigurationr; "ConfigurationResetCount"
0x14003fa49  mov     rcx, rbp; hKey
0x14003fa4c  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows "...
0x14003fa53  xor     ebx, ebx
0x14003fa55  call    cs:__imp_RegDeleteKeyValueW
0x14003fa5c  nop     dword ptr [rax+rax+00h]
0x14003fa61  test    eax, eax
0x14003fa63  jz      short loc_14003FA7B
0x14003fa65  mov     r8d, eax
0x14003fa68  lea     rdx, aFailedToDelete; "Failed to delete WPP configuration rese"...
0x14003fa6f  lea     rcx, aGetupdatedconf; "GetUpdatedConfigurationStateForSource"
0x14003fa76  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003fa7b  mov     eax, ebx
0x14003fa7d  mov     rbx, [rsp+48h+arg_10]
0x14003fa82  add     rsp, 40h
0x14003fa86  pop     rbp
0x14003fa87  retn
```
