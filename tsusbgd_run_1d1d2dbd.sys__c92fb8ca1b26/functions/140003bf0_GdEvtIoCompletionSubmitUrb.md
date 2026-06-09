# GdEvtIoCompletionSubmitUrb

- ea: `0x140003bf0`
- end: `0x140003c05`
- name: `GdEvtIoCompletionSubmitUrb`
- size: `21`
- prototype: `void __fastcall(struct WDFREQUEST__ *, __int64, struct _WDF_REQUEST_COMPLETION_PARAMS *, CGenericUSB *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001d10`

## pseudocode

```c
void __fastcall GdEvtIoCompletionSubmitUrb(
        struct WDFREQUEST__ *a1,
        __int64 a2,
        struct _WDF_REQUEST_COMPLETION_PARAMS *a3,
        CGenericUSB *a4)
{
  CGenericUSB::IoCtlCompletionSubmitUrb(a4, a1, a3);
}

```

## disassembly

```asm
0x140003bf0  sub     rsp, 28h
0x140003bf4  mov     rdx, rcx; struct WDFREQUEST__ *
0x140003bf7  mov     rcx, r9; this
0x140003bfa  call    ?IoCtlCompletionSubmitUrb@CGenericUSB@@QEAAXPEAUWDFREQUEST__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@@Z; CGenericUSB::IoCtlCompletionSubmitUrb(WDFREQUEST__ *,_WDF_REQUEST_COMPLETION_PARAMS *)
0x140003bff  add     rsp, 28h
0x140003c03  retn
```
