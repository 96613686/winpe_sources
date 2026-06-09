# McTemplateU0z_EventWriteTransfer

- ea: `0x1800242e8`
- end: `0x180024362`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001fc58`
- `0x180021ed8`

## callees

- `0x180024290`
- `0x1800242e8`
- `0x180024640`

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
0x1800242e8  sub     rsp, 68h
0x1800242ec  mov     rax, cs:__security_cookie
0x1800242f3  xor     rax, rsp
0x1800242f6  mov     [rsp+68h+var_18], rax
0x1800242fb  xor     r9d, r9d
0x1800242fe  test    r8, r8
0x180024301  jz      short loc_18002431A
0x180024303  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024307  inc     rax
0x18002430a  cmp     [r8+rax*2], r9w
0x18002430f  jnz     short loc_180024307
0x180024311  lea     eax, ds:2[rax*2]
0x180024318  jmp     short loc_18002431F
0x18002431a  mov     eax, 0Ah
0x18002431f  test    r8, r8
0x180024322  mov     [rsp+68h+var_20], eax
0x180024326  lea     rcx, aNull; "NULL"
0x18002432d  mov     [rsp+68h+var_1C], r9d
0x180024332  cmovz   r8, rcx
0x180024336  lea     rax, [rsp+68h+var_38]
0x18002433b  mov     r9d, 2
0x180024341  mov     [rsp+68h+var_28], r8
0x180024346  mov     [rsp+68h+var_48], rax
0x18002434b  call    McGenEventWrite_EventWriteTransfer
0x180024350  mov     rcx, [rsp+68h+var_18]
0x180024355  xor     rcx, rsp; StackCookie
0x180024358  call    __security_check_cookie
0x18002435d  add     rsp, 68h
0x180024361  retn
```
