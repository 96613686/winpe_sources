# PtMouseQueryWmiDataBlock

- ea: `0x140009fb0`
- end: `0x14000a0ea`
- name: `PtMouseQueryWmiDataBlock`
- size: `314`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000173c`
- `0x140001a80`
- `0x140009fb0`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x14000a0c4`
- `WMILIB!WmiCompleteRequest` at `0x14000a0c4`

## pseudocode

```c
NTSTATUS __fastcall PtMouseQueryWmiDataBlock(
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
      25,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
  if ( a3 )
  {
    v11 = -1073741163;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return WmiCompleteRequest(DeviceObject, Irp, v11, 0x14u, 0);
    v12 = 27;
    goto LABEL_9;
  }
  if ( a7 < 0x14 )
  {
    v11 = -1073741789;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return WmiCompleteRequest(DeviceObject, Irp, v11, 0x14u, 0);
    v12 = 26;
LABEL_9:
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      a3,
      v12,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
    goto LABEL_11;
  }
  *(_QWORD *)a8 = 0;
  *(_DWORD *)(a8 + 8) = 0;
  *(_QWORD *)(a8 + 12) = 2;
  v11 = 0;
  *a6 = 20;
LABEL_11:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      a3,
      28,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
  return WmiCompleteRequest(DeviceObject, Irp, v11, 0x14u, 0);
}

```

## disassembly

```asm
0x140009fb0  mov     [rsp+arg_10], rbx
0x140009fb5  mov     [rsp+arg_18], rbp
0x140009fba  push    rsi
0x140009fbb  push    rdi
0x140009fbc  push    r12
0x140009fbe  push    r13
0x140009fc0  push    r14
0x140009fc2  sub     rsp, 40h
0x140009fc6  mov     rbx, [rsp+68h+arg_38]
0x140009fce  mov     edi, r8d
0x140009fd1  mov     r14, [rsp+68h+arg_28]
0x140009fd9  mov     rbp, rdx
0x140009fdc  mov     rsi, rcx
0x140009fdf  lea     r12, WPP_RECORDER_INITIALIZED
0x140009fe6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140009fed  lea     r13, WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids
0x140009ff4  jz      short loc_14000A011
0x140009ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x140009ffd  mov     r9d, 19h
0x14000a003  mov     qword ptr [rsp+68h+PriorityBoost], r13
0x14000a008  mov     rcx, [rcx+40h]
0x14000a00c  call    WPP_RECORDER_SF_s
0x14000a011  test    edi, edi
0x14000a013  jz      short loc_14000A02F
0x14000a015  mov     ebx, 0C0000295h
0x14000a01a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000a021  jz      loc_14000A0B0
0x14000a027  mov     r9d, 1Bh
0x14000a02d  jmp     short loc_14000A04D
0x14000a02f  cmp     [rsp+68h+arg_30], 14h
0x14000a037  jnb     short loc_14000A064
0x14000a039  mov     ebx, 0C0000023h
0x14000a03e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000a045  jz      short loc_14000A0B0
0x14000a047  mov     r9d, 1Ah
0x14000a04d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a054  mov     qword ptr [rsp+68h+PriorityBoost], r13
0x14000a059  mov     rcx, [rcx+40h]
0x14000a05d  call    WPP_RECORDER_SF_s
0x14000a062  jmp     short loc_14000A083
0x14000a064  mov     qword ptr [rbx], 0
0x14000a06b  mov     dword ptr [rbx+8], 0
0x14000a072  mov     qword ptr [rbx+0Ch], 2
0x14000a07a  xor     ebx, ebx
0x14000a07c  mov     dword ptr [r14], 14h
0x14000a083  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000a08a  jz      short loc_14000A0B0
0x14000a08c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a093  mov     r9d, 1Ch
0x14000a099  mov     [rsp+68h+var_30], ebx
0x14000a09d  mov     [rsp+68h+var_38], rsi
0x14000a0a2  mov     qword ptr [rsp+68h+PriorityBoost], r13
0x14000a0a7  mov     rcx, [rcx+40h]
0x14000a0ab  call    WPP_RECORDER_SF_sqd
0x14000a0b0  mov     r9d, 14h; BufferUsed
0x14000a0b6  mov     [rsp+68h+PriorityBoost], 0; PriorityBoost
0x14000a0bb  mov     r8d, ebx; Status
0x14000a0be  mov     rdx, rbp; Irp
0x14000a0c1  mov     rcx, rsi; DeviceObject
0x14000a0c4  call    cs:__imp_WmiCompleteRequest
0x14000a0cb  nop     dword ptr [rax+rax+00h]
0x14000a0d0  lea     r11, [rsp+68h+var_28]
0x14000a0d5  mov     rbx, [r11+40h]
0x14000a0d9  mov     rbp, [r11+48h]
0x14000a0dd  mov     rsp, r11
0x14000a0e0  pop     r14
0x14000a0e2  pop     r13
0x14000a0e4  pop     r12
0x14000a0e6  pop     rdi
0x14000a0e7  pop     rsi
0x14000a0e8  retn
```
