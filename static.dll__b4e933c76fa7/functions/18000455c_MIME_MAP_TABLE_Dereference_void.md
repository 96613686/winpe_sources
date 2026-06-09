# MIME_MAP_TABLE::Dereference(void)

- ea: `0x18000455c`
- end: `0x18000458a`
- name: `?Dereference@MIME_MAP_TABLE@@QEAAXXZ`
- size: `46`
- prototype: `void __fastcall(MIME_MAP_TABLE *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002c04`
- `0x1800043d4`
- `0x1800054f0`
- `0x180005700`

## callees

- `0x18000455c`
- `0x180007010`

## pseudocode

```c
void __fastcall MIME_MAP_TABLE::Dereference(MIME_MAP_TABLE *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 266, 0xFFFFFFFF) == 1 )
  {
    if ( this )
      (**(void (__fastcall ***)(MIME_MAP_TABLE *, __int64))this)(this, 1);
  }
}

```

## disassembly

```asm
0x18000455c  sub     rsp, 28h
0x180004560  or      eax, 0FFFFFFFFh
0x180004563  lock xadd [rcx+428h], eax
0x18000456b  cmp     eax, 1
0x18000456e  jnz     short loc_180004585
0x180004570  test    rcx, rcx
0x180004573  jz      short loc_180004585
0x180004575  mov     rax, [rcx]
0x180004578  mov     edx, 1
0x18000457d  mov     rax, [rax]
0x180004580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004585  add     rsp, 28h
0x180004589  retn
```
