# WorkerModule::InitializeSelf(void)

- ea: `0x1401297ac`
- end: `0x14012a1bf`
- name: `?InitializeSelf@WorkerModule@@QEAAXXZ`
- size: `2579`
- prototype: `void __fastcall(WorkerModule *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400653a8`

## callees

- `0x1400364a0`
- `0x14004ad3c`
- `0x14004dd04`
- `0x1400545bc`
- `0x140083990`
- `0x14011ea40`
- `0x14011f6fc`
- `0x1401277a0`
- `0x140127848`
- `0x1401297ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14012a146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14012a146`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14012a0ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14012a0ca`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14012a19a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14012a19a`

## string_xrefs

- `0x14012a152`: `Cannot create initialization timeout timer. Error code: %d.\n`

## pseudocode

```c
void __fastcall WorkerModule::InitializeSelf(WorkerModule *this)
{
  const struct wil::FailureInfo *v1; // rdx
  const char *v2; // r9
  DWORD LastError; // eax
  _BYTE v4[160]; // [rsp+20h] [rbp-B8h] BYREF
  struct _FILETIME pftDueTime; // [rsp+C0h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  qword_1403C4710 = (__int64)MSVML_WORKER_EXCEPTIONS_INFO;
  qword_1403C82F0 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_INFO;
  qword_1403C4708 = (__int64)MSVML_WORKER_EXCEPTIONS_WARNING;
  qword_1403C82E8 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_WARNING;
  qword_1403C4700 = (__int64)MSVML_WORKER_EXCEPTIONS_ERROR;
  qword_1403C82E0 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_ERROR;
  qword_1403C46F8 = (__int64)MSVML_WORKER_EXCEPTIONS_CRITICAL;
  qword_1403C4730 = (__int64)MSVML_WORKER_MODULES_INFO;
  qword_1403C4728 = (__int64)MSVML_WORKER_MODULES_WARNING;
  qword_1403C4720 = (__int64)MSVML_WORKER_MODULES_ERROR;
  qword_1403C4718 = (__int64)MSVML_WORKER_MODULES_CRITICAL;
  qword_1403C4750 = (__int64)MSVML_WORKER_COM_INFO;
  qword_1403C4748 = (__int64)MSVML_WORKER_COM_WARNING;
  qword_1403C4740 = (__int64)MSVML_WORKER_COM_ERROR;
  qword_1403C4738 = (__int64)MSVML_WORKER_COM_CRITICAL;
  qword_1403C4770 = (__int64)MSVML_WORKER_REGISTRY_INFO;
  qword_1403C4768 = (__int64)MSVML_WORKER_REGISTRY_WARNING;
  qword_1403C4760 = (__int64)MSVML_WORKER_REGISTRY_ERROR;
  qword_1403C4758 = (__int64)MSVML_WORKER_REGISTRY_CRITICAL;
  qword_1403C4790 = (__int64)MSVML_WORKER_THREADS_INFO;
  qword_1403C4788 = (__int64)MSVML_WORKER_THREADS_WARNING;
  qword_1403C4780 = (__int64)MSVML_WORKER_THREADS_ERROR;
  qword_1403C4778 = (__int64)MSVML_WORKER_THREADS_CRITICAL;
  qword_1403C47B0 = (__int64)MSVML_WORKER_REFCOUNTED_INFO;
  qword_1403C47A8 = (__int64)MSVML_WORKER_REFCOUNTED_WARNING;
  qword_1403C47A0 = (__int64)MSVML_WORKER_REFCOUNTED_ERROR;
  qword_1403C4798 = (__int64)MSVML_WORKER_REFCOUNTED_CRITICAL;
  qword_1403C47D0 = (__int64)MSVML_WORKER_WMI_INFO;
  qword_1403C47C8 = (__int64)MSVML_WORKER_WMI_WARNING;
  qword_1403C47C0 = (__int64)MSVML_WORKER_WMI_ERROR;
  qword_1403C47B8 = (__int64)MSVML_WORKER_WMI_CRITICAL;
  qword_1403C82D8 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_CRITICAL;
  qword_1403C8318 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_CRITICAL;
  qword_1403C5EF0 = (__int64)MSVDEV_BIOS_INFO;
  qword_1403C5EE8 = (__int64)MSVDEV_BIOS_WARNING;
  qword_1403C5EE0 = (__int64)MSVDEV_BIOS_ERROR;
  qword_1403C5ED8 = (__int64)MSVDEV_BIOS_CRITICAL;
  qword_1403C5F10 = (__int64)MSVDEV_CMOS_INFO;
  qword_1403C5F08 = (__int64)MSVDEV_CMOS_WARNING;
  qword_1403C8330 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_INFO;
  qword_1403C8328 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_WARNING;
  qword_1403C8320 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_ERROR;
  qword_1403C5F00 = (__int64)MSVDEV_CMOS_ERROR;
  qword_1403C5EF8 = (__int64)MSVDEV_CMOS_CRITICAL;
  qword_1403C5F30 = (__int64)MSVDEV_POWER_MANAGEMENT_INFO;
  qword_1403C5F28 = (__int64)MSVDEV_POWER_MANAGEMENT_WARNING;
  qword_1403C5F20 = (__int64)MSVDEV_POWER_MANAGEMENT_ERROR;
  qword_1403C5F18 = (__int64)MSVDEV_POWER_MANAGEMENT_CRITICAL;
  qword_1403C5F50 = (__int64)MSVDEV_SM_BUS_INFO;
  qword_1403C5F48 = (__int64)MSVDEV_SM_BUS_WARNING;
  qword_1403C5F40 = (__int64)MSVDEV_SM_BUS_ERROR;
  qword_1403C5F38 = (__int64)MSVDEV_SM_BUS_CRITICAL;
  qword_1403C5F70 = (__int64)MSVDEV_ISA_BUS_INFO;
  qword_1403C5F68 = (__int64)MSVDEV_ISA_BUS_WARNING;
  qword_1403C5F60 = (__int64)MSVDEV_ISA_BUS_ERROR;
  qword_1403C5F58 = (__int64)MSVDEV_ISA_BUS_CRITICAL;
  qword_1403C5F90 = (__int64)MSVDEV_PCI_BUS_INFO;
  qword_1403C5F88 = (__int64)MSVDEV_PCI_BUS_WARNING;
  qword_1403C5F80 = (__int64)MSVDEV_PCI_BUS_ERROR;
  qword_1403C5F78 = (__int64)"2(";
  qword_1403C5FB0 = (__int64)MSVDEV_APIC_INFO;
  qword_1403C5FA8 = (__int64)MSVDEV_APIC_WARNING;
  qword_1403C5FA0 = (__int64)MSVDEV_APIC_ERROR;
  qword_1403C5F98 = (__int64)MSVDEV_APIC_CRITICAL;
  qword_1403C5FD0 = (__int64)MSVDEV_DMA_INFO;
  qword_1403C5FC8 = (__int64)MSVDEV_DMA_WARNING;
  qword_1403C5FC0 = (__int64)MSVDEV_DMA_ERROR;
  qword_1403C5FB8 = (__int64)MSVDEV_DMA_CRITICAL;
  qword_1403C5FF0 = (__int64)MSVDEV_PIC_INFO;
  qword_1403C5FE8 = (__int64)MSVDEV_PIC_WARNING;
  qword_1403C5FE0 = (__int64)MSVDEV_PIC_ERROR;
  qword_1403C5FD8 = (__int64)MSVDEV_PIC_CRITICAL;
  qword_1403C6010 = (__int64)MSVDEV_PIT_INFO;
  qword_1403C6008 = (__int64)MSVDEV_PIT_WARNING;
  qword_1403C6000 = (__int64)MSVDEV_PIT_ERROR;
  qword_1403C5FF8 = (__int64)MSVDEV_PIT_CRITICAL;
  qword_1403C6030 = (__int64)MSVDEV_SUPER_IO_INFO;
  qword_1403C6028 = (__int64)MSVDEV_SUPER_IO_WARNING;
  qword_1403C6020 = (__int64)MSVDEV_SUPER_IO_ERROR;
  qword_1403C6018 = (__int64)MSVDEV_SUPER_IO_CRITICAL;
  qword_1403C6050 = (__int64)MSVDEV_SERIAL_CONTROLLER_INFO;
  qword_1403C6048 = (__int64)MSVDEV_SERIAL_CONTROLLER_WARNING;
  qword_1403C6040 = (__int64)MSVDEV_SERIAL_CONTROLLER_ERROR;
  qword_1403C6038 = (__int64)MSVDEV_SERIAL_CONTROLLER_CRITICAL;
  qword_1403C6090 = (__int64)"|)";
  qword_1403C6070 = (__int64)MSVDEV_KEYBOARD_INFO;
  qword_1403C6088 = (__int64)MSVDEV_MOUSE_WARNING;
  qword_1403C6068 = (__int64)MSVDEV_KEYBOARD_WARNING;
  qword_1403C6080 = (__int64)MSVDEV_MOUSE_ERROR;
  qword_1403C6060 = (__int64)MSVDEV_KEYBOARD_ERROR;
  qword_1403C6058 = (__int64)MSVDEV_KEYBOARD_CRITICAL;
  qword_1403C6078 = (__int64)MSVDEV_MOUSE_CRITICAL;
  qword_1403C6278 = (__int64)MSVDEV_MOUSE_CRITICAL;
  qword_1403C60B0 = (__int64)MSVDEV_FLOPPY_CONTROLLER_INFO;
  qword_1403C60A8 = (__int64)MSVDEV_FLOPPY_CONTROLLER_WARNING;
  qword_1403C60A0 = (__int64)MSVDEV_FLOPPY_CONTROLLER_ERROR;
  qword_1403C6098 = (__int64)MSVDEV_FLOPPY_CONTROLLER_CRITICAL;
  qword_1403C60D0 = (__int64)MSVDEV_FLOPPY_DRIVE_INFO;
  qword_1403C60C8 = (__int64)MSVDEV_FLOPPY_DRIVE_WARNING;
  qword_1403C60C0 = (__int64)MSVDEV_FLOPPY_DRIVE_ERROR;
  qword_1403C60B8 = (__int64)MSVDEV_FLOPPY_DRIVE_CRITICAL;
  qword_1403C60F0 = (__int64)MSVDEV_IDE_CONTROLLER_INFO;
  qword_1403C60E8 = (__int64)MSVDEV_IDE_CONTROLLER_WARNING;
  qword_1403C60E0 = (__int64)MSVDEV_IDE_CONTROLLER_ERROR;
  qword_1403C60D8 = (__int64)MSVDEV_IDE_CONTROLLER_CRITICAL;
  qword_1403C6110 = (__int64)MSVDEV_IDE_ATTACHMENT_INFO;
  qword_1403C6108 = (__int64)MSVDEV_IDE_ATTACHMENT_WARNING;
  qword_1403C6100 = (__int64)MSVDEV_IDE_ATTACHMENT_ERROR;
  qword_1403C60F8 = (__int64)MSVDEV_IDE_ATTACHMENT_CRITICAL;
  qword_1403C6130 = (__int64)MSVDEV_SCSI_CONTROLLER_INFO;
  qword_1403C6128 = (__int64)MSVDEV_SCSI_CONTROLLER_WARNING;
  qword_1403C6120 = (__int64)MSVDEV_SCSI_CONTROLLER_ERROR;
  qword_1403C6118 = (__int64)MSVDEV_SCSI_CONTROLLER_CRITICAL;
  qword_1403C6150 = (__int64)MSVDEV_SCSI_BUS_INFO;
  qword_1403C6148 = (__int64)MSVDEV_SCSI_BUS_WARNING;
  qword_1403C6140 = (__int64)MSVDEV_SCSI_BUS_ERROR;
  qword_1403C6138 = (__int64)MSVDEV_SCSI_BUS_CRITICAL;
  qword_1403C6170 = (__int64)MSVDEV_SCSI_ATTACHMENT_INFO;
  qword_1403C6168 = (__int64)MSVDEV_SCSI_ATTACHMENT_WARNING;
  qword_1403C6160 = (__int64)MSVDEV_SCSI_ATTACHMENT_ERROR;
  qword_1403C6158 = (__int64)MSVDEV_SCSI_ATTACHMENT_CRITICAL;
  qword_1403C6190 = (__int64)MSVDEV_MEDIA_INFO;
  qword_1403C6290 = (__int64)"|)";
  qword_1403C6288 = (__int64)MSVDEV_MOUSE_WARNING;
  qword_1403C6280 = (__int64)MSVDEV_MOUSE_ERROR;
  qword_1403C6188 = (__int64)MSVDEV_MEDIA_WARNING;
  qword_1403C61F0 = (__int64)MSVDEV_VIDEO_CONTROLLER_INFO;
  qword_1403C6180 = (__int64)MSVDEV_MEDIA_ERROR;
  qword_1403C61E8 = (__int64)">+";
  qword_1403C6178 = (__int64)MSVDEV_MEDIA_CRITICAL;
  qword_1403C61E0 = (__int64)MSVDEV_VIDEO_CONTROLLER_ERROR;
  qword_1403C61B0 = (__int64)MSVDEV_HARD_DRIVE_INFO;
  qword_1403C61A8 = (__int64)MSVDEV_HARD_DRIVE_WARNING;
  qword_1403C61A0 = (__int64)MSVDEV_HARD_DRIVE_ERROR;
  qword_1403C6198 = (__int64)MSVDEV_HARD_DRIVE_CRITICAL;
  qword_1403C61D0 = (__int64)MSVDEV_ETHERNET_INFO;
  qword_1403C61C8 = (__int64)MSVDEV_ETHERNET_WARNING;
  qword_1403C61C0 = (__int64)MSVDEV_ETHERNET_ERROR;
  qword_1403C61B8 = (__int64)MSVDEV_ETHERNET_CRITICAL;
  qword_1403C61D8 = (__int64)"R+";
  qword_1403C6258 = (__int64)"R+";
  qword_1403C6210 = (__int64)MSVDEV_REPOSITORY_INFO;
  qword_1403C6208 = (__int64)"f+";
  qword_1403C6200 = (__int64)MSVDEV_REPOSITORY_ERROR;
  qword_1403C61F8 = (__int64)"z+";
  qword_1403C6230 = (__int64)MSVDEV_REMOTING_INFO;
  qword_1403C6228 = (__int64)MSVDEV_REMOTING_WARNING;
  qword_1403C6220 = (__int64)MSVDEV_REMOTING_ERROR;
  qword_1403C6218 = (__int64)MSVDEV_REMOTING_CRITICAL;
  qword_1403C6250 = (__int64)MSVDEV_HID_INFO;
  qword_1403C6248 = (__int64)MSVDEV_HID_WARNING;
  qword_1403C6240 = (__int64)MSVDEV_HID_ERROR;
  qword_1403C6238 = (__int64)MSVDEV_HID_CRITICAL;
  qword_1403C62D0 = (__int64)MSVDEV_VIRTUAL_MOTHERBOARD_INFO;
  qword_1403C62C8 = (__int64)"6)";
  qword_1403C62C0 = (__int64)MSVDEV_VIRTUAL_MOTHERBOARD_ERROR;
  qword_1403C62B8 = (__int64)MSVDEV_VIRTUAL_MOTHERBOARD_CRITICAL;
  qword_1403C72F0 = (__int64)MSVDEV_DYNMEM_INFO;
  qword_1403C72E8 = (__int64)MSVDEV_DYNMEM_WARNING;
  qword_1403C72E0 = (__int64)MSVDEV_DYNMEM_ERROR;
  qword_1403C72D8 = (__int64)MSVDEV_DYNMEM_CRITICAL;
  qword_1403C7310 = (__int64)MSVDEV_SYNTH3DVIDEO_INFO;
  qword_1403C7308 = (__int64)MSVDEV_SYNTH3DVIDEO_WARNING;
  qword_1403C7300 = (__int64)MSVDEV_SYNTH3DVIDEO_ERROR;
  qword_1403C72F8 = (__int64)MSVDEV_SYNTH3DVIDEO_CRITICAL;
  qword_1403C6270 = (__int64)MSVDEV_VIDEO_CONTROLLER_INFO;
  qword_1403C6268 = (__int64)">+";
  qword_1403C6260 = (__int64)MSVDEV_VIDEO_CONTROLLER_ERROR;
  std::function<void (unsigned short,unsigned short const *)>::operator=<void (&)(unsigned short,unsigned short const *),0>(g_HvsTraceFunctions);
  std::function<bool (unsigned short)>::operator=<int (&)(unsigned short),0>(qword_1403CD1F0);
  pti = CreateThreadpoolTimer(WorkerModule::InitializeTimeoutCallback, &g_Module, 0);
  if ( wil::details::g_pfnTelemetryCallback
    && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != VmWorkerTrace::FallbackTelemetryCallback )
  {
    memset_0(v4, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v4, v1);
  }
  wil::details::g_pfnTelemetryCallback = (__int64)VmWorkerTrace::FallbackTelemetryCallback;
  *(_DWORD *)(wil::details::static_lazy<VmWorkerTrace>::get(
                VmWorkerTrace::FallbackTelemetryCallback,
                _lambda_f90d4020ca5a3ee22356c2a70c24b4bd_::_lambda_invoker_cdecl_)
            + 20) = 2;
  if ( !pti )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
    {
      LastError = GetLastError();
      VmlDebugTrace(16416, L"Cannot create initialization timeout timer. Error code: %d.\n", LastError);
    }
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x413,
      (unsigned int)"onecore\\vm\\worker\\wpexe\\workermodule.cpp",
      v2);
  }
  pftDueTime = (struct _FILETIME)-600000000LL;
  SetThreadpoolTimer(pti, &pftDueTime, 0, 0);
}

```

