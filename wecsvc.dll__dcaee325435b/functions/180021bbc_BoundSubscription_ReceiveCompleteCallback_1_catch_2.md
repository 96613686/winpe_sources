# _BoundSubscription::ReceiveCompleteCallback_::_1_::catch$2

- ea: `0x180021bbc`
- end: `0x180021bfc`
- name: `_BoundSubscription::ReceiveCompleteCallback_::_1_::catch$2`
- size: `64`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800025a4`
- `0x180011384`
- `0x180021bbc`

## pseudocode

```c
void __noreturn BoundSubscription::ReceiveCompleteCallback_::_1_::catch_2()
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58);
  }
  EcTerminateService();
}

```

## disassembly

```asm
0x180021bbc  mov     [rsp+arg_8], rdx
0x180021bc1  push    rbp
0x180021bc2  sub     rsp, 40h
0x180021bc6  mov     rbp, rdx
0x180021bc9  lea     rax, WPP_GLOBAL_Control
0x180021bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180021bd7  cmp     rcx, rax
0x180021bda  jz      short loc_180021BF6
0x180021bdc  test    byte ptr [rcx+1Ch], 10h
0x180021be0  jz      short loc_180021BF6
0x180021be2  cmp     byte ptr [rcx+19h], 2
0x180021be6  jb      short loc_180021BF6
0x180021be8  mov     edx, 3Ah ; ':'
0x180021bed  mov     rcx, [rcx+10h]
0x180021bf1  call    WPP_SF_
0x180021bf6  call    ?EcTerminateService@@YAXXZ; EcTerminateService(void)
```
