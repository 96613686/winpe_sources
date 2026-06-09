# __security_check_cookie

- ea: `0x1400f3620`
- end: `0x1400f363e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `313`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003860`
- `0x140006b20`
- `0x140007170`
- `0x140008ec4`
- `0x1400091e0`
- `0x14000bab0`
- `0x14000d060`
- `0x14000d660`
- `0x14000dcd0`
- `0x14000e4b0`
- `0x14000facc`
- `0x1400118d0`
- `0x140012380`
- `0x140012498`
- `0x140012620`
- `0x140012750`
- `0x140013200`
- `0x1400136dc`
- `0x1400139c0`
- `0x1400149b4`
- `0x140014dd0`
- `0x14001bcfc`
- `0x14001ca04`
- `0x14001d0ac`
- `0x14001e71c`
- `0x14001ed6c`
- `0x140020360`
- `0x1400204a0`
- `0x140021428`
- `0x140021ce8`
- `0x140026240`
- `0x1400280b0`
- `0x140029308`
- `0x14002a0b0`
- `0x14002bdf4`
- `0x14002e70c`
- `0x14002eabc`
- `0x14003228c`
- `0x140033b58`
- `0x140034988`
- `0x1400351c0`
- `0x140035474`
- `0x140035c9c`
- `0x140036b08`
- `0x140036ea8`
- `0x140037c60`
- `0x140037fe4`
- `0x1400393a4`
- `0x14003acd8`
- `0x14003bfac`

## callees

- `0x14003bf68`
- `0x1400f3620`

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
0x1400f3620  cmp     rcx, cs:__security_cookie
0x1400f3627  jnz     short ReportFailure
0x1400f3629  rol     rcx, 10h
0x1400f362d  test    cx, 0FFFFh
0x1400f3632  jnz     short RestoreRcx
0x1400f3634  retn
0x1400f3635  ror     rcx, 10h; StackCookie
0x1400f3639  jmp     __report_gsfailure
```
