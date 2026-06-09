# SmpUnlockKnownSubSysList

- ea: `0x1400030f0`
- end: `0x14000310e`
- name: `SmpUnlockKnownSubSysList`
- size: `30`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400014a0`
- `0x140001580`
- `0x140001f60`
- `0x1400027a0`
- `0x140002bb0`
- `0x140005f64`
- `0x1400151e0`
- `0x140017f58`
- `0x140018154`

## callees

- `0x1400030f0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x140003107`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140003100`

## pseudocode

```c
__int64 __fastcall SmpUnlockKnownSubSysList(__int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8) + 16LL;
  if ( *(_DWORD *)a1 == 1 )
    return RtlReleaseSRWLockShared(v2);
  else
    return RtlReleaseSRWLockExclusive(v2);
}

```

## disassembly

```asm
0x1400030f0  mov     rax, rcx
0x1400030f3  mov     rcx, [rcx+8]
0x1400030f7  add     rcx, 10h
0x1400030fb  cmp     dword ptr [rax], 1
0x1400030fe  jz      short loc_140003107
0x140003100  jmp     cs:__imp_RtlReleaseSRWLockExclusive
0x140003107  jmp     cs:__imp_RtlReleaseSRWLockShared
```
