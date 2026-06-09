# GdEvtIoCompletionQueryDeviceText

- ea: `0x140003bd0`
- end: `0x140003be2`
- name: `GdEvtIoCompletionQueryDeviceText`
- size: `18`
- prototype: `void __fastcall(struct WDFREQUEST__ *, __int64, struct _WDF_REQUEST_COMPLETION_PARAMS *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001b50`

## pseudocode

```c
void __fastcall GdEvtIoCompletionQueryDeviceText(
        struct WDFREQUEST__ *a1,
        __int64 a2,
        struct _WDF_REQUEST_COMPLETION_PARAMS *a3)
{
  CGenericUSB::IoCtlCompletionQueryDeviceText((CGenericUSB *)a1, a1, a3);
}

```

## disassembly

```asm
0x140003bd0  sub     rsp, 28h
0x140003bd4  mov     rdx, rcx; struct WDFREQUEST__ *
0x140003bd7  call    ?IoCtlCompletionQueryDeviceText@CGenericUSB@@QEAAXPEAUWDFREQUEST__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@@Z; CGenericUSB::IoCtlCompletionQueryDeviceText(WDFREQUEST__ *,_WDF_REQUEST_COMPLETION_PARAMS *)
0x140003bdc  add     rsp, 28h
0x140003be0  retn
```
