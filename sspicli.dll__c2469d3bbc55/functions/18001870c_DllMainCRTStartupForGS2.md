# _DllMainCRTStartupForGS2

- ea: `0x18001870c`
- end: `0x180018724`
- name: `_DllMainCRTStartupForGS2`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c7f0`

## callees

- `0x18001870c`
- `0x180018abc`

## pseudocode

```c
__int64 __fastcall DllMainCRTStartupForGS2(__int64 a1, int a2)
{
  if ( a2 == 1 )
    _security_init_cookie();
  return 1;
}

```

## disassembly

```asm
0x18001870c  sub     rsp, 28h
0x180018710  cmp     edx, 1
0x180018713  jnz     short loc_18001871A
0x180018715  call    __security_init_cookie
0x18001871a  mov     eax, 1
0x18001871f  add     rsp, 28h
0x180018723  retn
```
