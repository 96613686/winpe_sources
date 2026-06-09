# WPP_SF_sqqd

- ea: `0x140013ffc`
- end: `0x1400140a6`
- name: `WPP_SF_sqqd`
- size: `170`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140006db0`
- `0x140008c90`
- `0x140009010`
- `0x140009ad0`

## callees

- `0x140013ffc`
- `0x140018590`

## pseudocode

```c
__int64 WPP_SF_sqqd(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4, ...)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v8; // [rsp+A0h] [rbp+28h] BYREF
  va_list va; // [rsp+A0h] [rbp+28h]
  __int64 v10; // [rsp+A8h] [rbp+30h] BYREF
  va_list va1; // [rsp+A8h] [rbp+30h]
  va_list va2; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va2, a4);
  va_start(va1, a4);
  va_start(va, a4);
  v8 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v10 = va_arg(va2, _QWORD);
  if ( a4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a4[v5] );
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return pfnWppTraceMessage(
           a1,
           43,
           WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
           a2,
           a4,
           v6,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           8,
           va2,
           4,
           0);
}

```

## disassembly

```asm
0x140013ffc  sub     rsp, 78h
0x140014000  mov     r10, rcx
0x140014003  test    r9, r9
0x140014006  jz      short loc_14001401C
0x140014008  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001400c  inc     rax
0x14001400f  cmp     byte ptr [r9+rax], 0
0x140014014  jnz     short loc_14001400C
0x140014016  lea     rcx, [rax+1]
0x14001401a  jmp     short loc_140014021
0x14001401c  mov     ecx, 5
0x140014021  mov     [rsp+78h+var_18], 0
0x14001402a  lea     r8, [rsp+78h+arg_30]
0x140014032  mov     [rsp+78h+var_20], 4
0x14001403b  lea     rax, aNull; "NULL"
0x140014042  mov     [rsp+78h+var_28], r8
0x140014047  mov     r11d, 8
0x14001404d  mov     [rsp+78h+var_30], r11
0x140014052  lea     r8, [rsp+78h+arg_28]
0x14001405a  mov     [rsp+78h+var_38], r8
0x14001405f  test    r9, r9
0x140014062  mov     [rsp+78h+var_40], r11
0x140014067  lea     r8, [rsp+78h+arg_20]
0x14001406f  mov     [rsp+78h+var_48], r8
0x140014074  cmovz   r9, rax
0x140014078  mov     rax, cs:pfnWppTraceMessage
0x14001407f  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140014086  mov     [rsp+78h+var_50], rcx
0x14001408b  mov     rcx, r10
0x14001408e  mov     [rsp+78h+var_58], r9
0x140014093  movzx   r9d, dx
0x140014097  lea     edx, [r11+23h]
0x14001409b  call    _guard_dispatch_icall
0x1400140a0  add     rsp, 78h
0x1400140a4  retn
```
