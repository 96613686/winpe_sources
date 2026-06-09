# WPP_SF_D

- ea: `0x1800027ac`
- end: `0x1800027e3`
- name: `WPP_SF_D`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `38`
- callee_count: `0`
- tags: ``

## callers

- `0x18000262c`
- `0x1800027ec`
- `0x180002900`
- `0x180002a14`
- `0x1800036fc`
- `0x180003870`
- `0x180004510`
- `0x180004640`
- `0x180004780`
- `0x180004940`
- `0x180004b50`
- `0x180004cc0`
- `0x180004ec0`
- `0x180005220`
- `0x1800054c0`
- `0x1800057b0`
- `0x180005900`
- `0x180005a00`
- `0x180005b90`
- `0x180005f18`
- `0x18000632c`
- `0x1800066c4`
- `0x180006818`
- `0x180006b88`
- `0x180006fb8`
- `0x1800073c4`
- `0x1800075e0`
- `0x180007720`
- `0x180007aa0`
- `0x18000908c`
- `0x18000996c`
- `0x18000a820`
- `0x18000acec`
- `0x18000aea4`
- `0x18000b540`
- `0x18000b6b8`
- `0x18000b804`
- `0x18000b880`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800027d8`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800027d8`

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
0x1800027ac  mov     r11, rsp
0x1800027af  mov     [r11+20h], r9d
0x1800027b3  sub     rsp, 48h
0x1800027b7  mov     qword ptr [r11-18h], 0
0x1800027bf  lea     rax, [r11+20h]
0x1800027c3  movzx   r9d, dx; MessageNumber
0x1800027c7  mov     edx, 2Bh ; '+'; MessageFlags
0x1800027cc  mov     qword ptr [r11-20h], 4
0x1800027d4  mov     [r11-28h], rax
0x1800027d8  call    cs:__imp_TraceMessage
0x1800027de  add     rsp, 48h
0x1800027e2  retn
```
