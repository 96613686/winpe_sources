# McTemplateK0zjqqqqqqqqqqtq_EtwWriteTransfer

- ea: `0x140013d70`
- end: `0x140013ee8`
- name: `McTemplateK0zjqqqqqqqqqqtq_EtwWriteTransfer`
- size: `376`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400300c4`
- `0x140031ee8`

## callees

- `0x1400095bc`
- `0x140013d70`
- `0x14001ede0`

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
0x140013d70  push    rbp
0x140013d72  lea     rbp, [rsp-30h]
0x140013d77  sub     rsp, 130h
0x140013d7e  mov     rax, cs:__security_cookie
0x140013d85  xor     rax, rsp
0x140013d88  mov     [rbp+30h+var_10], rax
0x140013d8c  xor     r10d, r10d
0x140013d8f  test    r9, r9
0x140013d92  jz      short loc_140013DAB
0x140013d94  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013d98  inc     rax
0x140013d9b  cmp     [r9+rax*2], r10w
0x140013da0  jnz     short loc_140013D98
0x140013da2  lea     eax, ds:2[rax*2]
0x140013da9  jmp     short loc_140013DB0
0x140013dab  mov     eax, 0Ah
0x140013db0  mov     [rsp+130h+var_E8], eax
0x140013db4  lea     r8, aNull; "NULL"
0x140013dbb  mov     rax, [rbp+30h+arg_20]
0x140013dbf  test    r9, r9
0x140013dc2  mov     [rsp+130h+var_E0], rax
0x140013dc7  lea     rax, [rbp+30h+arg_28]
0x140013dcb  mov     [rsp+130h+var_D0], rax
0x140013dd0  cmovz   r9, r8
0x140013dd4  lea     rax, [rbp+30h+arg_30]
0x140013dd8  mov     [rsp+130h+var_F0], r9
0x140013ddd  mov     [rsp+130h+var_C0], rax
0x140013de2  mov     r9d, 0Fh
0x140013de8  lea     rax, [rbp+30h+arg_38]
0x140013dec  mov     [rsp+130h+var_E4], r10d
0x140013df1  mov     [rbp+30h+var_B0], rax
0x140013df5  lea     rax, [rbp+30h+arg_40]
0x140013dfc  mov     [rbp+30h+var_A0], rax
0x140013e00  lea     rax, [rbp+30h+arg_48]
0x140013e07  mov     [rbp+30h+var_90], rax
0x140013e0b  lea     rax, [rbp+30h+arg_50]
0x140013e12  mov     [rbp+30h+var_80], rax
0x140013e16  lea     rax, [rbp+30h+arg_58]
0x140013e1d  mov     [rbp+30h+var_70], rax
0x140013e21  lea     rax, [rbp+30h+arg_60]
0x140013e28  mov     [rbp+30h+var_60], rax
0x140013e2c  lea     rax, [rbp+30h+arg_68]
0x140013e33  mov     [rbp+30h+var_50], rax
0x140013e37  lea     rax, [rbp+30h+arg_70]
0x140013e3e  mov     [rbp+30h+var_40], rax
0x140013e42  lea     rax, [rbp+30h+arg_78]
0x140013e49  mov     [rbp+30h+var_30], rax
0x140013e4d  lea     rax, [rbp+30h+arg_80]
0x140013e54  mov     [rbp+30h+var_20], rax
0x140013e58  lea     rax, [rsp+130h+var_100]
0x140013e5d  mov     [rsp+130h+var_110], rax
0x140013e62  mov     [rsp+130h+var_D8], 10h
0x140013e6b  mov     [rsp+130h+var_C8], 4
0x140013e74  mov     [rsp+130h+var_B8], 4
0x140013e7d  mov     [rbp+30h+var_A8], 4
0x140013e85  mov     [rbp+30h+var_98], 4
0x140013e8d  mov     [rbp+30h+var_88], 4
0x140013e95  mov     [rbp+30h+var_78], 4
0x140013e9d  mov     [rbp+30h+var_68], 4
0x140013ea5  mov     [rbp+30h+var_58], 4
0x140013ead  mov     [rbp+30h+var_48], 4
0x140013eb5  mov     [rbp+30h+var_38], 4
0x140013ebd  mov     [rbp+30h+var_28], 4
0x140013ec5  mov     [rbp+30h+var_18], 4
0x140013ecd  call    McGenEventWrite_EtwWriteTransfer
0x140013ed2  mov     rcx, [rbp+30h+var_10]
0x140013ed6  xor     rcx, rsp; StackCookie
0x140013ed9  call    __security_check_cookie
0x140013ede  add     rsp, 130h
0x140013ee5  pop     rbp
0x140013ee6  retn
```
