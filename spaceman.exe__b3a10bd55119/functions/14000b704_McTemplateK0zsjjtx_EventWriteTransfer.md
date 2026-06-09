# McTemplateK0zsjjtx_EventWriteTransfer

- ea: `0x14000b704`
- end: `0x14000b7f1`
- name: `McTemplateK0zsjjtx_EventWriteTransfer`
- size: `237`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, __int64, const char *, __int64, __int64, char, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000afb8`
- `0x14000b200`

## callees

- `0x14000377c`
- `0x14000b704`
- `0x14000d1f0`

## pseudocode

```c
ULONG __fastcall McTemplateK0zsjjtx_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        const char *a5,
        __int64 a6,
        __int64 a7,
        char a8,
        char a9)
{
  __int64 v9; // rcx
  __int64 v10; // rax
  const char *v11; // rax
  int v12; // ecx
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-51h] BYREF
  WCHAR *v15; // [rsp+40h] [rbp-41h]
  int v16; // [rsp+48h] [rbp-39h]
  int v17; // [rsp+4Ch] [rbp-35h]
  const char *v18; // [rsp+50h] [rbp-31h]
  int v19; // [rsp+58h] [rbp-29h]
  int v20; // [rsp+5Ch] [rbp-25h]
  __int64 v21; // [rsp+60h] [rbp-21h]
  __int64 v22; // [rsp+68h] [rbp-19h]
  __int64 v23; // [rsp+70h] [rbp-11h]
  __int64 v24; // [rsp+78h] [rbp-9h]
  char *v25; // [rsp+80h] [rbp-1h]
  __int64 v26; // [rsp+88h] [rbp+7h]
  char *v27; // [rsp+90h] [rbp+Fh]
  __int64 v28; // [rsp+98h] [rbp+17h]

  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( *(&ModuleName + v10) );
  v15 = &ModuleName;
  v16 = 2 * v10 + 2;
  v11 = a5;
  v17 = 0;
  if ( a5 )
  {
    do
      ++v9;
    while ( a5[v9] );
    v12 = v9 + 1;
  }
  else
  {
    v12 = 5;
  }
  v19 = v12;
  v20 = 0;
  if ( !a5 )
    v11 = "NULL";
  v22 = 16;
  v18 = v11;
  v21 = a6;
  v23 = a7;
  v25 = &a8;
  v27 = &a9;
  v24 = 16;
  v26 = 4;
  v28 = 8;
  return McGenEventWrite_EventWriteTransfer((REGHANDLE *)SpaceApiProvider_Context, a2, (__int64)"NULL", 7u, &v14);
}

```

## disassembly

```asm
0x14000b704  push    rbp
0x14000b706  lea     rbp, [rsp-2Fh]
0x14000b70b  sub     rsp, 0B0h
0x14000b712  mov     rax, cs:__security_cookie
0x14000b719  xor     rax, rsp
0x14000b71c  mov     [rbp+2Fh+var_10], rax
0x14000b720  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000b724  lea     r8, ?ModuleName@@3PAGA; ushort near * ModuleName
0x14000b72b  mov     rax, rcx
0x14000b72e  xor     r9d, r9d
0x14000b731  inc     rax
0x14000b734  cmp     [r8+rax*2], r9w
0x14000b739  jnz     short loc_14000B731
0x14000b73b  lea     eax, ds:2[rax*2]
0x14000b742  mov     [rbp+2Fh+var_70], r8
0x14000b746  mov     [rbp+2Fh+var_68], eax
0x14000b749  mov     rax, [rbp+2Fh+arg_20]
0x14000b74d  mov     [rbp+2Fh+var_64], r9d
0x14000b751  test    rax, rax
0x14000b754  jz      short loc_14000B763
0x14000b756  inc     rcx
0x14000b759  cmp     [rax+rcx], r9b
0x14000b75d  jnz     short loc_14000B756
0x14000b75f  inc     ecx
0x14000b761  jmp     short loc_14000B768
0x14000b763  mov     ecx, 5
0x14000b768  test    rax, rax
0x14000b76b  mov     [rbp+2Fh+var_58], ecx
0x14000b76e  lea     r8, aNull; "NULL"
0x14000b775  mov     [rbp+2Fh+var_54], r9d
0x14000b779  cmovz   rax, r8
0x14000b77d  mov     [rbp+2Fh+var_48], 10h
0x14000b785  mov     [rbp+2Fh+var_60], rax
0x14000b789  lea     rcx, SpaceApiProvider_Context
0x14000b790  mov     rax, [rbp+2Fh+arg_28]
0x14000b794  mov     r9d, 7
0x14000b79a  mov     [rbp+2Fh+var_50], rax
0x14000b79e  mov     rax, [rbp+2Fh+arg_30]
0x14000b7a2  mov     [rbp+2Fh+var_40], rax
0x14000b7a6  lea     rax, [rbp+2Fh+arg_38]
0x14000b7aa  mov     [rbp+2Fh+var_30], rax
0x14000b7ae  lea     rax, [rbp+2Fh+arg_40]
0x14000b7b2  mov     [rbp+2Fh+var_20], rax
0x14000b7b6  lea     rax, [rbp+2Fh+var_80]
0x14000b7ba  mov     [rsp+0B0h+var_90], rax
0x14000b7bf  mov     [rbp+2Fh+var_38], 10h
0x14000b7c7  mov     [rbp+2Fh+var_28], 4
0x14000b7cf  mov     [rbp+2Fh+var_18], 8
0x14000b7d7  call    McGenEventWrite_EventWriteTransfer
0x14000b7dc  mov     rcx, [rbp+2Fh+var_10]
0x14000b7e0  xor     rcx, rsp; StackCookie
0x14000b7e3  call    __security_check_cookie
0x14000b7e8  add     rsp, 0B0h
0x14000b7ef  pop     rbp
0x14000b7f0  retn
```
