# IsRecoverableDiskError(long)

- ea: `0x18000c840`
- end: `0x18000c874`
- name: `?IsRecoverableDiskError@@YAHJ@Z`
- size: `52`
- prototype: `_BOOL8 __fastcall(int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b50`
- `0x180006a80`
- `0x18000c430`
- `0x18000cd40`
- `0x18000f22c`

## callees

- `0x1800012e8`
- `0x18000c840`

## pseudocode

```c
_BOOL8 __fastcall IsRecoverableDiskError(int a1)
{
  _BOOL8 result; // rax

  switch ( a1 )
  {
    case -1913991167:
      return 1;
    case 21:
      return 1;
    case -2147024875:
      return 1;
    case -1073741661:
      return 1;
  }
  result = IsErrorDueToLockedVolume(a1);
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x18000c840  sub     rsp, 28h
0x18000c844  cmp     ecx, 8DEAD001h
0x18000c84a  jz      short loc_18000C86A
0x18000c84c  cmp     ecx, 15h
0x18000c84f  jz      short loc_18000C86A
0x18000c851  cmp     ecx, 80070015h
0x18000c857  jz      short loc_18000C86A
0x18000c859  cmp     ecx, 0C00000A3h
0x18000c85f  jz      short loc_18000C86A
0x18000c861  call    ?IsErrorDueToLockedVolume@@YAHJ@Z; IsErrorDueToLockedVolume(long)
0x18000c866  test    eax, eax
0x18000c868  jz      short loc_18000C86F
0x18000c86a  mov     eax, 1
0x18000c86f  add     rsp, 28h
0x18000c873  retn
```
