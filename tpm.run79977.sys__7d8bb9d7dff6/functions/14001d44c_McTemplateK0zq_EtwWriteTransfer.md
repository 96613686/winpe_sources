# McTemplateK0zq_EtwWriteTransfer

- ea: `0x14001d44c`
- end: `0x14001d4dd`
- name: `McTemplateK0zq_EtwWriteTransfer`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140013da0`
- `0x14001e130`

## callees

- `0x140014ac4`
- `0x14001d44c`
- `0x140039740`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zq_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const wchar_t *a4,
        char a5)
{
  __int64 v5; // rax
  int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v9; // [rsp+40h] [rbp-38h]
  int v10; // [rsp+48h] [rbp-30h]
  int v11; // [rsp+4Ch] [rbp-2Ch]
  char *v12; // [rsp+50h] [rbp-28h]
  __int64 v13; // [rsp+58h] [rbp-20h]

  if ( a4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a4[v5] );
    v6 = 2 * v5 + 2;
  }
  else
  {
    v6 = 10;
  }
  v10 = v6;
  v11 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v13 = 4;
  v9 = a4;
  v12 = &a5;
  return McGenEventWrite_EtwWriteTransfer((__int64)L"NULL", a2, 0, 3u, &v8);
}

```

## disassembly

```asm
0x14001d44c  sub     rsp, 78h
0x14001d450  mov     rax, cs:__security_cookie
0x14001d457  xor     rax, rsp
0x14001d45a  mov     [rsp+78h+var_18], rax
0x14001d45f  xor     r8d, r8d
0x14001d462  test    r9, r9
0x14001d465  jz      short loc_14001D47E
0x14001d467  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001d46b  inc     rax
0x14001d46e  cmp     [r9+rax*2], r8w
0x14001d473  jnz     short loc_14001D46B
0x14001d475  lea     eax, ds:2[rax*2]
0x14001d47c  jmp     short loc_14001D483
0x14001d47e  mov     eax, 0Ah
0x14001d483  test    r9, r9
0x14001d486  mov     [rsp+78h+var_30], eax
0x14001d48a  lea     rcx, aNull_0; "NULL"
0x14001d491  mov     [rsp+78h+var_2C], r8d
0x14001d496  cmovz   r9, rcx
0x14001d49a  mov     [rsp+78h+var_20], 4
0x14001d4a3  lea     rax, [rsp+78h+arg_20]
0x14001d4ab  mov     [rsp+78h+var_38], r9
0x14001d4b0  mov     [rsp+78h+var_28], rax
0x14001d4b5  mov     r9d, 3
0x14001d4bb  lea     rax, [rsp+78h+var_48]
0x14001d4c0  mov     [rsp+78h+var_58], rax
0x14001d4c5  call    McGenEventWrite_EtwWriteTransfer
0x14001d4ca  mov     rcx, [rsp+78h+var_18]
0x14001d4cf  xor     rcx, rsp; StackCookie
0x14001d4d2  call    __security_check_cookie
0x14001d4d7  add     rsp, 78h
0x14001d4db  retn
```
