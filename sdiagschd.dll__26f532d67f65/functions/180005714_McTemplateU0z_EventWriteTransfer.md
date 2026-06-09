# McTemplateU0z_EventWriteTransfer

- ea: `0x180005714`
- end: `0x180005796`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `130`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000440c`
- `0x1800046ac`
- `0x180005974`
- `0x1800062c4`

## callees

- `0x1800056b4`
- `0x180005714`
- `0x18000c860`

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
  return McGenEventWrite_EventWriteTransfer(&SCHEDULED_DIAGNOSTICS_PROVIDER_Context, a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x180005714  sub     rsp, 68h
0x180005718  mov     rax, cs:__security_cookie
0x18000571f  xor     rax, rsp
0x180005722  mov     [rsp+68h+var_18], rax
0x180005727  xor     r9d, r9d
0x18000572a  test    r8, r8
0x18000572d  jz      short loc_180005746
0x18000572f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005733  inc     rax
0x180005736  cmp     [r8+rax*2], r9w
0x18000573b  jnz     short loc_180005733
0x18000573d  lea     eax, ds:2[rax*2]
0x180005744  jmp     short loc_18000574B
0x180005746  mov     eax, 0Ah
0x18000574b  test    r8, r8
0x18000574e  mov     [rsp+68h+var_20], eax
0x180005752  lea     rcx, aNull; "NULL"
0x180005759  mov     [rsp+68h+var_1C], r9d
0x18000575e  cmovz   r8, rcx
0x180005762  lea     rax, [rsp+68h+var_38]
0x180005767  lea     rcx, SCHEDULED_DIAGNOSTICS_PROVIDER_Context
0x18000576e  mov     [rsp+68h+var_28], r8
0x180005773  mov     r9d, 2
0x180005779  mov     [rsp+68h+var_48], rax
0x18000577e  call    McGenEventWrite_EventWriteTransfer
0x180005783  mov     rcx, [rsp+68h+var_18]
0x180005788  xor     rcx, rsp; StackCookie
0x18000578b  call    __security_check_cookie
0x180005790  add     rsp, 68h
0x180005794  retn
```
