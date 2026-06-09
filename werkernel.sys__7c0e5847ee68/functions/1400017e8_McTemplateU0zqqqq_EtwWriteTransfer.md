# McTemplateU0zqqqq_EtwWriteTransfer

- ea: `0x1400017e8`
- end: `0x1400018b4`
- name: `McTemplateU0zqqqq_EtwWriteTransfer`
- size: `204`
- prototype: `NTSTATUS __fastcall(__int64, __int64, const wchar_t *, int, char, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c6f0`

## callees

- `0x140001788`
- `0x1400017e8`
- `0x140002750`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0zqqqq_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        int a4,
        char a5,
        char a6,
        char a7)
{
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-31h] BYREF
  const wchar_t *v11; // [rsp+40h] [rbp-21h]
  int v12; // [rsp+48h] [rbp-19h]
  int v13; // [rsp+4Ch] [rbp-15h]
  int *v14; // [rsp+50h] [rbp-11h]
  __int64 v15; // [rsp+58h] [rbp-9h]
  char *v16; // [rsp+60h] [rbp-1h]
  __int64 v17; // [rsp+68h] [rbp+7h]
  char *v18; // [rsp+70h] [rbp+Fh]
  __int64 v19; // [rsp+78h] [rbp+17h]
  char *v20; // [rsp+80h] [rbp+1Fh]
  __int64 v21; // [rsp+88h] [rbp+27h]
  int v22; // [rsp+C8h] [rbp+67h] BYREF

  v22 = a4;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v12 = v8;
  v13 = 0;
  v14 = &v22;
  v15 = 4;
  v16 = &a5;
  v17 = 4;
  v18 = &a6;
  if ( !a3 )
    a3 = L"NULL";
  v11 = a3;
  v20 = &a7;
  v19 = 4;
  v21 = 4;
  return McGenEventWrite_EtwWriteTransfer(
           (__int64)L"NULL",
           (const EVENT_DESCRIPTOR *)WERKERNEL_CREATE_REPORT,
           (__int64)a3,
           6u,
           &v10);
}

```

## disassembly

```asm
0x1400017e8  mov     [rsp-8+arg_18], r9d
0x1400017ed  push    rbp
0x1400017ee  lea     rbp, [rsp-3Fh]
0x1400017f3  sub     rsp, 0A0h
0x1400017fa  mov     rax, cs:__security_cookie
0x140001801  xor     rax, rsp
0x140001804  mov     [rbp+3Fh+var_10], rax
0x140001808  xor     edx, edx
0x14000180a  test    r8, r8
0x14000180d  jz      short loc_140001826
0x14000180f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001813  inc     rax
0x140001816  cmp     [r8+rax*2], dx
0x14000181b  jnz     short loc_140001813
0x14000181d  lea     eax, ds:2[rax*2]
0x140001824  jmp     short loc_14000182B
0x140001826  mov     eax, 0Ah
0x14000182b  mov     [rbp+3Fh+var_58], eax
0x14000182e  lea     rcx, aNull; "NULL"
0x140001835  lea     rax, [rbp+3Fh+arg_18]
0x140001839  mov     [rbp+3Fh+var_54], edx
0x14000183c  mov     [rbp+3Fh+var_50], rax
0x140001840  lea     rdx, WERKERNEL_CREATE_REPORT
0x140001847  lea     rax, [rbp+3Fh+arg_20]
0x14000184b  mov     [rbp+3Fh+var_48], 4
0x140001853  mov     [rbp+3Fh+var_40], rax
0x140001857  test    r8, r8
0x14000185a  lea     rax, [rbp+3Fh+arg_28]
0x14000185e  mov     [rbp+3Fh+var_38], 4
0x140001866  mov     [rbp+3Fh+var_30], rax
0x14000186a  cmovz   r8, rcx
0x14000186e  lea     rax, [rbp+3Fh+arg_30]
0x140001872  mov     [rbp+3Fh+var_60], r8
0x140001876  mov     [rbp+3Fh+var_20], rax
0x14000187a  mov     r9d, 6
0x140001880  lea     rax, [rbp+3Fh+var_70]
0x140001884  mov     [rbp+3Fh+var_28], 4
0x14000188c  mov     [rsp+0A0h+var_80], rax
0x140001891  mov     [rbp+3Fh+var_18], 4
0x140001899  call    McGenEventWrite_EtwWriteTransfer
0x14000189e  mov     rcx, [rbp+3Fh+var_10]
0x1400018a2  xor     rcx, rsp; StackCookie
0x1400018a5  call    __security_check_cookie
0x1400018aa  add     rsp, 0A0h
0x1400018b1  pop     rbp
0x1400018b2  retn
```
