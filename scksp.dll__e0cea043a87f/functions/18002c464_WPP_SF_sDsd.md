# WPP_SF_sDsd

- ea: `0x18002c464`
- end: `0x18002c4d1`
- name: `WPP_SF_sDsd`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c428`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18002c4c6`
- `ntdll!EtwTraceMessage` at `0x18002c4c6`

## string_xrefs

- `0x18002c490`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall WPP_SF_sDsd(__int64 a1)
{
  return EtwTraceMessage(a1, 43, WPP_0d7e072671ea36b765e87831c1b7d985_Traceguids);
}

```

## disassembly

```asm
0x18002c464  mov     r11, rsp
0x18002c467  sub     rsp, 78h
0x18002c46b  mov     qword ptr [r11-18h], 0
0x18002c473  lea     rax, [r11+38h]
0x18002c477  mov     r9d, 0Ah
0x18002c47d  lea     r8, WPP_0d7e072671ea36b765e87831c1b7d985_Traceguids
0x18002c484  lea     edx, [r9-6]
0x18002c488  mov     [r11-20h], rdx
0x18002c48c  mov     [r11-28h], rax
0x18002c490  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002c497  mov     qword ptr [r11-30h], 35h ; '5'
0x18002c49f  mov     [r11-38h], rax
0x18002c4a3  lea     rax, [r11+28h]
0x18002c4a7  mov     [r11-40h], rdx
0x18002c4ab  lea     edx, [r9+21h]
0x18002c4af  mov     [r11-48h], rax
0x18002c4b3  lea     rax, aStatus; "Status"
0x18002c4ba  mov     qword ptr [r11-50h], 7
0x18002c4c2  mov     [r11-58h], rax
0x18002c4c6  call    cs:__imp_EtwTraceMessage
0x18002c4cc  add     rsp, 78h
0x18002c4d0  retn
```
