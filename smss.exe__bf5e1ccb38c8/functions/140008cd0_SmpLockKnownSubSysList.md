# SmpLockKnownSubSysList

- ea: `0x140008cd0`
- end: `0x140008d05`
- name: `SmpLockKnownSubSysList`
- size: `53`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140001580`
- `0x140002bb0`
- `0x140017f58`
- `0x140018154`

## callees

- `0x140008cd0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x140008cfe`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140008cf7`

## pseudocode

```c
__int64 __fastcall SmpLockKnownSubSysList(char a1, int a2, __int64 a3)
{
  __int64 v3; // r9
  __int64 v4; // rcx

  v3 = SmpKnownSubSysTable + 24LL * (a1 & 0x1F);
  if ( a3 )
  {
    *(_QWORD *)(a3 + 8) = v3;
    *(_DWORD *)a3 = a2;
  }
  v4 = v3 + 16;
  if ( a2 == 1 )
    return RtlAcquireSRWLockShared(v4);
  else
    return RtlAcquireSRWLockExclusive(v4);
}

```

## disassembly

```asm
0x140008cd0  mov     rax, cs:SmpKnownSubSysTable
0x140008cd7  and     ecx, 1Fh
0x140008cda  lea     rcx, [rcx+rcx*2]
0x140008cde  lea     r9, [rax+rcx*8]
0x140008ce2  test    r8, r8
0x140008ce5  jz      short loc_140008CEE
0x140008ce7  mov     [r8+8], r9
0x140008ceb  mov     [r8], edx
0x140008cee  lea     rcx, [r9+10h]
0x140008cf2  cmp     edx, 1
0x140008cf5  jz      short loc_140008CFE
0x140008cf7  jmp     cs:__imp_RtlAcquireSRWLockExclusive
0x140008cfe  jmp     cs:__imp_RtlAcquireSRWLockShared
```
