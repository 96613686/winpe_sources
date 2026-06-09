# CCipherMill::FindAcceptableCredential(CSsl3TlsServerContext *,CCipherSuiteInfo *,uchar,_UNICODE_STRING *,uchar,CSslCredential * *)

- ea: `0x180030c60`
- end: `0x18003110a`
- name: `?FindAcceptableCredential@CCipherMill@@AEAAKPEAVCSsl3TlsServerContext@@PEAVCCipherSuiteInfo@@EPEAU_UNICODE_STRING@@EPEAPEAVCSslCredential@@@Z`
- size: `1194`
- prototype: `unsigned int(CCipherMill *__hidden this, struct CSsl3TlsServerContext *, struct CCipherSuiteInfo *, unsigned __int8, struct _UNICODE_STRING *, unsigned __int8, struct CSslCredential **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800743c8`

## callees

- `0x180021da8`
- `0x180030c60`
- `0x180031110`
- `0x1800313cc`
- `0x180057c8c`
- `0x180058bbc`
- `0x18007c830`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180030f7a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180030f7a`
- `ntdll!RtlReleaseResource` at `0x180030e89`
- `ntdll!RtlReleaseResource` at `0x180030e97`
- `ntdll!RtlReleaseResource` at `0x180030e89`
- `ntdll!RtlReleaseResource` at `0x180030e97`
- `ntdll!RtlAcquireResourceShared` at `0x180030dac`
- `ntdll!RtlAcquireResourceShared` at `0x180030f2c`
- `ntdll!RtlAcquireResourceShared` at `0x180030dac`
- `ntdll!RtlAcquireResourceShared` at `0x180030f2c`

## pseudocode

```c
__int64 __fastcall CCipherMill::FindAcceptableCredential(
        CCipherMill *this,
        struct CSsl3TlsServerContext *a2,
        struct CCipherSuiteInfo *a3,
        char a4,
        struct _UNICODE_STRING *a5,
        unsigned __int8 a6,
        struct CSslCredential **a7)
{
  struct CSslCredential **v9; // r14
  int v10; // eax
  __int64 v11; // rbp
  struct CSslCredential *v12; // rdi
  char v13; // si
  const struct CTlsSignatureSuiteList *v14; // r12
  bool v15; // zf
  __int64 v16; // rsi
  struct CSessionCacheServerItem *v17; // rbx
  unsigned int v18; // esi
  struct CSslCredential *v19; // r13
  int v20; // edx
  const void *v21; // r9
  struct CSslCredential *v22; // rax
  struct CSslCredential *v23; // rbp
  char *v24; // r14
  unsigned int v25; // ebx
  char *v26; // rcx
  int IsServerCredApplicable; // eax
  char v28; // dl
  char v29; // al
  __int64 v31; // r9
  const void *v32; // rcx
  unsigned int *v33; // rdx
  unsigned __int64 v34; // r8
  struct CSslCredential *v35; // r9
  struct CSslCredential *v36; // rax
  unsigned int v37; // eax
  const struct CTlsSignatureSuiteList *v38; // r10
  unsigned int v39; // r8d
  CCredentialGroup *v40; // rcx
  unsigned int v41; // r9d
  int v42; // eax
  struct CSslCredential *v43; // rax
  char v44; // [rsp+20h] [rbp-C8h]
  struct _TLS_PARAMETERS *v45; // [rsp+30h] [rbp-B8h]
  int v46; // [rsp+40h] [rbp-A8h]
  struct CSslCredential *v47; // [rsp+60h] [rbp-88h]
  const void *v48; // [rsp+68h] [rbp-80h]
  struct CSessionCacheServerItem *v49; // [rsp+70h] [rbp-78h] BYREF
  char *v50; // [rsp+78h] [rbp-70h]
  struct CSslCredential *v51; // [rsp+80h] [rbp-68h]
  int v52; // [rsp+88h] [rbp-60h]
  __int64 v53; // [rsp+90h] [rbp-58h]
  struct CSessionCacheServerItem *v54; // [rsp+98h] [rbp-50h]
  PRTL_RESOURCE Resource; // [rsp+A0h] [rbp-48h]
  int v56; // [rsp+F0h] [rbp+8h]
  struct CEccCurveInfo *v57; // [rsp+F0h] [rbp+8h]
  struct CSslCredential *v58; // [rsp+F8h] [rbp+10h] BYREF

