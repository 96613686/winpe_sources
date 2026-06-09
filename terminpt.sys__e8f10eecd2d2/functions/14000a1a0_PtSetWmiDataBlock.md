# PtSetWmiDataBlock

- ea: `0x14000a1a0`
- end: `0x14000a249`
- name: `PtSetWmiDataBlock`
- size: `169`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000173c`
- `0x140001a80`
- `0x14000a1a0`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x14000a231`
- `WMILIB!WmiCompleteRequest` at `0x14000a231`

## pseudocode

```c
NTSTATUS __fastcall PtSetWmiDataBlock(PDEVICE_OBJECT DeviceObject, PIRP Irp, int a3)
{
  NTSTATUS v6; // ebx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      a3,
      19,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
  v6 = a3 != 0 ? -1073741163 : -1073741114;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      a3,
      20,
      (__int64)WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids);
  return WmiCompleteRequest(DeviceObject, Irp, v6, 0, 0);
}

```

## disassembly

```asm
0x14000a1a0  push    rbx
0x14000a1a2  push    rbp
0x14000a1a3  push    rsi
0x14000a1a4  push    rdi
0x14000a1a5  push    r14
0x14000a1a7  sub     rsp, 40h
0x14000a1ab  mov     ebx, r8d
0x14000a1ae  mov     rsi, rdx
0x14000a1b1  mov     rdi, rcx
0x14000a1b4  lea     r14, WPP_RECORDER_INITIALIZED
0x14000a1bb  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000a1c2  lea     rbp, WPP_75dad5a240733c7ee0bdc334ce996264_Traceguids
0x14000a1c9  jz      short loc_14000A1E6
0x14000a1cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a1d2  mov     r9d, 13h
0x14000a1d8  mov     qword ptr [rsp+68h+PriorityBoost], rbp
0x14000a1dd  mov     rcx, [rcx+40h]
0x14000a1e1  call    WPP_RECORDER_SF_s
0x14000a1e6  neg     ebx
0x14000a1e8  sbb     ebx, ebx
0x14000a1ea  and     ebx, 0FFFFFFCFh
0x14000a1ed  add     ebx, 0C00002C6h
0x14000a1f3  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000a1fa  jz      short loc_14000A220
0x14000a1fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a203  mov     r9d, 14h
0x14000a209  mov     [rsp+68h+var_30], ebx
0x14000a20d  mov     [rsp+68h+var_38], rdi
0x14000a212  mov     qword ptr [rsp+68h+PriorityBoost], rbp
0x14000a217  mov     rcx, [rcx+40h]
0x14000a21b  call    WPP_RECORDER_SF_sqd
0x14000a220  xor     r9d, r9d; BufferUsed
0x14000a223  mov     [rsp+68h+PriorityBoost], 0; PriorityBoost
0x14000a228  mov     r8d, ebx; Status
0x14000a22b  mov     rdx, rsi; Irp
0x14000a22e  mov     rcx, rdi; DeviceObject
0x14000a231  call    cs:__imp_WmiCompleteRequest
0x14000a238  nop     dword ptr [rax+rax+00h]
0x14000a23d  add     rsp, 40h
0x14000a241  pop     r14
0x14000a243  pop     rdi
0x14000a244  pop     rsi
0x14000a245  pop     rbp
0x14000a246  pop     rbx
0x14000a247  retn
```
