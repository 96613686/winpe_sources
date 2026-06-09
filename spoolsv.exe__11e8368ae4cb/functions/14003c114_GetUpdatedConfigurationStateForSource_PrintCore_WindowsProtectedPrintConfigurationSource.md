# GetUpdatedConfigurationStateForSource(PrintCore::WindowsProtectedPrintConfigurationSource)

- ea: `0x14003c114`
- end: `0x14003c23a`
- name: `?GetUpdatedConfigurationStateForSource@@YA?AW4WindowsProtectedPrintConfigurationState@PrintCore@@W4WindowsProtectedPrintConfigurationSource@2@@Z`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14003c530`

## callees

- `0x1400160a0`
- `0x14002f030`
- `0x14003c114`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14003c16d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14003c16d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14003c1ca`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14003c1ca`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x14003c20d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x14003c20d`

## string_xrefs

- `0x14003c191`: `Resetting WPP configuration...`
- `0x14003c188`: `GetUpdatedConfigurationStateForSource`
- `0x14003c1de`: `GetUpdatedConfigurationStateForSource`
- `0x14003c221`: `GetUpdatedConfigurationStateForSource`
- `0x14003c1d4`: `Failed to update WPP configuration reset count in registry. Error %d`
- `0x14003c1ee`: `Max WPP configuration reset count reached. Disabling WPP...`
- `0x14003c21a`: `Failed to delete WPP configuration reset count from registry. Error %d`
- `0x14003c17a`: `Failed to read WPP configuration reset count from registry. Error %d`
- `0x14003c14d`: `ConfigurationResetCount`
- `0x14003c1ae`: `ConfigurationResetCount`
- `0x14003c1fa`: `ConfigurationResetCount`

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
0x14003c114  mov     r11, rsp
0x14003c117  mov     [r11+18h], rbx
0x14003c11b  push    rbp
0x14003c11c  sub     rsp, 40h
0x14003c120  mov     ebx, 2
0x14003c125  test    ecx, ecx
0x14003c127  jnz     loc_14003C22D
0x14003c12d  lea     rax, [r11+10h]
0x14003c131  mov     [rsp+48h+Data], ecx
0x14003c135  mov     [r11-18h], rax
0x14003c139  lea     r9d, [rbx+0Eh]; dwFlags
0x14003c13d  lea     rax, [r11+8]
0x14003c141  mov     [rsp+48h+arg_8], 4
0x14003c149  mov     [r11-20h], rax
0x14003c14d  lea     r8, aConfigurationr; "ConfigurationResetCount"
0x14003c154  mov     rbp, 0FFFFFFFF80000002h
0x14003c15b  mov     qword ptr [r11-28h], 0
0x14003c163  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows "...
0x14003c16a  mov     rcx, rbp; hkey
0x14003c16d  call    cs:__imp_RegGetValueW
0x14003c173  test    eax, 0FFFFFFFDh
0x14003c178  jz      short loc_14003C183
0x14003c17a  lea     rdx, aFailedToReadWp; "Failed to read WPP configuration reset "...
0x14003c181  jmp     short loc_14003C1DB
0x14003c183  cmp     [rsp+48h+Data], 5
0x14003c188  lea     rcx, aGetupdatedconf; "GetUpdatedConfigurationStateForSource"
0x14003c18f  jnb     short loc_14003C1EE
0x14003c191  lea     rdx, aResettingWppCo; "Resetting WPP configuration..."
0x14003c198  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14003c19d  inc     [rsp+48h+Data]
0x14003c1a1  lea     rax, [rsp+48h+Data]
0x14003c1a6  mov     [rsp+48h+cbData], 4; cbData
0x14003c1ae  lea     r8, aConfigurationr; "ConfigurationResetCount"
0x14003c1b5  mov     r9d, 4; dwType
0x14003c1bb  mov     [rsp+48h+lpData], rax; lpData
0x14003c1c0  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows "...
0x14003c1c7  mov     rcx, rbp; hKey
0x14003c1ca  call    cs:__imp_RegSetKeyValueW
0x14003c1d0  test    eax, eax
0x14003c1d2  jz      short loc_14003C22D
0x14003c1d4  lea     rdx, aFailedToUpdate; "Failed to update WPP configuration rese"...
0x14003c1db  mov     r8d, eax
0x14003c1de  lea     rcx, aGetupdatedconf; "GetUpdatedConfigurationStateForSource"
0x14003c1e5  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003c1ea  xor     ebx, ebx
0x14003c1ec  jmp     short loc_14003C22D
0x14003c1ee  lea     rdx, aMaxWppConfigur; "Max WPP configuration reset count reach"...
0x14003c1f5  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14003c1fa  lea     r8, aConfigurationr; "ConfigurationResetCount"
0x14003c201  mov     rcx, rbp; hKey
0x14003c204  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows "...
0x14003c20b  xor     ebx, ebx
0x14003c20d  call    cs:__imp_RegDeleteKeyValueW
0x14003c213  test    eax, eax
0x14003c215  jz      short loc_14003C22D
0x14003c217  mov     r8d, eax
0x14003c21a  lea     rdx, aFailedToDelete; "Failed to delete WPP configuration rese"...
0x14003c221  lea     rcx, aGetupdatedconf; "GetUpdatedConfigurationStateForSource"
0x14003c228  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003c22d  mov     eax, ebx
0x14003c22f  mov     rbx, [rsp+48h+arg_10]
0x14003c234  add     rsp, 40h
0x14003c238  pop     rbp
0x14003c239  retn
```
