# DriverEntry

- ea: `0x14001303c`
- end: `0x140013281`
- name: `DriverEntry`
- size: `581`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14000a464`

## callees

- `0x140004f18`
- `0x140004f48`
- `0x1400098b8`
- `0x1400098f8`
- `0x14000aa30`
- `0x14001271c`
- `0x140012904`
- `0x140012988`
- `0x140012a1c`
- `0x14001303c`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v4; // eax
  NTSTATUS v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int128 v10; // [rsp+40h] [rbp-29h] BYREF
  __int128 v11; // [rsp+50h] [rbp-19h]
  __int128 v12; // [rsp+60h] [rbp-9h] BYREF
  __int128 v13; // [rsp+70h] [rbp+7h]
  __int128 v14; // [rsp+80h] [rbp+17h]
  __int64 *v15; // [rsp+90h] [rbp+27h]
  unsigned __int64 v16; // [rsp+E0h] [rbp+77h] BYREF

  WPP_MAIN_CB.NextDevice = 0;
  v15 = 0;
  v16 = 0;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_CtlGuid;
  v10 = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_260dd1c9628d3ac9f90233475d78e5d7_Traceguids);
  McGenEventRegister_EtwRegister();
  *(_QWORD *)&v10 = 32;
  *(_QWORD *)&v13 = 0;
  *((_QWORD *)&v11 + 1) = 0;
  *((_QWORD *)&v10 + 1) = FdEvtDeviceAdd;
  *(_QWORD *)&v11 = FdEvtDriverUnload;
  v15 = off_14000F018;
  v12 = 0;
  LODWORD(v12) = 56;
  v14 = 0;
  *((_QWORD *)&v13 + 1) = 0x400000002LL;
  v4 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _DRIVER_OBJECT *, PUNICODE_STRING, __int128 *, __int128 *, unsigned __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[58].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         DriverObject,
         RegistryPath,
         &v12,
         &v10,
         &v16);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_13;
    v7 = 11;
    goto LABEL_12;
  }
  v8 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, unsigned __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         v16,
         off_14000F018);
  *(_QWORD *)&v13 = 0;
  *((_QWORD *)&v13 + 1) = 0x100000001LL;
  v14 = v16;
  v12 = 0;
  v15 = 0;
  LODWORD(v12) = 56;
  v4 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int128 *, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[156].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         &v12,
         v8 + 8);
  v5 = v4;
  if ( v4 >= 0 )
  {
    *(_BYTE *)(v8 + 16) = (unsigned int)IsUsbRedirectionEnabled() != 2;
    return v5;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v7 = 12;
LABEL_12:
    WPP_SF_d(v6->AttachedDevice, v7, WPP_260dd1c9628d3ac9f90233475d78e5d7_Traceguids, (unsigned int)v4);
  }
LABEL_13:
  McGenEventUnregister_EtwUnregister();
  WppCleanupKm();
  return v5;
}

```

## disassembly

