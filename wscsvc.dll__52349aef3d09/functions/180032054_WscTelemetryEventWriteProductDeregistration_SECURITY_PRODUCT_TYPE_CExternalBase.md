# WscTelemetryEventWriteProductDeregistration(_SECURITY_PRODUCT_TYPE,CExternalBase *)

- ea: `0x180032054`
- end: `0x1800321e7`
- name: `?WscTelemetryEventWriteProductDeregistration@@YAXW4_SECURITY_PRODUCT_TYPE@@PEAVCExternalBase@@@Z`
- size: `403`
- prototype: `void(enum _SECURITY_PRODUCT_TYPE, struct CExternalBase *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800250c0`

## callees

- `0x18000156c`
- `0x180016820`
- `0x180019384`
- `0x180019518`
- `0x180023dec`
- `0x180029e74`
- `0x180032054`

## pseudocode

```c
void __fastcall WscTelemetryEventWriteProductDeregistration(enum _SECURITY_PRODUCT_TYPE a1, struct CExternalBase *a2)
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
  __int16 *v15; // rdx
  const WCHAR *v16; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v17; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int16 *v18; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int16 *v19; // [rsp+A8h] [rbp+58h] BYREF

  v2 = (unsigned __int16 *)*((_QWORD *)a2 + 5);
  v4 = (unsigned __int16 *)*((_QWORD *)a2 + 6);
  v6 = (const WCHAR *)*((_QWORD *)a2 + 4);
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
        v15 = &word_18004C48E;
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
      v15 = (__int16 *)byte_18004C3E3;
      goto LABEL_20;
    }
  }
  else if ( (unsigned int)dword_180053218 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180053218, 0x400000000000LL) )
  {
    v15 = (__int16 *)&unk_18004C438;
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
0x180032054  mov     [rsp-38h+arg_0], rbx
0x180032059  push    rbp
0x18003205a  push    rsi
0x18003205b  push    rdi
0x18003205c  push    r12
0x18003205e  push    r13
0x180032060  push    r14
0x180032062  push    r15
0x180032064  mov     rbp, rsp
0x180032067  sub     rsp, 50h
0x18003206b  mov     r12, [rdx+28h]
0x18003206f  mov     rdi, rdx
0x180032072  mov     r15, [rdx+30h]
0x180032076  mov     ebx, ecx
0x180032078  mov     r13, [rdx+20h]
0x18003207c  mov     r14, r12
0x18003207f  mov     [rbp+arg_8], r12
0x180032083  mov     rsi, r15
0x180032086  mov     [rbp+arg_10], r15
0x18003208a  test    r12, r12
0x18003208d  jz      short loc_180032094
0x18003208f  test    r15, r15
0x180032092  jnz     short loc_1800320BC
0x180032094  xor     eax, eax
0x180032096  lea     r8, [rbp+arg_10]
0x18003209a  test    r15, r15
0x18003209d  lea     rdx, [rbp+arg_8]
0x1800320a1  mov     rcx, r13; lpSrc
0x1800320a4  cmovnz  r8, rax; unsigned __int16 **
0x1800320a8  test    r12, r12
0x1800320ab  cmovnz  rdx, rax; unsigned __int16 **
0x1800320af  call    ?WscGetProductInfo@@YAXPEBGPEAPEAG1@Z; WscGetProductInfo(ushort const *,ushort * *,ushort * *)
0x1800320b4  mov     r14, [rbp+arg_8]
0x1800320b8  mov     rsi, [rbp+arg_10]
0x1800320bc  test    ebx, ebx
0x1800320be  jz      short loc_180032136
0x1800320c0  sub     ebx, 1
0x1800320c3  jz      short loc_180032104
0x1800320c5  cmp     ebx, 1
0x1800320c8  jnz     loc_18003219F
0x1800320ce  mov     eax, cs:dword_180053218
0x1800320d4  cmp     eax, 5
0x1800320d7  jbe     loc_18003219F
0x1800320dd  mov     rdx, 400000000000h
0x1800320e7  lea     rcx, dword_180053218
0x1800320ee  call    _tlgKeywordOn
0x1800320f3  test    al, al
0x1800320f5  jz      loc_18003219F
0x1800320fb  lea     rdx, word_18004C48E
0x180032102  jmp     short loc_180032162
0x180032104  mov     eax, cs:dword_180053218
0x18003210a  cmp     eax, 5
0x18003210d  jbe     loc_18003219F
0x180032113  mov     rdx, 400000000000h
0x18003211d  lea     rcx, dword_180053218
0x180032124  call    _tlgKeywordOn
0x180032129  test    al, al
0x18003212b  jz      short loc_18003219F
0x18003212d  lea     rdx, byte_18004C3E3
0x180032134  jmp     short loc_180032162
0x180032136  mov     eax, cs:dword_180053218
0x18003213c  cmp     eax, 5
0x18003213f  jbe     short loc_18003219F
0x180032141  mov     rdx, 400000000000h
0x18003214b  lea     rcx, dword_180053218
0x180032152  call    _tlgKeywordOn
0x180032157  test    al, al
0x180032159  jz      short loc_18003219F
0x18003215b  lea     rdx, unk_18004C438
0x180032162  mov     rax, [rdi+10h]
0x180032166  mov     [rbp+arg_10], rax
0x18003216a  lea     rax, [rbp+arg_8]
0x18003216e  mov     [rsp+50h+var_18], rax
0x180032173  lea     rax, [rbp+arg_10]
0x180032177  mov     [rsp+50h+var_20], rax
0x18003217c  lea     rax, [rbp+arg_18]
0x180032180  mov     [rsp+50h+var_28], rax
0x180032185  lea     rax, [rbp+var_10]
0x180032189  mov     [rsp+50h+var_30], rax
0x18003218e  mov     [rbp+arg_8], rsi
0x180032192  mov     [rbp+arg_18], r14
0x180032196  mov     [rbp+var_10], r13
0x18003219a  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18003219f  test    r12, r12
0x1800321a2  jnz     short loc_1800321B7
0x1800321a4  mov     rdx, r14; unsigned __int16 *
0x1800321a7  mov     rcx, rdi; this
0x1800321aa  call    ?SetCompanyName@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetCompanyName(ushort const *)
0x1800321af  mov     rcx, r14; Block
0x1800321b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800321b7  test    r15, r15
0x1800321ba  jnz     short loc_1800321CF
0x1800321bc  mov     rdx, rsi; unsigned __int16 *
0x1800321bf  mov     rcx, rdi; this
0x1800321c2  call    ?SetVersionNumber@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetVersionNumber(ushort const *)
0x1800321c7  mov     rcx, rsi; Block
0x1800321ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800321cf  mov     rbx, [rsp+50h+arg_0]
0x1800321d7  add     rsp, 50h
0x1800321db  pop     r15
0x1800321dd  pop     r14
0x1800321df  pop     r13
0x1800321e1  pop     r12
0x1800321e3  pop     rdi
0x1800321e4  pop     rsi
0x1800321e5  pop     rbp
0x1800321e6  retn
```
