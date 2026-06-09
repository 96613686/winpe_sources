# WorkerModule::InitializeSelf(void)

- ea: `0x14013d6cc`
- end: `0x14013e0df`
- name: `?InitializeSelf@WorkerModule@@QEAAXXZ`
- size: `2579`
- prototype: `void __fastcall(WorkerModule *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400c3838`

## callees

- `0x140042260`
- `0x14004c15c`
- `0x14004edc4`
- `0x140054a90`
- `0x14005b648`
- `0x140132960`
- `0x14013361c`
- `0x14013b6c0`
- `0x14013b768`
- `0x14013d6cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14013e066`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14013e066`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14013e0ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14013e0ba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14013dfea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14013dfea`

## string_xrefs

- `0x14013e072`: `Cannot create initialization timeout timer. Error code: %d.\n`

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

  qword_1403B8180 = (__int64)MSVML_WORKER_EXCEPTIONS_INFO;
  qword_1403BBD60 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_INFO;
  qword_1403B8178 = (__int64)MSVML_WORKER_EXCEPTIONS_WARNING;
  qword_1403BBD58 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_WARNING;
  qword_1403B8170 = (__int64)MSVML_WORKER_EXCEPTIONS_ERROR;
  qword_1403BBD50 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_ERROR;
  qword_1403B8168 = (__int64)MSVML_WORKER_EXCEPTIONS_CRITICAL;
  qword_1403B81A0 = (__int64)MSVML_WORKER_MODULES_INFO;
  qword_1403B8198 = (__int64)MSVML_WORKER_MODULES_WARNING;
  qword_1403B8190 = (__int64)MSVML_WORKER_MODULES_ERROR;
  qword_1403B8188 = (__int64)MSVML_WORKER_MODULES_CRITICAL;
  qword_1403B81C0 = (__int64)MSVML_WORKER_COM_INFO;
  qword_1403B81B8 = (__int64)MSVML_WORKER_COM_WARNING;
  qword_1403B81B0 = (__int64)MSVML_WORKER_COM_ERROR;
  qword_1403B81A8 = (__int64)MSVML_WORKER_COM_CRITICAL;
  qword_1403B81E0 = (__int64)MSVML_WORKER_REGISTRY_INFO;
  qword_1403B81D8 = (__int64)MSVML_WORKER_REGISTRY_WARNING;
  qword_1403B81D0 = (__int64)MSVML_WORKER_REGISTRY_ERROR;
  qword_1403B81C8 = (__int64)MSVML_WORKER_REGISTRY_CRITICAL;
  qword_1403B8200 = (__int64)MSVML_WORKER_THREADS_INFO;
  qword_1403B81F8 = (__int64)MSVML_WORKER_THREADS_WARNING;
  qword_1403B81F0 = (__int64)MSVML_WORKER_THREADS_ERROR;
  qword_1403B81E8 = (__int64)MSVML_WORKER_THREADS_CRITICAL;
  qword_1403B8220 = (__int64)MSVML_WORKER_REFCOUNTED_INFO;
  qword_1403B8218 = (__int64)MSVML_WORKER_REFCOUNTED_WARNING;
  qword_1403B8210 = (__int64)MSVML_WORKER_REFCOUNTED_ERROR;
  qword_1403B8208 = (__int64)MSVML_WORKER_REFCOUNTED_CRITICAL;
  qword_1403B8240 = (__int64)MSVML_WORKER_WMI_INFO;
  qword_1403B8238 = (__int64)MSVML_WORKER_WMI_WARNING;
  qword_1403B8230 = (__int64)MSVML_WORKER_WMI_ERROR;
  qword_1403B8228 = (__int64)MSVML_WORKER_WMI_CRITICAL;
  qword_1403BBD48 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_CRITICAL;
  qword_1403BBD88 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_CRITICAL;
  qword_1403B9960 = (__int64)MSVDEV_BIOS_INFO;
  qword_1403B9958 = (__int64)MSVDEV_BIOS_WARNING;
  qword_1403B9950 = (__int64)MSVDEV_BIOS_ERROR;
  qword_1403B9948 = (__int64)MSVDEV_BIOS_CRITICAL;
  qword_1403B9980 = (__int64)MSVDEV_CMOS_INFO;
  qword_1403B9978 = (__int64)MSVDEV_CMOS_WARNING;
  qword_1403BBDA0 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_INFO;
  qword_1403BBD98 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_WARNING;
  qword_1403BBD90 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_ERROR;
  qword_1403B9970 = (__int64)MSVDEV_CMOS_ERROR;
  qword_1403B9968 = (__int64)MSVDEV_CMOS_CRITICAL;
  qword_1403B99A0 = (__int64)MSVDEV_POWER_MANAGEMENT_INFO;
  qword_1403B9998 = (__int64)MSVDEV_POWER_MANAGEMENT_WARNING;
  qword_1403B9990 = (__int64)MSVDEV_POWER_MANAGEMENT_ERROR;
  qword_1403B9988 = (__int64)MSVDEV_POWER_MANAGEMENT_CRITICAL;
  qword_1403B99C0 = (__int64)MSVDEV_SM_BUS_INFO;
  qword_1403B99B8 = (__int64)MSVDEV_SM_BUS_WARNING;
  qword_1403B99B0 = (__int64)MSVDEV_SM_BUS_ERROR;
  qword_1403B99A8 = (__int64)MSVDEV_SM_BUS_CRITICAL;
  qword_1403B99E0 = (__int64)MSVDEV_ISA_BUS_INFO;
  qword_1403B99D8 = (__int64)MSVDEV_ISA_BUS_WARNING;
  qword_1403B99D0 = (__int64)MSVDEV_ISA_BUS_ERROR;
  qword_1403B99C8 = (__int64)MSVDEV_ISA_BUS_CRITICAL;
  qword_1403B9A00 = (__int64)MSVDEV_PCI_BUS_INFO;
  qword_1403B99F8 = (__int64)MSVDEV_PCI_BUS_WARNING;
  qword_1403B99F0 = (__int64)MSVDEV_PCI_BUS_ERROR;
  qword_1403B99E8 = (__int64)"2(";
  qword_1403B9A20 = (__int64)MSVDEV_APIC_INFO;
  qword_1403B9A18 = (__int64)MSVDEV_APIC_WARNING;
  qword_1403B9A10 = (__int64)MSVDEV_APIC_ERROR;
  qword_1403B9A08 = (__int64)MSVDEV_APIC_CRITICAL;
  qword_1403B9A40 = (__int64)MSVDEV_DMA_INFO;
  qword_1403B9A38 = (__int64)MSVDEV_DMA_WARNING;
  qword_1403B9A30 = (__int64)MSVDEV_DMA_ERROR;
  qword_1403B9A28 = (__int64)MSVDEV_DMA_CRITICAL;
  qword_1403B9A60 = (__int64)MSVDEV_PIC_INFO;
  qword_1403B9A58 = (__int64)MSVDEV_PIC_WARNING;
  qword_1403B9A50 = (__int64)MSVDEV_PIC_ERROR;
  qword_1403B9A48 = (__int64)MSVDEV_PIC_CRITICAL;
  qword_1403B9A80 = (__int64)MSVDEV_PIT_INFO;
  qword_1403B9A78 = (__int64)MSVDEV_PIT_WARNING;
  qword_1403B9A70 = (__int64)MSVDEV_PIT_ERROR;
  qword_1403B9A68 = (__int64)MSVDEV_PIT_CRITICAL;
  qword_1403B9AA0 = (__int64)MSVDEV_SUPER_IO_INFO;
  qword_1403B9A98 = (__int64)MSVDEV_SUPER_IO_WARNING;
  qword_1403B9A90 = (__int64)MSVDEV_SUPER_IO_ERROR;
  qword_1403B9A88 = (__int64)MSVDEV_SUPER_IO_CRITICAL;
  qword_1403B9AC0 = (__int64)MSVDEV_SERIAL_CONTROLLER_INFO;
  qword_1403B9AB8 = (__int64)MSVDEV_SERIAL_CONTROLLER_WARNING;
  qword_1403B9AB0 = (__int64)MSVDEV_SERIAL_CONTROLLER_ERROR;
  qword_1403B9AA8 = (__int64)MSVDEV_SERIAL_CONTROLLER_CRITICAL;
  qword_1403B9B00 = (__int64)"|)";
  qword_1403B9AE0 = (__int64)MSVDEV_KEYBOARD_INFO;
  qword_1403B9AF8 = (__int64)MSVDEV_MOUSE_WARNING;
  qword_1403B9AD8 = (__int64)MSVDEV_KEYBOARD_WARNING;
  qword_1403B9AF0 = (__int64)MSVDEV_MOUSE_ERROR;
  qword_1403B9AD0 = (__int64)MSVDEV_KEYBOARD_ERROR;
  qword_1403B9AC8 = (__int64)MSVDEV_KEYBOARD_CRITICAL;
  qword_1403B9AE8 = (__int64)MSVDEV_MOUSE_CRITICAL;
  qword_1403B9CE8 = (__int64)MSVDEV_MOUSE_CRITICAL;
  qword_1403B9B20 = (__int64)MSVDEV_FLOPPY_CONTROLLER_INFO;
  qword_1403B9B18 = (__int64)MSVDEV_FLOPPY_CONTROLLER_WARNING;
  qword_1403B9B10 = (__int64)MSVDEV_FLOPPY_CONTROLLER_ERROR;
  qword_1403B9B08 = (__int64)MSVDEV_FLOPPY_CONTROLLER_CRITICAL;
  qword_1403B9B40 = (__int64)MSVDEV_FLOPPY_DRIVE_INFO;
  qword_1403B9B38 = (__int64)MSVDEV_FLOPPY_DRIVE_WARNING;
  qword_1403B9B30 = (__int64)MSVDEV_FLOPPY_DRIVE_ERROR;
  qword_1403B9B28 = (__int64)MSVDEV_FLOPPY_DRIVE_CRITICAL;
  qword_1403B9B60 = (__int64)MSVDEV_IDE_CONTROLLER_INFO;
  qword_1403B9B58 = (__int64)MSVDEV_IDE_CONTROLLER_WARNING;
  qword_1403B9B50 = (__int64)MSVDEV_IDE_CONTROLLER_ERROR;
  qword_1403B9B48 = (__int64)MSVDEV_IDE_CONTROLLER_CRITICAL;
  qword_1403B9B80 = (__int64)MSVDEV_IDE_ATTACHMENT_INFO;
  qword_1403B9B78 = (__int64)MSVDEV_IDE_ATTACHMENT_WARNING;
  qword_1403B9B70 = (__int64)MSVDEV_IDE_ATTACHMENT_ERROR;
  qword_1403B9B68 = (__int64)MSVDEV_IDE_ATTACHMENT_CRITICAL;
  qword_1403B9BA0 = (__int64)MSVDEV_SCSI_CONTROLLER_INFO;
  qword_1403B9B98 = (__int64)MSVDEV_SCSI_CONTROLLER_WARNING;
  qword_1403B9B90 = (__int64)MSVDEV_SCSI_CONTROLLER_ERROR;
  qword_1403B9B88 = (__int64)MSVDEV_SCSI_CONTROLLER_CRITICAL;
  qword_1403B9BC0 = (__int64)MSVDEV_SCSI_BUS_INFO;
  qword_1403B9BB8 = (__int64)MSVDEV_SCSI_BUS_WARNING;
  qword_1403B9BB0 = (__int64)MSVDEV_SCSI_BUS_ERROR;
  qword_1403B9BA8 = (__int64)MSVDEV_SCSI_BUS_CRITICAL;
  qword_1403B9BE0 = (__int64)MSVDEV_SCSI_ATTACHMENT_INFO;
  qword_1403B9BD8 = (__int64)MSVDEV_SCSI_ATTACHMENT_WARNING;
  qword_1403B9BD0 = (__int64)MSVDEV_SCSI_ATTACHMENT_ERROR;
  qword_1403B9BC8 = (__int64)MSVDEV_SCSI_ATTACHMENT_CRITICAL;
  qword_1403B9C00 = (__int64)MSVDEV_MEDIA_INFO;
  qword_1403B9D00 = (__int64)"|)";
  qword_1403B9CF8 = (__int64)MSVDEV_MOUSE_WARNING;
  qword_1403B9CF0 = (__int64)MSVDEV_MOUSE_ERROR;
  qword_1403B9BF8 = (__int64)MSVDEV_MEDIA_WARNING;
  qword_1403B9C60 = (__int64)MSVDEV_VIDEO_CONTROLLER_INFO;
  qword_1403B9BF0 = (__int64)MSVDEV_MEDIA_ERROR;
  qword_1403B9C58 = (__int64)">+";
  qword_1403B9BE8 = (__int64)MSVDEV_MEDIA_CRITICAL;
  qword_1403B9C50 = (__int64)MSVDEV_VIDEO_CONTROLLER_ERROR;
  qword_1403B9C20 = (__int64)MSVDEV_HARD_DRIVE_INFO;
  qword_1403B9C18 = (__int64)MSVDEV_HARD_DRIVE_WARNING;
  qword_1403B9C10 = (__int64)MSVDEV_HARD_DRIVE_ERROR;
  qword_1403B9C08 = (__int64)MSVDEV_HARD_DRIVE_CRITICAL;
  qword_1403B9C40 = (__int64)MSVDEV_ETHERNET_INFO;
  qword_1403B9C38 = (__int64)MSVDEV_ETHERNET_WARNING;
  qword_1403B9C30 = (__int64)MSVDEV_ETHERNET_ERROR;
  qword_1403B9C28 = (__int64)MSVDEV_ETHERNET_CRITICAL;
  qword_1403B9C48 = (__int64)"R+";
  qword_1403B9CC8 = (__int64)"R+";
  qword_1403B9C80 = (__int64)MSVDEV_REPOSITORY_INFO;
  qword_1403B9C78 = (__int64)"f+";
  qword_1403B9C70 = (__int64)MSVDEV_REPOSITORY_ERROR;
  qword_1403B9C68 = (__int64)MSVDEV_REPOSITORY_CRITICAL;
  qword_1403B9CA0 = (__int64)MSVDEV_REMOTING_INFO;
  qword_1403B9C98 = (__int64)MSVDEV_REMOTING_WARNING;
  qword_1403B9C90 = (__int64)MSVDEV_REMOTING_ERROR;
  qword_1403B9C88 = (__int64)MSVDEV_REMOTING_CRITICAL;
  qword_1403B9CC0 = (__int64)MSVDEV_HID_INFO;
  qword_1403B9CB8 = (__int64)MSVDEV_HID_WARNING;
  qword_1403B9CB0 = (__int64)MSVDEV_HID_ERROR;
  qword_1403B9CA8 = (__int64)MSVDEV_HID_CRITICAL;
  qword_1403B9D40 = (__int64)MSVDEV_VIRTUAL_MOTHERBOARD_INFO;
  qword_1403B9D38 = (__int64)"6)";
  qword_1403B9D30 = (__int64)MSVDEV_VIRTUAL_MOTHERBOARD_ERROR;
  qword_1403B9D28 = (__int64)MSVDEV_VIRTUAL_MOTHERBOARD_CRITICAL;
  qword_1403BAD60 = (__int64)MSVDEV_DYNMEM_INFO;
  qword_1403BAD58 = (__int64)MSVDEV_DYNMEM_WARNING;
  qword_1403BAD50 = (__int64)MSVDEV_DYNMEM_ERROR;
  qword_1403BAD48 = (__int64)MSVDEV_DYNMEM_CRITICAL;
  qword_1403BAD80 = (__int64)MSVDEV_SYNTH3DVIDEO_INFO;
  qword_1403BAD78 = (__int64)MSVDEV_SYNTH3DVIDEO_WARNING;
  qword_1403BAD70 = (__int64)MSVDEV_SYNTH3DVIDEO_ERROR;
  qword_1403BAD68 = (__int64)MSVDEV_SYNTH3DVIDEO_CRITICAL;
  qword_1403B9CE0 = (__int64)MSVDEV_VIDEO_CONTROLLER_INFO;
  qword_1403B9CD8 = (__int64)">+";
  qword_1403B9CD0 = (__int64)MSVDEV_VIDEO_CONTROLLER_ERROR;
  std::function<void (unsigned short,unsigned short const *)>::operator=<void (&)(unsigned short,unsigned short const *),0>(g_HvsTraceFunctions);
  std::function<bool (unsigned short)>::operator=<int (&)(unsigned short),0>(qword_1403C0C60);
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
0x14013d6cc  sub     rsp, 0D8h
0x14013d6d3  mov     rax, cs:__security_cookie
0x14013d6da  xor     rax, rsp
0x14013d6dd  mov     [rsp+0D8h+var_10], rax
0x14013d6e5  lea     rax, MSVML_WORKER_EXCEPTIONS_INFO
0x14013d6ec  mov     cs:qword_1403B8180, rax
0x14013d6f3  lea     r8, MSVM_WORKER_MIGRATION_DEBUG_INFO
0x14013d6fa  lea     rax, MSVML_WORKER_EXCEPTIONS_WARNING
0x14013d701  mov     cs:qword_1403BBD60, r8
0x14013d708  mov     cs:qword_1403B8178, rax
0x14013d70f  lea     rdx, MSVM_WORKER_MIGRATION_DEBUG_WARNING
0x14013d716  lea     rax, MSVML_WORKER_EXCEPTIONS_ERROR
0x14013d71d  mov     cs:qword_1403BBD58, rdx
0x14013d724  mov     cs:qword_1403B8170, rax
0x14013d72b  lea     rcx, MSVM_WORKER_MIGRATION_DEBUG_ERROR
0x14013d732  lea     rax, MSVML_WORKER_EXCEPTIONS_CRITICAL
0x14013d739  mov     cs:qword_1403BBD50, rcx
0x14013d740  mov     cs:qword_1403B8168, rax
0x14013d747  lea     rax, MSVML_WORKER_MODULES_INFO
0x14013d74e  mov     cs:qword_1403B81A0, rax
0x14013d755  lea     rax, MSVML_WORKER_MODULES_WARNING
0x14013d75c  mov     cs:qword_1403B8198, rax
0x14013d763  lea     rax, MSVML_WORKER_MODULES_ERROR
0x14013d76a  mov     cs:qword_1403B8190, rax
0x14013d771  lea     rax, MSVML_WORKER_MODULES_CRITICAL
0x14013d778  mov     cs:qword_1403B8188, rax
0x14013d77f  lea     rax, MSVML_WORKER_COM_INFO
0x14013d786  mov     cs:qword_1403B81C0, rax
0x14013d78d  lea     rax, MSVML_WORKER_COM_WARNING
0x14013d794  mov     cs:qword_1403B81B8, rax
0x14013d79b  lea     rax, MSVML_WORKER_COM_ERROR
0x14013d7a2  mov     cs:qword_1403B81B0, rax
0x14013d7a9  lea     rax, MSVML_WORKER_COM_CRITICAL
0x14013d7b0  mov     cs:qword_1403B81A8, rax
0x14013d7b7  lea     rax, MSVML_WORKER_REGISTRY_INFO
0x14013d7be  mov     cs:qword_1403B81E0, rax
0x14013d7c5  lea     rax, MSVML_WORKER_REGISTRY_WARNING
0x14013d7cc  mov     cs:qword_1403B81D8, rax
0x14013d7d3  lea     rax, MSVML_WORKER_REGISTRY_ERROR
0x14013d7da  mov     cs:qword_1403B81D0, rax
0x14013d7e1  lea     rax, MSVML_WORKER_REGISTRY_CRITICAL
0x14013d7e8  mov     cs:qword_1403B81C8, rax
0x14013d7ef  lea     rax, MSVML_WORKER_THREADS_INFO
0x14013d7f6  mov     cs:qword_1403B8200, rax
0x14013d7fd  lea     rax, MSVML_WORKER_THREADS_WARNING
0x14013d804  mov     cs:qword_1403B81F8, rax
0x14013d80b  lea     rax, MSVML_WORKER_THREADS_ERROR
0x14013d812  mov     cs:qword_1403B81F0, rax
0x14013d819  lea     rax, MSVML_WORKER_THREADS_CRITICAL
0x14013d820  mov     cs:qword_1403B81E8, rax
0x14013d827  lea     rax, MSVML_WORKER_REFCOUNTED_INFO
0x14013d82e  mov     cs:qword_1403B8220, rax
0x14013d835  lea     rax, MSVML_WORKER_REFCOUNTED_WARNING
0x14013d83c  mov     cs:qword_1403B8218, rax
0x14013d843  lea     rax, MSVML_WORKER_REFCOUNTED_ERROR
0x14013d84a  mov     cs:qword_1403B8210, rax
0x14013d851  lea     rax, MSVML_WORKER_REFCOUNTED_CRITICAL
0x14013d858  mov     cs:qword_1403B8208, rax
0x14013d85f  lea     rax, MSVML_WORKER_WMI_INFO
0x14013d866  mov     cs:qword_1403B8240, rax
0x14013d86d  lea     rax, MSVML_WORKER_WMI_WARNING
0x14013d874  mov     cs:qword_1403B8238, rax
0x14013d87b  lea     rax, MSVML_WORKER_WMI_ERROR
0x14013d882  mov     cs:qword_1403B8230, rax
0x14013d889  lea     rax, MSVML_WORKER_WMI_CRITICAL
0x14013d890  mov     cs:qword_1403B8228, rax
0x14013d897  lea     rax, MSVM_WORKER_MIGRATION_DEBUG_CRITICAL
0x14013d89e  mov     cs:qword_1403BBD48, rax
0x14013d8a5  mov     cs:qword_1403BBD88, rax
0x14013d8ac  lea     rax, MSVDEV_BIOS_INFO
0x14013d8b3  mov     cs:qword_1403B9960, rax
0x14013d8ba  lea     rax, MSVDEV_BIOS_WARNING
0x14013d8c1  mov     cs:qword_1403B9958, rax
0x14013d8c8  lea     rax, MSVDEV_BIOS_ERROR
0x14013d8cf  mov     cs:qword_1403B9950, rax
0x14013d8d6  lea     rax, MSVDEV_BIOS_CRITICAL
0x14013d8dd  mov     cs:qword_1403B9948, rax
0x14013d8e4  lea     rax, MSVDEV_CMOS_INFO
0x14013d8eb  mov     cs:qword_1403B9980, rax
0x14013d8f2  lea     rax, MSVDEV_CMOS_WARNING
0x14013d8f9  mov     cs:qword_1403B9978, rax
0x14013d900  lea     rax, MSVDEV_CMOS_ERROR
0x14013d907  mov     cs:qword_1403BBDA0, r8
0x14013d90e  mov     cs:qword_1403BBD98, rdx
0x14013d915  mov     cs:qword_1403BBD90, rcx
0x14013d91c  mov     cs:qword_1403B9970, rax
0x14013d923  lea     rax, MSVDEV_CMOS_CRITICAL
0x14013d92a  mov     cs:qword_1403B9968, rax
0x14013d931  lea     rax, MSVDEV_POWER_MANAGEMENT_INFO
0x14013d938  mov     cs:qword_1403B99A0, rax
0x14013d93f  lea     rax, MSVDEV_POWER_MANAGEMENT_WARNING
0x14013d946  mov     cs:qword_1403B9998, rax
0x14013d94d  lea     rax, MSVDEV_POWER_MANAGEMENT_ERROR
0x14013d954  mov     cs:qword_1403B9990, rax
0x14013d95b  lea     rax, MSVDEV_POWER_MANAGEMENT_CRITICAL
0x14013d962  mov     cs:qword_1403B9988, rax
0x14013d969  lea     rax, MSVDEV_SM_BUS_INFO
0x14013d970  mov     cs:qword_1403B99C0, rax
0x14013d977  lea     rax, MSVDEV_SM_BUS_WARNING
0x14013d97e  mov     cs:qword_1403B99B8, rax
0x14013d985  lea     rax, MSVDEV_SM_BUS_ERROR
0x14013d98c  mov     cs:qword_1403B99B0, rax
0x14013d993  lea     rax, MSVDEV_SM_BUS_CRITICAL
0x14013d99a  mov     cs:qword_1403B99A8, rax
0x14013d9a1  lea     rax, MSVDEV_ISA_BUS_INFO
0x14013d9a8  mov     cs:qword_1403B99E0, rax
0x14013d9af  lea     rax, MSVDEV_ISA_BUS_WARNING
0x14013d9b6  mov     cs:qword_1403B99D8, rax
0x14013d9bd  lea     rax, MSVDEV_ISA_BUS_ERROR
0x14013d9c4  mov     cs:qword_1403B99D0, rax
0x14013d9cb  lea     rax, MSVDEV_ISA_BUS_CRITICAL
0x14013d9d2  mov     cs:qword_1403B99C8, rax
0x14013d9d9  lea     rax, MSVDEV_PCI_BUS_INFO
0x14013d9e0  mov     cs:qword_1403B9A00, rax
0x14013d9e7  lea     rax, MSVDEV_PCI_BUS_WARNING
0x14013d9ee  mov     cs:qword_1403B99F8, rax
0x14013d9f5  lea     rax, MSVDEV_PCI_BUS_ERROR
0x14013d9fc  mov     cs:qword_1403B99F0, rax
0x14013da03  lea     rax, MSVDEV_PCI_BUS_CRITICAL; "2("
0x14013da0a  mov     cs:qword_1403B99E8, rax
0x14013da11  lea     rax, MSVDEV_APIC_INFO
0x14013da18  mov     cs:qword_1403B9A20, rax
0x14013da1f  lea     rax, MSVDEV_APIC_WARNING
0x14013da26  mov     cs:qword_1403B9A18, rax
0x14013da2d  lea     rax, MSVDEV_APIC_ERROR
0x14013da34  mov     cs:qword_1403B9A10, rax
0x14013da3b  lea     rax, MSVDEV_APIC_CRITICAL
0x14013da42  mov     cs:qword_1403B9A08, rax
0x14013da49  lea     rax, MSVDEV_DMA_INFO
0x14013da50  mov     cs:qword_1403B9A40, rax
0x14013da57  lea     rax, MSVDEV_DMA_WARNING
0x14013da5e  mov     cs:qword_1403B9A38, rax
0x14013da65  lea     rax, MSVDEV_DMA_ERROR
0x14013da6c  mov     cs:qword_1403B9A30, rax
0x14013da73  lea     rax, MSVDEV_DMA_CRITICAL
0x14013da7a  mov     cs:qword_1403B9A28, rax
0x14013da81  lea     rax, MSVDEV_PIC_INFO
0x14013da88  mov     cs:qword_1403B9A60, rax
0x14013da8f  lea     rax, MSVDEV_PIC_WARNING
0x14013da96  mov     cs:qword_1403B9A58, rax
0x14013da9d  lea     rax, MSVDEV_PIC_ERROR
0x14013daa4  mov     cs:qword_1403B9A50, rax
0x14013daab  lea     rax, MSVDEV_PIC_CRITICAL
0x14013dab2  mov     cs:qword_1403B9A48, rax
0x14013dab9  lea     rax, MSVDEV_PIT_INFO
0x14013dac0  mov     cs:qword_1403B9A80, rax
0x14013dac7  lea     rax, MSVDEV_PIT_WARNING
0x14013dace  mov     cs:qword_1403B9A78, rax
0x14013dad5  lea     rax, MSVDEV_PIT_ERROR
0x14013dadc  mov     cs:qword_1403B9A70, rax
0x14013dae3  lea     rax, MSVDEV_PIT_CRITICAL
0x14013daea  mov     cs:qword_1403B9A68, rax
0x14013daf1  lea     rax, MSVDEV_SUPER_IO_INFO
0x14013daf8  mov     cs:qword_1403B9AA0, rax
0x14013daff  lea     rax, MSVDEV_SUPER_IO_WARNING
0x14013db06  mov     cs:qword_1403B9A98, rax
0x14013db0d  lea     rax, MSVDEV_SUPER_IO_ERROR
0x14013db14  mov     cs:qword_1403B9A90, rax
0x14013db1b  lea     rax, MSVDEV_SUPER_IO_CRITICAL
0x14013db22  mov     cs:qword_1403B9A88, rax
0x14013db29  lea     rax, MSVDEV_SERIAL_CONTROLLER_INFO
0x14013db30  mov     cs:qword_1403B9AC0, rax
0x14013db37  lea     rax, MSVDEV_SERIAL_CONTROLLER_WARNING
0x14013db3e  mov     cs:qword_1403B9AB8, rax
0x14013db45  lea     rax, MSVDEV_SERIAL_CONTROLLER_ERROR
0x14013db4c  mov     cs:qword_1403B9AB0, rax
0x14013db53  lea     rax, MSVDEV_SERIAL_CONTROLLER_CRITICAL
0x14013db5a  mov     cs:qword_1403B9AA8, rax
0x14013db61  lea     r8, MSVDEV_MOUSE_INFO; "|)"
0x14013db68  lea     rax, MSVDEV_KEYBOARD_INFO
0x14013db6f  mov     cs:qword_1403B9B00, r8
0x14013db76  mov     cs:qword_1403B9AE0, rax
0x14013db7d  lea     rdx, MSVDEV_MOUSE_WARNING
0x14013db84  lea     rax, MSVDEV_KEYBOARD_WARNING
0x14013db8b  mov     cs:qword_1403B9AF8, rdx
0x14013db92  mov     cs:qword_1403B9AD8, rax
0x14013db99  lea     rcx, MSVDEV_MOUSE_ERROR
0x14013dba0  lea     rax, MSVDEV_KEYBOARD_ERROR
0x14013dba7  mov     cs:qword_1403B9AF0, rcx
0x14013dbae  mov     cs:qword_1403B9AD0, rax
0x14013dbb5  lea     rax, MSVDEV_KEYBOARD_CRITICAL
0x14013dbbc  mov     cs:qword_1403B9AC8, rax
0x14013dbc3  lea     rax, MSVDEV_MOUSE_CRITICAL
0x14013dbca  mov     cs:qword_1403B9AE8, rax
0x14013dbd1  mov     cs:qword_1403B9CE8, rax
0x14013dbd8  lea     rax, MSVDEV_FLOPPY_CONTROLLER_INFO
0x14013dbdf  mov     cs:qword_1403B9B20, rax
0x14013dbe6  lea     rax, MSVDEV_FLOPPY_CONTROLLER_WARNING
0x14013dbed  mov     cs:qword_1403B9B18, rax
0x14013dbf4  lea     rax, MSVDEV_FLOPPY_CONTROLLER_ERROR
0x14013dbfb  mov     cs:qword_1403B9B10, rax
0x14013dc02  lea     rax, MSVDEV_FLOPPY_CONTROLLER_CRITICAL
0x14013dc09  mov     cs:qword_1403B9B08, rax
0x14013dc10  lea     rax, MSVDEV_FLOPPY_DRIVE_INFO
0x14013dc17  mov     cs:qword_1403B9B40, rax
0x14013dc1e  lea     rax, MSVDEV_FLOPPY_DRIVE_WARNING
0x14013dc25  mov     cs:qword_1403B9B38, rax
0x14013dc2c  lea     rax, MSVDEV_FLOPPY_DRIVE_ERROR
0x14013dc33  mov     cs:qword_1403B9B30, rax
0x14013dc3a  lea     rax, MSVDEV_FLOPPY_DRIVE_CRITICAL
0x14013dc41  mov     cs:qword_1403B9B28, rax
0x14013dc48  lea     rax, MSVDEV_IDE_CONTROLLER_INFO
0x14013dc4f  mov     cs:qword_1403B9B60, rax
0x14013dc56  lea     rax, MSVDEV_IDE_CONTROLLER_WARNING
0x14013dc5d  mov     cs:qword_1403B9B58, rax
0x14013dc64  lea     rax, MSVDEV_IDE_CONTROLLER_ERROR
0x14013dc6b  mov     cs:qword_1403B9B50, rax
0x14013dc72  lea     rax, MSVDEV_IDE_CONTROLLER_CRITICAL
0x14013dc79  mov     cs:qword_1403B9B48, rax
0x14013dc80  lea     rax, MSVDEV_IDE_ATTACHMENT_INFO
0x14013dc87  mov     cs:qword_1403B9B80, rax
0x14013dc8e  lea     rax, MSVDEV_IDE_ATTACHMENT_WARNING
0x14013dc95  mov     cs:qword_1403B9B78, rax
0x14013dc9c  lea     rax, MSVDEV_IDE_ATTACHMENT_ERROR
0x14013dca3  mov     cs:qword_1403B9B70, rax
0x14013dcaa  lea     rax, MSVDEV_IDE_ATTACHMENT_CRITICAL
0x14013dcb1  mov     cs:qword_1403B9B68, rax
0x14013dcb8  lea     rax, MSVDEV_SCSI_CONTROLLER_INFO
0x14013dcbf  mov     cs:qword_1403B9BA0, rax
0x14013dcc6  lea     rax, MSVDEV_SCSI_CONTROLLER_WARNING
0x14013dccd  mov     cs:qword_1403B9B98, rax
0x14013dcd4  lea     rax, MSVDEV_SCSI_CONTROLLER_ERROR
0x14013dcdb  mov     cs:qword_1403B9B90, rax
0x14013dce2  lea     rax, MSVDEV_SCSI_CONTROLLER_CRITICAL
0x14013dce9  mov     cs:qword_1403B9B88, rax
0x14013dcf0  lea     rax, MSVDEV_SCSI_BUS_INFO
0x14013dcf7  mov     cs:qword_1403B9BC0, rax
0x14013dcfe  lea     rax, MSVDEV_SCSI_BUS_WARNING
0x14013dd05  mov     cs:qword_1403B9BB8, rax
0x14013dd0c  lea     rax, MSVDEV_SCSI_BUS_ERROR
0x14013dd13  mov     cs:qword_1403B9BB0, rax
0x14013dd1a  lea     rax, MSVDEV_SCSI_BUS_CRITICAL
0x14013dd21  mov     cs:qword_1403B9BA8, rax
0x14013dd28  lea     rax, MSVDEV_SCSI_ATTACHMENT_INFO
0x14013dd2f  mov     cs:qword_1403B9BE0, rax
0x14013dd36  lea     rax, MSVDEV_SCSI_ATTACHMENT_WARNING
0x14013dd3d  mov     cs:qword_1403B9BD8, rax
0x14013dd44  lea     rax, MSVDEV_SCSI_ATTACHMENT_ERROR
0x14013dd4b  mov     cs:qword_1403B9BD0, rax
0x14013dd52  lea     rax, MSVDEV_SCSI_ATTACHMENT_CRITICAL
0x14013dd59  mov     cs:qword_1403B9BC8, rax
0x14013dd60  lea     rax, MSVDEV_MEDIA_INFO
0x14013dd67  mov     cs:qword_1403B9C00, rax
0x14013dd6e  lea     rax, MSVDEV_MEDIA_WARNING
0x14013dd75  mov     cs:qword_1403B9D00, r8
0x14013dd7c  mov     cs:qword_1403B9CF8, rdx
0x14013dd83  mov     cs:qword_1403B9CF0, rcx
0x14013dd8a  mov     cs:qword_1403B9BF8, rax
0x14013dd91  lea     r8, MSVDEV_VIDEO_CONTROLLER_INFO
0x14013dd98  lea     rax, MSVDEV_MEDIA_ERROR
0x14013dd9f  mov     cs:qword_1403B9C60, r8
0x14013dda6  mov     cs:qword_1403B9BF0, rax
0x14013ddad  lea     rdx, MSVDEV_VIDEO_CONTROLLER_WARNING; ">+"
0x14013ddb4  lea     rax, MSVDEV_MEDIA_CRITICAL
0x14013ddbb  mov     cs:qword_1403B9C58, rdx
0x14013ddc2  mov     cs:qword_1403B9BE8, rax
0x14013ddc9  lea     rcx, MSVDEV_VIDEO_CONTROLLER_ERROR
0x14013ddd0  lea     rax, MSVDEV_HARD_DRIVE_INFO
0x14013ddd7  mov     cs:qword_1403B9C50, rcx
0x14013ddde  mov     cs:qword_1403B9C20, rax
0x14013dde5  lea     rax, MSVDEV_HARD_DRIVE_WARNING
0x14013ddec  mov     cs:qword_1403B9C18, rax
0x14013ddf3  lea     rax, MSVDEV_HARD_DRIVE_ERROR
0x14013ddfa  mov     cs:qword_1403B9C10, rax
0x14013de01  lea     rax, MSVDEV_HARD_DRIVE_CRITICAL
0x14013de08  mov     cs:qword_1403B9C08, rax
0x14013de0f  lea     rax, MSVDEV_ETHERNET_INFO
0x14013de16  mov     cs:qword_1403B9C40, rax
0x14013de1d  lea     rax, MSVDEV_ETHERNET_WARNING
0x14013de24  mov     cs:qword_1403B9C38, rax
0x14013de2b  lea     rax, MSVDEV_ETHERNET_ERROR
0x14013de32  mov     cs:qword_1403B9C30, rax
0x14013de39  lea     rax, MSVDEV_ETHERNET_CRITICAL
0x14013de40  mov     cs:qword_1403B9C28, rax
0x14013de47  lea     rax, MSVDEV_VIDEO_CONTROLLER_CRITICAL; "R+"
0x14013de4e  mov     cs:qword_1403B9C48, rax
0x14013de55  mov     cs:qword_1403B9CC8, rax
0x14013de5c  lea     rax, MSVDEV_REPOSITORY_INFO
0x14013de63  mov     cs:qword_1403B9C80, rax
0x14013de6a  lea     rax, MSVDEV_REPOSITORY_WARNING; "f+"
0x14013de71  mov     cs:qword_1403B9C78, rax
0x14013de78  lea     rax, MSVDEV_REPOSITORY_ERROR
0x14013de7f  mov     cs:qword_1403B9C70, rax
0x14013de86  lea     rax, MSVDEV_REPOSITORY_CRITICAL
0x14013de8d  mov     cs:qword_1403B9C68, rax
0x14013de94  lea     rax, MSVDEV_REMOTING_INFO
0x14013de9b  mov     cs:qword_1403B9CA0, rax
0x14013dea2  lea     rax, MSVDEV_REMOTING_WARNING
0x14013dea9  mov     cs:qword_1403B9C98, rax
0x14013deb0  lea     rax, MSVDEV_REMOTING_ERROR
0x14013deb7  mov     cs:qword_1403B9C90, rax
0x14013debe  lea     rax, MSVDEV_REMOTING_CRITICAL
0x14013dec5  mov     cs:qword_1403B9C88, rax
0x14013decc  lea     rax, MSVDEV_HID_INFO
0x14013ded3  mov     cs:qword_1403B9CC0, rax
0x14013deda  lea     rax, MSVDEV_HID_WARNING
0x14013dee1  mov     cs:qword_1403B9CB8, rax
0x14013dee8  lea     rax, MSVDEV_HID_ERROR
0x14013deef  mov     cs:qword_1403B9CB0, rax
0x14013def6  lea     rax, MSVDEV_HID_CRITICAL
  ... truncated ...
```
