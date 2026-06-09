# McTemplateU0zq_EventWriteTransfer

- ea: `0x180029f00`
- end: `0x180029f9a`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `154`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180028610`
- `0x180029938`

## callees

- `0x180001ec0`
- `0x180029dd0`
- `0x180029f00`

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
           (const EVENT_DESCRIPTOR *)EVENT_TPM_VERIFICATION_FAIL,
           (__int64)a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x180029f00  mov     [rsp+arg_18], r9d
0x180029f05  sub     rsp, 78h
0x180029f09  mov     rax, cs:__security_cookie
0x180029f10  xor     rax, rsp
0x180029f13  mov     [rsp+78h+var_18], rax
0x180029f18  xor     edx, edx
0x180029f1a  test    r8, r8
0x180029f1d  jz      short loc_180029F36
0x180029f1f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029f23  inc     rax
0x180029f26  cmp     [r8+rax*2], dx
0x180029f2b  jnz     short loc_180029F23
0x180029f2d  lea     eax, ds:2[rax*2]
0x180029f34  jmp     short loc_180029F3B
0x180029f36  mov     eax, 0Ah
0x180029f3b  mov     [rsp+78h+var_30], eax
0x180029f3f  lea     rcx, aNull_0; "NULL"
0x180029f46  lea     rax, [rsp+78h+arg_18]
0x180029f4e  mov     [rsp+78h+var_2C], edx
0x180029f52  test    r8, r8
0x180029f55  mov     [rsp+78h+var_28], rax
0x180029f5a  lea     rax, [rsp+78h+var_48]
0x180029f5f  mov     [rsp+78h+var_20], 4
0x180029f68  cmovz   r8, rcx
0x180029f6c  mov     [rsp+78h+var_58], rax
0x180029f71  mov     r9d, 3
0x180029f77  mov     [rsp+78h+var_38], r8
0x180029f7c  lea     rdx, EVENT_TPM_VERIFICATION_FAIL
0x180029f83  call    McGenEventWrite_EventWriteTransfer
0x180029f88  mov     rcx, [rsp+78h+var_18]
0x180029f8d  xor     rcx, rsp; StackCookie
0x180029f90  call    __security_check_cookie
0x180029f95  add     rsp, 78h
0x180029f99  retn
```
