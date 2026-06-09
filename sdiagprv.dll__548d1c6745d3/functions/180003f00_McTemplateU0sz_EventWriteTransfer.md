# McTemplateU0sz_EventWriteTransfer

- ea: `0x180003f00`
- end: `0x180003fb0`
- name: `McTemplateU0sz_EventWriteTransfer`
- size: `176`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const char *, const wchar_t *)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x180003a30`
- `0x180003c30`
- `0x180013b60`
- `0x180013ca0`
- `0x180013de0`
- `0x180013f20`
- `0x180014060`
- `0x1800143b0`
- `0x1800144f0`
- `0x180014840`
- `0x180014980`
- `0x180014ac0`
- `0x180014c0c`
- `0x180014d44`
- `0x180014f1c`

## callees

- `0x18000247c`
- `0x180003f00`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0sz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const char *a3,
        const wchar_t *a4)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  int v6; // ecx
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-48h] BYREF
  const char *v10; // [rsp+40h] [rbp-38h]
  int v11; // [rsp+48h] [rbp-30h]
  int v12; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v13; // [rsp+50h] [rbp-28h]
  int v14; // [rsp+58h] [rbp-20h]
  int v15; // [rsp+5Ch] [rbp-1Ch]

  v4 = -1;
  if ( a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  v11 = v6;
  v12 = 0;
  if ( !a3 )
    a3 = "NULL";
  v10 = a3;
  if ( a4 )
  {
    do
      ++v4;
    while ( a4[v4] );
    v7 = 2 * v4 + 2;
  }
  else
  {
    v7 = 10;
  }
  v14 = v7;
  v15 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v13 = a4;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 3u, &v9);
}

```

## disassembly

```asm
0x180003f00  sub     rsp, 78h
0x180003f04  mov     rax, cs:__security_cookie
0x180003f0b  xor     rax, rsp
0x180003f0e  mov     [rsp+78h+var_18], rax
0x180003f13  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003f17  xor     r11d, r11d
0x180003f1a  test    r8, r8
0x180003f1d  jz      short loc_180003F2F
0x180003f1f  mov     rcx, rax
0x180003f22  inc     rcx
0x180003f25  cmp     [r8+rcx], r11b
0x180003f29  jnz     short loc_180003F22
0x180003f2b  inc     ecx
0x180003f2d  jmp     short loc_180003F34
0x180003f2f  mov     ecx, 5
0x180003f34  test    r8, r8
0x180003f37  mov     [rsp+78h+var_30], ecx
0x180003f3b  lea     r10, aNull; "NULL"
0x180003f42  mov     [rsp+78h+var_2C], r11d
0x180003f47  cmovz   r8, r10
0x180003f4b  mov     [rsp+78h+var_38], r8
0x180003f50  test    r9, r9
0x180003f53  jz      short loc_180003F68
0x180003f55  inc     rax
0x180003f58  cmp     [r9+rax*2], r11w
0x180003f5d  jnz     short loc_180003F55
0x180003f5f  lea     eax, ds:2[rax*2]
0x180003f66  jmp     short loc_180003F6D
0x180003f68  mov     eax, 0Ah
0x180003f6d  test    r9, r9
0x180003f70  mov     [rsp+78h+var_20], eax
0x180003f74  lea     rcx, aNull_0; "NULL"
0x180003f7b  mov     [rsp+78h+var_1C], r11d
0x180003f80  cmovz   r9, rcx
0x180003f84  lea     rax, [rsp+78h+var_48]
0x180003f89  mov     [rsp+78h+var_28], r9
0x180003f8e  mov     r9d, 3
0x180003f94  mov     [rsp+78h+var_58], rax
0x180003f99  call    McGenEventWrite_EventWriteTransfer
0x180003f9e  mov     rcx, [rsp+78h+var_18]
0x180003fa3  xor     rcx, rsp; StackCookie
0x180003fa6  call    __security_check_cookie
0x180003fab  add     rsp, 78h
0x180003faf  retn
```
