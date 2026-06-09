# __acrt_uninitialize_stdio

- ea: `0x10041f100`
- end: `0x10041f15b`
- name: `__acrt_uninitialize_stdio`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x10041c24c`
- `0x10041efb4`
- `0x10041f100`
- `0x100421b84`
- `0x100421c3c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x10041f131`
- `KERNEL32!DeleteCriticalSection` at `0x10041f131`

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
0x10041f100  push    rbx
0x10041f102  sub     rsp, 20h
0x10041f106  call    _flushall
0x10041f10b  call    _fcloseall
0x10041f110  xor     ebx, ebx
0x10041f112  mov     rcx, cs:__piob
0x10041f119  mov     rcx, [rbx+rcx]
0x10041f11d  call    __acrt_stdio_free_buffer_nolock
0x10041f122  mov     rax, cs:__piob
0x10041f129  mov     rcx, [rbx+rax]
0x10041f12d  add     rcx, 30h ; '0'; lpCriticalSection
0x10041f131  call    cs:__imp_DeleteCriticalSection
0x10041f137  add     rbx, 8
0x10041f13b  cmp     rbx, 18h
0x10041f13f  jnz     short loc_10041F112
0x10041f141  mov     rcx, cs:__piob; Block
0x10041f148  call    _free_base
0x10041f14d  and     cs:__piob, 0
0x10041f155  add     rsp, 20h
0x10041f159  pop     rbx
0x10041f15a  retn
```
