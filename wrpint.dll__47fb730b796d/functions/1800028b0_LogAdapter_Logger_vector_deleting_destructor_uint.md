# LogAdapter::Logger::`vector deleting destructor'(uint)

- ea: `0x1800028b0`
- end: `0x18000291b`
- name: `??_ELogger@LogAdapter@@UEAAPEAXI@Z`
- size: `107`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x1800012f4`
- `0x1800028b0`
- `0x180004130`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x1800028e3`
- `ntdll!RtlDeleteCriticalSection` at `0x1800028e3`
- `ntdll!RtlRaiseStatus` at `0x1800028ef`
- `ntdll!RtlRaiseStatus` at `0x1800028ef`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall LogAdapter::Logger::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *this,
        char a2)
{
  int v4; // eax

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&LogAdapter::Logger::`vftable';
  LogAdapter::Logger::Close((LogAdapter::Logger *)this);
  if ( LOBYTE(this[105].DebugInfo) )
  {
    v4 = RtlDeleteCriticalSection(this + 104);
    if ( v4 < 0 )
      RtlRaiseStatus(v4);
    LOBYTE(this[105].DebugInfo) = 0;
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800028b0  mov     [rsp+arg_0], rbx
0x1800028b5  mov     [rsp+arg_8], rsi
0x1800028ba  push    rdi
0x1800028bb  sub     rsp, 20h
0x1800028bf  lea     rax, ??_7Logger@LogAdapter@@6B@; const LogAdapter::Logger::`vftable'
0x1800028c6  mov     esi, edx
0x1800028c8  mov     [rcx], rax
0x1800028cb  mov     rbx, rcx
0x1800028ce  call    ?Close@Logger@LogAdapter@@UEAAXXZ; LogAdapter::Logger::Close(void)
0x1800028d3  lea     rdi, [rbx+1040h]
0x1800028da  cmp     byte ptr [rdi+28h], 0
0x1800028de  jz      short loc_1800028FA
0x1800028e0  mov     rcx, rdi; CriticalSection
0x1800028e3  call    cs:__imp_RtlDeleteCriticalSection
0x1800028e9  test    eax, eax
0x1800028eb  jns     short loc_1800028F6
0x1800028ed  mov     ecx, eax; Status
0x1800028ef  call    cs:__imp_RtlRaiseStatus
0x1800028f5  int     3; Trap to Debugger
0x1800028f6  mov     byte ptr [rdi+28h], 0
0x1800028fa  test    sil, 1
0x1800028fe  jz      short loc_180002908
0x180002900  mov     rcx, rbx; Block
0x180002903  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002908  mov     rsi, [rsp+28h+arg_8]
0x18000290d  mov     rax, rbx
0x180002910  mov     rbx, [rsp+28h+arg_0]
0x180002915  add     rsp, 20h
0x180002919  pop     rdi
0x18000291a  retn
```
