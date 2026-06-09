# IsBackgroundExtensionContract(ushort const *)

- ea: `0x18007546c`
- end: `0x180075558`
- name: `?IsBackgroundExtensionContract@@YA_NPEBG@Z`
- size: `236`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180075d70`

## callees

- `0x18007546c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007552f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007552f`

## string_xrefs

- `0x180075483`: `Windows.BackgroundTasks`
- `0x1800754a9`: `Windows.AppService`
- `0x18007549e`: `Windows.UpdateTask`
- `0x180075493`: `Windows.PreInstalledConfigTask`
- `0x1800754e0`: `Windows.PrintWorkflowBackgroundTask`
- `0x1800754d5`: `Windows.UserDataTaskDataProvider`
- `0x180075501`: `Windows.PrintSupportExtension`

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
0x18007546c  mov     [rsp-8+arg_0], rbx
0x180075471  mov     [rsp-8+arg_8], rdi
0x180075476  push    rbp
0x180075477  lea     rbp, [rsp-57h]
0x18007547c  sub     rsp, 90h
0x180075483  lea     rax, aWindowsBackgro; "Windows.BackgroundTasks"
0x18007548a  mov     rdi, rcx
0x18007548d  mov     [rbp+57h+var_70], rax
0x180075491  xor     ebx, ebx
0x180075493  lea     rax, aWindowsPreinst; "Windows.PreInstalledConfigTask"
0x18007549a  mov     [rbp+57h+var_68], rax
0x18007549e  lea     rax, aWindowsUpdatet; "Windows.UpdateTask"
0x1800754a5  mov     [rbp+57h+var_60], rax
0x1800754a9  lea     rax, aWindowsAppserv; "Windows.AppService"
0x1800754b0  mov     [rbp+57h+var_58], rax
0x1800754b4  lea     rax, aWindowsAppoint; "Windows.AppointmentDataProvider"
0x1800754bb  mov     [rbp+57h+var_50], rax
0x1800754bf  lea     rax, aWindowsContact_5; "Windows.ContactDataProvider"
0x1800754c6  mov     [rbp+57h+var_48], rax
0x1800754ca  lea     rax, aWindowsEmailda; "Windows.EmailDataProvider"
0x1800754d1  mov     [rbp+57h+var_40], rax
0x1800754d5  lea     rax, aWindowsUserdat_0; "Windows.UserDataTaskDataProvider"
0x1800754dc  mov     [rbp+57h+var_38], rax
0x1800754e0  lea     rax, aWindowsPrintwo; "Windows.PrintWorkflowBackgroundTask"
0x1800754e7  mov     [rbp+57h+var_30], rax
0x1800754eb  lea     rax, aWindowsBarcode_0; "Windows.BarcodeScannerProvider"
0x1800754f2  mov     [rbp+57h+var_28], rax
0x1800754f6  lea     rax, aWindowsPospaym; "Windows.PosPaymentConnector"
0x1800754fd  mov     [rbp+57h+var_20], rax
0x180075501  lea     rax, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x180075508  mov     [rbp+57h+var_18], rax
0x18007550c  lea     rax, aWindowsPrintsu; "Windows.PrintSupportWorkflow"
0x180075513  mov     [rbp+57h+var_10], rax
0x180075517  lea     rax, aWindowsPrintsu_0; "Windows.PrintSupportVirtualPrinterWorkf"...
0x18007551e  mov     [rbp+57h+var_8], rax
0x180075522  cmp     ebx, 0Eh
0x180075525  jnb     short loc_180075541
0x180075527  mov     rdx, [rbp+rbx*8+57h+var_70]
0x18007552c  mov     rcx, rdi
0x18007552f  call    cs:__imp__o__wcsicmp
0x180075535  test    eax, eax
0x180075537  jz      short loc_18007553D
0x180075539  inc     ebx
0x18007553b  jmp     short loc_180075522
0x18007553d  mov     al, 1
0x18007553f  jmp     short loc_180075543
0x180075541  xor     al, al
0x180075543  lea     r11, [rsp+90h+var_s0]
0x18007554b  mov     rbx, [r11+10h]
0x18007554f  mov     rdi, [r11+18h]
0x180075553  mov     rsp, r11
0x180075556  pop     rbp
0x180075557  retn
```
