# _dynamic_atexit_destructor_for__CWaitEventItem::g_WaitEventNotificationCS__

- ea: `0x180010db0`
- end: `0x180010de2`
- name: `_dynamic_atexit_destructor_for__CWaitEventItem::g_WaitEventNotificationCS__`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010db0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010dca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010dca`

## pseudocode

```c
void dynamic_atexit_destructor_for__CWaitEventItem::g_WaitEventNotificationCS__()
{
  if ( dword_18005A630 == 1 )
  {
    DeleteCriticalSection(&CWaitEventItem::g_WaitEventNotificationCS);
    dword_18005A630 = 0;
  }
}

```

## disassembly

```asm
0x180010db0  sub     rsp, 28h
0x180010db4  cmp     cs:dword_18005A630, 1
0x180010dbb  jz      short loc_180010DC3
0x180010dbd  add     rsp, 28h
0x180010dc1  retn
0x180010dc3  lea     rcx, ?g_WaitEventNotificationCS@CWaitEventItem@@0VCCriticalSection@@A; lpCriticalSection
0x180010dca  call    cs:__imp_DeleteCriticalSection
0x180010dd1  nop     dword ptr [rax+rax+00h]
0x180010dd6  mov     cs:dword_18005A630, 0
0x180010de0  jmp     short loc_180010DBD
```
