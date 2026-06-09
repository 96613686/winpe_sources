# GdEvtIoCompletionGetControllerName

- ea: `0x140003b00`
- end: `0x140003bc1`
- name: `GdEvtIoCompletionGetControllerName`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003b00`
- `0x140006370`

## pseudocode

```c
__int64 __fastcall GdEvtIoCompletionGetControllerName(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // eax
  __int64 v6; // r8
  _QWORD v8[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v9; // [rsp+68h] [rbp+20h] BYREF

  v9 = 0;
  v8[0] = 0;
  v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64, _QWORD *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a1,
         4,
         v8,
         &v9);
  v6 = (unsigned int)v5;
  if ( v5 < 0 )
    return ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
             WPP_MAIN_CB.Queue.ListEntry.Blink,
             a1,
             v6);
  v6 = *(unsigned int *)(a3 + 8);
  if ( (_DWORD)v6 == -1073741789 )
  {
    v6 = 2147483653LL;
    return ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
             WPP_MAIN_CB.Queue.ListEntry.Blink,
             a1,
             v6);
  }
  if ( (int)v6 < 0 )
    return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
             WPP_MAIN_CB.Queue.ListEntry.Blink,
             a1,
             v6);
  return ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[132].Blink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           a1,
           v6,
           v9);
}

```

## disassembly

```asm
0x140003b00  mov     r11, rsp
0x140003b03  mov     [r11+8], rbx
0x140003b07  mov     [r11+20h], r9
0x140003b0b  push    rdi
0x140003b0c  sub     rsp, 40h
0x140003b10  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003b17  lea     r9, [r11-18h]
0x140003b1b  mov     rbx, rcx
0x140003b1e  mov     qword ptr [r11+20h], 0
0x140003b26  lea     rcx, [r11+20h]
0x140003b2a  mov     qword ptr [r11-18h], 0
0x140003b32  mov     rdi, r8
0x140003b35  mov     [r11-28h], rcx
0x140003b39  mov     rax, [rax+870h]
0x140003b40  mov     r8d, 4
0x140003b46  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003b4d  mov     rdx, rbx
0x140003b50  call    _guard_dispatch_icall
0x140003b55  mov     r8d, eax
0x140003b58  test    eax, eax
0x140003b5a  js      short loc_140003B6F
0x140003b5c  mov     r8d, [rdi+8]
0x140003b60  cmp     r8d, 0C0000023h
0x140003b67  jnz     short loc_140003B98
0x140003b69  mov     r8d, 80000005h
0x140003b6f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003b76  mov     rdx, rbx
0x140003b79  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003b80  mov     rax, [rax+838h]
0x140003b87  call    _guard_dispatch_icall
0x140003b8c  mov     rbx, [rsp+48h+arg_0]
0x140003b91  add     rsp, 40h
0x140003b95  pop     rdi
0x140003b96  retn
0x140003b98  test    r8d, r8d
0x140003b9b  js      short loc_140003B6F
0x140003b9d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003ba4  mov     rdx, rbx
0x140003ba7  mov     r9, [rsp+48h+arg_18]
0x140003bac  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003bb3  mov     rax, [rax+848h]
0x140003bba  call    _guard_dispatch_icall
0x140003bbf  jmp     short loc_140003B8C
```
