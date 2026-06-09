# WPP_SF_

- ea: `0x180006fac`
- end: `0x180006fd4`
- name: `WPP_SF_`
- size: `40`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800025c0`
- `0x180002740`
- `0x180004270`
- `0x180004610`
- `0x180004b50`
- `0x180004f60`
- `0x1800073d0`
- `0x180007a40`
- `0x180008a10`
- `0x180008cb0`
- `0x180008f70`
- `0x180009480`
- `0x180009b90`
- `0x18000a184`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180006fc2`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180006fc2`

## pseudocode

```c
ULONG __fastcall WPP_SF_(TRACEHANDLE a1, USHORT a2, const GUID *a3)
{
  return TraceMessage(a1, 0x2Bu, a3, a2, 0);
}

```

## disassembly

```asm
0x180006fac  sub     rsp, 38h
0x180006fb0  movzx   r9d, dx; MessageNumber
0x180006fb4  mov     edx, 2Bh ; '+'; MessageFlags
0x180006fb9  mov     [rsp+38h+var_18], 0
0x180006fc2  call    cs:__imp_TraceMessage
0x180006fc9  nop     dword ptr [rax+rax+00h]
0x180006fce  add     rsp, 38h
0x180006fd2  retn
```
