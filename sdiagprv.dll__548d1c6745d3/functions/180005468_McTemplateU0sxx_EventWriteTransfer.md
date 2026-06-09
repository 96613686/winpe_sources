# McTemplateU0sxx_EventWriteTransfer

- ea: `0x180005468`
- end: `0x180005506`
- name: `McTemplateU0sxx_EventWriteTransfer`
- size: `158`
- prototype: `ULONG(__int64, const EVENT_DESCRIPTOR *, const char *, ...)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800046b0`
- `0x180004a30`
- `0x180010e88`

## callees

- `0x18000247c`
- `0x180005468`
- `0x1800180f0`

## pseudocode

```c
ULONG McTemplateU0sxx_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const char *a3, ...)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-50h] BYREF
  const char *v7; // [rsp+40h] [rbp-40h]
  int v8; // [rsp+48h] [rbp-38h]
  int v9; // [rsp+4Ch] [rbp-34h]
  va_list v10; // [rsp+50h] [rbp-30h]
  __int64 v11; // [rsp+58h] [rbp-28h]
  va_list v12; // [rsp+60h] [rbp-20h]
  __int64 v13; // [rsp+68h] [rbp-18h]
  __int64 v14; // [rsp+A8h] [rbp+28h] BYREF
  va_list va; // [rsp+A8h] [rbp+28h]
  va_list va1; // [rsp+B0h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v14 = va_arg(va1, _QWORD);
  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = v3 + 1;
  }
  else
  {
    v4 = 5;
  }
  v8 = v4;
  v9 = 0;
  va_copy(v10, va);
  v11 = 8;
  va_copy(v12, va1);
  if ( !a3 )
    a3 = "NULL";
  v7 = a3;
  v13 = 8;
  return McGenEventWrite_EventWriteTransfer((__int64)"NULL", a2, (__int64)a3, 4u, &v6);
}

```

## disassembly

```asm
0x180005468  mov     [rsp-8+arg_18], r9
0x18000546d  push    rbp
0x18000546e  mov     rbp, rsp
0x180005471  sub     rsp, 80h
0x180005478  mov     rax, cs:__security_cookie
0x18000547f  xor     rax, rsp
0x180005482  mov     [rbp+var_10], rax
0x180005486  xor     r9d, r9d
0x180005489  test    r8, r8
0x18000548c  jz      short loc_18000549F
0x18000548e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005492  inc     rax
0x180005495  cmp     [r8+rax], r9b
0x180005499  jnz     short loc_180005492
0x18000549b  inc     eax
0x18000549d  jmp     short loc_1800054A4
0x18000549f  mov     eax, 5
0x1800054a4  mov     [rbp+var_38], eax
0x1800054a7  lea     rcx, aNull; "NULL"
0x1800054ae  lea     rax, [rbp+arg_18]
0x1800054b2  mov     [rbp+var_34], r9d
0x1800054b6  mov     [rbp+var_30], rax
0x1800054ba  test    r8, r8
0x1800054bd  lea     rax, [rbp+arg_20]
0x1800054c1  mov     [rbp+var_28], 8
0x1800054c9  mov     [rbp+var_20], rax
0x1800054cd  cmovz   r8, rcx
0x1800054d1  lea     rax, [rbp+var_50]
0x1800054d5  mov     [rbp+var_40], r8
0x1800054d9  mov     r9d, 4
0x1800054df  mov     [rsp+80h+var_60], rax
0x1800054e4  mov     [rbp+var_18], 8
0x1800054ec  call    McGenEventWrite_EventWriteTransfer
0x1800054f1  mov     rcx, [rbp+var_10]
0x1800054f5  xor     rcx, rsp; StackCookie
0x1800054f8  call    __security_check_cookie
0x1800054fd  add     rsp, 80h
0x180005504  pop     rbp
0x180005505  retn
```