  if ( a2 )
  {
    if ( a3 )
    {
      v9 = a7;
      if ( a7 )
      {
        v10 = *((_DWORD *)a3 + 13);
        if ( v10 == 3 || *((_DWORD *)a2 + 22) == 4096 )
        {
          v11 = *((_QWORD *)a2 + 13);
          v12 = 0;
          v47 = 0;
          v13 = 1;
          v49 = 0;
          *a7 = 0;
          if ( v10 == 3 && !*(_BYTE *)(v11 + 972) )
          {
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_09dceeee5ffe36f0dedb0b1d6c80af61_Traceguids);
            }
            return (unsigned int)-2146893007;
          }
        }
        else
        {
          v11 = *((_QWORD *)a2 + 13);
          v13 = 0;
          v12 = 0;
          v49 = 0;
          *a7 = 0;
          v47 = 0;
        }
        if ( a4 )
        {
          (*(void (__fastcall **)(struct CSsl3TlsServerContext *, struct CSessionCacheServerItem **))(*(_QWORD *)a2 + 248LL))(
            a2,
            &v49);
          if ( !v49 )
            return (unsigned int)-2146893052;
        }
        v14 = (struct CSsl3TlsServerContext *)((char *)a2 + 2230);
        if ( (*((_DWORD *)a2 + 22) & 0x41400) == 0 )
          v14 = 0;
        LODWORD(v58) = *((_DWORD *)a2 + 22);
        if ( *(_BYTE *)(v11 + 972) && v13 )
        {
          v33 = (unsigned int *)*((_QWORD *)a3 + 106);
          v51 = (struct CSslCredential *)v33;
          if ( !v33 )
            return (unsigned int)-2146893052;
          v34 = *(_QWORD *)v33;
          v35 = 0;
          v18 = -2146893007;
          while ( 1 )
          {
            v57 = (struct CEccCurveInfo *)v34;
            if ( v34 >= *(_QWORD *)v33 + 780 * (unsigned __int64)v33[2] )
              goto LABEL_31;
            v18 = CSsl3TlsServerContext::LookupNamedGroup(a2, *(_DWORD *)(v34 + 772));
            if ( v18 )
              goto LABEL_83;
            v38 = 0;
            v39 = *(_DWORD *)(v11 + 260);
            if ( *((_BYTE *)a2 + 2645) )
              v38 = v14;
            v40 = (CCredentialGroup *)*((_QWORD *)a2 + 13);
            v45 = *(struct _TLS_PARAMETERS **)(v11 + 264);
            v41 = *((_DWORD *)a2 + 22);
            v44 = (*((_DWORD *)a2 + 464) & 0x8000000) != 0;
            v58 = 0;
            v42 = CCredentialGroup::PickServerCredential(v40, a3, v57, v41, v44, v38, v45, v39, a5, a6, v49, &v58);
            v18 = v42;
            if ( !v42 )
            {
              *v9 = v58;
              return v18;
            }
            v35 = v47;
            if ( v42 == -2146893007 && !v47 && (v43 = v58) != 0 )
            {
              if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  58,
                  WPP_09dceeee5ffe36f0dedb0b1d6c80af61_Traceguids,
                  *((unsigned int *)v57 + 193));
                v43 = v58;
              }
              v35 = v43;
              v47 = v43;
            }
            else if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                59,
                WPP_09dceeee5ffe36f0dedb0b1d6c80af61_Traceguids,
                *((unsigned int *)v57 + 193));
LABEL_83:
              v35 = v47;
            }
            v33 = (unsigned int *)v51;
            v34 = (unsigned __int64)v57 + 780;
          }
        }
        if ( !*((_BYTE *)a2 + 2645) )
          v14 = 0;
        if ( !*(_DWORD *)(v11 + 92) )
        {
          v18 = -2146893007;
          goto LABEL_94;
        }
        v15 = (*(_BYTE *)(v11 + 220) & 0x40) == 0;
        v16 = *((_QWORD *)a2 + 232);
        v17 = v49;
        v52 = *(_DWORD *)(v11 + 260);
        v53 = *(_QWORD *)(v11 + 264);
        v54 = v49;
        if ( !v15 )
        {
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids);
          }
          v37 = CCredentialGroup::CheckForCredentialRenewal((CCredentialGroup *)v11);
          if ( v37 )
          {
            v18 = v37;
            goto LABEL_88;
          }
        }
        v51 = 0;
        v48 = 0;
        v50 = (char *)(v16 & 0x8000000);
        v56 = 0;
        v18 = -2146893007;
        Resource = (PRTL_RESOURCE)(v11 + 112);
        v19 = 0;
        RtlAcquireResourceShared((PRTL_RESOURCE)(v11 + 112), 1u);
        if ( v17
          && (RtlAcquireResourceShared((PRTL_RESOURCE)(*((_QWORD *)v17 + 5) + 80LL), 1u),
              (v31 = *(_QWORD *)(*((_QWORD *)v17 + 20) + 232LL)) != 0) )
        {
          v21 = (const void *)(v31 + 40);
          v20 = 20;
          v48 = v21;
          v56 = 20;
        }
        else
        {
          v20 = 0;
          v21 = 0;
        }
        v22 = *(struct CSslCredential **)(v11 + 96);
        v23 = (struct CSslCredential *)(v11 + 96);
        if ( v22 == v23 )
        {
LABEL_25:
          if ( v17 )
            RtlReleaseResource((PRTL_RESOURCE)(*((_QWORD *)v17 + 5) + 80LL));
          RtlReleaseResource(Resource);
          v12 = v51;
          if ( v19 )
            v12 = v19;
          if ( !v18 )
          {
            *v9 = v12;
            return v18;
          }
          v37 = v18;
LABEL_88:
          if ( v37 == -2146893007 && v12 )
          {
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_09dceeee5ffe36f0dedb0b1d6c80af61_Traceguids);
            }
            v35 = v12;
