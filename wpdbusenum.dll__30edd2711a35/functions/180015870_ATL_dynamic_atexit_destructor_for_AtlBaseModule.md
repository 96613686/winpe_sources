# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x180015870`
- end: `0x1800158ad`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `61`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a156`
- `0x180015870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001587b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001587b`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  DeleteCriticalSection(&CriticalSection);
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_18001F728 = 0;
}

```

## disassembly

```asm
0x180015870  sub     rsp, 28h
0x180015874  lea     rcx, CriticalSection; lpCriticalSection
0x18001587b  call    cs:__imp_DeleteCriticalSection
0x180015881  mov     rcx, cs:Block; Block
0x180015888  test    rcx, rcx
0x18001588b  jz      short loc_18001589D
0x18001588d  call    free
0x180015892  mov     cs:Block, 0
0x18001589d  mov     cs:qword_18001F728, 0
0x1800158a8  add     rsp, 28h
0x1800158ac  retn
```
