# FxStubDriverUnloadCommon(void)

- ea: `0x14000bf04`
- end: `0x14000bf34`
- name: `?FxStubDriverUnloadCommon@@YAXXZ`
- size: `48`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000bf74`
- `0x14000c0f0`

## callees

- `0x14000c284`

## import_xrefs

- `WDFLDR!WdfVersionUnbind` at `0x14000bf22`
- `WDFLDR!WdfVersionUnbind` at `0x14000bf22`

## pseudocode

```c
void __fastcall FxStubDriverUnloadCommon(struct _WDF_BIND_INFO *a1)
{
  FxStubUnbindClasses(a1);
  WdfVersionUnbind(&DestinationString, &qword_14001C1A0, WdfDriverGlobals);
}

```

## disassembly

```asm
0x14000bf04  sub     rsp, 28h
0x14000bf08  call    ?FxStubUnbindClasses@@YAXPEAU_WDF_BIND_INFO@@@Z; FxStubUnbindClasses(_WDF_BIND_INFO *)
0x14000bf0d  mov     r8, cs:WdfDriverGlobals
0x14000bf14  lea     rdx, qword_14001C1A0
0x14000bf1b  lea     rcx, DestinationString
0x14000bf22  call    cs:__imp_WdfVersionUnbind
0x14000bf29  nop     dword ptr [rax+rax+00h]
0x14000bf2e  add     rsp, 28h
0x14000bf32  retn
```