```asm
0x14001303c  push    rbp
0x14001303e  push    rbx
0x14001303f  push    rdi
0x140013040  push    r12
0x140013042  lea     rbp, [rsp-3Fh]
0x140013047  sub     rsp, 0A8h
0x14001304e  xor     eax, eax
0x140013050  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14001305b  xorps   xmm1, xmm1
0x14001305e  mov     [rbp+57h+var_30], rax
0x140013062  xorps   xmm0, xmm0
0x140013065  mov     [rbp+57h+arg_10], rax
0x140013069  mov     qword ptr cs:WPP_MAIN_CB.Type, rax
0x140013070  mov     rbx, rdx
0x140013073  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x14001307a  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x140013085  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14001308c  mov     rdi, rcx
0x14001308f  movups  [rbp+57h+var_80], xmm0
0x140013093  mov     cs:WPP_MAIN_CB.Timer, 1
0x14001309e  movups  [rbp+57h+var_70], xmm0
0x1400130a2  movups  [rbp+57h+var_60], xmm1
0x1400130a6  movups  [rbp+57h+var_50], xmm1
0x1400130aa  movups  [rbp+57h+var_40], xmm1
0x1400130ae  call    WppLoadTracingSupport
0x1400130b3  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400130be  call    WppInitKm
0x1400130c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400130ca  lea     r12, WPP_GLOBAL_Control
0x1400130d1  cmp     rcx, r12
0x1400130d4  jz      short loc_1400130F1
0x1400130d6  cmp     byte ptr [rcx+29h], 5
0x1400130da  jb      short loc_1400130F1
0x1400130dc  mov     rcx, [rcx+18h]
0x1400130e0  lea     r8, WPP_260dd1c9628d3ac9f90233475d78e5d7_Traceguids
0x1400130e7  mov     edx, 0Ah
0x1400130ec  call    WPP_SF_
0x1400130f1  call    McGenEventRegister_EtwRegister
0x1400130f6  xorps   xmm0, xmm0
0x1400130f9  mov     qword ptr [rbp+57h+var_80], 20h ; ' '
0x140013101  movups  [rbp+57h+var_50], xmm0
0x140013105  lea     rax, FdEvtDeviceAdd
0x14001310c  mov     qword ptr [rbp+57h+var_70+8], 0
0x140013114  mov     qword ptr [rbp+57h+var_80+8], rax
0x140013118  lea     rcx, [rbp+57h+arg_10]
0x14001311c  mov     [rsp+0C0h+var_98], rcx
0x140013121  lea     rax, FdEvtDriverUnload
0x140013128  mov     qword ptr [rbp+57h+var_70], rax
0x14001312c  lea     rcx, [rbp+57h+var_80]
0x140013130  mov     rax, cs:off_14000F018
0x140013137  lea     r9, [rbp+57h+var_60]
0x14001313b  mov     [rbp+57h+var_30], rax
0x14001313f  mov     r8, rbx
0x140013142  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140013149  mov     rdx, rdi
0x14001314c  movups  [rbp+57h+var_60], xmm0
0x140013150  mov     dword ptr [rbp+57h+var_60], 38h ; '8'
0x140013157  movups  [rbp+57h+var_40], xmm0
0x14001315b  mov     dword ptr [rbp+57h+var_50+8], 2
0x140013162  mov     dword ptr [rbp+57h+var_50+0Ch], 4
0x140013169  mov     rax, [rax+3A0h]
0x140013170  mov     [rsp+0C0h+var_A0], rcx
0x140013175  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14001317c  call    _guard_dispatch_icall
0x140013181  mov     ebx, eax
0x140013183  test    eax, eax
0x140013185  jns     short loc_1400131AB
0x140013187  mov     rcx, cs:WPP_GLOBAL_Control
0x14001318e  cmp     rcx, r12
0x140013191  jz      loc_140013257
0x140013197  cmp     byte ptr [rcx+29h], 2
0x14001319b  jb      loc_140013257
0x1400131a1  mov     edx, 0Bh
0x1400131a6  jmp     loc_140013244
0x1400131ab  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400131b2  mov     r8, cs:off_14000F018
0x1400131b9  mov     rdx, [rbp+57h+arg_10]
0x1400131bd  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400131c4  mov     rax, [rax+650h]
0x1400131cb  call    _guard_dispatch_icall
0x1400131d0  mov     rcx, [rbp+57h+arg_10]
0x1400131d4  lea     rdx, [rbp+57h+var_60]
0x1400131d8  xorps   xmm0, xmm0
0x1400131db  mov     rdi, rax
0x1400131de  movups  [rbp+57h+var_50], xmm0
0x1400131e2  xor     eax, eax
0x1400131e4  mov     dword ptr [rbp+57h+var_50+8], 1
0x1400131eb  movups  [rbp+57h+var_40], xmm0
0x1400131ef  mov     qword ptr [rbp+57h+var_40], rcx
0x1400131f3  lea     r8, [rdi+8]
0x1400131f7  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x1400131fe  movups  [rbp+57h+var_60], xmm0
0x140013202  mov     [rbp+57h+var_30], rax
0x140013206  mov     dword ptr [rbp+57h+var_60], 38h ; '8'
0x14001320d  mov     dword ptr [rbp+57h+var_50+0Ch], 1
0x140013214  mov     rax, [rcx+9C0h]
0x14001321b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140013222  call    _guard_dispatch_icall
0x140013227  mov     ebx, eax
0x140013229  test    eax, eax
0x14001322b  jns     short loc_140013263
0x14001322d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013234  cmp     rcx, r12
0x140013237  jz      short loc_140013257
0x140013239  cmp     byte ptr [rcx+29h], 2
0x14001323d  jb      short loc_140013257
0x14001323f  mov     edx, 0Ch
0x140013244  mov     rcx, [rcx+18h]
0x140013248  lea     r8, WPP_260dd1c9628d3ac9f90233475d78e5d7_Traceguids
0x14001324f  mov     r9d, eax
0x140013252  call    WPP_SF_d
0x140013257  call    McGenEventUnregister_EtwUnregister
0x14001325c  call    WppCleanupKm
0x140013261  jmp     short loc_140013271
0x140013263  call    IsUsbRedirectionEnabled
0x140013268  cmp     eax, 2
0x14001326b  setnz   al
0x14001326e  mov     [rdi+10h], al
0x140013271  mov     eax, ebx
0x140013273  add     rsp, 0A8h
0x14001327a  pop     r12
0x14001327c  pop     rdi
0x14001327d  pop     rbx
0x14001327e  pop     rbp
0x14001327f  retn
```
