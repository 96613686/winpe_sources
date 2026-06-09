# PtSystemControl

- ea: `0x14000a300`
- end: `0x14000a4f4`
- name: `PtSystemControl`
- size: `500`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000173c`
- `0x1400018c0`
- `0x140001a80`
- `0x14000a300`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000a46d`
- `ntoskrnl!IofCallDriver` at `0x14000a46d`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000a3b8`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000a3b8`
- `ntoskrnl!IofCompleteRequest` at `0x14000a3da`
- `ntoskrnl!IofCompleteRequest` at `0x14000a482`
- `ntoskrnl!IofCompleteRequest` at `0x14000a3da`
- `ntoskrnl!IofCompleteRequest` at `0x14000a482`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000a49f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000a49f`
- `WMILIB!WmiSystemControl` at `0x14000a40d`
- `WMILIB!WmiSystemControl` at `0x14000a40d`

## pseudocode

```c
__int64 __fastcall PtSystemControl(PDEVICE_OBJECT DeviceObject, PIRP Irp, int a3)
{
  char *DeviceExtension; // rbp
  int v7; // eax
  unsigned int v8; // esi
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  int v12; // edx
  int v13; // r8d
  _SYSCTL_IRP_DISPOSITION IrpDisposition; // [rsp+70h] [rbp+8h] BYREF

  IrpDisposition = IrpProcessed;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      a3,
      12,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
  if ( DeviceObject->DeviceType != 56 )
  {
    DeviceExtension = (char *)DeviceObject->DeviceExtension;
    v7 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 24), PtSystemControl, File, 1u, 0x20u);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v8 = WmiSystemControl((PWMILIB_CONTEXT)(DeviceExtension + 96), DeviceObject, Irp, &IrpDisposition);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          v13,
          15,
          (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
      if ( IrpDisposition )
      {
        if ( IrpDisposition == IrpNotCompleted )
        {
          IofCompleteRequest(Irp, 0);
        }
        else
        {
          ++Irp->CurrentLocation;
          ++Irp->Tail.Overlay.CurrentStackLocation;
          v8 = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 1), Irp);
        }
      }
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 24), PtSystemControl, 0x20u);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v8;
      v11 = 16;
    }
    else
    {
      Irp->IoStatus.Status = v7;
      Irp->IoStatus.Information = 0;
      IofCompleteRequest(Irp, 0);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v8;
      v11 = 14;
    }
    WPP_RECORDER_SF_sqd(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      v10,
      v11,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
    return v8;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      a3,
      13,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
  return 3221225488LL;
}

