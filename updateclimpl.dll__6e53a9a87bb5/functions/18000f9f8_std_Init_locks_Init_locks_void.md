# std::_Init_locks::~_Init_locks(void)

- ea: `0x18000f9f8`
- end: `0x18000fa34`
- name: `??1_Init_locks@std@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(std::_Init_locks *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180016270`
- `0x180016300`
- `0x180016390`
- `0x180016460`

## callees

- `0x18000f9f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fa18`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fa18`

## pseudocode

```c
void __fastcall std::_Init_locks::~_Init_locks(std::_Init_locks *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  if ( _InterlockedDecrement(&dword_18001F1C0) < 0 )
  {
    v1 = &CriticalSection;
    do
      DeleteCriticalSection(v1++);
    while ( v1 != (struct _RTL_CRITICAL_SECTION *)&std::num_get<char,std::istreambuf_iterator<char>>::id );
  }
}

```

## disassembly

```asm
0x18000f9f8  push    rbx
0x18000f9fa  sub     rsp, 20h
0x18000f9fe  or      eax, 0FFFFFFFFh
0x18000fa01  lock xadd cs:dword_18001F1C0, eax
0x18000fa09  cmp     eax, 1
0x18000fa0c  jns     short loc_18000FA2E
0x18000fa0e  lea     rbx, CriticalSection
0x18000fa15  mov     rcx, rbx; lpCriticalSection
0x18000fa18  call    cs:__imp_DeleteCriticalSection
0x18000fa1e  lea     rax, ?id@?$num_get@DV?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@@std@@2V0locale@2@A; std::locale::id std::num_get<char,std::istreambuf_iterator<char>>::id
0x18000fa25  add     rbx, 28h ; '('
0x18000fa29  cmp     rbx, rax
0x18000fa2c  jnz     short loc_18000FA15
0x18000fa2e  add     rsp, 20h
0x18000fa32  pop     rbx
0x18000fa33  retn
```
