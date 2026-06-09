# McTemplateU0spq_EventWriteTransfer

- ea: `0x180003e60`
- end: `0x180003efa`
- name: `McTemplateU0spq_EventWriteTransfer`
- size: `154`
- prototype: `ULONG(__int64, const EVENT_DESCRIPTOR *, const char *, ...)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x1800037a0`
- `0x180003890`
- `0x180004c90`
- `0x180004ed0`
- `0x180005c80`
- `0x180006010`
- `0x180006760`
- `0x180007860`
- `0x1800110f0`
- `0x180011560`
- `0x1800135b0`
- `0x180013ae0`

## callees

- `0x18000247c`
- `0x180003e60`
- `0x1800180f0`

## pseudocode

```c
ULONG McTemplateU0spq_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const char *a3, ...)
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
  v13 = 4;
  return McGenEventWrite_EventWriteTransfer((__int64)"NULL", a2, (__int64)a3, 4u, &v6);
}

```

## disassembly

```asm
0x180003e60  mov     [rsp-8+arg_18], r9
0x180003e65  push    rbp
0x180003e66  mov     rbp, rsp
0x180003e69  sub     rsp, 80h
0x180003e70  mov     rax, cs:__security_cookie
0x180003e77  xor     rax, rsp
0x180003e7a  mov     [rbp+var_10], rax
0x180003e7e  xor     r10d, r10d
0x180003e81  test    r8, r8
0x180003e84  jz      short loc_180003E97
0x180003e86  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003e8a  inc     rax
0x180003e8d  cmp     [r8+rax], r10b
0x180003e91  jnz     short loc_180003E8A
0x180003e93  inc     eax
0x180003e95  jmp     short loc_180003E9C
0x180003e97  mov     eax, 5
0x180003e9c  mov     [rbp+var_38], eax
0x180003e9f  lea     rcx, aNull; "NULL"
0x180003ea6  lea     rax, [rbp+arg_18]
0x180003eaa  mov     [rbp+var_34], r10d
0x180003eae  mov     [rbp+var_30], rax
0x180003eb2  test    r8, r8
0x180003eb5  lea     rax, [rbp+arg_20]
0x180003eb9  mov     [rbp+var_28], 8
0x180003ec1  mov     [rbp+var_20], rax
0x180003ec5  cmovz   r8, rcx
0x180003ec9  lea     rax, [rbp+var_50]
0x180003ecd  mov     [rbp+var_40], r8
0x180003ed1  mov     r9d, 4
0x180003ed7  mov     [rsp+80h+var_60], rax
0x180003edc  mov     [rbp+var_18], r9
0x180003ee0  call    McGenEventWrite_EventWriteTransfer
0x180003ee5  mov     rcx, [rbp+var_10]
0x180003ee9  xor     rcx, rsp; StackCookie
0x180003eec  call    __security_check_cookie
0x180003ef1  add     rsp, 80h
0x180003ef8  pop     rbp
0x180003ef9  retn
```
