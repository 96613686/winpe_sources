# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x18000b0d0`
- end: `0x18000b10c`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b0d0`

## import_xrefs

- `msvcrt!free` at `0x18000b0ed`
- `msvcrt!free` at `0x18000b0ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b0db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b0db`

## pseudocode

```c
__int64 ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  __int64 result; // rax

  DeleteCriticalSection(&stru_180014B28);
  if ( Block )
  {
    free(Block);
    result = 0;
    Block = 0;
  }
  else
  {
    result = 0;
  }
  qword_180014B58 = 0;
  return result;
}

```

## disassembly

```asm
0x18000b0d0  sub     rsp, 28h
0x18000b0d4  lea     rcx, stru_180014B28; lpCriticalSection
0x18000b0db  call    cs:__imp_DeleteCriticalSection
0x18000b0e1  mov     rcx, cs:Block; Block
0x18000b0e8  test    rcx, rcx
0x18000b0eb  jz      short loc_18000B0FE
0x18000b0ed  call    cs:__imp_free
0x18000b0f3  xor     eax, eax
0x18000b0f5  mov     cs:Block, rax
0x18000b0fc  jmp     short loc_18000B100
0x18000b0fe  xor     eax, eax
0x18000b100  mov     cs:qword_180014B58, rax
0x18000b107  add     rsp, 28h
0x18000b10b  retn
```
