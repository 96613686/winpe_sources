# McTemplateU0z_EventWriteTransfer

- ea: `0x180013128`
- end: `0x1800131a2`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ad80`
- `0x18000cf00`
- `0x180011630`

## callees

- `0x1800130d0`
- `0x180013128`
- `0x1800298c0`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 10;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x180013128  sub     rsp, 68h
0x18001312c  mov     rax, cs:__security_cookie
0x180013133  xor     rax, rsp
0x180013136  mov     [rsp+68h+var_18], rax
0x18001313b  xor     r9d, r9d
0x18001313e  test    r8, r8
0x180013141  jz      short loc_18001315A
0x180013143  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013147  inc     rax
0x18001314a  cmp     [r8+rax*2], r9w
0x18001314f  jnz     short loc_180013147
0x180013151  lea     eax, ds:2[rax*2]
0x180013158  jmp     short loc_18001315F
0x18001315a  mov     eax, 0Ah
0x18001315f  test    r8, r8
0x180013162  mov     [rsp+68h+var_20], eax
0x180013166  lea     rcx, aNull; "NULL"
0x18001316d  mov     [rsp+68h+var_1C], r9d
0x180013172  cmovz   r8, rcx
0x180013176  lea     rax, [rsp+68h+var_38]
0x18001317b  mov     r9d, 2
0x180013181  mov     [rsp+68h+var_28], r8
0x180013186  mov     [rsp+68h+var_48], rax
0x18001318b  call    McGenEventWrite_EventWriteTransfer
0x180013190  mov     rcx, [rsp+68h+var_18]
0x180013195  xor     rcx, rsp; StackCookie
0x180013198  call    __security_check_cookie
0x18001319d  add     rsp, 68h
0x1800131a1  retn
```
