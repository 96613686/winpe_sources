# CSsdpByebye::~CSsdpByebye(void)

- ea: `0x18000bfc0`
- end: `0x18000c038`
- name: `??1CSsdpByebye@@UEAA@XZ`
- size: `120`
- prototype: `void __fastcall(CSsdpByebye *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180031dc0`

## callees

- `0x18000ba2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bfd7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bfea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bfd7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bfea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c008`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c008`

## pseudocode

```c
void __fastcall CSsdpByebye::~CSsdpByebye(CSsdpByebye *this)
{
  *(_QWORD *)this = &CSsdpByebye::`vftable';
  free(*((void **)this + 2));
  free(*((void **)this + 21));
  *((_QWORD *)this + 21) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  *((_QWORD *)this + 4) = &CTimer<CSsdpByebye>::`vftable';
  CTimerBase::~CTimerBase((CSsdpByebye *)((char *)this + 32));
  *(_QWORD *)this = &CWorkItem::`vftable';
}

```

## disassembly

```asm
0x18000bfc0  push    rbx
0x18000bfc2  sub     rsp, 20h
0x18000bfc6  lea     rax, ??_7CSsdpByebye@@6B@; const CSsdpByebye::`vftable'
0x18000bfcd  mov     rbx, rcx
0x18000bfd0  mov     [rcx], rax
0x18000bfd3  mov     rcx, [rcx+10h]; Block
0x18000bfd7  call    cs:__imp_free
0x18000bfde  nop     dword ptr [rax+rax+00h]
0x18000bfe3  mov     rcx, [rbx+0A8h]; Block
0x18000bfea  call    cs:__imp_free
0x18000bff1  nop     dword ptr [rax+rax+00h]
0x18000bff6  lea     rcx, [rbx+80h]; lpCriticalSection
0x18000bffd  mov     qword ptr [rbx+0A8h], 0
0x18000c008  call    cs:__imp_DeleteCriticalSection
0x18000c00f  nop     dword ptr [rax+rax+00h]
0x18000c014  lea     rcx, [rbx+20h]; this
0x18000c018  lea     rax, ??_7?$CTimer@VCSsdpByebye@@@@6B@; const CTimer<CSsdpByebye>::`vftable'
0x18000c01f  mov     [rcx], rax
0x18000c022  call    ??1CTimerBase@@UEAA@XZ; CTimerBase::~CTimerBase(void)
0x18000c027  lea     rax, ??_7CWorkItem@@6B@; const CWorkItem::`vftable'
0x18000c02e  mov     [rbx], rax
0x18000c031  add     rsp, 20h
0x18000c035  pop     rbx
0x18000c036  retn
```
