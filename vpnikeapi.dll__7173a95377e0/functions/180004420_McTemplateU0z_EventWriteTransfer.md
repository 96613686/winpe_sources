# McTemplateU0z_EventWriteTransfer

- ea: `0x180004420`
- end: `0x18000449a`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: `ULONG __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, const wchar_t *)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x1800011c0`
- `0x1800013c0`
- `0x180002360`
- `0x180002660`
- `0x180002910`
- `0x180002b70`
- `0x180002f80`
- `0x180003120`
- `0x1800032c0`
- `0x180003470`
- `0x180003620`
- `0x1800038d0`
- `0x180003b80`
- `0x180003e30`
- `0x180004110`
- `0x1800044a0`
- `0x180004780`
- `0x180004a20`
- `0x180004cd0`
- `0x180004f80`
- `0x1800052f0`
- `0x1800055b0`
- `0x180005880`
- `0x180005b30`
- `0x180005de0`
- `0x1800060c0`

## callees

- `0x1800043c0`
- `0x180004420`
- `0x18000cff0`

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
0x180004420  sub     rsp, 68h
0x180004424  mov     rax, cs:__security_cookie
0x18000442b  xor     rax, rsp
0x18000442e  mov     [rsp+68h+var_18], rax
0x180004433  xor     r10d, r10d
0x180004436  test    r8, r8
0x180004439  jz      short loc_180004452
0x18000443b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000443f  inc     rax
0x180004442  cmp     [r8+rax*2], r10w
0x180004447  jnz     short loc_18000443F
0x180004449  lea     eax, ds:2[rax*2]
0x180004450  jmp     short loc_180004457
0x180004452  mov     eax, 0Ah
0x180004457  lea     r9, aNull; "NULL"
0x18000445e  mov     [rsp+68h+var_20], eax
0x180004462  test    r8, r8
0x180004465  mov     [rsp+68h+var_1C], r10d
0x18000446a  lea     rax, [rsp+68h+var_38]
0x18000446f  cmovz   r8, r9
0x180004473  mov     [rsp+68h+var_48], rax
0x180004478  mov     r9d, 2
0x18000447e  mov     [rsp+68h+var_28], r8
0x180004483  call    McGenEventWrite_EventWriteTransfer
0x180004488  mov     rcx, [rsp+68h+var_18]
0x18000448d  xor     rcx, rsp; StackCookie
0x180004490  call    __security_check_cookie
0x180004495  add     rsp, 68h
0x180004499  retn
```
