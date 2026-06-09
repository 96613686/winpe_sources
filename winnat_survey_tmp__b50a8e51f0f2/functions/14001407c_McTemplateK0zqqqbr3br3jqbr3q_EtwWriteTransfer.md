# McTemplateK0zqqqbr3br3jqbr3q_EtwWriteTransfer

- ea: `0x14001407c`
- end: `0x14001419a`
- name: `McTemplateK0zqqqbr3br3jqbr3q_EtwWriteTransfer`
- size: `286`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400308ac`
- `0x1400315a0`
- `0x1400321a4`

## callees

- `0x1400095bc`
- `0x14001407c`
- `0x14001ede0`

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
0x14001407c  push    rbp
0x14001407e  lea     rbp, [rsp-0Fh]
0x140014083  sub     rsp, 0F0h
0x14001408a  mov     rax, cs:__security_cookie
0x140014091  xor     rax, rsp
0x140014094  mov     [rbp+0Fh+var_10], rax
0x140014098  xor     r10d, r10d
0x14001409b  test    r9, r9
0x14001409e  jz      short loc_1400140B7
0x1400140a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400140a4  inc     rax
0x1400140a7  cmp     [r9+rax*2], r10w
0x1400140ac  jnz     short loc_1400140A4
0x1400140ae  lea     eax, ds:2[rax*2]
0x1400140b5  jmp     short loc_1400140BC
0x1400140b7  mov     eax, 0Ah
0x1400140bc  mov     [rsp+0F0h+var_A8], eax
0x1400140c0  lea     r8, aNull; "NULL"
0x1400140c7  test    r9, r9
0x1400140ca  mov     [rsp+0F0h+var_A4], r10d
0x1400140cf  lea     rax, [rbp+0Fh+arg_20]
0x1400140d3  mov     [rsp+0F0h+var_98], 4
0x1400140dc  mov     [rsp+0F0h+var_A0], rax
0x1400140e1  cmovz   r9, r8
0x1400140e5  mov     r8d, [rbp+0Fh+arg_30]
0x1400140e9  lea     rax, [rbp+0Fh+arg_28]
0x1400140ed  mov     [rsp+0F0h+var_90], rax
0x1400140f2  lea     rax, [rbp+0Fh+arg_30]
0x1400140f6  mov     [rbp+0Fh+var_80], rax
0x1400140fa  mov     rax, [rbp+0Fh+arg_38]
0x1400140fe  mov     [rbp+0Fh+var_70], rax
0x140014102  mov     rax, [rbp+0Fh+arg_40]
0x140014106  mov     [rbp+0Fh+var_60], rax
0x14001410a  mov     rax, [rbp+0Fh+arg_48]
0x14001410e  mov     [rbp+0Fh+var_50], rax
0x140014112  lea     rax, [rbp+0Fh+arg_50]
0x140014116  mov     [rbp+0Fh+var_40], rax
0x14001411a  mov     rax, [rbp+0Fh+arg_58]
0x14001411e  mov     [rbp+0Fh+var_30], rax
0x140014122  lea     rax, [rbp+0Fh+arg_60]
0x140014126  mov     [rbp+0Fh+var_20], rax
0x14001412a  lea     rax, [rsp+0F0h+var_C0]
0x14001412f  mov     [rsp+0F0h+var_B0], r9
0x140014134  mov     r9d, 0Bh
0x14001413a  mov     [rsp+0F0h+var_D0], rax
0x14001413f  mov     [rbp+0Fh+var_88], 4
0x140014147  mov     [rbp+0Fh+var_78], 4
0x14001414f  mov     [rbp+0Fh+var_68], r8d
0x140014153  mov     [rbp+0Fh+var_64], r10d
0x140014157  mov     [rbp+0Fh+var_58], r8d
0x14001415b  mov     [rbp+0Fh+var_54], r10d
0x14001415f  mov     [rbp+0Fh+var_48], 10h
0x140014167  mov     [rbp+0Fh+var_38], 4
0x14001416f  mov     [rbp+0Fh+var_28], r8d
0x140014173  mov     [rbp+0Fh+var_24], r10d
0x140014177  mov     [rbp+0Fh+var_18], 4
0x14001417f  call    McGenEventWrite_EtwWriteTransfer
0x140014184  mov     rcx, [rbp+0Fh+var_10]
0x140014188  xor     rcx, rsp; StackCookie
0x14001418b  call    __security_check_cookie
0x140014190  add     rsp, 0F0h
0x140014197  pop     rbp
0x140014198  retn
```