```

## disassembly

```asm
0x14000a300  mov     rax, rsp
0x14000a303  mov     [rax+10h], rbx
0x14000a307  mov     [rax+18h], rbp
0x14000a30b  push    rsi
0x14000a30c  push    rdi
0x14000a30d  push    r12
0x14000a30f  push    r14
0x14000a311  push    r15
0x14000a313  sub     rsp, 40h
0x14000a317  mov     rbx, rdx
0x14000a31a  mov     dword ptr [rax+8], 0
0x14000a321  mov     rdi, rcx
0x14000a324  lea     r12, WPP_RECORDER_INITIALIZED
0x14000a32b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000a332  lea     r15, WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids
0x14000a339  jz      short loc_14000A355
0x14000a33b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a342  mov     r9d, 0Ch
0x14000a348  mov     [rax-48h], r15
0x14000a34c  mov     rcx, [rcx+40h]
0x14000a350  call    WPP_RECORDER_SF_s
0x14000a355  cmp     dword ptr [rdi+48h], 38h ; '8'
0x14000a359  jnz     short loc_14000A394
0x14000a35b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000a362  mov     ebx, 0C0000010h
0x14000a367  jz      short loc_14000A38D
0x14000a369  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a370  mov     r9d, 0Dh
0x14000a376  mov     [rsp+68h+var_30], ebx
0x14000a37a  mov     [rsp+68h+var_38], rdi
0x14000a37f  mov     qword ptr [rsp+68h+RemlockSize], r15
0x14000a384  mov     rcx, [rcx+40h]
0x14000a388  call    WPP_RECORDER_SF_sqd
0x14000a38d  mov     eax, ebx
0x14000a38f  jmp     loc_14000A4DA
0x14000a394  mov     rbp, [rdi+40h]
0x14000a398  lea     r8, File; File
0x14000a39f  mov     r9d, 1; Line
0x14000a3a5  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x14000a3ad  lea     rdx, PtSystemControl; Tag
0x14000a3b4  lea     rcx, [rbp+18h]; RemoveLock
0x14000a3b8  call    cs:__imp_IoAcquireRemoveLockEx
0x14000a3bf  nop     dword ptr [rax+rax+00h]
0x14000a3c4  mov     esi, eax
0x14000a3c6  test    eax, eax
0x14000a3c8  jns     short loc_14000A3FE
0x14000a3ca  xor     edx, edx; PriorityBoost
0x14000a3cc  mov     [rbx+30h], eax
0x14000a3cf  mov     rcx, rbx; Irp
0x14000a3d2  mov     qword ptr [rbx+38h], 0
0x14000a3da  call    cs:__imp_IofCompleteRequest
0x14000a3e1  nop     dword ptr [rax+rax+00h]
0x14000a3e6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000a3ed  jz      loc_14000A4D8
0x14000a3f3  mov     r9d, 0Eh
0x14000a3f9  jmp     loc_14000A4BA
0x14000a3fe  lea     rcx, [rbp+60h]; WmiLibInfo
0x14000a402  mov     r8, rbx; Irp
0x14000a405  lea     r9, [rsp+68h+IrpDisposition]; IrpDisposition
0x14000a40a  mov     rdx, rdi; DeviceObject
0x14000a40d  call    cs:__imp_WmiSystemControl
0x14000a414  nop     dword ptr [rax+rax+00h]
0x14000a419  mov     esi, eax
0x14000a41b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000a422  jz      short loc_14000A44B
0x14000a424  mov     ecx, [rsp+68h+IrpDisposition]
0x14000a428  mov     r9d, 0Fh
0x14000a42e  mov     [rsp+68h+var_30], eax
0x14000a432  mov     dword ptr [rsp+68h+var_38], ecx
0x14000a436  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a43d  mov     qword ptr [rsp+68h+RemlockSize], r15
0x14000a442  mov     rcx, [rcx+40h]
0x14000a446  call    WPP_RECORDER_SF_sDd
0x14000a44b  mov     edx, [rsp+68h+IrpDisposition]
0x14000a44f  test    edx, edx
0x14000a451  jz      short loc_14000A48E
0x14000a453  sub     edx, 1
0x14000a456  jz      short loc_14000A47D
0x14000a458  inc     byte ptr [rbx+43h]
0x14000a45b  sub     edx, 1
0x14000a45e  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14000a466  mov     rdx, rbx; Irp
0x14000a469  mov     rcx, [rbp+8]; DeviceObject
0x14000a46d  call    cs:__imp_IofCallDriver
0x14000a474  nop     dword ptr [rax+rax+00h]
0x14000a479  mov     esi, eax
0x14000a47b  jmp     short loc_14000A48E
0x14000a47d  xor     edx, edx; PriorityBoost
0x14000a47f  mov     rcx, rbx; Irp
0x14000a482  call    cs:__imp_IofCompleteRequest
0x14000a489  nop     dword ptr [rax+rax+00h]
0x14000a48e  mov     r8d, 20h ; ' '; RemlockSize
0x14000a494  lea     rdx, PtSystemControl; Tag
0x14000a49b  lea     rcx, [rbp+18h]; RemoveLock
0x14000a49f  call    cs:__imp_IoReleaseRemoveLockEx
0x14000a4a6  nop     dword ptr [rax+rax+00h]
0x14000a4ab  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000a4b2  jz      short loc_14000A4D8
0x14000a4b4  mov     r9d, 10h
0x14000a4ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4c1  mov     [rsp+68h+var_30], esi
0x14000a4c5  mov     [rsp+68h+var_38], rdi
0x14000a4ca  mov     qword ptr [rsp+68h+RemlockSize], r15
0x14000a4cf  mov     rcx, [rcx+40h]
0x14000a4d3  call    WPP_RECORDER_SF_sqd
0x14000a4d8  mov     eax, esi
0x14000a4da  lea     r11, [rsp+68h+var_28]
0x14000a4df  mov     rbx, [r11+38h]
0x14000a4e3  mov     rbp, [r11+40h]
0x14000a4e7  mov     rsp, r11
0x14000a4ea  pop     r15
0x14000a4ec  pop     r14
0x14000a4ee  pop     r12
0x14000a4f0  pop     rdi
0x14000a4f1  pop     rsi
0x14000a4f2  retn
```
