# McTemplateU0pz_EventWriteTransfer

- ea: `0x18000c210`
- end: `0x18000c2a1`
- name: `McTemplateU0pz_EventWriteTransfer`
- size: `145`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180001800`
- `0x180001ea0`
- `0x180002390`
- `0x18000ccb0`
- `0x18000e0e0`
- `0x18000e2e0`
- `0x18000e4e0`
- `0x18000ef50`
- `0x18000f210`
- `0x1800123b0`

## callees

- `0x1800061d0`
- `0x180006620`
- `0x18000c210`

## pseudocode

```c
ULONG __fastcall McTemplateU0pz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  const wchar_t *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]
  __int64 v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = a3;
  v9 = 8;
  v8 = &v13;
  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v11 = v5;
  v12 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v10 = a4;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, 0, 3u, &v7);
}

```

## disassembly

```asm
0x18000c210  mov     r11, rsp
0x18000c213  mov     [r11+18h], r8
0x18000c217  sub     rsp, 78h
0x18000c21b  mov     rax, cs:__security_cookie
0x18000c222  xor     rax, rsp
0x18000c225  mov     [rsp+78h+var_18], rax
0x18000c22a  xor     r8d, r8d
0x18000c22d  mov     qword ptr [r11-30h], 8
0x18000c235  lea     rax, [r11+18h]
0x18000c239  mov     [r11-38h], rax
0x18000c23d  test    r9, r9
0x18000c240  jz      short loc_18000C259
0x18000c242  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c246  inc     rax
0x18000c249  cmp     [r9+rax*2], r8w
0x18000c24e  jnz     short loc_18000C246
0x18000c250  lea     eax, ds:2[rax*2]
0x18000c257  jmp     short loc_18000C25E
0x18000c259  mov     eax, 0Ah
0x18000c25e  test    r9, r9
0x18000c261  mov     [rsp+78h+var_20], eax
0x18000c265  lea     rcx, aNull_0; "NULL"
0x18000c26c  mov     [rsp+78h+var_1C], r8d
0x18000c271  cmovz   r9, rcx
0x18000c275  lea     rax, [rsp+78h+var_48]
0x18000c27a  mov     [rsp+78h+var_28], r9
0x18000c27f  mov     r9d, 3
0x18000c285  mov     [rsp+78h+var_58], rax
0x18000c28a  call    McGenEventWrite_EventWriteTransfer
0x18000c28f  mov     rcx, [rsp+78h+var_18]
0x18000c294  xor     rcx, rsp; StackCookie
0x18000c297  call    __security_check_cookie
0x18000c29c  add     rsp, 78h
0x18000c2a0  retn
```
