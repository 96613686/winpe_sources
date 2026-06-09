# McTemplateK0zqqqbr3br3jqbr3q_EtwWriteTransfer

- ea: `0x1400149bc`
- end: `0x140014ada`
- name: `McTemplateK0zqqqbr3br3jqbr3q_EtwWriteTransfer`
- size: `286`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400319dc`
- `0x1400326d0`
- `0x1400332d4`

## callees

- `0x1400095bc`
- `0x1400149bc`
- `0x14001f320`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zqqqbr3br3jqbr3q_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const wchar_t *a4,
        char a5,
        char a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        char a11,
        __int64 a12,
        char a13)
{
  __int64 v13; // rax
  int v14; // eax
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+30h] [rbp-B1h] BYREF
  const wchar_t *v17; // [rsp+40h] [rbp-A1h]
  int v18; // [rsp+48h] [rbp-99h]
  int v19; // [rsp+4Ch] [rbp-95h]
  char *v20; // [rsp+50h] [rbp-91h]
  __int64 v21; // [rsp+58h] [rbp-89h]
  char *v22; // [rsp+60h] [rbp-81h]
  __int64 v23; // [rsp+68h] [rbp-79h]
  unsigned int *v24; // [rsp+70h] [rbp-71h]
  __int64 v25; // [rsp+78h] [rbp-69h]
  __int64 v26; // [rsp+80h] [rbp-61h]
  unsigned int v27; // [rsp+88h] [rbp-59h]
  int v28; // [rsp+8Ch] [rbp-55h]
  __int64 v29; // [rsp+90h] [rbp-51h]
  unsigned int v30; // [rsp+98h] [rbp-49h]
  int v31; // [rsp+9Ch] [rbp-45h]
  __int64 v32; // [rsp+A0h] [rbp-41h]
  __int64 v33; // [rsp+A8h] [rbp-39h]
  char *v34; // [rsp+B0h] [rbp-31h]
  __int64 v35; // [rsp+B8h] [rbp-29h]
  __int64 v36; // [rsp+C0h] [rbp-21h]
  unsigned int v37; // [rsp+C8h] [rbp-19h]
  int v38; // [rsp+CCh] [rbp-15h]
  char *v39; // [rsp+D0h] [rbp-11h]
  __int64 v40; // [rsp+D8h] [rbp-9h]

  if ( a4 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a4[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v14 = 10;
  }
  v18 = v14;
  v19 = 0;
  v21 = 4;
  v20 = &a5;
  if ( !a4 )
    a4 = L"NULL";
  v22 = &a6;
  v24 = &a7;
  v26 = a8;
  v29 = a9;
  v32 = a10;
  v34 = &a11;
  v36 = a12;
  v39 = &a13;
  v17 = a4;
  v23 = 4;
  v25 = 4;
  v27 = a7;
  v28 = 0;
  v30 = a7;
  v31 = 0;
  v33 = 16;
  v35 = 4;
  v37 = a7;
  v38 = 0;
  v40 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a7, 0xBu, &v16);
}

```

## disassembly

```asm
0x1400149bc  push    rbp
0x1400149be  lea     rbp, [rsp-0Fh]
0x1400149c3  sub     rsp, 0F0h
0x1400149ca  mov     rax, cs:__security_cookie
0x1400149d1  xor     rax, rsp
0x1400149d4  mov     [rbp+0Fh+var_10], rax
0x1400149d8  xor     r10d, r10d
0x1400149db  test    r9, r9
0x1400149de  jz      short loc_1400149F7
0x1400149e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400149e4  inc     rax
0x1400149e7  cmp     [r9+rax*2], r10w
0x1400149ec  jnz     short loc_1400149E4
0x1400149ee  lea     eax, ds:2[rax*2]
0x1400149f5  jmp     short loc_1400149FC
0x1400149f7  mov     eax, 0Ah
0x1400149fc  mov     [rsp+0F0h+var_A8], eax
0x140014a00  lea     r8, aNull; "NULL"
0x140014a07  test    r9, r9
0x140014a0a  mov     [rsp+0F0h+var_A4], r10d
0x140014a0f  lea     rax, [rbp+0Fh+arg_20]
0x140014a13  mov     [rsp+0F0h+var_98], 4
0x140014a1c  mov     [rsp+0F0h+var_A0], rax
0x140014a21  cmovz   r9, r8
0x140014a25  mov     r8d, [rbp+0Fh+arg_30]
0x140014a29  lea     rax, [rbp+0Fh+arg_28]
0x140014a2d  mov     [rsp+0F0h+var_90], rax
0x140014a32  lea     rax, [rbp+0Fh+arg_30]
0x140014a36  mov     [rbp+0Fh+var_80], rax
0x140014a3a  mov     rax, [rbp+0Fh+arg_38]
0x140014a3e  mov     [rbp+0Fh+var_70], rax
0x140014a42  mov     rax, [rbp+0Fh+arg_40]
0x140014a46  mov     [rbp+0Fh+var_60], rax
0x140014a4a  mov     rax, [rbp+0Fh+arg_48]
0x140014a4e  mov     [rbp+0Fh+var_50], rax
0x140014a52  lea     rax, [rbp+0Fh+arg_50]
0x140014a56  mov     [rbp+0Fh+var_40], rax
0x140014a5a  mov     rax, [rbp+0Fh+arg_58]
0x140014a5e  mov     [rbp+0Fh+var_30], rax
0x140014a62  lea     rax, [rbp+0Fh+arg_60]
0x140014a66  mov     [rbp+0Fh+var_20], rax
0x140014a6a  lea     rax, [rsp+0F0h+var_C0]
0x140014a6f  mov     [rsp+0F0h+var_B0], r9
0x140014a74  mov     r9d, 0Bh
0x140014a7a  mov     [rsp+0F0h+var_D0], rax
0x140014a7f  mov     [rbp+0Fh+var_88], 4
0x140014a87  mov     [rbp+0Fh+var_78], 4
0x140014a8f  mov     [rbp+0Fh+var_68], r8d
0x140014a93  mov     [rbp+0Fh+var_64], r10d
0x140014a97  mov     [rbp+0Fh+var_58], r8d
0x140014a9b  mov     [rbp+0Fh+var_54], r10d
0x140014a9f  mov     [rbp+0Fh+var_48], 10h
0x140014aa7  mov     [rbp+0Fh+var_38], 4
0x140014aaf  mov     [rbp+0Fh+var_28], r8d
0x140014ab3  mov     [rbp+0Fh+var_24], r10d
0x140014ab7  mov     [rbp+0Fh+var_18], 4
0x140014abf  call    McGenEventWrite_EtwWriteTransfer
0x140014ac4  mov     rcx, [rbp+0Fh+var_10]
0x140014ac8  xor     rcx, rsp; StackCookie
0x140014acb  call    __security_check_cookie
0x140014ad0  add     rsp, 0F0h
0x140014ad7  pop     rbp
0x140014ad8  retn
```
