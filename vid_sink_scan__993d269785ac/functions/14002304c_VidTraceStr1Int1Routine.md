# VidTraceStr1Int1Routine

- ea: `0x14002304c`
- end: `0x140023114`
- name: `VidTraceStr1Int1Routine`
- size: `200`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14008d084`
- `0x1400cd890`
- `0x1400cdb90`
- `0x1400ce2a0`
- `0x1400ce610`

## callees

- `0x140021650`
- `0x14002304c`
- `0x14003534c`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x140023096`
- `ntoskrnl!EtwActivityIdControl` at `0x140023096`
- `ntoskrnl!EtwWrite` at `0x1400230e8`
- `ntoskrnl!EtwWrite` at `0x1400230e8`

## pseudocode

```c
NTSTATUS __fastcall VidTraceStr1Int1Routine(PCEVENT_DESCRIPTOR EventDescriptor, __int64 a2, __int64 a3)
{
  GUID v3; // xmm1
  GUID ActivityId; // [rsp+30h] [rbp-50h] BYREF
  GUID v9; // [rsp+40h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-30h] BYREF
  GUID *p_ActivityId; // [rsp+60h] [rbp-20h]
  __int64 v12; // [rsp+68h] [rbp-18h]

  v3 = 0;
  v9 = 0;
  ActivityId = 0;
  if ( VID_TRACE_ETW_GUID_Context )
  {
    EtwActivityIdControl(1u, &ActivityId);
    v3 = ActivityId;
  }
  v9 = v3;
  *(_QWORD *)&ActivityId.Data1 = a3;
  VidTracepEventDataDescCreateUnicodeString(&UserData, a2);
  v12 = 8;
  p_ActivityId = &ActivityId;
  return EtwWrite(VID_TRACE_ETW_GUID_Context, EventDescriptor, &v9, 2u, &UserData);
}

```

## disassembly

```asm
0x14002304c  mov     [rsp-18h+arg_10], rbx
0x140023051  push    rbp
0x140023052  push    rsi
0x140023053  push    rdi
0x140023054  mov     rbp, rsp
0x140023057  sub     rsp, 80h
0x14002305e  mov     rax, cs:__security_cookie
0x140023065  xor     rax, rsp
0x140023068  mov     [rbp+var_10], rax
0x14002306c  cmp     cs:VID_TRACE_ETW_GUID_Context, 0
0x140023074  xorps   xmm0, xmm0
0x140023077  xorps   xmm1, xmm1
0x14002307a  mov     rbx, r8
0x14002307d  movups  xmmword ptr [rbp+var_40.Data1], xmm0
0x140023081  mov     rsi, rdx
0x140023084  mov     rdi, rcx
0x140023087  movaps  xmmword ptr [rbp+ActivityId.Data1], xmm1
0x14002308b  jz      short loc_1400230A6
0x14002308d  lea     rdx, [rbp+ActivityId]; ActivityId
0x140023091  mov     ecx, 1; ControlCode
0x140023096  call    cs:__imp_EtwActivityIdControl
0x14002309d  nop     dword ptr [rax+rax+00h]
0x1400230a2  movaps  xmm1, xmmword ptr [rbp+ActivityId.Data1]
0x1400230a6  mov     rdx, rsi
0x1400230a9  movdqa  xmmword ptr [rbp+var_40.Data1], xmm1
0x1400230ae  lea     rcx, [rbp+var_30]
0x1400230b2  mov     qword ptr [rbp+ActivityId.Data1], rbx
0x1400230b6  call    VidTracepEventDataDescCreateUnicodeString
0x1400230bb  lea     rcx, [rbp+ActivityId]
0x1400230bf  mov     [rbp+var_18], 8
0x1400230c7  mov     [rbp+var_20], rcx
0x1400230cb  lea     rax, [rbp+var_30]
0x1400230cf  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x1400230d6  lea     r8, [rbp+var_40]; ActivityId
0x1400230da  mov     r9d, 2; UserDataCount
0x1400230e0  mov     [rsp+80h+UserData], rax; UserData
0x1400230e5  mov     rdx, rdi; EventDescriptor
0x1400230e8  call    cs:__imp_EtwWrite
0x1400230ef  nop     dword ptr [rax+rax+00h]
0x1400230f4  mov     rcx, [rbp+var_10]
0x1400230f8  xor     rcx, rsp; StackCookie
0x1400230fb  call    __security_check_cookie
0x140023100  mov     rbx, [rsp+80h+arg_10]
0x140023108  add     rsp, 80h
0x14002310f  pop     rdi
0x140023110  pop     rsi
0x140023111  pop     rbp
0x140023112  retn
```
