# McTemplateU0zz_EventWriteTransfer

- ea: `0x18000699c`
- end: `0x180006a57`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180005974`

## callees

- `0x1800056b4`
- `0x18000699c`
- `0x18000c860`

## pseudocode

```c
ULONG __fastcall McTemplateU0zz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  __int64 v4; // rax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // ecx
  bool v9; // zf
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v12; // [rsp+40h] [rbp-38h]
  int v13; // [rsp+48h] [rbp-30h]
  int v14; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v15; // [rsp+50h] [rbp-28h]
  int v16; // [rsp+58h] [rbp-20h]
  int v17; // [rsp+5Ch] [rbp-1Ch]

  v4 = -1;
  v6 = 10;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v13 = v8;
  v14 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v12 = a3;
  v9 = a4 == 0;
  if ( a4 )
  {
    do
      ++v4;
    while ( a4[v4] );
    v6 = 2 * v4 + 2;
    v9 = a4 == 0;
  }
  if ( v9 )
    a4 = L"NULL";
  v16 = v6;
  v15 = a4;
  v17 = 0;
  return McGenEventWrite_EventWriteTransfer(&SCHEDULED_DIAGNOSTICS_PROVIDER_Context, a2, (__int64)a3, 3u, &v11);
}

```

## disassembly

```asm
0x18000699c  push    rbx
0x18000699e  sub     rsp, 70h
0x1800069a2  mov     rax, cs:__security_cookie
0x1800069a9  xor     rax, rsp
0x1800069ac  mov     [rsp+78h+var_18], rax
0x1800069b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800069b5  xor     r11d, r11d
0x1800069b8  mov     r10, rdx
0x1800069bb  mov     edx, 0Ah
0x1800069c0  test    r8, r8
0x1800069c3  jz      short loc_1800069DB
0x1800069c5  mov     rcx, rax
0x1800069c8  inc     rcx
0x1800069cb  cmp     [r8+rcx*2], r11w
0x1800069d0  jnz     short loc_1800069C8
0x1800069d2  lea     ecx, ds:2[rcx*2]
0x1800069d9  jmp     short loc_1800069DD
0x1800069db  mov     ecx, edx
0x1800069dd  test    r8, r8
0x1800069e0  mov     [rsp+78h+var_30], ecx
0x1800069e4  lea     rbx, aNull; "NULL"
0x1800069eb  mov     [rsp+78h+var_2C], r11d
0x1800069f0  cmovz   r8, rbx
0x1800069f4  mov     [rsp+78h+var_38], r8
0x1800069f9  test    r9, r9
0x1800069fc  jz      short loc_180006A12
0x1800069fe  inc     rax
0x180006a01  cmp     [r9+rax*2], r11w
0x180006a06  jnz     short loc_1800069FE
0x180006a08  lea     edx, ds:2[rax*2]
0x180006a0f  test    r9, r9
0x180006a12  cmovz   r9, rbx
0x180006a16  mov     [rsp+78h+var_20], edx
0x180006a1a  mov     [rsp+78h+var_28], r9
0x180006a1f  lea     rax, [rsp+78h+var_48]
0x180006a24  mov     r9d, 3
0x180006a2a  mov     [rsp+78h+var_1C], r11d
0x180006a2f  mov     rdx, r10
0x180006a32  mov     [rsp+78h+var_58], rax
0x180006a37  lea     rcx, SCHEDULED_DIAGNOSTICS_PROVIDER_Context
0x180006a3e  call    McGenEventWrite_EventWriteTransfer
0x180006a43  mov     rcx, [rsp+78h+var_18]
0x180006a48  xor     rcx, rsp; StackCookie
0x180006a4b  call    __security_check_cookie
0x180006a50  add     rsp, 70h
0x180006a54  pop     rbx
0x180006a55  retn
```
