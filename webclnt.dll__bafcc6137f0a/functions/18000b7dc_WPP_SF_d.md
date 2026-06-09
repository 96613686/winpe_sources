# WPP_SF_d

- ea: `0x18000b7dc`
- end: `0x18000b813`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, int)`
- caller_count: `134`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000235c`
- `0x18000298c`
- `0x180002ca0`
- `0x18000306c`
- `0x1800031d0`
- `0x180003458`
- `0x18000370c`
- `0x180003a9c`
- `0x180003cbc`
- `0x180003f8c`
- `0x1800045e8`
- `0x1800049bc`
- `0x180005310`
- `0x180005568`
- `0x1800056f4`
- `0x180005844`
- `0x18000591c`
- `0x180005a38`
- `0x180005de4`
- `0x18000656c`
- `0x180006618`
- `0x180006670`
- `0x180006a90`
- `0x180006d20`
- `0x180007b50`
- `0x180007e10`
- `0x180008c50`
- `0x180008f00`
- `0x1800091e0`
- `0x180009480`
- `0x180009740`
- `0x1800099d0`
- `0x18000a010`
- `0x18000a370`
- `0x18000a6e0`
- `0x18000a770`
- `0x18000b060`
- `0x18000bd30`
- `0x18000c128`
- `0x18000c350`
- `0x18000c7a4`
- `0x18000ca04`
- `0x18000cc84`
- `0x18000ce10`
- `0x18000d9e4`
- `0x18000fa88`
- `0x18000fce0`
- `0x180010028`
- `0x180010478`
- `0x180010770`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000b808`
- `ntdll!EtwTraceMessage` at `0x18000b808`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5);
}

```

## disassembly

```asm
0x18000b7dc  mov     r11, rsp
0x18000b7df  mov     [r11+20h], r9d
0x18000b7e3  sub     rsp, 48h
0x18000b7e7  mov     qword ptr [r11-18h], 0
0x18000b7ef  lea     rax, [r11+20h]
0x18000b7f3  movzx   r9d, dx
0x18000b7f7  mov     edx, 2Bh ; '+'
0x18000b7fc  mov     qword ptr [r11-20h], 4
0x18000b804  mov     [r11-28h], rax
0x18000b808  call    cs:__imp_EtwTraceMessage
0x18000b80e  add     rsp, 48h
0x18000b812  retn
```
