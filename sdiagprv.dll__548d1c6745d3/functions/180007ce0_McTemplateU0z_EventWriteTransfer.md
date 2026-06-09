# McTemplateU0z_EventWriteTransfer

- ea: `0x180007ce0`
- end: `0x180007d5a`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180006fa0`
- `0x180008f00`
- `0x180011d2c`

## callees

- `0x18000247c`
- `0x180007ce0`
- `0x1800180f0`

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
0x180007ce0  sub     rsp, 68h
0x180007ce4  mov     rax, cs:__security_cookie
0x180007ceb  xor     rax, rsp
0x180007cee  mov     [rsp+68h+var_18], rax
0x180007cf3  xor     r9d, r9d
0x180007cf6  test    r8, r8
0x180007cf9  jz      short loc_180007D12
0x180007cfb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007cff  inc     rax
0x180007d02  cmp     [r8+rax*2], r9w
0x180007d07  jnz     short loc_180007CFF
0x180007d09  lea     eax, ds:2[rax*2]
0x180007d10  jmp     short loc_180007D17
0x180007d12  mov     eax, 0Ah
0x180007d17  test    r8, r8
0x180007d1a  mov     [rsp+68h+var_20], eax
0x180007d1e  lea     rcx, aNull_0; "NULL"
0x180007d25  mov     [rsp+68h+var_1C], r9d
0x180007d2a  cmovz   r8, rcx
0x180007d2e  lea     rax, [rsp+68h+var_38]
0x180007d33  mov     r9d, 2
0x180007d39  mov     [rsp+68h+var_28], r8
0x180007d3e  mov     [rsp+68h+var_48], rax
0x180007d43  call    McGenEventWrite_EventWriteTransfer
0x180007d48  mov     rcx, [rsp+68h+var_18]
0x180007d4d  xor     rcx, rsp; StackCookie
0x180007d50  call    __security_check_cookie
0x180007d55  add     rsp, 68h
0x180007d59  retn
```
