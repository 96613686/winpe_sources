# McTemplateU0qdzz_EventWriteTransfer

- ea: `0x18000d100`
- end: `0x18000d1e9`
- name: `McTemplateU0qdzz_EventWriteTransfer`
- size: `233`
- prototype: `ULONG __fastcall(__int64, __int64, int, int, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c618`

## callees

- `0x18000247c`
- `0x18000d100`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0qdzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        const wchar_t *a5,
        const wchar_t *a6)
{
  const wchar_t *v6; // rdx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rcx
  int v10; // ecx
  const wchar_t *v11; // rcx
  bool v12; // zf
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-19h] BYREF
  int *v15; // [rsp+40h] [rbp-9h]
  __int64 v16; // [rsp+48h] [rbp-1h]
  int *v17; // [rsp+50h] [rbp+7h]
  __int64 v18; // [rsp+58h] [rbp+Fh]
  const wchar_t *v19; // [rsp+60h] [rbp+17h]
  int v20; // [rsp+68h] [rbp+1Fh]
  int v21; // [rsp+6Ch] [rbp+23h]
  const wchar_t *v22; // [rsp+70h] [rbp+27h]
  int v23; // [rsp+78h] [rbp+2Fh]
  int v24; // [rsp+7Ch] [rbp+33h]
  int v25; // [rsp+B0h] [rbp+67h] BYREF
  int v26; // [rsp+B8h] [rbp+6Fh] BYREF

  v26 = a4;
  v25 = a3;
  v6 = a5;
  v15 = &v25;
  v16 = 4;
  v17 = &v26;
  v7 = -1;
  v18 = 4;
  v8 = 10;
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
  v20 = v10;
  v11 = a6;
  if ( !a5 )
    v6 = L"NULL";
  v21 = 0;
  v19 = v6;
  v12 = a6 == 0;
  if ( a6 )
  {
    do
      ++v7;
    while ( a6[v7] );
    v8 = (unsigned int)(2 * v7 + 2);
    v12 = a6 == 0;
  }
  if ( v12 )
    v11 = L"NULL";
  v24 = 0;
  v22 = v11;
  v23 = v8;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v11,
           (const EVENT_DESCRIPTOR *)SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_PROXY_FAILURE,
           v8,
           5u,
           &v14);
}

```

## disassembly

```asm
0x18000d100  mov     [rsp-8+arg_18], r9d
0x18000d105  mov     [rsp-8+arg_10], r8d
0x18000d10a  push    rbp
0x18000d10b  lea     rbp, [rsp-47h]
0x18000d110  sub     rsp, 90h
0x18000d117  mov     rax, cs:__security_cookie
0x18000d11e  xor     rax, rsp
0x18000d121  mov     [rbp+47h+var_10], rax
0x18000d125  mov     rdx, [rbp+47h+arg_20]
0x18000d129  lea     rax, [rbp+47h+arg_10]
0x18000d12d  mov     [rbp+47h+var_50], rax
0x18000d131  xor     r9d, r9d
0x18000d134  lea     rax, [rbp+47h+arg_18]
0x18000d138  mov     [rbp+47h+var_48], 4
0x18000d140  mov     [rbp+47h+var_40], rax
0x18000d144  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d148  mov     [rbp+47h+var_38], 4
0x18000d150  lea     r8d, [r9+0Ah]
0x18000d154  test    rdx, rdx
0x18000d157  jz      short loc_18000D16F
0x18000d159  mov     rcx, rax
0x18000d15c  inc     rcx
0x18000d15f  cmp     [rdx+rcx*2], r9w
0x18000d164  jnz     short loc_18000D15C
0x18000d166  lea     ecx, ds:2[rcx*2]
0x18000d16d  jmp     short loc_18000D172
0x18000d16f  mov     ecx, r8d
0x18000d172  test    rdx, rdx
0x18000d175  mov     [rbp+47h+var_28], ecx
0x18000d178  mov     rcx, [rbp+47h+arg_28]
0x18000d17c  lea     r10, aNull_0; "NULL"
0x18000d183  cmovz   rdx, r10
0x18000d187  mov     [rbp+47h+var_24], r9d
0x18000d18b  mov     [rbp+47h+var_30], rdx
0x18000d18f  test    rcx, rcx
0x18000d192  jz      short loc_18000D1A9
0x18000d194  inc     rax
0x18000d197  cmp     [rcx+rax*2], r9w
0x18000d19c  jnz     short loc_18000D194
0x18000d19e  lea     r8d, ds:2[rax*2]
0x18000d1a6  test    rcx, rcx
0x18000d1a9  cmovz   rcx, r10
0x18000d1ad  mov     [rbp+47h+var_14], r9d
0x18000d1b1  lea     rax, [rbp+47h+var_60]
0x18000d1b5  mov     [rbp+47h+var_20], rcx
0x18000d1b9  mov     r9d, 5
0x18000d1bf  mov     [rsp+90h+var_70], rax
0x18000d1c4  lea     rdx, SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_PROXY_FAILURE
0x18000d1cb  mov     [rbp+47h+var_18], r8d
0x18000d1cf  call    McGenEventWrite_EventWriteTransfer
0x18000d1d4  mov     rcx, [rbp+47h+var_10]
0x18000d1d8  xor     rcx, rsp; StackCookie
0x18000d1db  call    __security_check_cookie
0x18000d1e0  add     rsp, 90h
0x18000d1e7  pop     rbp
0x18000d1e8  retn
```
