# McTemplateU0pzqqz_EventWriteTransfer

- ea: `0x18000c2a8`
- end: `0x18000c395`
- name: `McTemplateU0pzqqz_EventWriteTransfer`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d930`

## callees

- `0x1800061d0`
- `0x180006620`
- `0x18000c2a8`

## pseudocode

```c
ULONG __fastcall McTemplateU0pzqqz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        char a5,
        char a6,
        const wchar_t *a7)
{
  __int64 v7; // rax
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ecx
  const wchar_t *v11; // rcx
  bool v12; // zf
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-31h] BYREF
  __int64 *v15; // [rsp+40h] [rbp-21h]
  __int64 v16; // [rsp+48h] [rbp-19h]
  const wchar_t *v17; // [rsp+50h] [rbp-11h]
  int v18; // [rsp+58h] [rbp-9h]
  int v19; // [rsp+5Ch] [rbp-5h]
  char *v20; // [rsp+60h] [rbp-1h]
  __int64 v21; // [rsp+68h] [rbp+7h]
  char *v22; // [rsp+70h] [rbp+Fh]
  __int64 v23; // [rsp+78h] [rbp+17h]
  const wchar_t *v24; // [rsp+80h] [rbp+1Fh]
  int v25; // [rsp+88h] [rbp+27h]
  int v26; // [rsp+8Ch] [rbp+2Bh]
  __int64 v27; // [rsp+C0h] [rbp+5Fh] BYREF

  v27 = a3;
  v16 = 8;
  v15 = &v27;
  v7 = -1;
  v8 = 10;
  if ( a4 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a4[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v18 = v10;
  v19 = 0;
  v20 = &a5;
  v21 = 4;
  if ( !a4 )
    a4 = L"NULL";
  v22 = &a6;
  v11 = a7;
  v17 = a4;
  v23 = 4;
  v12 = a7 == 0;
  if ( a7 )
  {
    do
      ++v7;
    while ( a7[v7] );
    v8 = 2 * v7 + 2;
    v12 = a7 == 0;
  }
  if ( v12 )
    v11 = L"NULL";
  v25 = v8;
  v24 = v11;
  v26 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v11,
           (const EVENT_DESCRIPTOR *)SamCreateUser2InDomainEntry,
           a3,
           6u,
           &v14);
}

```

## disassembly

```asm
0x18000c2a8  mov     [rsp-8+arg_10], r8
0x18000c2ad  push    rbp
0x18000c2ae  lea     rbp, [rsp-3Fh]
0x18000c2b3  sub     rsp, 0A0h
0x18000c2ba  mov     rax, cs:__security_cookie
0x18000c2c1  xor     rax, rsp
0x18000c2c4  mov     [rbp+3Fh+var_10], rax
0x18000c2c8  lea     rax, [rbp+3Fh+arg_10]
0x18000c2cc  mov     [rbp+3Fh+var_58], 8
0x18000c2d4  xor     r10d, r10d
0x18000c2d7  mov     [rbp+3Fh+var_60], rax
0x18000c2db  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c2df  lea     edx, [r10+0Ah]
0x18000c2e3  test    r9, r9
0x18000c2e6  jz      short loc_18000C2FE
0x18000c2e8  mov     rcx, rax
0x18000c2eb  inc     rcx
0x18000c2ee  cmp     [r9+rcx*2], r10w
0x18000c2f3  jnz     short loc_18000C2EB
0x18000c2f5  lea     ecx, ds:2[rcx*2]
0x18000c2fc  jmp     short loc_18000C300
0x18000c2fe  mov     ecx, edx
0x18000c300  mov     [rbp+3Fh+var_48], ecx
0x18000c303  lea     r11, aNull_0; "NULL"
0x18000c30a  lea     rcx, [rbp+3Fh+arg_20]
0x18000c30e  mov     [rbp+3Fh+var_44], r10d
0x18000c312  mov     [rbp+3Fh+var_40], rcx
0x18000c316  test    r9, r9
0x18000c319  lea     rcx, [rbp+3Fh+arg_28]
0x18000c31d  mov     [rbp+3Fh+var_38], 4
0x18000c325  cmovz   r9, r11
0x18000c329  mov     [rbp+3Fh+var_30], rcx
0x18000c32d  mov     rcx, [rbp+3Fh+arg_30]
0x18000c331  mov     [rbp+3Fh+var_50], r9
0x18000c335  mov     [rbp+3Fh+var_28], 4
0x18000c33d  test    rcx, rcx
0x18000c340  jz      short loc_18000C356
0x18000c342  inc     rax
0x18000c345  cmp     [rcx+rax*2], r10w
0x18000c34a  jnz     short loc_18000C342
0x18000c34c  lea     edx, ds:2[rax*2]
0x18000c353  test    rcx, rcx
0x18000c356  cmovz   rcx, r11
0x18000c35a  mov     [rbp+3Fh+var_18], edx
0x18000c35d  lea     rax, [rbp+3Fh+var_70]
0x18000c361  mov     [rbp+3Fh+var_20], rcx
0x18000c365  lea     rdx, SamCreateUser2InDomainEntry
0x18000c36c  mov     [rsp+0A0h+var_80], rax
0x18000c371  mov     r9d, 6
0x18000c377  mov     [rbp+3Fh+var_14], r10d
0x18000c37b  call    McGenEventWrite_EventWriteTransfer
0x18000c380  mov     rcx, [rbp+3Fh+var_10]
0x18000c384  xor     rcx, rsp; StackCookie
0x18000c387  call    __security_check_cookie
0x18000c38c  add     rsp, 0A0h
0x18000c393  pop     rbp
0x18000c394  retn
```
