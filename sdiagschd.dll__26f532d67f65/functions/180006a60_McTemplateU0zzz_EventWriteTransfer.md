# McTemplateU0zzz_EventWriteTransfer

- ea: `0x180006a60`
- end: `0x180006b5c`
- name: `McTemplateU0zzz_EventWriteTransfer`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180006770`

## callees

- `0x1800056b4`
- `0x180006a60`
- `0x18000c860`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  const wchar_t *v5; // r10
  __int64 v6; // rax
  int v7; // edx
  __int64 v8; // rcx
  int v9; // ecx
  __int64 v10; // rcx
  int v11; // ecx
  bool v12; // zf
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-58h] BYREF
  const wchar_t *v15; // [rsp+40h] [rbp-48h]
  int v16; // [rsp+48h] [rbp-40h]
  int v17; // [rsp+4Ch] [rbp-3Ch]
  const wchar_t *v18; // [rsp+50h] [rbp-38h]
  int v19; // [rsp+58h] [rbp-30h]
  int v20; // [rsp+5Ch] [rbp-2Ch]
  const wchar_t *v21; // [rsp+60h] [rbp-28h]
  int v22; // [rsp+68h] [rbp-20h]
  int v23; // [rsp+6Ch] [rbp-1Ch]

  v5 = a5;
  v6 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v16 = v9;
  v17 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v15 = a3;
  if ( a4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a4[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v19 = v11;
  v20 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v18 = a4;
  v12 = a5 == 0;
  if ( a5 )
  {
    do
      ++v6;
    while ( a5[v6] );
    v7 = 2 * v6 + 2;
    v12 = a5 == 0;
  }
  if ( v12 )
    v5 = L"NULL";
  v22 = v7;
  v21 = v5;
  v23 = 0;
  return McGenEventWrite_EventWriteTransfer(
           &SCHEDULED_DIAGNOSTICS_PROVIDER_Context,
           &SCHEDULED_DIAGNOSTICS_EVENT_ROOTCAUSE_DETECTED,
           (__int64)a3,
           4u,
           &v14);
}

```

## disassembly

```asm
0x180006a60  push    rbx
0x180006a62  sub     rsp, 80h
0x180006a69  mov     rax, cs:__security_cookie
0x180006a70  xor     rax, rsp
0x180006a73  mov     [rsp+88h+var_18], rax
0x180006a78  mov     r10, [rsp+88h+arg_20]
0x180006a80  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006a84  xor     r11d, r11d
0x180006a87  mov     edx, 0Ah
0x180006a8c  test    r8, r8
0x180006a8f  jz      short loc_180006AA7
0x180006a91  mov     rcx, rax
0x180006a94  inc     rcx
0x180006a97  cmp     [r8+rcx*2], r11w
0x180006a9c  jnz     short loc_180006A94
0x180006a9e  lea     ecx, ds:2[rcx*2]
0x180006aa5  jmp     short loc_180006AA9
0x180006aa7  mov     ecx, edx
0x180006aa9  test    r8, r8
0x180006aac  mov     [rsp+88h+var_40], ecx
0x180006ab0  lea     rbx, aNull; "NULL"
0x180006ab7  mov     [rsp+88h+var_3C], r11d
0x180006abc  cmovz   r8, rbx
0x180006ac0  mov     [rsp+88h+var_48], r8
0x180006ac5  test    r9, r9
0x180006ac8  jz      short loc_180006AE0
0x180006aca  mov     rcx, rax
0x180006acd  inc     rcx
0x180006ad0  cmp     [r9+rcx*2], r11w
0x180006ad5  jnz     short loc_180006ACD
0x180006ad7  lea     ecx, ds:2[rcx*2]
0x180006ade  jmp     short loc_180006AE2
0x180006ae0  mov     ecx, edx
0x180006ae2  test    r9, r9
0x180006ae5  mov     [rsp+88h+var_30], ecx
0x180006ae9  mov     [rsp+88h+var_2C], r11d
0x180006aee  cmovz   r9, rbx
0x180006af2  mov     [rsp+88h+var_38], r9
0x180006af7  test    r10, r10
0x180006afa  jz      short loc_180006B10
0x180006afc  inc     rax
0x180006aff  cmp     [r10+rax*2], r11w
0x180006b04  jnz     short loc_180006AFC
0x180006b06  lea     edx, ds:2[rax*2]
0x180006b0d  test    r10, r10
0x180006b10  cmovz   r10, rbx
0x180006b14  mov     [rsp+88h+var_20], edx
0x180006b18  lea     rax, [rsp+88h+var_58]
0x180006b1d  mov     [rsp+88h+var_28], r10
0x180006b22  lea     rdx, SCHEDULED_DIAGNOSTICS_EVENT_ROOTCAUSE_DETECTED
0x180006b29  mov     [rsp+88h+var_68], rax
0x180006b2e  mov     r9d, 4
0x180006b34  mov     [rsp+88h+var_1C], r11d
0x180006b39  lea     rcx, SCHEDULED_DIAGNOSTICS_PROVIDER_Context
0x180006b40  call    McGenEventWrite_EventWriteTransfer
0x180006b45  mov     rcx, [rsp+88h+var_18]
0x180006b4a  xor     rcx, rsp; StackCookie
0x180006b4d  call    __security_check_cookie
0x180006b52  add     rsp, 80h
0x180006b59  pop     rbx
0x180006b5a  retn
```
