# ??1?$unique_ptr@U_CRASH_SHARED_DATA@@U?$generic_delete@U_CRASH_SHARED_DATA@@U?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ

- ea: `0x140004e08`
- end: `0x140004e1f`
- name: `??1?$unique_ptr@U_CRASH_SHARED_DATA@@U?$generic_delete@U_CRASH_SHARED_DATA@@U?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140011410`

## callees

- `0x140004e08`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140004e14`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140004e14`

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
0x140004e08  sub     rsp, 28h
0x140004e0c  mov     rcx, [rcx]; lpBaseAddress
0x140004e0f  test    rcx, rcx
0x140004e12  jz      short loc_140004E1A
0x140004e14  call    cs:__imp_UnmapViewOfFile
0x140004e1a  add     rsp, 28h
0x140004e1e  retn
```
