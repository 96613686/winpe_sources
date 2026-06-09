# McTemplateK0zsjsq_EventWriteTransfer

- ea: `0x14000aaa4`
- end: `0x14000aba7`
- name: `McTemplateK0zsjsq_EventWriteTransfer`
- size: `259`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, __int64, const char *, __int64, const char *, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a7a8`
- `0x14000c018`

## callees

- `0x14000377c`
- `0x14000aaa4`
- `0x14000d1f0`

## pseudocode

```c
ULONG __fastcall McTemplateK0zsjsq_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        const char *a5,
        __int64 a6,
        const char *a7,
        char a8)
{
  __int64 v8; // rcx
  __int64 v10; // rax
  __int64 v11; // r8
  const char *v12; // rax
  __int64 v13; // rdx
  int v14; // edx
  const char *v15; // rax
  bool v16; // zf
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-39h] BYREF
  WCHAR *v19; // [rsp+40h] [rbp-29h]
  int v20; // [rsp+48h] [rbp-21h]
  int v21; // [rsp+4Ch] [rbp-1Dh]
  const char *v22; // [rsp+50h] [rbp-19h]
  int v23; // [rsp+58h] [rbp-11h]
  int v24; // [rsp+5Ch] [rbp-Dh]
  __int64 v25; // [rsp+60h] [rbp-9h]
  __int64 v26; // [rsp+68h] [rbp-1h]
  const char *v27; // [rsp+70h] [rbp+7h]
  int v28; // [rsp+78h] [rbp+Fh]
  int v29; // [rsp+7Ch] [rbp+13h]
  char *v30; // [rsp+80h] [rbp+17h]
  __int64 v31; // [rsp+88h] [rbp+1Fh]

  v8 = -1;
  v10 = -1;
  do
    ++v10;
  while ( *(&ModuleName + v10) );
  v19 = &ModuleName;
  v20 = 2 * v10 + 2;
  v11 = 5;
  v12 = a5;
  v21 = 0;
  if ( a5 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a5[v13] );
    v14 = v13 + 1;
  }
  else
  {
    v14 = 5;
  }
  v23 = v14;
  v24 = 0;
  if ( !a5 )
    v12 = "NULL";
  v26 = 16;
  v22 = v12;
  v25 = a6;
  v15 = a7;
  v16 = a7 == 0;
  if ( a7 )
  {
    do
      ++v8;
    while ( a7[v8] );
    v11 = (unsigned int)(v8 + 1);
    v16 = a7 == 0;
  }
  if ( v16 )
    v15 = "NULL";
  v29 = 0;
  v27 = v15;
  v28 = v11;
  v30 = &a8;
  v31 = 4;
  return McGenEventWrite_EventWriteTransfer((REGHANDLE *)SpaceApiProvider_Context, a2, v11, 6u, &v18);
}

```

## disassembly

```asm
0x14000aaa4  push    rbp
0x14000aaa6  lea     rbp, [rsp-37h]
0x14000aaab  sub     rsp, 0A0h
0x14000aab2  mov     rax, cs:__security_cookie
0x14000aab9  xor     rax, rsp
0x14000aabc  mov     [rbp+37h+var_10], rax
0x14000aac0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000aac4  mov     r10, rdx
0x14000aac7  mov     rax, rcx
0x14000aaca  lea     rdx, ?ModuleName@@3PAGA; ushort near * ModuleName
0x14000aad1  xor     r9d, r9d
0x14000aad4  inc     rax
0x14000aad7  cmp     [rdx+rax*2], r9w
0x14000aadc  jnz     short loc_14000AAD4
0x14000aade  lea     eax, ds:2[rax*2]
0x14000aae5  mov     [rbp+37h+var_60], rdx
0x14000aae9  mov     [rbp+37h+var_58], eax
0x14000aaec  mov     r8d, 5
0x14000aaf2  mov     rax, [rbp+37h+arg_20]
0x14000aaf6  mov     [rbp+37h+var_54], r9d
0x14000aafa  test    rax, rax
0x14000aafd  jz      short loc_14000AB0F
0x14000aaff  mov     rdx, rcx
0x14000ab02  inc     rdx
0x14000ab05  cmp     [rax+rdx], r9b
0x14000ab09  jnz     short loc_14000AB02
0x14000ab0b  inc     edx
0x14000ab0d  jmp     short loc_14000AB12
0x14000ab0f  mov     edx, r8d
0x14000ab12  test    rax, rax
0x14000ab15  mov     [rbp+37h+var_48], edx
0x14000ab18  lea     r11, aNull; "NULL"
0x14000ab1f  mov     [rbp+37h+var_44], r9d
0x14000ab23  cmovz   rax, r11
0x14000ab27  mov     [rbp+37h+var_38], 10h
0x14000ab2f  mov     [rbp+37h+var_50], rax
0x14000ab33  mov     rax, [rbp+37h+arg_28]
0x14000ab37  mov     [rbp+37h+var_40], rax
0x14000ab3b  mov     rax, [rbp+37h+arg_30]
0x14000ab3f  test    rax, rax
0x14000ab42  jz      short loc_14000AB54
0x14000ab44  inc     rcx
0x14000ab47  cmp     [rax+rcx], r9b
0x14000ab4b  jnz     short loc_14000AB44
0x14000ab4d  lea     r8d, [rcx+1]
0x14000ab51  test    rax, rax
0x14000ab54  cmovz   rax, r11
0x14000ab58  mov     [rbp+37h+var_24], r9d
0x14000ab5c  mov     [rbp+37h+var_30], rax
0x14000ab60  lea     rcx, SpaceApiProvider_Context
0x14000ab67  lea     rax, [rbp+37h+arg_38]
0x14000ab6b  mov     [rbp+37h+var_28], r8d
0x14000ab6f  mov     [rbp+37h+var_20], rax
0x14000ab73  mov     r9d, 6
0x14000ab79  lea     rax, [rbp+37h+var_70]
0x14000ab7d  mov     [rbp+37h+var_18], 4
0x14000ab85  mov     rdx, r10
0x14000ab88  mov     [rsp+0A0h+var_80], rax
0x14000ab8d  call    McGenEventWrite_EventWriteTransfer
0x14000ab92  mov     rcx, [rbp+37h+var_10]
0x14000ab96  xor     rcx, rsp; StackCookie
0x14000ab99  call    __security_check_cookie
0x14000ab9e  add     rsp, 0A0h
0x14000aba5  pop     rbp
0x14000aba6  retn
```
