# WPP_SF_sqs

- ea: `0x1400130bc`
- end: `0x14001316d`
- name: `WPP_SF_sqs`
- size: `177`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400012b0`
- `0x140002fb0`
- `0x140004df4`
- `0x1400126e4`

## callees

- `0x1400130bc`
- `0x140018590`

## pseudocode

```c
__int64 __fastcall WPP_SF_sqs(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4, char a5, const char *a6)
{
  const char *v6; // r11
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // r10
  __int64 v10; // r10
  bool v11; // zf

  v6 = a6;
  v7 = -1;
  v8 = 5;
  if ( a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a6[v9] );
    v10 = v9 + 1;
  }
  else
  {
    v10 = 5;
  }
  if ( !a6 )
    v6 = "NULL";
  v11 = a4 == 0;
  if ( a4 )
  {
    do
      ++v7;
    while ( a4[v7] );
    v8 = v7 + 1;
    v11 = a4 == 0;
  }
  if ( v11 )
    a4 = "NULL";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, const char *, __int64, char *, __int64, const char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           a4,
           v8,
           &a5,
           8,
           v6,
           v10,
           0);
}

```

## disassembly

```asm
0x1400130bc  mov     [rsp+arg_0], rbx
0x1400130c1  push    rsi
0x1400130c2  sub     rsp, 60h
0x1400130c6  mov     r11, [rsp+68h+arg_28]
0x1400130ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400130d2  mov     ebx, 5
0x1400130d7  test    r11, r11
0x1400130da  jz      short loc_1400130EE
0x1400130dc  mov     r10, rax
0x1400130df  inc     r10
0x1400130e2  cmp     byte ptr [r11+r10], 0
0x1400130e7  jnz     short loc_1400130DF
0x1400130e9  inc     r10
0x1400130ec  jmp     short loc_1400130F1
0x1400130ee  mov     r10, rbx
0x1400130f1  test    r11, r11
0x1400130f4  lea     rsi, aNull; "NULL"
0x1400130fb  cmovz   r11, rsi
0x1400130ff  test    r9, r9
0x140013102  jz      short loc_140013115
0x140013104  inc     rax
0x140013107  cmp     byte ptr [r9+rax], 0
0x14001310c  jnz     short loc_140013104
0x14001310e  lea     rbx, [rax+1]
0x140013112  test    r9, r9
0x140013115  mov     rax, cs:pfnWppTraceMessage
0x14001311c  cmovz   r9, rsi
0x140013120  mov     [rsp+68h+var_18], 0
0x140013129  mov     [rsp+68h+var_20], r10
0x14001312e  lea     r10, [rsp+68h+arg_20]
0x140013136  mov     [rsp+68h+var_28], r11
0x14001313b  mov     [rsp+68h+var_30], 8
0x140013144  mov     [rsp+68h+var_38], r10
0x140013149  mov     [rsp+68h+var_40], rbx
0x14001314e  mov     [rsp+68h+var_48], r9
0x140013153  movzx   r9d, dx
0x140013157  mov     edx, 2Bh ; '+'
0x14001315c  call    _guard_dispatch_icall
0x140013161  mov     rbx, [rsp+68h+arg_0]
0x140013166  add     rsp, 60h
0x14001316a  pop     rsi
0x14001316b  retn
```
