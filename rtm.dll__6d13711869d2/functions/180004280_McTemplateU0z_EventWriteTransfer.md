# McTemplateU0z_EventWriteTransfer

- ea: `0x180004280`
- end: `0x1800042fa`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dea0`

## callees

- `0x180002c5c`
- `0x180004280`
- `0x18001f980`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(REGHANDLE *a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3)
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
  return McGenEventWrite_EventWriteTransfer(a1, a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x180004280  sub     rsp, 68h
0x180004284  mov     rax, cs:__security_cookie
0x18000428b  xor     rax, rsp
0x18000428e  mov     [rsp+68h+var_18], rax
0x180004293  xor     r10d, r10d
0x180004296  test    r8, r8
0x180004299  jz      short loc_1800042B2
0x18000429b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000429f  inc     rax
0x1800042a2  cmp     [r8+rax*2], r10w
0x1800042a7  jnz     short loc_18000429F
0x1800042a9  lea     eax, ds:2[rax*2]
0x1800042b0  jmp     short loc_1800042B7
0x1800042b2  mov     eax, 0Ah
0x1800042b7  lea     r9, aNull; "NULL"
0x1800042be  mov     [rsp+68h+var_20], eax
0x1800042c2  test    r8, r8
0x1800042c5  mov     [rsp+68h+var_1C], r10d
0x1800042ca  lea     rax, [rsp+68h+var_38]
0x1800042cf  cmovz   r8, r9
0x1800042d3  mov     [rsp+68h+var_48], rax
0x1800042d8  mov     r9d, 2
0x1800042de  mov     [rsp+68h+var_28], r8
0x1800042e3  call    McGenEventWrite_EventWriteTransfer
0x1800042e8  mov     rcx, [rsp+68h+var_18]
0x1800042ed  xor     rcx, rsp; StackCookie
0x1800042f0  call    __security_check_cookie
0x1800042f5  add     rsp, 68h
0x1800042f9  retn
```
