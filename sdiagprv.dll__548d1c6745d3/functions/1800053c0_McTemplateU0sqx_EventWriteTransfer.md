# McTemplateU0sqx_EventWriteTransfer

- ea: `0x1800053c0`
- end: `0x18000545f`
- name: `McTemplateU0sqx_EventWriteTransfer`
- size: `159`
- prototype: `ULONG __fastcall(__int64, __int64, const char *, int, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005040`
- `0x1800116d0`

## callees

- `0x18000247c`
- `0x1800053c0`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0sqx_EventWriteTransfer(__int64 a1, __int64 a2, const char *a3, int a4, char a5)
{
  __int64 v5; // rax
  int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-50h] BYREF
  const char *v9; // [rsp+40h] [rbp-40h]
  int v10; // [rsp+48h] [rbp-38h]
  int v11; // [rsp+4Ch] [rbp-34h]
  int *v12; // [rsp+50h] [rbp-30h]
  __int64 v13; // [rsp+58h] [rbp-28h]
  char *v14; // [rsp+60h] [rbp-20h]
  __int64 v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+A8h] [rbp+28h] BYREF

  v16 = a4;
  if ( a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  v10 = v6;
  v11 = 0;
  v12 = &v16;
  v15 = 8;
  v14 = &a5;
  if ( !a3 )
    a3 = "NULL";
  v9 = a3;
  v13 = 4;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)"NULL",
           (const EVENT_DESCRIPTOR *)SDIAGPRV_EVENT_DEBUG_GET_ITEM_ERRORNOTFOUND,
           (__int64)a3,
           4u,
           &v8);
}

```

## disassembly

```asm
0x1800053c0  mov     [rsp-8+arg_18], r9d
0x1800053c5  push    rbp
0x1800053c6  mov     rbp, rsp
0x1800053c9  sub     rsp, 80h
0x1800053d0  mov     rax, cs:__security_cookie
0x1800053d7  xor     rax, rsp
0x1800053da  mov     [rbp+var_10], rax
0x1800053de  xor     edx, edx
0x1800053e0  test    r8, r8
0x1800053e3  jz      short loc_1800053F6
0x1800053e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800053e9  inc     rax
0x1800053ec  cmp     [r8+rax], dl
0x1800053f0  jnz     short loc_1800053E9
0x1800053f2  inc     eax
0x1800053f4  jmp     short loc_1800053FB
0x1800053f6  mov     eax, 5
0x1800053fb  mov     [rbp+var_38], eax
0x1800053fe  lea     rcx, aNull; "NULL"
0x180005405  lea     rax, [rbp+arg_18]
0x180005409  mov     [rbp+var_34], edx
0x18000540c  mov     [rbp+var_30], rax
0x180005410  lea     rdx, SDIAGPRV_EVENT_DEBUG_GET_ITEM_ERRORNOTFOUND
0x180005417  lea     rax, [rbp+arg_20]
0x18000541b  mov     [rbp+var_18], 8
0x180005423  test    r8, r8
0x180005426  mov     [rbp+var_20], rax
0x18000542a  lea     rax, [rbp+var_50]
0x18000542e  mov     r9d, 4
0x180005434  cmovz   r8, rcx
0x180005438  mov     [rsp+80h+var_60], rax
0x18000543d  mov     [rbp+var_40], r8
0x180005441  mov     [rbp+var_28], r9
0x180005445  call    McGenEventWrite_EventWriteTransfer
0x18000544a  mov     rcx, [rbp+var_10]
0x18000544e  xor     rcx, rsp; StackCookie
0x180005451  call    __security_check_cookie
0x180005456  add     rsp, 80h
0x18000545d  pop     rbp
0x18000545e  retn
```
