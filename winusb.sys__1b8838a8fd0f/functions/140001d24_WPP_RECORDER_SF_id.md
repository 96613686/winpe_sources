# WPP_RECORDER_SF_id

- ea: `0x140001d24`
- end: `0x140001dfc`
- name: `WPP_RECORDER_SF_id`
- size: `216`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004908`
- `0x140004ea4`

## callees

- `0x140001d24`
- `0x140010700`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001de4`
- `WppRecorder!WppAutoLogTrace` at `0x140001de4`

## pseudocode

```c
__int64 WPP_RECORDER_SF_id(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, int a5, ...)
{
  int v8; // [rsp+20h] [rbp-48h]
  int v9[6]; // [rsp+50h] [rbp-18h] BYREF
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v9[0] = -1073741811;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(_DEVICE_OBJECT *, __int64, __int64 *, _QWORD, char *, __int64, int *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
      a4,
      va,
      8,
      v9,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 2, 3, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids, v8, va);
}

```

## disassembly

```asm
0x140001d24  mov     r11, rsp
0x140001d27  mov     [r11+8], rbx
0x140001d2b  push    rdi
0x140001d2c  sub     rsp, 60h
0x140001d30  mov     rdi, rcx
0x140001d33  mov     [rsp+68h+var_18], 0C000000Dh
0x140001d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140001d42  movzx   ebx, r9w
0x140001d46  mov     eax, [rcx+2Ch]
0x140001d49  test    al, 4
0x140001d4b  jz      short loc_140001D9A
0x140001d4d  cmp     byte ptr [rcx+29h], 2
0x140001d51  jb      short loc_140001D9A
0x140001d53  mov     rax, cs:pfnWppTraceMessage
0x140001d5a  lea     rdx, [r11-18h]
0x140001d5e  mov     rcx, [rcx+18h]
0x140001d62  lea     r8, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x140001d69  mov     qword ptr [r11-28h], 0
0x140001d71  mov     r9d, ebx
0x140001d74  mov     qword ptr [r11-30h], 4
0x140001d7c  mov     [r11-38h], rdx
0x140001d80  lea     rdx, [r11+30h]
0x140001d84  mov     qword ptr [r11-40h], 8
0x140001d8c  mov     [r11-48h], rdx
0x140001d90  mov     edx, 2Bh ; '+'
0x140001d95  call    _guard_dispatch_icall
0x140001d9a  mov     [rsp+68h+var_20], 0
0x140001da3  lea     rax, [rsp+68h+var_18]
0x140001da8  mov     [rsp+68h+var_28], 4
0x140001db1  lea     r9, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x140001db8  mov     [rsp+68h+var_30], rax
0x140001dbd  mov     edx, 2
0x140001dc2  lea     rax, [rsp+68h+arg_28]
0x140001dca  mov     [rsp+68h+var_38], 8
0x140001dd3  mov     [rsp+68h+var_40], rax
0x140001dd8  mov     rcx, rdi
0x140001ddb  mov     [rsp+68h+var_48], bx
0x140001de0  lea     r8d, [rdx+1]
0x140001de4  call    cs:__imp_WppAutoLogTrace
0x140001deb  nop     dword ptr [rax+rax+00h]
0x140001df0  mov     rbx, [rsp+68h+arg_0]
0x140001df5  add     rsp, 60h
0x140001df9  pop     rdi
0x140001dfa  retn
```
