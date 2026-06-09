# McTemplateK0zqbr1qbr1qqqtxxqq_EtwWriteTransfer

- ea: `0x14000e510`
- end: `0x14000e677`
- name: `McTemplateK0zqbr1qbr1qqqtxxqq_EtwWriteTransfer`
- size: `359`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e980`
- `0x14000eb50`
- `0x1400113c0`

## callees

- `0x1400095bc`
- `0x14000e510`
- `0x14001ede0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zqbr1qbr1qqqtxxqq_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const wchar_t *a4,
        int a5,
        __int64 a6,
        char a7,
        __int64 a8,
        char a9,
        char a10,
        char a11,
        char a12,
        char a13,
        char a14,
        char a15,
        char a16)
{
  __int64 v16; // rax
  int v17; // eax
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v20; // [rsp+40h] [rbp-C0h]
  int v21; // [rsp+48h] [rbp-B8h]
  int v22; // [rsp+4Ch] [rbp-B4h]
  int *v23; // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+58h] [rbp-A8h]
  __int64 v25; // [rsp+60h] [rbp-A0h]
  int v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+6Ch] [rbp-94h]
  char *v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  int v31; // [rsp+88h] [rbp-78h]
  int v32; // [rsp+8Ch] [rbp-74h]
  char *v33; // [rsp+90h] [rbp-70h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  char *v35; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  char *v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  char *v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  char *v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  char *v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  char *v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  char *v47; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+108h] [rbp+8h]

  if ( a4 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a4[v16] );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v17 = 10;
  }
  v21 = v17;
  v22 = 0;
  v24 = 4;
  v23 = &a5;
  if ( !a4 )
    a4 = L"NULL";
  v25 = a6;
  v28 = &a7;
  v30 = a8;
  v33 = &a9;
  v35 = &a10;
  v37 = &a11;
  v39 = &a12;
  v41 = &a13;
  v43 = &a14;
  v45 = &a15;
  v47 = &a16;
  v20 = a4;
  v26 = a5;
  v31 = a5;
  v27 = 0;
  v29 = 4;
  v32 = 0;
  v34 = 4;
  v36 = 4;
  v38 = 4;
  v40 = 4;
  v42 = 8;
  v44 = 8;
  v46 = 4;
  v48 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, (__int64)a1, 0xEu, &v19);
}

```

## disassembly

```asm
0x14000e510  push    rbp
0x14000e512  lea     rbp, [rsp-20h]
0x14000e517  sub     rsp, 120h
0x14000e51e  mov     rax, cs:__security_cookie
0x14000e525  xor     rax, rsp
0x14000e528  mov     [rbp+20h+var_10], rax
0x14000e52c  xor     r10d, r10d
0x14000e52f  mov     r8, rcx
0x14000e532  test    r9, r9
0x14000e535  jz      short loc_14000E54E
0x14000e537  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e53b  inc     rax
0x14000e53e  cmp     [r9+rax*2], r10w
0x14000e543  jnz     short loc_14000E53B
0x14000e545  lea     eax, ds:2[rax*2]
0x14000e54c  jmp     short loc_14000E553
0x14000e54e  mov     eax, 0Ah
0x14000e553  mov     [rsp+120h+var_D8], eax
0x14000e557  lea     rcx, aNull; "NULL"
0x14000e55e  test    r9, r9
0x14000e561  mov     [rsp+120h+var_D4], r10d
0x14000e566  lea     rax, [rbp+20h+arg_20]
0x14000e56a  mov     [rsp+120h+var_C8], 4
0x14000e573  mov     [rsp+120h+var_D0], rax
0x14000e578  cmovz   r9, rcx
0x14000e57c  mov     ecx, [rbp+20h+arg_20]
0x14000e57f  mov     rax, [rbp+20h+arg_28]
0x14000e583  mov     [rsp+120h+var_C0], rax
0x14000e588  lea     rax, [rbp+20h+arg_30]
0x14000e58c  mov     [rsp+120h+var_B0], rax
0x14000e591  mov     rax, [rbp+20h+arg_38]
0x14000e595  mov     [rbp+20h+var_A0], rax
0x14000e599  lea     rax, [rbp+20h+arg_40]
0x14000e59d  mov     [rbp+20h+var_90], rax
0x14000e5a1  lea     rax, [rbp+20h+arg_48]
0x14000e5a5  mov     [rbp+20h+var_80], rax
0x14000e5a9  lea     rax, [rbp+20h+arg_50]
0x14000e5b0  mov     [rbp+20h+var_70], rax
0x14000e5b4  lea     rax, [rbp+20h+arg_58]
0x14000e5bb  mov     [rbp+20h+var_60], rax
0x14000e5bf  lea     rax, [rbp+20h+arg_60]
0x14000e5c6  mov     [rbp+20h+var_50], rax
0x14000e5ca  lea     rax, [rbp+20h+arg_68]
0x14000e5d1  mov     [rbp+20h+var_40], rax
0x14000e5d5  lea     rax, [rbp+20h+arg_70]
0x14000e5dc  mov     [rbp+20h+var_30], rax
0x14000e5e0  lea     rax, [rbp+20h+arg_78]
0x14000e5e7  mov     [rbp+20h+var_20], rax
0x14000e5eb  lea     rax, [rsp+120h+var_F0]
0x14000e5f0  mov     [rsp+120h+var_E0], r9
0x14000e5f5  mov     r9d, 0Eh
0x14000e5fb  mov     [rsp+120h+var_B8], ecx
0x14000e5ff  mov     [rbp+20h+var_98], ecx
0x14000e602  mov     rcx, r8
0x14000e605  mov     [rsp+120h+var_100], rax
0x14000e60a  mov     [rsp+120h+var_B4], r10d
0x14000e60f  mov     [rsp+120h+var_A8], 4
0x14000e618  mov     [rbp+20h+var_94], r10d
0x14000e61c  mov     [rbp+20h+var_88], 4
0x14000e624  mov     [rbp+20h+var_78], 4
0x14000e62c  mov     [rbp+20h+var_68], 4
0x14000e634  mov     [rbp+20h+var_58], 4
0x14000e63c  mov     [rbp+20h+var_48], 8
0x14000e644  mov     [rbp+20h+var_38], 8
0x14000e64c  mov     [rbp+20h+var_28], 4
0x14000e654  mov     [rbp+20h+var_18], 4
0x14000e65c  call    McGenEventWrite_EtwWriteTransfer
0x14000e661  mov     rcx, [rbp+20h+var_10]
0x14000e665  xor     rcx, rsp; StackCookie
0x14000e668  call    __security_check_cookie
0x14000e66d  add     rsp, 120h
0x14000e674  pop     rbp
0x14000e675  retn
```
