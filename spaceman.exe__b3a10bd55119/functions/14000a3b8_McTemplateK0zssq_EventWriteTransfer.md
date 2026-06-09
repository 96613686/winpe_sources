# McTemplateK0zssq_EventWriteTransfer

- ea: `0x14000a3b8`
- end: `0x14000a4aa`
- name: `McTemplateK0zssq_EventWriteTransfer`
- size: `242`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, __int64, const char *, const char *, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140002074`
- `0x140009328`

## callees

- `0x14000377c`
- `0x14000a3b8`
- `0x14000d1f0`

## pseudocode

```c
ULONG __fastcall McTemplateK0zssq_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        const char *a5,
        const char *a6,
        char a7)
{
  __int64 v7; // rcx
  __int64 v9; // rax
  const char *v10; // rax
  __int64 v11; // rdx
  int v12; // edx
  const char *v13; // rax
  int v14; // ecx
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+30h] [rbp-21h] BYREF
  WCHAR *v17; // [rsp+40h] [rbp-11h]
  int v18; // [rsp+48h] [rbp-9h]
  int v19; // [rsp+4Ch] [rbp-5h]
  const char *v20; // [rsp+50h] [rbp-1h]
  int v21; // [rsp+58h] [rbp+7h]
  int v22; // [rsp+5Ch] [rbp+Bh]
  const char *v23; // [rsp+60h] [rbp+Fh]
  int v24; // [rsp+68h] [rbp+17h]
  int v25; // [rsp+6Ch] [rbp+1Bh]
  char *v26; // [rsp+70h] [rbp+1Fh]
  __int64 v27; // [rsp+78h] [rbp+27h]

  v7 = -1;
  v9 = -1;
  do
    ++v9;
  while ( *(&ModuleName + v9) );
  v17 = &ModuleName;
  v18 = 2 * v9 + 2;
  v10 = a5;
  v19 = 0;
  if ( a5 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a5[v11] );
    v12 = v11 + 1;
  }
  else
  {
    v12 = 5;
  }
  v21 = v12;
  v22 = 0;
  if ( !a5 )
    v10 = "NULL";
  v20 = v10;
  v13 = a6;
  if ( a6 )
  {
    do
      ++v7;
    while ( a6[v7] );
    v14 = v7 + 1;
  }
  else
  {
    v14 = 5;
  }
  v24 = v14;
  v25 = 0;
  if ( !a6 )
    v13 = "NULL";
  v27 = 4;
  v23 = v13;
  v26 = &a7;
  return McGenEventWrite_EventWriteTransfer((REGHANDLE *)SpaceApiProvider_Context, a2, (__int64)a2, 5u, &v16);
}

```

## disassembly

```asm
0x14000a3b8  push    rbp
0x14000a3ba  lea     rbp, [rsp-3Fh]
0x14000a3bf  sub     rsp, 90h
0x14000a3c6  mov     rax, cs:__security_cookie
0x14000a3cd  xor     rax, rsp
0x14000a3d0  mov     [rbp+3Fh+var_10], rax
0x14000a3d4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000a3d8  mov     r8, rdx
0x14000a3db  mov     rax, rcx
0x14000a3de  lea     rdx, ?ModuleName@@3PAGA; ushort near * ModuleName
0x14000a3e5  xor     r9d, r9d
0x14000a3e8  inc     rax
0x14000a3eb  cmp     [rdx+rax*2], r9w
0x14000a3f0  jnz     short loc_14000A3E8
0x14000a3f2  lea     eax, ds:2[rax*2]
0x14000a3f9  mov     [rbp+3Fh+var_50], rdx
0x14000a3fd  mov     [rbp+3Fh+var_48], eax
0x14000a400  mov     r10d, 5
0x14000a406  mov     rax, [rbp+3Fh+arg_20]
0x14000a40a  mov     [rbp+3Fh+var_44], r9d
0x14000a40e  test    rax, rax
0x14000a411  jz      short loc_14000A423
0x14000a413  mov     rdx, rcx
0x14000a416  inc     rdx
0x14000a419  cmp     [rax+rdx], r9b
0x14000a41d  jnz     short loc_14000A416
0x14000a41f  inc     edx
0x14000a421  jmp     short loc_14000A426
0x14000a423  mov     edx, r10d
0x14000a426  test    rax, rax
0x14000a429  mov     [rbp+3Fh+var_38], edx
0x14000a42c  lea     r11, aNull; "NULL"
0x14000a433  mov     [rbp+3Fh+var_34], r9d
0x14000a437  cmovz   rax, r11
0x14000a43b  mov     [rbp+3Fh+var_40], rax
0x14000a43f  mov     rax, [rbp+3Fh+arg_28]
0x14000a443  test    rax, rax
0x14000a446  jz      short loc_14000A455
0x14000a448  inc     rcx
0x14000a44b  cmp     [rax+rcx], r9b
0x14000a44f  jnz     short loc_14000A448
0x14000a451  inc     ecx
0x14000a453  jmp     short loc_14000A458
0x14000a455  mov     ecx, r10d
0x14000a458  test    rax, rax
0x14000a45b  mov     [rbp+3Fh+var_28], ecx
0x14000a45e  mov     [rbp+3Fh+var_24], r9d
0x14000a462  lea     rcx, SpaceApiProvider_Context
0x14000a469  cmovz   rax, r11
0x14000a46d  mov     [rbp+3Fh+var_18], 4
0x14000a475  mov     [rbp+3Fh+var_30], rax
0x14000a479  mov     r9d, r10d
0x14000a47c  lea     rax, [rbp+3Fh+arg_30]
0x14000a480  mov     rdx, r8
0x14000a483  mov     [rbp+3Fh+var_20], rax
0x14000a487  lea     rax, [rbp+3Fh+var_60]
0x14000a48b  mov     [rsp+90h+var_70], rax
0x14000a490  call    McGenEventWrite_EventWriteTransfer
0x14000a495  mov     rcx, [rbp+3Fh+var_10]
0x14000a499  xor     rcx, rsp; StackCookie
0x14000a49c  call    __security_check_cookie
0x14000a4a1  add     rsp, 90h
0x14000a4a8  pop     rbp
0x14000a4a9  retn
```
