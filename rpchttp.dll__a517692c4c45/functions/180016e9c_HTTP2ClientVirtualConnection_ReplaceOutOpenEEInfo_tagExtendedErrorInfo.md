# HTTP2ClientVirtualConnection::ReplaceOutOpenEEInfo(tagExtendedErrorInfo *)

- ea: `0x180016e9c`
- end: `0x180016ede`
- name: `?ReplaceOutOpenEEInfo@HTTP2ClientVirtualConnection@@AEAAPEAUtagExtendedErrorInfo@@PEAU2@@Z`
- size: `66`
- prototype: `struct tagExtendedErrorInfo *__fastcall(HTTP2ClientVirtualConnection *__hidden this, struct tagExtendedErrorInfo *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006050`
- `0x180012110`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180016ecc`
- `ntdll!RtlLeaveCriticalSection` at `0x180016ecc`
- `ntdll!RtlEnterCriticalSection` at `0x180016eb5`
- `ntdll!RtlEnterCriticalSection` at `0x180016eb5`

## pseudocode

```c
struct tagExtendedErrorInfo *__fastcall HTTP2ClientVirtualConnection::ReplaceOutOpenEEInfo(
        HTTP2ClientVirtualConnection *this,
        struct tagExtendedErrorInfo *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v5; // rbx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 328);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 328));
  v5 = *((_QWORD *)this + 55);
  *((_QWORD *)this + 55) = a2;
  RtlLeaveCriticalSection(v2);
  return (struct tagExtendedErrorInfo *)v5;
}

```

## disassembly

```asm
0x180016e9c  push    rbx
0x180016e9e  push    rbp
0x180016e9f  push    rsi
0x180016ea0  push    rdi
0x180016ea1  sub     rsp, 28h
0x180016ea5  lea     rdi, [rcx+148h]
0x180016eac  mov     rsi, rcx
0x180016eaf  mov     rcx, rdi; CriticalSection
0x180016eb2  mov     rbp, rdx
0x180016eb5  call    cs:__imp_RtlEnterCriticalSection
0x180016ebb  mov     rbx, [rsi+1B8h]
0x180016ec2  mov     rcx, rdi; CriticalSection
0x180016ec5  mov     [rsi+1B8h], rbp
0x180016ecc  call    cs:__imp_RtlLeaveCriticalSection
0x180016ed2  mov     rax, rbx
0x180016ed5  add     rsp, 28h
0x180016ed9  pop     rdi
0x180016eda  pop     rsi
0x180016edb  pop     rbp
0x180016edc  pop     rbx
0x180016edd  retn
```
