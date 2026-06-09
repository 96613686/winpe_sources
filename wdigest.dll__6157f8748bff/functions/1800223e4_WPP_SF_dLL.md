# WPP_SF_dLL

- ea: `0x1800223e4`
- end: `0x18002243b`
- name: `WPP_SF_dLL`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800206d0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180022430`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180022430`

## pseudocode

```c
ULONG WPP_SF_dLL(TRACEHANDLE a1, __int64 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+88h] [rbp+20h] BYREF
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  v5 = a4;
  return TraceMessage(a1, 0x2Bu, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, 0x57u, &v5, 4, va, 4, va1, 4, 0);
}

```

## disassembly

```asm
0x1800223e4  mov     r11, rsp
0x1800223e7  mov     [r11+20h], r9d
0x1800223eb  sub     rsp, 68h
0x1800223ef  mov     qword ptr [r11-18h], 0
0x1800223f7  lea     rax, [r11+30h]
0x1800223fb  mov     r9d, 57h ; 'W'; MessageNumber
0x180022401  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids; MessageGuid
0x180022408  lea     edx, [r9-53h]
0x18002240c  mov     [r11-20h], rdx
0x180022410  mov     [r11-28h], rax
0x180022414  lea     rax, [r11+28h]
0x180022418  mov     [r11-30h], rdx
0x18002241c  mov     [r11-38h], rax
0x180022420  lea     rax, [r11+20h]
0x180022424  mov     [r11-40h], rdx
0x180022428  lea     edx, [r9-2Ch]; MessageFlags
0x18002242c  mov     [r11-48h], rax
0x180022430  call    cs:__imp_TraceMessage
0x180022436  add     rsp, 68h
0x18002243a  retn
```
