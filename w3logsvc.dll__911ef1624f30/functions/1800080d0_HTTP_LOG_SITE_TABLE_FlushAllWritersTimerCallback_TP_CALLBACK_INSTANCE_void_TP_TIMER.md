# HTTP_LOG_SITE_TABLE::FlushAllWritersTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800080d0`
- end: `0x180008116`
- name: `?FlushAllWritersTimerCallback@HTTP_LOG_SITE_TABLE@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `70`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, struct _FILETIME *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800086a4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000810f`

## pseudocode

```c
void __fastcall HTTP_LOG_SITE_TABLE::FlushAllWritersTimerCallback(
        PTP_CALLBACK_INSTANCE Instance,
        struct _FILETIME *Context,
        PTP_TIMER Timer)
{
  HTTP_LOG_SITE_TABLE::Iterate(
    (HTTP_LOG_SITE_TABLE *)Context,
    (int (*)(struct HTTP_LOG_SITE_ENTRY *, struct HTTP_LOG_SITE_TABLE *))HTTP_LOG_SITE_TABLE::FlushWriter,
    1);
  SetThreadpoolTimer(Timer, Context + 139, 0, 0);
}

```

## disassembly

```asm
0x1800080d0  mov     [rsp+arg_0], rbx
0x1800080d5  push    rdi
0x1800080d6  sub     rsp, 20h
0x1800080da  mov     rbx, rdx
0x1800080dd  mov     rdi, r8
0x1800080e0  mov     rcx, rbx; this
0x1800080e3  lea     rdx, ?FlushWriter@HTTP_LOG_SITE_TABLE@@CAJPEAVHTTP_LOG_SITE_ENTRY@@PEAV1@@Z; int (*)(struct HTTP_LOG_SITE_ENTRY *, struct HTTP_LOG_SITE_TABLE *)
0x1800080ea  mov     r8d, 1; int
0x1800080f0  call    ?Iterate@HTTP_LOG_SITE_TABLE@@AEAAJP6AJPEAVHTTP_LOG_SITE_ENTRY@@PEAV1@@ZH@Z; HTTP_LOG_SITE_TABLE::Iterate(long (*)(HTTP_LOG_SITE_ENTRY *,HTTP_LOG_SITE_TABLE *),int)
0x1800080f5  lea     rdx, [rbx+458h]
0x1800080fc  xor     r9d, r9d
0x1800080ff  xor     r8d, r8d
0x180008102  mov     rcx, rdi
0x180008105  mov     rbx, [rsp+28h+arg_0]
0x18000810a  add     rsp, 20h
0x18000810e  pop     rdi
0x18000810f  jmp     cs:__imp_SetThreadpoolTimer
```
