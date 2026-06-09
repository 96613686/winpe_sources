# CCredentialGroup::PickServerCredential(CCipherSuiteInfo *,CEccCurveInfo *,ulong,uchar,CTlsSignatureSuiteList const *,_TLS_PARAMETERS *,ulong,_UNICODE_STRING *,uchar,CSessionCacheServerItem *,CSslCredential * *)

- ea: `0x180031110`
- end: `0x1800313c3`
- name: `?PickServerCredential@CCredentialGroup@@QEAAKPEAVCCipherSuiteInfo@@PEAVCEccCurveInfo@@KEPEBVCTlsSignatureSuiteList@@PEAU_TLS_PARAMETERS@@KPEAU_UNICODE_STRING@@EPEAVCSessionCacheServerItem@@PEAPEAVCSslCredential@@@Z`
- size: `691`
- prototype: `unsigned int __usercall@<eax>(CCredentialGroup *__hidden this@<rcx>, struct CCipherSuiteInfo *@<rdx>, struct CEccCurveInfo *@<r8>, unsigned int@<r9d>, char, const struct CTlsSignatureSuiteList *, struct _TLS_PARAMETERS *, unsigned int, struct _UNICODE_STRING *, unsigned __int8, struct CSessionCacheServerItem *, struct CSslCredential **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030c60`

## callees

- `0x180031110`
- `0x1800313cc`
- `0x180057c8c`
- `0x180058bbc`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18003132b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18003132b`
- `ntdll!RtlReleaseResource` at `0x180031282`
- `ntdll!RtlReleaseResource` at `0x18003128d`
- `ntdll!RtlReleaseResource` at `0x180031282`
- `ntdll!RtlReleaseResource` at `0x18003128d`
- `ntdll!RtlAcquireResourceShared` at `0x180031194`
- `ntdll!RtlAcquireResourceShared` at `0x1800312dd`
- `ntdll!RtlAcquireResourceShared` at `0x180031194`
- `ntdll!RtlAcquireResourceShared` at `0x1800312dd`

## pseudocode

```c
int __fastcall CCredentialGroup::PickServerCredential(
        CCredentialGroup *this,
        struct CCipherSuiteInfo *a2,
        struct CEccCurveInfo *a3,
        unsigned int a4,
        char a5,
        const struct CTlsSignatureSuiteList *a6,
        struct _TLS_PARAMETERS *a7,
        unsigned int a8,
        struct _UNICODE_STRING *a9,
        unsigned __int8 a10,
        struct CSessionCacheServerItem *a11,
        struct CSslCredential **a12)
{
  struct CSslCredential **v12; // rbx
  int v17; // esi
  struct CSslCredential *v18; // r13
  struct CSessionCacheServerItem *v19; // rbp
  int v20; // r8d
  CCredentialGroup *v21; // rax
  CCredentialGroup *v22; // rcx
  const void *v23; // rbp
  struct CSslCredential *v24; // rdi
  CCredentialGroup *v25; // rbx
  char *v26; // rcx
  int IsServerCredApplicable; // eax
  char v28; // al
  struct CSslCredential *v29; // rax
  int result; // eax
  __int64 v31; // rcx
  int v32; // [rsp+40h] [rbp-68h]
  int v33; // [rsp+50h] [rbp-58h]
  void *Source1; // [rsp+58h] [rbp-50h]
  char *Source1a; // [rsp+58h] [rbp-50h]
  struct CSslCredential *v36; // [rsp+60h] [rbp-48h]
  CCredentialGroup *v37; // [rsp+60h] [rbp-48h]
  struct _RTL_RESOURCE *Resource; // [rsp+70h] [rbp-38h]

