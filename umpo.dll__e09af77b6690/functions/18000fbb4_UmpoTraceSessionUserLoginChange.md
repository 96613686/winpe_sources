# UmpoTraceSessionUserLoginChange

- ea: `0x18000fbb4`
- end: `0x18000fc71`
- name: `UmpoTraceSessionUserLoginChange`
- size: `189`
- prototype: `__int64 __fastcall(char, __int64, int, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f9a8`
- `0x18000fb58`

## callees

- `0x18000f3dc`
- `0x18000fbb4`
- `0x180010070`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000fc54`
- `ntdll!EtwEventWrite` at `0x18000fc54`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000fc2b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000fc2b`

## pseudocode

```c
__int64 __fastcall UmpoTraceSessionUserLoginChange(char a1, __int64 a2, int a3, void *a4)
{
  BOOL v7; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v8[7]; // [rsp+30h] [rbp-50h] BYREF
  DWORD LengthSid; // [rsp+68h] [rbp-18h]
  int v10; // [rsp+6Ch] [rbp-14h]
  __int64 v11; // [rsp+A8h] [rbp+28h] BYREF
  int v12; // [rsp+B0h] [rbp+30h] BYREF

  v12 = a3;
  v11 = a2;
  v7 = 0;
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v8[3] = 8;
  v8[1] = 4;
  v7 = a1 != 0;
  v8[0] = &v7;
  v8[2] = &v11;
  v8[4] = &v12;
  v8[5] = 4;
  LengthSid = GetLengthSid(a4);
  v8[6] = a4;
  v10 = 0;
  return EtwEventWrite(UmpoProviderHandle, UMPO_EVT_SESSION_USER_CHANGE, 4, v8);
}

```

## disassembly

```asm
0x18000fbb4  mov     [rsp-18h+arg_10], r8d
0x18000fbb9  mov     [rsp-18h+arg_8], rdx
0x18000fbbe  push    rbp
0x18000fbbf  push    rbx
0x18000fbc0  push    rdi
0x18000fbc1  mov     rbp, rsp
0x18000fbc4  sub     rsp, 80h
0x18000fbcb  mov     rax, cs:__security_cookie
0x18000fbd2  xor     rax, rsp
0x18000fbd5  mov     [rbp+var_10], rax
0x18000fbd9  mov     [rbp+var_60], 0
0x18000fbe0  mov     rbx, r9
0x18000fbe3  mov     dil, cl
0x18000fbe6  test    r9, r9
0x18000fbe9  jnz     short loc_18000FBF0
0x18000fbeb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000fbf0  xor     eax, eax
0x18000fbf2  mov     [rbp+var_38], 8
0x18000fbfa  test    dil, dil
0x18000fbfd  mov     rcx, rbx; pSid
0x18000fc00  mov     edi, 4
0x18000fc05  setnz   al
0x18000fc08  mov     [rbp+var_48], rdi
0x18000fc0c  mov     [rbp+var_60], eax
0x18000fc0f  lea     rax, [rbp+var_60]
0x18000fc13  mov     [rbp+var_50], rax
0x18000fc17  lea     rax, [rbp+arg_8]
0x18000fc1b  mov     [rbp+var_40], rax
0x18000fc1f  lea     rax, [rbp+arg_10]
0x18000fc23  mov     [rbp+var_30], rax
0x18000fc27  mov     [rbp+var_28], rdi
0x18000fc2b  call    cs:__imp_GetLengthSid
0x18000fc31  mov     rcx, cs:UmpoProviderHandle
0x18000fc38  lea     r9, [rbp+var_50]
0x18000fc3c  mov     r8d, edi
0x18000fc3f  mov     [rbp+var_18], eax
0x18000fc42  lea     rdx, UMPO_EVT_SESSION_USER_CHANGE
0x18000fc49  mov     [rbp+var_20], rbx
0x18000fc4d  mov     [rbp+var_14], 0
0x18000fc54  call    cs:__imp_EtwEventWrite
0x18000fc5a  mov     rcx, [rbp+var_10]
0x18000fc5e  xor     rcx, rsp; StackCookie
0x18000fc61  call    __security_check_cookie
0x18000fc66  add     rsp, 80h
0x18000fc6d  pop     rdi
0x18000fc6e  pop     rbx
0x18000fc6f  pop     rbp
0x18000fc70  retn
```
