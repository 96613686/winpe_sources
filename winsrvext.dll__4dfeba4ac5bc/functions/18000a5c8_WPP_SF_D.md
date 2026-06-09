# WPP_SF_D

- ea: `0x18000a5c8`
- end: `0x18000a60d`
- name: `WPP_SF_D`
- size: `69`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180009688`
- `0x18000a914`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000a5fb`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000a5fb`

## pseudocode

```c
ULONG __fastcall WPP_SF_D(TRACEHANDLE a1, USHORT a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, &WPP_95618e15e79d3e424986cec7c2aa39d0_Traceguids, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x18000a5c8  mov     r11, rsp
0x18000a5cb  mov     [r11+20h], r9d
0x18000a5cf  sub     rsp, 48h
0x18000a5d3  mov     qword ptr [r11-18h], 0
0x18000a5db  lea     rax, [r11+20h]
0x18000a5df  movzx   r9d, dx; MessageNumber
0x18000a5e3  lea     r8, WPP_95618e15e79d3e424986cec7c2aa39d0_Traceguids; MessageGuid
0x18000a5ea  mov     qword ptr [r11-20h], 4
0x18000a5f2  mov     edx, 2Bh ; '+'; MessageFlags
0x18000a5f7  mov     [r11-28h], rax
0x18000a5fb  call    cs:__imp_TraceMessage
0x18000a602  nop     dword ptr [rax+rax+00h]
0x18000a607  add     rsp, 48h
0x18000a60b  retn
```
