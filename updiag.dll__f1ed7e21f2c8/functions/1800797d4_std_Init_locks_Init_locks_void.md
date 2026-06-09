# std::_Init_locks::~_Init_locks(void)

- ea: `0x1800797d4`
- end: `0x180079810`
- name: `??1_Init_locks@std@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(std::_Init_locks *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18009da30`
- `0x18009dac0`
- `0x18009dc00`
- `0x18009dc20`

## callees

- `0x1800797d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800797f4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800797f4`

## pseudocode

```c
void __fastcall std::_Init_locks::~_Init_locks(std::_Init_locks *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  if ( _InterlockedDecrement(&dword_180182590) < 0 )
  {
    v1 = &CriticalSection;
    do
      DeleteCriticalSection(v1++);
    while ( v1 != (struct _RTL_CRITICAL_SECTION *)&std::num_get<wchar_t,std::istreambuf_iterator<wchar_t>>::id );
  }
}

```

## disassembly

```asm
0x1800797d4  push    rbx
0x1800797d6  sub     rsp, 20h
0x1800797da  or      eax, 0FFFFFFFFh
0x1800797dd  lock xadd cs:dword_180182590, eax
0x1800797e5  cmp     eax, 1
0x1800797e8  jns     short loc_18007980A
0x1800797ea  lea     rbx, CriticalSection
0x1800797f1  mov     rcx, rbx; lpCriticalSection
0x1800797f4  call    cs:__imp_DeleteCriticalSection
0x1800797fa  lea     rax, ?id@?$num_get@_WV?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@2V0locale@2@A; std::locale::id std::num_get<wchar_t,std::istreambuf_iterator<wchar_t>>::id
0x180079801  add     rbx, 28h ; '('
0x180079805  cmp     rbx, rax
0x180079808  jnz     short loc_1800797F1
0x18007980a  add     rsp, 20h
0x18007980e  pop     rbx
0x18007980f  retn
```
