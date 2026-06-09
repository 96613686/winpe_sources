# McTemplateK0zz_EtwWriteTransfer

- ea: `0x1400227ec`
- end: `0x1400228a6`
- name: `McTemplateK0zz_EtwWriteTransfer`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002215c`

## callees

- `0x140014ac4`
- `0x1400227ec`
- `0x140039740`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zz_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  __int64 v5; // rax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // ecx
  const wchar_t *v9; // rcx
  bool v10; // zf
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v13; // [rsp+40h] [rbp-38h]
  int v14; // [rsp+48h] [rbp-30h]
  int v15; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v16; // [rsp+50h] [rbp-28h]
  int v17; // [rsp+58h] [rbp-20h]
  int v18; // [rsp+5Ch] [rbp-1Ch]

  v5 = -1;
  v6 = 10;
  if ( a4 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a4[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v14 = v8;
  v9 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v15 = 0;
  v13 = a4;
  v10 = a5 == 0;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v6 = 2 * v5 + 2;
    v10 = a5 == 0;
  }
  if ( v10 )
    v9 = L"NULL";
  v17 = v6;
  v16 = v9;
  v18 = 0;
  return McGenEventWrite_EtwWriteTransfer((__int64)v9, (const EVENT_DESCRIPTOR *)TPM_AUTH_FAILED, 0, 3u, &v12);
}

```

## disassembly

```asm
0x1400227ec  sub     rsp, 78h
0x1400227f0  mov     rax, cs:__security_cookie
0x1400227f7  xor     rax, rsp
0x1400227fa  mov     [rsp+78h+var_18], rax
0x1400227ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x140022803  xor     r8d, r8d
0x140022806  mov     edx, 0Ah
0x14002280b  test    r9, r9
0x14002280e  jz      short loc_140022826
0x140022810  mov     rcx, rax
0x140022813  inc     rcx
0x140022816  cmp     [r9+rcx*2], r8w
0x14002281b  jnz     short loc_140022813
0x14002281d  lea     ecx, ds:2[rcx*2]
0x140022824  jmp     short loc_140022828
0x140022826  mov     ecx, edx
0x140022828  test    r9, r9
0x14002282b  mov     [rsp+78h+var_30], ecx
0x14002282f  mov     rcx, [rsp+78h+arg_20]
0x140022837  lea     r10, aNull_0; "NULL"
0x14002283e  cmovz   r9, r10
0x140022842  mov     [rsp+78h+var_2C], r8d
0x140022847  mov     [rsp+78h+var_38], r9
0x14002284c  test    rcx, rcx
0x14002284f  jz      short loc_140022865
0x140022851  inc     rax
0x140022854  cmp     [rcx+rax*2], r8w
0x140022859  jnz     short loc_140022851
0x14002285b  lea     edx, ds:2[rax*2]
0x140022862  test    rcx, rcx
0x140022865  cmovz   rcx, r10
0x140022869  mov     [rsp+78h+var_20], edx
0x14002286d  lea     rax, [rsp+78h+var_48]
0x140022872  mov     [rsp+78h+var_28], rcx
0x140022877  lea     rdx, TPM_AUTH_FAILED
0x14002287e  mov     [rsp+78h+var_58], rax
0x140022883  mov     r9d, 3
0x140022889  mov     [rsp+78h+var_1C], r8d
0x14002288e  call    McGenEventWrite_EtwWriteTransfer
0x140022893  mov     rcx, [rsp+78h+var_18]
0x140022898  xor     rcx, rsp; StackCookie
0x14002289b  call    __security_check_cookie
0x1400228a0  add     rsp, 78h
0x1400228a4  retn
```
