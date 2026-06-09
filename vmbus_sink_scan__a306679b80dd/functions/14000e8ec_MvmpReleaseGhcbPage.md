# MvmpReleaseGhcbPage

- ea: `0x14000e8ec`
- end: `0x14000e90a`
- name: `MvmpReleaseGhcbPage`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x14000aae0`
- `0x14000ada0`
- `0x14000d300`
- `0x14000d410`
- `0x14000d620`
- `0x14000d704`
- `0x14000d910`
- `0x14000da50`
- `0x14000dbc0`
- `0x14000e408`

## callees

- `0x14000b42c`
- `0x14000e8ec`

## pseudocode

```c
__int64 __fastcall MvmpReleaseGhcbPage(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = a2;
  if ( a2 )
    return MvmUnmapPage(a2, *(_QWORD *)(a1 + 64));
  return result;
}

```

## disassembly

```asm
0x14000e8ec  sub     rsp, 28h
0x14000e8f0  mov     rax, rdx
0x14000e8f3  test    rdx, rdx
0x14000e8f6  jz      short loc_14000E904
0x14000e8f8  mov     rdx, [rcx+40h]
0x14000e8fc  mov     rcx, rax
0x14000e8ff  call    MvmUnmapPage
0x14000e904  add     rsp, 28h
0x14000e908  retn
```
