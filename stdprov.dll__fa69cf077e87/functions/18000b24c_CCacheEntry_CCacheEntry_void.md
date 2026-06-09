# CCacheEntry::~CCacheEntry(void)

- ea: `0x18000b24c`
- end: `0x18000b292`
- name: `??1CCacheEntry@@UEAA@XZ`
- size: `70`
- prototype: `void __fastcall(CCacheEntry *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f5c0`

## callees

- `0x18000b24c`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000b26c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000b27b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000b26c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000b27b`

## pseudocode

```c
void __fastcall CCacheEntry::~CCacheEntry(CCacheEntry *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CCacheEntry::`vftable';
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
    CWin32DefaultArena::WbemMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    CWin32DefaultArena::WbemMemFree(v3);
  *(_QWORD *)this = &CObject::`vftable';
}

```

## disassembly

```asm
0x18000b24c  mov     [rsp+arg_0], rcx
0x18000b251  push    rbx
0x18000b252  sub     rsp, 20h
0x18000b256  mov     rbx, rcx
0x18000b259  lea     rax, ??_7CCacheEntry@@6B@; const CCacheEntry::`vftable'
0x18000b260  mov     [rcx], rax
0x18000b263  mov     rcx, [rcx+10h]
0x18000b267  test    rcx, rcx
0x18000b26a  jz      short loc_18000B272
0x18000b26c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000b272  mov     rcx, [rbx+18h]
0x18000b276  test    rcx, rcx
0x18000b279  jz      short loc_18000B282
0x18000b27b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000b281  nop
0x18000b282  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x18000b289  mov     [rbx], rax
0x18000b28c  add     rsp, 20h
0x18000b290  pop     rbx
0x18000b291  retn
```
