# WPP_SF_

- ea: `0x14000d8ec`
- end: `0x14000d914`
- name: `WPP_SF_`
- size: `40`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `68`
- callee_count: `1`
- tags: ``

## callers

- `0x140001008`
- `0x140001174`
- `0x14000204c`
- `0x14000228c`
- `0x14000253c`
- `0x140002710`
- `0x1400027d0`
- `0x140002c90`
- `0x14000317c`
- `0x1400033f0`
- `0x140003634`
- `0x140003854`
- `0x1400038f0`
- `0x140003b7c`
- `0x140003fe8`
- `0x1400040d8`
- `0x1400041a0`
- `0x14000448c`
- `0x140004568`
- `0x140004c50`
- `0x140004d70`
- `0x140005108`
- `0x1400053c8`
- `0x140005630`
- `0x140005968`
- `0x140005bf0`
- `0x140006790`
- `0x1400069a0`
- `0x140006bc0`
- `0x14000745c`
- `0x140007d58`
- `0x140007f70`
- `0x1400080f0`
- `0x140008570`
- `0x1400087b0`
- `0x140008cf0`
- `0x140009740`
- `0x1400097e4`
- `0x140009bec`
- `0x140009e70`
- `0x14000a260`
- `0x14000ae50`
- `0x14000aef0`
- `0x14000b558`
- `0x14000b600`
- `0x14000b6e0`
- `0x14000b790`
- `0x14000b8d0`
- `0x14000bc28`
- `0x14000bfb8`

## callees

- `0x14000f150`

## pseudocode

```c
__int64 __fastcall WPP_SF_(__int64 a1, unsigned __int16 a2, __int64 a3)
{
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, _QWORD))pfnWppTraceMessage)(a1, 43, a3, a2, 0);
}

```

## disassembly

```asm
0x14000d8ec  sub     rsp, 38h
0x14000d8f0  mov     rax, cs:pfnWppTraceMessage
0x14000d8f7  movzx   r9d, dx
0x14000d8fb  mov     edx, 2Bh ; '+'
0x14000d900  mov     [rsp+38h+var_18], 0
0x14000d909  call    _guard_dispatch_icall
0x14000d90e  add     rsp, 38h
0x14000d912  retn
```
