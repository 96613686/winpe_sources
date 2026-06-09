# TdxTraceConnectionRoutine

- ea: `0x14000fc90`
- end: `0x14000fcde`
- name: `TdxTraceConnectionRoutine`
- size: `78`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003c9c`
- `0x140013460`
- `0x1400135a0`

## callees

- `0x14000fc90`
- `0x140013bf8`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall TdxTraceConnectionRoutine(__int64 a1, __int64 a2)
{
  PDEVICE_OBJECT *result; // rax

  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    return (PDEVICE_OBJECT *)WPP_SF_qs(
                               (__int64)WPP_GLOBAL_Control->AttachedDevice,
                               0xBu,
                               (__int64)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
                               a1,
                               a2);
  }
  return result;
}

```

## disassembly

```asm
0x14000fc90  sub     rsp, 38h
0x14000fc94  mov     r8, rdx
0x14000fc97  mov     r9, rcx
0x14000fc9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fca1  lea     rax, WPP_GLOBAL_Control
0x14000fca8  cmp     rcx, rax
0x14000fcab  jz      short loc_14000FCB3
0x14000fcad  cmp     byte ptr [rcx+29h], 5
0x14000fcb1  jnb     short loc_14000FCB9
0x14000fcb3  add     rsp, 38h
0x14000fcb7  retn
0x14000fcb9  test    dword ptr [rcx+2Ch], 200h
0x14000fcc0  jz      short loc_14000FCB3
0x14000fcc2  mov     rcx, [rcx+18h]
0x14000fcc6  mov     edx, 0Bh
0x14000fccb  mov     [rsp+38h+var_18], r8
0x14000fcd0  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x14000fcd7  call    WPP_SF_qs
0x14000fcdc  jmp     short loc_14000FCB3
```