  v12 = a12;
  if ( !a12 )
    return 87;
  *a12 = 0;
  if ( !*((_DWORD *)this + 23) )
    return -2146893007;
  if ( (*((_BYTE *)this + 220) & 0x40) == 0 )
    goto LABEL_4;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids);
  result = CCredentialGroup::CheckForCredentialRenewal(this);
  if ( !result )
  {
LABEL_4:
    v36 = 0;
    Source1 = 0;
    v17 = -2146893007;
    v33 = 0;
    v18 = 0;
    Resource = (struct _RTL_RESOURCE *)((char *)this + 112);
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 112), 1u);
    v19 = a11;
    if ( a11
      && (RtlAcquireResourceShared((PRTL_RESOURCE)(*((_QWORD *)a11 + 5) + 80LL), 1u),
          (v31 = *(_QWORD *)(*((_QWORD *)a11 + 20) + 232LL)) != 0) )
    {
      v20 = 20;
      Source1 = (void *)(v31 + 40);
      v33 = 20;
    }
    else
    {
      v20 = 0;
    }
    v21 = (CCredentialGroup *)*((_QWORD *)this + 12);
    v22 = (CCredentialGroup *)((char *)this + 96);
    if ( v21 == (CCredentialGroup *)((char *)this + 96) )
      goto LABEL_13;
    v23 = Source1;
    v24 = 0;
    v25 = v22;
    while ( 1 )
    {
      v26 = (char *)v21 - 8;
      v21 = *(CCredentialGroup **)v21;
      v37 = v21;
      Source1a = v26;
      if ( !v23 )
        goto LABEL_9;
      if ( v26 == (char *)-40LL || v20 != 20 )
        goto LABEL_28;
      if ( RtlCompareMemory(v23, v26 + 40, 0x14u) == 20 )
        break;
LABEL_27:
      v21 = v37;
LABEL_28:
      v20 = v33;
      if ( v21 == v25 )
        goto LABEL_12;
    }
    v26 = Source1a;
LABEL_9:
    LOBYTE(v32) = a10;
    IsServerCredApplicable = CSslCredential::IsServerCredApplicable(v26, a2, a3, a4, a6, a7, a8, a9, v32);
    if ( IsServerCredApplicable == 1 )
    {
      v28 = Source1a[80];
      if ( !v18 || v28 != a5 )
      {
        v17 = 0;
        v18 = (struct CSslCredential *)Source1a;
        if ( v28 != a5 )
        {
LABEL_12:
          v12 = a12;
          v19 = a11;
          v36 = v24;
LABEL_13:
          if ( v19 )
            RtlReleaseResource((PRTL_RESOURCE)(*((_QWORD *)v19 + 5) + 80LL));
          RtlReleaseResource(Resource);
          v29 = v36;
          if ( v18 )
            v29 = v18;
          *v12 = v29;
          return v17;
        }
      }
    }
    else if ( IsServerCredApplicable == 2 && !v24 )
    {
      v24 = (struct CSslCredential *)Source1a;
    }
    goto LABEL_27;
  }
  return result;
}

