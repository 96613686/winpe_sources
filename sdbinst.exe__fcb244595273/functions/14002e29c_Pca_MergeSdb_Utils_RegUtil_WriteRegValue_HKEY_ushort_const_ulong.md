# Pca::MergeSdb::Utils::RegUtil::WriteRegValue(HKEY__ *,ushort const *,ulong)

- ea: `0x14002e29c`
- end: `0x14002e2d2`
- name: `?WriteRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGK@Z`
- size: `54`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14002285c`

## callees

- `0x14002e29c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14002e2c7`
- `ADVAPI32!RegSetValueExW` at `0x14002e2c7`

## pseudocode

```c
LSTATUS __fastcall Pca::MergeSdb::Utils::RegUtil::WriteRegValue(HKEY a1, const unsigned __int16 *a2, int a3)
{
  int Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  if ( a2 )
    return RegSetValueExW(a1, a2, 0, 4u, (const BYTE *)&Data, 4u);
  else
    return 87;
}

```

## disassembly

```asm
0x14002e29c  mov     [rsp+Data], r8d
0x14002e2a1  sub     rsp, 38h
0x14002e2a5  test    rdx, rdx
0x14002e2a8  jnz     short loc_14002E2AF
0x14002e2aa  lea     eax, [rdx+57h]
0x14002e2ad  jmp     short loc_14002E2CD
0x14002e2af  mov     r9d, 4; dwType
0x14002e2b5  lea     rax, [rsp+38h+Data]
0x14002e2ba  mov     [rsp+38h+cbData], r9d; cbData
0x14002e2bf  xor     r8d, r8d; Reserved
0x14002e2c2  mov     [rsp+38h+lpData], rax; lpData
0x14002e2c7  call    cs:__imp_RegSetValueExW
0x14002e2cd  add     rsp, 38h
0x14002e2d1  retn
```
