# McTemplateU0zzq_EventWriteTransfer

- ea: `0x18000b324`
- end: `0x18000b3ef`
- name: `McTemplateU0zzq_EventWriteTransfer`
- size: `203`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *, const wchar_t *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009e60`

## callees

- `0x18000247c`
- `0x18000b324`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzq_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        char a5)
{
  __int64 v5; // rax
  int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // rcx
  bool v10; // zf
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-58h] BYREF
  const wchar_t *v13; // [rsp+40h] [rbp-48h]
  int v14; // [rsp+48h] [rbp-40h]
  int v15; // [rsp+4Ch] [rbp-3Ch]
  const wchar_t *v16; // [rsp+50h] [rbp-38h]
  int v17; // [rsp+58h] [rbp-30h]
  int v18; // [rsp+5Ch] [rbp-2Ch]
  char *v19; // [rsp+60h] [rbp-28h]
  __int64 v20; // [rsp+68h] [rbp-20h]

  v5 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = (unsigned int)(2 * v8 + 2);
  }
  else
  {
    v9 = 10;
  }
  v14 = v9;
  v15 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v13 = a3;
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v5;
    while ( a4[v5] );
    v7 = 2 * v5 + 2;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = L"NULL";
  v17 = v7;
  v16 = a4;
  v19 = &a5;
  v20 = 4;
  v18 = 0;
  return McGenEventWrite_EventWriteTransfer(v9, a2, (__int64)a3, 4u, &v12);
}

```

## disassembly

```asm
0x18000b324  push    rbx
0x18000b326  sub     rsp, 80h
0x18000b32d  mov     rax, cs:__security_cookie
0x18000b334  xor     rax, rsp
0x18000b337  mov     [rsp+88h+var_18], rax
0x18000b33c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b340  xor     r11d, r11d
0x18000b343  mov     r10, rdx
0x18000b346  mov     edx, 0Ah
0x18000b34b  test    r8, r8
0x18000b34e  jz      short loc_18000B366
0x18000b350  mov     rcx, rax
0x18000b353  inc     rcx
0x18000b356  cmp     [r8+rcx*2], r11w
0x18000b35b  jnz     short loc_18000B353
0x18000b35d  lea     ecx, ds:2[rcx*2]
0x18000b364  jmp     short loc_18000B368
0x18000b366  mov     ecx, edx
0x18000b368  test    r8, r8
0x18000b36b  mov     [rsp+88h+var_40], ecx
0x18000b36f  lea     rbx, aNull_0; "NULL"
0x18000b376  mov     [rsp+88h+var_3C], r11d
0x18000b37b  cmovz   r8, rbx
0x18000b37f  mov     [rsp+88h+var_48], r8
0x18000b384  test    r9, r9
0x18000b387  jz      short loc_18000B39D
0x18000b389  inc     rax
0x18000b38c  cmp     [r9+rax*2], r11w
0x18000b391  jnz     short loc_18000B389
0x18000b393  lea     edx, ds:2[rax*2]
0x18000b39a  test    r9, r9
0x18000b39d  cmovz   r9, rbx
0x18000b3a1  mov     [rsp+88h+var_30], edx
0x18000b3a5  lea     rax, [rsp+88h+arg_20]
0x18000b3ad  mov     [rsp+88h+var_38], r9
0x18000b3b2  mov     [rsp+88h+var_28], rax
0x18000b3b7  mov     r9d, 4
0x18000b3bd  lea     rax, [rsp+88h+var_58]
0x18000b3c2  mov     [rsp+88h+var_20], r9
0x18000b3c7  mov     rdx, r10
0x18000b3ca  mov     [rsp+88h+var_68], rax
0x18000b3cf  mov     [rsp+88h+var_2C], r11d
0x18000b3d4  call    McGenEventWrite_EventWriteTransfer
0x18000b3d9  mov     rcx, [rsp+88h+var_18]
0x18000b3de  xor     rcx, rsp; StackCookie
0x18000b3e1  call    __security_check_cookie
0x18000b3e6  add     rsp, 80h
0x18000b3ed  pop     rbx
0x18000b3ee  retn
```
