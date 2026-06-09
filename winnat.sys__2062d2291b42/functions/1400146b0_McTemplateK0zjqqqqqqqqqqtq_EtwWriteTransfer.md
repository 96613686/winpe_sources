# McTemplateK0zjqqqqqqqqqqtq_EtwWriteTransfer

- ea: `0x1400146b0`
- end: `0x140014828`
- name: `McTemplateK0zjqqqqqqqqqqtq_EtwWriteTransfer`
- size: `376`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400311f4`
- `0x140033018`

## callees

- `0x1400095bc`
- `0x1400146b0`
- `0x14001f320`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zjqqqqqqqqqqtq_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const wchar_t *a4,
        __int64 a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        char a13,
        char a14,
        char a15,
        char a16,
        char a17)
{
  __int64 v17; // rax
  int v18; // eax
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v21; // [rsp+40h] [rbp-C0h]
  int v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+4Ch] [rbp-B4h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+58h] [rbp-A8h]
  char *v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  char *v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  char *v30; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+88h] [rbp-78h]
  char *v32; // [rsp+90h] [rbp-70h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  char *v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  char *v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  char *v38; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  char *v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  char *v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  char *v44; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F8h] [rbp-8h]
  char *v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]
  char *v48; // [rsp+110h] [rbp+10h]
  __int64 v49; // [rsp+118h] [rbp+18h]

  if ( a4 )
  {
    v17 = -1;
    do
      ++v17;
    while ( a4[v17] );
    v18 = 2 * v17 + 2;
  }
  else
  {
    v18 = 10;
  }
  v22 = v18;
  v24 = a5;
  v26 = &a6;
  if ( !a4 )
    a4 = L"NULL";
  v21 = a4;
  v28 = &a7;
  v23 = 0;
  v30 = &a8;
  v32 = &a9;
  v34 = &a10;
  v36 = &a11;
  v38 = &a12;
  v40 = &a13;
  v42 = &a14;
  v44 = &a15;
  v46 = &a16;
  v48 = &a17;
  v25 = 16;
  v27 = 4;
  v29 = 4;
  v31 = 4;
  v33 = 4;
  v35 = 4;
  v37 = 4;
  v39 = 4;
  v41 = 4;
  v43 = 4;
  v45 = 4;
  v47 = 4;
  v49 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, (__int64)L"NULL", 0xFu, &v20);
}

```

## disassembly

```asm
0x1400146b0  push    rbp
0x1400146b2  lea     rbp, [rsp-30h]
0x1400146b7  sub     rsp, 130h
0x1400146be  mov     rax, cs:__security_cookie
0x1400146c5  xor     rax, rsp
0x1400146c8  mov     [rbp+30h+var_10], rax
0x1400146cc  xor     r10d, r10d
0x1400146cf  test    r9, r9
0x1400146d2  jz      short loc_1400146EB
0x1400146d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400146d8  inc     rax
0x1400146db  cmp     [r9+rax*2], r10w
0x1400146e0  jnz     short loc_1400146D8
0x1400146e2  lea     eax, ds:2[rax*2]
0x1400146e9  jmp     short loc_1400146F0
0x1400146eb  mov     eax, 0Ah
0x1400146f0  mov     [rsp+130h+var_E8], eax
0x1400146f4  lea     r8, aNull; "NULL"
0x1400146fb  mov     rax, [rbp+30h+arg_20]
0x1400146ff  test    r9, r9
0x140014702  mov     [rsp+130h+var_E0], rax
0x140014707  lea     rax, [rbp+30h+arg_28]
0x14001470b  mov     [rsp+130h+var_D0], rax
0x140014710  cmovz   r9, r8
0x140014714  lea     rax, [rbp+30h+arg_30]
0x140014718  mov     [rsp+130h+var_F0], r9
0x14001471d  mov     [rsp+130h+var_C0], rax
0x140014722  mov     r9d, 0Fh
0x140014728  lea     rax, [rbp+30h+arg_38]
0x14001472c  mov     [rsp+130h+var_E4], r10d
0x140014731  mov     [rbp+30h+var_B0], rax
0x140014735  lea     rax, [rbp+30h+arg_40]
0x14001473c  mov     [rbp+30h+var_A0], rax
0x140014740  lea     rax, [rbp+30h+arg_48]
0x140014747  mov     [rbp+30h+var_90], rax
0x14001474b  lea     rax, [rbp+30h+arg_50]
0x140014752  mov     [rbp+30h+var_80], rax
0x140014756  lea     rax, [rbp+30h+arg_58]
0x14001475d  mov     [rbp+30h+var_70], rax
0x140014761  lea     rax, [rbp+30h+arg_60]
0x140014768  mov     [rbp+30h+var_60], rax
0x14001476c  lea     rax, [rbp+30h+arg_68]
0x140014773  mov     [rbp+30h+var_50], rax
0x140014777  lea     rax, [rbp+30h+arg_70]
0x14001477e  mov     [rbp+30h+var_40], rax
0x140014782  lea     rax, [rbp+30h+arg_78]
0x140014789  mov     [rbp+30h+var_30], rax
0x14001478d  lea     rax, [rbp+30h+arg_80]
0x140014794  mov     [rbp+30h+var_20], rax
0x140014798  lea     rax, [rsp+130h+var_100]
0x14001479d  mov     [rsp+130h+var_110], rax
0x1400147a2  mov     [rsp+130h+var_D8], 10h
0x1400147ab  mov     [rsp+130h+var_C8], 4
0x1400147b4  mov     [rsp+130h+var_B8], 4
0x1400147bd  mov     [rbp+30h+var_A8], 4
0x1400147c5  mov     [rbp+30h+var_98], 4
0x1400147cd  mov     [rbp+30h+var_88], 4
0x1400147d5  mov     [rbp+30h+var_78], 4
0x1400147dd  mov     [rbp+30h+var_68], 4
0x1400147e5  mov     [rbp+30h+var_58], 4
0x1400147ed  mov     [rbp+30h+var_48], 4
0x1400147f5  mov     [rbp+30h+var_38], 4
0x1400147fd  mov     [rbp+30h+var_28], 4
0x140014805  mov     [rbp+30h+var_18], 4
0x14001480d  call    McGenEventWrite_EtwWriteTransfer
0x140014812  mov     rcx, [rbp+30h+var_10]
0x140014816  xor     rcx, rsp; StackCookie
0x140014819  call    __security_check_cookie
0x14001481e  add     rsp, 130h
0x140014825  pop     rbp
0x140014826  retn
```
