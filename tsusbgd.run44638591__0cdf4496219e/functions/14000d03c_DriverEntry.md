# DriverEntry

- ea: `0x14000d03c`
- end: `0x14000d189`
- name: `DriverEntry`
- size: `333`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140004244`

## callees

- `0x140001ac0`
- `0x140003934`
- `0x140006370`
- `0x14000c430`
- `0x14000c4c4`
- `0x14000d03c`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v4; // eax
  NTSTATUS v5; // ebx
  __int128 v7; // [rsp+40h] [rbp-28h] BYREF
  __int128 v8; // [rsp+50h] [rbp-18h]
  __int64 v9; // [rsp+80h] [rbp+18h] BYREF

  v9 = 0;
  v7 = 0;
  v8 = 0;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_d0a1ae740783355ab6709b133c59cb89_Traceguids);
  *(_QWORD *)&v7 = 32;
  *((_QWORD *)&v7 + 1) = GdEvtDeviceAdd;
  *(_QWORD *)&v8 = GdEvtDriverUnload;
  *((_QWORD *)&v8 + 1) = 0;
  v4 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _DRIVER_OBJECT *, PUNICODE_STRING, _QWORD, __int128 *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[58].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         DriverObject,
         RegistryPath,
         0,
         &v7,
         &v9);
  v5 = v4;
  if ( v4 < 0 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_d0a1ae740783355ab6709b133c59cb89_Traceguids, (unsigned int)v4);
  return v5;
}

```

## disassembly

```asm
0x14000d03c  mov     rax, rsp
0x14000d03f  mov     [rax+8], rbx
0x14000d043  mov     [rax+10h], rbp
0x14000d047  push    rdi
0x14000d048  sub     rsp, 60h
0x14000d04c  xorps   xmm0, xmm0
0x14000d04f  mov     qword ptr [rax+18h], 0
0x14000d057  movups  xmmword ptr [rax-28h], xmm0
0x14000d05b  mov     rbx, rdx
0x14000d05e  mov     rdi, rcx
0x14000d061  movups  xmmword ptr [rax-18h], xmm0
0x14000d065  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x14000d06c  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14000d077  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14000d07e  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14000d089  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14000d094  mov     cs:WPP_MAIN_CB.Timer, 1
0x14000d09f  call    WppLoadTracingSupport
0x14000d0a4  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14000d0af  call    WppInitKm
0x14000d0b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d0bb  lea     rbp, WPP_GLOBAL_Control
0x14000d0c2  cmp     rcx, rbp
0x14000d0c5  jz      short loc_14000D0E2
0x14000d0c7  cmp     byte ptr [rcx+29h], 5
0x14000d0cb  jb      short loc_14000D0E2
0x14000d0cd  mov     rcx, [rcx+18h]
0x14000d0d1  lea     r8, WPP_d0a1ae740783355ab6709b133c59cb89_Traceguids
0x14000d0d8  mov     edx, 0Ah
0x14000d0dd  call    WPP_SF_
0x14000d0e2  lea     rax, GdEvtDeviceAdd
0x14000d0e9  mov     [rsp+68h+var_28], 20h ; ' '
0x14000d0f2  mov     [rsp+68h+var_20], rax
0x14000d0f7  lea     rcx, [rsp+68h+arg_10]
0x14000d0ff  mov     [rsp+68h+var_40], rcx
0x14000d104  lea     rax, GdEvtDriverUnload
0x14000d10b  mov     [rsp+68h+var_18], rax
0x14000d110  lea     rcx, [rsp+68h+var_28]
0x14000d115  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000d11c  xor     r9d, r9d
0x14000d11f  mov     [rsp+68h+var_10], 0
0x14000d128  mov     r8, rbx
0x14000d12b  mov     [rsp+68h+var_48], rcx
0x14000d130  mov     rdx, rdi
0x14000d133  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000d13a  mov     rax, [rax+3A0h]
0x14000d141  call    _guard_dispatch_icall
0x14000d146  mov     ebx, eax
0x14000d148  test    eax, eax
0x14000d14a  jns     short loc_14000D176
0x14000d14c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d153  cmp     rcx, rbp
0x14000d156  jz      short loc_14000D176
0x14000d158  cmp     byte ptr [rcx+29h], 5
0x14000d15c  jb      short loc_14000D176
0x14000d15e  mov     rcx, [rcx+18h]
0x14000d162  lea     r8, WPP_d0a1ae740783355ab6709b133c59cb89_Traceguids
0x14000d169  mov     edx, 0Bh
0x14000d16e  mov     r9d, eax
0x14000d171  call    WPP_SF_d
0x14000d176  mov     rbp, [rsp+68h+arg_8]
0x14000d17b  mov     eax, ebx
0x14000d17d  mov     rbx, [rsp+68h+arg_0]
0x14000d182  add     rsp, 60h
0x14000d186  pop     rdi
0x14000d187  retn
```
