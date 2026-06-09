# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x180030790`
- end: `0x1800307ce`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180030790`

## import_xrefs

- `msvcrt!free` at `0x1800307ad`
- `msvcrt!free` at `0x1800307ad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003079b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003079b`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  DeleteCriticalSection(&stru_180049D38);
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_180049D68 = 0;
}

```

## disassembly

```asm
0x180030790  sub     rsp, 28h
0x180030794  lea     rcx, stru_180049D38; lpCriticalSection
0x18003079b  call    cs:__imp_DeleteCriticalSection
0x1800307a1  mov     rcx, cs:Block; Block
0x1800307a8  test    rcx, rcx
0x1800307ab  jz      short loc_1800307BE
0x1800307ad  call    cs:__imp_free
0x1800307b3  mov     cs:Block, 0
0x1800307be  mov     cs:qword_180049D68, 0
0x1800307c9  add     rsp, 28h
0x1800307cd  retn
```
