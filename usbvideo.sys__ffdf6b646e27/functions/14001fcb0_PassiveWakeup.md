# PassiveWakeup

- ea: `0x14001fcb0`
- end: `0x14001fdde`
- name: `PassiveWakeup`
- size: `302`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140005308`
- `0x1400199e8`
- `0x14001b15c`
- `0x14001d20c`
- `0x14001d244`
- `0x14001d4e0`
- `0x14001fcb0`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001fda5`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001fda5`
- `ntoskrnl!IoFreeWorkItem` at `0x14001fce2`
- `ntoskrnl!IoFreeWorkItem` at `0x14001fce2`
- `ntoskrnl!IoUninitializeWorkItem` at `0x14001fccd`
- `ntoskrnl!IoUninitializeWorkItem` at `0x14001fccd`

## pseudocode

```c
void __fastcall PassiveWakeup(PDEVICE_OBJECT DeviceObject, struct _IO_REMOVE_LOCK *Context)
{
  int IsEnabledNoReportingNoInline; // eax
  struct _IO_WORKITEM *Blink; // rcx
  int v5; // edi
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8

  IsEnabledNoReportingNoInline = Feature_Servicing_UvcPerfIrpCache__private_IsEnabledNoReportingNoInline(DeviceObject);
  Blink = (struct _IO_WORKITEM *)Context[7].Common.RemoveEvent.Header.WaitListHead.Blink;
  if ( IsEnabledNoReportingNoInline )
  {
    IoUninitializeWorkItem(Blink);
    Context[11].Common.Reserved[0] = 0;
  }
  else
  {
    IoFreeWorkItem(Blink);
    Context[7].Common.RemoveEvent.Header.WaitListHead.Blink = 0;
  }
  LoadPowerLineFrequency((__int64)Context);
  if ( LODWORD(Context[44].Common.RemoveEvent.Header.WaitListHead.Flink) )
  {
    v5 = 0;
    while ( 1 )
    {
      while ( v5 == 5 )
      {
        if ( LODWORD(Context[45].Common.RemoveEvent.Header.WaitListHead.Blink) != 1 )
          LoadUVCCacheControl((__int64)Context);
        v5 = 6;
      }
      if ( v5 == 9 )
        break;
      LoadUVCCacheControl((__int64)Context);
      if ( ++v5 >= 10 )
        goto LABEL_15;
    }
    if ( LODWORD(Context[46].Common.RemoveEvent.Header.WaitListHead.Blink) != 1 )
      LoadUVCCacheControl((__int64)Context);
  }
LABEL_15:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 160, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, Context);
  FilterCreateQueue_CompleteQueue((struct _IO_CSQ *)Context, 0);
  IoReleaseRemoveLockEx(Context + 24, IdleDetectWorkItem, 0x20u);
  if ( (unsigned int)Feature_Servicing_UvcPerfIrpCache__private_IsEnabledNoReportingNoInline(v6)
    && ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
  {
    McTemplateK0p_EtwWriteTransfer(v7, USBVideo_PowerIrp_PassiveWakeupCompleted, v8, 0);
  }
}

```

## disassembly

```asm
0x14001fcb0  mov     [rsp+arg_0], rbx
0x14001fcb5  push    rdi
0x14001fcb6  sub     rsp, 20h
0x14001fcba  mov     rbx, rdx
0x14001fcbd  call    Feature_Servicing_UvcPerfIrpCache__private_IsEnabledNoReportingNoInline
0x14001fcc2  mov     rcx, [rbx+0F8h]; IoWorkItem
0x14001fcc9  test    eax, eax
0x14001fccb  jz      short loc_14001FCE2
0x14001fccd  call    cs:__imp_IoUninitializeWorkItem
0x14001fcd4  nop     dword ptr [rax+rax+00h]
0x14001fcd9  mov     byte ptr [rbx+161h], 0
0x14001fce0  jmp     short loc_14001FCF9
0x14001fce2  call    cs:__imp_IoFreeWorkItem
0x14001fce9  nop     dword ptr [rax+rax+00h]
0x14001fcee  mov     qword ptr [rbx+0F8h], 0
0x14001fcf9  mov     rcx, rbx; __int64
0x14001fcfc  call    LoadPowerLineFrequency
0x14001fd01  cmp     dword ptr [rbx+590h], 0
0x14001fd08  jz      short loc_14001FD56
0x14001fd0a  xor     edi, edi
0x14001fd0c  cmp     edi, 5
0x14001fd0f  jnz     short loc_14001FD28
0x14001fd11  cmp     dword ptr [rbx+5B8h], 1
0x14001fd18  jz      short loc_14001FD24
0x14001fd1a  mov     edx, edi
0x14001fd1c  mov     rcx, rbx; __int64
0x14001fd1f  call    LoadUVCCacheControl
0x14001fd24  inc     edi
0x14001fd26  jmp     short loc_14001FD0C
0x14001fd28  cmp     edi, 9
0x14001fd2b  jz      short loc_14001FD40
0x14001fd2d  mov     edx, edi
0x14001fd2f  mov     rcx, rbx; __int64
0x14001fd32  call    LoadUVCCacheControl
0x14001fd37  inc     edi
0x14001fd39  cmp     edi, 0Ah
0x14001fd3c  jl      short loc_14001FD0C
0x14001fd3e  jmp     short loc_14001FD56
0x14001fd40  cmp     dword ptr [rbx+5D8h], 1
0x14001fd47  jz      short loc_14001FD56
0x14001fd49  mov     edx, 9
0x14001fd4e  mov     rcx, rbx; __int64
0x14001fd51  call    LoadUVCCacheControl
0x14001fd56  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fd5d  lea     rax, WPP_GLOBAL_Control
0x14001fd64  cmp     rcx, rax
0x14001fd67  jz      short loc_14001FD87
0x14001fd69  cmp     byte ptr [rcx+29h], 4
0x14001fd6d  jb      short loc_14001FD87
0x14001fd6f  mov     rcx, [rcx+18h]
0x14001fd73  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x14001fd7a  mov     edx, 0A0h
0x14001fd7f  mov     r9, rbx
0x14001fd82  call    WPP_SF_q
0x14001fd87  xor     edx, edx
0x14001fd89  mov     rcx, rbx
0x14001fd8c  call    FilterCreateQueue_CompleteQueue
0x14001fd91  lea     rcx, [rbx+300h]; RemoveLock
0x14001fd98  mov     r8d, 20h ; ' '; RemlockSize
0x14001fd9e  lea     rdx, IdleDetectWorkItem; Tag
0x14001fda5  call    cs:__imp_IoReleaseRemoveLockEx
0x14001fdac  nop     dword ptr [rax+rax+00h]
0x14001fdb1  call    Feature_Servicing_UvcPerfIrpCache__private_IsEnabledNoReportingNoInline
0x14001fdb6  test    eax, eax
0x14001fdb8  jz      short loc_14001FDD2
0x14001fdba  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x14001fdc1  jz      short loc_14001FDD2
0x14001fdc3  xor     r9d, r9d
0x14001fdc6  lea     rdx, USBVideo_PowerIrp_PassiveWakeupCompleted
0x14001fdcd  call    McTemplateK0p_EtwWriteTransfer
0x14001fdd2  mov     rbx, [rsp+28h+arg_0]
0x14001fdd7  add     rsp, 20h
0x14001fddb  pop     rdi
0x14001fddc  retn
```
