# I_MapSecurityStatusToWinError(long)

- ea: `0x18001a31c`
- end: `0x18001a35f`
- name: `?I_MapSecurityStatusToWinError@@YAKJ@Z`
- size: `67`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `18`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800183b8`
- `0x1800188ac`
- `0x1800194c8`
- `0x18001a49c`
- `0x18001ec10`
- `0x18001f784`
- `0x18001fc4c`
- `0x1800201f0`
- `0x1800203fc`
- `0x180020cf0`
- `0x180021214`
- `0x1800215d0`
- `0x180021be0`
- `0x180022e80`
- `0x180023840`
- `0x180028610`
- `0x18002893c`
- `0x180029938`

## callees

- `0x18001a31c`

## pseudocode

```c
__int64 __fastcall I_MapSecurityStatusToWinError(unsigned int a1)
{
  switch ( a1 )
  {
    case 0x80090009:
      return 2148532228LL;
    case 0x80090010:
      return 2148532331LL;
    case 0x80090027:
      return 2148532228LL;
    case 0x80090029:
      return 2148532258LL;
    case 0x80090031:
      return 2148532332LL;
  }
  return a1;
}

```

## disassembly

```asm
0x18001a31c  cmp     ecx, 80090009h
0x18001a322  jz      short loc_18001A359
0x18001a324  cmp     ecx, 80090010h
0x18001a32a  jz      short loc_18001A353
0x18001a32c  cmp     ecx, 80090027h
0x18001a332  jz      short loc_18001A359
0x18001a334  cmp     ecx, 80090029h
0x18001a33a  jz      short loc_18001A34D
0x18001a33c  cmp     ecx, 80090031h
0x18001a342  jz      short loc_18001A347
0x18001a344  mov     eax, ecx
0x18001a346  retn
0x18001a347  mov     eax, 8010006Ch
0x18001a34c  retn
0x18001a34d  mov     eax, 80100022h
0x18001a352  retn
0x18001a353  mov     eax, 8010006Bh
0x18001a358  retn
0x18001a359  mov     eax, 80100004h
0x18001a35e  retn
```
