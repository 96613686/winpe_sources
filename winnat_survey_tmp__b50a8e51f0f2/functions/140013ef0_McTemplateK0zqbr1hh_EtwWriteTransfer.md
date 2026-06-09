# McTemplateK0zqbr1hh_EtwWriteTransfer

- ea: `0x140013ef0`
- end: `0x140013fb5`
- name: `McTemplateK0zqbr1hh_EtwWriteTransfer`
- size: `197`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14001448c`
- `0x1400310f8`
- `0x1400320a8`

## callees

- `0x1400095bc`
- `0x140013ef0`
- `0x14001ede0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zqbr1hh_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const wchar_t *a4,
        int a5,
        __int64 a6,
        char a7,
        char a8)
{
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-39h] BYREF
  const wchar_t *v12; // [rsp+40h] [rbp-29h]
  int v13; // [rsp+48h] [rbp-21h]
  int v14; // [rsp+4Ch] [rbp-1Dh]
  int *v15; // [rsp+50h] [rbp-19h]
  __int64 v16; // [rsp+58h] [rbp-11h]
  __int64 v17; // [rsp+60h] [rbp-9h]
  int v18; // [rsp+68h] [rbp-1h]
  int v19; // [rsp+6Ch] [rbp+3h]
  char *v20; // [rsp+70h] [rbp+7h]
  __int64 v21; // [rsp+78h] [rbp+Fh]
  char *v22; // [rsp+80h] [rbp+17h]
  __int64 v23; // [rsp+88h] [rbp+1Fh]

  if ( a4 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a4[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v13 = v9;
  v14 = 0;
  v16 = 4;
  v15 = &a5;
  if ( !a4 )
    a4 = L"NULL";
  v17 = a6;
  v18 = a5;
  v20 = &a7;
  v22 = &a8;
  v12 = a4;
  v19 = 0;
  v21 = 2;
  v23 = 2;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, (__int64)L"NULL", 6u, &v11);
}

```

## disassembly

```asm
0x140013ef0  push    rbp
0x140013ef2  lea     rbp, [rsp-37h]
0x140013ef7  sub     rsp, 0A0h
0x140013efe  mov     rax, cs:__security_cookie
0x140013f05  xor     rax, rsp
0x140013f08  mov     [rbp+37h+var_10], rax
0x140013f0c  xor     r10d, r10d
0x140013f0f  test    r9, r9
0x140013f12  jz      short loc_140013F2B
0x140013f14  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013f18  inc     rax
0x140013f1b  cmp     [r9+rax*2], r10w
0x140013f20  jnz     short loc_140013F18
0x140013f22  lea     eax, ds:2[rax*2]
0x140013f29  jmp     short loc_140013F30
0x140013f2b  mov     eax, 0Ah
0x140013f30  mov     [rbp+37h+var_58], eax
0x140013f33  lea     r8, aNull; "NULL"
0x140013f3a  test    r9, r9
0x140013f3d  mov     [rbp+37h+var_54], r10d
0x140013f41  lea     rax, [rbp+37h+arg_20]
0x140013f45  mov     [rbp+37h+var_48], 4
0x140013f4d  mov     [rbp+37h+var_50], rax
0x140013f51  cmovz   r9, r8
0x140013f55  mov     rax, [rbp+37h+arg_28]
0x140013f59  mov     [rbp+37h+var_40], rax
0x140013f5d  mov     eax, [rbp+37h+arg_20]
0x140013f60  mov     [rbp+37h+var_38], eax
0x140013f63  lea     rax, [rbp+37h+arg_30]
0x140013f67  mov     [rbp+37h+var_30], rax
0x140013f6b  lea     rax, [rbp+37h+arg_38]
0x140013f6f  mov     [rbp+37h+var_20], rax
0x140013f73  lea     rax, [rbp+37h+var_70]
0x140013f77  mov     [rbp+37h+var_60], r9
0x140013f7b  mov     r9d, 6
0x140013f81  mov     [rsp+0A0h+var_80], rax
0x140013f86  mov     [rbp+37h+var_34], r10d
0x140013f8a  mov     [rbp+37h+var_28], 2
0x140013f92  mov     [rbp+37h+var_18], 2
0x140013f9a  call    McGenEventWrite_EtwWriteTransfer
0x140013f9f  mov     rcx, [rbp+37h+var_10]
0x140013fa3  xor     rcx, rsp; StackCookie
0x140013fa6  call    __security_check_cookie
0x140013fab  add     rsp, 0A0h
0x140013fb2  pop     rbp
0x140013fb3  retn
```
