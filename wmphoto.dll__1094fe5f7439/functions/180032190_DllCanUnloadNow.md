# DllCanUnloadNow

- ea: `0x180032190`
- end: `0x1800321b9`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180032190`
- `0x1800343c4`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = 1;
  if ( !g_refcntWMPCodec )
  {
    ReleaseWICFactory();
    if ( !g_refcntWMPCodec )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180032190  sub     rsp, 28h
0x180032194  cmp     cs:?g_refcntWMPCodec@@3JA, 0; long g_refcntWMPCodec
0x18003219b  jz      short loc_1800321A7
0x18003219d  mov     eax, 1
0x1800321a2  add     rsp, 28h
0x1800321a6  retn
0x1800321a7  call    ?ReleaseWICFactory@@YAXXZ; ReleaseWICFactory(void)
0x1800321ac  cmp     cs:?g_refcntWMPCodec@@3JA, 0; long g_refcntWMPCodec
0x1800321b3  jnz     short loc_18003219D
0x1800321b5  xor     eax, eax
0x1800321b7  jmp     short loc_1800321A2
```
