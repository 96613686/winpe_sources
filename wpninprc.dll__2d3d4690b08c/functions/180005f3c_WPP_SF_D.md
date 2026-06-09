# WPP_SF_D

- ea: `0x180005f3c`
- end: `0x180005f73`
- name: `WPP_SF_D`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005990`
- `0x180005b7c`
- `0x180006320`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180005f68`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180005f68`

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
0x180005f3c  mov     r11, rsp
0x180005f3f  mov     [r11+20h], r9d
0x180005f43  sub     rsp, 48h
0x180005f47  mov     qword ptr [r11-18h], 0
0x180005f4f  lea     rax, [r11+20h]
0x180005f53  movzx   r9d, dx; MessageNumber
0x180005f57  mov     edx, 2Bh ; '+'; MessageFlags
0x180005f5c  mov     qword ptr [r11-20h], 4
0x180005f64  mov     [r11-28h], rax
0x180005f68  call    cs:__imp_TraceMessage
0x180005f6e  add     rsp, 48h
0x180005f72  retn
```
