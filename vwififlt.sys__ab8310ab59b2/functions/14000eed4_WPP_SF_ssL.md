# WPP_SF_ssL

- ea: `0x14000eed4`
- end: `0x14000ef83`
- name: `WPP_SF_ssL`
- size: `175`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140008e70`
- `0x140009300`
- `0x14000a880`
- `0x14000aef0`
- `0x14000cd98`

## callees

- `0x14000eed4`
- `0x14000f150`

## pseudocode

```c
__int64 WPP_SF_ssL(__int64 a1, __int64 a2, __int64 a3, const char *a4, const char *a5, ...)
{
  const char *v5; // rdx
  __int64 v6; // rax
  __int64 v7; // r10
  __int64 v8; // r8
  __int64 v9; // r8
  bool v10; // zf
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v5 = a5;
  v6 = -1;
  v7 = 5;
  if ( a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a5[v8] );
    v9 = v8 + 1;
  }
  else
  {
    v9 = 5;
  }
  if ( !a5 )
    v5 = "NULL";
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v7 = v6 + 1;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = "NULL";
  return pfnWppTraceMessage(a1, 43, WPP_209ac2dacfe33e766942e225d4aecb6d_Traceguids, 10, a4, v7, v5, v9, va, 4, 0);
}

```

## disassembly

```asm
0x14000eed4  push    rbx
0x14000eed6  sub     rsp, 60h
0x14000eeda  mov     rdx, [rsp+68h+arg_20]
0x14000eee2  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000eee6  xor     r11d, r11d
0x14000eee9  mov     r10d, 5
0x14000eeef  test    rdx, rdx
0x14000eef2  jz      short loc_14000EF05
0x14000eef4  mov     r8, rax
0x14000eef7  inc     r8
0x14000eefa  cmp     [rdx+r8], r11b
0x14000eefe  jnz     short loc_14000EEF7
0x14000ef00  inc     r8
0x14000ef03  jmp     short loc_14000EF08
0x14000ef05  mov     r8, r10
0x14000ef08  test    rdx, rdx
0x14000ef0b  lea     rbx, aNull; "NULL"
0x14000ef12  cmovz   rdx, rbx
0x14000ef16  test    r9, r9
0x14000ef19  jz      short loc_14000EF2B
0x14000ef1b  inc     rax
0x14000ef1e  cmp     [r9+rax], r11b
0x14000ef22  jnz     short loc_14000EF1B
0x14000ef24  lea     r10, [rax+1]
0x14000ef28  test    r9, r9
0x14000ef2b  mov     rax, cs:pfnWppTraceMessage
0x14000ef32  cmovz   r9, rbx
0x14000ef36  mov     [rsp+68h+var_18], r11
0x14000ef3b  mov     ebx, 0Ah
0x14000ef40  mov     [rsp+68h+var_20], 4
0x14000ef49  lea     r11, [rsp+68h+arg_28]
0x14000ef51  mov     [rsp+68h+var_28], r11
0x14000ef56  mov     [rsp+68h+var_30], r8
0x14000ef5b  lea     r8, WPP_209ac2dacfe33e766942e225d4aecb6d_Traceguids
0x14000ef62  mov     [rsp+68h+var_38], rdx
0x14000ef67  lea     edx, [rbx+21h]
0x14000ef6a  mov     [rsp+68h+var_40], r10
0x14000ef6f  mov     [rsp+68h+var_48], r9
0x14000ef74  mov     r9d, ebx
0x14000ef77  call    _guard_dispatch_icall
0x14000ef7c  add     rsp, 60h
0x14000ef80  pop     rbx
0x14000ef81  retn
```
