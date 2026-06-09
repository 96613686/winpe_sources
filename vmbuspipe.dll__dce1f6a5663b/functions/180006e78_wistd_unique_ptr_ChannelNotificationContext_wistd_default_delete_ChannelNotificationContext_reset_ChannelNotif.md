# wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::reset(ChannelNotificationContext *)

- ea: `0x180006e78`
- end: `0x180006ea4`
- name: `?reset@?$unique_ptr@UChannelNotificationContext@@U?$default_delete@UChannelNotificationContext@@@wistd@@@wistd@@QEAAXPEAUChannelNotificationContext@@@Z`
- size: `44`
- prototype: `void __fastcall(ChannelNotificationContext **, ChannelNotificationContext *)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003fe0`
- `0x18000416c`
- `0x180005940`
- `0x180006a10`
- `0x1800073d0`

## callees

- `0x180002504`
- `0x180004094`
- `0x180006e78`

## pseudocode

```c
void __fastcall wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::reset(
        ChannelNotificationContext **a1,
        ChannelNotificationContext *a2)
{
  ChannelNotificationContext *v2; // rbx

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
  {
    ChannelNotificationContext::~ChannelNotificationContext(v2);
    operator delete(v2, 0x2E0u);
  }
}

```

## disassembly

```asm
0x180006e78  push    rbx
0x180006e7a  sub     rsp, 20h
0x180006e7e  mov     rbx, [rcx]
0x180006e81  mov     [rcx], rdx
0x180006e84  test    rbx, rbx
0x180006e87  jz      short loc_180006E9E
0x180006e89  mov     rcx, rbx; this
0x180006e8c  call    ??1ChannelNotificationContext@@QEAA@XZ; ChannelNotificationContext::~ChannelNotificationContext(void)
0x180006e91  mov     edx, 2E0h; unsigned __int64
0x180006e96  mov     rcx, rbx; void *
0x180006e99  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006e9e  add     rsp, 20h
0x180006ea2  pop     rbx
0x180006ea3  retn
```
