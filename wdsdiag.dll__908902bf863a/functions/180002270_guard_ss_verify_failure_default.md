# __guard_ss_verify_failure_default

- ea: `0x180002270`
- end: `0x1800022b6`
- name: `__guard_ss_verify_failure_default`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002240`

## callees

- `0x180002270`

## pseudocode

```c
void __noreturn _guard_ss_verify_failure_default()
{
  __fastfail(0x2Cu);
}

```

## disassembly

```asm
0x180002270  mov     rax, r11
0x180002273  and     rax, 7
0x180002277  test    eax, eax
0x180002279  jnz     short loc_18000228B
0x18000227b  mov     rdx, [rsp+0]
0x18000227f  mov     r8, fs:[rsp]
0x180002284  mov     ecx, 2Ch ; ','
0x180002289  int     29h; Win8: RtlFailFast(ecx)
0x18000228b  cmp     al, 3
0x18000228d  jz      short loc_1800022AE
0x18000228f  mov     r8, rcx
0x180002292  cmp     al, 1
0x180002294  jz      short loc_1800022AE
0x180002296  mov     r8, rdx
0x180002299  cmp     al, 2
0x18000229b  jz      short loc_1800022AE
0x18000229d  mov     r8, r9
0x1800022a0  cmp     al, 4
0x1800022a2  jz      short loc_1800022AE
0x1800022a4  mov     r8, r10
0x1800022a7  cmp     al, 5
0x1800022a9  jz      short loc_1800022AE
0x1800022ab  xor     r8, r8
0x1800022ae  xor     r11, rax
0x1800022b1  mov     rdx, [r11]
0x1800022b4  jmp     short loc_180002284
```
