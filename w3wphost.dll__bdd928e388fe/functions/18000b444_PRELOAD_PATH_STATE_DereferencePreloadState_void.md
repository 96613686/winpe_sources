# PRELOAD_PATH_STATE::DereferencePreloadState(void)

- ea: `0x18000b444`
- end: `0x18000b463`
- name: `?DereferencePreloadState@PRELOAD_PATH_STATE@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(PRELOAD_PATH_STATE *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b50c`
- `0x18000c140`

## callees

- `0x180002f84`
- `0x18000b444`

## pseudocode

```c
void __fastcall PRELOAD_PATH_STATE::DereferencePreloadState(PRELOAD_PATH_STATE *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this, 0xFFFFFFFF) == 1 )
  {
    if ( this )
      PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'(this);
  }
}

```

## disassembly

```asm
0x18000b444  sub     rsp, 28h
0x18000b448  or      eax, 0FFFFFFFFh
0x18000b44b  lock xadd [rcx], eax
0x18000b44f  cmp     eax, 1
0x18000b452  jnz     short loc_18000B45E
0x18000b454  test    rcx, rcx
0x18000b457  jz      short loc_18000B45E
0x18000b459  call    ??_GPROTOCOL_ID_ARRAY_LIST_ENTRY@@QEAAPEAXI@Z; PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'(uint)
0x18000b45e  add     rsp, 28h
0x18000b462  retn
```
