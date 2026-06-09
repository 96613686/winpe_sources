# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)

- ea: `0x1800014c4`
- end: `0x180001600`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z`
- size: `316`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f1f8`
- `0x18000fce4`
- `0x18000fec0`
- `0x1800104b0`
- `0x180010870`
- `0x180011310`

## callees

- `0x18000131c`
- `0x1800014c4`
- `0x1800155c0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        const unsigned __int16 **a10)
{
  __int64 v11; // rcx
  int v12; // r8d
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rax
  int v21; // eax
  const unsigned __int16 *v22; // rdx
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+30h] [rbp-69h] BYREF
  const unsigned __int16 *v25; // [rsp+50h] [rbp-49h]
  int v26; // [rsp+58h] [rbp-41h]
  int v27; // [rsp+5Ch] [rbp-3Dh]
  __int64 v28; // [rsp+60h] [rbp-39h]
  __int64 v29; // [rsp+68h] [rbp-31h]
  const unsigned __int16 *v30; // [rsp+70h] [rbp-29h]
  int v31; // [rsp+78h] [rbp-21h]
  int v32; // [rsp+7Ch] [rbp-1Dh]
  __int64 v33; // [rsp+80h] [rbp-19h]
  __int64 v34; // [rsp+88h] [rbp-11h]
  const unsigned __int16 *v35; // [rsp+90h] [rbp-9h]
  int v36; // [rsp+98h] [rbp-1h]
  int v37; // [rsp+9Ch] [rbp+3h]
  const unsigned __int16 *v38; // [rsp+A0h] [rbp+7h]
  int v39; // [rsp+A8h] [rbp+Fh]
  int v40; // [rsp+ACh] [rbp+13h]

  v11 = -1;
  v12 = 1;
  v13 = *a10;
  if ( *a10 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)v13 + v14) );
    v15 = v14 + 1;
  }
  else
  {
    v13 = &qword_180018198;
    v15 = 1;
  }
  v39 = v15;
  v38 = v13;
  v40 = 0;
  v16 = *a9;
  if ( *a9 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_BYTE *)v16 + v17) );
    v18 = v17 + 1;
  }
  else
  {
    v16 = &qword_180018198;
    v18 = 1;
  }
  v36 = v18;
  v33 = a8;
  v35 = v16;
  v37 = 0;
  v34 = 4;
  v19 = *a7;
  if ( *a7 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *((_BYTE *)v19 + v20) );
    v21 = v20 + 1;
  }
  else
  {
    v19 = &qword_180018198;
    v21 = 1;
  }
  v31 = v21;
  v28 = a6;
  v30 = v19;
  v32 = 0;
  v29 = 4;
  v22 = *a5;
  if ( *a5 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v22 + v11) );
    v12 = v11 + 1;
  }
  else
  {
    v22 = &qword_180018198;
  }
  v25 = v22;
  v26 = v12;
  v27 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001F000, a2, 0, 0, 8u, &v24);
}

```

## disassembly

```asm
0x1800014c4  push    rbp
0x1800014c6  lea     rbp, [rsp-27h]
0x1800014cb  sub     rsp, 0C0h
0x1800014d2  mov     rax, cs:__security_cookie
0x1800014d9  xor     rax, rsp
0x1800014dc  mov     [rbp+27h+var_10], rax
0x1800014e0  mov     rax, [rbp+27h+arg_48]
0x1800014e4  lea     r11, qword_180018198
0x1800014eb  mov     r10, rdx
0x1800014ee  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800014f2  xor     r9d, r9d
0x1800014f5  mov     r8d, 1
0x1800014fb  mov     rdx, [rax]
0x1800014fe  test    rdx, rdx
0x180001501  jz      short loc_180001513
0x180001503  mov     rax, rcx
0x180001506  inc     rax
0x180001509  cmp     [rdx+rax], r9b
0x18000150d  jnz     short loc_180001506
0x18000150f  inc     eax
0x180001511  jmp     short loc_180001519
0x180001513  mov     rdx, r11
0x180001516  mov     eax, r8d
0x180001519  mov     [rbp+27h+var_18], eax
0x18000151c  mov     rax, [rbp+27h+arg_40]
0x180001520  mov     [rbp+27h+var_20], rdx
0x180001524  mov     [rbp+27h+var_14], r9d
0x180001528  mov     rdx, [rax]
0x18000152b  test    rdx, rdx
0x18000152e  jz      short loc_180001540
0x180001530  mov     rax, rcx
0x180001533  inc     rax
0x180001536  cmp     [rdx+rax], r9b
0x18000153a  jnz     short loc_180001533
0x18000153c  inc     eax
0x18000153e  jmp     short loc_180001546
0x180001540  mov     rdx, r11
0x180001543  mov     eax, r8d
0x180001546  mov     [rbp+27h+var_28], eax
0x180001549  mov     rax, [rbp+27h+arg_38]
0x18000154d  mov     [rbp+27h+var_40], rax
0x180001551  mov     rax, [rbp+27h+arg_30]
0x180001555  mov     [rbp+27h+var_30], rdx
0x180001559  mov     [rbp+27h+var_24], r9d
0x18000155d  mov     [rbp+27h+var_38], 4
0x180001565  mov     rdx, [rax]
0x180001568  test    rdx, rdx
0x18000156b  jz      short loc_18000157D
0x18000156d  mov     rax, rcx
0x180001570  inc     rax
0x180001573  cmp     [rdx+rax], r9b
0x180001577  jnz     short loc_180001570
0x180001579  inc     eax
0x18000157b  jmp     short loc_180001583
0x18000157d  mov     rdx, r11
0x180001580  mov     eax, r8d
0x180001583  mov     [rbp+27h+var_48], eax
0x180001586  mov     rax, [rbp+27h+arg_28]
0x18000158a  mov     [rbp+27h+var_60], rax
0x18000158e  mov     rax, [rbp+27h+arg_20]
0x180001592  mov     [rbp+27h+var_50], rdx
0x180001596  mov     [rbp+27h+var_44], r9d
0x18000159a  mov     [rbp+27h+var_58], 4
0x1800015a2  mov     rdx, [rax]
0x1800015a5  test    rdx, rdx
0x1800015a8  jz      short loc_1800015B9
0x1800015aa  inc     rcx
0x1800015ad  cmp     [rdx+rcx], r9b
0x1800015b1  jnz     short loc_1800015AA
0x1800015b3  lea     r8d, [rcx+1]
0x1800015b7  jmp     short loc_1800015BC
0x1800015b9  mov     rdx, r11
0x1800015bc  lea     rax, [rbp+27h+var_90]
0x1800015c0  mov     [rbp+27h+var_70], rdx
0x1800015c4  mov     [rbp+27h+var_68], r8d
0x1800015c8  lea     rcx, dword_18001F000
0x1800015cf  mov     [rsp+0C0h+var_98], rax
0x1800015d4  xor     r8d, r8d
0x1800015d7  mov     rdx, r10
0x1800015da  mov     [rsp+0C0h+var_A0], 8
0x1800015e2  mov     [rbp+27h+var_64], r9d
0x1800015e6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800015eb  mov     rcx, [rbp+27h+var_10]
0x1800015ef  xor     rcx, rsp; StackCookie
0x1800015f2  call    __security_check_cookie
0x1800015f7  add     rsp, 0C0h
0x1800015fe  pop     rbp
0x1800015ff  retn
```
