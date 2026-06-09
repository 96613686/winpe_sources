# McTemplateU0zz_EtwEventWriteTransfer

- ea: `0x180012130`
- end: `0x1800121e1`
- name: `McTemplateU0zz_EtwEventWriteTransfer`
- size: `177`
- prototype: `__int64 __fastcall(__int64, __int64, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800086c0`

## callees

- `0x18000f970`
- `0x180012130`
- `0x180018970`

## pseudocode

```c
__int64 __fastcall McTemplateU0zz_EtwEventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // edx
  __int64 v6; // rcx
  int v7; // ecx
  bool v8; // zf
  _BYTE v10[16]; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v11; // [rsp+40h] [rbp-38h]
  int v12; // [rsp+48h] [rbp-30h]
  int v13; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v14; // [rsp+50h] [rbp-28h]
  int v15; // [rsp+58h] [rbp-20h]
  int v16; // [rsp+5Ch] [rbp-1Ch]

  v4 = -1;
  v5 = 10;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v7 = 10;
  }
  v12 = v7;
  v13 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v11 = a3;
  v8 = a4 == 0;
  if ( a4 )
  {
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
    v8 = a4 == 0;
  }
  if ( v8 )
    a4 = L"NULL";
  v15 = v5;
  v14 = a4;
  v16 = 0;
  return McGenEventWrite_EtwEventWriteTransfer(v7, (unsigned int)SCHEDULER_PARENT_FOUND, (_DWORD)a3, 3, (__int64)v10);
}

```

## disassembly

```asm
0x180012130  sub     rsp, 78h
0x180012134  mov     rax, cs:__security_cookie
0x18001213b  xor     rax, rsp
0x18001213e  mov     [rsp+78h+var_18], rax
0x180012143  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012147  xor     r10d, r10d
0x18001214a  mov     edx, 0Ah
0x18001214f  test    r8, r8
0x180012152  jz      short loc_18001216A
0x180012154  mov     rcx, rax
0x180012157  inc     rcx
0x18001215a  cmp     [r8+rcx*2], r10w
0x18001215f  jnz     short loc_180012157
0x180012161  lea     ecx, ds:2[rcx*2]
0x180012168  jmp     short loc_18001216C
0x18001216a  mov     ecx, edx
0x18001216c  test    r8, r8
0x18001216f  mov     [rsp+78h+var_30], ecx
0x180012173  lea     r11, aNull; "NULL"
0x18001217a  mov     [rsp+78h+var_2C], r10d
0x18001217f  cmovz   r8, r11
0x180012183  mov     [rsp+78h+var_38], r8
0x180012188  test    r9, r9
0x18001218b  jz      short loc_1800121A1
0x18001218d  inc     rax
0x180012190  cmp     [r9+rax*2], r10w
0x180012195  jnz     short loc_18001218D
0x180012197  lea     edx, ds:2[rax*2]
0x18001219e  test    r9, r9
0x1800121a1  cmovz   r9, r11
0x1800121a5  mov     [rsp+78h+var_20], edx
0x1800121a9  mov     [rsp+78h+var_28], r9
0x1800121ae  lea     rax, [rsp+78h+var_48]
0x1800121b3  mov     r9d, 3
0x1800121b9  mov     [rsp+78h+var_1C], r10d
0x1800121be  lea     rdx, SCHEDULER_PARENT_FOUND
0x1800121c5  mov     [rsp+78h+var_58], rax
0x1800121ca  call    McGenEventWrite_EtwEventWriteTransfer
0x1800121cf  mov     rcx, [rsp+78h+var_18]
0x1800121d4  xor     rcx, rsp; StackCookie
0x1800121d7  call    __security_check_cookie
0x1800121dc  add     rsp, 78h
0x1800121e0  retn
```
