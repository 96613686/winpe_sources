# UmpoTraceConsoleSessionRundown

- ea: `0x180015f10`
- end: `0x180015f70`
- name: `UmpoTraceConsoleSessionRundown`
- size: `96`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008c80`

## callees

- `0x180010070`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180015f58`
- `ntdll!EtwEventWrite` at `0x180015f58`

## pseudocode

```c
__int64 UmpoTraceConsoleSessionRundown()
{
  int v1; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v2[2]; // [rsp+28h] [rbp-20h] BYREF

  v1 = UmpoConsoleSessionId;
  v2[1] = 4;
  v2[0] = &v1;
  return EtwEventWrite(UmpoProviderHandle, UMPO_EVT_CONSOLE_SESSION_RUNDOWN, 1, v2);
}

```

## disassembly

```asm
0x180015f10  mov     r11, rsp
0x180015f13  sub     rsp, 48h
0x180015f17  mov     rax, cs:__security_cookie
0x180015f1e  xor     rax, rsp
0x180015f21  mov     [rsp+48h+var_10], rax
0x180015f26  mov     eax, cs:UmpoConsoleSessionId
0x180015f2c  lea     r9, [r11-20h]
0x180015f30  mov     rcx, cs:UmpoProviderHandle
0x180015f37  lea     rdx, UMPO_EVT_CONSOLE_SESSION_RUNDOWN
0x180015f3e  mov     [rsp+48h+var_28], eax
0x180015f42  mov     r8d, 1
0x180015f48  lea     rax, [r11-28h]
0x180015f4c  mov     qword ptr [r11-18h], 4
0x180015f54  mov     [r11-20h], rax
0x180015f58  call    cs:__imp_EtwEventWrite
0x180015f5e  mov     rcx, [rsp+48h+var_10]
0x180015f63  xor     rcx, rsp; StackCookie
0x180015f66  call    __security_check_cookie
0x180015f6b  add     rsp, 48h
0x180015f6f  retn
```
