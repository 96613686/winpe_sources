# CHandleCache::`vector deleting destructor'(uint)

- ea: `0x1800093e0`
- end: `0x180009413`
- name: `??_ECHandleCache@@UEAAPEAXI@Z`
- size: `51`
- prototype: `CHandleCache *__fastcall(CHandleCache *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800093e0`
- `0x18000941c`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000940b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000940b`

## pseudocode

```c
CHandleCache *__fastcall CHandleCache::`vector deleting destructor'(CHandleCache *this, char a2)
{
  CHandleCache::~CHandleCache(this);
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x1800093e0  mov     [rsp+arg_0], rbx
0x1800093e5  push    rdi
0x1800093e6  sub     rsp, 20h
0x1800093ea  mov     edi, edx
0x1800093ec  mov     rbx, rcx
0x1800093ef  call    ??1CHandleCache@@UEAA@XZ; CHandleCache::~CHandleCache(void)
0x1800093f4  test    dil, 1
0x1800093f8  jnz     short loc_180009408
0x1800093fa  mov     rax, rbx
0x1800093fd  mov     rbx, [rsp+28h+arg_0]
0x180009402  add     rsp, 20h
0x180009406  pop     rdi
0x180009407  retn
0x180009408  mov     rcx, rbx
0x18000940b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180009411  jmp     short loc_1800093FA
```
