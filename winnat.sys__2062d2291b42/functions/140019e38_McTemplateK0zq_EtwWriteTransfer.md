# McTemplateK0zq_EtwWriteTransfer

- ea: `0x140019e38`
- end: `0x140019ed5`
- name: `McTemplateK0zq_EtwWriteTransfer`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140008a7c`

## callees

- `0x1400095bc`
- `0x140019e38`
- `0x14001f320`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zq_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, const wchar_t *a4, char a5)
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
  return McGenEventWrite_EtwWriteTransfer(
           &MICROSOFT_WINNAT_ETW_PROVIDER_Context,
           (const EVENT_DESCRIPTOR *)WINNATM_OUT_OF_PORTS_OPERATIONAL,
           a3,
           3u,
           &v8);
}

```

## disassembly

```asm
0x140019e38  sub     rsp, 78h
0x140019e3c  mov     rax, cs:__security_cookie
0x140019e43  xor     rax, rsp
0x140019e46  mov     [rsp+78h+var_18], rax
0x140019e4b  xor     edx, edx
0x140019e4d  test    r9, r9
0x140019e50  jz      short loc_140019E69
0x140019e52  or      rax, 0FFFFFFFFFFFFFFFFh
0x140019e56  inc     rax
0x140019e59  cmp     [r9+rax*2], dx
0x140019e5e  jnz     short loc_140019E56
0x140019e60  lea     eax, ds:2[rax*2]
0x140019e67  jmp     short loc_140019E6E
0x140019e69  mov     eax, 0Ah
0x140019e6e  test    r9, r9
0x140019e71  mov     [rsp+78h+var_30], eax
0x140019e75  lea     rcx, aNull; "NULL"
0x140019e7c  mov     [rsp+78h+var_2C], edx
0x140019e80  cmovz   r9, rcx
0x140019e84  mov     [rsp+78h+var_20], 4
0x140019e8d  lea     rax, [rsp+78h+arg_20]
0x140019e95  mov     [rsp+78h+var_38], r9
0x140019e9a  mov     [rsp+78h+var_28], rax
0x140019e9f  lea     rdx, WINNATM_OUT_OF_PORTS_OPERATIONAL
0x140019ea6  lea     rax, [rsp+78h+var_48]
0x140019eab  mov     r9d, 3
0x140019eb1  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140019eb8  mov     [rsp+78h+var_58], rax
0x140019ebd  call    McGenEventWrite_EtwWriteTransfer
0x140019ec2  mov     rcx, [rsp+78h+var_18]
0x140019ec7  xor     rcx, rsp; StackCookie
0x140019eca  call    __security_check_cookie
0x140019ecf  add     rsp, 78h
0x140019ed3  retn
```
