# ??1?$unique_ptr@U_CRASH_SHARED_DATA@@U?$generic_delete@U_CRASH_SHARED_DATA@@U?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ

- ea: `0x180013fe8`
- end: `0x180013fff`
- name: `??1?$unique_ptr@U_CRASH_SHARED_DATA@@U?$generic_delete@U_CRASH_SHARED_DATA@@U?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18003492b`
- `0x1800349e1`
- `0x180034c8a`
- `0x180034cae`
- `0x180034e95`
- `0x180034feb`

## callees

- `0x180013fe8`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180013ff4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180013ff4`

## pseudocode

```c
BOOL __fastcall __1__unique_ptr_U_CRASH_SHARED_DATA__U__generic_delete_U_CRASH_SHARED_DATA__U__generic_deallocate__MP6AHPEBX_Z1_UnmapViewOfFile__YAH0_ZPEAX_tlx___tlx___utl__QEAA_XZ(
        const void **a1)
{
  const void *v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return UnmapViewOfFile(v1);
  return result;
}

```

## disassembly

```asm
0x180013fe8  sub     rsp, 28h
0x180013fec  mov     rcx, [rcx]; lpBaseAddress
0x180013fef  test    rcx, rcx
0x180013ff2  jz      short loc_180013FFA
0x180013ff4  call    cs:__imp_UnmapViewOfFile
0x180013ffa  add     rsp, 28h
0x180013ffe  retn
```
