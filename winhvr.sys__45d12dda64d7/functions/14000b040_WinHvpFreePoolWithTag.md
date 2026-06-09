# WinHvpFreePoolWithTag

- ea: `0x14000b040`
- end: `0x14000b056`
- name: `WinHvpFreePoolWithTag`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `40`
- callee_count: `0`
- tags: ``

## callers

- `0x1400026d0`
- `0x140002830`
- `0x1400042dc`
- `0x140005720`
- `0x140005920`
- `0x140005e40`
- `0x140007240`
- `0x140007274`
- `0x140007828`
- `0x140008e70`
- `0x14000b0f0`
- `0x14001b1a0`
- `0x14001b700`
- `0x14001b890`
- `0x14001ba40`
- `0x14001bfac`
- `0x14001d2cc`
- `0x14001d4e4`
- `0x14001d65c`
- `0x14001d8c8`
- `0x14001db10`
- `0x14001dd90`
- `0x14001e244`
- `0x14001e2a0`
- `0x14001e420`
- `0x14001f2d0`
- `0x14001ff34`
- `0x1400204a4`
- `0x140021864`
- `0x140021a10`
- `0x140022240`
- `0x1400225c0`
- `0x1400227a8`
- `0x140023350`
- `0x140023540`
- `0x140023fdc`
- `0x140024330`
- `0x1400254e0`
- `0x14002a40c`
- `0x14002a63c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b044`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b044`

## pseudocode

```c
void __fastcall WinHvpFreePoolWithTag(void *a1, ULONG a2)
{
  ExFreePoolWithTag(a1, a2);
}

```

## disassembly

```asm
0x14000b040  sub     rsp, 28h
0x14000b044  call    cs:__imp_ExFreePoolWithTag
0x14000b04b  nop     dword ptr [rax+rax+00h]
0x14000b050  add     rsp, 28h
0x14000b054  retn
```
