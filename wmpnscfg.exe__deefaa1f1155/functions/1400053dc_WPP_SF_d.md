# WPP_SF_d

- ea: `0x1400053dc`
- end: `0x140005413`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140005658`
- `0x1400065cc`
- `0x140006764`
- `0x140006848`
- `0x140006a04`
- `0x140006d7c`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x140005408`
- `ADVAPI32!TraceMessage` at `0x140005408`

## pseudocode

```c
ULONG __fastcall WPP_SF_d(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x1400053dc  mov     r11, rsp
0x1400053df  mov     [r11+20h], r9d
0x1400053e3  sub     rsp, 48h
0x1400053e7  mov     qword ptr [r11-18h], 0
0x1400053ef  lea     rax, [r11+20h]
0x1400053f3  movzx   r9d, dx; MessageNumber
0x1400053f7  mov     edx, 2Bh ; '+'; MessageFlags
0x1400053fc  mov     qword ptr [r11-20h], 4
0x140005404  mov     [r11-28h], rax
0x140005408  call    cs:__imp_TraceMessage
0x14000540e  add     rsp, 48h
0x140005412  retn
```
