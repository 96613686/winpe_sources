# McTemplateU0st_EventWriteTransfer

- ea: `0x180003d30`
- end: `0x180003dbf`
- name: `McTemplateU0st_EventWriteTransfer`
- size: `143`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const char *, int)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180003930`
- `0x180003b50`
- `0x180007bc0`
- `0x180007c40`
- `0x1800141a0`
- `0x180014760`
- `0x180014e7c`

## callees

- `0x18000247c`
- `0x180003d30`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0st_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const char *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  const char *v8; // [rsp+40h] [rbp-38h]
  int v9; // [rsp+48h] [rbp-30h]
  int v10; // [rsp+4Ch] [rbp-2Ch]
  int *v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = a4;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v5 = v4 + 1;
  }
  else
  {
    v5 = 5;
  }
  v9 = v5;
  v10 = 0;
  v11 = &v13;
  v12 = 4;
  if ( !a3 )
    a3 = "NULL";
  v8 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)"NULL", a2, (__int64)a3, 3u, &v7);
}

```

## disassembly

```asm
0x180003d30  mov     [rsp+arg_18], r9d
0x180003d35  sub     rsp, 78h
0x180003d39  mov     rax, cs:__security_cookie
0x180003d40  xor     rax, rsp
0x180003d43  mov     [rsp+78h+var_18], rax
0x180003d48  xor     r9d, r9d
0x180003d4b  test    r8, r8
0x180003d4e  jz      short loc_180003D61
0x180003d50  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003d54  inc     rax
0x180003d57  cmp     [r8+rax], r9b
0x180003d5b  jnz     short loc_180003D54
0x180003d5d  inc     eax
0x180003d5f  jmp     short loc_180003D66
0x180003d61  mov     eax, 5
0x180003d66  mov     [rsp+78h+var_30], eax
0x180003d6a  lea     rcx, aNull; "NULL"
0x180003d71  lea     rax, [rsp+78h+arg_18]
0x180003d79  mov     [rsp+78h+var_2C], r9d
0x180003d7e  test    r8, r8
0x180003d81  mov     [rsp+78h+var_28], rax
0x180003d86  lea     rax, [rsp+78h+var_48]
0x180003d8b  mov     [rsp+78h+var_20], 4
0x180003d94  cmovz   r8, rcx
0x180003d98  mov     [rsp+78h+var_58], rax
0x180003d9d  mov     r9d, 3
0x180003da3  mov     [rsp+78h+var_38], r8
0x180003da8  call    McGenEventWrite_EventWriteTransfer
0x180003dad  mov     rcx, [rsp+78h+var_18]
0x180003db2  xor     rcx, rsp; StackCookie
0x180003db5  call    __security_check_cookie
0x180003dba  add     rsp, 78h
0x180003dbe  retn
```
