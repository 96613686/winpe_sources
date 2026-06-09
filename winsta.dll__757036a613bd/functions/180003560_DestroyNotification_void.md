# DestroyNotification(void)

- ea: `0x180003560`
- end: `0x1800035c9`
- name: `?DestroyNotification@@YAJXZ`
- size: `105`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003494`

## callees

- `0x180003560`
- `0x1800035d0`
- `0x180007890`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000359f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000359f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003589`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003589`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003570`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003570`

## pseudocode

```c
__int64 DestroyNotification(void)
{
  CWindowNotification::DestroyWindowNotificationGlobal();
  EnterCriticalSection(&CWaitEventItem::g_WaitEventNotificationCS);
  if ( CWaitEventItem::g_NumWaitEventNotification )
    _DbgPrintMessage(4, "g_NumWaitEventNotification is not zero (%d)", CWaitEventItem::g_NumWaitEventNotification);
  LeaveCriticalSection(&CWaitEventItem::g_WaitEventNotificationCS);
  if ( dword_180057630 == 1 )
  {
    DeleteCriticalSection(&CWaitEventItem::g_WaitEventNotificationCS);
    dword_180057630 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180003560  sub     rsp, 28h
0x180003564  call    ?DestroyWindowNotificationGlobal@CWindowNotification@@SAJXZ; CWindowNotification::DestroyWindowNotificationGlobal(void)
0x180003569  lea     rcx, ?g_WaitEventNotificationCS@CWaitEventItem@@0VCCriticalSection@@A; lpCriticalSection
0x180003570  call    cs:__imp_EnterCriticalSection
0x180003576  mov     r8d, cs:?g_NumWaitEventNotification@CWaitEventItem@@0JA; long CWaitEventItem::g_NumWaitEventNotification
0x18000357d  test    r8d, r8d
0x180003580  jnz     short loc_1800035B6
0x180003582  lea     rcx, ?g_WaitEventNotificationCS@CWaitEventItem@@0VCCriticalSection@@A; lpCriticalSection
0x180003589  call    cs:__imp_LeaveCriticalSection
0x18000358f  cmp     cs:dword_180057630, 1
0x180003596  jnz     short loc_1800035AF
0x180003598  lea     rcx, ?g_WaitEventNotificationCS@CWaitEventItem@@0VCCriticalSection@@A; lpCriticalSection
0x18000359f  call    cs:__imp_DeleteCriticalSection
0x1800035a5  mov     cs:dword_180057630, 0
0x1800035af  xor     eax, eax
0x1800035b1  add     rsp, 28h
0x1800035b5  retn
0x1800035b6  lea     rdx, aGNumwaiteventn; "g_NumWaitEventNotification is not zero "...
0x1800035bd  mov     ecx, 4; int
0x1800035c2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800035c7  jmp     short loc_180003582
```
