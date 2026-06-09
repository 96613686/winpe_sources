# McTemplateU0zq_EventWriteTransfer

- ea: `0x180009890`
- end: `0x18000992b`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `155`
- prototype: `ULONG __fastcall(__int64, __int64, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003930`
- `0x180004f60`

## callees

- `0x180005730`
- `0x1800097bc`
- `0x180009890`

## pseudocode

```c
ULONG __fastcall McTemplateU0zq_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-38h]
  int v9; // [rsp+48h] [rbp-30h]
  int v10; // [rsp+4Ch] [rbp-2Ch]
  int *v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = a4;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v9 = v5;
  v10 = 0;
  v11 = &v13;
  v12 = 4;
  if ( !a3 )
    a3 = L"NULL";
  v8 = a3;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)L"NULL",
           (const EVENT_DESCRIPTOR *)VirtdiskOpenStart,
           (__int64)a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x180009890  mov     [rsp+arg_18], r9d
0x180009895  sub     rsp, 78h
0x180009899  mov     rax, cs:__security_cookie
0x1800098a0  xor     rax, rsp
0x1800098a3  mov     [rsp+78h+var_18], rax
0x1800098a8  xor     edx, edx
0x1800098aa  test    r8, r8
0x1800098ad  jz      short loc_1800098C6
0x1800098af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800098b3  inc     rax
0x1800098b6  cmp     [r8+rax*2], dx
0x1800098bb  jnz     short loc_1800098B3
0x1800098bd  lea     eax, ds:2[rax*2]
0x1800098c4  jmp     short loc_1800098CB
0x1800098c6  mov     eax, 0Ah
0x1800098cb  mov     [rsp+78h+var_30], eax
0x1800098cf  lea     rcx, aNull; "NULL"
0x1800098d6  lea     rax, [rsp+78h+arg_18]
0x1800098de  mov     [rsp+78h+var_2C], edx
0x1800098e2  test    r8, r8
0x1800098e5  mov     [rsp+78h+var_28], rax
0x1800098ea  lea     rax, [rsp+78h+var_48]
0x1800098ef  mov     [rsp+78h+var_20], 4
0x1800098f8  cmovz   r8, rcx
0x1800098fc  mov     [rsp+78h+var_58], rax
0x180009901  mov     r9d, 3
0x180009907  mov     [rsp+78h+var_38], r8
0x18000990c  lea     rdx, VirtdiskOpenStart
0x180009913  call    McGenEventWrite_EventWriteTransfer
0x180009918  mov     rcx, [rsp+78h+var_18]
0x18000991d  xor     rcx, rsp; StackCookie
0x180009920  call    __security_check_cookie
0x180009925  add     rsp, 78h
0x180009929  retn
```
