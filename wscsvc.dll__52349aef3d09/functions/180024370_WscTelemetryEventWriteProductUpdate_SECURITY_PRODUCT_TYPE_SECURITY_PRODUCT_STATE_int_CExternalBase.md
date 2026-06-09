# WscTelemetryEventWriteProductUpdate(_SECURITY_PRODUCT_TYPE,_SECURITY_PRODUCT_STATE,int,CExternalBase *)

- ea: `0x180024370`
- end: `0x18002459e`
- name: `?WscTelemetryEventWriteProductUpdate@@YAXW4_SECURITY_PRODUCT_TYPE@@W4_SECURITY_PRODUCT_STATE@@HPEAVCExternalBase@@@Z`
- size: `558`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180025520`

## callees

- `0x1800010f4`
- `0x180016820`
- `0x180019384`
- `0x180019518`
- `0x180024370`
- `0x180029e74`

## pseudocode

```c
void __fastcall WscTelemetryEventWriteProductUpdate(int a1, unsigned int a2, __int64 a3, CExternalBase *a4)
{
  __int64 v6; // r9
  unsigned __int16 *v7; // r12
  unsigned __int16 *v8; // r15
  unsigned __int16 *v9; // r14
  const WCHAR *v10; // r13
  unsigned __int16 *v11; // rsi
  unsigned __int16 **v12; // r8
  unsigned __int16 **v13; // rdx
  int v14; // ebx
  char *v15; // rdx
  unsigned __int16 **v16; // rax
  unsigned __int16 **v17; // [rsp+38h] [rbp-40h]
  unsigned __int16 **v18; // [rsp+40h] [rbp-38h]
  unsigned __int16 **v19; // [rsp+48h] [rbp-30h]
  unsigned __int16 *v20; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int16 *v21; // [rsp+58h] [rbp-20h] BYREF
  unsigned __int16 *v22; // [rsp+60h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+68h] [rbp-10h] BYREF
  int v24; // [rsp+C0h] [rbp+48h] BYREF
  unsigned int v25; // [rsp+C8h] [rbp+50h]
  unsigned int v26; // [rsp+D0h] [rbp+58h]
  unsigned __int16 *v27; // [rsp+D8h] [rbp+60h] BYREF

  v26 = a3;
  v25 = a2;
  v6 = a2;
  v7 = (unsigned __int16 *)*((_QWORD *)a4 + 5);
  v8 = (unsigned __int16 *)*((_QWORD *)a4 + 6);
  v9 = v7;
  v10 = (const WCHAR *)*((_QWORD *)a4 + 3);
  v11 = v8;
  v27 = v7;
  v20 = v8;
  if ( !v7 || !v8 )
  {
    v12 = &v20;
    v13 = &v27;
    if ( v8 )
      v12 = 0;
    if ( v7 )
      v13 = 0;
    WscGetProductInfo(v10, v13, v12);
    a3 = v26;
    v6 = v25;
    v9 = v27;
    v11 = v20;
  }
  if ( !a1 )
  {
    if ( (unsigned int)dword_180053218 <= 5
      || (qword_180053228 & 0x400000000000LL) == 0
      || (qword_180053230 & 0x400000000000LL) != qword_180053230 )
    {
      goto LABEL_25;
    }
    v15 = byte_18004C319;
LABEL_23:
    v22 = (unsigned __int16 *)*((_QWORD *)a4 + 2);
    v19 = (unsigned __int16 **)v23;
    v18 = &v22;
    v17 = &v21;
    v16 = &v20;
    v20 = (unsigned __int16 *)v10;
    v21 = v9;
    v23[0] = v11;
    goto LABEL_24;
  }
  v14 = a1 - 1;
  if ( !v14 )
  {
    if ( (unsigned int)dword_180053218 <= 5
      || (qword_180053228 & 0x400000000000LL) == 0
      || (qword_180053230 & 0x400000000000LL) != qword_180053230 )
    {
      goto LABEL_25;
    }
    v15 = (char *)&word_18004C2B6;
    goto LABEL_23;
  }
  if ( v14 == 1
    && (unsigned int)dword_180053218 > 5
    && (qword_180053228 & 0x400000000000LL) != 0
    && (qword_180053230 & 0x400000000000LL) == qword_180053230 )
  {
    v15 = byte_18004C37D;
    v21 = (unsigned __int16 *)*((_QWORD *)a4 + 2);
    v19 = &v20;
    v18 = &v21;
    v17 = &v22;
    v16 = (unsigned __int16 **)v23;
    v20 = v11;
    v22 = v9;
    v23[0] = v10;
LABEL_24:
    v24 = a3;
    LODWORD(v27) = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      0x400000000000LL,
      (__int64)v15,
      a3,
      v6,
      (__int64)&v27,
      (__int64)&v24,
      v16,
      v17,
      v18,
      v19);
  }
