# McTemplateU0qzd_EventWriteTransfer

- ea: `0x1800124a8`
- end: `0x18001254c`
- name: `McTemplateU0qzd_EventWriteTransfer`
- size: `164`
- prototype: `ULONG __fastcall(__int64, __int64, int, const wchar_t *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011d2c`

## callees

- `0x18000247c`
- `0x1800124a8`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0qzd_EventWriteTransfer(__int64 a1, __int64 a2, int a3, const wchar_t *a4, char a5)
{
  __int64 v5; // rax
  int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-50h] BYREF
  int *v9; // [rsp+40h] [rbp-40h]
  __int64 v10; // [rsp+48h] [rbp-38h]
  const wchar_t *v11; // [rsp+50h] [rbp-30h]
  int v12; // [rsp+58h] [rbp-28h]
  int v13; // [rsp+5Ch] [rbp-24h]
  char *v14; // [rsp+60h] [rbp-20h]
  __int64 v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+A0h] [rbp+20h] BYREF

  v16 = a3;
  v9 = &v16;
  v10 = 4;
  if ( a4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a4[v5] );
    v6 = 2 * v5 + 2;
  }
  else
  {
    v6 = 10;
  }
  v12 = v6;
  v13 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v15 = 4;
  v11 = a4;
  v14 = &a5;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)L"NULL",
           (const EVENT_DESCRIPTOR *)SDIAGPRV_EVENT_LOCAL_CONTENT_DIAGNOSTIC_PROVIDER_INVALID_STRING_RESOURCE,
           4,
           4u,
           &v8);
}

```

## disassembly

```asm
0x1800124a8  mov     [rsp-8+arg_10], r8d
0x1800124ad  push    rbp
0x1800124ae  mov     rbp, rsp
0x1800124b1  sub     rsp, 80h
0x1800124b8  mov     rax, cs:__security_cookie
0x1800124bf  xor     rax, rsp
0x1800124c2  mov     [rbp+var_10], rax
0x1800124c6  xor     edx, edx
0x1800124c8  lea     rax, [rbp+arg_10]
0x1800124cc  mov     [rbp+var_40], rax
0x1800124d0  mov     r8d, 4
0x1800124d6  mov     [rbp+var_38], r8
0x1800124da  test    r9, r9
0x1800124dd  jz      short loc_1800124F6
0x1800124df  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800124e3  inc     rax
0x1800124e6  cmp     [r9+rax*2], dx
0x1800124eb  jnz     short loc_1800124E3
0x1800124ed  lea     eax, ds:2[rax*2]
0x1800124f4  jmp     short loc_1800124FB
0x1800124f6  mov     eax, 0Ah
0x1800124fb  test    r9, r9
0x1800124fe  mov     [rbp+var_28], eax
0x180012501  lea     rcx, aNull_0; "NULL"
0x180012508  mov     [rbp+var_24], edx
0x18001250b  cmovz   r9, rcx
0x18001250f  mov     [rbp+var_18], r8
0x180012513  lea     rax, [rbp+arg_20]
0x180012517  mov     [rbp+var_30], r9
0x18001251b  mov     [rbp+var_20], rax
0x18001251f  lea     rdx, SDIAGPRV_EVENT_LOCAL_CONTENT_DIAGNOSTIC_PROVIDER_INVALID_STRING_RESOURCE
0x180012526  lea     rax, [rbp+var_50]
0x18001252a  mov     r9d, r8d
0x18001252d  mov     [rsp+80h+var_60], rax
0x180012532  call    McGenEventWrite_EventWriteTransfer
0x180012537  mov     rcx, [rbp+var_10]
0x18001253b  xor     rcx, rsp; StackCookie
0x18001253e  call    __security_check_cookie
0x180012543  add     rsp, 80h
0x18001254a  pop     rbp
0x18001254b  retn
```
