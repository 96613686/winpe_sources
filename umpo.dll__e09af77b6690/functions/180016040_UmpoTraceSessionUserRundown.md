# UmpoTraceSessionUserRundown

- ea: `0x180016040`
- end: `0x1800160e0`
- name: `UmpoTraceSessionUserRundown`
- size: `160`
- prototype: `__int64 __fastcall(__int64, int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008c80`

## callees

- `0x18000f3dc`
- `0x180010070`
- `0x180016040`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800160c0`
- `ntdll!EtwEventWrite` at `0x1800160c0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180016094`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180016094`

## pseudocode

```c
__int64 __fastcall UmpoTraceSessionUserRundown(__int64 a1, int a2, void *a3)
{
  _QWORD v5[5]; // [rsp+20h] [rbp-40h] BYREF
  DWORD LengthSid; // [rsp+48h] [rbp-18h]
  int v7; // [rsp+4Ch] [rbp-14h]
  __int64 v8; // [rsp+70h] [rbp+10h] BYREF
  int v9; // [rsp+78h] [rbp+18h] BYREF

  v9 = a2;
  v8 = a1;
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v5[1] = 8;
  v5[0] = &v8;
  v5[3] = 4;
  v5[2] = &v9;
  LengthSid = GetLengthSid(a3);
  v5[4] = a3;
  v7 = 0;
  return EtwEventWrite(UmpoProviderHandle, UMPO_EVT_SESSION_USER_RUNDOWN, 3, v5);
}

```

## disassembly

```asm
0x180016040  mov     [rsp-8+arg_18], rbx
0x180016045  mov     [rsp-8+arg_8], edx
0x180016049  mov     [rsp-8+arg_0], rcx
0x18001604e  push    rbp
0x18001604f  mov     rbp, rsp
0x180016052  sub     rsp, 60h
0x180016056  mov     rax, cs:__security_cookie
0x18001605d  xor     rax, rsp
0x180016060  mov     [rbp+var_10], rax
0x180016064  mov     rbx, r8
0x180016067  test    r8, r8
0x18001606a  jnz     short loc_180016071
0x18001606c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180016071  lea     rax, [rbp+arg_0]
0x180016075  mov     [rbp+var_38], 8
0x18001607d  mov     [rbp+var_40], rax
0x180016081  mov     rcx, rbx; pSid
0x180016084  lea     rax, [rbp+arg_8]
0x180016088  mov     [rbp+var_28], 4
0x180016090  mov     [rbp+var_30], rax
0x180016094  call    cs:__imp_GetLengthSid
0x18001609a  mov     rcx, cs:UmpoProviderHandle
0x1800160a1  lea     r9, [rbp+var_40]
0x1800160a5  mov     r8d, 3
0x1800160ab  mov     [rbp+var_18], eax
0x1800160ae  lea     rdx, UMPO_EVT_SESSION_USER_RUNDOWN
0x1800160b5  mov     [rbp+var_20], rbx
0x1800160b9  mov     [rbp+var_14], 0
0x1800160c0  call    cs:__imp_EtwEventWrite
0x1800160c6  mov     rcx, [rbp+var_10]
0x1800160ca  xor     rcx, rsp; StackCookie
0x1800160cd  call    __security_check_cookie
0x1800160d2  mov     rbx, [rsp+60h+arg_18]
0x1800160da  add     rsp, 60h
0x1800160de  pop     rbp
0x1800160df  retn
```
