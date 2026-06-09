# DllCanUnloadNow

- ea: `0x180032530`
- end: `0x18003255a`
- name: `DllCanUnloadNow`
- size: `42`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180032530`
- `0x180034a28`

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
0x180032530  sub     rsp, 28h
0x180032534  cmp     cs:?g_refcntWMPCodec@@3JA, 0; long g_refcntWMPCodec
0x18003253b  jz      short loc_180032548
0x18003253d  mov     eax, 1
0x180032542  add     rsp, 28h
0x180032546  retn
0x180032548  call    ?ReleaseWICFactory@@YAXXZ; ReleaseWICFactory(void)
0x18003254d  cmp     cs:?g_refcntWMPCodec@@3JA, 0; long g_refcntWMPCodec
0x180032554  jnz     short loc_18003253D
0x180032556  xor     eax, eax
0x180032558  jmp     short loc_180032542
```
