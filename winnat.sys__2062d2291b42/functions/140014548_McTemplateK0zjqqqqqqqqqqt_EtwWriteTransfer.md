# McTemplateK0zjqqqqqqqqqqt_EtwWriteTransfer

- ea: `0x140014548`
- end: `0x1400146a7`
- name: `McTemplateK0zjqqqqqqqqqqt_EtwWriteTransfer`
- size: `351`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000bc6c`
- `0x140030b2c`
- `0x140032430`
- `0x140033730`

## callees

- `0x1400095bc`
- `0x140014548`
- `0x14001f320`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zjqqqqqqqqqqt_EtwWriteTransfer(
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
        char a16)
{
  __int64 v16; // rax
  int v17; // eax
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v20; // [rsp+40h] [rbp-C0h]
  int v21; // [rsp+48h] [rbp-B8h]
  int v22; // [rsp+4Ch] [rbp-B4h]
  __int64 v23; // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+58h] [rbp-A8h]
  char *v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+68h] [rbp-98h]
  char *v27; // [rsp+70h] [rbp-90h]
  __int64 v28; // [rsp+78h] [rbp-88h]
  char *v29; // [rsp+80h] [rbp-80h]
  __int64 v30; // [rsp+88h] [rbp-78h]
  char *v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  char *v33; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  char *v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  char *v37; // [rsp+C0h] [rbp-40h]
  __int64 v38; // [rsp+C8h] [rbp-38h]
  char *v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  char *v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  char *v43; // [rsp+F0h] [rbp-10h]
  __int64 v44; // [rsp+F8h] [rbp-8h]
  char *v45; // [rsp+100h] [rbp+0h]
  __int64 v46; // [rsp+108h] [rbp+8h]

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
  v23 = a5;
  v25 = &a6;
  if ( !a4 )
    a4 = L"NULL";
  v20 = a4;
  v27 = &a7;
  v22 = 0;
  v29 = &a8;
  v31 = &a9;
  v33 = &a10;
  v35 = &a11;
  v37 = &a12;
  v39 = &a13;
  v41 = &a14;
  v43 = &a15;
  v45 = &a16;
  v24 = 16;
  v26 = 4;
  v28 = 4;
  v30 = 4;
  v32 = 4;
  v34 = 4;
  v36 = 4;
  v38 = 4;
  v40 = 4;
  v42 = 4;
  v44 = 4;
  v46 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, (__int64)L"NULL", 0xEu, &v19);
}

```

## disassembly

```asm
0x140014548  push    rbp
0x14001454a  lea     rbp, [rsp-20h]
0x14001454f  sub     rsp, 120h
0x140014556  mov     rax, cs:__security_cookie
0x14001455d  xor     rax, rsp
0x140014560  mov     [rbp+20h+var_10], rax
0x140014564  xor     r10d, r10d
0x140014567  test    r9, r9
0x14001456a  jz      short loc_140014583
0x14001456c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140014570  inc     rax
0x140014573  cmp     [r9+rax*2], r10w
0x140014578  jnz     short loc_140014570
0x14001457a  lea     eax, ds:2[rax*2]
0x140014581  jmp     short loc_140014588
0x140014583  mov     eax, 0Ah
0x140014588  mov     [rsp+120h+var_D8], eax
0x14001458c  lea     r8, aNull; "NULL"
0x140014593  mov     rax, [rbp+20h+arg_20]
0x140014597  test    r9, r9
0x14001459a  mov     [rsp+120h+var_D0], rax
0x14001459f  lea     rax, [rbp+20h+arg_28]
0x1400145a3  mov     [rsp+120h+var_C0], rax
0x1400145a8  cmovz   r9, r8
0x1400145ac  lea     rax, [rbp+20h+arg_30]
0x1400145b0  mov     [rsp+120h+var_E0], r9
0x1400145b5  mov     [rsp+120h+var_B0], rax
0x1400145ba  mov     r9d, 0Eh
0x1400145c0  lea     rax, [rbp+20h+arg_38]
0x1400145c4  mov     [rsp+120h+var_D4], r10d
0x1400145c9  mov     [rbp+20h+var_A0], rax
0x1400145cd  lea     rax, [rbp+20h+arg_40]
0x1400145d1  mov     [rbp+20h+var_90], rax
0x1400145d5  lea     rax, [rbp+20h+arg_48]
0x1400145d9  mov     [rbp+20h+var_80], rax
0x1400145dd  lea     rax, [rbp+20h+arg_50]
0x1400145e4  mov     [rbp+20h+var_70], rax
0x1400145e8  lea     rax, [rbp+20h+arg_58]
0x1400145ef  mov     [rbp+20h+var_60], rax
0x1400145f3  lea     rax, [rbp+20h+arg_60]
0x1400145fa  mov     [rbp+20h+var_50], rax
0x1400145fe  lea     rax, [rbp+20h+arg_68]
0x140014605  mov     [rbp+20h+var_40], rax
0x140014609  lea     rax, [rbp+20h+arg_70]
0x140014610  mov     [rbp+20h+var_30], rax
0x140014614  lea     rax, [rbp+20h+arg_78]
0x14001461b  mov     [rbp+20h+var_20], rax
0x14001461f  lea     rax, [rsp+120h+var_F0]
0x140014624  mov     [rsp+120h+var_100], rax
0x140014629  mov     [rsp+120h+var_C8], 10h
0x140014632  mov     [rsp+120h+var_B8], 4
0x14001463b  mov     [rsp+120h+var_A8], 4
0x140014644  mov     [rbp+20h+var_98], 4
0x14001464c  mov     [rbp+20h+var_88], 4
0x140014654  mov     [rbp+20h+var_78], 4
0x14001465c  mov     [rbp+20h+var_68], 4
0x140014664  mov     [rbp+20h+var_58], 4
0x14001466c  mov     [rbp+20h+var_48], 4
0x140014674  mov     [rbp+20h+var_38], 4
0x14001467c  mov     [rbp+20h+var_28], 4
0x140014684  mov     [rbp+20h+var_18], 4
0x14001468c  call    McGenEventWrite_EtwWriteTransfer
0x140014691  mov     rcx, [rbp+20h+var_10]
0x140014695  xor     rcx, rsp; StackCookie
0x140014698  call    __security_check_cookie
0x14001469d  add     rsp, 120h
0x1400146a4  pop     rbp
0x1400146a5  retn
```
