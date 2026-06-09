# McTemplateU0pqkz_EventWriteTransfer

- ea: `0x1800152bc`
- end: `0x1800153a0`
- name: `McTemplateU0pqkz_EventWriteTransfer`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002a80`

## callees

- `0x1800061d0`
- `0x180006620`
- `0x1800152bc`

## pseudocode

```c
ULONG __fastcall McTemplateU0pqkz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        const wchar_t *a6)
{
  __int64 *v6; // rcx
  int v7; // eax
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-19h] BYREF
  __int64 *v13; // [rsp+40h] [rbp-9h]
  __int64 v14; // [rsp+48h] [rbp-1h]
  int *v15; // [rsp+50h] [rbp+7h]
  __int64 v16; // [rsp+58h] [rbp+Fh]
  __int64 *v17; // [rsp+60h] [rbp+17h]
  int v18; // [rsp+68h] [rbp+1Fh]
  int v19; // [rsp+6Ch] [rbp+23h]
  const wchar_t *v20; // [rsp+70h] [rbp+27h]
  int v21; // [rsp+78h] [rbp+2Fh]
  int v22; // [rsp+7Ch] [rbp+33h]
  __int64 v23; // [rsp+B0h] [rbp+67h] BYREF
  int v24; // [rsp+B8h] [rbp+6Fh] BYREF

  v24 = a4;
  v23 = a3;
  v16 = 4;
  v13 = &v23;
  v15 = &v24;
  v6 = (__int64 *)a5;
  v7 = 8;
  v14 = 8;
  if ( a5 )
    v7 = 4 * *(unsigned __int8 *)(a5 + 1) + 8;
  v18 = v7;
  v19 = 0;
  if ( !a5 )
    v6 = &qword_180020BB8;
  v17 = v6;
  v8 = a6;
  if ( a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a6[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v21 = v10;
  v22 = 0;
  if ( !a6 )
    v8 = L"NULL";
  v20 = v8;
  return McGenEventWrite_EventWriteTransfer((__int64)v8, (const EVENT_DESCRIPTOR *)SamOpenDomainEntry, 0, 5u, &v12);
}

```

## disassembly

```asm
0x1800152bc  mov     [rsp-8+arg_18], r9d
0x1800152c1  mov     [rsp-8+arg_10], r8
0x1800152c6  push    rbp
0x1800152c7  lea     rbp, [rsp-47h]
0x1800152cc  sub     rsp, 90h
0x1800152d3  mov     rax, cs:__security_cookie
0x1800152da  xor     rax, rsp
0x1800152dd  mov     [rbp+47h+var_10], rax
0x1800152e1  lea     rax, [rbp+47h+arg_10]
0x1800152e5  mov     [rbp+47h+var_38], 4
0x1800152ed  lea     rcx, [rbp+47h+arg_18]
0x1800152f1  mov     [rbp+47h+var_50], rax
0x1800152f5  mov     [rbp+47h+var_40], rcx
0x1800152f9  xor     r8d, r8d
0x1800152fc  mov     rcx, [rbp+47h+arg_20]
0x180015300  mov     eax, 8
0x180015305  mov     [rbp+47h+var_48], rax
0x180015309  test    rcx, rcx
0x18001530c  jz      short loc_180015319
0x18001530e  movzx   eax, byte ptr [rcx+1]
0x180015312  lea     eax, ds:8[rax*4]
0x180015319  test    rcx, rcx
0x18001531c  mov     [rbp+47h+var_28], eax
0x18001531f  lea     rdx, qword_180020BB8
0x180015326  mov     [rbp+47h+var_24], r8d
0x18001532a  cmovz   rcx, rdx
0x18001532e  mov     [rbp+47h+var_30], rcx
0x180015332  mov     rcx, [rbp+47h+arg_28]
0x180015336  test    rcx, rcx
0x180015339  jz      short loc_180015352
0x18001533b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001533f  inc     rax
0x180015342  cmp     [rcx+rax*2], r8w
0x180015347  jnz     short loc_18001533F
0x180015349  lea     eax, ds:2[rax*2]
0x180015350  jmp     short loc_180015357
0x180015352  mov     eax, 0Ah
0x180015357  test    rcx, rcx
0x18001535a  mov     [rbp+47h+var_18], eax
0x18001535d  lea     rdx, aNull_0; "NULL"
0x180015364  mov     [rbp+47h+var_14], r8d
0x180015368  cmovz   rcx, rdx
0x18001536c  lea     rax, [rbp+47h+var_60]
0x180015370  lea     rdx, SamOpenDomainEntry
0x180015377  mov     [rbp+47h+var_20], rcx
0x18001537b  mov     r9d, 5
0x180015381  mov     [rsp+90h+var_70], rax
0x180015386  call    McGenEventWrite_EventWriteTransfer
0x18001538b  mov     rcx, [rbp+47h+var_10]
0x18001538f  xor     rcx, rsp; StackCookie
0x180015392  call    __security_check_cookie
0x180015397  add     rsp, 90h
0x18001539e  pop     rbp
0x18001539f  retn
```