LABEL_58:
            if ( v35 )
            {
              *v9 = v35;
              return (unsigned int)-2146893007;
            }
            return v18;
          }
LABEL_94:
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_09dceeee5ffe36f0dedb0b1d6c80af61_Traceguids);
          }
          v35 = 0;
LABEL_31:
          if ( !v18 )
            return v18;
          goto LABEL_58;
        }
        v24 = v50;
        v25 = (unsigned int)v58;
        while ( 1 )
        {
          v26 = (char *)v22 - 8;
          v22 = *(struct CSslCredential **)v22;
          v58 = v22;
          v50 = v26;
          if ( v21 )
          {
            v32 = v26 + 40;
            if ( !v32 || v20 != 20 )
              goto LABEL_43;
            if ( RtlCompareMemory(v21, v32, 0x14u) != 20 )
              goto LABEL_42;
            v26 = v50;
          }
          LOBYTE(v46) = a6;
          IsServerCredApplicable = CSslCredential::IsServerCredApplicable(v26, a3, 0, v25, v14, v53, v52, a5, v46);
          if ( IsServerCredApplicable == 1 )
          {
            v28 = v50[80];
            if ( !v19 )
            {
              v29 = v24 != 0;
LABEL_23:
              v19 = (struct CSslCredential *)v50;
              v18 = 0;
              if ( v28 != v29 )
                goto LABEL_24;
              goto LABEL_42;
            }
            v29 = v24 != 0;
            if ( v28 != (v24 != 0) )
              goto LABEL_23;
          }
          else if ( IsServerCredApplicable == 2 )
          {
            v36 = v51;
            if ( !v51 )
              v36 = (struct CSslCredential *)v50;
            v51 = v36;
          }
LABEL_42:
          v22 = v58;
          v21 = v48;
LABEL_43:
          v20 = v56;
          if ( v22 == v23 )
          {
LABEL_24:
            v9 = a7;
            v17 = v54;
            goto LABEL_25;
          }
        }
      }
    }
  }
  return 2148074333LL;
}

