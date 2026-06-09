# CQuickStringTBase::~CQuickStringTBase(void)

- ea: `0x18000f0dc`
- end: `0x18000f0ff`
- name: `??1CQuickStringTBase@@MEAA@XZ`
- size: `35`
- prototype: `void __fastcall(CQuickStringTBase *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003798`
- `0x1800037b0`
- `0x1800037f0`
- `0x180003ab0`
- `0x180009560`
- `0x18000c0e0`

## callees

- `0x18000f0dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f0f4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f0f4`

## pseudocode

```c
void __fastcall CQuickStringTBase::~CQuickStringTBase(CQuickStringTBase *this)
{
  bool v1; // sf

  v1 = *((int *)this + 4) < 0;
  *(_QWORD *)this = &CQuickStringTBase::`vftable';
  if ( !v1 )
    free(*((void **)this + 1));
}

```

## disassembly

```asm
0x18000f0dc  sub     rsp, 28h
0x18000f0e0  cmp     dword ptr [rcx+10h], 0
0x18000f0e4  lea     rax, ??_7CQuickStringTBase@@6B@; const CQuickStringTBase::`vftable'
0x18000f0eb  mov     [rcx], rax
0x18000f0ee  jl      short loc_18000F0FA
0x18000f0f0  mov     rcx, [rcx+8]; Block
0x18000f0f4  call    cs:__imp_free
0x18000f0fa  add     rsp, 28h
0x18000f0fe  retn
```
