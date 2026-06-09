# IsBackgroundExtensionContract(ushort const *)

- ea: `0x1800c6658`
- end: `0x1800c6744`
- name: `?IsBackgroundExtensionContract@@YA_NPEBG@Z`
- size: `236`
- prototype: `bool __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800c7070`

## callees

- `0x1800c6658`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800c671b`
- `msvcrt!_wcsicmp` at `0x1800c671b`

## string_xrefs

- `0x1800c666f`: `Windows.BackgroundTasks`
- `0x1800c66c1`: `Windows.UserDataTaskDataProvider`
- `0x1800c66cc`: `Windows.PrintWorkflowBackgroundTask`
- `0x1800c667f`: `Windows.PreInstalledConfigTask`
- `0x1800c668a`: `Windows.UpdateTask`
- `0x1800c6695`: `Windows.AppService`
- `0x1800c66ed`: `Windows.PrintSupportExtension`

## pseudocode

```c
char __fastcall IsBackgroundExtensionContract(wchar_t *String1)
{
  __int64 v2; // rbx
  wchar_t *String2[14]; // [rsp+20h] [rbp-19h]

  String2[0] = L"Windows.BackgroundTasks";
  v2 = 0;
  String2[1] = L"Windows.PreInstalledConfigTask";
  String2[2] = L"Windows.UpdateTask";
  String2[3] = L"Windows.AppService";
  String2[4] = L"Windows.AppointmentDataProvider";
  String2[5] = L"Windows.ContactDataProvider";
  String2[6] = L"Windows.EmailDataProvider";
  String2[7] = L"Windows.UserDataTaskDataProvider";
  String2[8] = L"Windows.PrintWorkflowBackgroundTask";
  String2[9] = L"Windows.BarcodeScannerProvider";
  String2[10] = L"Windows.PosPaymentConnector";
  String2[11] = L"Windows.PrintSupportExtension";
  String2[12] = L"Windows.PrintSupportWorkflow";
  String2[13] = L"Windows.PrintSupportVirtualPrinterWorkflow";
  while ( (unsigned int)v2 < 0xE )
  {
    if ( !_wcsicmp(String1, String2[v2]) )
      return 1;
    v2 = (unsigned int)(v2 + 1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800c6658  mov     [rsp-8+arg_0], rbx
0x1800c665d  mov     [rsp-8+arg_8], rdi
0x1800c6662  push    rbp
0x1800c6663  lea     rbp, [rsp-57h]
0x1800c6668  sub     rsp, 90h
0x1800c666f  lea     rax, aWindowsBackgro; "Windows.BackgroundTasks"
0x1800c6676  mov     rdi, rcx
0x1800c6679  mov     [rbp+57h+String2], rax
0x1800c667d  xor     ebx, ebx
0x1800c667f  lea     rax, aWindowsPreinst; "Windows.PreInstalledConfigTask"
0x1800c6686  mov     [rbp+57h+var_68], rax
0x1800c668a  lea     rax, aWindowsUpdatet; "Windows.UpdateTask"
0x1800c6691  mov     [rbp+57h+var_60], rax
0x1800c6695  lea     rax, aWindowsAppserv; "Windows.AppService"
0x1800c669c  mov     [rbp+57h+var_58], rax
0x1800c66a0  lea     rax, aWindowsAppoint; "Windows.AppointmentDataProvider"
0x1800c66a7  mov     [rbp+57h+var_50], rax
0x1800c66ab  lea     rax, aWindowsContact_5; "Windows.ContactDataProvider"
0x1800c66b2  mov     [rbp+57h+var_48], rax
0x1800c66b6  lea     rax, aWindowsEmailda; "Windows.EmailDataProvider"
0x1800c66bd  mov     [rbp+57h+var_40], rax
0x1800c66c1  lea     rax, aWindowsUserdat_0; "Windows.UserDataTaskDataProvider"
0x1800c66c8  mov     [rbp+57h+var_38], rax
0x1800c66cc  lea     rax, aWindowsPrintwo; "Windows.PrintWorkflowBackgroundTask"
0x1800c66d3  mov     [rbp+57h+var_30], rax
0x1800c66d7  lea     rax, aWindowsBarcode_0; "Windows.BarcodeScannerProvider"
0x1800c66de  mov     [rbp+57h+var_28], rax
0x1800c66e2  lea     rax, aWindowsPospaym; "Windows.PosPaymentConnector"
0x1800c66e9  mov     [rbp+57h+var_20], rax
0x1800c66ed  lea     rax, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x1800c66f4  mov     [rbp+57h+var_18], rax
0x1800c66f8  lea     rax, aWindowsPrintsu; "Windows.PrintSupportWorkflow"
0x1800c66ff  mov     [rbp+57h+var_10], rax
0x1800c6703  lea     rax, aWindowsPrintsu_0; "Windows.PrintSupportVirtualPrinterWorkf"...
0x1800c670a  mov     [rbp+57h+var_8], rax
0x1800c670e  cmp     ebx, 0Eh
0x1800c6711  jnb     short loc_1800C672D
0x1800c6713  mov     rdx, [rbp+rbx*8+57h+String2]; String2
0x1800c6718  mov     rcx, rdi; String1
0x1800c671b  call    cs:__imp__wcsicmp
0x1800c6721  test    eax, eax
0x1800c6723  jz      short loc_1800C6729
0x1800c6725  inc     ebx
0x1800c6727  jmp     short loc_1800C670E
0x1800c6729  mov     al, 1
0x1800c672b  jmp     short loc_1800C672F
0x1800c672d  xor     al, al
0x1800c672f  lea     r11, [rsp+90h+var_s0]
0x1800c6737  mov     rbx, [r11+10h]
0x1800c673b  mov     rdi, [r11+18h]
0x1800c673f  mov     rsp, r11
0x1800c6742  pop     rbp
0x1800c6743  retn
```
