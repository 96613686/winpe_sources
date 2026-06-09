# PtSetWmiDataItem

- ea: `0x14000a250`
- end: `0x14000a2f9`
- name: `PtSetWmiDataItem`
- size: `169`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000173c`
- `0x140001a80`
- `0x14000a250`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x14000a2e1`
- `WMILIB!WmiCompleteRequest` at `0x14000a2e1`

## pseudocode

```c
NTSTATUS __fastcall PtSetWmiDataItem(PDEVICE_OBJECT DeviceObject, PIRP Irp, int a3)
{
  NTSTATUS v6; // ebx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      a3,
      17,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
  v6 = a3 != 0 ? -1073741163 : -1073741114;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      a3,
      18,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
  return WmiCompleteRequest(DeviceObject, Irp, v6, 0, 0);
}

```

## disassembly

```asm
0x14000a250  push    rbx
0x14000a252  push    rbp
0x14000a253  push    rsi
0x14000a254  push    rdi
0x14000a255  push    r14
0x14000a257  sub     rsp, 40h
0x14000a25b  mov     ebx, r8d
0x14000a25e  mov     rsi, rdx
0x14000a261  mov     rdi, rcx
0x14000a264  lea     r14, WPP_RECORDER_INITIALIZED
0x14000a26b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000a272  lea     rbp, WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids
0x14000a279  jz      short loc_14000A296
0x14000a27b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a282  mov     r9d, 11h
0x14000a288  mov     qword ptr [rsp+68h+PriorityBoost], rbp
0x14000a28d  mov     rcx, [rcx+40h]
0x14000a291  call    WPP_RECORDER_SF_s
0x14000a296  neg     ebx
0x14000a298  sbb     ebx, ebx
0x14000a29a  and     ebx, 0FFFFFFCFh
0x14000a29d  add     ebx, 0C00002C6h
0x14000a2a3  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000a2aa  jz      short loc_14000A2D0
0x14000a2ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a2b3  mov     r9d, 12h
0x14000a2b9  mov     [rsp+68h+var_30], ebx
0x14000a2bd  mov     [rsp+68h+var_38], rdi
0x14000a2c2  mov     qword ptr [rsp+68h+PriorityBoost], rbp
0x14000a2c7  mov     rcx, [rcx+40h]
0x14000a2cb  call    WPP_RECORDER_SF_sqd
0x14000a2d0  xor     r9d, r9d; BufferUsed
0x14000a2d3  mov     [rsp+68h+PriorityBoost], 0; PriorityBoost
0x14000a2d8  mov     r8d, ebx; Status
0x14000a2db  mov     rdx, rsi; Irp
0x14000a2de  mov     rcx, rdi; DeviceObject
0x14000a2e1  call    cs:__imp_WmiCompleteRequest
0x14000a2e8  nop     dword ptr [rax+rax+00h]
0x14000a2ed  add     rsp, 40h
0x14000a2f1  pop     r14
0x14000a2f3  pop     rdi
0x14000a2f4  pop     rsi
0x14000a2f5  pop     rbp
0x14000a2f6  pop     rbx
0x14000a2f7  retn
```
