# VidTraceInt2Routine

- ea: `0x140030b60`
- end: `0x140030c28`
- name: `VidTraceInt2Routine`
- size: `200`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x140025e74`
- `0x140026090`
- `0x14002ab18`
- `0x14002b790`
- `0x14002b934`
- `0x14002bab0`
- `0x14002bd44`
- `0x14002c610`
- `0x14002f408`
- `0x140030650`
- `0x1400c4fd4`
- `0x1400c5620`
- `0x1400c5dcc`
- `0x1400c7170`
- `0x1400d633c`
- `0x1400db3c0`
- `0x1400de334`
- `0x1400e0af8`
- `0x1400e37a0`

## callees

- `0x140021c60`
- `0x140030b60`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x140030ba9`
- `ntoskrnl!EtwActivityIdControl` at `0x140030ba9`
- `ntoskrnl!EtwWrite` at `0x140030c03`
- `ntoskrnl!EtwWrite` at `0x140030c03`

## pseudocode

```c
NTSTATUS __fastcall VidTraceInt2Routine(PCEVENT_DESCRIPTOR EventDescriptor, __int64 a2, __int64 a3)
{
  GUID v3; // xmm1
  GUID ActivityId; // [rsp+30h] [rbp-29h] BYREF
  __int64 v9; // [rsp+40h] [rbp-19h] BYREF
  GUID v10; // [rsp+50h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp+7h] BYREF
  GUID *p_ActivityId; // [rsp+70h] [rbp+17h]
  __int64 v13; // [rsp+78h] [rbp+1Fh]

  v3 = 0;
  v10 = 0;
  ActivityId = 0;
  if ( VID_TRACE_ETW_GUID_Context )
  {
    EtwActivityIdControl(1u, &ActivityId);
    v3 = ActivityId;
  }
  UserData.Ptr = (ULONGLONG)&v9;
  v10 = v3;
  p_ActivityId = &ActivityId;
  *(_QWORD *)&ActivityId.Data1 = a3;
  v9 = a2;
  *(_QWORD *)&UserData.Size = 8;
  v13 = 8;
  return EtwWrite(VID_TRACE_ETW_GUID_Context, EventDescriptor, &v10, 2u, &UserData);
}

```

## disassembly

```asm
0x140030b60  push    rbp
0x140030b62  push    rbx
0x140030b63  push    rsi
0x140030b64  push    rdi
0x140030b65  lea     rbp, [rsp-3Fh]
0x140030b6a  sub     rsp, 98h
0x140030b71  mov     rax, cs:__security_cookie
0x140030b78  xor     rax, rsp
0x140030b7b  mov     [rbp+57h+var_30], rax
0x140030b7f  cmp     cs:VID_TRACE_ETW_GUID_Context, 0
0x140030b87  xorps   xmm0, xmm0
0x140030b8a  xorps   xmm1, xmm1
0x140030b8d  mov     rbx, r8
0x140030b90  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x140030b94  mov     rdi, rdx
0x140030b97  mov     rsi, rcx
0x140030b9a  movaps  xmmword ptr [rbp+57h+ActivityId.Data1], xmm1
0x140030b9e  jz      short loc_140030BB9
0x140030ba0  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x140030ba4  mov     ecx, 1; ControlCode
0x140030ba9  call    cs:__imp_EtwActivityIdControl
0x140030bb0  nop     dword ptr [rax+rax+00h]
0x140030bb5  movaps  xmm1, xmmword ptr [rbp+57h+ActivityId.Data1]
0x140030bb9  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x140030bc0  lea     rax, [rbp+57h+var_70]
0x140030bc4  mov     [rbp+57h+var_50.Ptr], rax
0x140030bc8  lea     r8, [rbp+57h+var_60]; ActivityId
0x140030bcc  lea     rax, [rbp+57h+ActivityId]
0x140030bd0  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm1
0x140030bd5  mov     [rbp+57h+var_40], rax
0x140030bd9  mov     r9d, 2; UserDataCount
0x140030bdf  lea     rax, [rbp+57h+var_50]
0x140030be3  mov     qword ptr [rbp+57h+ActivityId.Data1], rbx
0x140030be7  mov     rdx, rsi; EventDescriptor
0x140030bea  mov     [rsp+0B0h+UserData], rax; UserData
0x140030bef  mov     [rbp+57h+var_70], rdi
0x140030bf3  mov     qword ptr [rbp+57h+var_50.Size], 8
0x140030bfb  mov     [rbp+57h+var_38], 8
0x140030c03  call    cs:__imp_EtwWrite
0x140030c0a  nop     dword ptr [rax+rax+00h]
0x140030c0f  mov     rcx, [rbp+57h+var_30]
0x140030c13  xor     rcx, rsp; StackCookie
0x140030c16  call    __security_check_cookie
0x140030c1b  add     rsp, 98h
0x140030c22  pop     rdi
0x140030c23  pop     rsi
0x140030c24  pop     rbx
0x140030c25  pop     rbp
0x140030c26  retn
```
