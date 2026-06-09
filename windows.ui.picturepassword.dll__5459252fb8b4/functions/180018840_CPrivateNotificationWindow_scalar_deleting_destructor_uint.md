# CPrivateNotificationWindow::`scalar deleting destructor'(uint)

- ea: `0x180018840`
- end: `0x18001887e`
- name: `??_GCPrivateNotificationWindow@@MEAAPEAXI@Z`
- size: `62`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002bb0`
- `0x180018840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001885d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001885d`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall CPrivateNotificationWindow::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *this,
        char a2)
{
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CPrivateNotificationWindow::`vftable';
  DeleteCriticalSection(this + 1);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180018840  mov     [rsp+arg_0], rbx
0x180018845  push    rdi
0x180018846  sub     rsp, 20h
0x18001884a  lea     rax, ??_7CPrivateNotificationWindow@@6B@; const CPrivateNotificationWindow::`vftable'
0x180018851  mov     rdi, rcx
0x180018854  mov     [rcx], rax
0x180018857  mov     ebx, edx
0x180018859  add     rcx, 28h ; '('; lpCriticalSection
0x18001885d  call    cs:__imp_DeleteCriticalSection
0x180018863  test    bl, 1
0x180018866  jz      short loc_180018870
0x180018868  mov     rcx, rdi; Block
0x18001886b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018870  mov     rbx, [rsp+28h+arg_0]
0x180018875  mov     rax, rdi
0x180018878  add     rsp, 20h
0x18001887c  pop     rdi
0x18001887d  retn
```
