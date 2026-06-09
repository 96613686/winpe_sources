# WPP_SF_d

- ea: `0x180006c9c`
- end: `0x180006cd3`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `60`
- callee_count: `0`
- tags: ``

## callers

- `0x180002be0`
- `0x180002c98`
- `0x180002e70`
- `0x180002ff0`
- `0x1800030d0`
- `0x1800031bc`
- `0x180003868`
- `0x1800039c0`
- `0x180003ab0`
- `0x180003d98`
- `0x180003fb0`
- `0x1800041b0`
- `0x1800042c0`
- `0x180006ce0`
- `0x180006ec0`
- `0x180006fe0`
- `0x18000773c`
- `0x180007b9c`
- `0x180007d20`
- `0x180007dd8`
- `0x180007fe0`
- `0x180008208`
- `0x180008420`
- `0x18000a650`
- `0x18000aa40`
- `0x18000b5e8`
- `0x18000e35c`
- `0x18000e3fc`
- `0x18000e700`
- `0x18000ef80`
- `0x18000f148`
- `0x18000f25c`
- `0x18000f364`
- `0x18000f46c`
- `0x18000f59c`
- `0x18000f6c8`
- `0x18000f7f8`
- `0x18000f9dc`
- `0x18000fb0c`
- `0x18000fd54`
- `0x18000fef4`
- `0x1800100b4`
- `0x1800101bc`
- `0x1800102f8`
- `0x180010400`
- `0x180010508`
- `0x180010650`
- `0x180010734`
- `0x1800108f4`
- `0x180010b28`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180006cc8`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180006cc8`

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
0x180006c9c  mov     r11, rsp
0x180006c9f  mov     [r11+20h], r9d
0x180006ca3  sub     rsp, 48h
0x180006ca7  mov     qword ptr [r11-18h], 0
0x180006caf  lea     rax, [r11+20h]
0x180006cb3  movzx   r9d, dx; MessageNumber
0x180006cb7  mov     edx, 2Bh ; '+'; MessageFlags
0x180006cbc  mov     qword ptr [r11-20h], 4
0x180006cc4  mov     [r11-28h], rax
0x180006cc8  call    cs:__imp_TraceMessage
0x180006cce  add     rsp, 48h
0x180006cd2  retn
```
