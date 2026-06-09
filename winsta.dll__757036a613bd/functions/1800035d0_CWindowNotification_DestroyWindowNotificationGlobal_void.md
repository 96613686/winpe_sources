# CWindowNotification::DestroyWindowNotificationGlobal(void)

- ea: `0x1800035d0`
- end: `0x180003634`
- name: `?DestroyWindowNotificationGlobal@CWindowNotification@@SAJXZ`
- size: `100`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003560`

## callees

- `0x1800035d0`
- `0x180007890`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000360a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000360a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800035f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800035f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800035db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800035db`

## pseudocode

```c
__int64 CWindowNotification::DestroyWindowNotificationGlobal(void)
{
  EnterCriticalSection(&CWindowNotification::g_WindowNotificationCS);
  if ( CWindowNotification::g_NumNotifications )
    _DbgPrintMessage(4, "CWindowNotification::g_NumNotifications is %d", CWindowNotification::g_NumNotifications);
  LeaveCriticalSection(&CWindowNotification::g_WindowNotificationCS);
  if ( dword_180057660 == 1 )
  {
    DeleteCriticalSection(&CWindowNotification::g_WindowNotificationCS);
    dword_180057660 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800035d0  sub     rsp, 28h
0x1800035d4  lea     rcx, ?g_WindowNotificationCS@CWindowNotification@@2VCCriticalSection@@A; lpCriticalSection
0x1800035db  call    cs:__imp_EnterCriticalSection
0x1800035e1  mov     r8d, cs:?g_NumNotifications@CWindowNotification@@2JA; long CWindowNotification::g_NumNotifications
0x1800035e8  test    r8d, r8d
0x1800035eb  jnz     short loc_180003621
0x1800035ed  lea     rcx, ?g_WindowNotificationCS@CWindowNotification@@2VCCriticalSection@@A; lpCriticalSection
0x1800035f4  call    cs:__imp_LeaveCriticalSection
0x1800035fa  cmp     cs:dword_180057660, 1
0x180003601  jnz     short loc_18000361A
0x180003603  lea     rcx, ?g_WindowNotificationCS@CWindowNotification@@2VCCriticalSection@@A; lpCriticalSection
0x18000360a  call    cs:__imp_DeleteCriticalSection
0x180003610  mov     cs:dword_180057660, 0
0x18000361a  xor     eax, eax
0x18000361c  add     rsp, 28h
0x180003620  retn
0x180003621  lea     rdx, aCwindownotific; "CWindowNotification::g_NumNotifications"...
0x180003628  mov     ecx, 4; int
0x18000362d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003632  jmp     short loc_1800035ED
```
