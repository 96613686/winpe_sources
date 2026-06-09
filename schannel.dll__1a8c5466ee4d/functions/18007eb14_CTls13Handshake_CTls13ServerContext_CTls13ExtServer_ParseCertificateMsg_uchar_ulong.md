# CTls13Handshake<CTls13ServerContext,CTls13ExtServer>::ParseCertificateMsg(uchar *,ulong)

- ea: `0x18007eb14`
- end: `0x18007ef51`
- name: `?ParseCertificateMsg@?$CTls13Handshake@VCTls13ServerContext@@VCTls13ExtServer@@@@QEAAKPEAEK@Z`
- size: `1085`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, int, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180057400`

## callees

- `0x180014240`
- `0x18001e7e0`
- `0x1800214f0`
- `0x180021eb0`
- `0x18003cfa0`
- `0x180057c8c`
- `0x1800597b0`
- `0x18007e8e8`
- `0x18007eb14`
- `0x180088a54`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18007ec0c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18007ec0c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007edda`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007edda`
- `ntdll!RtlReleaseResource` at `0x18007ee23`
- `ntdll!RtlReleaseResource` at `0x18007ee23`
- `CRYPT32!CertFreeCertificateContext` at `0x18007ee15`
- `CRYPT32!CertFreeCertificateContext` at `0x18007ee15`

## pseudocode

```c
__int64 __fastcall CTls13Handshake<CTls13ServerContext,CTls13ExtServer>::ParseCertificateMsg(
        __int64 a1,
        unsigned __int8 *a2,
        int a3,
        __int64 a4)
{
  __int64 v5; // rcx
  unsigned int v7; // r13d
  __int64 v8; // rdx
  unsigned int v9; // r15d
  __int64 v10; // r14
  char *v11; // r15
  unsigned int v12; // esi
  __int64 v13; // rax
  const void *v14; // rdx
  char *v15; // rdx
  unsigned int v16; // r12d
  int v17; // r8d
  __int64 v18; // rax
  unsigned __int8 *v19; // rdx
  int v20; // r8d
  unsigned int i; // ebx
  unsigned int v22; // ebx
  __int64 v23; // rsi
  __int64 v24; // r14
  unsigned __int8 *v25; // r13
  unsigned int v26; // ebx
  unsigned int v27; // ebx
  __int64 v28; // rsi
  unsigned __int8 *v29; // r14
  unsigned int v30; // eax
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rsi
  __int64 v34; // r14
  __int64 v35; // rbx
  void *v36; // rcx
  void *v37; // rcx
  const CERT_CONTEXT *v38; // rcx
  __int64 v39; // r10
  __int64 v40; // r10
  _DWORD *v41; // rax
  char *v42; // rbx
  char *v43; // rsi
  int v44; // eax
  int v45; // r14d
  char *v46; // rsi
  __int64 v47; // r14
  char *v48; // rbx
  __int64 v49; // r8
  unsigned int v50; // [rsp+40h] [rbp-39h]
  int v51; // [rsp+44h] [rbp-35h]
  __int64 v52; // [rsp+48h] [rbp-31h] BYREF
  __int64 v53; // [rsp+50h] [rbp-29h] BYREF
  _DWORD *v54; // [rsp+58h] [rbp-21h]
  char *v55; // [rsp+60h] [rbp-19h]
  __int64 v56; // [rsp+68h] [rbp-11h]
  __int16 v57; // [rsp+70h] [rbp-9h] BYREF
  __int128 v58; // [rsp+72h] [rbp-7h]
  __int128 v59; // [rsp+82h] [rbp+9h]
  __int16 v60; // [rsp+92h] [rbp+19h]

  if ( !a2 || !a3 )
    return 87;
  v5 = *(_QWORD *)(a1 + 8);
  v56 = *(_QWORD *)(v5 + 112);
  if ( !v56 )
    return 1359;
  v7 = 0;
  v54 = 0;
  v50 = 0;
  v53 = 0;
  v52 = 0;
  v57 = 0;
  v60 = 0;
  v58 = 0;
  v59 = 0;
  v10 = *a2;
  v11 = (char *)(a2 + 1);
  v12 = a3 - 1;
  if ( (_BYTE)v10 )
  {
    if ( v12 < (unsigned int)v10 )
      goto LABEL_6;
    if ( (*(_DWORD *)(v5 + 88) & 0x40051555) == 0 )
      goto LABEL_6;
    if ( *(_DWORD *)(v5 + 92) != 78 )
      goto LABEL_6;
    v13 = *(unsigned __int8 *)(v5 + 2952);
    if ( (_BYTE)v10 != (_BYTE)v13 )
      goto LABEL_6;
    v14 = *(const void **)(v5 + 2944);
    if ( !v14 )
    {
      v9 = -2146893052;
      goto LABEL_43;
    }
    if ( RtlCompareMemory(v11, v14, *(unsigned __int8 *)(v5 + 2952)) != v13 )
    {
LABEL_17:
      v5 = *(_QWORD *)(a1 + 8);
LABEL_6:
      LOBYTE(a4) = 50;
      goto LABEL_7;
    }
    v15 = &v11[v10];
    v12 -= v10;
  }
  else
  {
    v15 = (char *)(a2 + 1);
  }
  if ( v12 < 3 )
    goto LABEL_17;
  v16 = v12 - 3;
  v17 = (unsigned __int8)v15[2] + ((((unsigned __int8)*v15 << 8) + (unsigned __int8)v15[1]) << 8);
  if ( v12 - 3 != v17 )
    goto LABEL_17;
  if ( v17 )
  {
    v19 = (unsigned __int8 *)(v15 + 3);
    v9 = 0;
    v55 = (char *)v19;
    v20 = 0;
    for ( i = v12 - 3; ; i = v27 - v28 )
    {
      v51 = v20;
      if ( !i )
        break;
      if ( i < 3 )
        goto LABEL_17;
      v22 = i - 3;
      v23 = v19[2] + ((v19[1] + (*v19 << 8)) << 8);
      if ( v22 < (unsigned int)v23 )
        goto LABEL_17;
      v24 = (unsigned int)v23;
      if ( ~v7 < (unsigned __int64)(v23 + 4) )
        goto LABEL_17;
      v25 = v19 + 3;
      v9 = CTls13Handshake<CTls13ServerContext,CTls13ExtServer>::ParseCertData(
             a1,
             (int)v19 + 3,
             v23,
             v20,
             (CTlsSignatureSuiteList *)&v57,
             (__int64)&v53,
             (__int64)&v52);
      if ( v9 )
        goto LABEL_42;
      v26 = v22 - v23;
      v50 += v23 + 4;
      if ( v26 < 2 )
      {
        v31 = 2148074248LL;
        LOBYTE(a4) = 50;
        v9 = -2146893048;
        v32 = 250;
        goto LABEL_41;
      }
      v27 = v26 - 2;
      v28 = _byteswap_ushort(*(_WORD *)&v25[v23]);
      if ( v27 < (unsigned int)v28 )
      {
        v31 = 2148074248LL;
        LOBYTE(a4) = 50;
        v9 = -2146893048;
        goto LABEL_40;
      }
      v29 = &v25[v24 + 2];
      LOBYTE(a4) = 11;
      v30 = CTlsExt::ParseTlsExtensions(*(_QWORD *)(a1 + 16), v29, (unsigned int)v28, a4);
      v9 = v30;
      if ( v30 )
      {
        LOBYTE(a4) = 110;
        v31 = v30;
LABEL_40:
        v32 = 253;
LABEL_41:
        CSslContext::SetErrorAndFatalAlert(*(_QWORD *)(a1 + 8), v32, v31, a4);
LABEL_42:
        v7 = v50;
        goto LABEL_43;
      }
      v19 = &v29[v28];
      v7 = v50;
      v20 = v51 + 1;
    }
    v39 = *(_QWORD *)(a1 + 8);
    if ( v39 == -2194 )
    {
      v9 = 1359;
      goto LABEL_43;
    }
    if ( CTlsSignatureSuiteList::IsSupportedSignatureSuiteList(
           (CTlsSignatureSuiteList *)(v39 + 2194),
           (struct CTlsSignatureSuiteList *)&v57) )
    {
      v41 = SPExternalAlloc(v7);
      v54 = v41;
      if ( v41 )
      {
        v42 = (char *)v41;
        if ( v16 )
        {
          v43 = v55;
          do
          {
            v44 = (unsigned __int8)v43[2];
            v45 = ((unsigned __int8)v43[1] + ((unsigned __int8)*v43 << 8)) << 8;
            v46 = v43 + 3;
            v47 = (unsigned int)(v44 + v45);
            *(_DWORD *)v42 = v47;
            v48 = v42 + 4;
            memcpy_0(v48, v46, (unsigned int)v47);
            v42 = &v48[(unsigned int)v47];
            v49 = _byteswap_ushort(*(_WORD *)&v46[v47]);
            v43 = &v46[v47 + 2 + v49];
            v16 += -5 - v49 - v47;
          }
          while ( v16 );
        }
      }
      else
      {
        v9 = 14;
      }
      goto LABEL_43;
    }
    LOBYTE(a4) = 40;
    v8 = 252;
    v5 = v40;
    goto LABEL_8;
  }
  v18 = *(_QWORD *)(a1 + 8);
  if ( (*(_DWORD *)(v18 + 88) & 0x800A2AAA) == 0 )
  {
    *(_BYTE *)(v18 + 2272) = 1;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ca7b144d2da03908b1ea89985908c21d_Traceguids);
    v9 = 0;
    goto LABEL_43;
  }
  LOBYTE(a4) = 42;
  v5 = *(_QWORD *)(a1 + 8);
