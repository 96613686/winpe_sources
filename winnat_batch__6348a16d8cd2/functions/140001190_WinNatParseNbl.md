# WinNatParseNbl

- ea: `0x140001190`
- end: `0x1400011d6`
- name: `WinNatParseNbl`
- size: `70`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000c328`
- `0x14001c210`
- `0x14001c4e4`
- `0x14001c974`
- `0x14001cef8`
- `0x14001d87c`

## callees

- `0x140001190`
- `0x1400011e0`
- `0x14000caa0`

## pseudocode

```c
char __fastcall WinNatParseNbl(__int64 a1, __int64 *a2, char a3, unsigned __int16 a4)
{
  if ( **(_QWORD **)(a1 + 8) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  return WinNatParseNb(*(PNET_BUFFER *)(a1 + 8), a2, a3, a4);
}

```

## disassembly

```asm
0x140001190  push    rbx
0x140001192  push    rbp
0x140001193  push    rsi
0x140001194  push    rdi
0x140001195  sub     rsp, 28h
0x140001199  mov     rax, [rcx+8]
0x14000119d  movzx   edi, r9w
0x1400011a1  movzx   esi, r8b
0x1400011a5  mov     rbp, rdx
0x1400011a8  mov     rbx, rcx
0x1400011ab  cmp     qword ptr [rax], 0
0x1400011af  jnz     short loc_1400011CF
0x1400011b1  mov     rcx, [rbx+8]; NetBuffer
0x1400011b5  movzx   r9d, di
0x1400011b9  movzx   r8d, sil
0x1400011bd  mov     rdx, rbp
0x1400011c0  call    WinNatParseNb
0x1400011c5  add     rsp, 28h
0x1400011c9  pop     rdi
0x1400011ca  pop     rsi
0x1400011cb  pop     rbp
0x1400011cc  pop     rbx
0x1400011cd  retn
0x1400011cf  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400011d4  jmp     short loc_1400011B1
```
