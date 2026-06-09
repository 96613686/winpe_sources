# WPP_SF_d

- ea: `0x180011d6c`
- end: `0x180011da3`
- name: `WPP_SF_d`
- size: `55`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006800`
- `0x1800072fc`
- `0x1800073a0`
- `0x1800084d0`
- `0x180008be0`
- `0x180008ee0`
- `0x18000e720`
- `0x18000f578`
- `0x18001dc78`
- `0x18001dec0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180011d98`
- `ntdll!EtwTraceMessage` at `0x180011d98`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x180011d6c  mov     r11, rsp
0x180011d6f  mov     [r11+20h], r9d
0x180011d73  sub     rsp, 48h
0x180011d77  mov     qword ptr [r11-18h], 0
0x180011d7f  lea     rax, [r11+20h]
0x180011d83  movzx   r9d, dx
0x180011d87  mov     edx, 2Bh ; '+'
0x180011d8c  mov     qword ptr [r11-20h], 4
0x180011d94  mov     [r11-28h], rax
0x180011d98  call    cs:__imp_EtwTraceMessage
0x180011d9e  add     rsp, 48h
0x180011da2  retn
```
