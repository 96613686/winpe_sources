# __security_check_cookie

- ea: `0x1800157f0`
- end: `0x18001580e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `44`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e6c`
- `0x180001fbc`
- `0x1800029d8`
- `0x180002e9c`
- `0x1800046f0`
- `0x180004928`
- `0x180004e20`
- `0x18000572c`
- `0x180005e30`
- `0x1800062e8`
- `0x180006840`
- `0x180006b50`
- `0x180007534`
- `0x180007c30`
- `0x1800088ac`
- `0x180008b98`
- `0x180008ce8`
- `0x180008e78`
- `0x18000902c`
- `0x1800098b4`
- `0x180009a6c`
- `0x180009d8c`
- `0x18000a790`
- `0x18000b3b0`
- `0x18000ca98`
- `0x18000d69c`
- `0x18000d800`
- `0x18000deac`
- `0x18000ea60`
- `0x18000ee14`
- `0x18000f310`
- `0x18000fcb8`
- `0x18000ff54`
- `0x18001078c`
- `0x180010b30`
- `0x180010f00`
- `0x180011964`
- `0x180011cdc`
- `0x18001291c`
- `0x180012b9c`
- `0x180013468`
- `0x1800141ac`
- `0x180014ae0`
- `0x180015590`

## callees

- `0x1800018d0`
- `0x1800157f0`

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
0x1800157f0  cmp     rcx, cs:__security_cookie
0x1800157f7  jnz     short ReportFailure
0x1800157f9  rol     rcx, 10h
0x1800157fd  test    cx, 0FFFFh
0x180015802  jnz     short RestoreRcx
0x180015804  retn
0x180015805  ror     rcx, 10h
0x180015809  jmp     __report_gsfailure
```
