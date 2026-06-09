# UmpoTraceSmartPresenceClearAwayIntervals

- ea: `0x18000c9f4`
- end: `0x18000ca66`
- name: `UmpoTraceSmartPresenceClearAwayIntervals`
- size: `114`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009ad0`

## callees

- `0x18000c9f4`
- `0x18000f3dc`
- `0x180010070`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000ca1d`
- `ntdll!RtlLengthSid` at `0x18000ca1d`
- `ntdll!EtwEventWrite` at `0x18000ca4d`
- `ntdll!EtwEventWrite` at `0x18000ca4d`

## pseudocode

```c
__int64 UmpoTraceSmartPresenceClearAwayIntervals()
{
  PSID v0; // rbx
  PSID v2; // [rsp+20h] [rbp-28h] BYREF
  ULONG v3; // [rsp+28h] [rbp-20h]
  int v4; // [rsp+2Ch] [rbp-1Ch]

  v0 = UmpoNullSid;
  if ( !UmpoNullSid )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v3 = RtlLengthSid(v0);
  v2 = v0;
  v4 = 0;
  return EtwEventWrite(UmpoProviderHandle, UMPO_EVT_SMART_USER_PRESENCE_INTERVALS_CLEAR, 1, &v2);
}

```

## disassembly

```asm
0x18000c9f4  push    rbx
0x18000c9f6  sub     rsp, 40h
0x18000c9fa  mov     rax, cs:__security_cookie
0x18000ca01  xor     rax, rsp
0x18000ca04  mov     [rsp+48h+var_18], rax
0x18000ca09  mov     rbx, cs:UmpoNullSid
0x18000ca10  test    rbx, rbx
0x18000ca13  jnz     short loc_18000CA1A
0x18000ca15  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ca1a  mov     rcx, rbx; Sid
0x18000ca1d  call    cs:__imp_RtlLengthSid
0x18000ca23  mov     rcx, cs:UmpoProviderHandle
0x18000ca2a  lea     r9, [rsp+48h+var_28]
0x18000ca2f  mov     r8d, 1
0x18000ca35  mov     [rsp+48h+var_20], eax
0x18000ca39  lea     rdx, UMPO_EVT_SMART_USER_PRESENCE_INTERVALS_CLEAR
0x18000ca40  mov     [rsp+48h+var_28], rbx
0x18000ca45  mov     [rsp+48h+var_1C], 0
0x18000ca4d  call    cs:__imp_EtwEventWrite
0x18000ca53  mov     rcx, [rsp+48h+var_18]
0x18000ca58  xor     rcx, rsp; StackCookie
0x18000ca5b  call    __security_check_cookie
0x18000ca60  add     rsp, 40h
0x18000ca64  pop     rbx
0x18000ca65  retn
```
