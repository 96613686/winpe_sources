# LOG_SVC_CONFIG_CHANGE_HANDLER::Release(void)

- ea: `0x18000cb30`
- end: `0x18000cb5f`
- name: `?Release@LOG_SVC_CONFIG_CHANGE_HANDLER@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(LOG_SVC_CONFIG_CHANGE_HANDLER *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180001048`
- `0x18000cb30`

## pseudocode

```c
__int64 __fastcall LOG_SVC_CONFIG_CHANGE_HANDLER::Release(LOG_SVC_CONFIG_CHANGE_HANDLER *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &LOG_SVC_CONFIG_CHANGE_HANDLER::`vftable';
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x18000cb30  push    rbx
0x18000cb32  sub     rsp, 20h
0x18000cb36  or      ebx, 0FFFFFFFFh
0x18000cb39  lock xadd [rcx+8], ebx
0x18000cb3e  sub     ebx, 1
0x18000cb41  jnz     short loc_18000CB57
0x18000cb43  test    rcx, rcx
0x18000cb46  jz      short loc_18000CB57
0x18000cb48  lea     rax, ??_7LOG_SVC_CONFIG_CHANGE_HANDLER@@6B@; const LOG_SVC_CONFIG_CHANGE_HANDLER::`vftable'
0x18000cb4f  mov     [rcx], rax
0x18000cb52  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cb57  mov     eax, ebx
0x18000cb59  add     rsp, 20h
0x18000cb5d  pop     rbx
0x18000cb5e  retn
```
