# McTemplateU0zzz_EventWriteTransfer

- ea: `0x18000c554`
- end: `0x18000c645`
- name: `McTemplateU0zzz_EventWriteTransfer`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d020`

## callees

- `0x1800061d0`
- `0x180006620`
- `0x18000c554`

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
           (const EVENT_DESCRIPTOR *)SamChangePasswordUser2Entry,
           (__int64)a3,
           4u,
           &v14);
}

```

## disassembly

```asm
0x18000c554  sub     rsp, 88h
0x18000c55b  mov     rax, cs:__security_cookie
0x18000c562  xor     rax, rsp
0x18000c565  mov     [rsp+88h+var_18], rax
0x18000c56a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c56e  xor     r10d, r10d
0x18000c571  mov     edx, 0Ah
0x18000c576  test    r8, r8
0x18000c579  jz      short loc_18000C591
0x18000c57b  mov     rcx, rax
0x18000c57e  inc     rcx
0x18000c581  cmp     [r8+rcx*2], r10w
0x18000c586  jnz     short loc_18000C57E
0x18000c588  lea     ecx, ds:2[rcx*2]
0x18000c58f  jmp     short loc_18000C593
0x18000c591  mov     ecx, edx
0x18000c593  test    r8, r8
0x18000c596  mov     [rsp+88h+var_40], ecx
0x18000c59a  lea     r11, aNull_0; "NULL"
0x18000c5a1  mov     [rsp+88h+var_3C], r10d
0x18000c5a6  cmovz   r8, r11
0x18000c5aa  mov     [rsp+88h+var_48], r8
0x18000c5af  test    r9, r9
0x18000c5b2  jz      short loc_18000C5CA
0x18000c5b4  mov     rcx, rax
0x18000c5b7  inc     rcx
0x18000c5ba  cmp     [r9+rcx*2], r10w
0x18000c5bf  jnz     short loc_18000C5B7
0x18000c5c1  lea     ecx, ds:2[rcx*2]
0x18000c5c8  jmp     short loc_18000C5CC
0x18000c5ca  mov     ecx, edx
0x18000c5cc  test    r9, r9
0x18000c5cf  mov     [rsp+88h+var_30], ecx
0x18000c5d3  mov     rcx, [rsp+88h+arg_20]
0x18000c5db  cmovz   r9, r11
0x18000c5df  mov     [rsp+88h+var_2C], r10d
0x18000c5e4  mov     [rsp+88h+var_38], r9
0x18000c5e9  test    rcx, rcx
0x18000c5ec  jz      short loc_18000C602
0x18000c5ee  inc     rax
0x18000c5f1  cmp     [rcx+rax*2], r10w
0x18000c5f6  jnz     short loc_18000C5EE
0x18000c5f8  lea     edx, ds:2[rax*2]
0x18000c5ff  test    rcx, rcx
0x18000c602  cmovz   rcx, r11
0x18000c606  mov     [rsp+88h+var_20], edx
0x18000c60a  lea     rax, [rsp+88h+var_58]
0x18000c60f  mov     [rsp+88h+var_28], rcx
0x18000c614  lea     rdx, SamChangePasswordUser2Entry
0x18000c61b  mov     [rsp+88h+var_68], rax
0x18000c620  mov     r9d, 4
0x18000c626  mov     [rsp+88h+var_1C], r10d
0x18000c62b  call    McGenEventWrite_EventWriteTransfer
0x18000c630  mov     rcx, [rsp+88h+var_18]
0x18000c635  xor     rcx, rsp; StackCookie
0x18000c638  call    __security_check_cookie
0x18000c63d  add     rsp, 88h
0x18000c644  retn
```
