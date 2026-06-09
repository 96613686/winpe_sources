# _dynamic_atexit_destructor_for__CWaitEventItem::g_WaitEventNotificationCS__

- ea: `0x180010360`
- end: `0x18001038b`
- name: `_dynamic_atexit_destructor_for__CWaitEventItem::g_WaitEventNotificationCS__`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010379`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010379`

## pseudocode

```c
void dynamic_atexit_destructor_for__CWaitEventItem::g_WaitEventNotificationCS__()
{
  if ( dword_180057630 == 1 )
  {
    DeleteCriticalSection(&CWaitEventItem::g_WaitEventNotificationCS);
    dword_180057630 = 0;
  }
}

```

## disassembly

```asm
0x180010360  sub     rsp, 28h
0x180010364  cmp     cs:dword_180057630, 1
0x18001036b  jz      short loc_180010372
0x18001036d  add     rsp, 28h
0x180010371  retn
0x180010372  lea     rcx, ?g_WaitEventNotificationCS@CWaitEventItem@@0VCCriticalSection@@A; lpCriticalSection
0x180010379  call    cs:__imp_DeleteCriticalSection
0x18001037f  mov     cs:dword_180057630, 0
0x180010389  jmp     short loc_18001036D
```
