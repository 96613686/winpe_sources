# McTemplateK0zsjjtsq_EventWriteTransfer

- ea: `0x14000b5d8`
- end: `0x14000b6fb`
- name: `McTemplateK0zsjjtsq_EventWriteTransfer`
- size: `291`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, __int64, const char *, __int64, __int64, char, const char *, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000afb8`
- `0x14000b200`

## callees

- `0x14000377c`
- `0x14000b5d8`
- `0x14000d1f0`

## pseudocode

```c
ULONG __fastcall McTemplateK0zsjjtsq_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        const char *a5,
        __int64 a6,
        __int64 a7,
        char a8,
        const char *a9,
        char a10)
{
  __int64 v10; // rcx
  __int64 v12; // rax
  const char *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // eax
  const char *v17; // rax
  bool v18; // zf
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+30h] [rbp-69h] BYREF
  WCHAR *v21; // [rsp+40h] [rbp-59h]
  int v22; // [rsp+48h] [rbp-51h]
  int v23; // [rsp+4Ch] [rbp-4Dh]
  const char *v24; // [rsp+50h] [rbp-49h]
  int v25; // [rsp+58h] [rbp-41h]
  int v26; // [rsp+5Ch] [rbp-3Dh]
  __int64 v27; // [rsp+60h] [rbp-39h]
  __int64 v28; // [rsp+68h] [rbp-31h]
  __int64 v29; // [rsp+70h] [rbp-29h]
  __int64 v30; // [rsp+78h] [rbp-21h]
  char *v31; // [rsp+80h] [rbp-19h]
  __int64 v32; // [rsp+88h] [rbp-11h]
  const char *v33; // [rsp+90h] [rbp-9h]
  int v34; // [rsp+98h] [rbp-1h]
  int v35; // [rsp+9Ch] [rbp+3h]
  char *v36; // [rsp+A0h] [rbp+7h]
  __int64 v37; // [rsp+A8h] [rbp+Fh]

  v10 = -1;
  v12 = -1;
  do
    ++v12;
  while ( *(&ModuleName + v12) );
  v21 = &ModuleName;
  v13 = a5;
  v14 = 5;
  v22 = 2 * v12 + 2;
  v23 = 0;
  if ( a5 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a5[v15] );
    v16 = v15 + 1;
  }
  else
  {
    v16 = 5;
  }
  v25 = v16;
  v27 = a6;
  if ( !a5 )
    v13 = "NULL";
  v29 = a7;
  v31 = &a8;
  v17 = a9;
  v24 = v13;
  v26 = 0;
  v28 = 16;
  v30 = 16;
  v32 = 4;
  v18 = a9 == 0;
  if ( a9 )
  {
    do
      ++v10;
    while ( a9[v10] );
    v14 = (unsigned int)(v10 + 1);
    v18 = a9 == 0;
  }
  if ( v18 )
    v17 = "NULL";
  v35 = 0;
  v33 = v17;
  v34 = v14;
  v36 = &a10;
  v37 = 4;
  return McGenEventWrite_EventWriteTransfer((REGHANDLE *)SpaceApiProvider_Context, a2, v14, 8u, &v20);
}

```

## disassembly

```asm
0x14000b5d8  push    rbp
0x14000b5da  lea     rbp, [rsp-27h]
0x14000b5df  sub     rsp, 0C0h
0x14000b5e6  mov     rax, cs:__security_cookie
0x14000b5ed  xor     rax, rsp
0x14000b5f0  mov     [rbp+27h+var_10], rax
0x14000b5f4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000b5f8  mov     r10, rdx
0x14000b5fb  mov     rax, rcx
0x14000b5fe  lea     rdx, ?ModuleName@@3PAGA; ushort near * ModuleName
0x14000b605  xor     r9d, r9d
0x14000b608  inc     rax
0x14000b60b  cmp     [rdx+rax*2], r9w
0x14000b610  jnz     short loc_14000B608
0x14000b612  mov     [rbp+27h+var_80], rdx
0x14000b616  lea     eax, ds:2[rax*2]
0x14000b61d  mov     rdx, [rbp+27h+arg_20]
0x14000b621  mov     r8d, 5
0x14000b627  mov     [rbp+27h+var_78], eax
0x14000b62a  mov     [rbp+27h+var_74], r9d
0x14000b62e  test    rdx, rdx
0x14000b631  jz      short loc_14000B643
0x14000b633  mov     rax, rcx
0x14000b636  inc     rax
0x14000b639  cmp     [rdx+rax], r9b
0x14000b63d  jnz     short loc_14000B636
0x14000b63f  inc     eax
0x14000b641  jmp     short loc_14000B646
0x14000b643  mov     eax, r8d
0x14000b646  mov     [rbp+27h+var_68], eax
0x14000b649  lea     r11, aNull; "NULL"
0x14000b650  mov     rax, [rbp+27h+arg_28]
0x14000b654  test    rdx, rdx
0x14000b657  mov     [rbp+27h+var_60], rax
0x14000b65b  mov     rax, [rbp+27h+arg_30]
0x14000b65f  cmovz   rdx, r11
0x14000b663  mov     [rbp+27h+var_50], rax
0x14000b667  lea     rax, [rbp+27h+arg_38]
0x14000b66b  mov     [rbp+27h+var_40], rax
0x14000b66f  mov     rax, [rbp+27h+arg_40]
0x14000b673  mov     [rbp+27h+var_70], rdx
0x14000b677  mov     [rbp+27h+var_64], r9d
0x14000b67b  mov     [rbp+27h+var_58], 10h
0x14000b683  mov     [rbp+27h+var_48], 10h
0x14000b68b  mov     [rbp+27h+var_38], 4
0x14000b693  test    rax, rax
0x14000b696  jz      short loc_14000B6A8
0x14000b698  inc     rcx
0x14000b69b  cmp     [rax+rcx], r9b
0x14000b69f  jnz     short loc_14000B698
0x14000b6a1  lea     r8d, [rcx+1]
0x14000b6a5  test    rax, rax
0x14000b6a8  cmovz   rax, r11
0x14000b6ac  mov     [rbp+27h+var_24], r9d
0x14000b6b0  mov     [rbp+27h+var_30], rax
0x14000b6b4  lea     rcx, SpaceApiProvider_Context
0x14000b6bb  lea     rax, [rbp+27h+arg_48]
0x14000b6bf  mov     [rbp+27h+var_28], r8d
0x14000b6c3  mov     [rbp+27h+var_20], rax
0x14000b6c7  mov     r9d, 8
0x14000b6cd  lea     rax, [rbp+27h+var_90]
0x14000b6d1  mov     [rbp+27h+var_18], 4
0x14000b6d9  mov     rdx, r10
0x14000b6dc  mov     [rsp+0C0h+var_A0], rax
0x14000b6e1  call    McGenEventWrite_EventWriteTransfer
0x14000b6e6  mov     rcx, [rbp+27h+var_10]
0x14000b6ea  xor     rcx, rsp; StackCookie
0x14000b6ed  call    __security_check_cookie
0x14000b6f2  add     rsp, 0C0h
0x14000b6f9  pop     rbp
0x14000b6fa  retn
```
