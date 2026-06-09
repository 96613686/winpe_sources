# McTemplateU0zzs_EventWriteTransfer

- ea: `0x18000b3f8`
- end: `0x18000b4ef`
- name: `McTemplateU0zzs_EventWriteTransfer`
- size: `247`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *, const wchar_t *, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009e60`

## callees

- `0x18000247c`
- `0x18000b3f8`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzs_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const char *a5)
{
  __int64 v5; // rax
  int v7; // edx
  __int64 v8; // rcx
  int v9; // ecx
  bool v10; // zf
  __int64 v11; // rcx
  const char *v12; // rcx
  int v13; // eax
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-58h] BYREF
  const wchar_t *v16; // [rsp+40h] [rbp-48h]
  int v17; // [rsp+48h] [rbp-40h]
  int v18; // [rsp+4Ch] [rbp-3Ch]
  const wchar_t *v19; // [rsp+50h] [rbp-38h]
  int v20; // [rsp+58h] [rbp-30h]
  int v21; // [rsp+5Ch] [rbp-2Ch]
  const char *v22; // [rsp+60h] [rbp-28h]
  int v23; // [rsp+68h] [rbp-20h]
  int v24; // [rsp+6Ch] [rbp-1Ch]

  v5 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v17 = v9;
  v18 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v16 = a3;
  v10 = a4 == 0;
  if ( a4 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a4[v11] );
    v7 = 2 * v11 + 2;
    v10 = a4 == 0;
  }
  v12 = a5;
  if ( v10 )
    a4 = L"NULL";
  v19 = a4;
  v20 = v7;
  v21 = 0;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v13 = v5 + 1;
  }
  else
  {
    v13 = 5;
  }
  v23 = v13;
  v24 = 0;
  if ( !a5 )
    v12 = "NULL";
  v22 = v12;
  return McGenEventWrite_EventWriteTransfer((__int64)v12, a2, (__int64)a3, 4u, &v15);
}

```

## disassembly

```asm
0x18000b3f8  push    rbx
0x18000b3fa  sub     rsp, 80h
0x18000b401  mov     rax, cs:__security_cookie
0x18000b408  xor     rax, rsp
0x18000b40b  mov     [rsp+88h+var_18], rax
0x18000b410  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b414  xor     r11d, r11d
0x18000b417  mov     r10, rdx
0x18000b41a  mov     edx, 0Ah
0x18000b41f  test    r8, r8
0x18000b422  jz      short loc_18000B43A
0x18000b424  mov     rcx, rax
0x18000b427  inc     rcx
0x18000b42a  cmp     [r8+rcx*2], r11w
0x18000b42f  jnz     short loc_18000B427
0x18000b431  lea     ecx, ds:2[rcx*2]
0x18000b438  jmp     short loc_18000B43C
0x18000b43a  mov     ecx, edx
0x18000b43c  test    r8, r8
0x18000b43f  mov     [rsp+88h+var_40], ecx
0x18000b443  lea     rbx, aNull_0; "NULL"
0x18000b44a  mov     [rsp+88h+var_3C], r11d
0x18000b44f  cmovz   r8, rbx
0x18000b453  mov     [rsp+88h+var_48], r8
0x18000b458  test    r9, r9
0x18000b45b  jz      short loc_18000B474
0x18000b45d  mov     rcx, rax
0x18000b460  inc     rcx
0x18000b463  cmp     [r9+rcx*2], r11w
0x18000b468  jnz     short loc_18000B460
0x18000b46a  lea     edx, ds:2[rcx*2]
0x18000b471  test    r9, r9
0x18000b474  mov     rcx, [rsp+88h+arg_20]
0x18000b47c  cmovz   r9, rbx
0x18000b480  mov     [rsp+88h+var_38], r9
0x18000b485  mov     [rsp+88h+var_30], edx
0x18000b489  mov     [rsp+88h+var_2C], r11d
0x18000b48e  test    rcx, rcx
0x18000b491  jz      short loc_18000B4A0
0x18000b493  inc     rax
0x18000b496  cmp     [rcx+rax], r11b
0x18000b49a  jnz     short loc_18000B493
0x18000b49c  inc     eax
0x18000b49e  jmp     short loc_18000B4A5
0x18000b4a0  mov     eax, 5
0x18000b4a5  test    rcx, rcx
0x18000b4a8  mov     [rsp+88h+var_20], eax
0x18000b4ac  lea     rdx, aNull; "NULL"
0x18000b4b3  mov     [rsp+88h+var_1C], r11d
0x18000b4b8  cmovz   rcx, rdx
0x18000b4bc  lea     rax, [rsp+88h+var_58]
0x18000b4c1  mov     rdx, r10
0x18000b4c4  mov     [rsp+88h+var_28], rcx
0x18000b4c9  mov     r9d, 4
0x18000b4cf  mov     [rsp+88h+var_68], rax
0x18000b4d4  call    McGenEventWrite_EventWriteTransfer
0x18000b4d9  mov     rcx, [rsp+88h+var_18]
0x18000b4de  xor     rcx, rsp; StackCookie
0x18000b4e1  call    __security_check_cookie
0x18000b4e6  add     rsp, 80h
0x18000b4ed  pop     rbx
0x18000b4ee  retn
```