```

## disassembly

```asm
0x180030c60  mov     rax, rsp
0x180030c63  mov     [rax+8], rcx
0x180030c67  push    rbx
0x180030c68  push    r14
0x180030c6a  push    r15
0x180030c6c  sub     rsp, 0D0h
0x180030c73  mov     r15, r8
0x180030c76  mov     rbx, rdx
0x180030c79  test    rdx, rdx
0x180030c7c  jz      loc_180031066
0x180030c82  test    r8, r8
0x180030c85  jz      loc_180031066
0x180030c8b  mov     r14, [rsp+0E8h+arg_30]
0x180030c93  test    r14, r14
0x180030c96  jz      loc_180031066
0x180030c9c  mov     [rax-20h], rsi
0x180030ca0  mov     [rax+18h], rbp
0x180030ca4  mov     [rax-28h], rdi
0x180030ca8  mov     [rax-38h], r13
0x180030cac  mov     eax, [r8+34h]
0x180030cb0  cmp     eax, 3
0x180030cb3  jz      short loc_180030CC2
0x180030cb5  cmp     dword ptr [rdx+58h], 1000h
0x180030cbc  jnz     loc_180031025
0x180030cc2  mov     rbp, [rdx+68h]
0x180030cc6  xor     edi, edi
0x180030cc8  mov     [rsp+0E8h+var_88], rdi
0x180030ccd  mov     sil, 1
0x180030cd0  mov     [rsp+0E8h+var_78], rdi
0x180030cd5  mov     [r14], rdi
0x180030cd8  cmp     eax, 3
0x180030cdb  jz      loc_180030FF5
0x180030ce1  test    r9b, r9b
0x180030ce4  jnz     loc_180030EF8
0x180030cea  mov     eax, [rbx+58h]
0x180030ced  test    eax, 41400h
0x180030cf2  mov     [rsp+0E8h+var_30], r12
0x180030cfa  lea     r12, [rbx+8B6h]
0x180030d01  cmovz   r12, rdi
0x180030d05  mov     dword ptr [rsp+0E8h+arg_8], eax
0x180030d0c  cmp     byte ptr [rbp+3CCh], 0
0x180030d13  jnz     loc_180030FBB
0x180030d19  cmp     byte ptr [rbx+0A55h], 0
0x180030d20  jz      loc_180031040
0x180030d26  cmp     dword ptr [rbp+5Ch], 0
0x180030d2a  lea     r13, WPP_GLOBAL_Control
0x180030d31  jz      loc_1800310AA
0x180030d37  test    byte ptr [rbp+0DCh], 40h
0x180030d3e  mov     eax, [rbp+104h]
0x180030d44  mov     rsi, [rbx+740h]
0x180030d4b  mov     rbx, [rsp+0E8h+var_78]
0x180030d50  mov     [rsp+0E8h+var_60], eax
0x180030d57  mov     rax, [rbp+108h]
0x180030d5e  mov     [rsp+0E8h+var_58], rax
0x180030d66  mov     [rsp+0E8h+var_50], rbx
0x180030d6e  jnz     loc_1800310B4
0x180030d74  lea     rax, [rbp+70h]
0x180030d78  mov     [rsp+0E8h+var_68], rdi
0x180030d80  and     esi, 8000000h
0x180030d86  mov     [rsp+0E8h+var_80], rdi
0x180030d8b  mov     [rsp+0E8h+var_70], rsi
0x180030d90  mov     rcx, rax; Resource
0x180030d93  mov     dl, 1; Wait
0x180030d95  mov     dword ptr [rsp+0E8h+arg_0], edi
0x180030d9c  mov     esi, 80090331h
0x180030da1  mov     [rsp+0E8h+Resource], rax
0x180030da9  mov     r13, rdi
0x180030dac  call    cs:__imp_RtlAcquireResourceShared
0x180030db2  test    rbx, rbx
0x180030db5  jnz     loc_180030F22
0x180030dbb  mov     edx, edi
0x180030dbd  mov     r9, rdi
0x180030dc0  mov     rax, [rbp+60h]
0x180030dc4  add     rbp, 60h ; '`'
0x180030dc8  cmp     rax, rbp
0x180030dcb  jz      loc_180030E7C
0x180030dd1  mov     r14, [rsp+0E8h+var_70]
0x180030dd6  mov     ebx, dword ptr [rsp+0E8h+arg_8]
0x180030ddd  lea     rcx, [rax-8]
0x180030de1  mov     rax, [rax]
0x180030de4  mov     [rsp+0E8h+arg_8], rax
0x180030dec  mov     [rsp+0E8h+var_70], rcx
0x180030df1  test    r9, r9
0x180030df4  jnz     loc_180030F63
0x180030dfa  movzx   eax, [rsp+0E8h+arg_28]
0x180030e02  mov     r9d, ebx
0x180030e05  mov     byte ptr [rsp+0E8h+var_A8], al
0x180030e09  xor     r8d, r8d
0x180030e0c  mov     rax, [rsp+0E8h+arg_20]
0x180030e14  mov     rdx, r15
0x180030e17  mov     qword ptr [rsp+0E8h+var_B0], rax
0x180030e1c  mov     eax, [rsp+0E8h+var_60]
0x180030e23  mov     dword ptr [rsp+0E8h+var_B8], eax
0x180030e27  mov     rax, [rsp+0E8h+var_58]
0x180030e2f  mov     [rsp+0E8h+var_C0], rax
0x180030e34  mov     qword ptr [rsp+0E8h+var_C8], r12
0x180030e39  call    ?IsServerCredApplicable@CSslCredential@@QEAA?AW4eServerCredApplicable@1@PEAVCCipherSuiteInfo@@PEAVCEccCurveInfo@@KPEBVCTlsSignatureSuiteList@@PEAU_TLS_PARAMETERS@@KPEAU_UNICODE_STRING@@E@Z; CSslCredential::IsServerCredApplicable(CCipherSuiteInfo *,CEccCurveInfo *,ulong,CTlsSignatureSuiteList const *,_TLS_PARAMETERS *,ulong,_UNICODE_STRING *,uchar)
0x180030e3e  cmp     eax, 1
0x180030e41  jnz     loc_180030F90
0x180030e47  mov     rcx, [rsp+0E8h+var_70]
0x180030e4c  movzx   edx, byte ptr [rcx+50h]
0x180030e50  test    r13, r13
0x180030e53  jnz     loc_1800310E9
0x180030e59  test    r14, r14
0x180030e5c  setnz   al
0x180030e5f  mov     r13, rcx
0x180030e62  mov     esi, edi
0x180030e64  cmp     dl, al
0x180030e66  jz      loc_180030F99
0x180030e6c  mov     r14, [rsp+0E8h+arg_30]
0x180030e74  mov     rbx, [rsp+0E8h+var_50]
0x180030e7c  test    rbx, rbx
0x180030e7f  jz      short loc_180030E8F
0x180030e81  mov     rcx, [rbx+28h]
0x180030e85  add     rcx, 50h ; 'P'; Resource
0x180030e89  call    cs:__imp_RtlReleaseResource
0x180030e8f  mov     rcx, [rsp+0E8h+Resource]; Resource
0x180030e97  call    cs:__imp_RtlReleaseResource
0x180030e9d  mov     rdi, [rsp+0E8h+var_68]
0x180030ea5  test    r13, r13
0x180030ea8  cmovnz  rdi, r13
0x180030eac  test    esi, esi
0x180030eae  jnz     loc_1800310FC
0x180030eb4  mov     [r14], rdi
0x180030eb7  jmp     short loc_180030EC1
0x180030eb9  test    esi, esi
0x180030ebb  jnz     loc_180031070
0x180030ec1  mov     r12, [rsp+0E8h+var_30]
0x180030ec9  mov     r13, [rsp+0E8h+var_38]
0x180030ed1  mov     eax, esi
0x180030ed3  mov     rsi, [rsp+0E8h+var_20]
0x180030edb  mov     rdi, [rsp+0E8h+var_28]
0x180030ee3  mov     rbp, [rsp+0E8h+arg_10]
0x180030eeb  add     rsp, 0D0h
0x180030ef2  pop     r15
0x180030ef4  pop     r14
0x180030ef6  pop     rbx
0x180030ef7  retn
0x180030ef8  mov     rax, [rdx]
0x180030efb  mov     rcx, rbx
0x180030efe  lea     rdx, [rsp+0E8h+var_78]
0x180030f03  mov     rax, [rax+0F8h]
0x180030f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f0f  cmp     [rsp+0E8h+var_78], 0
0x180030f15  jnz     loc_180030CEA
0x180030f1b  mov     esi, 80090304h
0x180030f20  jmp     short loc_180030EC9
0x180030f22  mov     rcx, [rbx+28h]
0x180030f26  mov     dl, 1; Wait
0x180030f28  add     rcx, 50h ; 'P'; Resource
0x180030f2c  call    cs:__imp_RtlAcquireResourceShared
0x180030f32  mov     rax, [rbx+0A0h]
0x180030f39  mov     r9, [rax+0E8h]
0x180030f40  test    r9, r9
0x180030f43  jz      loc_180030DBB
0x180030f49  add     r9, 28h ; '('
0x180030f4d  mov     edx, 14h
0x180030f52  mov     [rsp+0E8h+var_80], r9
0x180030f57  mov     dword ptr [rsp+0E8h+arg_0], edx
0x180030f5e  jmp     loc_180030DC0
0x180030f63  add     rcx, 28h ; '('
0x180030f67  jz      short loc_180030FA6
0x180030f69  cmp     edx, 14h
0x180030f6c  jnz     short loc_180030FA6
0x180030f6e  mov     rdx, rcx; Source2
0x180030f71  mov     r8d, 14h; Length
0x180030f77  mov     rcx, r9; Source1
0x180030f7a  call    cs:__imp_RtlCompareMemory
0x180030f80  cmp     rax, 14h
0x180030f84  jnz     short loc_180030F99
0x180030f86  mov     rcx, [rsp+0E8h+var_70]
0x180030f8b  jmp     loc_180030DFA
0x180030f90  cmp     eax, 2
0x180030f93  jz      loc_180031048
0x180030f99  mov     rax, [rsp+0E8h+arg_8]
0x180030fa1  mov     r9, [rsp+0E8h+var_80]
0x180030fa6  mov     edx, dword ptr [rsp+0E8h+arg_0]
0x180030fad  cmp     rax, rbp
0x180030fb0  jz      loc_180030E6C
0x180030fb6  jmp     loc_180030DDD
0x180030fbb  test    sil, sil
0x180030fbe  jz      loc_180030D19
0x180030fc4  mov     rdx, [r15+350h]
0x180030fcb  mov     [rsp+0E8h+var_68], rdx
0x180030fd3  test    rdx, rdx
0x180030fd6  jz      loc_1800310A0
0x180030fdc  mov     r8, [rdx]
0x180030fdf  lea     r13, WPP_GLOBAL_Control
0x180030fe6  mov     r9, [rsp+0E8h+var_88]
0x180030feb  mov     esi, 80090331h
0x180030ff0  jmp     loc_18008DDEA
0x180030ff5  cmp     [rbp+3CCh], dil
0x180030ffc  jnz     loc_180030CE1
0x180031002  mov     rcx, cs:WPP_GLOBAL_Control
0x180031009  lea     r13, WPP_GLOBAL_Control
0x180031010  cmp     rcx, r13
0x180031013  jz      short loc_18003101B
0x180031015  test    byte ptr [rcx+1Ch], 4
0x180031019  jnz     short loc_180031086
0x18003101b  mov     esi, 80090331h
0x180031020  jmp     loc_180030EC9
0x180031025  mov     rbp, [rdx+68h]
0x180031029  xor     sil, sil
0x18003102c  xor     edi, edi
0x18003102e  mov     [rsp+0E8h+var_78], rdi
0x180031033  mov     [r14], rdi
0x180031036  mov     [rsp+0E8h+var_88], rdi
0x18003103b  jmp     loc_180030CE1
0x180031040  mov     r12, rdi
0x180031043  jmp     loc_180030D26
0x180031048  mov     rax, [rsp+0E8h+var_68]
0x180031050  test    rax, rax
0x180031053  cmovz   rax, [rsp+0E8h+var_70]
0x180031059  mov     [rsp+0E8h+var_68], rax
0x180031061  jmp     loc_180030F99
0x180031066  mov     eax, 8009035Dh
0x18003106b  jmp     loc_180030EEB
0x180031070  test    r9, r9
0x180031073  jz      loc_180030EC1
0x180031079  mov     [r14], r9
0x18003107c  mov     esi, 80090331h
0x180031081  jmp     loc_180030EC1
0x180031086  mov     rcx, [rcx+10h]
0x18003108a  lea     r8, WPP_09dceeee5ffe36f0dedb0b1d6c80af61_Traceguids
0x180031091  mov     edx, 37h ; '7'
0x180031096  call    WPP_SF_
0x18003109b  jmp     loc_18003101B
0x1800310a0  mov     esi, 80090304h
0x1800310a5  jmp     loc_180030EC1
0x1800310aa  mov     esi, 80090331h
0x1800310af  jmp     loc_18008DFCF
0x1800310b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800310bb  cmp     rcx, r13
0x1800310be  jz      loc_18008DF82
0x1800310c4  test    byte ptr [rcx+1Ch], 4
0x1800310c8  jz      loc_18008DF82
0x1800310ce  mov     rcx, [rcx+10h]
0x1800310d2  lea     r8, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids
0x1800310d9  mov     edx, 25h ; '%'
0x1800310de  call    WPP_SF_
0x1800310e3  nop
0x1800310e4  jmp     loc_18008DF82
0x1800310e9  test    r14, r14
0x1800310ec  setnz   al
0x1800310ef  cmp     dl, al
0x1800310f1  jz      loc_180030F99
0x1800310f7  jmp     loc_180030E5F
0x1800310fc  mov     eax, esi
0x1800310fe  lea     r13, WPP_GLOBAL_Control
0x180031105  jmp     loc_18008DF94
0x18008ddea  mov     eax, [rdx+8]
0x18008dded  imul    rcx, rax, 30Ch
0x18008ddf4  mov     [rsp+0E8h+arg_0], r8
0x18008ddfc  add     rcx, [rdx]
0x18008ddff  cmp     r8, rcx
0x18008de02  jnb     loc_180030EB9
0x18008de08  mov     edx, [r8+304h]; unsigned int
0x18008de0f  mov     rcx, rbx; this
0x18008de12  call    ?LookupNamedGroup@CSsl3TlsServerContext@@UEAAKK@Z; CSsl3TlsServerContext::LookupNamedGroup(ulong)
0x18008de17  mov     esi, eax
0x18008de19  test    eax, eax
0x18008de1b  jnz     loc_18008DF51
0x18008de21  cmp     [rbx+0A55h], al
0x18008de27  lea     rcx, [rsp+0E8h+arg_8]
0x18008de2f  mov     rdx, [rsp+0E8h+var_78]
0x18008de34  mov     r10, rdi
0x18008de37  mov     r8d, [rbp+104h]
0x18008de3e  cmovnz  r10, r12
0x18008de42  mov     r9, [rbp+108h]
0x18008de49  mov     eax, [rbx+740h]
0x18008de4f  mov     [rsp+0E8h+var_90], rcx; struct CSslCredential **
0x18008de54  movzx   ecx, [rsp+0E8h+arg_28]
0x18008de5c  mov     [rsp+0E8h+var_98], rdx; struct CSessionCacheServerItem *
0x18008de61  mov     rdx, r15; struct CCipherSuiteInfo *
0x18008de64  mov     [rsp+0E8h+var_A0], cl; unsigned __int8
0x18008de68  mov     rcx, [rsp+0E8h+arg_20]
0x18008de70  mov     [rsp+0E8h+var_A8], rcx; struct _UNICODE_STRING *
0x18008de75  mov     rcx, [rbx+68h]; this
0x18008de79  mov     [rsp+0E8h+var_B0], r8d; unsigned int
0x18008de7e  mov     r8, [rsp+0E8h+arg_0]; struct CEccCurveInfo *
0x18008de86  mov     [rsp+0E8h+var_B8], r9; struct _TLS_PARAMETERS *
0x18008de8b  mov     r9d, [rbx+58h]; unsigned int
0x18008de8f  shr     rax, 1Bh
0x18008de93  and     al, 1
0x18008de95  mov     [rsp+0E8h+var_C0], r10; struct CTlsSignatureSuiteList *
0x18008de9a  mov     [rsp+0E8h+var_C8], al; char
0x18008de9e  mov     [rsp+0E8h+arg_8], rdi
0x18008dea6  call    ?PickServerCredential@CCredentialGroup@@QEAAKPEAVCCipherSuiteInfo@@PEAVCEccCurveInfo@@KEPEBVCTlsSignatureSuiteList@@PEAU_TLS_PARAMETERS@@KPEAU_UNICODE_STRING@@EPEAVCSessionCacheServerItem@@PEAPEAVCSslCredential@@@Z; CCredentialGroup::PickServerCredential(CCipherSuiteInfo *,CEccCurveInfo *,ulong,uchar,CTlsSignatureSuiteList const *,_TLS_PARAMETERS *,ulong,_UNICODE_STRING *,uchar,CSessionCacheServerItem *,CSslCredential * *)
0x18008deab  mov     esi, eax
0x18008dead  test    eax, eax
0x18008deaf  jz      loc_18008DF72
0x18008deb5  mov     r9, [rsp+0E8h+var_88]
0x18008deba  cmp     eax, 80090331h
0x18008debf  jnz     short loc_18008DF1B
0x18008dec1  test    r9, r9
0x18008dec4  jnz     short loc_18008DF1B
0x18008dec6  mov     rax, [rsp+0E8h+arg_8]
0x18008dece  test    rax, rax
0x18008ded1  jz      short loc_18008DF1B
0x18008ded3  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
