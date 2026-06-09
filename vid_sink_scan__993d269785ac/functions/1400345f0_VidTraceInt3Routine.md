# VidTraceInt3Routine

- ea: `0x1400345f0`
- end: `0x1400346e4`
- name: `VidTraceInt3Routine`
- size: `244`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x1400197f0`
- `0x140025cd4`
- `0x140025ef0`
- `0x14002a918`
- `0x14002b590`
- `0x14002b734`
- `0x14002b8b0`
- `0x14002bb44`
- `0x14002c404`
- `0x14002e3c0`
- `0x1400a6e68`
- `0x1400d399c`
- `0x1400d8990`
- `0x1400db8d8`
- `0x1400ddf8c`
- `0x1400e0bd0`

## callees

- `0x140021650`
- `0x1400345f0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x140034645`
- `ntoskrnl!EtwActivityIdControl` at `0x140034645`
- `ntoskrnl!EtwWrite` at `0x1400346b3`
- `ntoskrnl!EtwWrite` at `0x1400346b3`

## pseudocode

```c
NTSTATUS __fastcall VidTraceInt3Routine(PCEVENT_DESCRIPTOR EventDescriptor, __int64 a2, __int64 a3, __int64 a4)
{
  GUID v4; // xmm1
  GUID ActivityId; // [rsp+30h] [rbp-29h] BYREF
  __int64 v11; // [rsp+40h] [rbp-19h] BYREF
  __int64 v12; // [rsp+48h] [rbp-11h] BYREF
  GUID v13; // [rsp+50h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp+7h] BYREF
  __int64 *v15; // [rsp+70h] [rbp+17h]
  __int64 v16; // [rsp+78h] [rbp+1Fh]
  GUID *p_ActivityId; // [rsp+80h] [rbp+27h]
  __int64 v18; // [rsp+88h] [rbp+2Fh]

  v4 = 0;
  v13 = 0;
  ActivityId = 0;
  if ( VID_TRACE_ETW_GUID_Context )
  {
    EtwActivityIdControl(1u, &ActivityId);
    v4 = ActivityId;
  }
  UserData.Ptr = (ULONGLONG)&v11;
  v13 = v4;
  v15 = &v12;
  *(_QWORD *)&ActivityId.Data1 = a4;
  p_ActivityId = &ActivityId;
  v12 = a3;
  v11 = a2;
  *(_QWORD *)&UserData.Size = 8;
  v16 = 8;
  v18 = 8;
  return EtwWrite(VID_TRACE_ETW_GUID_Context, EventDescriptor, &v13, 3u, &UserData);
}

```

## disassembly

```asm
0x1400345f0  mov     [rsp-8+arg_8], rbx
0x1400345f5  mov     [rsp-8+arg_10], rsi
0x1400345fa  push    rbp
0x1400345fb  push    rdi
0x1400345fc  push    r14
0x1400345fe  lea     rbp, [rsp-47h]
0x140034603  sub     rsp, 0A0h
0x14003460a  mov     rax, cs:__security_cookie
0x140034611  xor     rax, rsp
0x140034614  mov     [rbp+57h+var_20], rax
0x140034618  cmp     cs:VID_TRACE_ETW_GUID_Context, 0
0x140034620  xorps   xmm0, xmm0
0x140034623  xorps   xmm1, xmm1
0x140034626  mov     rbx, r9
0x140034629  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x14003462d  mov     rdi, r8
0x140034630  mov     rsi, rdx
0x140034633  movaps  xmmword ptr [rbp+57h+ActivityId.Data1], xmm1
0x140034637  mov     r14, rcx
0x14003463a  jz      short loc_140034655
0x14003463c  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x140034640  mov     ecx, 1; ControlCode
0x140034645  call    cs:__imp_EtwActivityIdControl
0x14003464c  nop     dword ptr [rax+rax+00h]
0x140034651  movaps  xmm1, xmmword ptr [rbp+57h+ActivityId.Data1]
0x140034655  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x14003465c  lea     rax, [rbp+57h+var_70]
0x140034660  mov     [rbp+57h+var_50.Ptr], rax
0x140034664  lea     r8, [rbp+57h+var_60]; ActivityId
0x140034668  lea     rax, [rbp+57h+var_68]
0x14003466c  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm1
0x140034671  mov     [rbp+57h+var_40], rax
0x140034675  mov     r9d, 3; UserDataCount
0x14003467b  lea     rax, [rbp+57h+ActivityId]
0x14003467f  mov     qword ptr [rbp+57h+ActivityId.Data1], rbx
0x140034683  mov     [rbp+57h+var_30], rax
0x140034687  mov     rdx, r14; EventDescriptor
0x14003468a  lea     rax, [rbp+57h+var_50]
0x14003468e  mov     [rbp+57h+var_68], rdi
0x140034692  mov     [rsp+0B0h+UserData], rax; UserData
0x140034697  mov     [rbp+57h+var_70], rsi
0x14003469b  mov     qword ptr [rbp+57h+var_50.Size], 8
0x1400346a3  mov     [rbp+57h+var_38], 8
0x1400346ab  mov     [rbp+57h+var_28], 8
0x1400346b3  call    cs:__imp_EtwWrite
0x1400346ba  nop     dword ptr [rax+rax+00h]
0x1400346bf  mov     rcx, [rbp+57h+var_20]
0x1400346c3  xor     rcx, rsp; StackCookie
0x1400346c6  call    __security_check_cookie
0x1400346cb  lea     r11, [rsp+0B0h+var_10]
0x1400346d3  mov     rbx, [r11+28h]
0x1400346d7  mov     rsi, [r11+30h]
0x1400346db  mov     rsp, r11
0x1400346de  pop     r14
0x1400346e0  pop     rdi
0x1400346e1  pop     rbp
0x1400346e2  retn
```