LABEL_7:
  v8 = 250;
LABEL_8:
  v9 = -2146893048;
  CSslContext::SetErrorAndFatalAlert(v5, v8, 2148074248LL, a4);
LABEL_43:
  v33 = v52;
  v34 = v53;
  v35 = *(_QWORD *)(v56 + 40);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)(v35 + 80), 1u);
  v36 = *(void **)(v35 + 16);
  if ( v36 )
    SPExternalFree(v36);
  v37 = *(void **)(v35 + 32);
  *(_QWORD *)(v35 + 16) = v54;
  *(_DWORD *)(v35 + 24) = v7;
  if ( v37 )
    SPExternalFree(v37);
  v38 = *(const CERT_CONTEXT **)(v35 + 40);
  *(_QWORD *)(v35 + 32) = v34;
  if ( v38 )
    CertFreeCertificateContext(v38);
  *(_QWORD *)(v35 + 40) = v33;
  RtlReleaseResource((PRTL_RESOURCE)(v35 + 80));
  return v9;
}

```

## disassembly

```asm
0x18007eb14  mov     [rsp-8+arg_10], rbx
0x18007eb19  push    rbp
0x18007eb1a  push    rsi
0x18007eb1b  push    rdi
0x18007eb1c  push    r12
0x18007eb1e  push    r13
0x18007eb20  push    r14
0x18007eb22  push    r15
0x18007eb24  lea     rbp, [rsp-27h]
0x18007eb29  sub     rsp, 0A0h
0x18007eb30  mov     rax, cs:__security_cookie
0x18007eb37  xor     rax, rsp
0x18007eb3a  mov     [rbp+57h+var_38], rax
0x18007eb3e  mov     rdi, rcx
0x18007eb41  test    rdx, rdx
0x18007eb44  jz      loc_18007EF25
0x18007eb4a  test    r8d, r8d
0x18007eb4d  jz      loc_18007EF25
0x18007eb53  mov     rcx, [rcx+8]
0x18007eb57  mov     rax, [rcx+70h]
0x18007eb5b  mov     [rbp+57h+var_68], rax
0x18007eb5f  test    rax, rax
0x18007eb62  jnz     short loc_18007EB6E
0x18007eb64  mov     eax, 54Fh
0x18007eb69  jmp     loc_18007EF2A
0x18007eb6e  xor     r13d, r13d
0x18007eb71  mov     [rbp+57h+var_78], 0
0x18007eb79  xor     eax, eax
0x18007eb7b  mov     [rbp+57h+var_90], r13d
0x18007eb7f  mov     [rbp+57h+var_80], r13
0x18007eb83  xorps   xmm0, xmm0
0x18007eb86  mov     [rbp+57h+var_88], r13
0x18007eb8a  mov     [rbp+57h+var_60], ax
0x18007eb8e  mov     [rbp+57h+var_3E], ax
0x18007eb92  movups  [rbp+57h+var_5E], xmm0
0x18007eb96  movups  [rbp+57h+var_4E], xmm0
0x18007eb9a  cmp     r8d, 1
0x18007eb9e  jnb     short loc_18007EBBB
0x18007eba0  mov     r9b, 32h ; '2'
0x18007eba3  mov     edx, 0FAh
0x18007eba8  mov     r8d, 80090308h
0x18007ebae  mov     r15d, r8d
0x18007ebb1  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18007ebb6  jmp     loc_18007EDC4
0x18007ebbb  movzx   r14d, byte ptr [rdx]
0x18007ebbf  lea     r15, [rdx+1]
0x18007ebc3  lea     esi, [r8-1]
0x18007ebc7  test    r14b, r14b
0x18007ebca  jz      short loc_18007EC26
0x18007ebcc  cmp     esi, r14d
0x18007ebcf  jb      short loc_18007EBA0
0x18007ebd1  test    dword ptr [rcx+58h], 40051555h
0x18007ebd8  jbe     short loc_18007EBA0
0x18007ebda  cmp     dword ptr [rcx+5Ch], 4Eh ; 'N'
0x18007ebde  jnz     short loc_18007EBA0
0x18007ebe0  movzx   eax, byte ptr [rcx+0B88h]
0x18007ebe7  cmp     r14b, al
0x18007ebea  jnz     short loc_18007EBA0
0x18007ebec  mov     rdx, [rcx+0B80h]; Source2
0x18007ebf3  test    rdx, rdx
0x18007ebf6  jnz     short loc_18007EC03
0x18007ebf8  mov     r15d, 80090304h
0x18007ebfe  jmp     loc_18007EDC4
0x18007ec03  mov     r8, rax; Length
0x18007ec06  mov     rcx, r15; Source1
0x18007ec09  mov     rbx, rax
0x18007ec0c  call    cs:__imp_RtlCompareMemory
0x18007ec12  cmp     rax, rbx
0x18007ec15  jz      short loc_18007EC1D
0x18007ec17  mov     rcx, [rdi+8]
0x18007ec1b  jmp     short loc_18007EBA0
0x18007ec1d  lea     rdx, [r15+r14]
0x18007ec21  sub     esi, r14d
0x18007ec24  jmp     short loc_18007EC29
0x18007ec26  mov     rdx, r15
0x18007ec29  cmp     esi, 3
0x18007ec2c  jb      short loc_18007EC17
0x18007ec2e  movzx   eax, byte ptr [rdx]
0x18007ec31  lea     r12d, [rsi-3]
0x18007ec35  movzx   r8d, byte ptr [rdx+1]
0x18007ec3a  shl     eax, 8
0x18007ec3d  add     r8d, eax
0x18007ec40  movzx   eax, byte ptr [rdx+2]
0x18007ec44  shl     r8d, 8
0x18007ec48  add     r8d, eax
0x18007ec4b  cmp     r12d, r8d
0x18007ec4e  jnz     short loc_18007EC17
0x18007ec50  test    r8d, r8d
0x18007ec53  jnz     short loc_18007ECAA
0x18007ec55  mov     rax, [rdi+8]
0x18007ec59  test    dword ptr [rax+58h], 800A2AAAh
0x18007ec60  jz      short loc_18007EC6D
0x18007ec62  mov     r9b, 2Ah ; '*'
0x18007ec65  mov     rcx, rax
0x18007ec68  jmp     loc_18007EBA3
0x18007ec6d  mov     byte ptr [rax+8E0h], 1
0x18007ec74  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ec7b  lea     rax, WPP_GLOBAL_Control
0x18007ec82  cmp     rcx, rax
0x18007ec85  jz      short loc_18007ECA2
0x18007ec87  test    byte ptr [rcx+1Ch], 2
0x18007ec8b  jz      short loc_18007ECA2
0x18007ec8d  mov     rcx, [rcx+10h]
0x18007ec91  lea     r8, WPP_ca7b144d2da03908b1ea89985908c21d_Traceguids
0x18007ec98  mov     edx, 10h
0x18007ec9d  call    WPP_SF_
0x18007eca2  xor     r15d, r15d
0x18007eca5  jmp     loc_18007EDC4
0x18007ecaa  add     rdx, 3
0x18007ecae  xor     r15d, r15d
0x18007ecb1  mov     [rbp+57h+var_70], rdx
0x18007ecb5  xor     r8d, r8d
0x18007ecb8  mov     ebx, r12d
0x18007ecbb  mov     [rbp+57h+var_8C], r8d
0x18007ecbf  test    ebx, ebx
0x18007ecc1  jz      loc_18007EE58
0x18007ecc7  cmp     ebx, 3
0x18007ecca  jb      loc_18007EC17
0x18007ecd0  movzx   eax, byte ptr [rdx+1]
0x18007ecd4  add     ebx, 0FFFFFFFDh
0x18007ecd7  movzx   esi, byte ptr [rdx]
0x18007ecda  shl     esi, 8
0x18007ecdd  add     esi, eax
0x18007ecdf  movzx   eax, byte ptr [rdx+2]
0x18007ece3  shl     esi, 8
0x18007ece6  add     esi, eax
0x18007ece8  cmp     ebx, esi
0x18007ecea  jb      loc_18007EC17
0x18007ecf0  mov     eax, r13d
0x18007ecf3  mov     r14d, esi
0x18007ecf6  not     eax
0x18007ecf8  lea     rcx, [rsi+4]
0x18007ecfc  cmp     rax, rcx
0x18007ecff  jb      loc_18007EC17
0x18007ed05  lea     rax, [rbp+57h+var_88]
0x18007ed09  mov     r9d, r8d; int
0x18007ed0c  mov     [rsp+0D0h+var_A0], rax; __int64
0x18007ed11  lea     r13, [rdx+3]
0x18007ed15  lea     rax, [rbp+57h+var_80]
0x18007ed19  mov     r8d, esi; int
0x18007ed1c  mov     [rsp+0D0h+var_A8], rax; __int64
0x18007ed21  mov     rdx, r13; int
0x18007ed24  lea     rax, [rbp+57h+var_60]
0x18007ed28  mov     rcx, rdi; int
0x18007ed2b  mov     [rsp+0D0h+var_B0], rax; CTlsSignatureSuiteList *
0x18007ed30  call    ?ParseCertData@?$CTls13Handshake@VCTls13ServerContext@@VCTls13ExtServer@@@@IEAAKPEAEKKAEAVCTlsSignatureSuiteList@@AEAPEAU_PUBLICKEY@@AEAPEBU_CERT_CONTEXT@@@Z; CTls13Handshake<CTls13ServerContext,CTls13ExtServer>::ParseCertData(uchar *,ulong,ulong,CTlsSignatureSuiteList &,_PUBLICKEY * &,_CERT_CONTEXT const * &)
0x18007ed35  mov     r15d, eax
0x18007ed38  test    eax, eax
0x18007ed3a  jnz     loc_18007EDC0
0x18007ed40  mov     eax, [rbp+57h+var_90]
0x18007ed43  sub     ebx, esi
0x18007ed45  add     eax, 4
0x18007ed48  add     eax, esi
0x18007ed4a  mov     [rbp+57h+var_90], eax
0x18007ed4d  cmp     ebx, 2
0x18007ed50  jb      loc_18007EE42
0x18007ed56  movzx   eax, byte ptr [rsi+r13]
0x18007ed5b  add     ebx, 0FFFFFFFEh
0x18007ed5e  movzx   ecx, byte ptr [rsi+r13+1]
0x18007ed64  shl     ax, 8
0x18007ed68  or      cx, ax
0x18007ed6b  movzx   esi, cx
0x18007ed6e  cmp     ebx, esi
0x18007ed70  jb      loc_18007EE31
0x18007ed76  mov     rcx, [rdi+10h]
0x18007ed7a  add     r14, 2
0x18007ed7e  add     r14, r13
0x18007ed81  mov     r9b, 0Bh
0x18007ed84  mov     rdx, r14
0x18007ed87  mov     r8d, esi
0x18007ed8a  call    ?ParseTlsExtensions@CTlsExt@@QEAAKPEAEKW4eTlsHandshakeType@@@Z; CTlsExt::ParseTlsExtensions(uchar *,ulong,eTlsHandshakeType)
0x18007ed8f  mov     r15d, eax
0x18007ed92  test    eax, eax
0x18007ed94  jnz     short loc_18007EDAC
0x18007ed96  mov     r8d, [rbp+57h+var_8C]
0x18007ed9a  lea     rdx, [r14+rsi]
0x18007ed9e  mov     r13d, [rbp+57h+var_90]
0x18007eda2  inc     r8d
0x18007eda5  sub     ebx, esi
0x18007eda7  jmp     loc_18007ECBB
0x18007edac  mov     r9b, 6Eh ; 'n'
0x18007edaf  mov     r8d, eax
0x18007edb2  mov     edx, 0FDh
0x18007edb7  mov     rcx, [rdi+8]
0x18007edbb  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18007edc0  mov     r13d, [rbp+57h+var_90]
0x18007edc4  mov     rbx, [rbp+57h+var_68]
0x18007edc8  mov     dl, 1; Wait
0x18007edca  mov     rsi, [rbp+57h+var_88]
0x18007edce  mov     r14, [rbp+57h+var_80]
0x18007edd2  mov     rbx, [rbx+28h]
0x18007edd6  lea     rcx, [rbx+50h]; Resource
0x18007edda  call    cs:__imp_RtlAcquireResourceExclusive
0x18007ede0  mov     rcx, [rbx+10h]; void *
0x18007ede4  test    rcx, rcx
0x18007ede7  jz      short loc_18007EDEE
0x18007ede9  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18007edee  mov     rcx, [rbx+20h]; void *
0x18007edf2  mov     rax, [rbp+57h+var_78]
0x18007edf6  mov     [rbx+10h], rax
0x18007edfa  mov     [rbx+18h], r13d
0x18007edfe  test    rcx, rcx
0x18007ee01  jz      short loc_18007EE08
0x18007ee03  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18007ee08  mov     rcx, [rbx+28h]; pCertContext
0x18007ee0c  mov     [rbx+20h], r14
0x18007ee10  test    rcx, rcx
0x18007ee13  jz      short loc_18007EE1B
0x18007ee15  call    cs:__imp_CertFreeCertificateContext
0x18007ee1b  lea     rcx, [rbx+50h]; Resource
0x18007ee1f  mov     [rbx+28h], rsi
0x18007ee23  call    cs:__imp_RtlReleaseResource
0x18007ee29  mov     eax, r15d
0x18007ee2c  jmp     loc_18007EF2A
0x18007ee31  mov     r8d, 80090308h
0x18007ee37  mov     r9b, 32h ; '2'
0x18007ee3a  mov     r15d, r8d
0x18007ee3d  jmp     loc_18007EDB2
0x18007ee42  mov     r8d, 80090308h
0x18007ee48  mov     r9b, 32h ; '2'
0x18007ee4b  mov     r15d, r8d
0x18007ee4e  mov     edx, 0FAh
0x18007ee53  jmp     loc_18007EDB7
0x18007ee58  mov     r10, [rdi+8]
0x18007ee5c  lea     rcx, [r10+892h]; this
0x18007ee63  test    rcx, rcx
0x18007ee66  jnz     short loc_18007EE73
0x18007ee68  mov     r15d, 54Fh
0x18007ee6e  jmp     loc_18007EDC4
0x18007ee73  lea     rdx, [rbp+57h+var_60]; struct CTlsSignatureSuiteList *
0x18007ee77  call    ?IsSupportedSignatureSuiteList@CTlsSignatureSuiteList@@QEBAEPEAV1@@Z; CTlsSignatureSuiteList::IsSupportedSignatureSuiteList(CTlsSignatureSuiteList *)
0x18007ee7c  test    al, al
0x18007ee7e  jnz     short loc_18007EE90
0x18007ee80  mov     r9b, 28h ; '('
0x18007ee83  mov     edx, 0FCh
0x18007ee88  mov     rcx, r10
0x18007ee8b  jmp     loc_18007EBA8
0x18007ee90  mov     ecx, r13d; uBytes
0x18007ee93  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18007ee98  mov     [rbp+57h+var_78], rax
0x18007ee9c  test    rax, rax
0x18007ee9f  jnz     short loc_18007EEAA
0x18007eea1  lea     r15d, [rax+0Eh]
0x18007eea5  jmp     loc_18007EDC4
0x18007eeaa  mov     rbx, rax
0x18007eead  test    r12d, r12d
0x18007eeb0  jz      loc_18007EDC4
0x18007eeb6  mov     rsi, [rbp+57h+var_70]
0x18007eeba  movzx   eax, byte ptr [rsi+1]
0x18007eebe  movzx   r14d, byte ptr [rsi]
0x18007eec2  shl     r14d, 8
0x18007eec6  add     r14d, eax
0x18007eec9  movzx   eax, byte ptr [rsi+2]
0x18007eecd  shl     r14d, 8
0x18007eed1  add     rsi, 3
0x18007eed5  add     r14d, eax
0x18007eed8  mov     rdx, rsi; Src
0x18007eedb  mov     [rbx], r14d
0x18007eede  add     rbx, 4
0x18007eee2  mov     rcx, rbx; void *
0x18007eee5  mov     r8d, r14d; Size
0x18007eee8  mov     edi, r14d
0x18007eeeb  call    memcpy_0
0x18007eef0  lea     rdx, [r14+rsi]
0x18007eef4  add     rbx, rdi
0x18007eef7  movzx   eax, byte ptr [rdx+1]
0x18007eefb  movzx   ecx, byte ptr [rdx]
0x18007eefe  shl     cx, 8
0x18007ef02  or      cx, ax
0x18007ef05  mov     eax, 0FFFFFFFBh
0x18007ef0a  movzx   r8d, cx
0x18007ef0e  sub     eax, r8d
0x18007ef11  sub     eax, r14d
0x18007ef14  lea     rsi, [r8+2]
0x18007ef18  add     rsi, rdx
0x18007ef1b  add     r12d, eax
0x18007ef1e  jnz     short loc_18007EEBA
0x18007ef20  jmp     loc_18007EDC4
0x18007ef25  mov     eax, 57h ; 'W'
0x18007ef2a  mov     rcx, [rbp+57h+var_38]
0x18007ef2e  xor     rcx, rsp; StackCookie
0x18007ef31  call    __security_check_cookie
0x18007ef36  mov     rbx, [rsp+0D0h+arg_10]
0x18007ef3e  add     rsp, 0A0h
0x18007ef45  pop     r15
0x18007ef47  pop     r14
0x18007ef49  pop     r13
0x18007ef4b  pop     r12
0x18007ef4d  pop     rdi
0x18007ef4e  pop     rsi
0x18007ef4f  pop     rbp
0x18007ef50  retn
```
