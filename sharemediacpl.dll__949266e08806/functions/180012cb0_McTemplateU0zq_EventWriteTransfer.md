# McTemplateU0zq_EventWriteTransfer

- ea: `0x180012cb0`
- end: `0x180012d45`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `149`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000822c`
- `0x1800087c0`
- `0x18000d338`
- `0x18000df2c`

## callees

- `0x180001d60`
- `0x180012c58`
- `0x180012cb0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zq_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-38h]
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
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v9 = v5;
  v10 = 0;
  v11 = &v13;
  v12 = 4;
  if ( !a3 )
    a3 = L"NULL";
  v8 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 3u, &v7);
}

```

## disassembly

```asm
0x180012cb0  mov     [rsp+arg_18], r9d
0x180012cb5  sub     rsp, 78h
0x180012cb9  mov     rax, cs:__security_cookie
0x180012cc0  xor     rax, rsp
0x180012cc3  mov     [rsp+78h+var_18], rax
0x180012cc8  xor     r9d, r9d
0x180012ccb  test    r8, r8
0x180012cce  jz      short loc_180012CE7
0x180012cd0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012cd4  inc     rax
0x180012cd7  cmp     [r8+rax*2], r9w
0x180012cdc  jnz     short loc_180012CD4
0x180012cde  lea     eax, ds:2[rax*2]
0x180012ce5  jmp     short loc_180012CEC
0x180012ce7  mov     eax, 0Ah
0x180012cec  mov     [rsp+78h+var_30], eax
0x180012cf0  lea     rcx, aNull_0; "NULL"
0x180012cf7  lea     rax, [rsp+78h+arg_18]
0x180012cff  mov     [rsp+78h+var_2C], r9d
0x180012d04  test    r8, r8
0x180012d07  mov     [rsp+78h+var_28], rax
0x180012d0c  lea     rax, [rsp+78h+var_48]
0x180012d11  mov     [rsp+78h+var_20], 4
0x180012d1a  cmovz   r8, rcx
0x180012d1e  mov     [rsp+78h+var_58], rax
0x180012d23  mov     r9d, 3
0x180012d29  mov     [rsp+78h+var_38], r8
0x180012d2e  call    McGenEventWrite_EventWriteTransfer
0x180012d33  mov     rcx, [rsp+78h+var_18]
0x180012d38  xor     rcx, rsp; StackCookie
0x180012d3b  call    __security_check_cookie
0x180012d40  add     rsp, 78h
0x180012d44  retn
```
