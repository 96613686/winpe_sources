# McTemplateK0z_EtwWriteTransfer

- ea: `0x14001c1ac`
- end: `0x14001c22c`
- name: `McTemplateK0z_EtwWriteTransfer`
- size: `128`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000463c`
- `0x1400116fc`
- `0x1400171d0`

## callees

- `0x140014ac4`
- `0x14001c1ac`
- `0x140039740`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0z_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-28h]
  int v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+4Ch] [rbp-1Ch]

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v9 = v5;
  v10 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v8 = a4;
  return McGenEventWrite_EtwWriteTransfer(
           (__int64)L"NULL",
           (const EVENT_DESCRIPTOR *)TPM_USER_SW_LOCKED_OUT,
           a3,
           2u,
           &v7);
}

```

## disassembly

```asm
0x14001c1ac  sub     rsp, 68h
0x14001c1b0  mov     rax, cs:__security_cookie
0x14001c1b7  xor     rax, rsp
0x14001c1ba  mov     [rsp+68h+var_18], rax
0x14001c1bf  xor     edx, edx
0x14001c1c1  test    r9, r9
0x14001c1c4  jz      short loc_14001C1DD
0x14001c1c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001c1ca  inc     rax
0x14001c1cd  cmp     [r9+rax*2], dx
0x14001c1d2  jnz     short loc_14001C1CA
0x14001c1d4  lea     eax, ds:2[rax*2]
0x14001c1db  jmp     short loc_14001C1E2
0x14001c1dd  mov     eax, 0Ah
0x14001c1e2  test    r9, r9
0x14001c1e5  mov     [rsp+68h+var_20], eax
0x14001c1e9  lea     rcx, aNull_0; "NULL"
0x14001c1f0  mov     [rsp+68h+var_1C], edx
0x14001c1f4  cmovz   r9, rcx
0x14001c1f8  lea     rax, [rsp+68h+var_38]
0x14001c1fd  mov     [rsp+68h+var_28], r9
0x14001c202  lea     rdx, TPM_USER_SW_LOCKED_OUT
0x14001c209  mov     r9d, 2
0x14001c20f  mov     [rsp+68h+var_48], rax
0x14001c214  call    McGenEventWrite_EtwWriteTransfer
0x14001c219  mov     rcx, [rsp+68h+var_18]
0x14001c21e  xor     rcx, rsp; StackCookie
0x14001c221  call    __security_check_cookie
0x14001c226  add     rsp, 68h
0x14001c22a  retn
```
