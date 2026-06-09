# CSsdpByebye::~CSsdpByebye(void)

- ea: `0x18000a64c`
- end: `0x18000a6b1`
- name: `??1CSsdpByebye@@UEAA@XZ`
- size: `101`
- prototype: `void __fastcall(CSsdpByebye *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002fac0`

## callees

- `0x18000a358`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a663`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a670`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a663`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a670`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a688`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a688`

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
0x18000a64c  push    rbx
0x18000a64e  sub     rsp, 20h
0x18000a652  lea     rax, ??_7CSsdpByebye@@6B@; const CSsdpByebye::`vftable'
0x18000a659  mov     rbx, rcx
0x18000a65c  mov     [rcx], rax
0x18000a65f  mov     rcx, [rcx+10h]; Block
0x18000a663  call    cs:__imp_free
0x18000a669  mov     rcx, [rbx+0A8h]; Block
0x18000a670  call    cs:__imp_free
0x18000a676  lea     rcx, [rbx+80h]; lpCriticalSection
0x18000a67d  mov     qword ptr [rbx+0A8h], 0
0x18000a688  call    cs:__imp_DeleteCriticalSection
0x18000a68e  lea     rcx, [rbx+20h]; this
0x18000a692  lea     rax, ??_7?$CTimer@VCSsdpByebye@@@@6B@; const CTimer<CSsdpByebye>::`vftable'
0x18000a699  mov     [rcx], rax
0x18000a69c  call    ??1CTimerBase@@UEAA@XZ; CTimerBase::~CTimerBase(void)
0x18000a6a1  lea     rax, ??_7CWorkItem@@6B@; const CWorkItem::`vftable'
0x18000a6a8  mov     [rbx], rax
0x18000a6ab  add     rsp, 20h
0x18000a6af  pop     rbx
0x18000a6b0  retn
```
