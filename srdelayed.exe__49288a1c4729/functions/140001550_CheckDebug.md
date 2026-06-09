# CheckDebug

- ea: `0x140001550`
- end: `0x140001566`
- name: `CheckDebug`
- size: `22`
- prototype: `__int64 __fastcall(__int64, int, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001550`

## pseudocode

```c
__int64 __fastcall CheckDebug(__int64 a1, int a2, _DWORD *a3)
{
  if ( a2 == 4 && *a3 )
  {
    g_fDebug = 1;
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x140001550  cmp     edx, 4
0x140001553  jnz     short loc_140001563
0x140001555  cmp     dword ptr [r8], 0
0x140001559  jz      short loc_140001563
0x14000155b  mov     cs:g_fDebug, 1
0x140001562  int     3; Trap to Debugger
0x140001563  xor     eax, eax
0x140001565  retn
```
