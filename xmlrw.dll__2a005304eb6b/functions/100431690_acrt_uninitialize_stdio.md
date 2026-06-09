# __acrt_uninitialize_stdio

- ea: `0x100431690`
- end: `0x1004316eb`
- name: `__acrt_uninitialize_stdio`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x10042e7dc`
- `0x100431544`
- `0x100431690`
- `0x100435134`
- `0x1004351ec`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1004316c1`
- `KERNEL32!DeleteCriticalSection` at `0x1004316c1`

## pseudocode

```c
void _acrt_uninitialize_stdio()
{
  __int64 i; // rbx

  flushall();
  fcloseall();
  for ( i = 0; i != 24; i += 8 )
  {
    _acrt_stdio_free_buffer_nolock(*(_QWORD *)((char *)_piob + i));
    DeleteCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)((char *)_piob + i) + 48LL));
  }
  free_base(_piob);
  _piob = 0;
}

```

## disassembly

```asm
0x100431690  push    rbx
0x100431692  sub     rsp, 20h
0x100431696  call    _flushall
0x10043169b  call    _fcloseall
0x1004316a0  xor     ebx, ebx
0x1004316a2  mov     rcx, cs:__piob
0x1004316a9  mov     rcx, [rbx+rcx]
0x1004316ad  call    __acrt_stdio_free_buffer_nolock
0x1004316b2  mov     rax, cs:__piob
0x1004316b9  mov     rcx, [rbx+rax]
0x1004316bd  add     rcx, 30h ; '0'; lpCriticalSection
0x1004316c1  call    cs:__imp_DeleteCriticalSection
0x1004316c7  add     rbx, 8
0x1004316cb  cmp     rbx, 18h
0x1004316cf  jnz     short loc_1004316A2
0x1004316d1  mov     rcx, cs:__piob; Block
0x1004316d8  call    _free_base
0x1004316dd  and     cs:__piob, 0
0x1004316e5  add     rsp, 20h
0x1004316e9  pop     rbx
0x1004316ea  retn
```
