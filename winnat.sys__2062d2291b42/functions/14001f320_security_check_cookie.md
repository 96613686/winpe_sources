# __security_check_cookie

- ea: `0x14001f320`
- end: `0x14001f33e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `91`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400011e0`
- `0x1400020e0`
- `0x140003830`
- `0x140004094`
- `0x140004648`
- `0x140004ed0`
- `0x1400052d0`
- `0x140006f04`
- `0x140007610`
- `0x140007bb0`
- `0x140008df0`
- `0x1400091e0`
- `0x1400093f0`
- `0x14000975c`
- `0x140009b04`
- `0x14000a9d0`
- `0x14000ae68`
- `0x14000b220`
- `0x14000bdf0`
- `0x14000c328`
- `0x14000cad4`
- `0x14000d700`
- `0x14000d7c8`
- `0x14000e1ac`
- `0x14000e3e8`
- `0x14000e4b0`
- `0x14000e538`
- `0x14000e6a8`
- `0x14000e790`
- `0x14000e9b0`
- `0x14000eb80`
- `0x14000ee98`
- `0x14000f480`
- `0x14000fce8`
- `0x140010b24`
- `0x140011420`
- `0x140012048`
- `0x14001263c`
- `0x140012db8`
- `0x140012fb4`
- `0x1400130f4`
- `0x1400134dc`
- `0x140014480`
- `0x140014548`
- `0x1400146b0`
- `0x140014830`
- `0x1400148fc`
- `0x1400149bc`
- `0x140014b60`
- `0x140014dcc`

## callees

- `0x14000d7b0`
- `0x14001f320`

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
0x14001f320  cmp     rcx, cs:__security_cookie
0x14001f327  jnz     short ReportFailure
0x14001f329  rol     rcx, 10h
0x14001f32d  test    cx, 0FFFFh
0x14001f332  jnz     short RestoreRcx
0x14001f334  retn
0x14001f335  ror     rcx, 10h; StackCookie
0x14001f339  jmp     __report_gsfailure
```
