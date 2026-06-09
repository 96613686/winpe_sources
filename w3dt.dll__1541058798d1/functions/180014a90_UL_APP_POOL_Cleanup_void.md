# UL_APP_POOL::Cleanup(void)

- ea: `0x180014a90`
- end: `0x180014aef`
- name: `?Cleanup@UL_APP_POOL@@QEAAJXZ`
- size: `95`
- prototype: `__int64 __fastcall(UL_APP_POOL *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180001060`
- `0x1800147e4`
- `0x180014a18`

## callees

- `0x180014a4c`
- `0x180014a90`
- `0x180014af8`

## import_xrefs

- `HTTPAPI!HttpCloseRequestQueue` at `0x180014ac4`
- `HTTPAPI!HttpCloseRequestQueue` at `0x180014ac4`

## pseudocode

```c
__int64 __fastcall UL_APP_POOL::Cleanup(UL_APP_POOL *this)
{
  unsigned int v1; // ebx
  void *v3; // rsi
  signed int v4; // eax

  v1 = 0;
  if ( *(_QWORD *)this )
  {
    UL_APP_POOL::AcquireLockExclusive(this);
    v3 = *(void **)this;
    *(_QWORD *)this = 0;
    UL_APP_POOL::ReleaseLockExclusive(this);
    if ( v3 )
    {
      v4 = HttpCloseRequestQueue(v3);
      if ( v4 )
      {
        if ( v4 > 0 )
          return (unsigned __int16)v4 | 0x80070000;
        else
          return (unsigned int)v4;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180014a90  mov     [rsp+arg_0], rbx
0x180014a95  mov     [rsp+arg_8], rsi
0x180014a9a  push    rdi
0x180014a9b  sub     rsp, 20h
0x180014a9f  xor     ebx, ebx
0x180014aa1  mov     rdi, rcx
0x180014aa4  cmp     [rcx], rbx
0x180014aa7  jz      short loc_180014ADD
0x180014aa9  call    ?AcquireLockExclusive@UL_APP_POOL@@AEAAXXZ; UL_APP_POOL::AcquireLockExclusive(void)
0x180014aae  mov     rsi, [rdi]
0x180014ab1  mov     rcx, rdi; this
0x180014ab4  mov     [rdi], rbx
0x180014ab7  call    ?ReleaseLockExclusive@UL_APP_POOL@@AEAAXXZ; UL_APP_POOL::ReleaseLockExclusive(void)
0x180014abc  test    rsi, rsi
0x180014abf  jz      short loc_180014ADD
0x180014ac1  mov     rcx, rsi; RequestQueueHandle
0x180014ac4  call    cs:__imp_HttpCloseRequestQueue
0x180014aca  test    eax, eax
0x180014acc  jz      short loc_180014ADD
0x180014ace  jg      short loc_180014AD4
0x180014ad0  mov     ebx, eax
0x180014ad2  jmp     short loc_180014ADD
0x180014ad4  movzx   ebx, ax
0x180014ad7  or      ebx, 80070000h
0x180014add  mov     rsi, [rsp+28h+arg_8]
0x180014ae2  mov     eax, ebx
0x180014ae4  mov     rbx, [rsp+28h+arg_0]
0x180014ae9  add     rsp, 20h
0x180014aed  pop     rdi
0x180014aee  retn
```
