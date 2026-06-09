# WscTelemetryEventWriteProductLoad(CExternalBase *,bool)

- ea: `0x18002698c`
- end: `0x180026ad6`
- name: `?WscTelemetryEventWriteProductLoad@@YAXPEAVCExternalBase@@_N@Z`
- size: `330`
- prototype: `void __fastcall(struct CExternalBase *this, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016d50`
- `0x180037460`

## callees

- `0x18000760c`
- `0x180016820`
- `0x180019384`
- `0x180019518`
- `0x18001fb88`
- `0x180023dec`
- `0x18002698c`
- `0x180029e74`

## pseudocode

```c
void __fastcall WscTelemetryEventWriteProductLoad(struct CExternalBase *this, unsigned __int8 a2)
{
  int v3; // r13d
  __int64 *v4; // r15
  __int64 *v5; // r14
  __int64 *v6; // rsi
  const WCHAR *v7; // r12
  __int64 *v8; // rdi
  unsigned __int16 **v9; // r8
  unsigned __int16 **v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 *v14; // [rsp+50h] [rbp-20h] BYREF
  __int64 *v15; // [rsp+58h] [rbp-18h] BYREF
  __int64 *v16; // [rsp+60h] [rbp-10h] BYREF
  const WCHAR *v17; // [rsp+68h] [rbp-8h] BYREF
  __int64 *v18; // [rsp+C0h] [rbp+50h] BYREF
  __int64 *v19; // [rsp+C8h] [rbp+58h] BYREF

  v3 = a2;
  if ( dword_180053218 )
  {
    v4 = (__int64 *)*((_QWORD *)this + 5);
    v5 = (__int64 *)*((_QWORD *)this + 6);
    v6 = v4;
    v7 = (const WCHAR *)*((_QWORD *)this + 3);
    v8 = v5;
    v18 = v4;
    v19 = v5;
    if ( !v4 || !v5 )
    {
      v9 = (unsigned __int16 **)&v19;
      v10 = (unsigned __int16 **)&v18;
      if ( v5 )
        v9 = 0;
      if ( v4 )
        v10 = 0;
      WscGetProductInfo(v7, v10, v9);
      v6 = v18;
      v8 = v19;
    }
    if ( (unsigned int)dword_180053218 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180053218, 0x400000000000LL) )
    {
      LODWORD(v18) = v3;
      LODWORD(v19) = CExternalBase::GetProductState((__int64)this);
      v15 = (__int64 *)*((_QWORD *)this + 2);
      v14 = v8;
      v16 = v6;
      v17 = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned __int8 *)byte_18004C611,
        v12,
        v13,
        (__int64 **)&v17,
        &v16,
        &v15,
        &v14,
        (__int64)&v19,
        (__int64)&v18);
    }
    if ( !v4 )
    {
      CExternalBase::SetCompanyName(this, (const unsigned __int16 *)v6);
      operator delete(v6);
    }
    if ( !v5 )
    {
      CExternalBase::SetVersionNumber(this, (const unsigned __int16 *)v8);
      operator delete(v8);
    }
  }
}

```

## disassembly

