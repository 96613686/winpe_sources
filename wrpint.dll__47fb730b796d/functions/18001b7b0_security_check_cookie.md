# __security_check_cookie

- ea: `0x18001b7b0`
- end: `0x18001b7ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `114`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001e20`
- `0x180002024`
- `0x1800029a4`
- `0x180002a50`
- `0x180002d00`
- `0x1800031c0`
- `0x1800036e0`
- `0x180003a40`
- `0x180003df0`
- `0x18000423c`
- `0x1800043ac`
- `0x180004680`
- `0x1800048bc`
- `0x180004abc`
- `0x180004bfc`
- `0x180005260`
- `0x180005540`
- `0x1800056a0`
- `0x180005920`
- `0x1800061c0`
- `0x1800064f0`
- `0x180006660`
- `0x1800067ac`
- `0x180006e50`
- `0x180006f84`
- `0x180007178`
- `0x180007288`
- `0x180007424`
- `0x180007ae0`
- `0x180009e30`
- `0x18000ac9c`
- `0x18000af30`
- `0x18000b794`
- `0x18000bb64`
- `0x18000bf5c`
- `0x18000c254`
- `0x18000c3f8`
- `0x18000caf4`
- `0x18000ce6c`
- `0x18000d140`
- `0x18000d770`
- `0x18000d810`
- `0x18000db10`
- `0x18000ddb8`
- `0x18000e048`
- `0x18000e09c`
- `0x18000e0f4`
- `0x18000e1ac`
- `0x18000e75c`

## callees

- `0x180001b30`
- `0x18001b7b0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x18001b7b0  cmp     rcx, cs:__security_cookie
0x18001b7b7  jnz     short ReportFailure
0x18001b7b9  rol     rcx, 10h
0x18001b7bd  test    cx, 0FFFFh
0x18001b7c2  jnz     short RestoreRcx
0x18001b7c4  retn
0x18001b7c5  ror     rcx, 10h
0x18001b7c9  jmp     __report_gsfailure
```
