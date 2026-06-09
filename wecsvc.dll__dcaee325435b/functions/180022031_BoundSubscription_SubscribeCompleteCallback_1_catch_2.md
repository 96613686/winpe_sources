# _BoundSubscription::SubscribeCompleteCallback_::_1_::catch$2

- ea: `0x180022031`
- end: `0x180022071`
- name: `_BoundSubscription::SubscribeCompleteCallback_::_1_::catch$2`
- size: `64`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800025a4`
- `0x180011384`
- `0x180022031`

## pseudocode

```c
void __noreturn BoundSubscription::SubscribeCompleteCallback_::_1_::catch_2()
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54);
  }
  EcTerminateService();
}

```

## disassembly

```asm
0x180022031  mov     [rsp+arg_8], rdx
0x180022036  push    rbp
0x180022037  sub     rsp, 40h
0x18002203b  mov     rbp, rdx
0x18002203e  lea     rax, WPP_GLOBAL_Control
0x180022045  mov     rcx, cs:WPP_GLOBAL_Control
0x18002204c  cmp     rcx, rax
0x18002204f  jz      short loc_18002206B
0x180022051  test    byte ptr [rcx+1Ch], 10h
0x180022055  jz      short loc_18002206B
0x180022057  cmp     byte ptr [rcx+19h], 2
0x18002205b  jb      short loc_18002206B
0x18002205d  mov     edx, 36h ; '6'
0x180022062  mov     rcx, [rcx+10h]
0x180022066  call    WPP_SF_
0x18002206b  call    ?EcTerminateService@@YAXXZ; EcTerminateService(void)
```
