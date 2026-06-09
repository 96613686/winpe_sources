# VmsTrcLogDeinitialize

- ea: `0x140089ed8`
- end: `0x140089fc2`
- name: `VmsTrcLogDeinitialize`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400a37d8`

## callees

- `0x140089ed8`
- `0x140237008`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogDelete` at `0x140089ef4`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140089f1e`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140089f48`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140089f72`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140089f9c`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140089ef4`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140089f1e`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140089f48`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140089f72`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140089f9c`

## pseudocode

```c
__int64 __fastcall VmsTrcLogDeinitialize(__int64 a1)
{
  if ( VmsStackTraceIfrLog )
  {
    imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
    VmsStackTraceIfrLog = 0;
  }
  if ( VmsVrssIfrLog )
  {
    imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
    VmsVrssIfrLog = 0;
  }
  if ( VmsIfrNicLog )
  {
    imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
    VmsIfrNicLog = 0;
  }
  if ( VmsIfrPortLog )
  {
    imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
    VmsIfrPortLog = 0;
  }
  if ( VmsIfrLog )
  {
    imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
    VmsIfrLog = 0;
  }
  return WppCleanupKm(a1);
}

```

## disassembly

```asm
0x140089ed8  push    rbx
0x140089eda  sub     rsp, 20h
0x140089ede  mov     rdx, cs:VmsStackTraceIfrLog
0x140089ee5  mov     rbx, rcx
0x140089ee8  test    rdx, rdx
0x140089eeb  jz      short loc_140089F0B
0x140089eed  mov     rcx, cs:WPP_GLOBAL_Control
0x140089ef4  call    cs:__imp_imp_WppRecorderLogDelete
0x140089efb  nop     dword ptr [rax+rax+00h]
0x140089f00  mov     cs:VmsStackTraceIfrLog, 0
0x140089f0b  mov     rdx, cs:VmsVrssIfrLog
0x140089f12  test    rdx, rdx
0x140089f15  jz      short loc_140089F35
0x140089f17  mov     rcx, cs:WPP_GLOBAL_Control
0x140089f1e  call    cs:__imp_imp_WppRecorderLogDelete
0x140089f25  nop     dword ptr [rax+rax+00h]
0x140089f2a  mov     cs:VmsVrssIfrLog, 0
0x140089f35  mov     rdx, cs:VmsIfrNicLog
0x140089f3c  test    rdx, rdx
0x140089f3f  jz      short loc_140089F5F
0x140089f41  mov     rcx, cs:WPP_GLOBAL_Control
0x140089f48  call    cs:__imp_imp_WppRecorderLogDelete
0x140089f4f  nop     dword ptr [rax+rax+00h]
0x140089f54  mov     cs:VmsIfrNicLog, 0
0x140089f5f  mov     rdx, cs:VmsIfrPortLog
0x140089f66  test    rdx, rdx
0x140089f69  jz      short loc_140089F89
0x140089f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140089f72  call    cs:__imp_imp_WppRecorderLogDelete
0x140089f79  nop     dword ptr [rax+rax+00h]
0x140089f7e  mov     cs:VmsIfrPortLog, 0
0x140089f89  mov     rdx, cs:VmsIfrLog
0x140089f90  test    rdx, rdx
0x140089f93  jz      short loc_140089FB3
0x140089f95  mov     rcx, cs:WPP_GLOBAL_Control
0x140089f9c  call    cs:__imp_imp_WppRecorderLogDelete
0x140089fa3  nop     dword ptr [rax+rax+00h]
0x140089fa8  mov     cs:VmsIfrLog, 0
0x140089fb3  mov     rcx, rbx
0x140089fb6  call    WppCleanupKm
0x140089fbb  add     rsp, 20h
0x140089fbf  pop     rbx
0x140089fc0  retn
```
