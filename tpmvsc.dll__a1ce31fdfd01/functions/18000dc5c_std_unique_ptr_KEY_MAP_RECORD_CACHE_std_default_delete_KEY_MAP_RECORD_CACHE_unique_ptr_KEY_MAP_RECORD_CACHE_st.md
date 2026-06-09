# std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>::~unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>(void)

- ea: `0x18000dc5c`
- end: `0x18000dc72`
- name: `??1?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cd48`
- `0x18000db58`
- `0x18000f6a0`
- `0x180035679`

## callees

- `0x18000dc5c`
- `0x18000f374`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<KEY_MAP_RECORD_CACHE>::~unique_ptr<KEY_MAP_RECORD_CACHE>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<KEY_MAP_RECORD_CACHE>::operator()();
  return result;
}

```

## disassembly

```asm
0x18000dc5c  sub     rsp, 28h
0x18000dc60  mov     rdx, [rcx]
0x18000dc63  test    rdx, rdx
0x18000dc66  jz      short loc_18000DC6D
0x18000dc68  call    ??R?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@QEBAXPEAUKEY_MAP_RECORD_CACHE@@@Z; std::default_delete<KEY_MAP_RECORD_CACHE>::operator()(KEY_MAP_RECORD_CACHE *)
0x18000dc6d  add     rsp, 28h
0x18000dc71  retn
```
