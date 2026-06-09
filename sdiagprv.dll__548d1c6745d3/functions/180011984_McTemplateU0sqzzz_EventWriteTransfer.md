# McTemplateU0sqzzz_EventWriteTransfer

- ea: `0x180011984`
- end: `0x180011a9f`
- name: `McTemplateU0sqzzz_EventWriteTransfer`
- size: `283`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, int, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010938`

## callees

- `0x18000247c`
- `0x180011984`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0sqzzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        const wchar_t *a5,
        const wchar_t *a6,
        const wchar_t *a7)
{
  const wchar_t *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rdx
  int v11; // edx
  const wchar_t *v12; // rcx
  __int64 v13; // rdx
  int v14; // edx
  const wchar_t *v15; // rcx
  bool v16; // zf
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-31h] BYREF
  const char *v19; // [rsp+40h] [rbp-21h]
  __int64 v20; // [rsp+48h] [rbp-19h]
  int *v21; // [rsp+50h] [rbp-11h]
  __int64 v22; // [rsp+58h] [rbp-9h]
  const wchar_t *v23; // [rsp+60h] [rbp-1h]
  int v24; // [rsp+68h] [rbp+7h]
  int v25; // [rsp+6Ch] [rbp+Bh]
  const wchar_t *v26; // [rsp+70h] [rbp+Fh]
  int v27; // [rsp+78h] [rbp+17h]
  int v28; // [rsp+7Ch] [rbp+1Bh]
  const wchar_t *v29; // [rsp+80h] [rbp+1Fh]
  int v30; // [rsp+88h] [rbp+27h]
  int v31; // [rsp+8Ch] [rbp+2Bh]
  int v32; // [rsp+C8h] [rbp+67h] BYREF

  v32 = a4;
  v7 = a5;
  v19 = "CDiagnosticCollection::Add";
  v20 = 27;
  v21 = &v32;
  v8 = -1;
  v22 = 4;
  v9 = 10;
  if ( a5 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a5[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v24 = v11;
  v25 = 0;
  if ( !a5 )
    v7 = L"NULL";
  v23 = v7;
  v12 = a6;
  if ( a6 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a6[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v14 = 10;
  }
  v27 = v14;
  v28 = 0;
  if ( !a6 )
    v12 = L"NULL";
  v26 = v12;
  v15 = a7;
  v16 = a7 == 0;
  if ( a7 )
  {
    do
      ++v8;
    while ( a7[v8] );
    v9 = (unsigned int)(2 * v8 + 2);
    v16 = a7 == 0;
  }
  if ( v16 )
    v15 = L"NULL";
  v31 = 0;
  v29 = v15;
  v30 = v9;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v15,
           (const EVENT_DESCRIPTOR *)SDIAGPRV_EVENT_DEBUG_ADD_DIAGNOSTIC_ERRORALREADYEXISTS,
           v9,
           6u,
           &v18);
}

```

## disassembly

```asm
0x180011984  mov     [rsp-8+arg_18], r9d
0x180011989  push    rbp
0x18001198a  lea     rbp, [rsp-3Fh]
0x18001198f  sub     rsp, 0A0h
0x180011996  mov     rax, cs:__security_cookie
0x18001199d  xor     rax, rsp
0x1800119a0  mov     [rbp+3Fh+var_10], rax
0x1800119a4  mov     rcx, [rbp+3Fh+arg_20]
0x1800119a8  lea     rax, aCdiagnosticcol_1; "CDiagnosticCollection::Add"
0x1800119af  mov     [rbp+3Fh+var_60], rax
0x1800119b3  xor     r9d, r9d
0x1800119b6  lea     rax, [rbp+3Fh+arg_18]
0x1800119ba  mov     [rbp+3Fh+var_58], 1Bh
0x1800119c2  mov     [rbp+3Fh+var_50], rax
0x1800119c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800119ca  mov     [rbp+3Fh+var_48], 4
0x1800119d2  lea     r8d, [r9+0Ah]
0x1800119d6  test    rcx, rcx
0x1800119d9  jz      short loc_1800119F1
0x1800119db  mov     rdx, rax
0x1800119de  inc     rdx
0x1800119e1  cmp     [rcx+rdx*2], r9w
0x1800119e6  jnz     short loc_1800119DE
0x1800119e8  lea     edx, ds:2[rdx*2]
0x1800119ef  jmp     short loc_1800119F4
0x1800119f1  mov     edx, r8d
0x1800119f4  test    rcx, rcx
0x1800119f7  mov     [rbp+3Fh+var_38], edx
0x1800119fa  lea     r10, aNull_0; "NULL"
0x180011a01  mov     [rbp+3Fh+var_34], r9d
0x180011a05  cmovz   rcx, r10
0x180011a09  mov     [rbp+3Fh+var_40], rcx
0x180011a0d  mov     rcx, [rbp+3Fh+arg_28]
0x180011a11  test    rcx, rcx
0x180011a14  jz      short loc_180011A2C
0x180011a16  mov     rdx, rax
0x180011a19  inc     rdx
0x180011a1c  cmp     [rcx+rdx*2], r9w
0x180011a21  jnz     short loc_180011A19
0x180011a23  lea     edx, ds:2[rdx*2]
0x180011a2a  jmp     short loc_180011A2F
0x180011a2c  mov     edx, r8d
0x180011a2f  test    rcx, rcx
0x180011a32  mov     [rbp+3Fh+var_28], edx
0x180011a35  mov     [rbp+3Fh+var_24], r9d
0x180011a39  cmovz   rcx, r10
0x180011a3d  mov     [rbp+3Fh+var_30], rcx
0x180011a41  mov     rcx, [rbp+3Fh+arg_30]
0x180011a45  test    rcx, rcx
0x180011a48  jz      short loc_180011A5F
0x180011a4a  inc     rax
0x180011a4d  cmp     [rcx+rax*2], r9w
0x180011a52  jnz     short loc_180011A4A
0x180011a54  lea     r8d, ds:2[rax*2]
0x180011a5c  test    rcx, rcx
0x180011a5f  cmovz   rcx, r10
0x180011a63  mov     [rbp+3Fh+var_14], r9d
0x180011a67  lea     rax, [rbp+3Fh+var_70]
0x180011a6b  mov     [rbp+3Fh+var_20], rcx
0x180011a6f  mov     r9d, 6
0x180011a75  mov     [rsp+0A0h+var_80], rax
0x180011a7a  lea     rdx, SDIAGPRV_EVENT_DEBUG_ADD_DIAGNOSTIC_ERRORALREADYEXISTS
0x180011a81  mov     [rbp+3Fh+var_18], r8d
0x180011a85  call    McGenEventWrite_EventWriteTransfer
0x180011a8a  mov     rcx, [rbp+3Fh+var_10]
0x180011a8e  xor     rcx, rsp; StackCookie
0x180011a91  call    __security_check_cookie
0x180011a96  add     rsp, 0A0h
0x180011a9d  pop     rbp
0x180011a9e  retn
```
