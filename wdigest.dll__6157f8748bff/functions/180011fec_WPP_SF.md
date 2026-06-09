# WPP_SF_

- ea: `0x180011fec`
- end: `0x18001200d`
- name: `WPP_SF_`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `150`
- callee_count: `0`
- tags: ``

## callers

- `0x180001bb0`
- `0x180002ef0`
- `0x180003520`
- `0x1800036c8`
- `0x180003850`
- `0x180003a50`
- `0x180004cb0`
- `0x180006260`
- `0x180006ec0`
- `0x1800076b0`
- `0x180007aa0`
- `0x180007ca0`
- `0x180008220`
- `0x1800083a0`
- `0x180008498`
- `0x180008664`
- `0x1800088b8`
- `0x180008c40`
- `0x180009820`
- `0x180009f00`
- `0x18000ab70`
- `0x18000b2e0`
- `0x18000c990`
- `0x18000cb00`
- `0x18000cca0`
- `0x18000cf00`
- `0x18000d9d0`
- `0x18000db00`
- `0x18000e6c0`
- `0x18000ee80`
- `0x18000f3dc`
- `0x18000fa94`
- `0x18000fe80`
- `0x180010510`
- `0x18001721c`
- `0x180017780`
- `0x1800179f4`
- `0x180017efc`
- `0x180018298`
- `0x180018e84`
- `0x1800192e8`
- `0x180019bd0`
- `0x180019f80`
- `0x18001a6c0`
- `0x18001aa20`
- `0x18001ab50`
- `0x18001ad3c`
- `0x18001b2f8`
- `0x18001b4b0`
- `0x18001baac`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180012002`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180012002`

## pseudocode

```c
ULONG __fastcall WPP_SF_(TRACEHANDLE a1, USHORT a2, const GUID *a3)
{
  return TraceMessage(a1, 0x2Bu, a3, a2, 0);
}

```

## disassembly

```asm
0x180011fec  sub     rsp, 38h
0x180011ff0  movzx   r9d, dx; MessageNumber
0x180011ff4  mov     edx, 2Bh ; '+'; MessageFlags
0x180011ff9  mov     [rsp+38h+var_18], 0
0x180012002  call    cs:__imp_TraceMessage
0x180012008  add     rsp, 38h
0x18001200c  retn
```
