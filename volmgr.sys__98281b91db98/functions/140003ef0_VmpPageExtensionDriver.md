# VmpPageExtensionDriver

- ea: `0x140003ef0`
- end: `0x140003f19`
- name: `VmpPageExtensionDriver`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `15`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140001ae0`
- `0x140003000`
- `0x14000e54c`
- `0x14000e888`
- `0x14000eba0`
- `0x14000f158`
- `0x14000fbe0`
- `0x140012964`
- `0x140012cf4`
- `0x140012f18`
- `0x14001462c`
- `0x1400147dc`
- `0x140014838`
- `0x1400149e8`
- `0x140014b80`

## callees

- `0x140003ef0`

## import_xrefs

- `ntoskrnl!MmPageEntireDriver` at `0x140003f07`
- `ntoskrnl!MmPageEntireDriver` at `0x140003f07`

## pseudocode

```c
PVOID __fastcall VmpPageExtensionDriver(__int64 a1)
{
  PVOID result; // rax

  if ( (*(_DWORD *)(a1 + 384))-- == 1 )
    return MmPageEntireDriver(**(PVOID **)(a1 + 392));
  return result;
}

```

## disassembly

```asm
0x140003ef0  sub     rsp, 28h
0x140003ef4  add     dword ptr [rcx+180h], 0FFFFFFFFh
0x140003efb  jnz     short loc_140003F13
0x140003efd  mov     rcx, [rcx+188h]
0x140003f04  mov     rcx, [rcx]; AddressWithinSection
0x140003f07  call    cs:__imp_MmPageEntireDriver
0x140003f0e  nop     dword ptr [rax+rax+00h]
0x140003f13  add     rsp, 28h
0x140003f17  retn
```
