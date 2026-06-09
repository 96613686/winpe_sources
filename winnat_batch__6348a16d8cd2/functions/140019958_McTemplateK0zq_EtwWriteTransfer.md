# McTemplateK0zq_EtwWriteTransfer

- ea: `0x140019958`
- end: `0x1400199f5`
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
- `0x140019958`
- `0x14001ede0`

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
0x140019958  sub     rsp, 78h
0x14001995c  mov     rax, cs:__security_cookie
0x140019963  xor     rax, rsp
0x140019966  mov     [rsp+78h+var_18], rax
0x14001996b  xor     edx, edx
0x14001996d  test    r9, r9
0x140019970  jz      short loc_140019989
0x140019972  or      rax, 0FFFFFFFFFFFFFFFFh
0x140019976  inc     rax
0x140019979  cmp     [r9+rax*2], dx
0x14001997e  jnz     short loc_140019976
0x140019980  lea     eax, ds:2[rax*2]
0x140019987  jmp     short loc_14001998E
0x140019989  mov     eax, 0Ah
0x14001998e  test    r9, r9
0x140019991  mov     [rsp+78h+var_30], eax
0x140019995  lea     rcx, aNull; "NULL"
0x14001999c  mov     [rsp+78h+var_2C], edx
0x1400199a0  cmovz   r9, rcx
0x1400199a4  mov     [rsp+78h+var_20], 4
0x1400199ad  lea     rax, [rsp+78h+arg_20]
0x1400199b5  mov     [rsp+78h+var_38], r9
0x1400199ba  mov     [rsp+78h+var_28], rax
0x1400199bf  lea     rdx, WINNATM_OUT_OF_PORTS_OPERATIONAL
0x1400199c6  lea     rax, [rsp+78h+var_48]
0x1400199cb  mov     r9d, 3
0x1400199d1  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400199d8  mov     [rsp+78h+var_58], rax
0x1400199dd  call    McGenEventWrite_EtwWriteTransfer
0x1400199e2  mov     rcx, [rsp+78h+var_18]
0x1400199e7  xor     rcx, rsp; StackCookie
0x1400199ea  call    __security_check_cookie
0x1400199ef  add     rsp, 78h
0x1400199f3  retn
```
