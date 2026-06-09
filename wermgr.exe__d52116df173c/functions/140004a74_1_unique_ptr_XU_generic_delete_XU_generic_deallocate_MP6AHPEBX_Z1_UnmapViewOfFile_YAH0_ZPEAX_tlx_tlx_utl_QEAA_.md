# ??1?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ

- ea: `0x140004a74`
- end: `0x140004a8b`
- name: `??1?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ`
- size: `23`
- prototype: `BOOL __fastcall(const void **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14001cc83`
- `0x14001cd91`
- `0x14001cdc7`
- `0x14001ce33`
- `0x14001cf31`

## callees

- `0x140004a74`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140004a80`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140004a80`

## pseudocode

```c
BOOL __fastcall __1__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6AHPEBX_Z1_UnmapViewOfFile__YAH0_ZPEAX_tlx___tlx___utl__QEAA_XZ(
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
0x140004a74  sub     rsp, 28h
0x140004a78  mov     rcx, [rcx]; lpBaseAddress
0x140004a7b  test    rcx, rcx
0x140004a7e  jz      short loc_140004A86
0x140004a80  call    cs:__imp_UnmapViewOfFile
0x140004a86  add     rsp, 28h
0x140004a8a  retn
```
