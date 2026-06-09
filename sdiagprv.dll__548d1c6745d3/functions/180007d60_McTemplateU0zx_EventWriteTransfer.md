# McTemplateU0zx_EventWriteTransfer

- ea: `0x180007d60`
- end: `0x180007dfa`
- name: `McTemplateU0zx_EventWriteTransfer`
- size: `154`
- prototype: `ULONG(__int64, __int64, const wchar_t *, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006fa0`

## callees

- `0x18000247c`
- `0x180007d60`
- `0x1800180f0`

## pseudocode

```c
ULONG McTemplateU0zx_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, ...)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v7; // [rsp+40h] [rbp-38h]
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
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 10;
  }
  v8 = v4;
  v9 = 0;
  va_copy(v10, va);
  v11 = 8;
  if ( !a3 )
    a3 = L"NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)L"NULL",
           (const EVENT_DESCRIPTOR *)SDIAGPRV_EVENT_IDIAGNOSTIC_PROVIDER_FIND_DIAGNOSTICS_BY_SEARCH_METADATA_SUCCESS,
           (__int64)a3,
           3u,
           &v6);
}

```

## disassembly

```asm
0x180007d60  mov     [rsp+arg_18], r9
0x180007d65  sub     rsp, 78h
0x180007d69  mov     rax, cs:__security_cookie
0x180007d70  xor     rax, rsp
0x180007d73  mov     [rsp+78h+var_18], rax
0x180007d78  xor     edx, edx
0x180007d7a  test    r8, r8
0x180007d7d  jz      short loc_180007D96
0x180007d7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007d83  inc     rax
0x180007d86  cmp     [r8+rax*2], dx
0x180007d8b  jnz     short loc_180007D83
0x180007d8d  lea     eax, ds:2[rax*2]
0x180007d94  jmp     short loc_180007D9B
0x180007d96  mov     eax, 0Ah
0x180007d9b  mov     [rsp+78h+var_30], eax
0x180007d9f  lea     rcx, aNull_0; "NULL"
0x180007da6  lea     rax, [rsp+78h+arg_18]
0x180007dae  mov     [rsp+78h+var_2C], edx
0x180007db2  test    r8, r8
0x180007db5  mov     [rsp+78h+var_28], rax
0x180007dba  lea     rax, [rsp+78h+var_48]
0x180007dbf  mov     [rsp+78h+var_20], 8
0x180007dc8  cmovz   r8, rcx
0x180007dcc  mov     [rsp+78h+var_58], rax
0x180007dd1  mov     r9d, 3
0x180007dd7  mov     [rsp+78h+var_38], r8
0x180007ddc  lea     rdx, SDIAGPRV_EVENT_IDIAGNOSTIC_PROVIDER_FIND_DIAGNOSTICS_BY_SEARCH_METADATA_SUCCESS
0x180007de3  call    McGenEventWrite_EventWriteTransfer
0x180007de8  mov     rcx, [rsp+78h+var_18]
0x180007ded  xor     rcx, rsp; StackCookie
0x180007df0  call    __security_check_cookie
0x180007df5  add     rsp, 78h
0x180007df9  retn
```
