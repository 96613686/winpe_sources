# McTemplateU0pqqqz_EventWriteTransfer

- ea: `0x18000bed0`
- end: `0x18000bf9f`
- name: `McTemplateU0pqqqz_EventWriteTransfer`
- size: `207`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001080`
- `0x180010e70`

## callees

- `0x1800061d0`
- `0x180006620`
- `0x18000bed0`

## pseudocode

```c
ULONG __fastcall McTemplateU0pqqqz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        const wchar_t *a7)
{
  const wchar_t *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-31h] BYREF
  __int64 *v12; // [rsp+40h] [rbp-21h]
  __int64 v13; // [rsp+48h] [rbp-19h]
  int *v14; // [rsp+50h] [rbp-11h]
  __int64 v15; // [rsp+58h] [rbp-9h]
  char *v16; // [rsp+60h] [rbp-1h]
  __int64 v17; // [rsp+68h] [rbp+7h]
  char *v18; // [rsp+70h] [rbp+Fh]
  __int64 v19; // [rsp+78h] [rbp+17h]
  const wchar_t *v20; // [rsp+80h] [rbp+1Fh]
  int v21; // [rsp+88h] [rbp+27h]
  int v22; // [rsp+8Ch] [rbp+2Bh]
  __int64 v23; // [rsp+C0h] [rbp+5Fh] BYREF
  int v24; // [rsp+C8h] [rbp+67h] BYREF

  v24 = a4;
  v23 = a3;
  v7 = a7;
  v12 = &v23;
  v13 = 8;
  v14 = &v24;
  v16 = &a5;
  v18 = &a6;
  v15 = 4;
  v17 = 4;
  v19 = 4;
  if ( a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a7[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v21 = v9;
  v22 = 0;
  if ( !a7 )
    v7 = L"NULL";
  v20 = v7;
  return McGenEventWrite_EventWriteTransfer((__int64)v7, a2, (__int64)L"NULL", 6u, &v11);
}

```

## disassembly

```asm
0x18000bed0  mov     [rsp-8+arg_18], r9d
0x18000bed5  mov     [rsp-8+arg_10], r8
0x18000beda  push    rbp
0x18000bedb  lea     rbp, [rsp-3Fh]
0x18000bee0  sub     rsp, 0A0h
0x18000bee7  mov     rax, cs:__security_cookie
0x18000beee  xor     rax, rsp
0x18000bef1  mov     [rbp+3Fh+var_10], rax
0x18000bef5  mov     rcx, [rbp+3Fh+arg_30]
0x18000bef9  lea     rax, [rbp+3Fh+arg_10]
0x18000befd  mov     [rbp+3Fh+var_60], rax
0x18000bf01  xor     r9d, r9d
0x18000bf04  mov     [rbp+3Fh+var_58], 8
0x18000bf0c  lea     rax, [rbp+3Fh+arg_18]
0x18000bf10  mov     [rbp+3Fh+var_50], rax
0x18000bf14  lea     rax, [rbp+3Fh+arg_20]
0x18000bf18  mov     [rbp+3Fh+var_40], rax
0x18000bf1c  lea     rax, [rbp+3Fh+arg_28]
0x18000bf20  mov     [rbp+3Fh+var_30], rax
0x18000bf24  mov     [rbp+3Fh+var_48], 4
0x18000bf2c  mov     [rbp+3Fh+var_38], 4
0x18000bf34  mov     [rbp+3Fh+var_28], 4
0x18000bf3c  test    rcx, rcx
0x18000bf3f  jz      short loc_18000BF58
0x18000bf41  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bf45  inc     rax
0x18000bf48  cmp     [rcx+rax*2], r9w
0x18000bf4d  jnz     short loc_18000BF45
0x18000bf4f  lea     eax, ds:2[rax*2]
0x18000bf56  jmp     short loc_18000BF5D
0x18000bf58  mov     eax, 0Ah
0x18000bf5d  test    rcx, rcx
0x18000bf60  mov     [rbp+3Fh+var_18], eax
0x18000bf63  lea     r8, aNull_0; "NULL"
0x18000bf6a  mov     [rbp+3Fh+var_14], r9d
0x18000bf6e  cmovz   rcx, r8
0x18000bf72  lea     rax, [rbp+3Fh+var_70]
0x18000bf76  mov     r9d, 6
0x18000bf7c  mov     [rbp+3Fh+var_20], rcx
0x18000bf80  mov     [rsp+0A0h+var_80], rax
0x18000bf85  call    McGenEventWrite_EventWriteTransfer
0x18000bf8a  mov     rcx, [rbp+3Fh+var_10]
0x18000bf8e  xor     rcx, rsp; StackCookie
0x18000bf91  call    __security_check_cookie
0x18000bf96  add     rsp, 0A0h
0x18000bf9d  pop     rbp
0x18000bf9e  retn
```
