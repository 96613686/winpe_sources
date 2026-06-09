# McTemplateU0zzz_EventWriteTransfer

- ea: `0x18000b5fc`
- end: `0x18000b6ed`
- name: `McTemplateU0zzz_EventWriteTransfer`
- size: `241`
- prototype: `ULONG __fastcall(__int64, __int64, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009e60`

## callees

- `0x18000247c`
- `0x18000b5fc`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  __int64 v5; // rax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // ecx
  __int64 v9; // rcx
  int v10; // ecx
  const wchar_t *v11; // rcx
  bool v12; // zf
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-58h] BYREF
  const wchar_t *v15; // [rsp+40h] [rbp-48h]
  int v16; // [rsp+48h] [rbp-40h]
  int v17; // [rsp+4Ch] [rbp-3Ch]
  const wchar_t *v18; // [rsp+50h] [rbp-38h]
  int v19; // [rsp+58h] [rbp-30h]
  int v20; // [rsp+5Ch] [rbp-2Ch]
  const wchar_t *v21; // [rsp+60h] [rbp-28h]
  int v22; // [rsp+68h] [rbp-20h]
  int v23; // [rsp+6Ch] [rbp-1Ch]

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
  v16 = v8;
  v17 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v15 = a3;
  if ( a4 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a4[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v19 = v10;
  v11 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v20 = 0;
  v18 = a4;
  v12 = a5 == 0;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v6 = 2 * v5 + 2;
    v12 = a5 == 0;
  }
  if ( v12 )
    v11 = L"NULL";
  v22 = v6;
  v21 = v11;
  v23 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v11,
           (const EVENT_DESCRIPTOR *)SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_REMOTE_RESPONSE_INVALID,
           (__int64)a3,
           4u,
           &v14);
}

```

## disassembly

```asm
0x18000b5fc  sub     rsp, 88h
0x18000b603  mov     rax, cs:__security_cookie
0x18000b60a  xor     rax, rsp
0x18000b60d  mov     [rsp+88h+var_18], rax
0x18000b612  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b616  xor     r10d, r10d
0x18000b619  mov     edx, 0Ah
0x18000b61e  test    r8, r8
0x18000b621  jz      short loc_18000B639
0x18000b623  mov     rcx, rax
0x18000b626  inc     rcx
0x18000b629  cmp     [r8+rcx*2], r10w
0x18000b62e  jnz     short loc_18000B626
0x18000b630  lea     ecx, ds:2[rcx*2]
0x18000b637  jmp     short loc_18000B63B
0x18000b639  mov     ecx, edx
0x18000b63b  test    r8, r8
0x18000b63e  mov     [rsp+88h+var_40], ecx
0x18000b642  lea     r11, aNull_0; "NULL"
0x18000b649  mov     [rsp+88h+var_3C], r10d
0x18000b64e  cmovz   r8, r11
0x18000b652  mov     [rsp+88h+var_48], r8
0x18000b657  test    r9, r9
0x18000b65a  jz      short loc_18000B672
0x18000b65c  mov     rcx, rax
0x18000b65f  inc     rcx
0x18000b662  cmp     [r9+rcx*2], r10w
0x18000b667  jnz     short loc_18000B65F
0x18000b669  lea     ecx, ds:2[rcx*2]
0x18000b670  jmp     short loc_18000B674
0x18000b672  mov     ecx, edx
0x18000b674  test    r9, r9
0x18000b677  mov     [rsp+88h+var_30], ecx
0x18000b67b  mov     rcx, [rsp+88h+arg_20]
0x18000b683  cmovz   r9, r11
0x18000b687  mov     [rsp+88h+var_2C], r10d
0x18000b68c  mov     [rsp+88h+var_38], r9
0x18000b691  test    rcx, rcx
0x18000b694  jz      short loc_18000B6AA
0x18000b696  inc     rax
0x18000b699  cmp     [rcx+rax*2], r10w
0x18000b69e  jnz     short loc_18000B696
0x18000b6a0  lea     edx, ds:2[rax*2]
0x18000b6a7  test    rcx, rcx
0x18000b6aa  cmovz   rcx, r11
0x18000b6ae  mov     [rsp+88h+var_20], edx
0x18000b6b2  lea     rax, [rsp+88h+var_58]
0x18000b6b7  mov     [rsp+88h+var_28], rcx
0x18000b6bc  lea     rdx, SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_REMOTE_RESPONSE_INVALID
0x18000b6c3  mov     [rsp+88h+var_68], rax
0x18000b6c8  mov     r9d, 4
0x18000b6ce  mov     [rsp+88h+var_1C], r10d
0x18000b6d3  call    McGenEventWrite_EventWriteTransfer
0x18000b6d8  mov     rcx, [rsp+88h+var_18]
0x18000b6dd  xor     rcx, rsp; StackCookie
0x18000b6e0  call    __security_check_cookie
0x18000b6e5  add     rsp, 88h
0x18000b6ec  retn
```
