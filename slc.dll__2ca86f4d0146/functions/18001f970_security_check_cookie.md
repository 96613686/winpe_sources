# __security_check_cookie

- ea: `0x18001f970`
- end: `0x18001f98e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800167ac`
- `0x18001e540`
- `0x18001f8b0`

## callees

- `0x18001cae0`
- `0x18001f970`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie == _security_cookie )
  {
    v1 = __ROL8__(StackCookie, 16);
    if ( !(_WORD)v1 )
      return;
    StackCookie = __ROR8__(v1, 16);
  }
  sub_18001CAE0(StackCookie);
}

```

## disassembly

```asm
0x18001f970  cmp     rcx, cs:__security_cookie
0x18001f977  jnz     short ReportFailure
0x18001f979  rol     rcx, 10h
0x18001f97d  test    cx, 0FFFFh
0x18001f982  jnz     short RestoreRcx
0x18001f984  retn
0x18001f985  ror     rcx, 10h
0x18001f989  jmp     sub_18001CAE0
```
