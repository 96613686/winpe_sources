# cxl::CriticalSection::IHaveLock(void)

- ea: `0x18000d194`
- end: `0x18000d1b2`
- name: `?IHaveLock@CriticalSection@cxl@@QEBA_NXZ`
- size: `30`
- prototype: `bool __fastcall(cxl::CriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c858`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d19d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d19d`

## pseudocode

```c
bool __fastcall cxl::CriticalSection::IHaveLock(cxl::CriticalSection *this)
{
  return *((_QWORD *)this + 2) == GetCurrentThreadId();
}

```

## disassembly

```asm
0x18000d194  push    rbx
0x18000d196  sub     rsp, 20h
0x18000d19a  mov     rbx, rcx
0x18000d19d  call    cs:__imp_GetCurrentThreadId
0x18000d1a3  mov     eax, eax
0x18000d1a5  cmp     [rbx+10h], rax
0x18000d1a9  setz    al
0x18000d1ac  add     rsp, 20h
0x18000d1b0  pop     rbx
0x18000d1b1  retn
```
