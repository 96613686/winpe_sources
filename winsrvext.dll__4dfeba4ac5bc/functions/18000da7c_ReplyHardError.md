# ReplyHardError

- ea: `0x18000da7c`
- end: `0x18000daea`
- name: `ReplyHardError`
- size: `110`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b9a8`
- `0x18000d030`
- `0x18000dda0`

## callees

- `0x18000beec`
- `0x18000da7c`

## import_xrefs

- `ntdll!NtSetEvent` at `0x18000dade`
- `CSRSRV!CsrDereferenceThread` at `0x18000dab5`
- `CSRSRV!CsrDereferenceThread` at `0x18000dab5`
- `CSRSRV!CsrReplyToMessage` at `0x18000da9c`
- `CSRSRV!CsrReplyToMessage` at `0x18000da9c`

## pseudocode

```c
NTSTATUS __fastcall ReplyHardError(__int64 a1, int a2)
{
  bool v2; // zf
  void *v4; // rcx

  v2 = *(_QWORD *)(a1 + 16) == 0;
  *(_DWORD *)(a1 + 84) = a2;
  if ( v2 && (*(_BYTE *)(a1 + 136) & 8) == 0 )
    CsrReplyToMessage(a1 + 24);
  if ( (*(_BYTE *)(a1 + 136) & 0x10) != 0 )
    CsrDereferenceThread(*(_QWORD *)(a1 + 8));
  v4 = *(void **)(a1 + 16);
  if ( v4 )
    return NtSetEvent(v4, 0);
  else
    return FreePhi(a1);
}

```

## disassembly

```asm
0x18000da7c  push    rbx
0x18000da7e  sub     rsp, 20h
0x18000da82  cmp     qword ptr [rcx+10h], 0
0x18000da87  mov     rbx, rcx
0x18000da8a  mov     [rcx+54h], edx
0x18000da8d  jnz     short loc_18000DAA8
0x18000da8f  test    byte ptr [rcx+88h], 8
0x18000da96  jnz     short loc_18000DAA8
0x18000da98  add     rcx, 18h
0x18000da9c  call    cs:__imp_CsrReplyToMessage
0x18000daa3  nop     dword ptr [rax+rax+00h]
0x18000daa8  test    byte ptr [rbx+88h], 10h
0x18000daaf  jz      short loc_18000DAC1
0x18000dab1  mov     rcx, [rbx+8]
0x18000dab5  call    cs:__imp_CsrDereferenceThread
0x18000dabc  nop     dword ptr [rax+rax+00h]
0x18000dac1  mov     rcx, [rbx+10h]
0x18000dac5  test    rcx, rcx
0x18000dac8  jnz     short loc_18000DAD7
0x18000daca  mov     rcx, rbx
0x18000dacd  add     rsp, 20h
0x18000dad1  pop     rbx
0x18000dad2  jmp     FreePhi
0x18000dad7  xor     edx, edx
0x18000dad9  add     rsp, 20h
0x18000dadd  pop     rbx
0x18000dade  jmp     cs:__imp_NtSetEvent
```
