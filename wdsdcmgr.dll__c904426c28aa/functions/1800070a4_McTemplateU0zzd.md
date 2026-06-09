# McTemplateU0zzd

- ea: `0x1800070a4`
- end: `0x18000717f`
- name: `McTemplateU0zzd`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800042f4`

## callees

- `0x1800070a4`
- `0x180007188`
- `0x180015660`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzd(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, const wchar_t *a4, char a5)
{
  __int64 v5; // rcx
  int v7; // r10d
  __int64 v8; // rax
  int v9; // edx
  const wchar_t *v10; // r11
  const wchar_t *v11; // rax
  bool v12; // zf
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-58h] BYREF
  const wchar_t *v15; // [rsp+40h] [rbp-48h]
  int v16; // [rsp+48h] [rbp-40h]
  int v17; // [rsp+4Ch] [rbp-3Ch]
  const wchar_t *v18; // [rsp+50h] [rbp-38h]
  int v19; // [rsp+58h] [rbp-30h]
  int v20; // [rsp+5Ch] [rbp-2Ch]
  char *v21; // [rsp+60h] [rbp-28h]
  __int64 v22; // [rsp+68h] [rbp-20h]

  v5 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(a3 + 2 * v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v16 = v9;
  v10 = L"NULL";
  v17 = 0;
  v11 = L"NULL";
  if ( a3 )
    v11 = (const wchar_t *)a3;
  v15 = v11;
  v12 = a4 == 0;
  if ( a4 )
  {
    do
      ++v5;
    while ( a4[v5] );
    v7 = 2 * v5 + 2;
    v12 = a4 == 0;
  }
  if ( !v12 )
    v10 = a4;
  v19 = v7;
  v18 = v10;
  v21 = &a5;
  v20 = 0;
  v22 = 4;
  return McGenEventWrite(v5, a2, a3, 4u, &v14);
}

```

## disassembly

```asm
0x1800070a4  mov     [rsp+arg_0], rbx
0x1800070a9  push    rdi
0x1800070aa  sub     rsp, 80h
0x1800070b1  mov     rax, cs:__security_cookie
0x1800070b8  xor     rax, rsp
0x1800070bb  mov     [rsp+88h+var_18], rax
0x1800070c0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800070c4  xor     edi, edi
0x1800070c6  mov     rbx, rdx
0x1800070c9  mov     r10d, 0Ah
0x1800070cf  test    r8, r8
0x1800070d2  jz      short loc_1800070EA
0x1800070d4  mov     rax, rcx
0x1800070d7  inc     rax
0x1800070da  cmp     [r8+rax*2], di
0x1800070df  jnz     short loc_1800070D7
0x1800070e1  lea     edx, ds:2[rax*2]
0x1800070e8  jmp     short loc_1800070ED
0x1800070ea  mov     edx, r10d
0x1800070ed  test    r8, r8
0x1800070f0  mov     [rsp+88h+var_40], edx
0x1800070f4  lea     r11, aNull; "NULL"
0x1800070fb  mov     [rsp+88h+var_3C], edi
0x1800070ff  mov     rax, r11
0x180007102  cmovnz  rax, r8
0x180007106  mov     [rsp+88h+var_48], rax
0x18000710b  test    r9, r9
0x18000710e  jz      short loc_180007125
0x180007110  inc     rcx
0x180007113  cmp     [r9+rcx*2], di
0x180007118  jnz     short loc_180007110
0x18000711a  lea     r10d, ds:2[rcx*2]
0x180007122  test    r9, r9
0x180007125  cmovnz  r11, r9
0x180007129  mov     [rsp+88h+var_30], r10d
0x18000712e  lea     rax, [rsp+88h+arg_20]
0x180007136  mov     [rsp+88h+var_38], r11
0x18000713b  mov     [rsp+88h+var_28], rax
0x180007140  mov     r9d, 4
0x180007146  lea     rax, [rsp+88h+var_58]
0x18000714b  mov     [rsp+88h+var_2C], edi
0x18000714f  mov     rdx, rbx
0x180007152  mov     [rsp+88h+var_68], rax
0x180007157  mov     [rsp+88h+var_20], r9
0x18000715c  call    McGenEventWrite
0x180007161  mov     rcx, [rsp+88h+var_18]
0x180007166  xor     rcx, rsp; StackCookie
0x180007169  call    __security_check_cookie
0x18000716e  mov     rbx, [rsp+88h+arg_0]
0x180007176  add     rsp, 80h
0x18000717d  pop     rdi
0x18000717e  retn
```
