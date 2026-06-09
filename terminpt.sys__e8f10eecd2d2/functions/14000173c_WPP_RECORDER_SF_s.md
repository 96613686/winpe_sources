# WPP_RECORDER_SF_s

- ea: `0x14000173c`
- end: `0x1400017e0`
- name: `WPP_RECORDER_SF_s`
- size: `164`
- prototype: ``
- caller_count: `29`
- callee_count: `2`
- tags: ``

## callers

- `0x140001020`
- `0x1400010c0`
- `0x1400014f0`
- `0x1400015dc`
- `0x140001c34`
- `0x140001ce0`
- `0x1400024e8`
- `0x1400026a0`
- `0x140002a7c`
- `0x140002c9c`
- `0x140009010`
- `0x1400092f0`
- `0x1400098b4`
- `0x1400099f0`
- `0x140009b60`
- `0x140009d48`
- `0x140009e60`
- `0x140009fb0`
- `0x14000a0f0`
- `0x14000a1a0`
- `0x14000a250`
- `0x14000a300`
- `0x14000a500`
- `0x14000acac`
- `0x14000ae50`
- `0x14000af20`
- `0x14000b2d0`
- `0x14000c078`
- `0x14000c1b8`

## callees

- `0x14000173c`
- `0x140003130`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400017c3`
- `WppRecorder!WppAutoLogTrace` at `0x1400017c3`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_s(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, __int64 a5)
{
  int v8; // [rsp+20h] [rbp-28h]

  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64, _QWORD, const char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      a5,
      a4,
      " ",
      2,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 0, 1, a5, v8, " ", 2, 0);
}

```

## disassembly

```asm
0x14000173c  mov     r11, rsp
0x14000173f  mov     [r11+8], rbx
0x140001743  mov     [r11+10h], rbp
0x140001747  push    rdi
0x140001748  sub     rsp, 40h
0x14000174c  mov     rdi, rcx
0x14000174f  movzx   ebx, r9w
0x140001753  mov     rcx, cs:WPP_GLOBAL_Control
0x14000175a  lea     rbp, asc_140005150; " "
0x140001761  mov     eax, [rcx+2Ch]
0x140001764  test    al, 1
0x140001766  jz      short loc_140001799
0x140001768  mov     rax, cs:pfnWppTraceMessage
0x14000176f  mov     r9d, ebx
0x140001772  mov     r8, [rsp+48h+arg_20]
0x140001777  mov     edx, 2Bh ; '+'
0x14000177c  mov     rcx, [rcx+18h]
0x140001780  mov     qword ptr [r11-18h], 0
0x140001788  mov     qword ptr [r11-20h], 2
0x140001790  mov     [r11-28h], rbp
0x140001794  call    _guard_dispatch_icall
0x140001799  mov     r9, [rsp+48h+arg_20]
0x14000179e  xor     edx, edx
0x1400017a0  mov     [rsp+48h+var_10], 0
0x1400017a9  mov     rcx, rdi
0x1400017ac  mov     [rsp+48h+var_18], 2
0x1400017b5  mov     [rsp+48h+var_20], rbp
0x1400017ba  lea     r8d, [rdx+1]
0x1400017be  mov     [rsp+48h+var_28], bx
0x1400017c3  call    cs:__imp_WppAutoLogTrace
0x1400017ca  nop     dword ptr [rax+rax+00h]
0x1400017cf  mov     rbx, [rsp+48h+arg_0]
0x1400017d4  mov     rbp, [rsp+48h+arg_8]
0x1400017d9  add     rsp, 40h
0x1400017dd  pop     rdi
0x1400017de  retn
```