LABEL_25:
  if ( !v7 )
  {
    CExternalBase::SetCompanyName(a4, v9);
    operator delete(v9);
  }
  if ( !v8 )
  {
    CExternalBase::SetVersionNumber(a4, v11);
    operator delete(v11);
  }
}

```

## disassembly

```asm
0x180024370  mov     [rsp-40h+arg_10], r8d
0x180024375  mov     [rsp-40h+arg_8], edx
0x180024379  push    rbp
0x18002437a  push    rbx
0x18002437b  push    rsi
0x18002437c  push    rdi
0x18002437d  push    r12
0x18002437f  push    r13
0x180024381  push    r14
0x180024383  push    r15
0x180024385  mov     rbp, rsp
0x180024388  sub     rsp, 78h
0x18002438c  mov     rdi, r9
0x18002438f  mov     ebx, ecx
0x180024391  mov     r9d, edx
0x180024394  mov     r12, [rdi+28h]
0x180024398  mov     r15, [rdi+30h]
0x18002439c  mov     r14, r12
0x18002439f  mov     r13, [rdi+18h]
0x1800243a3  mov     rsi, r15
0x1800243a6  mov     [rbp+arg_18], r12
0x1800243aa  mov     [rbp+var_28], r15
0x1800243ae  test    r12, r12
0x1800243b1  jz      short loc_1800243B8
0x1800243b3  test    r15, r15
0x1800243b6  jnz     short loc_1800243E8
0x1800243b8  xor     eax, eax
0x1800243ba  lea     r8, [rbp+var_28]
0x1800243be  test    r15, r15
0x1800243c1  lea     rdx, [rbp+arg_18]
0x1800243c5  mov     rcx, r13; lpSrc
0x1800243c8  cmovnz  r8, rax; unsigned __int16 **
0x1800243cc  test    r12, r12
0x1800243cf  cmovnz  rdx, rax; unsigned __int16 **
0x1800243d3  call    ?WscGetProductInfo@@YAXPEBGPEAPEAG1@Z; WscGetProductInfo(ushort const *,ushort * *,ushort * *)
0x1800243d8  mov     r8d, [rbp+arg_10]
0x1800243dc  mov     r9d, [rbp+arg_8]
0x1800243e0  mov     r14, [rbp+arg_18]
0x1800243e4  mov     rsi, [rbp+var_28]
0x1800243e8  test    ebx, ebx
0x1800243ea  jz      loc_1800244C8
0x1800243f0  sub     ebx, 1
0x1800243f3  jz      loc_180024480
0x1800243f9  cmp     ebx, 1
0x1800243fc  jnz     loc_18002455D
0x180024402  mov     eax, cs:dword_180053218
0x180024408  cmp     eax, 5
0x18002440b  jbe     loc_18002455D
0x180024411  mov     rdx, cs:qword_180053230
0x180024418  mov     rcx, 400000000000h
0x180024422  mov     rax, cs:qword_180053228
0x180024429  test    rcx, rax
0x18002442c  jz      loc_18002455D
0x180024432  mov     rax, rdx
0x180024435  and     rax, rcx
0x180024438  cmp     rax, rdx
0x18002443b  jnz     loc_18002455D
0x180024441  mov     rax, [rdi+10h]
0x180024445  lea     rdx, byte_18004C37D
0x18002444c  mov     [rbp+var_20], rax
0x180024450  lea     rax, [rbp+var_28]
0x180024454  mov     [rsp+78h+var_30], rax
0x180024459  lea     rax, [rbp+var_20]
0x18002445d  mov     [rsp+78h+var_38], rax
0x180024462  lea     rax, [rbp+var_18]
0x180024466  mov     [rsp+78h+var_40], rax
0x18002446b  lea     rax, [rbp+var_10]
0x18002446f  mov     [rbp+var_28], rsi
0x180024473  mov     [rbp+var_18], r14
0x180024477  mov     [rbp+var_10], r13
0x18002447b  jmp     loc_180024539
0x180024480  mov     eax, cs:dword_180053218
0x180024486  cmp     eax, 5
0x180024489  jbe     loc_18002455D
0x18002448f  mov     rdx, cs:qword_180053230
0x180024496  mov     rcx, 400000000000h
0x1800244a0  mov     rax, cs:qword_180053228
0x1800244a7  test    rcx, rax
0x1800244aa  jz      loc_18002455D
0x1800244b0  mov     rax, rdx
0x1800244b3  and     rax, rcx
0x1800244b6  cmp     rax, rdx
0x1800244b9  jnz     loc_18002455D
0x1800244bf  lea     rdx, word_18004C2B6
0x1800244c6  jmp     short loc_180024506
0x1800244c8  mov     eax, cs:dword_180053218
0x1800244ce  cmp     eax, 5
0x1800244d1  jbe     loc_18002455D
0x1800244d7  mov     rdx, cs:qword_180053230
0x1800244de  mov     rcx, 400000000000h
0x1800244e8  mov     rax, cs:qword_180053228
0x1800244ef  test    rcx, rax
0x1800244f2  jz      short loc_18002455D
0x1800244f4  mov     rax, rdx
0x1800244f7  and     rax, rcx
0x1800244fa  cmp     rax, rdx
0x1800244fd  jnz     short loc_18002455D
0x1800244ff  lea     rdx, byte_18004C319
0x180024506  mov     rax, [rdi+10h]
0x18002450a  mov     [rbp+var_18], rax
0x18002450e  lea     rax, [rbp+var_10]
0x180024512  mov     [rsp+78h+var_30], rax
0x180024517  lea     rax, [rbp+var_18]
0x18002451b  mov     [rsp+78h+var_38], rax
0x180024520  lea     rax, [rbp+var_20]
0x180024524  mov     [rsp+78h+var_40], rax
0x180024529  lea     rax, [rbp+var_28]
0x18002452d  mov     [rbp+var_28], r13
0x180024531  mov     [rbp+var_20], r14
0x180024535  mov     [rbp+var_10], rsi
0x180024539  mov     [rsp+78h+var_48], rax
0x18002453e  lea     rax, [rbp+arg_0]
0x180024542  mov     [rsp+78h+var_50], rax
0x180024547  lea     rax, [rbp+arg_18]
0x18002454b  mov     [rsp+78h+var_58], rax
0x180024550  mov     [rbp+arg_0], r8d
0x180024554  mov     dword ptr [rbp+arg_18], r9d
0x180024558  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18002455d  test    r12, r12
0x180024560  jnz     short loc_180024575
0x180024562  mov     rdx, r14; unsigned __int16 *
0x180024565  mov     rcx, rdi; this
0x180024568  call    ?SetCompanyName@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetCompanyName(ushort const *)
0x18002456d  mov     rcx, r14; Block
0x180024570  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024575  test    r15, r15
0x180024578  jnz     short loc_18002458D
0x18002457a  mov     rdx, rsi; unsigned __int16 *
0x18002457d  mov     rcx, rdi; this
0x180024580  call    ?SetVersionNumber@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetVersionNumber(ushort const *)
0x180024585  mov     rcx, rsi; Block
0x180024588  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002458d  add     rsp, 78h
0x180024591  pop     r15
0x180024593  pop     r14
0x180024595  pop     r13
0x180024597  pop     r12
0x180024599  pop     rdi
0x18002459a  pop     rsi
0x18002459b  pop     rbx
0x18002459c  pop     rbp
0x18002459d  retn
```
