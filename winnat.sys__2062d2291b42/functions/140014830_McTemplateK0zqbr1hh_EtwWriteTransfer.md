# McTemplateK0zqbr1hh_EtwWriteTransfer

- ea: `0x140014830`
- end: `0x1400148f5`
- name: `McTemplateK0zqbr1hh_EtwWriteTransfer`
- size: `197`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140014dcc`
- `0x140032228`
- `0x1400331d8`

## callees

- `0x1400095bc`
- `0x140014830`
- `0x14001f320`

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
0x140014830  push    rbp
0x140014832  lea     rbp, [rsp-37h]
0x140014837  sub     rsp, 0A0h
0x14001483e  mov     rax, cs:__security_cookie
0x140014845  xor     rax, rsp
0x140014848  mov     [rbp+37h+var_10], rax
0x14001484c  xor     r10d, r10d
0x14001484f  test    r9, r9
0x140014852  jz      short loc_14001486B
0x140014854  or      rax, 0FFFFFFFFFFFFFFFFh
0x140014858  inc     rax
0x14001485b  cmp     [r9+rax*2], r10w
0x140014860  jnz     short loc_140014858
0x140014862  lea     eax, ds:2[rax*2]
0x140014869  jmp     short loc_140014870
0x14001486b  mov     eax, 0Ah
0x140014870  mov     [rbp+37h+var_58], eax
0x140014873  lea     r8, aNull; "NULL"
0x14001487a  test    r9, r9
0x14001487d  mov     [rbp+37h+var_54], r10d
0x140014881  lea     rax, [rbp+37h+arg_20]
0x140014885  mov     [rbp+37h+var_48], 4
0x14001488d  mov     [rbp+37h+var_50], rax
0x140014891  cmovz   r9, r8
0x140014895  mov     rax, [rbp+37h+arg_28]
0x140014899  mov     [rbp+37h+var_40], rax
0x14001489d  mov     eax, [rbp+37h+arg_20]
0x1400148a0  mov     [rbp+37h+var_38], eax
0x1400148a3  lea     rax, [rbp+37h+arg_30]
0x1400148a7  mov     [rbp+37h+var_30], rax
0x1400148ab  lea     rax, [rbp+37h+arg_38]
0x1400148af  mov     [rbp+37h+var_20], rax
0x1400148b3  lea     rax, [rbp+37h+var_70]
0x1400148b7  mov     [rbp+37h+var_60], r9
0x1400148bb  mov     r9d, 6
0x1400148c1  mov     [rsp+0A0h+var_80], rax
0x1400148c6  mov     [rbp+37h+var_34], r10d
0x1400148ca  mov     [rbp+37h+var_28], 2
0x1400148d2  mov     [rbp+37h+var_18], 2
0x1400148da  call    McGenEventWrite_EtwWriteTransfer
0x1400148df  mov     rcx, [rbp+37h+var_10]
0x1400148e3  xor     rcx, rsp; StackCookie
0x1400148e6  call    __security_check_cookie
0x1400148eb  add     rsp, 0A0h
0x1400148f2  pop     rbp
0x1400148f3  retn
```
