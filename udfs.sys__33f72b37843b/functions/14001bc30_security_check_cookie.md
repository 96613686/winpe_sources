# __security_check_cookie

- ea: `0x14001bc30`
- end: `0x14001bc4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `48`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003148`
- `0x1400039fc`
- `0x1400041e0`
- `0x1400050d8`
- `0x14000a870`
- `0x14000aadc`
- `0x14000cbcc`
- `0x14000efc8`
- `0x1400116bc`
- `0x140014cb8`
- `0x140015e90`
- `0x1400177ac`
- `0x140017fa8`
- `0x14001bb2c`
- `0x14002fc98`
- `0x140031080`
- `0x140031b04`
- `0x140031d9c`
- `0x14003269c`
- `0x140033548`
- `0x140034450`
- `0x140037ba8`
- `0x140037f1c`
- `0x140038afc`
- `0x140039600`
- `0x140039938`
- `0x14003aa44`
- `0x14003b608`
- `0x14003cf8c`
- `0x14003d0c4`
- `0x14003d194`
- `0x14003d288`
- `0x14003ebc0`
- `0x14003f4c8`
- `0x1400401a0`
- `0x140040d34`
- `0x1400413f0`
- `0x140042c40`
- `0x14004628c`
- `0x140046750`
- `0x140049f80`
- `0x14004bdc0`
- `0x140055cd0`
- `0x140058d88`
- `0x140059a34`
- `0x14005d350`
- `0x14005d4f4`
- `0x14005dad8`

## callees

- `0x14000e650`
- `0x14001bc30`

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
0x14001bc30  cmp     rcx, cs:__security_cookie
0x14001bc37  jnz     short ReportFailure
0x14001bc39  rol     rcx, 10h
0x14001bc3d  test    cx, 0FFFFh
0x14001bc42  jnz     short RestoreRcx
0x14001bc44  retn
0x14001bc45  ror     rcx, 10h; StackCookie
0x14001bc49  jmp     __report_gsfailure
```
