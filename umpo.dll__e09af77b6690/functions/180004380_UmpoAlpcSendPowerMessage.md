# UmpoAlpcSendPowerMessage

- ea: `0x180004380`
- end: `0x180004418`
- name: `UmpoAlpcSendPowerMessage`
- size: `152`
- prototype: `__int64 __fastcall(const void *, unsigned int)`
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002bc0`
- `0x180003e40`
- `0x180004e60`
- `0x180008640`
- `0x18000c534`
- `0x180011978`
- `0x180016a3c`

## callees

- `0x180001770`
- `0x180004380`
- `0x18000f3dc`
- `0x180010070`
- `0x180010946`
- `0x180018850`
- `0x1800188c8`

## pseudocode

```c
__int64 __fastcall UmpoAlpcSendPowerMessage(const void *a1, unsigned int a2)
{
  size_t v2; // rbx
  _WORD v5[2]; // [rsp+20h] [rbp-1018h] BYREF
  _BYTE v6[36]; // [rsp+24h] [rbp-1014h] BYREF
  _BYTE v7[4056]; // [rsp+48h] [rbp-FF0h] BYREF

  v2 = a2;
  memset_0(v6, 0, 0xFFCu);
  if ( (unsigned int)v2 <= 0xFD8 )
  {
    v5[0] = v2;
    v5[1] = v2 + 40;
    memcpy_0(v7, a1, v2);
    return UmpoAlpcSendPortMessage((__int64)v5);
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return 111;
  }
}

```

## disassembly

```asm
0x180004380  mov     [rsp+arg_10], rbx
0x180004385  push    rdi
0x180004386  mov     eax, 1030h
0x18000438b  call    _alloca_probe
0x180004390  sub     rsp, rax
0x180004393  mov     rax, cs:__security_cookie
0x18000439a  xor     rax, rsp
0x18000439d  mov     [rsp+1038h+var_18], rax
0x1800043a5  mov     ebx, edx
0x1800043a7  mov     rdi, rcx
0x1800043aa  xor     edx, edx; Val
0x1800043ac  lea     rcx, [rsp+1038h+var_1014]; void *
0x1800043b1  mov     r8d, 0FFCh; Size
0x1800043b7  call    memset_0
0x1800043bc  cmp     ebx, 0FD8h
0x1800043c2  jbe     short loc_1800043D0
0x1800043c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800043c9  mov     eax, 6Fh ; 'o'
0x1800043ce  jmp     short loc_1800043F7
0x1800043d0  lea     eax, [rbx+28h]
0x1800043d3  mov     [rsp+1038h+var_1018], bx
0x1800043d8  mov     r8, rbx; Size
0x1800043db  mov     [rsp+1038h+var_1016], ax
0x1800043e0  mov     rdx, rdi; Src
0x1800043e3  lea     rcx, [rsp+1038h+var_FF0]; void *
0x1800043e8  call    memcpy_0
0x1800043ed  lea     rcx, [rsp+1038h+var_1018]
0x1800043f2  call    UmpoAlpcSendPortMessage
0x1800043f7  mov     rcx, [rsp+1038h+var_18]
0x1800043ff  xor     rcx, rsp; StackCookie
0x180004402  call    __security_check_cookie
0x180004407  mov     rbx, [rsp+1038h+arg_10]
0x18000440f  add     rsp, 1030h
0x180004416  pop     rdi
0x180004417  retn
```
