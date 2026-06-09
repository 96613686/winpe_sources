# McTemplateK0qzqq_EtwWriteTransfer

- ea: `0x14000d7f8`
- end: `0x14000d8c0`
- name: `McTemplateK0qzqq_EtwWriteTransfer`
- size: `200`
- prototype: ``
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x14001448c`
- `0x14002f9fc`
- `0x1400300c4`
- `0x1400308ac`
- `0x140032314`
- `0x1400323e8`
- `0x1400324b8`
- `0x140032600`
- `0x140032770`
- `0x140032838`
- `0x140032948`
- `0x140032f48`
- `0x140035078`
- `0x140035580`

## callees

- `0x1400095bc`
- `0x14000d7f8`
- `0x14001ede0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qzqq_EtwWriteTransfer(
        REGHANDLE *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        const wchar_t *a5,
        char a6,
        char a7)
{
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-21h] BYREF
  int *v13; // [rsp+40h] [rbp-11h]
  __int64 v14; // [rsp+48h] [rbp-9h]
  const wchar_t *v15; // [rsp+50h] [rbp-1h]
  int v16; // [rsp+58h] [rbp+7h]
  int v17; // [rsp+5Ch] [rbp+Bh]
  char *v18; // [rsp+60h] [rbp+Fh]
  __int64 v19; // [rsp+68h] [rbp+17h]
  char *v20; // [rsp+70h] [rbp+1Fh]
  __int64 v21; // [rsp+78h] [rbp+27h]
  int v22; // [rsp+B8h] [rbp+67h] BYREF

  v22 = a4;
  v14 = 4;
  v8 = a5;
  v13 = &v22;
  if ( a5 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a5[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v16 = v10;
  v17 = 0;
  v19 = 4;
  if ( !a5 )
    v8 = L"NULL";
  v18 = &a6;
  v15 = v8;
  v20 = &a7;
  v21 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)WINNATM_GENERAL_ERROR, (__int64)a1, 5u, &v12);
}

```

## disassembly

```asm
0x14000d7f8  mov     [rsp-8+arg_18], r9d
0x14000d7fd  push    rbp
0x14000d7fe  lea     rbp, [rsp-3Fh]
0x14000d803  sub     rsp, 90h
0x14000d80a  mov     rax, cs:__security_cookie
0x14000d811  xor     rax, rsp
0x14000d814  mov     [rbp+3Fh+var_10], rax
0x14000d818  mov     r8, rcx
0x14000d81b  mov     [rbp+3Fh+var_48], 4
0x14000d823  mov     rcx, [rbp+3Fh+arg_20]
0x14000d827  lea     rax, [rbp+3Fh+arg_18]
0x14000d82b  xor     r9d, r9d
0x14000d82e  mov     [rbp+3Fh+var_50], rax
0x14000d832  test    rcx, rcx
0x14000d835  jz      short loc_14000D84E
0x14000d837  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d83b  inc     rax
0x14000d83e  cmp     [rcx+rax*2], r9w
0x14000d843  jnz     short loc_14000D83B
0x14000d845  lea     eax, ds:2[rax*2]
0x14000d84c  jmp     short loc_14000D853
0x14000d84e  mov     eax, 0Ah
0x14000d853  mov     [rbp+3Fh+var_38], eax
0x14000d856  lea     rdx, aNull; "NULL"
0x14000d85d  test    rcx, rcx
0x14000d860  mov     [rbp+3Fh+var_34], r9d
0x14000d864  lea     rax, [rbp+3Fh+arg_28]
0x14000d868  mov     [rbp+3Fh+var_28], 4
0x14000d870  cmovz   rcx, rdx
0x14000d874  mov     [rbp+3Fh+var_30], rax
0x14000d878  lea     rax, [rbp+3Fh+arg_30]
0x14000d87c  mov     [rbp+3Fh+var_40], rcx
0x14000d880  mov     [rbp+3Fh+var_20], rax
0x14000d884  lea     rdx, WINNATM_GENERAL_ERROR
0x14000d88b  lea     rax, [rbp+3Fh+var_60]
0x14000d88f  mov     [rbp+3Fh+var_18], 4
0x14000d897  mov     r9d, 5
0x14000d89d  mov     [rsp+90h+var_70], rax
0x14000d8a2  mov     rcx, r8
0x14000d8a5  call    McGenEventWrite_EtwWriteTransfer
0x14000d8aa  mov     rcx, [rbp+3Fh+var_10]
0x14000d8ae  xor     rcx, rsp; StackCookie
0x14000d8b1  call    __security_check_cookie
0x14000d8b6  add     rsp, 90h
0x14000d8bd  pop     rbp
0x14000d8be  retn
```
