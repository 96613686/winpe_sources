# McTemplateU0pqqqqz_EventWriteTransfer

- ea: `0x18000bde4`
- end: `0x18000beca`
- name: `McTemplateU0pqqqqz_EventWriteTransfer`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010410`

## callees

- `0x1800061d0`
- `0x180006620`
- `0x18000bde4`

## pseudocode

```c
ULONG __fastcall McTemplateU0pqqqqz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        char a7,
        const wchar_t *a8)
{
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-49h] BYREF
  __int64 *v13; // [rsp+40h] [rbp-39h]
  __int64 v14; // [rsp+48h] [rbp-31h]
  int *v15; // [rsp+50h] [rbp-29h]
  __int64 v16; // [rsp+58h] [rbp-21h]
  char *v17; // [rsp+60h] [rbp-19h]
  __int64 v18; // [rsp+68h] [rbp-11h]
  char *v19; // [rsp+70h] [rbp-9h]
  __int64 v20; // [rsp+78h] [rbp-1h]
  char *v21; // [rsp+80h] [rbp+7h]
  __int64 v22; // [rsp+88h] [rbp+Fh]
  const wchar_t *v23; // [rsp+90h] [rbp+17h]
  int v24; // [rsp+98h] [rbp+1Fh]
  int v25; // [rsp+9Ch] [rbp+23h]
  __int64 v26; // [rsp+D0h] [rbp+57h] BYREF
  int v27; // [rsp+D8h] [rbp+5Fh] BYREF

  v27 = a4;
  v26 = a3;
  v8 = a8;
  v13 = &v26;
  v14 = 8;
  v15 = &v27;
  v17 = &a5;
  v19 = &a6;
  v21 = &a7;
  v16 = 4;
  v18 = 4;
  v20 = 4;
  v22 = 4;
  if ( a8 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a8[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v24 = v10;
  v25 = 0;
  if ( !a8 )
    v8 = L"NULL";
  v23 = v8;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v8,
           (const EVENT_DESCRIPTOR *)SamQueryDisplayInformationEntry,
           0,
           7u,
           &v12);
}

```

## disassembly

```asm
0x18000bde4  mov     [rsp-8+arg_18], r9d
0x18000bde9  mov     [rsp-8+arg_10], r8
0x18000bdee  push    rbp
0x18000bdef  lea     rbp, [rsp-37h]
0x18000bdf4  sub     rsp, 0B0h
0x18000bdfb  mov     rax, cs:__security_cookie
0x18000be02  xor     rax, rsp
0x18000be05  mov     [rbp+37h+var_10], rax
0x18000be09  mov     rcx, [rbp+37h+arg_38]
0x18000be0d  lea     rax, [rbp+37h+arg_10]
0x18000be11  mov     [rbp+37h+var_70], rax
0x18000be15  xor     r8d, r8d
0x18000be18  mov     [rbp+37h+var_68], 8
0x18000be20  lea     rax, [rbp+37h+arg_18]
0x18000be24  mov     [rbp+37h+var_60], rax
0x18000be28  lea     rax, [rbp+37h+arg_20]
0x18000be2c  mov     [rbp+37h+var_50], rax
0x18000be30  lea     rax, [rbp+37h+arg_28]
0x18000be34  mov     [rbp+37h+var_40], rax
0x18000be38  lea     rax, [rbp+37h+arg_30]
0x18000be3c  mov     [rbp+37h+var_30], rax
0x18000be40  mov     [rbp+37h+var_58], 4
0x18000be48  mov     [rbp+37h+var_48], 4
0x18000be50  mov     [rbp+37h+var_38], 4
0x18000be58  mov     [rbp+37h+var_28], 4
0x18000be60  test    rcx, rcx
0x18000be63  jz      short loc_18000BE7C
0x18000be65  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000be69  inc     rax
0x18000be6c  cmp     [rcx+rax*2], r8w
0x18000be71  jnz     short loc_18000BE69
0x18000be73  lea     eax, ds:2[rax*2]
0x18000be7a  jmp     short loc_18000BE81
0x18000be7c  mov     eax, 0Ah
0x18000be81  test    rcx, rcx
0x18000be84  mov     [rbp+37h+var_18], eax
0x18000be87  lea     rdx, aNull_0; "NULL"
0x18000be8e  mov     [rbp+37h+var_14], r8d
0x18000be92  cmovz   rcx, rdx
0x18000be96  lea     rax, [rbp+37h+var_80]
0x18000be9a  lea     rdx, SamQueryDisplayInformationEntry
0x18000bea1  mov     [rbp+37h+var_20], rcx
0x18000bea5  mov     r9d, 7
0x18000beab  mov     [rsp+0B0h+var_90], rax
0x18000beb0  call    McGenEventWrite_EventWriteTransfer
0x18000beb5  mov     rcx, [rbp+37h+var_10]
0x18000beb9  xor     rcx, rsp; StackCookie
0x18000bebc  call    __security_check_cookie
0x18000bec1  add     rsp, 0B0h
0x18000bec8  pop     rbp
0x18000bec9  retn
```
