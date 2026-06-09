# McTemplateU0zq_EventWriteTransfer

- ea: `0x180024368`
- end: `0x180024402`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `154`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001fc58`

## callees

- `0x180024290`
- `0x180024368`
- `0x180024640`

## pseudocode

```c
ULONG __fastcall McTemplateU0zq_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, int a4)
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
  return McGenEventWrite_EventWriteTransfer(
           (__int64)L"NULL",
           (const EVENT_DESCRIPTOR *)RpcProxyLbsArbitrationEnd,
           (__int64)a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x180024368  mov     [rsp+arg_18], r9d
0x18002436d  sub     rsp, 78h
0x180024371  mov     rax, cs:__security_cookie
0x180024378  xor     rax, rsp
0x18002437b  mov     [rsp+78h+var_18], rax
0x180024380  xor     edx, edx
0x180024382  test    r8, r8
0x180024385  jz      short loc_18002439E
0x180024387  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002438b  inc     rax
0x18002438e  cmp     [r8+rax*2], dx
0x180024393  jnz     short loc_18002438B
0x180024395  lea     eax, ds:2[rax*2]
0x18002439c  jmp     short loc_1800243A3
0x18002439e  mov     eax, 0Ah
0x1800243a3  mov     [rsp+78h+var_30], eax
0x1800243a7  lea     rcx, aNull; "NULL"
0x1800243ae  lea     rax, [rsp+78h+arg_18]
0x1800243b6  mov     [rsp+78h+var_2C], edx
0x1800243ba  test    r8, r8
0x1800243bd  mov     [rsp+78h+var_28], rax
0x1800243c2  lea     rax, [rsp+78h+var_48]
0x1800243c7  mov     [rsp+78h+var_20], 4
0x1800243d0  cmovz   r8, rcx
0x1800243d4  mov     [rsp+78h+var_58], rax
0x1800243d9  mov     r9d, 3
0x1800243df  mov     [rsp+78h+var_38], r8
0x1800243e4  lea     rdx, RpcProxyLbsArbitrationEnd
0x1800243eb  call    McGenEventWrite_EventWriteTransfer
0x1800243f0  mov     rcx, [rsp+78h+var_18]
0x1800243f5  xor     rcx, rsp; StackCookie
0x1800243f8  call    __security_check_cookie
0x1800243fd  add     rsp, 78h
0x180024401  retn
```
