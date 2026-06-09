# CIndexCache::`vector deleting destructor'(uint)

- ea: `0x18000d9c0`
- end: `0x18000d9f0`
- name: `??_ECIndexCache@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CIndexCache *__fastcall(CIndexCache *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b9ac`
- `0x18000d9c0`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000d9dc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000d9dc`

## pseudocode

```c
CIndexCache *__fastcall CIndexCache::`vector deleting destructor'(CIndexCache *this, char a2)
{
  CIndexCache::~CIndexCache(this);
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x18000d9c0  mov     [rsp+arg_0], rbx
0x18000d9c5  push    rdi
0x18000d9c6  sub     rsp, 20h
0x18000d9ca  mov     ebx, edx
0x18000d9cc  mov     rdi, rcx
0x18000d9cf  call    ??1CIndexCache@@UEAA@XZ; CIndexCache::~CIndexCache(void)
0x18000d9d4  test    bl, 1
0x18000d9d7  jz      short loc_18000D9E2
0x18000d9d9  mov     rcx, rdi
0x18000d9dc  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000d9e2  mov     rax, rdi
0x18000d9e5  mov     rbx, [rsp+28h+arg_0]
0x18000d9ea  add     rsp, 20h
0x18000d9ee  pop     rdi
0x18000d9ef  retn
```
