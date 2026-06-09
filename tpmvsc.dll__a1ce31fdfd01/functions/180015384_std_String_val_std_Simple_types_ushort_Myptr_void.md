# std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)

- ea: `0x180015384`
- end: `0x18001539c`
- name: `?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ`
- size: `24`
- prototype: `__int64()`
- caller_count: `32`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ca80`
- `0x18000d320`
- `0x18000f53c`
- `0x180010298`
- `0x1800105b4`
- `0x180010e90`
- `0x1800110c0`
- `0x180012074`
- `0x180012e58`
- `0x1800135d4`
- `0x1800156bc`
- `0x180015730`
- `0x180015834`
- `0x180015c68`
- `0x1800207b4`
- `0x180023840`
- `0x180027500`
- `0x18002801c`
- `0x180028610`
- `0x180028e48`
- `0x180029000`
- `0x180029938`
- `0x180029fa0`
- `0x18002a92c`
- `0x18002aa64`
- `0x18002adec`
- `0x18002af40`
- `0x18002b4a4`
- `0x18002bd24`
- `0x18002ee4c`
- `0x180033bbc`
- `0x18003431c`

## callees

- `0x1800152e0`
- `0x180015384`

## pseudocode

```c
__int64 std::_String_val<std::_Simple_types<unsigned short>>::_Myptr()
{
  __int64 v0; // rcx

  if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged() )
    return *(_QWORD *)v0;
  return v0;
}

```

## disassembly

```asm
0x180015384  sub     rsp, 28h
0x180015388  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x18001538d  test    al, al
0x18001538f  jz      short loc_180015394
0x180015391  mov     rcx, [rcx]
0x180015394  mov     rax, rcx
0x180015397  add     rsp, 28h
0x18001539b  retn
```
