# VmpRestoreExtensionDriver

- ea: `0x140003e70`
- end: `0x140003e9f`
- name: `VmpRestoreExtensionDriver`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `14`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140001ae0`
- `0x140003000`
- `0x14000e54c`
- `0x14000e888`
- `0x14000eba0`
- `0x14000fb00`
- `0x14001171c`
- `0x140012964`
- `0x140012cf4`
- `0x140012f18`
- `0x14001462c`
- `0x1400147dc`
- `0x140014838`
- `0x1400149e8`

## callees

- `0x140003e70`

## import_xrefs

- `ntoskrnl!MmResetDriverPaging` at `0x140003e8d`
- `ntoskrnl!MmResetDriverPaging` at `0x140003e8d`

## pseudocode

```c
void __fastcall VmpRestoreExtensionDriver(__int64 a1)
{
  if ( ++*(_DWORD *)(a1 + 384) == 1 )
    MmResetDriverPaging(**(PVOID **)(a1 + 392));
}

```

## disassembly

```asm
0x140003e70  sub     rsp, 28h
0x140003e74  inc     dword ptr [rcx+180h]
0x140003e7a  cmp     dword ptr [rcx+180h], 1
0x140003e81  jnz     short loc_140003E99
0x140003e83  mov     rcx, [rcx+188h]
0x140003e8a  mov     rcx, [rcx]; AddressWithinSection
0x140003e8d  call    cs:__imp_MmResetDriverPaging
0x140003e94  nop     dword ptr [rax+rax+00h]
0x140003e99  add     rsp, 28h
0x140003e9d  retn
```
