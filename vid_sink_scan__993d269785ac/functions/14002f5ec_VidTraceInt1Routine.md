# VidTraceInt1Routine

- ea: `0x14002f5ec`
- end: `0x14002f6a4`
- name: `VidTraceInt1Routine`
- size: `184`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400261ac`
- `0x14002e198`
- `0x14002f208`
- `0x1400a6e68`

## callees

- `0x140021650`
- `0x14002f5ec`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x14002f633`
- `ntoskrnl!EtwActivityIdControl` at `0x14002f633`
- `ntoskrnl!EtwWrite` at `0x14002f679`
- `ntoskrnl!EtwWrite` at `0x14002f679`

## pseudocode

```c
NTSTATUS __fastcall VidTraceInt1Routine(PCEVENT_DESCRIPTOR EventDescriptor, __int64 a2)
{
  GUID v2; // xmm1
  __int64 v6; // [rsp+30h] [rbp-40h] BYREF
  GUID ActivityId; // [rsp+40h] [rbp-30h] BYREF
  GUID v8; // [rsp+50h] [rbp-20h] BYREF

  v2 = 0;
  v8 = 0;
  ActivityId = 0;
  if ( VID_TRACE_ETW_GUID_Context )
  {
    EtwActivityIdControl(1u, &ActivityId);
    v2 = ActivityId;
  }
  *(_QWORD *)&ActivityId.Data1 = &v6;
  v8 = v2;
  v6 = a2;
  *(_QWORD *)ActivityId.Data4 = 8;
  return EtwWrite(VID_TRACE_ETW_GUID_Context, EventDescriptor, &v8, 1u, (PEVENT_DATA_DESCRIPTOR)&ActivityId);
}

```

## disassembly

```asm
0x14002f5ec  mov     [rsp-8+arg_8], rbx
0x14002f5f1  mov     [rsp-8+arg_10], rdi
0x14002f5f6  push    rbp
0x14002f5f7  mov     rbp, rsp
0x14002f5fa  sub     rsp, 70h
0x14002f5fe  mov     rax, cs:__security_cookie
0x14002f605  xor     rax, rsp
0x14002f608  mov     [rbp+var_10], rax
0x14002f60c  cmp     cs:VID_TRACE_ETW_GUID_Context, 0
0x14002f614  xorps   xmm0, xmm0
0x14002f617  xorps   xmm1, xmm1
0x14002f61a  mov     rbx, rdx
0x14002f61d  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x14002f621  mov     rdi, rcx
0x14002f624  movaps  xmmword ptr [rbp+ActivityId.Data1], xmm1
0x14002f628  jz      short loc_14002F643
0x14002f62a  lea     rdx, [rbp+ActivityId]; ActivityId
0x14002f62e  mov     ecx, 1; ControlCode
0x14002f633  call    cs:__imp_EtwActivityIdControl
0x14002f63a  nop     dword ptr [rax+rax+00h]
0x14002f63f  movaps  xmm1, xmmword ptr [rbp+ActivityId.Data1]
0x14002f643  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x14002f64a  lea     rax, [rbp+var_40]
0x14002f64e  mov     qword ptr [rbp+ActivityId.Data1], rax
0x14002f652  lea     r8, [rbp+var_20]; ActivityId
0x14002f656  lea     rax, [rbp+ActivityId]
0x14002f65a  movdqa  xmmword ptr [rbp+var_20.Data1], xmm1
0x14002f65f  mov     r9d, 1; UserDataCount
0x14002f665  mov     [rsp+70h+UserData], rax; UserData
0x14002f66a  mov     rdx, rdi; EventDescriptor
0x14002f66d  mov     [rbp+var_40], rbx
0x14002f671  mov     qword ptr [rbp+ActivityId.Data4], 8
0x14002f679  call    cs:__imp_EtwWrite
0x14002f680  nop     dword ptr [rax+rax+00h]
0x14002f685  mov     rcx, [rbp+var_10]
0x14002f689  xor     rcx, rsp; StackCookie
0x14002f68c  call    __security_check_cookie
0x14002f691  lea     r11, [rsp+70h+var_s0]
0x14002f696  mov     rbx, [r11+18h]
0x14002f69a  mov     rdi, [r11+20h]
0x14002f69e  mov     rsp, r11
0x14002f6a1  pop     rbp
0x14002f6a2  retn
```
