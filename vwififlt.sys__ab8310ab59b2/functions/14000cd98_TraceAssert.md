# TraceAssert

- ea: `0x14000cd98`
- end: `0x14000cdd2`
- name: `TraceAssert`
- size: `58`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `42`
- callee_count: `2`
- tags: ``

## callers

- `0x140001008`
- `0x14000253c`
- `0x140002c90`
- `0x1400033f0`
- `0x1400038f0`
- `0x140003fe8`
- `0x1400041a0`
- `0x14000443c`
- `0x140004568`
- `0x140005630`
- `0x1400057f8`
- `0x140005bf0`
- `0x140006960`
- `0x140006bc0`
- `0x140007d58`
- `0x140007f70`
- `0x140008570`
- `0x1400087b0`
- `0x140008cf0`
- `0x1400097e4`
- `0x140009bec`
- `0x140009e70`
- `0x14000a4e0`
- `0x14000a7c0`
- `0x14000a880`
- `0x14000ab50`
- `0x14000aef0`
- `0x14000b600`
- `0x14000b790`
- `0x14000b8d0`
- `0x14000bc28`
- `0x14000bfb8`
- `0x14000c7b0`
- `0x14000cebc`
- `0x14000d0a4`
- `0x14000d3a0`
- `0x14000d690`
- `0x14000e158`
- `0x14000e6e0`
- `0x14000e7b0`
- `0x14000e880`
- `0x140019078`

## callees

- `0x14000cd98`
- `0x14000eed4`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall TraceAssert(int a1, __int64 a2, int a3)
{
  PDEVICE_OBJECT *result; // rax

  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = (PDEVICE_OBJECT *)HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)result & 2) != 0 )
      return (PDEVICE_OBJECT *)WPP_SF_ssL(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x14000cd98  sub     rsp, 38h
0x14000cd9c  mov     r9, rcx
0x14000cd9f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cda6  lea     rax, WPP_GLOBAL_Control
0x14000cdad  cmp     rcx, rax
0x14000cdb0  jz      short loc_14000CDCC
0x14000cdb2  mov     eax, [rcx+2Ch]
0x14000cdb5  test    al, 2
0x14000cdb7  jz      short loc_14000CDCC
0x14000cdb9  mov     rcx, [rcx+18h]
0x14000cdbd  mov     [rsp+38h+var_10], r8d
0x14000cdc2  mov     [rsp+38h+var_18], rdx
0x14000cdc7  call    WPP_SF_ssL
0x14000cdcc  add     rsp, 38h
0x14000cdd0  retn
```
