# CPrivateNotificationWindow::CPrivateNotificationWindow(void)

- ea: `0x1800187e8`
- end: `0x18001882e`
- name: `??0CPrivateNotificationWindow@@IEAA@XZ`
- size: `70`
- prototype: `CPrivateNotificationWindow *__fastcall(CPrivateNotificationWindow *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000bcb8`
- `0x18000bd74`
- `0x180018884`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001881f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001881f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001880a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001880a`

## pseudocode

```c
CPrivateNotificationWindow *__fastcall CPrivateNotificationWindow::CPrivateNotificationWindow(
        CPrivateNotificationWindow *this)
{
  DWORD CurrentThreadId; // eax

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CPrivateNotificationWindow::`vftable';
  *((_QWORD *)this + 2) = 0;
  CurrentThreadId = GetCurrentThreadId();
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 6) = CurrentThreadId;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 1);
  return this;
}

```

## disassembly

```asm
0x1800187e8  push    rbx
0x1800187ea  sub     rsp, 20h
0x1800187ee  lea     rax, ??_7CPrivateNotificationWindow@@6B@; const CPrivateNotificationWindow::`vftable'
0x1800187f5  mov     dword ptr [rcx+8], 1
0x1800187fc  mov     [rcx], rax
0x1800187ff  mov     rbx, rcx
0x180018802  mov     qword ptr [rcx+10h], 0
0x18001880a  call    cs:__imp_GetCurrentThreadId
0x180018810  lea     rcx, [rbx+28h]; lpCriticalSection
0x180018814  mov     qword ptr [rbx+20h], 0
0x18001881c  mov     [rbx+18h], eax
0x18001881f  call    cs:__imp_InitializeCriticalSection
0x180018825  mov     rax, rbx
0x180018828  add     rsp, 20h
0x18001882c  pop     rbx
0x18001882d  retn
```
