# McTemplateK0zqhhxqq_EtwWriteTransfer

- ea: `0x14000e6a8`
- end: `0x14000e787`
- name: `McTemplateK0zqhhxqq_EtwWriteTransfer`
- size: `223`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000bdf0`
- `0x14000ee98`
- `0x14000f480`
- `0x14000f624`
- `0x140010ec4`

## callees

- `0x1400095bc`
- `0x14000e6a8`
- `0x14001f320`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zqhhxqq_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const wchar_t *a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10)
{
  __int64 v10; // rax
  int v11; // eax
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-69h] BYREF
  const wchar_t *v14; // [rsp+40h] [rbp-59h]
  int v15; // [rsp+48h] [rbp-51h]
  int v16; // [rsp+4Ch] [rbp-4Dh]
  char *v17; // [rsp+50h] [rbp-49h]
  __int64 v18; // [rsp+58h] [rbp-41h]
  char *v19; // [rsp+60h] [rbp-39h]
  __int64 v20; // [rsp+68h] [rbp-31h]
  char *v21; // [rsp+70h] [rbp-29h]
  __int64 v22; // [rsp+78h] [rbp-21h]
  char *v23; // [rsp+80h] [rbp-19h]
  __int64 v24; // [rsp+88h] [rbp-11h]
  char *v25; // [rsp+90h] [rbp-9h]
  __int64 v26; // [rsp+98h] [rbp-1h]
  char *v27; // [rsp+A0h] [rbp+7h]
  __int64 v28; // [rsp+A8h] [rbp+Fh]

  if ( a4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a4[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v15 = v11;
  v16 = 0;
  v18 = 4;
  v17 = &a5;
  if ( !a4 )
    a4 = L"NULL";
  v14 = a4;
  v19 = &a6;
  v20 = 2;
  v21 = &a7;
  v23 = &a8;
  v25 = &a9;
  v27 = &a10;
  v22 = 2;
  v24 = 8;
  v26 = 4;
  v28 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, (__int64)L"NULL", 8u, &v13);
}

```

## disassembly

```asm
0x14000e6a8  push    rbp
0x14000e6aa  lea     rbp, [rsp-27h]
0x14000e6af  sub     rsp, 0C0h
0x14000e6b6  mov     rax, cs:__security_cookie
0x14000e6bd  xor     rax, rsp
0x14000e6c0  mov     [rbp+27h+var_10], rax
0x14000e6c4  xor     r11d, r11d
0x14000e6c7  test    r9, r9
0x14000e6ca  jz      short loc_14000E6E3
0x14000e6cc  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e6d0  inc     rax
0x14000e6d3  cmp     [r9+rax*2], r11w
0x14000e6d8  jnz     short loc_14000E6D0
0x14000e6da  lea     eax, ds:2[rax*2]
0x14000e6e1  jmp     short loc_14000E6E8
0x14000e6e3  mov     eax, 0Ah
0x14000e6e8  mov     [rbp+27h+var_78], eax
0x14000e6eb  lea     r8, aNull; "NULL"
0x14000e6f2  test    r9, r9
0x14000e6f5  mov     [rbp+27h+var_74], r11d
0x14000e6f9  lea     rax, [rbp+27h+arg_20]
0x14000e6fd  mov     [rbp+27h+var_68], 4
0x14000e705  mov     [rbp+27h+var_70], rax
0x14000e709  cmovz   r9, r8
0x14000e70d  lea     rax, [rbp+27h+arg_28]
0x14000e711  mov     [rbp+27h+var_80], r9
0x14000e715  mov     [rbp+27h+var_60], rax
0x14000e719  mov     r9d, 8
0x14000e71f  lea     rax, [rbp+27h+arg_30]
0x14000e723  mov     [rbp+27h+var_58], 2
0x14000e72b  mov     [rbp+27h+var_50], rax
0x14000e72f  lea     rax, [rbp+27h+arg_38]
0x14000e733  mov     [rbp+27h+var_40], rax
0x14000e737  lea     rax, [rbp+27h+arg_40]
0x14000e73b  mov     [rbp+27h+var_30], rax
0x14000e73f  lea     rax, [rbp+27h+arg_48]
0x14000e743  mov     [rbp+27h+var_20], rax
0x14000e747  lea     rax, [rbp+27h+var_90]
0x14000e74b  mov     [rsp+0C0h+var_A0], rax
0x14000e750  mov     [rbp+27h+var_48], 2
0x14000e758  mov     [rbp+27h+var_38], r9
0x14000e75c  mov     [rbp+27h+var_28], 4
0x14000e764  mov     [rbp+27h+var_18], 4
0x14000e76c  call    McGenEventWrite_EtwWriteTransfer
0x14000e771  mov     rcx, [rbp+27h+var_10]
0x14000e775  xor     rcx, rsp; StackCookie
0x14000e778  call    __security_check_cookie
0x14000e77d  add     rsp, 0C0h
0x14000e784  pop     rbp
0x14000e785  retn
```
