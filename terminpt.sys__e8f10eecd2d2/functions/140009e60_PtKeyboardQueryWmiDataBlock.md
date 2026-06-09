# PtKeyboardQueryWmiDataBlock

- ea: `0x140009e60`
- end: `0x140009fa0`
- name: `PtKeyboardQueryWmiDataBlock`
- size: `320`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000173c`
- `0x140001a80`
- `0x140009e60`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x140009f7a`
- `WMILIB!WmiCompleteRequest` at `0x140009f7a`

## pseudocode

```c
NTSTATUS __fastcall PtKeyboardQueryWmiDataBlock(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        int a3,
        __int64 a4,
        int a5,
        _DWORD *a6,
        unsigned int a7,
        __int64 a8)
{
  NTSTATUS v11; // ebx
  int v12; // r9d

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      a3,
      21,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
  if ( a3 )
  {
    v11 = -1073741163;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return WmiCompleteRequest(DeviceObject, Irp, v11, 0x14u, 0);
    v12 = 23;
    goto LABEL_9;
  }
  if ( a7 < 0x14 )
  {
    v11 = -1073741789;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return WmiCompleteRequest(DeviceObject, Irp, v11, 0x14u, 0);
    v12 = 22;
LABEL_9:
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      a3,
      v12,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
    goto LABEL_11;
  }
  *(_DWORD *)a8 = 0;
  *(_QWORD *)(a8 + 4) = 1;
  *(_DWORD *)(a8 + 12) = 12;
  *(_DWORD *)(a8 + 16) = 3;
  v11 = 0;
  *a6 = 20;
LABEL_11:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      a3,
      24,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
  return WmiCompleteRequest(DeviceObject, Irp, v11, 0x14u, 0);
}

```

## disassembly

```asm
0x140009e60  mov     [rsp+arg_10], rbx
0x140009e65  mov     [rsp+arg_18], rbp
0x140009e6a  push    rsi
0x140009e6b  push    rdi
0x140009e6c  push    r12
0x140009e6e  push    r13
0x140009e70  push    r14
0x140009e72  sub     rsp, 40h
0x140009e76  mov     rbx, [rsp+68h+arg_38]
0x140009e7e  mov     edi, r8d
0x140009e81  mov     r14, [rsp+68h+arg_28]
0x140009e89  mov     rbp, rdx
0x140009e8c  mov     rsi, rcx
0x140009e8f  lea     r12, WPP_RECORDER_INITIALIZED
0x140009e96  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140009e9d  lea     r13, WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids
0x140009ea4  jz      short loc_140009EC1
0x140009ea6  mov     rcx, cs:WPP_GLOBAL_Control
0x140009ead  mov     r9d, 15h
0x140009eb3  mov     qword ptr [rsp+68h+PriorityBoost], r13
0x140009eb8  mov     rcx, [rcx+40h]
0x140009ebc  call    WPP_RECORDER_SF_s
0x140009ec1  test    edi, edi
0x140009ec3  jz      short loc_140009EDF
0x140009ec5  mov     ebx, 0C0000295h
0x140009eca  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140009ed1  jz      loc_140009F66
0x140009ed7  mov     r9d, 17h
0x140009edd  jmp     short loc_140009EFD
0x140009edf  cmp     [rsp+68h+arg_30], 14h
0x140009ee7  jnb     short loc_140009F14
0x140009ee9  mov     ebx, 0C0000023h
0x140009eee  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140009ef5  jz      short loc_140009F66
0x140009ef7  mov     r9d, 16h
0x140009efd  mov     rcx, cs:WPP_GLOBAL_Control
0x140009f04  mov     qword ptr [rsp+68h+PriorityBoost], r13
0x140009f09  mov     rcx, [rcx+40h]
0x140009f0d  call    WPP_RECORDER_SF_s
0x140009f12  jmp     short loc_140009F39
0x140009f14  mov     dword ptr [rbx], 0
0x140009f1a  mov     qword ptr [rbx+4], 1
0x140009f22  mov     dword ptr [rbx+0Ch], 0Ch
0x140009f29  mov     dword ptr [rbx+10h], 3
0x140009f30  xor     ebx, ebx
0x140009f32  mov     dword ptr [r14], 14h
0x140009f39  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140009f40  jz      short loc_140009F66
0x140009f42  mov     rcx, cs:WPP_GLOBAL_Control
0x140009f49  mov     r9d, 18h
0x140009f4f  mov     [rsp+68h+var_30], ebx
0x140009f53  mov     [rsp+68h+var_38], rsi
0x140009f58  mov     qword ptr [rsp+68h+PriorityBoost], r13
0x140009f5d  mov     rcx, [rcx+40h]
0x140009f61  call    WPP_RECORDER_SF_sqd
0x140009f66  mov     r9d, 14h; BufferUsed
0x140009f6c  mov     [rsp+68h+PriorityBoost], 0; PriorityBoost
0x140009f71  mov     r8d, ebx; Status
0x140009f74  mov     rdx, rbp; Irp
0x140009f77  mov     rcx, rsi; DeviceObject
0x140009f7a  call    cs:__imp_WmiCompleteRequest
0x140009f81  nop     dword ptr [rax+rax+00h]
0x140009f86  lea     r11, [rsp+68h+var_28]
0x140009f8b  mov     rbx, [r11+40h]
0x140009f8f  mov     rbp, [r11+48h]
0x140009f93  mov     rsp, r11
0x140009f96  pop     r14
0x140009f98  pop     r13
0x140009f9a  pop     r12
0x140009f9c  pop     rdi
0x140009f9d  pop     rsi
0x140009f9e  retn
```
