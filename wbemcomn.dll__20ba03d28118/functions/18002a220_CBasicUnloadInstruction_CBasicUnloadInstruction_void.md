# CBasicUnloadInstruction::~CBasicUnloadInstruction(void)

- ea: `0x18002a220`
- end: `0x18002a252`
- name: `??1CBasicUnloadInstruction@@UEAA@XZ`
- size: `50`
- prototype: `void __fastcall(CBasicUnloadInstruction *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180041400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a23b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a23b`

## pseudocode

```c
void __fastcall CBasicUnloadInstruction::~CBasicUnloadInstruction(CBasicUnloadInstruction *this)
{
  *(_QWORD *)this = &CBasicUnloadInstruction::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *(_QWORD *)this = &CTimerInstruction::`vftable';
}

```

## disassembly

```asm
0x18002a220  mov     [rsp+arg_0], rcx
0x18002a225  push    rbx
0x18002a226  sub     rsp, 20h
0x18002a22a  mov     rbx, rcx
0x18002a22d  lea     rax, ??_7CBasicUnloadInstruction@@6B@; const CBasicUnloadInstruction::`vftable'
0x18002a234  mov     [rcx], rax
0x18002a237  add     rcx, 18h; lpCriticalSection
0x18002a23b  call    cs:__imp_DeleteCriticalSection
0x18002a241  nop
0x18002a242  lea     rax, ??_7CTimerInstruction@@6B@; const CTimerInstruction::`vftable'
0x18002a249  mov     [rbx], rax
0x18002a24c  add     rsp, 20h
0x18002a250  pop     rbx
0x18002a251  retn
```
