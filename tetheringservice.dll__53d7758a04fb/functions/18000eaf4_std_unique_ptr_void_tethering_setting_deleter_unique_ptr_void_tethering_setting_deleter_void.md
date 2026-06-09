# std::unique_ptr<void,tethering_setting_deleter>::~unique_ptr<void,tethering_setting_deleter>(void)

- ea: `0x18000eaf4`
- end: `0x18000eb0b`
- name: `??1?$unique_ptr@XUtethering_setting_deleter@@@std@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180031b43`
- `0x180031b79`
- `0x180031b8b`
- `0x180031be5`
- `0x180031f20`
- `0x180031f44`
- `0x180031fb0`
- `0x180032683`

## callees

- `0x18000eaf4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000eb00`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000eb00`

## pseudocode

```c
void __fastcall std::unique_ptr<void,tethering_setting_deleter>::~unique_ptr<void,tethering_setting_deleter>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    free(v1);
}

```

## disassembly

```asm
0x18000eaf4  sub     rsp, 28h
0x18000eaf8  mov     rcx, [rcx]; Block
0x18000eafb  test    rcx, rcx
0x18000eafe  jz      short loc_18000EB06
0x18000eb00  call    cs:__imp_free
0x18000eb06  add     rsp, 28h
0x18000eb0a  retn
```
