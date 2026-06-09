# HTTP2ClientVirtualConnection::ReplaceInOpenEEInfo(tagExtendedErrorInfo *)

- ea: `0x180016e54`
- end: `0x180016e96`
- name: `?ReplaceInOpenEEInfo@HTTP2ClientVirtualConnection@@AEAAPEAUtagExtendedErrorInfo@@PEAU2@@Z`
- size: `66`
- prototype: `struct tagExtendedErrorInfo *__fastcall(HTTP2ClientVirtualConnection *__hidden this, struct tagExtendedErrorInfo *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006050`
- `0x180012110`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180016e84`
- `ntdll!RtlLeaveCriticalSection` at `0x180016e84`
- `ntdll!RtlEnterCriticalSection` at `0x180016e6d`
- `ntdll!RtlEnterCriticalSection` at `0x180016e6d`

## pseudocode

```c
struct tagExtendedErrorInfo *__fastcall HTTP2ClientVirtualConnection::ReplaceInOpenEEInfo(
        struct _RTL_CRITICAL_SECTION *this,
        struct tagExtendedErrorInfo *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  HANDLE LockSemaphore; // rbx

  v2 = this + 7;
  RtlEnterCriticalSection(this + 7);
  LockSemaphore = this[10].LockSemaphore;
  this[10].LockSemaphore = a2;
  RtlLeaveCriticalSection(v2);
  return (struct tagExtendedErrorInfo *)LockSemaphore;
}

```

## disassembly

```asm
0x180016e54  push    rbx
0x180016e56  push    rbp
0x180016e57  push    rsi
0x180016e58  push    rdi
0x180016e59  sub     rsp, 28h
0x180016e5d  lea     rdi, [rcx+118h]
0x180016e64  mov     rsi, rcx
0x180016e67  mov     rcx, rdi; CriticalSection
0x180016e6a  mov     rbp, rdx
0x180016e6d  call    cs:__imp_RtlEnterCriticalSection
0x180016e73  mov     rbx, [rsi+1A8h]
0x180016e7a  mov     rcx, rdi; CriticalSection
0x180016e7d  mov     [rsi+1A8h], rbp
0x180016e84  call    cs:__imp_RtlLeaveCriticalSection
0x180016e8a  mov     rax, rbx
0x180016e8d  add     rsp, 28h
0x180016e91  pop     rdi
0x180016e92  pop     rsi
0x180016e93  pop     rbp
0x180016e94  pop     rbx
0x180016e95  retn
```
