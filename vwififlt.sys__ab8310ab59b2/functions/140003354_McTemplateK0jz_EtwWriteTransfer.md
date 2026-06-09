# McTemplateK0jz_EtwWriteTransfer

- ea: `0x140003354`
- end: `0x1400033e5`
- name: `McTemplateK0jz_EtwWriteTransfer`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140004568`

## callees

- `0x140003354`
- `0x14000590c`
- `0x14000f110`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0jz_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        __int64 a4,
        const wchar_t *a5)
{
  const wchar_t *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-48h] BYREF
  __int64 v10; // [rsp+40h] [rbp-38h]
  __int64 v11; // [rsp+48h] [rbp-30h]
  const wchar_t *v12; // [rsp+50h] [rbp-28h]
  int v13; // [rsp+58h] [rbp-20h]
  int v14; // [rsp+5Ch] [rbp-1Ch]

  v5 = a5;
  v10 = a4;
  v11 = 16;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a5[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v7 = 10;
  }
  v13 = v7;
  v14 = 0;
  if ( !a5 )
    v5 = L"NULL";
  v12 = v5;
  return McGenEventWrite_EtwWriteTransfer((__int64)v5, a2, a3, 3u, &v9);
}

```

## disassembly

```asm
0x140003354  sub     rsp, 78h
0x140003358  mov     rax, cs:__security_cookie
0x14000335f  xor     rax, rsp
0x140003362  mov     [rsp+78h+var_18], rax
0x140003367  mov     rcx, [rsp+78h+arg_20]
0x14000336f  xor     r10d, r10d
0x140003372  mov     [rsp+78h+var_38], r9
0x140003377  mov     [rsp+78h+var_30], 10h
0x140003380  test    rcx, rcx
0x140003383  jz      short loc_1400033DE
0x140003385  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003389  inc     rax
0x14000338c  cmp     [rcx+rax*2], r10w
0x140003391  jnz     short loc_140003389
0x140003393  lea     eax, ds:2[rax*2]
0x14000339a  lea     r9, aNull_0; "NULL"
0x1400033a1  mov     [rsp+78h+var_20], eax
0x1400033a5  test    rcx, rcx
0x1400033a8  mov     [rsp+78h+var_1C], r10d
0x1400033ad  lea     rax, [rsp+78h+var_48]
0x1400033b2  cmovz   rcx, r9
0x1400033b6  mov     [rsp+78h+var_58], rax
0x1400033bb  mov     r9d, 3
0x1400033c1  mov     [rsp+78h+var_28], rcx
0x1400033c6  call    McGenEventWrite_EtwWriteTransfer
0x1400033cb  mov     rcx, [rsp+78h+var_18]
0x1400033d0  xor     rcx, rsp; StackCookie
0x1400033d3  call    __security_check_cookie
0x1400033d8  add     rsp, 78h
0x1400033dc  retn
0x1400033de  mov     eax, 0Ah
0x1400033e3  jmp     short loc_14000339A
```
