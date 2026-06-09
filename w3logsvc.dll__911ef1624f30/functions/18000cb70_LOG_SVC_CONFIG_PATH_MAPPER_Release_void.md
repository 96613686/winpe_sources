# LOG_SVC_CONFIG_PATH_MAPPER::Release(void)

- ea: `0x18000cb70`
- end: `0x18000cb9f`
- name: `?Release@LOG_SVC_CONFIG_PATH_MAPPER@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(LOG_SVC_CONFIG_PATH_MAPPER *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000cb70`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall LOG_SVC_CONFIG_PATH_MAPPER::Release(LOG_SVC_CONFIG_PATH_MAPPER *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
    (*(void (__fastcall **)(LOG_SVC_CONFIG_PATH_MAPPER *, __int64))(*(_QWORD *)this + 32LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x18000cb70  push    rbx
0x18000cb72  sub     rsp, 20h
0x18000cb76  or      ebx, 0FFFFFFFFh
0x18000cb79  lock xadd [rcx+8], ebx
0x18000cb7e  sub     ebx, 1
0x18000cb81  jnz     short loc_18000CB97
0x18000cb83  test    rcx, rcx
0x18000cb86  jz      short loc_18000CB97
0x18000cb88  mov     rdx, [rcx]
0x18000cb8b  mov     rax, [rdx+20h]
0x18000cb8f  lea     edx, [rbx+1]
0x18000cb92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb97  mov     eax, ebx
0x18000cb99  add     rsp, 20h
0x18000cb9d  pop     rbx
0x18000cb9e  retn
```
