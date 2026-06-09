# IsBackgroundExtensionContract(ushort const *)

- ea: `0x18002eb68`
- end: `0x18002ec54`
- name: `?IsBackgroundExtensionContract@@YA_NPEBG@Z`
- size: `236`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180030560`

## callees

- `0x18002eb68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002ec2b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002ec2b`

## string_xrefs

- `0x18002eb8f`: `Windows.PreInstalledConfigTask`
- `0x18002eb7f`: `Windows.BackgroundTasks`
- `0x18002eba5`: `Windows.AppService`
- `0x18002eb9a`: `Windows.UpdateTask`
- `0x18002ebd1`: `Windows.UserDataTaskDataProvider`
- `0x18002ebdc`: `Windows.PrintWorkflowBackgroundTask`
- `0x18002ebfd`: `Windows.PrintSupportExtension`

## pseudocode

```c
char __fastcall IsBackgroundExtensionContract(const unsigned __int16 *a1)
{
  __int64 v2; // rbx
  _QWORD v4[14]; // [rsp+20h] [rbp-19h]

  v4[0] = L"Windows.BackgroundTasks";
  v2 = 0;
  v4[1] = L"Windows.PreInstalledConfigTask";
  v4[2] = L"Windows.UpdateTask";
  v4[3] = L"Windows.AppService";
  v4[4] = L"Windows.AppointmentDataProvider";
  v4[5] = L"Windows.ContactDataProvider";
  v4[6] = L"Windows.EmailDataProvider";
  v4[7] = L"Windows.UserDataTaskDataProvider";
  v4[8] = L"Windows.PrintWorkflowBackgroundTask";
  v4[9] = L"Windows.BarcodeScannerProvider";
  v4[10] = L"Windows.PosPaymentConnector";
  v4[11] = L"Windows.PrintSupportExtension";
  v4[12] = L"Windows.PrintSupportWorkflow";
  v4[13] = L"Windows.PrintSupportVirtualPrinterWorkflow";
  while ( (unsigned int)v2 < 0xE )
  {
    if ( !(unsigned int)_o__wcsicmp(a1, v4[v2]) )
      return 1;
    v2 = (unsigned int)(v2 + 1);
  }
  return 0;
}

```

## disassembly

```asm
0x18002eb68  mov     [rsp-8+arg_0], rbx
0x18002eb6d  mov     [rsp-8+arg_8], rdi
0x18002eb72  push    rbp
0x18002eb73  lea     rbp, [rsp-57h]
0x18002eb78  sub     rsp, 90h
0x18002eb7f  lea     rax, aWindowsBackgro; "Windows.BackgroundTasks"
0x18002eb86  mov     rdi, rcx
0x18002eb89  mov     [rbp+57h+var_70], rax
0x18002eb8d  xor     ebx, ebx
0x18002eb8f  lea     rax, aWindowsPreinst; "Windows.PreInstalledConfigTask"
0x18002eb96  mov     [rbp+57h+var_68], rax
0x18002eb9a  lea     rax, aWindowsUpdatet; "Windows.UpdateTask"
0x18002eba1  mov     [rbp+57h+var_60], rax
0x18002eba5  lea     rax, aWindowsAppserv; "Windows.AppService"
0x18002ebac  mov     [rbp+57h+var_58], rax
0x18002ebb0  lea     rax, aWindowsAppoint; "Windows.AppointmentDataProvider"
0x18002ebb7  mov     [rbp+57h+var_50], rax
0x18002ebbb  lea     rax, aWindowsContact_5; "Windows.ContactDataProvider"
0x18002ebc2  mov     [rbp+57h+var_48], rax
0x18002ebc6  lea     rax, aWindowsEmailda; "Windows.EmailDataProvider"
0x18002ebcd  mov     [rbp+57h+var_40], rax
0x18002ebd1  lea     rax, aWindowsUserdat_0; "Windows.UserDataTaskDataProvider"
0x18002ebd8  mov     [rbp+57h+var_38], rax
0x18002ebdc  lea     rax, aWindowsPrintwo; "Windows.PrintWorkflowBackgroundTask"
0x18002ebe3  mov     [rbp+57h+var_30], rax
0x18002ebe7  lea     rax, aWindowsBarcode_0; "Windows.BarcodeScannerProvider"
0x18002ebee  mov     [rbp+57h+var_28], rax
0x18002ebf2  lea     rax, aWindowsPospaym; "Windows.PosPaymentConnector"
0x18002ebf9  mov     [rbp+57h+var_20], rax
0x18002ebfd  lea     rax, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x18002ec04  mov     [rbp+57h+var_18], rax
0x18002ec08  lea     rax, aWindowsPrintsu; "Windows.PrintSupportWorkflow"
0x18002ec0f  mov     [rbp+57h+var_10], rax
0x18002ec13  lea     rax, aWindowsPrintsu_0; "Windows.PrintSupportVirtualPrinterWorkf"...
0x18002ec1a  mov     [rbp+57h+var_8], rax
0x18002ec1e  cmp     ebx, 0Eh
0x18002ec21  jnb     short loc_18002EC3D
0x18002ec23  mov     rdx, [rbp+rbx*8+57h+var_70]
0x18002ec28  mov     rcx, rdi
0x18002ec2b  call    cs:__imp__o__wcsicmp
0x18002ec31  test    eax, eax
0x18002ec33  jz      short loc_18002EC39
0x18002ec35  inc     ebx
0x18002ec37  jmp     short loc_18002EC1E
0x18002ec39  mov     al, 1
0x18002ec3b  jmp     short loc_18002EC3F
0x18002ec3d  xor     al, al
0x18002ec3f  lea     r11, [rsp+90h+var_s0]
0x18002ec47  mov     rbx, [r11+10h]
0x18002ec4b  mov     rdi, [r11+18h]
0x18002ec4f  mov     rsp, r11
0x18002ec52  pop     rbp
0x18002ec53  retn
```
