# McTemplateU0dzz_EventWriteTransfer

- ea: `0x18000d030`
- end: `0x18000d0fa`
- name: `McTemplateU0dzz_EventWriteTransfer`
- size: `202`
- prototype: `ULONG __fastcall(__int64, __int64, int, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c980`
- `0x18000cafc`

## callees

- `0x18000247c`
- `0x18000d030`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0dzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        int a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  __int64 v5; // rax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // ecx
  const wchar_t *v9; // rcx
  bool v10; // zf
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-50h] BYREF
  int *v13; // [rsp+40h] [rbp-40h]
  __int64 v14; // [rsp+48h] [rbp-38h]
  const wchar_t *v15; // [rsp+50h] [rbp-30h]
  int v16; // [rsp+58h] [rbp-28h]
  int v17; // [rsp+5Ch] [rbp-24h]
  const wchar_t *v18; // [rsp+60h] [rbp-20h]
  int v19; // [rsp+68h] [rbp-18h]
  int v20; // [rsp+6Ch] [rbp-14h]
  int v21; // [rsp+A0h] [rbp+20h] BYREF

  v21 = a3;
  v13 = &v21;
  v5 = -1;
  v14 = 4;
  v6 = 10;
  if ( a4 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a4[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v16 = v8;
  v9 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v17 = 0;
  v15 = a4;
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
  v18 = v9;
  v20 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v9,
           (const EVENT_DESCRIPTOR *)SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_PROXY_ATTEMPT,
           0,
           4u,
           &v12);
}

```

## disassembly

```asm
0x18000d030  mov     [rsp-8+arg_10], r8d
0x18000d035  push    rbp
0x18000d036  mov     rbp, rsp
0x18000d039  sub     rsp, 80h
0x18000d040  mov     rax, cs:__security_cookie
0x18000d047  xor     rax, rsp
0x18000d04a  mov     [rbp+var_10], rax
0x18000d04e  lea     rax, [rbp+arg_10]
0x18000d052  mov     r11d, 4
0x18000d058  mov     [rbp+var_40], rax
0x18000d05c  xor     r8d, r8d
0x18000d05f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d063  mov     [rbp+var_38], r11
0x18000d067  lea     edx, [r11+6]
0x18000d06b  test    r9, r9
0x18000d06e  jz      short loc_18000D086
0x18000d070  mov     rcx, rax
0x18000d073  inc     rcx
0x18000d076  cmp     [r9+rcx*2], r8w
0x18000d07b  jnz     short loc_18000D073
0x18000d07d  lea     ecx, ds:2[rcx*2]
0x18000d084  jmp     short loc_18000D088
0x18000d086  mov     ecx, edx
0x18000d088  test    r9, r9
0x18000d08b  mov     [rbp+var_28], ecx
0x18000d08e  mov     rcx, [rbp+arg_20]
0x18000d092  lea     r10, aNull_0; "NULL"
0x18000d099  cmovz   r9, r10
0x18000d09d  mov     [rbp+var_24], r8d
0x18000d0a1  mov     [rbp+var_30], r9
0x18000d0a5  test    rcx, rcx
0x18000d0a8  jz      short loc_18000D0BE
0x18000d0aa  inc     rax
0x18000d0ad  cmp     [rcx+rax*2], r8w
0x18000d0b2  jnz     short loc_18000D0AA
0x18000d0b4  lea     edx, ds:2[rax*2]
0x18000d0bb  test    rcx, rcx
0x18000d0be  cmovz   rcx, r10
0x18000d0c2  mov     [rbp+var_18], edx
0x18000d0c5  lea     rax, [rbp+var_50]
0x18000d0c9  mov     [rbp+var_20], rcx
0x18000d0cd  lea     rdx, SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_PROXY_ATTEMPT
0x18000d0d4  mov     [rsp+80h+var_60], rax
0x18000d0d9  mov     r9d, r11d
0x18000d0dc  mov     [rbp+var_14], r8d
0x18000d0e0  call    McGenEventWrite_EventWriteTransfer
0x18000d0e5  mov     rcx, [rbp+var_10]
0x18000d0e9  xor     rcx, rsp; StackCookie
0x18000d0ec  call    __security_check_cookie
0x18000d0f1  add     rsp, 80h
0x18000d0f8  pop     rbp
0x18000d0f9  retn
```
