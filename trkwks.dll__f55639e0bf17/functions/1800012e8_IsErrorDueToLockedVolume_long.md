# IsErrorDueToLockedVolume(long)

- ea: `0x1800012e8`
- end: `0x180001316`
- name: `?IsErrorDueToLockedVolume@@YAHJ@Z`
- size: `46`
- prototype: `_BOOL8 __fastcall(int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x180002b50`
- `0x180003798`
- `0x180006a80`
- `0x18000c430`
- `0x18000c840`
- `0x18000cd40`
- `0x18000f22c`

## callees

- `0x1800012e8`

## pseudocode

```c
_BOOL8 __fastcall IsErrorDueToLockedVolume(int a1)
{
  return a1 == -1073741202 || a1 == -1073741790 || a1 == 5 || a1 == -2147024891 || a1 == -2147024786;
}

```

## disassembly

```asm
0x1800012e8  cmp     ecx, 0C000026Eh
0x1800012ee  jz      short loc_180001310
0x1800012f0  cmp     ecx, 0C0000022h
0x1800012f6  jz      short loc_180001310
0x1800012f8  cmp     ecx, 5
0x1800012fb  jz      short loc_180001310
0x1800012fd  cmp     ecx, 80070005h
0x180001303  jz      short loc_180001310
0x180001305  cmp     ecx, 8007006Eh
0x18000130b  jz      short loc_180001310
0x18000130d  xor     eax, eax
0x18000130f  retn
0x180001310  mov     eax, 1
0x180001315  retn
```
