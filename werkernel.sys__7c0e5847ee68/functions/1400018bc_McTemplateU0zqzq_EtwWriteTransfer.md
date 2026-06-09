# McTemplateU0zqzq_EtwWriteTransfer

- ea: `0x1400018bc`
- end: `0x14000199b`
- name: `McTemplateU0zqzq_EtwWriteTransfer`
- size: `223`
- prototype: `NTSTATUS __fastcall(__int64, __int64, const wchar_t *, int, const wchar_t *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000cc50`

## callees

- `0x140001788`
- `0x1400018bc`
- `0x140002750`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0zqzq_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        int a4,
        const wchar_t *a5,
        char a6)
{
  __int64 v6; // rax
  int v7; // edx
  __int64 v8; // rcx
  int v9; // ecx
  const wchar_t *v10; // rcx
  bool v11; // zf
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v14; // [rsp+40h] [rbp-9h]
  int v15; // [rsp+48h] [rbp-1h]
  int v16; // [rsp+4Ch] [rbp+3h]
  int *v17; // [rsp+50h] [rbp+7h]
  __int64 v18; // [rsp+58h] [rbp+Fh]
  const wchar_t *v19; // [rsp+60h] [rbp+17h]
  int v20; // [rsp+68h] [rbp+1Fh]
  int v21; // [rsp+6Ch] [rbp+23h]
  char *v22; // [rsp+70h] [rbp+27h]
  __int64 v23; // [rsp+78h] [rbp+2Fh]
  int v24; // [rsp+B8h] [rbp+6Fh] BYREF

  v24 = a4;
  v6 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v15 = v9;
  v16 = 0;
  v17 = &v24;
  v10 = a5;
  if ( !a3 )
    a3 = L"NULL";
  v18 = 4;
  v14 = a3;
  v11 = a5 == 0;
  if ( a5 )
  {
    do
      ++v6;
    while ( a5[v6] );
    v7 = 2 * v6 + 2;
    v11 = a5 == 0;
  }
  v20 = v7;
  v22 = &a6;
  v21 = 0;
  if ( v11 )
    v10 = L"NULL";
  v19 = v10;
  v23 = 4;
  return McGenEventWrite_EtwWriteTransfer(
           (__int64)v10,
           (const EVENT_DESCRIPTOR *)WERKERNEL_SUBMIT_REPORT,
           (__int64)a3,
           5u,
           &v13);
}

```

## disassembly

```asm
0x1400018bc  mov     [rsp-8+arg_18], r9d
0x1400018c1  push    rbp
0x1400018c2  lea     rbp, [rsp-47h]
0x1400018c7  sub     rsp, 90h
0x1400018ce  mov     rax, cs:__security_cookie
0x1400018d5  xor     rax, rsp
0x1400018d8  mov     [rbp+47h+var_10], rax
0x1400018dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400018e0  xor     r9d, r9d
0x1400018e3  mov     edx, 0Ah
0x1400018e8  test    r8, r8
0x1400018eb  jz      short loc_140001903
0x1400018ed  mov     rcx, rax
0x1400018f0  inc     rcx
0x1400018f3  cmp     [r8+rcx*2], r9w
0x1400018f8  jnz     short loc_1400018F0
0x1400018fa  lea     ecx, ds:2[rcx*2]
0x140001901  jmp     short loc_140001905
0x140001903  mov     ecx, edx
0x140001905  mov     [rbp+47h+var_48], ecx
0x140001908  lea     r10, aNull; "NULL"
0x14000190f  lea     rcx, [rbp+47h+arg_18]
0x140001913  mov     [rbp+47h+var_44], r9d
0x140001917  test    r8, r8
0x14000191a  mov     [rbp+47h+var_40], rcx
0x14000191e  mov     rcx, [rbp+47h+arg_20]
0x140001922  cmovz   r8, r10
0x140001926  mov     [rbp+47h+var_38], 4
0x14000192e  mov     [rbp+47h+var_50], r8
0x140001932  test    rcx, rcx
0x140001935  jz      short loc_14000194B
0x140001937  inc     rax
0x14000193a  cmp     [rcx+rax*2], r9w
0x14000193f  jnz     short loc_140001937
0x140001941  lea     edx, ds:2[rax*2]
0x140001948  test    rcx, rcx
0x14000194b  lea     rax, [rbp+47h+arg_28]
0x14000194f  mov     [rbp+47h+var_28], edx
0x140001952  mov     [rbp+47h+var_20], rax
0x140001956  lea     rdx, WERKERNEL_SUBMIT_REPORT
0x14000195d  lea     rax, [rbp+47h+var_60]
0x140001961  mov     [rbp+47h+var_24], r9d
0x140001965  cmovz   rcx, r10
0x140001969  mov     [rsp+90h+var_70], rax
0x14000196e  mov     r9d, 5
0x140001974  mov     [rbp+47h+var_30], rcx
0x140001978  mov     [rbp+47h+var_18], 4
0x140001980  call    McGenEventWrite_EtwWriteTransfer
0x140001985  mov     rcx, [rbp+47h+var_10]
0x140001989  xor     rcx, rsp; StackCookie
0x14000198c  call    __security_check_cookie
0x140001991  add     rsp, 90h
0x140001998  pop     rbp
0x140001999  retn
```
