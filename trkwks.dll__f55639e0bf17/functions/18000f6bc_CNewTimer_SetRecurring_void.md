# CNewTimer::SetRecurring(void)

- ea: `0x18000f6bc`
- end: `0x18000f6fb`
- name: `?SetRecurring@CNewTimer@@QEAAXXZ`
- size: `63`
- prototype: `void __fastcall(CNewTimer *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x18000756c`
- `0x18000d0a4`
- `0x18000f510`

## callees

- `0x180010220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f6d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f6d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f6ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f6ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011cb5`

## pseudocode

```c
void __fastcall CNewTimer::SetRecurring(CNewTimer *this)
{
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 2) |= 4u;
  CNewTimer::SetTimer(this);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18000f6bc  mov     [rsp+arg_8], rbx
0x18000f6c1  mov     [rsp+arg_0], rcx
0x18000f6c6  push    rdi
0x18000f6c7  sub     rsp, 20h
0x18000f6cb  mov     rbx, rcx
0x18000f6ce  add     rcx, 10h; lpCriticalSection
0x18000f6d2  call    cs:__imp_EnterCriticalSection
0x18000f6d8  nop
0x18000f6d9  or      dword ptr [rbx+8], 4
0x18000f6dd  mov     rcx, rbx; this
0x18000f6e0  call    ?SetTimer@CNewTimer@@AEAAXXZ; CNewTimer::SetTimer(void)
0x18000f6e5  nop
0x18000f6e6  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000f6ea  call    cs:__imp_LeaveCriticalSection
0x18000f6f0  mov     rbx, [rsp+28h+arg_8]
0x18000f6f5  add     rsp, 20h
0x18000f6f9  pop     rdi
0x18000f6fa  retn
0x180011c9f  push    rbp
0x180011ca1  sub     rsp, 20h
0x180011ca5  mov     rbp, rdx
0x180011ca8  mov     rcx, [rbp+30h]
0x180011cac  add     rcx, 10h
0x180011cb0  add     rsp, 20h
0x180011cb4  pop     rbp
0x180011cb5  jmp     cs:__imp_LeaveCriticalSection
```
