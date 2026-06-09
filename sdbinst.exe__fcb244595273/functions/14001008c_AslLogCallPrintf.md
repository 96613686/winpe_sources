# AslLogCallPrintf

- ea: `0x14001008c`
- end: `0x1400100bd`
- name: `AslLogCallPrintf`
- size: `49`
- prototype: `__int64 (__fastcall *(__int64, _QWORD, _QWORD, const char *, ...))(_QWORD)`
- caller_count: `166`
- callee_count: `2`
- tags: ``

## callers

- `0x140003ff4`
- `0x140004c74`
- `0x140008500`
- `0x14000c1a0`
- `0x14000d710`
- `0x14000d8e8`
- `0x14000ec8c`
- `0x14000ee5c`
- `0x14000f074`
- `0x14000f158`
- `0x14000f28c`
- `0x14000f644`
- `0x14000fa64`
- `0x14000fb1c`
- `0x14000fb80`
- `0x14000fc40`
- `0x14000fd88`
- `0x14000fea0`
- `0x1400100c4`
- `0x14001031c`
- `0x1400103d8`
- `0x140010480`
- `0x140010568`
- `0x140010678`
- `0x140010844`
- `0x140010a68`
- `0x140010ae8`
- `0x140010bd8`
- `0x140010c9c`
- `0x140010d44`
- `0x140010f80`
- `0x140011184`
- `0x1400114cc`
- `0x140012be0`
- `0x140012d20`
- `0x140012db0`
- `0x140012ea0`
- `0x140013060`
- `0x1400131a0`
- `0x140013280`
- `0x1400133f0`
- `0x1400134e0`
- `0x14001357c`
- `0x140013638`
- `0x140013780`
- `0x140013824`
- `0x140013898`
- `0x140013938`
- `0x140013b84`
- `0x140013c14`

## callees

- `0x14001008c`
- `0x14002f010`

## pseudocode

```c
__int64 (__fastcall *AslLogCallPrintf(__int64 a1, _QWORD a2, _QWORD a3, const char *a4, ...))(_QWORD)
{
  __int64 (__fastcall *result)(_QWORD); // rax

  result = g_AslLogPfnVPrintf;
  if ( g_AslLogPfnVPrintf )
    return (__int64 (__fastcall *)(_QWORD))g_AslLogPfnVPrintf(a1);
  return result;
}

```

## disassembly

```asm
0x14001008c  mov     r11, rsp
0x14001008f  mov     [r11+20h], r9
0x140010093  sub     rsp, 48h
0x140010097  mov     rax, cs:g_AslLogPfnVPrintf
0x14001009e  mov     qword ptr [r11-18h], 0
0x1400100a6  test    rax, rax
0x1400100a9  jz      short loc_1400100B8
0x1400100ab  lea     r10, [r11+28h]
0x1400100af  mov     [r11-28h], r10
0x1400100b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400100b8  add     rsp, 48h
0x1400100bc  retn
```
