# McTemplateU0z_EventWriteTransfer

- ea: `0x180029e80`
- end: `0x180029efa`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029938`

## callees

- `0x180001ec0`
- `0x180029dd0`
- `0x180029e80`

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
0x180029e80  sub     rsp, 68h
0x180029e84  mov     rax, cs:__security_cookie
0x180029e8b  xor     rax, rsp
0x180029e8e  mov     [rsp+68h+var_18], rax
0x180029e93  xor     r9d, r9d
0x180029e96  test    r8, r8
0x180029e99  jz      short loc_180029EB2
0x180029e9b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029e9f  inc     rax
0x180029ea2  cmp     [r8+rax*2], r9w
0x180029ea7  jnz     short loc_180029E9F
0x180029ea9  lea     eax, ds:2[rax*2]
0x180029eb0  jmp     short loc_180029EB7
0x180029eb2  mov     eax, 0Ah
0x180029eb7  test    r8, r8
0x180029eba  mov     [rsp+68h+var_20], eax
0x180029ebe  lea     rcx, aNull_0; "NULL"
0x180029ec5  mov     [rsp+68h+var_1C], r9d
0x180029eca  cmovz   r8, rcx
0x180029ece  lea     rax, [rsp+68h+var_38]
0x180029ed3  mov     r9d, 2
0x180029ed9  mov     [rsp+68h+var_28], r8
0x180029ede  mov     [rsp+68h+var_48], rax
0x180029ee3  call    McGenEventWrite_EventWriteTransfer
0x180029ee8  mov     rcx, [rsp+68h+var_18]
0x180029eed  xor     rcx, rsp; StackCookie
0x180029ef0  call    __security_check_cookie
0x180029ef5  add     rsp, 68h
0x180029ef9  retn
```
