# FcEvtDeviceFileCreate

- ea: `0x140009440`
- end: `0x14000948e`
- name: `FcEvtDeviceFileCreate`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140006efc`
- `0x14000aa30`

## pseudocode

```c
void __fastcall FcEvtDeviceFileCreate(__int64 a1, struct WDFREQUEST__ *a2, struct WDFFILEOBJECT__ *a3)
{
  CUsbFilterControl *v5; // rax

  v5 = (CUsbFilterControl *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                              WPP_MAIN_CB.Queue.ListEntry.Blink,
                              a1,
                              off_14000F068);
  CUsbFilterControl::EvtDeviceFileCreate(v5, a2, a3);
}

```

## disassembly

```asm
0x140009440  mov     [rsp+arg_0], rbx
0x140009445  push    rdi
0x140009446  sub     rsp, 20h
0x14000944a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140009451  mov     rdi, rdx
0x140009454  mov     rbx, r8
0x140009457  mov     rdx, rcx
0x14000945a  mov     r8, cs:off_14000F068
0x140009461  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140009468  mov     rax, [rax+650h]
0x14000946f  call    _guard_dispatch_icall
0x140009474  mov     r8, rbx; struct WDFFILEOBJECT__ *
0x140009477  mov     rdx, rdi; struct WDFREQUEST__ *
0x14000947a  mov     rcx, rax; this
0x14000947d  call    ?EvtDeviceFileCreate@CUsbFilterControl@@QEAAXPEAUWDFREQUEST__@@PEAUWDFFILEOBJECT__@@@Z; CUsbFilterControl::EvtDeviceFileCreate(WDFREQUEST__ *,WDFFILEOBJECT__ *)
0x140009482  mov     rbx, [rsp+28h+arg_0]
0x140009487  add     rsp, 20h
0x14000948b  pop     rdi
0x14000948c  retn
```
