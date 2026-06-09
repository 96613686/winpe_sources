# SkeAlertThreadByThreadId

- ea: `0x140035c9c`
- end: `0x140035d51`
- name: `SkeAlertThreadByThreadId`
- size: `181`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `15`
- callee_count: `6`
- tags: ``

## callers

- `0x140002900`
- `0x14000a06c`
- `0x14000a320`
- `0x14000ae60`
- `0x14000f8b0`
- `0x140010a9c`
- `0x140014dd0`
- `0x1400298d0`
- `0x140034154`
- `0x140034c28`
- `0x140035c4c`
- `0x140066e0c`
- `0x14009749c`
- `0x140099780`
- `0x1400ff23c`

## callees

- `0x140035c9c`
- `0x140098108`
- `0x1400ee8b0`
- `0x1400f2fc0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
char __fastcall SkeAlertThreadByThreadId(__int64 a1)
{
  unsigned __int8 CurrentIrql; // bl
  char v3; // al
  __int64 v4; // rcx
  char v5; // di
  _BYTE v7[16]; // [rsp+20h] [rbp-98h] BYREF
  unsigned int v8; // [rsp+30h] [rbp-88h] BYREF
  __int64 v9; // [rsp+38h] [rbp-80h]

  memset_0(&v8, 0, 0x68u);
  v7[0] = 0;
  CurrentIrql = KeGetCurrentIrql();
  __writecr8(2u);
  v3 = SkiAlertSingleThreadByThreadId(a1, v7);
  LOBYTE(v4) = CurrentIrql;
  v5 = v3;
  SkeLowerIrql(v4);
  if ( v7[0] )
  {
    v9 = *(_QWORD *)(a1 + 136);
    BYTE1(v8) = 0;
    HIWORD(v8) = 7;
    SkCallNormalMode(&v8);
  }
  return v5;
}

```

## disassembly

```asm
0x140035c9c  mov     [rsp+arg_8], rbx
0x140035ca1  mov     [rsp+arg_10], rsi
0x140035ca6  push    rdi
0x140035ca7  sub     rsp, 0B0h
0x140035cae  mov     rax, cs:__security_cookie
0x140035cb5  xor     rax, rsp
0x140035cb8  mov     [rsp+0B8h+var_18], rax
0x140035cc0  xor     edx, edx; Val
0x140035cc2  mov     rsi, rcx
0x140035cc5  lea     rcx, [rsp+0B8h+var_88]; void *
0x140035cca  lea     r8d, [rdx+68h]; Size
0x140035cce  call    memset_0
0x140035cd3  mov     [rsp+0B8h+var_98], 0
0x140035cd8  mov     rbx, cr8
0x140035cdc  mov     eax, 2
0x140035ce1  mov     cr8, rax
0x140035ce5  lea     rdx, [rsp+0B8h+var_98]
0x140035cea  mov     rcx, rsi
0x140035ced  call    SkiAlertSingleThreadByThreadId
0x140035cf2  mov     cl, bl
0x140035cf4  mov     dil, al
0x140035cf7  call    SkeLowerIrql
0x140035cfc  cmp     [rsp+0B8h+var_98], 0
0x140035d01  jz      short loc_140035D28
0x140035d03  mov     rcx, [rsi+88h]
0x140035d0a  mov     eax, 7
0x140035d0f  mov     [rsp+0B8h+var_80], rcx
0x140035d14  lea     rcx, [rsp+0B8h+var_88]
0x140035d19  mov     [rsp+0B8h+var_87], 0
0x140035d1e  mov     [rsp+0B8h+var_86], ax
0x140035d23  call    SkCallNormalMode
0x140035d28  mov     al, dil
0x140035d2b  mov     rcx, [rsp+0B8h+var_18]
0x140035d33  xor     rcx, rsp; StackCookie
0x140035d36  call    __security_check_cookie
0x140035d3b  lea     r11, [rsp+0B8h+var_8]
0x140035d43  mov     rbx, [r11+18h]
0x140035d47  mov     rsi, [r11+20h]
0x140035d4b  mov     rsp, r11
0x140035d4e  pop     rdi
0x140035d4f  retn
```
