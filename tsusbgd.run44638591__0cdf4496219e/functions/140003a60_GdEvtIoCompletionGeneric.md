# GdEvtIoCompletionGeneric

- ea: `0x140003a60`
- end: `0x140003aec`
- name: `GdEvtIoCompletionGeneric`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003a60`
- `0x140006370`

## pseudocode

```c
__int64 __fastcall GdEvtIoCompletionGeneric(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rax
  __int64 v6; // r8

  v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a1,
         off_140009018);
  v6 = *(unsigned int *)(a3 + 8);
  if ( (int)v6 < 0 )
    return ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
             WPP_MAIN_CB.Queue.ListEntry.Blink,
             a1,
             v6,
             v5);
  else
    return ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[132].Blink)(
             WPP_MAIN_CB.Queue.ListEntry.Blink,
             a1,
             v6,
             *(_QWORD *)(v5 + 1768));
}

```

## disassembly

```asm
0x140003a60  mov     [rsp+arg_0], rbx
0x140003a65  push    rdi
0x140003a66  sub     rsp, 30h
0x140003a6a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003a71  mov     rbx, r8
0x140003a74  mov     r8, cs:off_140009018
0x140003a7b  mov     rdi, rcx
0x140003a7e  mov     rdx, rcx
0x140003a81  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003a88  mov     rax, [rax+650h]
0x140003a8f  call    _guard_dispatch_icall
0x140003a94  mov     r8d, [rbx+8]
0x140003a98  mov     r9, rax
0x140003a9b  mov     rdx, rdi
0x140003a9e  test    r8d, r8d
0x140003aa1  js      short loc_140003AC6
0x140003aa3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140003aaa  mov     r9, [r9+6E8h]
0x140003ab1  mov     rax, [rcx+848h]
0x140003ab8  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003abf  call    _guard_dispatch_icall
0x140003ac4  jmp     short loc_140003AE0
0x140003ac6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003acd  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003ad4  mov     rax, [rax+838h]
0x140003adb  call    _guard_dispatch_icall
0x140003ae0  mov     rbx, [rsp+38h+arg_0]
0x140003ae5  add     rsp, 30h
0x140003ae9  pop     rdi
0x140003aea  retn
```
