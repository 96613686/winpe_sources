# McTemplateU0zdz_EventWriteTransfer

- ea: `0x1800153a8`
- end: `0x180015473`
- name: `McTemplateU0zdz_EventWriteTransfer`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004dd0`

## callees

- `0x1800061d0`
- `0x180006620`
- `0x1800153a8`

## pseudocode

```c
ULONG __fastcall McTemplateU0zdz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        int a4,
        const wchar_t *a5)
{
  __int64 v5; // rax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // ecx
  const wchar_t *v9; // rcx
  bool v10; // zf
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-50h] BYREF
  const wchar_t *v13; // [rsp+40h] [rbp-40h]
  int v14; // [rsp+48h] [rbp-38h]
  int v15; // [rsp+4Ch] [rbp-34h]
  int *v16; // [rsp+50h] [rbp-30h]
  __int64 v17; // [rsp+58h] [rbp-28h]
  const wchar_t *v18; // [rsp+60h] [rbp-20h]
  int v19; // [rsp+68h] [rbp-18h]
  int v20; // [rsp+6Ch] [rbp-14h]
  int v21; // [rsp+A8h] [rbp+28h] BYREF

  v21 = a4;
  v5 = -1;
  v6 = 10;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v14 = v8;
  v15 = 0;
  v16 = &v21;
  v9 = a5;
  if ( !a3 )
    a3 = L"NULL";
  v13 = a3;
  v17 = 4;
  v10 = a5 == 0;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v6 = 2 * v5 + 2;
    v10 = a5 == 0;
  }
  if ( v10 )
    v9 = L"NULL";
  v19 = v6;
  v20 = 0;
  v18 = v9;
  return McGenEventWrite_EventWriteTransfer((__int64)v9, (const EVENT_DESCRIPTOR *)SamConnectEntry, 4, 4u, &v12);
}

```

## disassembly

```asm
0x1800153a8  mov     [rsp-8+arg_18], r9d
0x1800153ad  push    rbp
0x1800153ae  mov     rbp, rsp
0x1800153b1  sub     rsp, 80h
0x1800153b8  mov     rax, cs:__security_cookie
0x1800153bf  xor     rax, rsp
0x1800153c2  mov     [rbp+var_10], rax
0x1800153c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800153ca  xor     r9d, r9d
0x1800153cd  mov     edx, 0Ah
0x1800153d2  test    r8, r8
0x1800153d5  jz      short loc_1800153ED
0x1800153d7  mov     rcx, rax
0x1800153da  inc     rcx
0x1800153dd  cmp     [r8+rcx*2], r9w
0x1800153e2  jnz     short loc_1800153DA
0x1800153e4  lea     ecx, ds:2[rcx*2]
0x1800153eb  jmp     short loc_1800153EF
0x1800153ed  mov     ecx, edx
0x1800153ef  test    r8, r8
0x1800153f2  mov     [rbp+var_38], ecx
0x1800153f5  lea     rcx, [rbp+arg_18]
0x1800153f9  mov     [rbp+var_34], r9d
0x1800153fd  lea     r10, aNull_0; "NULL"
0x180015404  mov     [rbp+var_30], rcx
0x180015408  mov     rcx, [rbp+arg_20]
0x18001540c  cmovz   r8, r10
0x180015410  mov     [rbp+var_40], r8
0x180015414  mov     r8d, 4
0x18001541a  mov     [rbp+var_28], r8
0x18001541e  test    rcx, rcx
0x180015421  jz      short loc_180015437
0x180015423  inc     rax
0x180015426  cmp     [rcx+rax*2], r9w
0x18001542b  jnz     short loc_180015423
0x18001542d  lea     edx, ds:2[rax*2]
0x180015434  test    rcx, rcx
0x180015437  cmovz   rcx, r10
0x18001543b  mov     [rbp+var_18], edx
0x18001543e  mov     [rbp+var_14], r9d
0x180015442  lea     rax, [rbp+var_50]
0x180015446  mov     r9d, r8d
0x180015449  mov     [rbp+var_20], rcx
0x18001544d  lea     rdx, SamConnectEntry
0x180015454  mov     [rsp+80h+var_60], rax
0x180015459  call    McGenEventWrite_EventWriteTransfer
0x18001545e  mov     rcx, [rbp+var_10]
0x180015462  xor     rcx, rsp; StackCookie
0x180015465  call    __security_check_cookie
0x18001546a  add     rsp, 80h
0x180015471  pop     rbp
0x180015472  retn
```
