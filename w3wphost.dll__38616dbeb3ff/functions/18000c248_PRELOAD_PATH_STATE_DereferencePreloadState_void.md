# PRELOAD_PATH_STATE::DereferencePreloadState(void)

- ea: `0x18000c248`
- end: `0x18000c268`
- name: `?DereferencePreloadState@PRELOAD_PATH_STATE@@QEAAXXZ`
- size: `32`
- prototype: `void __fastcall(PRELOAD_PATH_STATE *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c320`
- `0x18000d030`

## callees

- `0x18000315c`
- `0x18000c248`

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
0x18000c248  sub     rsp, 28h
0x18000c24c  or      eax, 0FFFFFFFFh
0x18000c24f  lock xadd [rcx], eax
0x18000c253  cmp     eax, 1
0x18000c256  jnz     short loc_18000C262
0x18000c258  test    rcx, rcx
0x18000c25b  jz      short loc_18000C262
0x18000c25d  call    ??_GPROTOCOL_ID_ARRAY_LIST_ENTRY@@QEAAPEAXI@Z; PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'(uint)
0x18000c262  add     rsp, 28h
0x18000c266  retn
```
