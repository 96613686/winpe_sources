# WscTelemetryEventWriteProductRegistration(_SECURITY_PRODUCT_TYPE,CExternalBase *)

- ea: `0x1800321f0`
- end: `0x180032383`
- name: `?WscTelemetryEventWriteProductRegistration@@YAXW4_SECURITY_PRODUCT_TYPE@@PEAVCExternalBase@@@Z`
- size: `403`
- prototype: `void(enum _SECURITY_PRODUCT_TYPE, struct CExternalBase *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180024b40`

## callees

- `0x18000156c`
- `0x180016820`
- `0x180019384`
- `0x180019518`
- `0x180023dec`
- `0x180029e74`
- `0x1800321f0`

## pseudocode

```c
void __fastcall WscTelemetryEventWriteProductRegistration(enum _SECURITY_PRODUCT_TYPE a1, struct CExternalBase *a2)
{
  unsigned __int16 *v2; // r12
  unsigned __int16 *v4; // r15
  const WCHAR *v6; // r13
  unsigned __int16 *v7; // r14
  unsigned __int16 *v8; // rsi
  unsigned __int16 **v9; // r8
  unsigned __int16 **v10; // rdx
  int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  char *v15; // rdx
  const WCHAR *v16; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v17; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int16 *v18; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int16 *v19; // [rsp+A8h] [rbp+58h] BYREF

  v2 = (unsigned __int16 *)*((_QWORD *)a2 + 5);
  v4 = (unsigned __int16 *)*((_QWORD *)a2 + 6);
  v6 = (const WCHAR *)*((_QWORD *)a2 + 3);
  v7 = v2;
  v17 = v2;
  v8 = v4;
  v18 = v4;
  if ( !v2 || !v4 )
  {
    v9 = &v18;
    v10 = &v17;
    if ( v4 )
      v9 = 0;
    if ( v2 )
      v10 = 0;
    WscGetProductInfo(v6, v10, v9);
    v7 = v17;
    v8 = v18;
  }
  if ( a1 )
  {
    v11 = a1 - 1;
    if ( v11 )
    {
      if ( v11 == 1
        && (unsigned int)dword_180053218 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_180053218, 0x400000000000LL) )
      {
        v15 = byte_18004C58D;
LABEL_20:
        v18 = (unsigned __int16 *)*((_QWORD *)a2 + 2);
        v17 = v8;
        v19 = v7;
        v16 = v6;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v12,
          (__int64)v15,
          v13,
          v14,
          &v16,
          &v19,
          &v18,
          &v17);
      }
    }
    else if ( (unsigned int)dword_180053218 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180053218, 0x400000000000LL) )
    {
      v15 = (char *)&word_18004C4E6;
      goto LABEL_20;
    }
  }
  else if ( (unsigned int)dword_180053218 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180053218, 0x400000000000LL) )
  {
    v15 = byte_18004C539;
    goto LABEL_20;
  }
  if ( !v2 )
  {
    CExternalBase::SetCompanyName(a2, v7);
    operator delete(v7);
  }
  if ( !v4 )
  {
    CExternalBase::SetVersionNumber(a2, v8);
    operator delete(v8);
  }
}

```

## disassembly

