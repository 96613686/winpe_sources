# McTemplateU0zqz

- ea: `0x180014404`
- end: `0x1800144dd`
- name: `McTemplateU0zqz`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001465c`

## callees

- `0x180007188`
- `0x180014404`
- `0x180015660`

## pseudocode

```c
ULONG __fastcall McTemplateU0zqz(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, int a4, const wchar_t *a5)
{
  __int64 v5; // rcx
  int v7; // r9d
  __int64 v8; // rax
  int v9; // edx
  const wchar_t *v10; // r10
  const wchar_t *v11; // rax
  bool v12; // zf
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-50h] BYREF
  const wchar_t *v15; // [rsp+40h] [rbp-40h]
  int v16; // [rsp+48h] [rbp-38h]
  int v17; // [rsp+4Ch] [rbp-34h]
  int *v18; // [rsp+50h] [rbp-30h]
  __int64 v19; // [rsp+58h] [rbp-28h]
  const wchar_t *v20; // [rsp+60h] [rbp-20h]
  int v21; // [rsp+68h] [rbp-18h]
  int v22; // [rsp+6Ch] [rbp-14h]
  int v23; // [rsp+A8h] [rbp+28h] BYREF

  v23 = a4;
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
  v19 = 4;
  v15 = v11;
  v18 = &v23;
  v12 = a5 == 0;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v7 = 2 * v5 + 2;
    v12 = a5 == 0;
  }
  if ( !v12 )
    v10 = a5;
  v21 = v7;
  v20 = v10;
  v22 = 0;
  return McGenEventWrite(v5, a2, a3, 4u, &v14);
}

```

## disassembly

```asm
0x180014404  mov     [rsp-8+arg_0], rbx
0x180014409  mov     [rsp-8+arg_18], r9d
0x18001440e  push    rbp
0x18001440f  mov     rbp, rsp
0x180014412  sub     rsp, 80h
0x180014419  mov     rax, cs:__security_cookie
0x180014420  xor     rax, rsp
0x180014423  mov     [rbp+var_10], rax
0x180014427  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001442b  xor     ebx, ebx
0x18001442d  mov     r11, rdx
0x180014430  mov     r9d, 0Ah
0x180014436  test    r8, r8
0x180014439  jz      short loc_180014451
0x18001443b  mov     rax, rcx
0x18001443e  inc     rax
0x180014441  cmp     [r8+rax*2], bx
0x180014446  jnz     short loc_18001443E
0x180014448  lea     edx, ds:2[rax*2]
0x18001444f  jmp     short loc_180014454
0x180014451  mov     edx, r9d
0x180014454  test    r8, r8
0x180014457  mov     [rbp+var_38], edx
0x18001445a  lea     r10, aNull; "NULL"
0x180014461  mov     [rbp+var_34], ebx
0x180014464  mov     rax, r10
0x180014467  mov     edx, 4
0x18001446c  cmovnz  rax, r8
0x180014470  mov     [rbp+var_28], rdx
0x180014474  mov     [rbp+var_40], rax
0x180014478  lea     rax, [rbp+arg_18]
0x18001447c  mov     [rbp+var_30], rax
0x180014480  mov     rax, [rbp+arg_20]
0x180014484  test    rax, rax
0x180014487  jz      short loc_18001449D
0x180014489  inc     rcx
0x18001448c  cmp     [rax+rcx*2], bx
0x180014490  jnz     short loc_180014489
0x180014492  lea     r9d, ds:2[rcx*2]
0x18001449a  test    rax, rax
0x18001449d  cmovnz  r10, rax
0x1800144a1  mov     [rbp+var_18], r9d
0x1800144a5  lea     rax, [rbp+var_50]
0x1800144a9  mov     [rbp+var_20], r10
0x1800144ad  mov     r9d, edx
0x1800144b0  mov     [rsp+80h+var_60], rax
0x1800144b5  mov     rdx, r11
0x1800144b8  mov     [rbp+var_14], ebx
0x1800144bb  call    McGenEventWrite
0x1800144c0  mov     rcx, [rbp+var_10]
0x1800144c4  xor     rcx, rsp; StackCookie
0x1800144c7  call    __security_check_cookie
0x1800144cc  mov     rbx, [rsp+80h+arg_0]
0x1800144d4  add     rsp, 80h
0x1800144db  pop     rbp
0x1800144dc  retn
```
