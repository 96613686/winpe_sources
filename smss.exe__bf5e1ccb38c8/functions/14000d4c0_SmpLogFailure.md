# SmpLogFailure

- ea: `0x14000d4c0`
- end: `0x14000d535`
- name: `SmpLogFailure`
- size: `117`
- prototype: ``
- caller_count: `41`
- callee_count: `3`
- tags: ``

## callers

- `0x140001580`
- `0x140001f60`
- `0x1400027a0`
- `0x140002bb0`
- `0x1400036d0`
- `0x1400041d0`
- `0x1400050a0`
- `0x140005f64`
- `0x140006680`
- `0x140006f30`
- `0x140008470`
- `0x140009930`
- `0x14000b514`
- `0x14000c638`
- `0x14000d53c`
- `0x14000d92c`
- `0x14000da48`
- `0x14000f120`
- `0x14000f6f4`
- `0x14000fa74`
- `0x14000fcf8`
- `0x14000fed0`
- `0x1400101ec`
- `0x140010344`
- `0x1400107e8`
- `0x140010dc8`
- `0x14001106c`
- `0x140011158`
- `0x140013a40`
- `0x140014100`
- `0x1400146ac`
- `0x140014e2c`
- `0x140014f30`
- `0x1400151e0`
- `0x1400153bc`
- `0x140015660`
- `0x140016018`
- `0x140017954`
- `0x140017a30`
- `0x140017ad0`
- `0x140017c70`

## callees

- `0x140005998`
- `0x14001cc29`
- `0x14001cc40`

## pseudocode

```c
__int64 __fastcall SmpLogFailure(__int64 a1, unsigned int a2, unsigned int a3)
{
  _BYTE v7[224]; // [rsp+20h] [rbp-F8h] BYREF

  memset_0(v7, 0, sizeof(v7));
  return SmpInternalLogFailure(a1, a2, a3, v7);
}

```

## disassembly

```asm
0x14000d4c0  mov     [rsp+arg_8], rbx
0x14000d4c5  mov     [rsp+arg_10], rsi
0x14000d4ca  push    rdi
0x14000d4cb  sub     rsp, 110h
0x14000d4d2  mov     rax, cs:__security_cookie
0x14000d4d9  xor     rax, rsp
0x14000d4dc  mov     [rsp+118h+var_18], rax
0x14000d4e4  mov     ebx, r8d
0x14000d4e7  mov     edi, edx
0x14000d4e9  mov     rsi, rcx
0x14000d4ec  xor     edx, edx; Val
0x14000d4ee  mov     r8d, 0E0h; Size
0x14000d4f4  lea     rcx, [rsp+118h+var_F8]; void *
0x14000d4f9  call    memset_0
0x14000d4fe  lea     r9, [rsp+118h+var_F8]
0x14000d503  mov     r8d, ebx
0x14000d506  mov     edx, edi
0x14000d508  mov     rcx, rsi
0x14000d50b  call    SmpInternalLogFailure
0x14000d510  mov     rcx, [rsp+118h+var_18]
0x14000d518  xor     rcx, rsp; StackCookie
0x14000d51b  call    __security_check_cookie
0x14000d520  lea     r11, [rsp+118h+var_8]
0x14000d528  mov     rbx, [r11+18h]
0x14000d52c  mov     rsi, [r11+20h]
0x14000d530  mov     rsp, r11
0x14000d533  pop     rdi
0x14000d534  retn
```
