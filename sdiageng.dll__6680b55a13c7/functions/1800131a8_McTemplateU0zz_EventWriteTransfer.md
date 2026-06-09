# McTemplateU0zz_EventWriteTransfer

- ea: `0x1800131a8`
- end: `0x18001325b`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `179`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *, const wchar_t *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cf00`
- `0x18000fcf0`
- `0x18001b0b4`

## callees

- `0x1800130d0`
- `0x1800131a8`
- `0x1800298c0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  __int64 v4; // rax
  int v6; // edx
  __int64 v7; // rcx
  __int64 v8; // rcx
  bool v9; // zf
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v12; // [rsp+40h] [rbp-38h]
  int v13; // [rsp+48h] [rbp-30h]
  int v14; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v15; // [rsp+50h] [rbp-28h]
  int v16; // [rsp+58h] [rbp-20h]
  int v17; // [rsp+5Ch] [rbp-1Ch]

  v4 = -1;
  v6 = 10;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = (unsigned int)(2 * v7 + 2);
  }
  else
  {
    v8 = 10;
  }
  v13 = v8;
  v14 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v12 = a3;
  v9 = a4 == 0;
  if ( a4 )
  {
    do
      ++v4;
    while ( a4[v4] );
    v6 = 2 * v4 + 2;
    v9 = a4 == 0;
  }
  if ( v9 )
    a4 = L"NULL";
  v16 = v6;
  v15 = a4;
  v17 = 0;
  return McGenEventWrite_EventWriteTransfer(v8, a2, (__int64)a3, 3u, &v11);
}

```

## disassembly

```asm
0x1800131a8  push    rbx
0x1800131aa  sub     rsp, 70h
0x1800131ae  mov     rax, cs:__security_cookie
0x1800131b5  xor     rax, rsp
0x1800131b8  mov     [rsp+78h+var_18], rax
0x1800131bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800131c1  xor     r11d, r11d
0x1800131c4  mov     r10, rdx
0x1800131c7  mov     edx, 0Ah
0x1800131cc  test    r8, r8
0x1800131cf  jz      short loc_1800131E7
0x1800131d1  mov     rcx, rax
0x1800131d4  inc     rcx
0x1800131d7  cmp     [r8+rcx*2], r11w
0x1800131dc  jnz     short loc_1800131D4
0x1800131de  lea     ecx, ds:2[rcx*2]
0x1800131e5  jmp     short loc_1800131E9
0x1800131e7  mov     ecx, edx
0x1800131e9  test    r8, r8
0x1800131ec  mov     [rsp+78h+var_30], ecx
0x1800131f0  lea     rbx, aNull; "NULL"
0x1800131f7  mov     [rsp+78h+var_2C], r11d
0x1800131fc  cmovz   r8, rbx
0x180013200  mov     [rsp+78h+var_38], r8
0x180013205  test    r9, r9
0x180013208  jz      short loc_18001321E
0x18001320a  inc     rax
0x18001320d  cmp     [r9+rax*2], r11w
0x180013212  jnz     short loc_18001320A
0x180013214  lea     edx, ds:2[rax*2]
0x18001321b  test    r9, r9
0x18001321e  cmovz   r9, rbx
0x180013222  mov     [rsp+78h+var_20], edx
0x180013226  mov     [rsp+78h+var_28], r9
0x18001322b  lea     rax, [rsp+78h+var_48]
0x180013230  mov     r9d, 3
0x180013236  mov     [rsp+78h+var_1C], r11d
0x18001323b  mov     rdx, r10
0x18001323e  mov     [rsp+78h+var_58], rax
0x180013243  call    McGenEventWrite_EventWriteTransfer
0x180013248  mov     rcx, [rsp+78h+var_18]
0x18001324d  xor     rcx, rsp; StackCookie
0x180013250  call    __security_check_cookie
0x180013255  add     rsp, 70h
0x180013259  pop     rbx
0x18001325a  retn
```
