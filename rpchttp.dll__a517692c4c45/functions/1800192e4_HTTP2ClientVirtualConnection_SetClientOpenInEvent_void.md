# HTTP2ClientVirtualConnection::SetClientOpenInEvent(void)

- ea: `0x1800192e4`
- end: `0x180019327`
- name: `?SetClientOpenInEvent@HTTP2ClientVirtualConnection@@AEAAXXZ`
- size: `67`
- prototype: `void __fastcall(HTTP2ClientVirtualConnection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012110`

## callees

- `0x1800192e4`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180019320`
- `ntdll!RtlEnterCriticalSection` at `0x1800192fb`
- `ntdll!RtlEnterCriticalSection` at `0x1800192fb`
- `KERNEL32!SetEvent` at `0x18001930d`
- `KERNEL32!SetEvent` at `0x18001930d`

## pseudocode

```c
void __fastcall HTTP2ClientVirtualConnection::SetClientOpenInEvent(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  v1 = this + 7;
  RtlEnterCriticalSection(this + 7);
  DebugInfo = this[10].DebugInfo;
  if ( DebugInfo )
    SetEvent(DebugInfo);
  RtlLeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x1800192e4  mov     [rsp+arg_0], rbx
0x1800192e9  push    rdi
0x1800192ea  sub     rsp, 20h
0x1800192ee  lea     rdi, [rcx+118h]
0x1800192f5  mov     rbx, rcx
0x1800192f8  mov     rcx, rdi; CriticalSection
0x1800192fb  call    cs:__imp_RtlEnterCriticalSection
0x180019301  mov     rcx, [rbx+190h]; hEvent
0x180019308  test    rcx, rcx
0x18001930b  jz      short loc_180019313
0x18001930d  call    cs:__imp_SetEvent
0x180019313  mov     rcx, rdi
0x180019316  mov     rbx, [rsp+28h+arg_0]
0x18001931b  add     rsp, 20h
0x18001931f  pop     rdi
0x180019320  jmp     cs:__imp_RtlLeaveCriticalSection
```
