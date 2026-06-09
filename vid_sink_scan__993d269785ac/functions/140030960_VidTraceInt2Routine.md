# VidTraceInt2Routine

- ea: `0x140030960`
- end: `0x140030a28`
- name: `VidTraceInt2Routine`
- size: `200`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x140025cd4`
- `0x140025ef0`
- `0x14002a918`
- `0x14002b590`
- `0x14002b734`
- `0x14002b8b0`
- `0x14002bb44`
- `0x14002c404`
- `0x14002f208`
- `0x140030450`
- `0x1400c2fd4`
- `0x1400c3620`
- `0x1400c3dcc`
- `0x1400c5170`
- `0x1400d399c`
- `0x1400d8990`
- `0x1400db8d8`
- `0x1400ddf8c`
- `0x1400e0bd0`

## callees

- `0x140021650`
- `0x140030960`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x1400309a9`
- `ntoskrnl!EtwActivityIdControl` at `0x1400309a9`
- `ntoskrnl!EtwWrite` at `0x140030a03`
- `ntoskrnl!EtwWrite` at `0x140030a03`

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
0x140030960  push    rbp
0x140030962  push    rbx
0x140030963  push    rsi
0x140030964  push    rdi
0x140030965  lea     rbp, [rsp-3Fh]
0x14003096a  sub     rsp, 98h
0x140030971  mov     rax, cs:__security_cookie
0x140030978  xor     rax, rsp
0x14003097b  mov     [rbp+57h+var_30], rax
0x14003097f  cmp     cs:VID_TRACE_ETW_GUID_Context, 0
0x140030987  xorps   xmm0, xmm0
0x14003098a  xorps   xmm1, xmm1
0x14003098d  mov     rbx, r8
0x140030990  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x140030994  mov     rdi, rdx
0x140030997  mov     rsi, rcx
0x14003099a  movaps  xmmword ptr [rbp+57h+ActivityId.Data1], xmm1
0x14003099e  jz      short loc_1400309B9
0x1400309a0  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1400309a4  mov     ecx, 1; ControlCode
0x1400309a9  call    cs:__imp_EtwActivityIdControl
0x1400309b0  nop     dword ptr [rax+rax+00h]
0x1400309b5  movaps  xmm1, xmmword ptr [rbp+57h+ActivityId.Data1]
0x1400309b9  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x1400309c0  lea     rax, [rbp+57h+var_70]
0x1400309c4  mov     [rbp+57h+var_50.Ptr], rax
0x1400309c8  lea     r8, [rbp+57h+var_60]; ActivityId
0x1400309cc  lea     rax, [rbp+57h+ActivityId]
0x1400309d0  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm1
0x1400309d5  mov     [rbp+57h+var_40], rax
0x1400309d9  mov     r9d, 2; UserDataCount
0x1400309df  lea     rax, [rbp+57h+var_50]
0x1400309e3  mov     qword ptr [rbp+57h+ActivityId.Data1], rbx
0x1400309e7  mov     rdx, rsi; EventDescriptor
0x1400309ea  mov     [rsp+0B0h+UserData], rax; UserData
0x1400309ef  mov     [rbp+57h+var_70], rdi
0x1400309f3  mov     qword ptr [rbp+57h+var_50.Size], 8
0x1400309fb  mov     [rbp+57h+var_38], 8
0x140030a03  call    cs:__imp_EtwWrite
0x140030a0a  nop     dword ptr [rax+rax+00h]
0x140030a0f  mov     rcx, [rbp+57h+var_30]
0x140030a13  xor     rcx, rsp; StackCookie
0x140030a16  call    __security_check_cookie
0x140030a1b  add     rsp, 98h
0x140030a22  pop     rdi
0x140030a23  pop     rsi
0x140030a24  pop     rbx
0x140030a25  pop     rbp
0x140030a26  retn
```
