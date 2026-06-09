# GdEvtDeviceFileCreate

- ea: `0x14000c330`
- end: `0x14000c37e`
- name: `GdEvtDeviceFileCreate`
- size: `78`
- prototype: `void __fastcall(__int64, struct WDFREQUEST__ *, struct WDFFILEOBJECT__ *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001308`
- `0x140006370`

## pseudocode

```c
void __fastcall GdEvtDeviceFileCreate(__int64 a1, struct WDFREQUEST__ *a2, struct WDFFILEOBJECT__ *a3)
{
  PEPROCESS *v5; // rax

  v5 = (PEPROCESS *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, void *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                      WPP_MAIN_CB.Queue.ListEntry.Blink,
                      a1,
                      off_140009040);
  CGenericUSB::EvtDeviceFileCreate(v5, a2, a3);
}

```

## disassembly

```asm
0x14000c330  mov     [rsp+arg_0], rbx
0x14000c335  push    rdi
0x14000c336  sub     rsp, 20h
0x14000c33a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000c341  mov     rdi, rdx
0x14000c344  mov     rbx, r8
0x14000c347  mov     rdx, rcx
0x14000c34a  mov     r8, cs:off_140009040
0x14000c351  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000c358  mov     rax, [rax+650h]
0x14000c35f  call    _guard_dispatch_icall
0x14000c364  mov     r8, rbx; struct WDFFILEOBJECT__ *
0x14000c367  mov     rdx, rdi; struct WDFREQUEST__ *
0x14000c36a  mov     rcx, rax; this
0x14000c36d  call    ?EvtDeviceFileCreate@CGenericUSB@@QEAAXPEAUWDFREQUEST__@@PEAUWDFFILEOBJECT__@@@Z; CGenericUSB::EvtDeviceFileCreate(WDFREQUEST__ *,WDFFILEOBJECT__ *)
0x14000c372  mov     rbx, [rsp+28h+arg_0]
0x14000c377  add     rsp, 20h
0x14000c37b  pop     rdi
0x14000c37c  retn
```
