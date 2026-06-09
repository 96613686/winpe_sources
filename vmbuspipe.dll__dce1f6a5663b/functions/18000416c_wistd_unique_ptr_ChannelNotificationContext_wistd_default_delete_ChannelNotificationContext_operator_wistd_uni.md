# wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::operator=(wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>> &&)

- ea: `0x18000416c`
- end: `0x180004190`
- name: `??4?$unique_ptr@UChannelNotificationContext@@U?$default_delete@UChannelNotificationContext@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `36`
- prototype: `ChannelNotificationContext **__fastcall(ChannelNotificationContext **, ChannelNotificationContext **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005940`
- `0x180006a10`
- `0x1800073d0`

## callees

- `0x180006e78`

## pseudocode

```c
ChannelNotificationContext **__fastcall wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::operator=(
        ChannelNotificationContext **a1,
        ChannelNotificationContext **a2)
{
  ChannelNotificationContext *v4; // rdx

  v4 = *a2;
  *a2 = 0;
  wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::reset(a1, v4);
  return a1;
}

```

## disassembly

```asm
0x18000416c  push    rbx
0x18000416e  sub     rsp, 20h
0x180004172  mov     rax, rdx
0x180004175  mov     rbx, rcx
0x180004178  mov     rdx, [rdx]
0x18000417b  mov     qword ptr [rax], 0
0x180004182  call    ?reset@?$unique_ptr@UChannelNotificationContext@@U?$default_delete@UChannelNotificationContext@@@wistd@@@wistd@@QEAAXPEAUChannelNotificationContext@@@Z; wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::reset(ChannelNotificationContext *)
0x180004187  mov     rax, rbx
0x18000418a  add     rsp, 20h
0x18000418e  pop     rbx
0x18000418f  retn
```