```

## disassembly

```asm
0x180031110  push    rbx
0x180031112  push    rdi
0x180031113  push    r12
0x180031115  push    r14
0x180031117  push    r15
0x180031119  sub     rsp, 80h
0x180031120  mov     rbx, [rsp+0A8h+arg_58]
0x180031128  mov     r14d, r9d
0x18003112b  mov     r15, r8
0x18003112e  mov     r12, rdx
0x180031131  mov     rdi, rcx
0x180031134  test    rbx, rbx
0x180031137  jz      loc_18003135E
0x18003113d  xor     eax, eax
0x18003113f  mov     [rsp+0A8h+arg_8], rsi
0x180031147  mov     [rbx], rax
0x18003114a  cmp     [rcx+5Ch], eax
0x18003114d  jz      loc_1800312CC
0x180031153  test    byte ptr [rcx+0DCh], 40h
0x18003115a  jnz     loc_18003137E
0x180031160  mov     [rsp+0A8h+var_48], rax
0x180031165  mov     dl, 1; Wait
0x180031167  mov     [rsp+0A8h+Source1], rax
0x18003116c  mov     esi, 80090331h
0x180031171  mov     [rsp+0A8h+var_58], eax
0x180031175  mov     [rsp+0A8h+arg_0], rbp
0x18003117d  mov     [rsp+0A8h+arg_10], r13
0x180031185  mov     r13, rax
0x180031188  lea     rax, [rdi+70h]
0x18003118c  mov     rcx, rax; Resource
0x18003118f  mov     [rsp+0A8h+Resource], rax
0x180031194  call    cs:__imp_RtlAcquireResourceShared
0x18003119a  mov     rbp, [rsp+0A8h+arg_50]
0x1800311a2  test    rbp, rbp
0x1800311a5  jnz     loc_1800312D3
0x1800311ab  mov     r8d, r13d
0x1800311ae  mov     rax, [rdi+60h]
0x1800311b2  lea     rcx, [rdi+60h]
0x1800311b6  cmp     rax, rcx
0x1800311b9  jz      loc_180031275
0x1800311bf  mov     rbp, [rsp+0A8h+Source1]
0x1800311c4  mov     rdi, r13
0x1800311c7  mov     rbx, rcx
0x1800311ca  lea     rcx, [rax-8]
0x1800311ce  mov     rax, [rax]
0x1800311d1  mov     [rsp+0A8h+var_48], rax
0x1800311d6  mov     [rsp+0A8h+Source1], rcx
0x1800311db  test    rbp, rbp
0x1800311de  jnz     loc_180031313
0x1800311e4  movzx   eax, [rsp+0A8h+arg_48]
0x1800311ec  mov     r9d, r14d
0x1800311ef  mov     byte ptr [rsp+0A8h+var_68], al
0x1800311f3  mov     r8, r15
0x1800311f6  mov     rax, [rsp+0A8h+arg_40]
0x1800311fe  mov     rdx, r12
0x180031201  mov     [rsp+0A8h+var_70], rax
0x180031206  mov     eax, [rsp+0A8h+arg_38]
0x18003120d  mov     [rsp+0A8h+var_78], eax
0x180031211  mov     rax, [rsp+0A8h+arg_30]
0x180031219  mov     [rsp+0A8h+var_80], rax
0x18003121e  mov     rax, [rsp+0A8h+arg_28]
0x180031226  mov     [rsp+0A8h+var_88], rax
0x18003122b  call    ?IsServerCredApplicable@CSslCredential@@QEAA?AW4eServerCredApplicable@1@PEAVCCipherSuiteInfo@@PEAVCEccCurveInfo@@KPEBVCTlsSignatureSuiteList@@PEAU_TLS_PARAMETERS@@KPEAU_UNICODE_STRING@@E@Z; CSslCredential::IsServerCredApplicable(CCipherSuiteInfo *,CEccCurveInfo *,ulong,CTlsSignatureSuiteList const *,_TLS_PARAMETERS *,ulong,_UNICODE_STRING *,uchar)
0x180031230  cmp     eax, 1
0x180031233  jnz     loc_180031341
0x180031239  mov     rcx, [rsp+0A8h+Source1]
0x18003123e  movzx   edx, [rsp+0A8h+arg_20]
0x180031246  movzx   eax, byte ptr [rcx+50h]
0x18003124a  test    r13, r13
0x18003124d  jnz     loc_1800313BA
0x180031253  xor     esi, esi
0x180031255  mov     r13, rcx
0x180031258  cmp     al, dl
0x18003125a  jz      loc_180031346
0x180031260  mov     rbx, [rsp+0A8h+arg_58]
0x180031268  mov     rbp, [rsp+0A8h+arg_50]
0x180031270  mov     [rsp+0A8h+var_48], rdi
0x180031275  test    rbp, rbp
0x180031278  jz      short loc_180031288
0x18003127a  mov     rcx, [rbp+28h]
0x18003127e  add     rcx, 50h ; 'P'; Resource
0x180031282  call    cs:__imp_RtlReleaseResource
0x180031288  mov     rcx, [rsp+0A8h+Resource]; Resource
0x18003128d  call    cs:__imp_RtlReleaseResource
0x180031293  mov     rax, [rsp+0A8h+var_48]
0x180031298  test    r13, r13
0x18003129b  mov     rbp, [rsp+0A8h+arg_0]
0x1800312a3  cmovnz  rax, r13
0x1800312a7  mov     r13, [rsp+0A8h+arg_10]
0x1800312af  mov     [rbx], rax
0x1800312b2  mov     eax, esi
0x1800312b4  mov     rsi, [rsp+0A8h+arg_8]
0x1800312bc  add     rsp, 80h
0x1800312c3  pop     r15
0x1800312c5  pop     r14
0x1800312c7  pop     r12
0x1800312c9  pop     rdi
0x1800312ca  pop     rbx
0x1800312cb  retn
0x1800312cc  mov     eax, 80090331h
0x1800312d1  jmp     short loc_1800312B4
0x1800312d3  mov     rcx, [rbp+28h]
0x1800312d7  mov     dl, 1; Wait
0x1800312d9  add     rcx, 50h ; 'P'; Resource
0x1800312dd  call    cs:__imp_RtlAcquireResourceShared
0x1800312e3  mov     rax, [rbp+0A0h]
0x1800312ea  mov     rcx, [rax+0E8h]
0x1800312f1  test    rcx, rcx
0x1800312f4  jz      loc_1800311AB
0x1800312fa  add     rcx, 28h ; '('
0x1800312fe  mov     r8d, 14h
0x180031304  mov     [rsp+0A8h+Source1], rcx
0x180031309  mov     [rsp+0A8h+var_58], r8d
0x18003130e  jmp     loc_1800311AE
0x180031313  lea     rdx, [rcx+28h]; Source2
0x180031317  test    rdx, rdx
0x18003131a  jz      short loc_18003134B
0x18003131c  cmp     r8d, 14h
0x180031320  jnz     short loc_18003134B
0x180031322  mov     r8d, 14h; Length
0x180031328  mov     rcx, rbp; Source1
0x18003132b  call    cs:__imp_RtlCompareMemory
0x180031331  cmp     rax, 14h
0x180031335  jnz     short loc_180031346
0x180031337  mov     rcx, [rsp+0A8h+Source1]
0x18003133c  jmp     loc_1800311E4
0x180031341  cmp     eax, 2
0x180031344  jz      short loc_180031373
0x180031346  mov     rax, [rsp+0A8h+var_48]
0x18003134b  mov     r8d, [rsp+0A8h+var_58]
0x180031350  cmp     rax, rbx
0x180031353  jz      loc_180031260
0x180031359  jmp     loc_1800311CA
0x18003135e  mov     eax, 57h ; 'W'
0x180031363  add     rsp, 80h
0x18003136a  pop     r15
0x18003136c  pop     r14
0x18003136e  pop     r12
0x180031370  pop     rdi
0x180031371  pop     rbx
0x180031372  retn
0x180031373  test    rdi, rdi
0x180031376  cmovz   rdi, [rsp+0A8h+Source1]
0x18003137c  jmp     short loc_180031346
0x18003137e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031385  lea     rax, WPP_GLOBAL_Control
0x18003138c  cmp     rcx, rax
0x18003138f  jz      loc_18008E000
0x180031395  test    byte ptr [rcx+1Ch], 4
0x180031399  jz      loc_18008E000
0x18003139f  mov     rcx, [rcx+10h]
0x1800313a3  lea     r8, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids
0x1800313aa  mov     edx, 25h ; '%'
0x1800313af  call    WPP_SF_
0x1800313b4  nop
0x1800313b5  jmp     loc_18008E000
0x1800313ba  cmp     al, dl
0x1800313bc  jz      short loc_180031346
0x1800313be  jmp     loc_180031253
0x18008e000  mov     rcx, rdi; this
0x18008e003  call    ?CheckForCredentialRenewal@CCredentialGroup@@AEAAKXZ; CCredentialGroup::CheckForCredentialRenewal(void)
0x18008e008  test    eax, eax
0x18008e00a  jnz     loc_1800312B4
0x18008e010  xor     eax, eax
0x18008e012  jmp     loc_180031160
```
