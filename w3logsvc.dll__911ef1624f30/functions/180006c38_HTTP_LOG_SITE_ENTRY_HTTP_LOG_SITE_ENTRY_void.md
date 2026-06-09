# HTTP_LOG_SITE_ENTRY::~HTTP_LOG_SITE_ENTRY(void)

- ea: `0x180006c38`
- end: `0x180006c60`
- name: `??1HTTP_LOG_SITE_ENTRY@@UEAA@XZ`
- size: `40`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006c70`

## callees

- `0x180007c8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006c59`

## pseudocode

```c
void __fastcall HTTP_LOG_SITE_ENTRY::~HTTP_LOG_SITE_ENTRY(struct _RTL_CRITICAL_SECTION *this)
{
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&HTTP_LOG_SITE_ENTRY::`vftable';
  HTTP_LOG_SITE_ENTRY::Terminate((HTTP_LOG_SITE_ENTRY *)this);
  DeleteCriticalSection(this + 1);
}

```

## disassembly

```asm
0x180006c38  push    rbx
0x180006c3a  sub     rsp, 20h
0x180006c3e  lea     rax, ??_7HTTP_LOG_SITE_ENTRY@@6B@; const HTTP_LOG_SITE_ENTRY::`vftable'
0x180006c45  mov     rbx, rcx
0x180006c48  mov     [rcx], rax
0x180006c4b  call    ?Terminate@HTTP_LOG_SITE_ENTRY@@QEAAXXZ; HTTP_LOG_SITE_ENTRY::Terminate(void)
0x180006c50  lea     rcx, [rbx+28h]
0x180006c54  add     rsp, 20h
0x180006c58  pop     rbx
0x180006c59  jmp     cs:__imp_DeleteCriticalSection
```
