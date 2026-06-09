# CCacheEntry::`scalar deleting destructor'(uint)

- ea: `0x18000f5c0`
- end: `0x18000f5f0`
- name: `??_GCCacheEntry@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CCacheEntry *__fastcall(CCacheEntry *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b24c`
- `0x18000f5c0`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000f5dc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000f5dc`

## pseudocode

```c
CCacheEntry *__fastcall CCacheEntry::`scalar deleting destructor'(CCacheEntry *this, char a2)
{
  CCacheEntry::~CCacheEntry(this);
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x18000f5c0  mov     [rsp+arg_0], rbx
0x18000f5c5  push    rdi
0x18000f5c6  sub     rsp, 20h
0x18000f5ca  mov     ebx, edx
0x18000f5cc  mov     rdi, rcx
0x18000f5cf  call    ??1CCacheEntry@@UEAA@XZ; CCacheEntry::~CCacheEntry(void)
0x18000f5d4  test    bl, 1
0x18000f5d7  jz      short loc_18000F5E2
0x18000f5d9  mov     rcx, rdi
0x18000f5dc  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000f5e2  mov     rax, rdi
0x18000f5e5  mov     rbx, [rsp+28h+arg_0]
0x18000f5ea  add     rsp, 20h
0x18000f5ee  pop     rdi
0x18000f5ef  retn
```