## disassembly

```asm
0x1401297ac  sub     rsp, 0D8h
0x1401297b3  mov     rax, cs:__security_cookie
0x1401297ba  xor     rax, rsp
0x1401297bd  mov     [rsp+0D8h+var_10], rax
0x1401297c5  lea     rax, MSVML_WORKER_EXCEPTIONS_INFO
0x1401297cc  mov     cs:qword_1403C4710, rax
0x1401297d3  lea     r8, MSVM_WORKER_MIGRATION_DEBUG_INFO
0x1401297da  lea     rax, MSVML_WORKER_EXCEPTIONS_WARNING
0x1401297e1  mov     cs:qword_1403C82F0, r8
0x1401297e8  mov     cs:qword_1403C4708, rax
0x1401297ef  lea     rdx, MSVM_WORKER_MIGRATION_DEBUG_WARNING
0x1401297f6  lea     rax, MSVML_WORKER_EXCEPTIONS_ERROR
0x1401297fd  mov     cs:qword_1403C82E8, rdx
0x140129804  mov     cs:qword_1403C4700, rax
0x14012980b  lea     rcx, MSVM_WORKER_MIGRATION_DEBUG_ERROR
0x140129812  lea     rax, MSVML_WORKER_EXCEPTIONS_CRITICAL
0x140129819  mov     cs:qword_1403C82E0, rcx
0x140129820  mov     cs:qword_1403C46F8, rax
0x140129827  lea     rax, MSVML_WORKER_MODULES_INFO
0x14012982e  mov     cs:qword_1403C4730, rax
0x140129835  lea     rax, MSVML_WORKER_MODULES_WARNING
0x14012983c  mov     cs:qword_1403C4728, rax
0x140129843  lea     rax, MSVML_WORKER_MODULES_ERROR
0x14012984a  mov     cs:qword_1403C4720, rax
0x140129851  lea     rax, MSVML_WORKER_MODULES_CRITICAL
0x140129858  mov     cs:qword_1403C4718, rax
0x14012985f  lea     rax, MSVML_WORKER_COM_INFO
0x140129866  mov     cs:qword_1403C4750, rax
0x14012986d  lea     rax, MSVML_WORKER_COM_WARNING
0x140129874  mov     cs:qword_1403C4748, rax
0x14012987b  lea     rax, MSVML_WORKER_COM_ERROR
0x140129882  mov     cs:qword_1403C4740, rax
0x140129889  lea     rax, MSVML_WORKER_COM_CRITICAL
0x140129890  mov     cs:qword_1403C4738, rax
0x140129897  lea     rax, MSVML_WORKER_REGISTRY_INFO
0x14012989e  mov     cs:qword_1403C4770, rax
0x1401298a5  lea     rax, MSVML_WORKER_REGISTRY_WARNING
0x1401298ac  mov     cs:qword_1403C4768, rax
0x1401298b3  lea     rax, MSVML_WORKER_REGISTRY_ERROR
0x1401298ba  mov     cs:qword_1403C4760, rax
0x1401298c1  lea     rax, MSVML_WORKER_REGISTRY_CRITICAL
0x1401298c8  mov     cs:qword_1403C4758, rax
0x1401298cf  lea     rax, MSVML_WORKER_THREADS_INFO
0x1401298d6  mov     cs:qword_1403C4790, rax
0x1401298dd  lea     rax, MSVML_WORKER_THREADS_WARNING
0x1401298e4  mov     cs:qword_1403C4788, rax
0x1401298eb  lea     rax, MSVML_WORKER_THREADS_ERROR
0x1401298f2  mov     cs:qword_1403C4780, rax
0x1401298f9  lea     rax, MSVML_WORKER_THREADS_CRITICAL
0x140129900  mov     cs:qword_1403C4778, rax
0x140129907  lea     rax, MSVML_WORKER_REFCOUNTED_INFO
0x14012990e  mov     cs:qword_1403C47B0, rax
0x140129915  lea     rax, MSVML_WORKER_REFCOUNTED_WARNING
0x14012991c  mov     cs:qword_1403C47A8, rax
0x140129923  lea     rax, MSVML_WORKER_REFCOUNTED_ERROR
0x14012992a  mov     cs:qword_1403C47A0, rax
0x140129931  lea     rax, MSVML_WORKER_REFCOUNTED_CRITICAL
0x140129938  mov     cs:qword_1403C4798, rax
0x14012993f  lea     rax, MSVML_WORKER_WMI_INFO
0x140129946  mov     cs:qword_1403C47D0, rax
0x14012994d  lea     rax, MSVML_WORKER_WMI_WARNING
0x140129954  mov     cs:qword_1403C47C8, rax
0x14012995b  lea     rax, MSVML_WORKER_WMI_ERROR
0x140129962  mov     cs:qword_1403C47C0, rax
0x140129969  lea     rax, MSVML_WORKER_WMI_CRITICAL
0x140129970  mov     cs:qword_1403C47B8, rax
0x140129977  lea     rax, MSVM_WORKER_MIGRATION_DEBUG_CRITICAL
0x14012997e  mov     cs:qword_1403C82D8, rax
0x140129985  mov     cs:qword_1403C8318, rax
0x14012998c  lea     rax, MSVDEV_BIOS_INFO
0x140129993  mov     cs:qword_1403C5EF0, rax
0x14012999a  lea     rax, MSVDEV_BIOS_WARNING
0x1401299a1  mov     cs:qword_1403C5EE8, rax
0x1401299a8  lea     rax, MSVDEV_BIOS_ERROR
0x1401299af  mov     cs:qword_1403C5EE0, rax
0x1401299b6  lea     rax, MSVDEV_BIOS_CRITICAL
0x1401299bd  mov     cs:qword_1403C5ED8, rax
0x1401299c4  lea     rax, MSVDEV_CMOS_INFO
0x1401299cb  mov     cs:qword_1403C5F10, rax
0x1401299d2  lea     rax, MSVDEV_CMOS_WARNING
0x1401299d9  mov     cs:qword_1403C5F08, rax
0x1401299e0  lea     rax, MSVDEV_CMOS_ERROR
0x1401299e7  mov     cs:qword_1403C8330, r8
0x1401299ee  mov     cs:qword_1403C8328, rdx
0x1401299f5  mov     cs:qword_1403C8320, rcx
0x1401299fc  mov     cs:qword_1403C5F00, rax
0x140129a03  lea     rax, MSVDEV_CMOS_CRITICAL
0x140129a0a  mov     cs:qword_1403C5EF8, rax
0x140129a11  lea     rax, MSVDEV_POWER_MANAGEMENT_INFO
0x140129a18  mov     cs:qword_1403C5F30, rax
0x140129a1f  lea     rax, MSVDEV_POWER_MANAGEMENT_WARNING
0x140129a26  mov     cs:qword_1403C5F28, rax
0x140129a2d  lea     rax, MSVDEV_POWER_MANAGEMENT_ERROR
0x140129a34  mov     cs:qword_1403C5F20, rax
0x140129a3b  lea     rax, MSVDEV_POWER_MANAGEMENT_CRITICAL
0x140129a42  mov     cs:qword_1403C5F18, rax
0x140129a49  lea     rax, MSVDEV_SM_BUS_INFO
0x140129a50  mov     cs:qword_1403C5F50, rax
0x140129a57  lea     rax, MSVDEV_SM_BUS_WARNING
0x140129a5e  mov     cs:qword_1403C5F48, rax
0x140129a65  lea     rax, MSVDEV_SM_BUS_ERROR
0x140129a6c  mov     cs:qword_1403C5F40, rax
0x140129a73  lea     rax, MSVDEV_SM_BUS_CRITICAL
0x140129a7a  mov     cs:qword_1403C5F38, rax
0x140129a81  lea     rax, MSVDEV_ISA_BUS_INFO
0x140129a88  mov     cs:qword_1403C5F70, rax
0x140129a8f  lea     rax, MSVDEV_ISA_BUS_WARNING
0x140129a96  mov     cs:qword_1403C5F68, rax
0x140129a9d  lea     rax, MSVDEV_ISA_BUS_ERROR
0x140129aa4  mov     cs:qword_1403C5F60, rax
0x140129aab  lea     rax, MSVDEV_ISA_BUS_CRITICAL
0x140129ab2  mov     cs:qword_1403C5F58, rax
0x140129ab9  lea     rax, MSVDEV_PCI_BUS_INFO
0x140129ac0  mov     cs:qword_1403C5F90, rax
0x140129ac7  lea     rax, MSVDEV_PCI_BUS_WARNING
0x140129ace  mov     cs:qword_1403C5F88, rax
0x140129ad5  lea     rax, MSVDEV_PCI_BUS_ERROR
0x140129adc  mov     cs:qword_1403C5F80, rax
0x140129ae3  lea     rax, MSVDEV_PCI_BUS_CRITICAL; "2("
0x140129aea  mov     cs:qword_1403C5F78, rax
0x140129af1  lea     rax, MSVDEV_APIC_INFO
0x140129af8  mov     cs:qword_1403C5FB0, rax
0x140129aff  lea     rax, MSVDEV_APIC_WARNING
0x140129b06  mov     cs:qword_1403C5FA8, rax
0x140129b0d  lea     rax, MSVDEV_APIC_ERROR
0x140129b14  mov     cs:qword_1403C5FA0, rax
0x140129b1b  lea     rax, MSVDEV_APIC_CRITICAL
0x140129b22  mov     cs:qword_1403C5F98, rax
0x140129b29  lea     rax, MSVDEV_DMA_INFO
0x140129b30  mov     cs:qword_1403C5FD0, rax
0x140129b37  lea     rax, MSVDEV_DMA_WARNING
0x140129b3e  mov     cs:qword_1403C5FC8, rax
0x140129b45  lea     rax, MSVDEV_DMA_ERROR
0x140129b4c  mov     cs:qword_1403C5FC0, rax
0x140129b53  lea     rax, MSVDEV_DMA_CRITICAL
0x140129b5a  mov     cs:qword_1403C5FB8, rax
0x140129b61  lea     rax, MSVDEV_PIC_INFO
0x140129b68  mov     cs:qword_1403C5FF0, rax
0x140129b6f  lea     rax, MSVDEV_PIC_WARNING
0x140129b76  mov     cs:qword_1403C5FE8, rax
0x140129b7d  lea     rax, MSVDEV_PIC_ERROR
0x140129b84  mov     cs:qword_1403C5FE0, rax
0x140129b8b  lea     rax, MSVDEV_PIC_CRITICAL
0x140129b92  mov     cs:qword_1403C5FD8, rax
0x140129b99  lea     rax, MSVDEV_PIT_INFO
0x140129ba0  mov     cs:qword_1403C6010, rax
0x140129ba7  lea     rax, MSVDEV_PIT_WARNING
0x140129bae  mov     cs:qword_1403C6008, rax
0x140129bb5  lea     rax, MSVDEV_PIT_ERROR
0x140129bbc  mov     cs:qword_1403C6000, rax
0x140129bc3  lea     rax, MSVDEV_PIT_CRITICAL
0x140129bca  mov     cs:qword_1403C5FF8, rax
0x140129bd1  lea     rax, MSVDEV_SUPER_IO_INFO
0x140129bd8  mov     cs:qword_1403C6030, rax
0x140129bdf  lea     rax, MSVDEV_SUPER_IO_WARNING
0x140129be6  mov     cs:qword_1403C6028, rax
0x140129bed  lea     rax, MSVDEV_SUPER_IO_ERROR
0x140129bf4  mov     cs:qword_1403C6020, rax
0x140129bfb  lea     rax, MSVDEV_SUPER_IO_CRITICAL
0x140129c02  mov     cs:qword_1403C6018, rax
0x140129c09  lea     rax, MSVDEV_SERIAL_CONTROLLER_INFO
0x140129c10  mov     cs:qword_1403C6050, rax
0x140129c17  lea     rax, MSVDEV_SERIAL_CONTROLLER_WARNING
0x140129c1e  mov     cs:qword_1403C6048, rax
0x140129c25  lea     rax, MSVDEV_SERIAL_CONTROLLER_ERROR
0x140129c2c  mov     cs:qword_1403C6040, rax
0x140129c33  lea     rax, MSVDEV_SERIAL_CONTROLLER_CRITICAL
0x140129c3a  mov     cs:qword_1403C6038, rax
0x140129c41  lea     r8, MSVDEV_MOUSE_INFO; "|)"
0x140129c48  lea     rax, MSVDEV_KEYBOARD_INFO
0x140129c4f  mov     cs:qword_1403C6090, r8
0x140129c56  mov     cs:qword_1403C6070, rax
0x140129c5d  lea     rdx, MSVDEV_MOUSE_WARNING
0x140129c64  lea     rax, MSVDEV_KEYBOARD_WARNING
0x140129c6b  mov     cs:qword_1403C6088, rdx
0x140129c72  mov     cs:qword_1403C6068, rax
0x140129c79  lea     rcx, MSVDEV_MOUSE_ERROR
0x140129c80  lea     rax, MSVDEV_KEYBOARD_ERROR
0x140129c87  mov     cs:qword_1403C6080, rcx
0x140129c8e  mov     cs:qword_1403C6060, rax
0x140129c95  lea     rax, MSVDEV_KEYBOARD_CRITICAL
0x140129c9c  mov     cs:qword_1403C6058, rax
0x140129ca3  lea     rax, MSVDEV_MOUSE_CRITICAL
0x140129caa  mov     cs:qword_1403C6078, rax
0x140129cb1  mov     cs:qword_1403C6278, rax
0x140129cb8  lea     rax, MSVDEV_FLOPPY_CONTROLLER_INFO
0x140129cbf  mov     cs:qword_1403C60B0, rax
0x140129cc6  lea     rax, MSVDEV_FLOPPY_CONTROLLER_WARNING
0x140129ccd  mov     cs:qword_1403C60A8, rax
0x140129cd4  lea     rax, MSVDEV_FLOPPY_CONTROLLER_ERROR
0x140129cdb  mov     cs:qword_1403C60A0, rax
0x140129ce2  lea     rax, MSVDEV_FLOPPY_CONTROLLER_CRITICAL
0x140129ce9  mov     cs:qword_1403C6098, rax
0x140129cf0  lea     rax, MSVDEV_FLOPPY_DRIVE_INFO
0x140129cf7  mov     cs:qword_1403C60D0, rax
0x140129cfe  lea     rax, MSVDEV_FLOPPY_DRIVE_WARNING
0x140129d05  mov     cs:qword_1403C60C8, rax
0x140129d0c  lea     rax, MSVDEV_FLOPPY_DRIVE_ERROR
0x140129d13  mov     cs:qword_1403C60C0, rax
0x140129d1a  lea     rax, MSVDEV_FLOPPY_DRIVE_CRITICAL
0x140129d21  mov     cs:qword_1403C60B8, rax
0x140129d28  lea     rax, MSVDEV_IDE_CONTROLLER_INFO
0x140129d2f  mov     cs:qword_1403C60F0, rax
0x140129d36  lea     rax, MSVDEV_IDE_CONTROLLER_WARNING
0x140129d3d  mov     cs:qword_1403C60E8, rax
0x140129d44  lea     rax, MSVDEV_IDE_CONTROLLER_ERROR
0x140129d4b  mov     cs:qword_1403C60E0, rax
0x140129d52  lea     rax, MSVDEV_IDE_CONTROLLER_CRITICAL
0x140129d59  mov     cs:qword_1403C60D8, rax
0x140129d60  lea     rax, MSVDEV_IDE_ATTACHMENT_INFO
0x140129d67  mov     cs:qword_1403C6110, rax
0x140129d6e  lea     rax, MSVDEV_IDE_ATTACHMENT_WARNING
0x140129d75  mov     cs:qword_1403C6108, rax
0x140129d7c  lea     rax, MSVDEV_IDE_ATTACHMENT_ERROR
0x140129d83  mov     cs:qword_1403C6100, rax
0x140129d8a  lea     rax, MSVDEV_IDE_ATTACHMENT_CRITICAL
0x140129d91  mov     cs:qword_1403C60F8, rax
0x140129d98  lea     rax, MSVDEV_SCSI_CONTROLLER_INFO
0x140129d9f  mov     cs:qword_1403C6130, rax
0x140129da6  lea     rax, MSVDEV_SCSI_CONTROLLER_WARNING
0x140129dad  mov     cs:qword_1403C6128, rax
0x140129db4  lea     rax, MSVDEV_SCSI_CONTROLLER_ERROR
0x140129dbb  mov     cs:qword_1403C6120, rax
0x140129dc2  lea     rax, MSVDEV_SCSI_CONTROLLER_CRITICAL
0x140129dc9  mov     cs:qword_1403C6118, rax
0x140129dd0  lea     rax, MSVDEV_SCSI_BUS_INFO
0x140129dd7  mov     cs:qword_1403C6150, rax
0x140129dde  lea     rax, MSVDEV_SCSI_BUS_WARNING
0x140129de5  mov     cs:qword_1403C6148, rax
0x140129dec  lea     rax, MSVDEV_SCSI_BUS_ERROR
0x140129df3  mov     cs:qword_1403C6140, rax
0x140129dfa  lea     rax, MSVDEV_SCSI_BUS_CRITICAL
0x140129e01  mov     cs:qword_1403C6138, rax
0x140129e08  lea     rax, MSVDEV_SCSI_ATTACHMENT_INFO
0x140129e0f  mov     cs:qword_1403C6170, rax
0x140129e16  lea     rax, MSVDEV_SCSI_ATTACHMENT_WARNING
0x140129e1d  mov     cs:qword_1403C6168, rax
0x140129e24  lea     rax, MSVDEV_SCSI_ATTACHMENT_ERROR
0x140129e2b  mov     cs:qword_1403C6160, rax
0x140129e32  lea     rax, MSVDEV_SCSI_ATTACHMENT_CRITICAL
0x140129e39  mov     cs:qword_1403C6158, rax
0x140129e40  lea     rax, MSVDEV_MEDIA_INFO
0x140129e47  mov     cs:qword_1403C6190, rax
0x140129e4e  lea     rax, MSVDEV_MEDIA_WARNING
0x140129e55  mov     cs:qword_1403C6290, r8
0x140129e5c  mov     cs:qword_1403C6288, rdx
0x140129e63  mov     cs:qword_1403C6280, rcx
0x140129e6a  mov     cs:qword_1403C6188, rax
0x140129e71  lea     r8, MSVDEV_VIDEO_CONTROLLER_INFO
0x140129e78  lea     rax, MSVDEV_MEDIA_ERROR
0x140129e7f  mov     cs:qword_1403C61F0, r8
0x140129e86  mov     cs:qword_1403C6180, rax
0x140129e8d  lea     rdx, MSVDEV_VIDEO_CONTROLLER_WARNING; ">+"
0x140129e94  lea     rax, MSVDEV_MEDIA_CRITICAL
0x140129e9b  mov     cs:qword_1403C61E8, rdx
0x140129ea2  mov     cs:qword_1403C6178, rax
0x140129ea9  lea     rcx, MSVDEV_VIDEO_CONTROLLER_ERROR
0x140129eb0  lea     rax, MSVDEV_HARD_DRIVE_INFO
0x140129eb7  mov     cs:qword_1403C61E0, rcx
0x140129ebe  mov     cs:qword_1403C61B0, rax
0x140129ec5  lea     rax, MSVDEV_HARD_DRIVE_WARNING
0x140129ecc  mov     cs:qword_1403C61A8, rax
0x140129ed3  lea     rax, MSVDEV_HARD_DRIVE_ERROR
0x140129eda  mov     cs:qword_1403C61A0, rax
0x140129ee1  lea     rax, MSVDEV_HARD_DRIVE_CRITICAL
0x140129ee8  mov     cs:qword_1403C6198, rax
0x140129eef  lea     rax, MSVDEV_ETHERNET_INFO
0x140129ef6  mov     cs:qword_1403C61D0, rax
0x140129efd  lea     rax, MSVDEV_ETHERNET_WARNING
0x140129f04  mov     cs:qword_1403C61C8, rax
0x140129f0b  lea     rax, MSVDEV_ETHERNET_ERROR
0x140129f12  mov     cs:qword_1403C61C0, rax
0x140129f19  lea     rax, MSVDEV_ETHERNET_CRITICAL
0x140129f20  mov     cs:qword_1403C61B8, rax
0x140129f27  lea     rax, MSVDEV_VIDEO_CONTROLLER_CRITICAL; "R+"
0x140129f2e  mov     cs:qword_1403C61D8, rax
0x140129f35  mov     cs:qword_1403C6258, rax
0x140129f3c  lea     rax, MSVDEV_REPOSITORY_INFO
0x140129f43  mov     cs:qword_1403C6210, rax
0x140129f4a  lea     rax, MSVDEV_REPOSITORY_WARNING; "f+"
0x140129f51  mov     cs:qword_1403C6208, rax
0x140129f58  lea     rax, MSVDEV_REPOSITORY_ERROR
0x140129f5f  mov     cs:qword_1403C6200, rax
0x140129f66  lea     rax, MSVDEV_REPOSITORY_CRITICAL; "z+"
0x140129f6d  mov     cs:qword_1403C61F8, rax
0x140129f74  lea     rax, MSVDEV_REMOTING_INFO
0x140129f7b  mov     cs:qword_1403C6230, rax
0x140129f82  lea     rax, MSVDEV_REMOTING_WARNING
0x140129f89  mov     cs:qword_1403C6228, rax
0x140129f90  lea     rax, MSVDEV_REMOTING_ERROR
0x140129f97  mov     cs:qword_1403C6220, rax
0x140129f9e  lea     rax, MSVDEV_REMOTING_CRITICAL
0x140129fa5  mov     cs:qword_1403C6218, rax
0x140129fac  lea     rax, MSVDEV_HID_INFO
0x140129fb3  mov     cs:qword_1403C6250, rax
0x140129fba  lea     rax, MSVDEV_HID_WARNING
0x140129fc1  mov     cs:qword_1403C6248, rax
0x140129fc8  lea     rax, MSVDEV_HID_ERROR
0x140129fcf  mov     cs:qword_1403C6240, rax
0x140129fd6  lea     rax, MSVDEV_HID_CRITICAL
  ... truncated ...
```
