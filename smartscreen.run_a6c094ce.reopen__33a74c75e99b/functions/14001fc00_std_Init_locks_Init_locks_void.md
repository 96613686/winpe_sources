# std::_Init_locks::~_Init_locks(void)

- ea: `0x14001fc00`
- end: `0x14001fc43`
- name: `??1_Init_locks@std@@QEAA@XZ`
- size: `67`
- prototype: `void __fastcall(std::_Init_locks *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400697a0`
- `0x140069880`

## callees

- `0x14001fc00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001fc20`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001fc20`

## pseudocode

```c
void __fastcall std::_Init_locks::~_Init_locks(std::_Init_locks *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  if ( _InterlockedDecrement(&dword_140087AE0) < 0 )
  {
    v1 = &CriticalSection;
    do
      DeleteCriticalSection(v1++);
    while ( v1 != (struct _RTL_CRITICAL_SECTION *)&Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<2>>::isInitialized );
  }
}

```

## disassembly

```asm
0x14001fc00  push    rbx
0x14001fc02  sub     rsp, 20h
0x14001fc06  or      eax, 0FFFFFFFFh
0x14001fc09  lock xadd cs:dword_140087AE0, eax
0x14001fc11  cmp     eax, 1
0x14001fc14  jns     short loc_14001FC3C
0x14001fc16  lea     rbx, CriticalSection
0x14001fc1d  mov     rcx, rbx; lpCriticalSection
0x14001fc20  call    cs:__imp_DeleteCriticalSection
0x14001fc27  nop     dword ptr [rax+rax+00h]
0x14001fc2c  lea     rax, ?isInitialized@?$Module@$00V?$DefaultModule@$01@Details@WRL@Microsoft@@@WRL@Microsoft@@0_NA; bool Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<2>>::isInitialized
0x14001fc33  add     rbx, 28h ; '('
0x14001fc37  cmp     rbx, rax
0x14001fc3a  jnz     short loc_14001FC1D
0x14001fc3c  add     rsp, 20h
0x14001fc40  pop     rbx
0x14001fc41  retn
```
