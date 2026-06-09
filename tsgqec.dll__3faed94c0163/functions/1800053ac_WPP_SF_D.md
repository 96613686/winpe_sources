# WPP_SF_D

- ea: `0x1800053ac`
- end: `0x1800053e3`
- name: `WPP_SF_D`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180002e64`
- `0x180003178`
- `0x180004cd0`
- `0x180005260`
- `0x180007430`
- `0x180007820`
- `0x180007de0`
- `0x180008990`
- `0x180008ea0`
- `0x180009170`
- `0x180009380`
- `0x1800097e0`
- `0x180009960`
- `0x18000aafc`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x1800053d8`
- `ADVAPI32!TraceMessage` at `0x1800053d8`

## pseudocode

```c
ULONG __fastcall WPP_SF_D(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x1800053ac  mov     r11, rsp
0x1800053af  mov     [r11+20h], r9d
0x1800053b3  sub     rsp, 48h
0x1800053b7  mov     qword ptr [r11-18h], 0
0x1800053bf  lea     rax, [r11+20h]
0x1800053c3  movzx   r9d, dx; MessageNumber
0x1800053c7  mov     edx, 2Bh ; '+'; MessageFlags
0x1800053cc  mov     qword ptr [r11-20h], 4
0x1800053d4  mov     [r11-28h], rax
0x1800053d8  call    cs:__imp_TraceMessage
0x1800053de  add     rsp, 48h
0x1800053e2  retn
```
