# Pca::MergeSdb::Utils::RegUtil::WriteRegValue(HKEY__ *,ushort const *,ushort const *)

- ea: `0x14002e24c`
- end: `0x14002e296`
- name: `?WriteRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBG1@Z`
- size: `74`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *, const BYTE *lpData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14002285c`
- `0x140028714`

## callees

- `0x14002e24c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14002e284`
- `ADVAPI32!RegSetValueExW` at `0x14002e284`

## pseudocode

```c
LSTATUS __fastcall Pca::MergeSdb::Utils::RegUtil::WriteRegValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const BYTE *lpData)
{
  __int64 v3; // rax

  if ( !a2 || !lpData )
    return 87;
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&lpData[2 * v3] );
  return RegSetValueExW(a1, a2, 0, 1u, lpData, 2 * v3 + 2);
}

```

## disassembly

```asm
0x14002e24c  sub     rsp, 38h
0x14002e250  xor     r9d, r9d
0x14002e253  test    rdx, rdx
0x14002e256  jz      short loc_14002E28C
0x14002e258  test    r8, r8
0x14002e25b  jz      short loc_14002E28C
0x14002e25d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002e261  inc     rax
0x14002e264  cmp     [r8+rax*2], r9w
0x14002e269  jnz     short loc_14002E261
0x14002e26b  lea     eax, ds:2[rax*2]
0x14002e272  mov     r9d, 1; dwType
0x14002e278  mov     [rsp+38h+cbData], eax; cbData
0x14002e27c  mov     [rsp+38h+lpData], r8; lpData
0x14002e281  xor     r8d, r8d; Reserved
0x14002e284  call    cs:__imp_RegSetValueExW
0x14002e28a  jmp     short loc_14002E291
0x14002e28c  mov     eax, 57h ; 'W'
0x14002e291  add     rsp, 38h
0x14002e295  retn
```
