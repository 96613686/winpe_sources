# EnumThreadWinCallback

- ea: `0x18000d060`
- end: `0x18000d065`
- name: `EnumThreadWinCallback`
- size: `5`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall EnumThreadWinCallback(HWND a1, _DWORD *a2)
{
  ++*a2;
  return 0;
}

```

## disassembly

```asm
0x18000d060  inc     dword ptr [rdx]
0x18000d062  xor     eax, eax
0x18000d064  retn
```
