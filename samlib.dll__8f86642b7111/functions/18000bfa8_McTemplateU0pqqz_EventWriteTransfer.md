# McTemplateU0pqqz_EventWriteTransfer

- ea: `0x18000bfa8`
- end: `0x18000c067`
- name: `McTemplateU0pqqz_EventWriteTransfer`
- size: `191`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800016a0`
- `0x180002e90`
- `0x18000c850`
- `0x18000fed0`
- `0x180010170`
- `0x180011ec0`

## callees

- `0x1800061d0`
- `0x180006620`
- `0x18000bfa8`

## pseudocode

```c
ULONG __fastcall McTemplateU0pqqz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        char a5,
        const wchar_t *a6)
{
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-19h] BYREF
  __int64 *v11; // [rsp+40h] [rbp-9h]
  __int64 v12; // [rsp+48h] [rbp-1h]
  int *v13; // [rsp+50h] [rbp+7h]
  __int64 v14; // [rsp+58h] [rbp+Fh]
  char *v15; // [rsp+60h] [rbp+17h]
  __int64 v16; // [rsp+68h] [rbp+1Fh]
  const wchar_t *v17; // [rsp+70h] [rbp+27h]
  int v18; // [rsp+78h] [rbp+2Fh]
  int v19; // [rsp+7Ch] [rbp+33h]
  __int64 v20; // [rsp+B0h] [rbp+67h] BYREF
  int v21; // [rsp+B8h] [rbp+6Fh] BYREF

  v21 = a4;
  v20 = a3;
  v6 = a6;
  v11 = &v20;
  v12 = 8;
  v13 = &v21;
  v15 = &a5;
  v14 = 4;
  v16 = 4;
  if ( a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a6[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v18 = v8;
  v19 = 0;
  if ( !a6 )
    v6 = L"NULL";
  v17 = v6;
  return McGenEventWrite_EventWriteTransfer((__int64)v6, a2, (__int64)L"NULL", 5u, &v10);
}

```

## disassembly

```asm
0x18000bfa8  mov     [rsp-8+arg_18], r9d
0x18000bfad  mov     [rsp-8+arg_10], r8
0x18000bfb2  push    rbp
0x18000bfb3  lea     rbp, [rsp-47h]
0x18000bfb8  sub     rsp, 90h
0x18000bfbf  mov     rax, cs:__security_cookie
0x18000bfc6  xor     rax, rsp
0x18000bfc9  mov     [rbp+47h+var_10], rax
0x18000bfcd  mov     rcx, [rbp+47h+arg_28]
0x18000bfd1  lea     rax, [rbp+47h+arg_10]
0x18000bfd5  mov     [rbp+47h+var_50], rax
0x18000bfd9  xor     r9d, r9d
0x18000bfdc  mov     [rbp+47h+var_48], 8
0x18000bfe4  lea     rax, [rbp+47h+arg_18]
0x18000bfe8  mov     [rbp+47h+var_40], rax
0x18000bfec  lea     rax, [rbp+47h+arg_20]
0x18000bff0  mov     [rbp+47h+var_30], rax
0x18000bff4  mov     [rbp+47h+var_38], 4
0x18000bffc  mov     [rbp+47h+var_28], 4
0x18000c004  test    rcx, rcx
0x18000c007  jz      short loc_18000C020
0x18000c009  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c00d  inc     rax
0x18000c010  cmp     [rcx+rax*2], r9w
0x18000c015  jnz     short loc_18000C00D
0x18000c017  lea     eax, ds:2[rax*2]
0x18000c01e  jmp     short loc_18000C025
0x18000c020  mov     eax, 0Ah
0x18000c025  test    rcx, rcx
0x18000c028  mov     [rbp+47h+var_18], eax
0x18000c02b  lea     r8, aNull_0; "NULL"
0x18000c032  mov     [rbp+47h+var_14], r9d
0x18000c036  cmovz   rcx, r8
0x18000c03a  lea     rax, [rbp+47h+var_60]
0x18000c03e  mov     r9d, 5
0x18000c044  mov     [rbp+47h+var_20], rcx
0x18000c048  mov     [rsp+90h+var_70], rax
0x18000c04d  call    McGenEventWrite_EventWriteTransfer
0x18000c052  mov     rcx, [rbp+47h+var_10]
0x18000c056  xor     rcx, rsp; StackCookie
0x18000c059  call    __security_check_cookie
0x18000c05e  add     rsp, 90h
0x18000c065  pop     rbp
0x18000c066  retn
```
