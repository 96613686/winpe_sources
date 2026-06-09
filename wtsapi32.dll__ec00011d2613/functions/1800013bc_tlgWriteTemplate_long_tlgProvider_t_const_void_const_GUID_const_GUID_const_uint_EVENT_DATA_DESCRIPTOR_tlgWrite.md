# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800013bc`
- end: `0x1800014bb`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `255`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f1f8`
- `0x18000fce4`
- `0x18000fec0`
- `0x1800104b0`
- `0x180010870`

## callees

- `0x18000131c`
- `0x1800013bc`
- `0x1800155c0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const unsigned __int16 **a6,
        __int64 a7,
        const unsigned __int16 **a8)
{
  __int64 v9; // rcx
  int v10; // r8d
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+30h] [rbp-39h] BYREF
  const unsigned __int16 *v20; // [rsp+50h] [rbp-19h]
  int v21; // [rsp+58h] [rbp-11h]
  int v22; // [rsp+5Ch] [rbp-Dh]
  const unsigned __int16 *v23; // [rsp+60h] [rbp-9h]
  int v24; // [rsp+68h] [rbp-1h]
  int v25; // [rsp+6Ch] [rbp+3h]
  __int64 v26; // [rsp+70h] [rbp+7h]
  __int64 v27; // [rsp+78h] [rbp+Fh]
  const unsigned __int16 *v28; // [rsp+80h] [rbp+17h]
  int v29; // [rsp+88h] [rbp+1Fh]
  int v30; // [rsp+8Ch] [rbp+23h]

  v9 = -1;
  v10 = 1;
  v11 = *a8;
  if ( *a8 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_BYTE *)v11 + v12) );
    v13 = v12 + 1;
  }
  else
  {
    v11 = &qword_180018198;
    v13 = 1;
  }
  v29 = v13;
  v26 = a7;
  v28 = v11;
  v30 = 0;
  v27 = 4;
  v14 = *a6;
  if ( *a6 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_BYTE *)v14 + v15) );
    v16 = v15 + 1;
  }
  else
  {
    v14 = &qword_180018198;
    v16 = 1;
  }
  v24 = v16;
  v23 = v14;
  v25 = 0;
  v17 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_BYTE *)v17 + v9) );
    v10 = v9 + 1;
  }
  else
  {
    v17 = &qword_180018198;
  }
  v20 = v17;
  v21 = v10;
  v22 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001F000, a2, 0, 0, 6u, &v19);
}

```

## disassembly

```asm
0x1800013bc  push    rbp
0x1800013be  lea     rbp, [rsp-37h]
0x1800013c3  sub     rsp, 0A0h
0x1800013ca  mov     rax, cs:__security_cookie
0x1800013d1  xor     rax, rsp
0x1800013d4  mov     [rbp+37h+var_10], rax
0x1800013d8  mov     rax, [rbp+37h+arg_38]
0x1800013dc  lea     r11, qword_180018198
0x1800013e3  mov     r10, rdx
0x1800013e6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800013ea  xor     r9d, r9d
0x1800013ed  mov     r8d, 1
0x1800013f3  mov     rdx, [rax]
0x1800013f6  test    rdx, rdx
0x1800013f9  jz      short loc_18000140B
0x1800013fb  mov     rax, rcx
0x1800013fe  inc     rax
0x180001401  cmp     [rdx+rax], r9b
0x180001405  jnz     short loc_1800013FE
0x180001407  inc     eax
0x180001409  jmp     short loc_180001411
0x18000140b  mov     rdx, r11
0x18000140e  mov     eax, r8d
0x180001411  mov     [rbp+37h+var_18], eax
0x180001414  mov     rax, [rbp+37h+arg_30]
0x180001418  mov     [rbp+37h+var_30], rax
0x18000141c  mov     rax, [rbp+37h+arg_28]
0x180001420  mov     [rbp+37h+var_20], rdx
0x180001424  mov     [rbp+37h+var_14], r9d
0x180001428  mov     [rbp+37h+var_28], 4
0x180001430  mov     rdx, [rax]
0x180001433  test    rdx, rdx
0x180001436  jz      short loc_180001448
0x180001438  mov     rax, rcx
0x18000143b  inc     rax
0x18000143e  cmp     [rdx+rax], r9b
0x180001442  jnz     short loc_18000143B
0x180001444  inc     eax
0x180001446  jmp     short loc_18000144E
0x180001448  mov     rdx, r11
0x18000144b  mov     eax, r8d
0x18000144e  mov     [rbp+37h+var_38], eax
0x180001451  mov     rax, [rbp+37h+arg_20]
0x180001455  mov     [rbp+37h+var_40], rdx
0x180001459  mov     [rbp+37h+var_34], r9d
0x18000145d  mov     rdx, [rax]
0x180001460  test    rdx, rdx
0x180001463  jz      short loc_180001474
0x180001465  inc     rcx
0x180001468  cmp     [rdx+rcx], r9b
0x18000146c  jnz     short loc_180001465
0x18000146e  lea     r8d, [rcx+1]
0x180001472  jmp     short loc_180001477
0x180001474  mov     rdx, r11
0x180001477  lea     rax, [rbp+37h+var_70]
0x18000147b  mov     [rbp+37h+var_50], rdx
0x18000147f  mov     [rbp+37h+var_48], r8d
0x180001483  lea     rcx, dword_18001F000
0x18000148a  mov     [rsp+0A0h+var_78], rax
0x18000148f  xor     r8d, r8d
0x180001492  mov     rdx, r10
0x180001495  mov     [rsp+0A0h+var_80], 6
0x18000149d  mov     [rbp+37h+var_44], r9d
0x1800014a1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800014a6  mov     rcx, [rbp+37h+var_10]
0x1800014aa  xor     rcx, rsp; StackCookie
0x1800014ad  call    __security_check_cookie
0x1800014b2  add     rsp, 0A0h
0x1800014b9  pop     rbp
0x1800014ba  retn
```
