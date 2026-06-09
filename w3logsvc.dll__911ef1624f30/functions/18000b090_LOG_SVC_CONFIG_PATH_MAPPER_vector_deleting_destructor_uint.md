# LOG_SVC_CONFIG_PATH_MAPPER::`vector deleting destructor'(uint)

- ea: `0x18000b090`
- end: `0x18000b0b6`
- name: `??_ELOG_SVC_CONFIG_PATH_MAPPER@@UEAAPEAXI@Z`
- size: `38`
- prototype: `LOG_SVC_CONFIG_PATH_MAPPER *__fastcall(LOG_SVC_CONFIG_PATH_MAPPER *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180001048`
- `0x18000b090`

## pseudocode

```c
LOG_SVC_CONFIG_PATH_MAPPER *__fastcall LOG_SVC_CONFIG_PATH_MAPPER::`vector deleting destructor'(
        LOG_SVC_CONFIG_PATH_MAPPER *this,
        char a2)
{
  *(_QWORD *)this = &LOG_SVC_CONFIG_PATH_MAPPER::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000b090  push    rbx
0x18000b092  sub     rsp, 20h
0x18000b096  lea     rax, ??_7LOG_SVC_CONFIG_PATH_MAPPER@@6B@; const LOG_SVC_CONFIG_PATH_MAPPER::`vftable'
0x18000b09d  mov     rbx, rcx
0x18000b0a0  mov     [rcx], rax
0x18000b0a3  test    dl, 1
0x18000b0a6  jz      short loc_18000B0AD
0x18000b0a8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b0ad  mov     rax, rbx
0x18000b0b0  add     rsp, 20h
0x18000b0b4  pop     rbx
0x18000b0b5  retn
```
