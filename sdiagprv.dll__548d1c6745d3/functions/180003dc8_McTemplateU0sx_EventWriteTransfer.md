# McTemplateU0sx_EventWriteTransfer

- ea: `0x180003dc8`
- end: `0x180003e57`
- name: `McTemplateU0sx_EventWriteTransfer`
- size: `143`
- prototype: `ULONG(__int64, const EVENT_DESCRIPTOR *, const char *, ...)`
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x1800035cc`
- `0x180003660`
- `0x1800044e8`
- `0x180004574`
- `0x180004f50`
- `0x180005040`
- `0x180005924`
- `0x1800059c0`
- `0x18000650c`
- `0x1800065bc`
- `0x180010774`
- `0x180010800`
- `0x1800115e0`
- `0x1800116d0`
- `0x1800133ac`
- `0x180013480`

## callees

- `0x18000247c`
- `0x180003dc8`
- `0x1800180f0`

## pseudocode

```c
ULONG McTemplateU0sx_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const char *a3, ...)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-48h] BYREF
  const char *v7; // [rsp+40h] [rbp-38h]
  int v8; // [rsp+48h] [rbp-30h]
  int v9; // [rsp+4Ch] [rbp-2Ch]
  va_list v10; // [rsp+50h] [rbp-28h]
  __int64 v11; // [rsp+58h] [rbp-20h]
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, a3);
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
  if ( !a3 )
    a3 = "NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)"NULL", a2, (__int64)a3, 3u, &v6);
}

```

## disassembly

```asm
0x180003dc8  mov     [rsp+arg_18], r9
0x180003dcd  sub     rsp, 78h
0x180003dd1  mov     rax, cs:__security_cookie
0x180003dd8  xor     rax, rsp
0x180003ddb  mov     [rsp+78h+var_18], rax
0x180003de0  xor     r9d, r9d
0x180003de3  test    r8, r8
0x180003de6  jz      short loc_180003DF9
0x180003de8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003dec  inc     rax
0x180003def  cmp     [r8+rax], r9b
0x180003df3  jnz     short loc_180003DEC
0x180003df5  inc     eax
0x180003df7  jmp     short loc_180003DFE
0x180003df9  mov     eax, 5
0x180003dfe  mov     [rsp+78h+var_30], eax
0x180003e02  lea     rcx, aNull; "NULL"
0x180003e09  lea     rax, [rsp+78h+arg_18]
0x180003e11  mov     [rsp+78h+var_2C], r9d
0x180003e16  test    r8, r8
0x180003e19  mov     [rsp+78h+var_28], rax
0x180003e1e  lea     rax, [rsp+78h+var_48]
0x180003e23  mov     [rsp+78h+var_20], 8
0x180003e2c  cmovz   r8, rcx
0x180003e30  mov     [rsp+78h+var_58], rax
0x180003e35  mov     r9d, 3
0x180003e3b  mov     [rsp+78h+var_38], r8
0x180003e40  call    McGenEventWrite_EventWriteTransfer
0x180003e45  mov     rcx, [rsp+78h+var_18]
0x180003e4a  xor     rcx, rsp; StackCookie
0x180003e4d  call    __security_check_cookie
0x180003e52  add     rsp, 78h
0x180003e56  retn
```
