# McTemplateU0zz_EventWriteTransfer

- ea: `0x180024408`
- end: `0x1800244b9`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `177`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001fc58`

## callees

- `0x180024290`
- `0x180024408`
- `0x180024640`

## pseudocode

```c
ULONG __fastcall McTemplateU0zz_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // edx
  __int64 v6; // rcx
  __int64 v7; // rcx
  bool v8; // zf
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-48h] BYREF
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
    v7 = (unsigned int)(2 * v6 + 2);
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
  return McGenEventWrite_EventWriteTransfer(
           v7,
           (const EVENT_DESCRIPTOR *)RpcProxyLbsArbitrationConflict,
           (__int64)a3,
           3u,
           &v10);
}

```

## disassembly

```asm
0x180024408  sub     rsp, 78h
0x18002440c  mov     rax, cs:__security_cookie
0x180024413  xor     rax, rsp
0x180024416  mov     [rsp+78h+var_18], rax
0x18002441b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002441f  xor     r10d, r10d
0x180024422  mov     edx, 0Ah
0x180024427  test    r8, r8
0x18002442a  jz      short loc_180024442
0x18002442c  mov     rcx, rax
0x18002442f  inc     rcx
0x180024432  cmp     [r8+rcx*2], r10w
0x180024437  jnz     short loc_18002442F
0x180024439  lea     ecx, ds:2[rcx*2]
0x180024440  jmp     short loc_180024444
0x180024442  mov     ecx, edx
0x180024444  test    r8, r8
0x180024447  mov     [rsp+78h+var_30], ecx
0x18002444b  lea     r11, aNull; "NULL"
0x180024452  mov     [rsp+78h+var_2C], r10d
0x180024457  cmovz   r8, r11
0x18002445b  mov     [rsp+78h+var_38], r8
0x180024460  test    r9, r9
0x180024463  jz      short loc_180024479
0x180024465  inc     rax
0x180024468  cmp     [r9+rax*2], r10w
0x18002446d  jnz     short loc_180024465
0x18002446f  lea     edx, ds:2[rax*2]
0x180024476  test    r9, r9
0x180024479  cmovz   r9, r11
0x18002447d  mov     [rsp+78h+var_20], edx
0x180024481  mov     [rsp+78h+var_28], r9
0x180024486  lea     rax, [rsp+78h+var_48]
0x18002448b  mov     r9d, 3
0x180024491  mov     [rsp+78h+var_1C], r10d
0x180024496  lea     rdx, RpcProxyLbsArbitrationConflict
0x18002449d  mov     [rsp+78h+var_58], rax
0x1800244a2  call    McGenEventWrite_EventWriteTransfer
0x1800244a7  mov     rcx, [rsp+78h+var_18]
0x1800244ac  xor     rcx, rsp; StackCookie
0x1800244af  call    __security_check_cookie
0x1800244b4  add     rsp, 78h
0x1800244b8  retn
```
