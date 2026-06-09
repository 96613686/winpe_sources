# cxl::CriticalSection::IHaveLock(void)

- ea: `0x18000d57c`
- end: `0x18000d5a1`
- name: `?IHaveLock@CriticalSection@cxl@@QEBA_NXZ`
- size: `37`
- prototype: `bool __fastcall(cxl::CriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000cbfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d585`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d585`

## pseudocode

```c
bool __fastcall cxl::CriticalSection::IHaveLock(cxl::CriticalSection *this)
{
  return *((_QWORD *)this + 2) == GetCurrentThreadId();
}

```

## disassembly

```asm
0x18000d57c  push    rbx
0x18000d57e  sub     rsp, 20h
0x18000d582  mov     rbx, rcx
0x18000d585  call    cs:__imp_GetCurrentThreadId
0x18000d58c  nop     dword ptr [rax+rax+00h]
0x18000d591  mov     eax, eax
0x18000d593  cmp     [rbx+10h], rax
0x18000d597  setz    al
0x18000d59a  add     rsp, 20h
0x18000d59e  pop     rbx
0x18000d59f  retn
```
