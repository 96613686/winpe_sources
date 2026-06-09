# McTemplateU0zq_EventWriteTransfer

- ea: `0x18000579c`
- end: `0x18000583e`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `162`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180004340`
- `0x18000440c`
- `0x1800046ac`
- `0x1800048bc`
- `0x1800083d0`

## callees

- `0x1800056b4`
- `0x18000579c`
- `0x18000c860`

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
           &SCHEDULED_DIAGNOSTICS_PROVIDER_Context,
           &SCHEDULED_DIAGNOSTICS_EVENT_ERROR,
           (__int64)a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x18000579c  mov     [rsp+arg_18], r9d
0x1800057a1  sub     rsp, 78h
0x1800057a5  mov     rax, cs:__security_cookie
0x1800057ac  xor     rax, rsp
0x1800057af  mov     [rsp+78h+var_18], rax
0x1800057b4  xor     edx, edx
0x1800057b6  test    r8, r8
0x1800057b9  jz      short loc_1800057D2
0x1800057bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800057bf  inc     rax
0x1800057c2  cmp     [r8+rax*2], dx
0x1800057c7  jnz     short loc_1800057BF
0x1800057c9  lea     eax, ds:2[rax*2]
0x1800057d0  jmp     short loc_1800057D7
0x1800057d2  mov     eax, 0Ah
0x1800057d7  mov     [rsp+78h+var_30], eax
0x1800057db  lea     rcx, aNull; "NULL"
0x1800057e2  lea     rax, [rsp+78h+arg_18]
0x1800057ea  mov     [rsp+78h+var_2C], edx
0x1800057ee  test    r8, r8
0x1800057f1  mov     [rsp+78h+var_28], rax
0x1800057f6  lea     rax, [rsp+78h+var_48]
0x1800057fb  mov     [rsp+78h+var_20], 4
0x180005804  cmovz   r8, rcx
0x180005808  mov     [rsp+78h+var_58], rax
0x18000580d  mov     r9d, 3
0x180005813  mov     [rsp+78h+var_38], r8
0x180005818  lea     rdx, SCHEDULED_DIAGNOSTICS_EVENT_ERROR
0x18000581f  lea     rcx, SCHEDULED_DIAGNOSTICS_PROVIDER_Context
0x180005826  call    McGenEventWrite_EventWriteTransfer
0x18000582b  mov     rcx, [rsp+78h+var_18]
0x180005830  xor     rcx, rsp; StackCookie
0x180005833  call    __security_check_cookie
0x180005838  add     rsp, 78h
0x18000583c  retn
```
