# __security_check_cookie

- ea: `0x1800155c0`
- end: `0x1800155de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `38`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010b0`
- `0x1800011c8`
- `0x1800013bc`
- `0x1800014c4`
- `0x180001608`
- `0x18000173c`
- `0x180001a00`
- `0x180002d20`
- `0x180004b80`
- `0x180005230`
- `0x1800057f0`
- `0x180005c60`
- `0x180008b50`
- `0x18000a580`
- `0x18000b870`
- `0x18000b960`
- `0x18000c584`
- `0x18000c760`
- `0x18000cb14`
- `0x18000cec8`
- `0x18000e43c`
- `0x1800104b0`
- `0x180010870`
- `0x1800120e4`
- `0x1800131b0`
- `0x180013290`
- `0x1800133f0`
- `0x180013600`
- `0x180013990`
- `0x180013c70`
- `0x180013e30`
- `0x180013fa0`
- `0x1800140f0`
- `0x180014230`
- `0x180014c74`
- `0x180015488`
- `0x1800154fc`

## callees

- `0x180007030`
- `0x1800155c0`

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
0x1800155c0  cmp     rcx, cs:__security_cookie
0x1800155c7  jnz     short ReportFailure
0x1800155c9  rol     rcx, 10h
0x1800155cd  test    cx, 0FFFFh
0x1800155d2  jnz     short RestoreRcx
0x1800155d4  retn
0x1800155d5  ror     rcx, 10h
0x1800155d9  jmp     __report_gsfailure
```
