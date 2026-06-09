# operator delete(void *)

- ea: `0x18000a9ac`
- end: `0x18000a9c7`
- name: `??3@YAXPEAX@Z`
- size: `27`
- prototype: `void __fastcall(void *)`
- caller_count: `59`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000a90c`
- `0x18000a934`
- `0x18000ac50`
- `0x18000ae2c`
- `0x18000bad0`
- `0x18000bf90`
- `0x18000c040`
- `0x18000c078`
- `0x18000cc58`
- `0x18000d920`
- `0x18000e064`
- `0x18000e3bc`
- `0x18000e438`
- `0x18000e838`
- `0x18000ece0`
- `0x18000f950`
- `0x18000fbdc`
- `0x18000fd20`
- `0x180010100`
- `0x180011d00`
- `0x1800131a4`
- `0x180013efc`
- `0x1800144b8`
- `0x180016e2c`
- `0x18001d7f4`
- `0x18001ddf4`
- `0x180022dd4`
- `0x180025140`
- `0x1800252f0`
- `0x180025ad4`
- `0x1800261e4`
- `0x1800269f0`
- `0x180026f84`
- `0x180027090`
- `0x18002984c`
- `0x18002a9e0`
- `0x18002f900`
- `0x18002fef0`
- `0x18002ff30`
- `0x180031400`
- `0x180031440`
- `0x1800317d0`
- `0x180031810`
- `0x180031d40`
- `0x180031d80`
- `0x180031dc0`
- `0x180031df8`
- `0x1800321ac`
- `0x180032360`
- `0x18003557c`

## callees

- `0x18000a9ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a9b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a9b5`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    free(a1);
}

```

## disassembly

```asm
0x18000a9ac  sub     rsp, 28h
0x18000a9b0  test    rcx, rcx
0x18000a9b3  jz      short loc_18000A9C1
0x18000a9b5  call    cs:__imp_free
0x18000a9bc  nop     dword ptr [rax+rax+00h]
0x18000a9c1  add     rsp, 28h
0x18000a9c5  retn
```