```asm
0x1800321f0  mov     [rsp-38h+arg_0], rbx
0x1800321f5  push    rbp
0x1800321f6  push    rsi
0x1800321f7  push    rdi
0x1800321f8  push    r12
0x1800321fa  push    r13
0x1800321fc  push    r14
0x1800321fe  push    r15
0x180032200  mov     rbp, rsp
0x180032203  sub     rsp, 50h
0x180032207  mov     r12, [rdx+28h]
0x18003220b  mov     rdi, rdx
0x18003220e  mov     r15, [rdx+30h]
0x180032212  mov     ebx, ecx
0x180032214  mov     r13, [rdx+18h]
0x180032218  mov     r14, r12
0x18003221b  mov     [rbp+arg_8], r12
0x18003221f  mov     rsi, r15
0x180032222  mov     [rbp+arg_10], r15
0x180032226  test    r12, r12
0x180032229  jz      short loc_180032230
0x18003222b  test    r15, r15
0x18003222e  jnz     short loc_180032258
0x180032230  xor     eax, eax
0x180032232  lea     r8, [rbp+arg_10]
0x180032236  test    r15, r15
0x180032239  lea     rdx, [rbp+arg_8]
0x18003223d  mov     rcx, r13; lpSrc
0x180032240  cmovnz  r8, rax; unsigned __int16 **
0x180032244  test    r12, r12
0x180032247  cmovnz  rdx, rax; unsigned __int16 **
0x18003224b  call    ?WscGetProductInfo@@YAXPEBGPEAPEAG1@Z; WscGetProductInfo(ushort const *,ushort * *,ushort * *)
0x180032250  mov     r14, [rbp+arg_8]
0x180032254  mov     rsi, [rbp+arg_10]
0x180032258  test    ebx, ebx
0x18003225a  jz      short loc_1800322D2
0x18003225c  sub     ebx, 1
0x18003225f  jz      short loc_1800322A0
0x180032261  cmp     ebx, 1
0x180032264  jnz     loc_18003233B
0x18003226a  mov     eax, cs:dword_180053218
0x180032270  cmp     eax, 5
0x180032273  jbe     loc_18003233B
0x180032279  mov     rdx, 400000000000h
0x180032283  lea     rcx, dword_180053218
0x18003228a  call    _tlgKeywordOn
0x18003228f  test    al, al
0x180032291  jz      loc_18003233B
0x180032297  lea     rdx, byte_18004C58D
0x18003229e  jmp     short loc_1800322FE
0x1800322a0  mov     eax, cs:dword_180053218
0x1800322a6  cmp     eax, 5
0x1800322a9  jbe     loc_18003233B
0x1800322af  mov     rdx, 400000000000h
0x1800322b9  lea     rcx, dword_180053218
0x1800322c0  call    _tlgKeywordOn
0x1800322c5  test    al, al
0x1800322c7  jz      short loc_18003233B
0x1800322c9  lea     rdx, word_18004C4E6
0x1800322d0  jmp     short loc_1800322FE
0x1800322d2  mov     eax, cs:dword_180053218
0x1800322d8  cmp     eax, 5
0x1800322db  jbe     short loc_18003233B
0x1800322dd  mov     rdx, 400000000000h
0x1800322e7  lea     rcx, dword_180053218
0x1800322ee  call    _tlgKeywordOn
0x1800322f3  test    al, al
0x1800322f5  jz      short loc_18003233B
0x1800322f7  lea     rdx, byte_18004C539
0x1800322fe  mov     rax, [rdi+10h]
0x180032302  mov     [rbp+arg_10], rax
0x180032306  lea     rax, [rbp+arg_8]
0x18003230a  mov     [rsp+50h+var_18], rax
0x18003230f  lea     rax, [rbp+arg_10]
0x180032313  mov     [rsp+50h+var_20], rax
0x180032318  lea     rax, [rbp+arg_18]
0x18003231c  mov     [rsp+50h+var_28], rax
0x180032321  lea     rax, [rbp+var_10]
0x180032325  mov     [rsp+50h+var_30], rax
0x18003232a  mov     [rbp+arg_8], rsi
0x18003232e  mov     [rbp+arg_18], r14
0x180032332  mov     [rbp+var_10], r13
0x180032336  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18003233b  test    r12, r12
0x18003233e  jnz     short loc_180032353
0x180032340  mov     rdx, r14; unsigned __int16 *
0x180032343  mov     rcx, rdi; this
0x180032346  call    ?SetCompanyName@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetCompanyName(ushort const *)
0x18003234b  mov     rcx, r14; Block
0x18003234e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180032353  test    r15, r15
0x180032356  jnz     short loc_18003236B
0x180032358  mov     rdx, rsi; unsigned __int16 *
0x18003235b  mov     rcx, rdi; this
0x18003235e  call    ?SetVersionNumber@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetVersionNumber(ushort const *)
0x180032363  mov     rcx, rsi; Block
0x180032366  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003236b  mov     rbx, [rsp+50h+arg_0]
0x180032373  add     rsp, 50h
0x180032377  pop     r15
0x180032379  pop     r14
0x18003237b  pop     r13
0x18003237d  pop     r12
0x18003237f  pop     rdi
0x180032380  pop     rsi
0x180032381  pop     rbp
0x180032382  retn
```
