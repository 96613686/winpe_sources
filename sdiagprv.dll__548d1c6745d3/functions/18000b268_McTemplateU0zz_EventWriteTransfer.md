# McTemplateU0zz_EventWriteTransfer

- ea: `0x18000b268`
- end: `0x18000b31b`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `179`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009e60`

## callees

- `0x18000247c`
- `0x18000b268`
- `0x1800180f0`

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
0x18000b268  push    rbx
0x18000b26a  sub     rsp, 70h
0x18000b26e  mov     rax, cs:__security_cookie
0x18000b275  xor     rax, rsp
0x18000b278  mov     [rsp+78h+var_18], rax
0x18000b27d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b281  xor     r11d, r11d
0x18000b284  mov     r10, rdx
0x18000b287  mov     edx, 0Ah
0x18000b28c  test    r8, r8
0x18000b28f  jz      short loc_18000B2A7
0x18000b291  mov     rcx, rax
0x18000b294  inc     rcx
0x18000b297  cmp     [r8+rcx*2], r11w
0x18000b29c  jnz     short loc_18000B294
0x18000b29e  lea     ecx, ds:2[rcx*2]
0x18000b2a5  jmp     short loc_18000B2A9
0x18000b2a7  mov     ecx, edx
0x18000b2a9  test    r8, r8
0x18000b2ac  mov     [rsp+78h+var_30], ecx
0x18000b2b0  lea     rbx, aNull_0; "NULL"
0x18000b2b7  mov     [rsp+78h+var_2C], r11d
0x18000b2bc  cmovz   r8, rbx
0x18000b2c0  mov     [rsp+78h+var_38], r8
0x18000b2c5  test    r9, r9
0x18000b2c8  jz      short loc_18000B2DE
0x18000b2ca  inc     rax
0x18000b2cd  cmp     [r9+rax*2], r11w
0x18000b2d2  jnz     short loc_18000B2CA
0x18000b2d4  lea     edx, ds:2[rax*2]
0x18000b2db  test    r9, r9
0x18000b2de  cmovz   r9, rbx
0x18000b2e2  mov     [rsp+78h+var_20], edx
0x18000b2e6  mov     [rsp+78h+var_28], r9
0x18000b2eb  lea     rax, [rsp+78h+var_48]
0x18000b2f0  mov     r9d, 3
0x18000b2f6  mov     [rsp+78h+var_1C], r11d
0x18000b2fb  mov     rdx, r10
0x18000b2fe  mov     [rsp+78h+var_58], rax
0x18000b303  call    McGenEventWrite_EventWriteTransfer
0x18000b308  mov     rcx, [rsp+78h+var_18]
0x18000b30d  xor     rcx, rsp; StackCookie
0x18000b310  call    __security_check_cookie
0x18000b315  add     rsp, 70h
0x18000b319  pop     rbx
0x18000b31a  retn
```
