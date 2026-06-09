# McTemplateU0sqz_EventWriteTransfer

- ea: `0x18000fc28`
- end: `0x18000fcef`
- name: `McTemplateU0sqz_EventWriteTransfer`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f658`

## callees

- `0x1800027f0`
- `0x180009950`
- `0x18000fc28`

## pseudocode

```c
ULONG __fastcall McTemplateU0sqz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const char *a3,
        int a4,
        const wchar_t *a5)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // ecx
  const wchar_t *v8; // rcx
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-50h] BYREF
  const char *v12; // [rsp+40h] [rbp-40h]
  int v13; // [rsp+48h] [rbp-38h]
  int v14; // [rsp+4Ch] [rbp-34h]
  int *v15; // [rsp+50h] [rbp-30h]
  __int64 v16; // [rsp+58h] [rbp-28h]
  const wchar_t *v17; // [rsp+60h] [rbp-20h]
  int v18; // [rsp+68h] [rbp-18h]
  int v19; // [rsp+6Ch] [rbp-14h]
  int v20; // [rsp+A8h] [rbp+28h] BYREF

  v20 = a4;
  v5 = -1;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = v6 + 1;
  }
  else
  {
    v7 = 5;
  }
  v13 = v7;
  v14 = 0;
  v15 = &v20;
  v8 = a5;
  if ( !a3 )
    a3 = "NULL";
  v12 = a3;
  v16 = 4;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v9 = 2 * v5 + 2;
  }
  else
  {
    v9 = 10;
  }
  v18 = v9;
  v19 = 0;
  if ( !a5 )
    v8 = L"NULL";
  v17 = v8;
  return McGenEventWrite_EventWriteTransfer((__int64)v8, a2, (__int64)L"NULL", 4u, &v11);
}

```

## disassembly

```asm
0x18000fc28  mov     [rsp-8+arg_18], r9d
0x18000fc2d  push    rbp
0x18000fc2e  mov     rbp, rsp
0x18000fc31  sub     rsp, 80h
0x18000fc38  mov     rax, cs:__security_cookie
0x18000fc3f  xor     rax, rsp
0x18000fc42  mov     [rbp+var_10], rax
0x18000fc46  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fc4a  xor     r10d, r10d
0x18000fc4d  test    r8, r8
0x18000fc50  jz      short loc_18000FC62
0x18000fc52  mov     rcx, rax
0x18000fc55  inc     rcx
0x18000fc58  cmp     [r8+rcx], r10b
0x18000fc5c  jnz     short loc_18000FC55
0x18000fc5e  inc     ecx
0x18000fc60  jmp     short loc_18000FC67
0x18000fc62  mov     ecx, 5
0x18000fc67  lea     r9, aNull; "NULL"
0x18000fc6e  mov     [rbp+var_38], ecx
0x18000fc71  lea     rcx, [rbp+arg_18]
0x18000fc75  mov     [rbp+var_34], r10d
0x18000fc79  test    r8, r8
0x18000fc7c  mov     [rbp+var_30], rcx
0x18000fc80  mov     rcx, [rbp+arg_20]
0x18000fc84  cmovz   r8, r9
0x18000fc88  mov     r9d, 4
0x18000fc8e  mov     [rbp+var_40], r8
0x18000fc92  mov     [rbp+var_28], r9
0x18000fc96  test    rcx, rcx
0x18000fc99  jz      short loc_18000FCAE
0x18000fc9b  inc     rax
0x18000fc9e  cmp     [rcx+rax*2], r10w
0x18000fca3  jnz     short loc_18000FC9B
0x18000fca5  lea     eax, ds:2[rax*2]
0x18000fcac  jmp     short loc_18000FCB3
0x18000fcae  mov     eax, 0Ah
0x18000fcb3  test    rcx, rcx
0x18000fcb6  mov     [rbp+var_18], eax
0x18000fcb9  lea     r8, aNull_0; "NULL"
0x18000fcc0  mov     [rbp+var_14], r10d
0x18000fcc4  cmovz   rcx, r8
0x18000fcc8  lea     rax, [rbp+var_50]
0x18000fccc  mov     [rbp+var_20], rcx
0x18000fcd0  mov     [rsp+80h+var_60], rax
0x18000fcd5  call    McGenEventWrite_EventWriteTransfer
0x18000fcda  mov     rcx, [rbp+var_10]
0x18000fcde  xor     rcx, rsp; StackCookie
0x18000fce1  call    __security_check_cookie
0x18000fce6  add     rsp, 80h
0x18000fced  pop     rbp
0x18000fcee  retn
```
