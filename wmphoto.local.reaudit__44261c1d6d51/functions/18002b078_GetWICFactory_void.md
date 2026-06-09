# GetWICFactory(void)

- ea: `0x18002b078`
- end: `0x18002b09c`
- name: `?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ`
- size: `36`
- prototype: `struct IWICComponentFactory *(void)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180029040`
- `0x180029930`
- `0x18002ae40`
- `0x18002af70`
- `0x18002c090`
- `0x180031850`
- `0x1800325a0`
- `0x1800327b0`
- `0x1800355e0`
- `0x180035a80`
- `0x1800388b0`
- `0x180039850`
- `0x180039e90`
- `0x18003abd0`
- `0x18003b050`
- `0x18003b1e0`
- `0x18003b400`

## callees

- `0x18002b078`
- `0x18002f3a8`

## pseudocode

```c
struct IWICComponentFactory *GetWICFactory(void)
{
  struct IWICComponentFactory *result; // rax

  result = (struct IWICComponentFactory *)qword_1800513B0;
  if ( !qword_1800513B0 )
  {
    InitWICFactory();
    return (struct IWICComponentFactory *)qword_1800513B0;
  }
  return result;
}

```

## disassembly

```asm
0x18002b078  sub     rsp, 28h
0x18002b07c  mov     rax, cs:qword_1800513B0
0x18002b083  test    rax, rax
0x18002b086  jz      short loc_18002B08E
0x18002b088  add     rsp, 28h
0x18002b08c  retn
0x18002b08e  call    ?InitWICFactory@@YAJXZ; InitWICFactory(void)
0x18002b093  mov     rax, cs:qword_1800513B0
0x18002b09a  jmp     short loc_18002B088
```
