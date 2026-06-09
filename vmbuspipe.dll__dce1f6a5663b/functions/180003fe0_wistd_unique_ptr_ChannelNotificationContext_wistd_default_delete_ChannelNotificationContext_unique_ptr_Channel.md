# wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::~unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>(void)

- ea: `0x180003fe0`
- end: `0x180003fe7`
- name: `??1?$unique_ptr@UChannelNotificationContext@@U?$default_delete@UChannelNotificationContext@@@wistd@@@wistd@@QEAA@XZ`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004094`
- `0x180007b1c`

## callees

- `0x180006e78`

## pseudocode

```c
void __fastcall wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::~unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>(
        ChannelNotificationContext **a1)
{
  wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::reset(a1, 0);
}

```

## disassembly

```asm
0x180003fe0  xor     edx, edx
0x180003fe2  jmp     ?reset@?$unique_ptr@UChannelNotificationContext@@U?$default_delete@UChannelNotificationContext@@@wistd@@@wistd@@QEAAXPEAUChannelNotificationContext@@@Z; wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::reset(ChannelNotificationContext *)
```