```asm
0x18002698c  mov     [rsp-38h+arg_0], rbx
0x180026991  push    rbp
0x180026992  push    rsi
0x180026993  push    rdi
0x180026994  push    r12
0x180026996  push    r13
0x180026998  push    r14
0x18002699a  push    r15
0x18002699c  mov     rbp, rsp
0x18002699f  sub     rsp, 70h
0x1800269a3  mov     eax, cs:dword_180053218
0x1800269a9  mov     rbx, rcx
0x1800269ac  movzx   r13d, dl
0x1800269b0  test    eax, eax
0x1800269b2  jz      loc_180026ABE
0x1800269b8  mov     r15, [rcx+28h]
0x1800269bc  mov     r14, [rcx+30h]
0x1800269c0  mov     rsi, r15
0x1800269c3  mov     r12, [rcx+18h]
0x1800269c7  mov     rdi, r14
0x1800269ca  mov     [rbp+arg_10], r15
0x1800269ce  mov     [rbp+arg_18], r14
0x1800269d2  test    r15, r15
0x1800269d5  jz      short loc_1800269DC
0x1800269d7  test    r14, r14
0x1800269da  jnz     short loc_180026A04
0x1800269dc  xor     eax, eax
0x1800269de  lea     r8, [rbp+arg_18]
0x1800269e2  test    r14, r14
0x1800269e5  lea     rdx, [rbp+arg_10]
0x1800269e9  mov     rcx, r12; lpSrc
0x1800269ec  cmovnz  r8, rax; unsigned __int16 **
0x1800269f0  test    r15, r15
0x1800269f3  cmovnz  rdx, rax; unsigned __int16 **
0x1800269f7  call    ?WscGetProductInfo@@YAXPEBGPEAPEAG1@Z; WscGetProductInfo(ushort const *,ushort * *,ushort * *)
0x1800269fc  mov     rsi, [rbp+arg_10]
0x180026a00  mov     rdi, [rbp+arg_18]
0x180026a04  mov     eax, cs:dword_180053218
0x180026a0a  cmp     eax, 5
0x180026a0d  jbe     short loc_180026A8E
0x180026a0f  mov     rdx, 400000000000h
0x180026a19  lea     rcx, dword_180053218
0x180026a20  call    _tlgKeywordOn
0x180026a25  test    al, al
0x180026a27  jz      short loc_180026A8E
0x180026a29  mov     rcx, rbx
0x180026a2c  mov     dword ptr [rbp+arg_10], r13d
0x180026a30  call    ?GetProductState@CExternalBase@@QEAA?AW4ProductState@@XZ; CExternalBase::GetProductState(void)
0x180026a35  mov     dword ptr [rbp+arg_18], eax
0x180026a38  lea     rdx, byte_18004C611
0x180026a3f  mov     rax, [rbx+10h]
0x180026a43  mov     [rbp+var_18], rax
0x180026a47  lea     rax, [rbp+arg_10]
0x180026a4b  mov     [rsp+70h+var_28], rax
0x180026a50  lea     rax, [rbp+arg_18]
0x180026a54  mov     [rsp+70h+var_30], rax
0x180026a59  lea     rax, [rbp+var_20]
0x180026a5d  mov     [rsp+70h+var_38], rax
0x180026a62  lea     rax, [rbp+var_18]
0x180026a66  mov     [rsp+70h+var_40], rax
0x180026a6b  lea     rax, [rbp+var_10]
0x180026a6f  mov     [rsp+70h+var_48], rax
0x180026a74  lea     rax, [rbp+var_8]
0x180026a78  mov     [rsp+70h+var_50], rax
0x180026a7d  mov     [rbp+var_20], rdi
0x180026a81  mov     [rbp+var_10], rsi
0x180026a85  mov     [rbp+var_8], r12
0x180026a89  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180026a8e  test    r15, r15
0x180026a91  jnz     short loc_180026AA6
0x180026a93  mov     rdx, rsi; unsigned __int16 *
0x180026a96  mov     rcx, rbx; this
0x180026a99  call    ?SetCompanyName@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetCompanyName(ushort const *)
0x180026a9e  mov     rcx, rsi; Block
0x180026aa1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026aa6  test    r14, r14
0x180026aa9  jnz     short loc_180026ABE
0x180026aab  mov     rdx, rdi; unsigned __int16 *
0x180026aae  mov     rcx, rbx; this
0x180026ab1  call    ?SetVersionNumber@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetVersionNumber(ushort const *)
0x180026ab6  mov     rcx, rdi; Block
0x180026ab9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026abe  mov     rbx, [rsp+70h+arg_0]
0x180026ac6  add     rsp, 70h
0x180026aca  pop     r15
0x180026acc  pop     r14
0x180026ace  pop     r13
0x180026ad0  pop     r12
0x180026ad2  pop     rdi
0x180026ad3  pop     rsi
0x180026ad4  pop     rbp
0x180026ad5  retn
```
