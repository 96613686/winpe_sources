# CTls13Handshake<CTls13ClientContext,CTls13ExtClient>::ParseCertificateMsg(uchar *,ulong)

- ea: `0x18003bc90`
- end: `0x18003c18a`
- name: `?ParseCertificateMsg@?$CTls13Handshake@VCTls13ClientContext@@VCTls13ExtClient@@@@QEAAKPEAEK@Z`
- size: `1274`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, int, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180050f90`

## callees

- `0x180014240`
- `0x18001e7e0`
- `0x1800214f0`
- `0x180021eb0`
- `0x18003bc90`
- `0x18003c190`
- `0x180057c8c`
- `0x1800597b0`
- `0x180088a54`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18008eeb5`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18008eeb5`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003bfc1`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003bfc1`
- `ntdll!RtlReleaseResource` at `0x18003c01a`
- `ntdll!RtlReleaseResource` at `0x18003c01a`
- `CRYPT32!CertFreeCertificateContext` at `0x18003c17f`
- `CRYPT32!CertFreeCertificateContext` at `0x18003c17f`

## pseudocode

```c
__int64 __fastcall CTls13Handshake<CTls13ClientContext,CTls13ExtClient>::ParseCertificateMsg(
        __int64 a1,
        unsigned __int8 *a2,
        int a3,
        __int64 a4)
{
  __int64 v5; // rcx
  _DWORD *v6; // r12
  unsigned int v7; // r15d
  __int64 v8; // r14
  char *v9; // rbp
  unsigned int v10; // edi
  char *v11; // rdx
  int v12; // r8d
  unsigned int v13; // r14d
  unsigned int v14; // ebx
  unsigned __int8 *v15; // rdx
  unsigned int v16; // ebx
  __int64 v17; // rdi
  __int64 v18; // rbp
  unsigned __int8 *v19; // r13
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  __int64 v22; // rdi
  unsigned __int8 *v23; // rbp
  unsigned int v24; // eax
  __int64 v25; // r10
  unsigned __int16 v26; // dx
  unsigned __int16 v27; // cx
  unsigned __int16 v28; // ax
  unsigned __int16 v29; // cx
  unsigned __int16 v30; // ax
  int v31; // edx
  _DWORD *v32; // rax
  unsigned int v33; // r13d
  char *v34; // rbx
  unsigned __int8 *v35; // rdi
  __int64 v36; // rbp
  char *v37; // rbx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // rsi
  __int64 v43; // rbp
  __int64 v44; // rbx
  void *v45; // rcx
  void *v46; // rcx
  const CERT_CONTEXT *v47; // rcx
  __int64 v49; // rax
  const void *v50; // rdx
  __int64 v51; // rax
  unsigned int v52; // [rsp+48h] [rbp-90h]
  __int64 v53; // [rsp+50h] [rbp-88h] BYREF
  __int64 v54; // [rsp+58h] [rbp-80h] BYREF
  unsigned __int8 *v55; // [rsp+60h] [rbp-78h]
  __int64 v56; // [rsp+68h] [rbp-70h]
  __int16 v57; // [rsp+70h] [rbp-68h] BYREF
  __int128 v58; // [rsp+72h] [rbp-66h]
  __int128 v59; // [rsp+82h] [rbp-56h]
  unsigned __int16 v60; // [rsp+92h] [rbp-46h]

  if ( !a2 || !a3 )
    return 87;
  v5 = *(_QWORD *)(a1 + 8);
  v56 = *(_QWORD *)(v5 + 112);
  if ( !v56 )
    return 1359;
  v6 = 0;
  v58 = 0;
  v7 = 0;
  v54 = 0;
  v53 = 0;
  v59 = 0;
  v57 = 0;
  v60 = 0;
  v8 = *a2;
  v9 = (char *)(a2 + 1);
  v10 = a3 - 1;
  if ( !(_BYTE)v8 )
  {
    v11 = (char *)(a2 + 1);
LABEL_6:
    if ( v10 >= 3 )
    {
      v52 = v10 - 3;
      v12 = (unsigned __int8)v11[2] + (((unsigned __int8)v11[1] + ((unsigned __int8)*v11 << 8)) << 8);
      if ( v10 - 3 == v12 )
      {
        if ( v12 )
        {
          v13 = 0;
          v14 = v10 - 3;
          v15 = (unsigned __int8 *)(v11 + 3);
          v55 = v15;
          while ( v14 )
          {
            if ( v14 < 3 )
              goto LABEL_62;
            v16 = v14 - 3;
            v17 = v15[2] + ((v15[1] + (*v15 << 8)) << 8);
            if ( v16 < (unsigned int)v17 )
              goto LABEL_62;
            v18 = (unsigned int)v17;
            if ( ~v7 < (unsigned __int64)(v17 + 4) )
              goto LABEL_62;
            v19 = v15 + 3;
            v13 = CTls13Handshake<CTls13ClientContext,CTls13ExtClient>::ParseCertData(
                    a1,
                    v15 + 3,
                    v17,
                    (unsigned int)v6,
                    (CTlsSignatureSuiteList *)&v57,
                    (struct _PUBLICKEY **)&v54,
                    (const CERT_CONTEXT **)&v53);
            if ( v13 )
              goto LABEL_37;
            v20 = v16 - v17;
            v7 += v17 + 4;
            if ( v20 < 2 )
            {
LABEL_62:
              v40 = *(_QWORD *)(a1 + 8);
              LOBYTE(a4) = 50;
              v39 = 250;
LABEL_35:
              v13 = -2146893048;
              v41 = 2148074248LL;
LABEL_36:
              CSslContext::SetErrorAndFatalAlert(v40, v39, v41, a4);
LABEL_37:
              v6 = 0;
              goto LABEL_38;
            }
            v21 = v20 - 2;
            v22 = _byteswap_ushort(*(_WORD *)&v19[v17]);
            if ( v21 < (unsigned int)v22 )
            {
              v40 = *(_QWORD *)(a1 + 8);
              LOBYTE(a4) = 50;
              v39 = 253;
              goto LABEL_35;
            }
            v23 = &v19[v18 + 2];
            LOBYTE(a4) = 11;
            v24 = CTlsExt::ParseTlsExtensions(*(_QWORD *)(a1 + 16), v23, (unsigned int)v22, a4);
            v13 = v24;
            if ( v24 )
            {
              v40 = *(_QWORD *)(a1 + 8);
              LOBYTE(a4) = 110;
              v41 = v24;
              v39 = 253;
              goto LABEL_36;
            }
            LODWORD(v6) = (_DWORD)v6 + 1;
            v15 = &v23[v22];
            v14 = v21 - v22;
          }
          v25 = *(_QWORD *)(a1 + 8);
          if ( v25 == -2194 )
          {
            v13 = 1359;
            goto LABEL_37;
          }
          if ( !v57 || !v60 )
            goto LABEL_34;
          v26 = *(_WORD *)(v25 + 2228);
          if ( (v26 & CTlsSignatureSuiteList::RsaSha256Flags) != 0 )
            v27 = CTlsSignatureSuiteList::RsaSha256Flags;
          else
            v27 = 0;
          v28 = CTlsSignatureSuiteList::RsaSha384Flags;
          v29 = v26 | v27;
          if ( (v29 & CTlsSignatureSuiteList::RsaSha384Flags) == 0 )
            v28 = 0;
          v30 = v29 | v28;
          v31 = (v30 & CTlsSignatureSuiteList::RsaSha512Flags) != 0 ? CTlsSignatureSuiteList::RsaSha512Flags : 0;
          if ( (~(v31 | v30) & v60) != 0 )
          {
LABEL_34:
            LOBYTE(a4) = 40;
            v39 = 252;
            v40 = *(_QWORD *)(a1 + 8);
            goto LABEL_35;
          }
          v32 = SPExternalAlloc(v7);
          v6 = v32;
          if ( v32 )
          {
            v33 = v52;
            v34 = (char *)v32;
            if ( v52 )
            {
              v35 = v55;
              do
              {
                v36 = v35[2] + ((v35[1] + (*v35 << 8)) << 8);
                *(_DWORD *)v34 = v36;
                v37 = v34 + 4;
                memcpy_0(v37, v35 + 3, (unsigned int)v36);
                v34 = &v37[(unsigned int)v36];
                v38 = _byteswap_ushort(*(_WORD *)&v35[v36 + 3]);
                v35 += v36 + v38 + 5;
                v33 += -5 - v38 - v36;
              }
              while ( v33 );
            }
          }
          else
          {
            v13 = 14;
          }
        }
        else
        {
          v51 = *(_QWORD *)(a1 + 8);
          if ( (*(_DWORD *)(v51 + 88) & 0x800A2AAA) != 0 )
          {
            v13 = -2146893048;
            LOBYTE(a4) = 42;
            CSslContext::SetErrorAndFatalAlert(*(_QWORD *)(a1 + 8), 250, 2148074248LL, a4);
          }
          else
          {
            *(_BYTE *)(v51 + 2272) = 1;
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ca7b144d2da03908b1ea89985908c21d_Traceguids);
            }
            v13 = 0;
          }
        }
        goto LABEL_38;
      }
    }
    goto LABEL_59;
  }
  if ( v10 < (unsigned int)v8 )
    goto LABEL_52;
  if ( (*(_DWORD *)(v5 + 88) & 0x40051555) == 0 )
    goto LABEL_52;
  if ( *(_DWORD *)(v5 + 92) != 78 )
    goto LABEL_52;
  v49 = *(unsigned __int8 *)(v5 + 3320);
  if ( (_BYTE)v8 != (_BYTE)v49 )
    goto LABEL_52;
  v50 = *(const void **)(v5 + 3312);
  if ( !v50 )
  {
    v13 = -2146893052;
    goto LABEL_38;
  }
  if ( RtlCompareMemory(v9, v50, *(unsigned __int8 *)(v5 + 3320)) == v49 )
  {
    v11 = &v9[v8];
    v10 -= v8;
    goto LABEL_6;
  }
LABEL_59:
  v5 = *(_QWORD *)(a1 + 8);
LABEL_52:
  v13 = -2146893048;
  LOBYTE(a4) = 50;
  CSslContext::SetErrorAndFatalAlert(v5, 250, 2148074248LL, a4);
LABEL_38:
  v42 = v53;
  v43 = v54;
  v44 = *(_QWORD *)(v56 + 40);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)(v44 + 80), 1u);
  v45 = *(void **)(v44 + 16);
  if ( v45 )
    SPExternalFree(v45);
  v46 = *(void **)(v44 + 32);
  *(_QWORD *)(v44 + 16) = v6;
  *(_DWORD *)(v44 + 24) = v7;
  if ( v46 )
    SPExternalFree(v46);
  v47 = *(const CERT_CONTEXT **)(v44 + 40);
  *(_QWORD *)(v44 + 32) = v43;
  if ( v47 )
    CertFreeCertificateContext(v47);
  *(_QWORD *)(v44 + 40) = v42;
  RtlReleaseResource((PRTL_RESOURCE)(v44 + 80));
  return v13;
}

```

## disassembly

```asm
0x18003bc90  mov     r11, rsp
0x18003bc93  push    rsi
0x18003bc94  sub     rsp, 0D0h
0x18003bc9b  mov     rax, cs:__security_cookie
0x18003bca2  xor     rax, rsp
0x18003bca5  mov     [rsp+0D8h+var_40], rax
0x18003bcad  mov     rsi, rcx
0x18003bcb0  test    rdx, rdx
0x18003bcb3  jz      loc_18003C054
0x18003bcb9  test    r8d, r8d
0x18003bcbc  jz      loc_18003C054
0x18003bcc2  mov     rcx, [rcx+8]
0x18003bcc6  mov     [r11-30h], r14
0x18003bcca  mov     rax, [rcx+70h]
0x18003bcce  mov     [rsp+0D8h+var_70], rax
0x18003bcd3  test    rax, rax
0x18003bcd6  jz      loc_18003C05B
0x18003bcdc  mov     [r11+18h], rbx
0x18003bce0  xor     eax, eax
0x18003bce2  mov     [r11-10h], rbp
0x18003bce6  xorps   xmm0, xmm0
0x18003bce9  mov     [r11-18h], rdi
0x18003bced  mov     [r11-20h], r12
0x18003bcf1  xor     r12d, r12d
0x18003bcf4  movups  [rsp+0D8h+var_66], xmm0
0x18003bcf9  mov     [r11-38h], r15
0x18003bcfd  xor     r15d, r15d
0x18003bd00  mov     [rsp+0D8h+var_98], r12
0x18003bd05  mov     [r11-80h], r12
0x18003bd09  mov     [rsp+0D8h+var_88], r12
0x18003bd0e  movups  xmmword ptr [r11-56h], xmm0
0x18003bd13  mov     [rsp+0D8h+var_68], ax
0x18003bd18  mov     [r11-46h], ax
0x18003bd1d  cmp     r8d, 1
0x18003bd21  jb      loc_18003C0BD
0x18003bd27  movzx   r14d, byte ptr [rdx]
0x18003bd2b  lea     rbp, [rdx+1]
0x18003bd2f  mov     [r11-28h], r13
0x18003bd33  lea     edi, [r8-1]
0x18003bd37  test    r14b, r14b
0x18003bd3a  jnz     loc_18003C0D8
0x18003bd40  mov     rdx, rbp
0x18003bd43  cmp     edi, 3
0x18003bd46  jb      loc_18003C10C
0x18003bd4c  movzx   eax, byte ptr [rdx+1]
0x18003bd50  lea     r13d, [rdi-3]
0x18003bd54  movzx   r8d, byte ptr [rdx]
0x18003bd58  shl     r8d, 8
0x18003bd5c  add     r8d, eax
0x18003bd5f  mov     [rsp+0D8h+var_90], r13d
0x18003bd64  movzx   eax, byte ptr [rdx+2]
0x18003bd68  shl     r8d, 8
0x18003bd6c  add     r8d, eax
0x18003bd6f  cmp     r13d, r8d
0x18003bd72  jnz     loc_18003C10C
0x18003bd78  test    r8d, r8d
0x18003bd7b  jz      loc_18003C112
0x18003bd81  xor     r14d, r14d
0x18003bd84  mov     ebx, r13d
0x18003bd87  add     rdx, 3
0x18003bd8b  mov     [rsp+0D8h+var_78], rdx
0x18003bd90  test    ebx, ebx
0x18003bd92  jz      loc_18003BE77
0x18003bd98  cmp     ebx, 3
0x18003bd9b  jb      loc_18003C141
0x18003bda1  movzx   eax, byte ptr [rdx+1]
0x18003bda5  add     ebx, 0FFFFFFFDh
0x18003bda8  movzx   edi, byte ptr [rdx]
0x18003bdab  shl     edi, 8
0x18003bdae  add     edi, eax
0x18003bdb0  movzx   eax, byte ptr [rdx+2]
0x18003bdb4  shl     edi, 8
0x18003bdb7  add     edi, eax
0x18003bdb9  cmp     ebx, edi
0x18003bdbb  jb      loc_18003C141
0x18003bdc1  mov     eax, r15d
0x18003bdc4  mov     ebp, edi
0x18003bdc6  not     eax
0x18003bdc8  lea     rcx, [rdi+4]
0x18003bdcc  cmp     rax, rcx
0x18003bdcf  jb      loc_18003C141
0x18003bdd5  lea     rax, [rsp+0D8h+var_88]
0x18003bdda  mov     r9d, r12d; int
0x18003bddd  mov     [rsp+0D8h+var_A8], rax; __int64
0x18003bde2  lea     r13, [rdx+3]
0x18003bde6  lea     rax, [rsp+0D8h+var_80]
0x18003bdeb  mov     r8d, edi; int
0x18003bdee  mov     [rsp+0D8h+var_B0], rax; __int64
0x18003bdf3  mov     rdx, r13; int
0x18003bdf6  lea     rax, [rsp+0D8h+var_68]
0x18003bdfb  mov     rcx, rsi; int
0x18003bdfe  mov     [rsp+0D8h+var_B8], rax; CTlsSignatureSuiteList *
0x18003be03  call    ?ParseCertData@?$CTls13Handshake@VCTls13ClientContext@@VCTls13ExtClient@@@@IEAAKPEAEKKAEAVCTlsSignatureSuiteList@@AEAPEAU_PUBLICKEY@@AEAPEBU_CERT_CONTEXT@@@Z; CTls13Handshake<CTls13ClientContext,CTls13ExtClient>::ParseCertData(uchar *,ulong,ulong,CTlsSignatureSuiteList &,_PUBLICKEY * &,_CERT_CONTEXT const * &)
0x18003be08  mov     r14d, eax
0x18003be0b  test    eax, eax
0x18003be0d  jnz     loc_18003BF9B
0x18003be13  add     r15d, 4
0x18003be17  sub     ebx, edi
0x18003be19  add     r15d, edi
0x18003be1c  cmp     ebx, 2
0x18003be1f  jb      loc_18003C141
0x18003be25  movzx   ecx, byte ptr [rdi+r13]
0x18003be2a  add     ebx, 0FFFFFFFEh
0x18003be2d  movzx   eax, byte ptr [rdi+r13+1]
0x18003be33  shl     cx, 8
0x18003be37  or      cx, ax
0x18003be3a  movzx   edi, cx
0x18003be3d  cmp     ebx, edi
0x18003be3f  jb      loc_18003C06D
0x18003be45  mov     rcx, [rsi+10h]
0x18003be49  add     rbp, 2
0x18003be4d  add     rbp, r13
0x18003be50  mov     r9b, 0Bh
0x18003be53  mov     rdx, rbp
0x18003be56  mov     r8d, edi
0x18003be59  call    ?ParseTlsExtensions@CTlsExt@@QEAAKPEAEKW4eTlsHandshakeType@@@Z; CTlsExt::ParseTlsExtensions(uchar *,ulong,eTlsHandshakeType)
0x18003be5e  mov     r14d, eax
0x18003be61  test    eax, eax
0x18003be63  jnz     loc_18003C085
0x18003be69  inc     r12d
0x18003be6c  lea     rdx, [rdi+rbp]
0x18003be70  sub     ebx, edi
0x18003be72  jmp     loc_18003BD90
0x18003be77  mov     r10, [rsi+8]
0x18003be7b  lea     rax, [r10+892h]
0x18003be82  test    rax, rax
0x18003be85  jz      loc_18003C062
0x18003be8b  cmp     [rsp+0D8h+var_68], 0
0x18003be91  jz      loc_18003BF82
0x18003be97  movzx   r8d, [rsp+0D8h+var_46]
0x18003bea0  test    r8w, r8w
0x18003bea4  jz      loc_18003BF82
0x18003beaa  movzx   edx, word ptr [rax+22h]
0x18003beae  movzx   eax, cs:?RsaSha256Flags@CTlsSignatureSuiteList@@0GA; ushort CTlsSignatureSuiteList::RsaSha256Flags
0x18003beb5  test    ax, dx
0x18003beb8  jz      loc_18003C152
0x18003bebe  mov     ecx, eax
0x18003bec0  movzx   eax, cs:?RsaSha384Flags@CTlsSignatureSuiteList@@0GA; ushort CTlsSignatureSuiteList::RsaSha384Flags
0x18003bec7  or      cx, dx
0x18003beca  test    ax, cx
0x18003becd  jz      loc_18003C159
0x18003bed3  or      ax, cx
0x18003bed6  movzx   ecx, cs:?RsaSha512Flags@CTlsSignatureSuiteList@@0GA; ushort CTlsSignatureSuiteList::RsaSha512Flags
0x18003bedd  test    cx, ax
0x18003bee0  jz      loc_18003C07E
0x18003bee6  mov     edx, ecx
0x18003bee8  movzx   ecx, ax
0x18003beeb  or      ecx, edx
0x18003beed  not     ecx
0x18003beef  test    r8d, ecx
0x18003bef2  jnz     loc_18003BF82
0x18003bef8  mov     ecx, r15d; uBytes
0x18003befb  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18003bf00  mov     r12, rax
0x18003bf03  test    rax, rax
0x18003bf06  jz      loc_18003C160
0x18003bf0c  mov     r13d, [rsp+0D8h+var_90]
0x18003bf11  mov     rbx, rax
0x18003bf14  test    r13d, r13d
0x18003bf17  jz      loc_18003BFA0
0x18003bf1d  mov     rdi, [rsp+0D8h+var_78]
0x18003bf22  movzx   eax, byte ptr [rdi+1]
0x18003bf26  lea     rsi, [rdi+3]
0x18003bf2a  movzx   ebp, byte ptr [rdi]
0x18003bf2d  mov     rdx, rsi; Src
0x18003bf30  shl     ebp, 8
0x18003bf33  add     ebp, eax
0x18003bf35  movzx   eax, byte ptr [rdi+2]
0x18003bf39  shl     ebp, 8
0x18003bf3c  add     ebp, eax
0x18003bf3e  mov     [rbx], ebp
0x18003bf40  add     rbx, 4
0x18003bf44  mov     rcx, rbx; void *
0x18003bf47  mov     r8d, ebp; Size
0x18003bf4a  mov     edi, ebp
0x18003bf4c  call    memcpy_0
0x18003bf51  movzx   eax, byte ptr [rsi+rbp+1]
0x18003bf56  lea     r8, [rsi+rbp]
0x18003bf5a  movzx   ecx, byte ptr [r8]
0x18003bf5e  add     rbx, rdi
0x18003bf61  shl     cx, 8
0x18003bf65  or      cx, ax
0x18003bf68  mov     eax, 0FFFFFFFBh
0x18003bf6d  movzx   edx, cx
0x18003bf70  sub     eax, edx
0x18003bf72  sub     eax, ebp
0x18003bf74  lea     rdi, [rdx+2]
0x18003bf78  add     rdi, r8
0x18003bf7b  add     r13d, eax
0x18003bf7e  jnz     short loc_18003BF22
0x18003bf80  jmp     short loc_18003BFA0
0x18003bf82  mov     r9b, 28h ; '('
0x18003bf85  mov     edx, 0FCh
0x18003bf8a  mov     rcx, r10
0x18003bf8d  mov     r14d, 80090308h
0x18003bf93  mov     r8d, r14d
0x18003bf96  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18003bf9b  mov     r12, [rsp+0D8h+var_98]
0x18003bfa0  mov     r13, [rsp+0D8h+var_28]
0x18003bfa8  mov     rbx, [rsp+0D8h+var_70]
0x18003bfad  mov     dl, 1; Wait
0x18003bfaf  mov     rsi, [rsp+0D8h+var_88]
0x18003bfb4  mov     rbp, [rsp+0D8h+var_80]
0x18003bfb9  mov     rbx, [rbx+28h]
0x18003bfbd  lea     rcx, [rbx+50h]; Resource
0x18003bfc1  call    cs:__imp_RtlAcquireResourceExclusive
0x18003bfc7  mov     rcx, [rbx+10h]; void *
0x18003bfcb  test    rcx, rcx
0x18003bfce  jnz     loc_18003C16B
0x18003bfd4  mov     rcx, [rbx+20h]; void *
0x18003bfd8  mov     [rbx+10h], r12
0x18003bfdc  mov     r12, [rsp+0D8h+var_20]
0x18003bfe4  mov     [rbx+18h], r15d
0x18003bfe8  mov     r15, [rsp+0D8h+var_38]
0x18003bff0  test    rcx, rcx
0x18003bff3  jnz     loc_18003C175
0x18003bff9  mov     rcx, [rbx+28h]; pCertContext
0x18003bffd  mov     [rbx+20h], rbp
0x18003c001  mov     rbp, [rsp+0D8h+var_10]
0x18003c009  test    rcx, rcx
0x18003c00c  jnz     loc_18003C17F
0x18003c012  lea     rcx, [rbx+50h]; Resource
0x18003c016  mov     [rbx+28h], rsi
0x18003c01a  call    cs:__imp_RtlReleaseResource
0x18003c020  mov     rdi, [rsp+0D8h+var_18]
0x18003c028  mov     eax, r14d
0x18003c02b  mov     rbx, [rsp+0D8h+arg_10]
0x18003c033  mov     r14, [rsp+0D8h+var_30]
0x18003c03b  mov     rcx, [rsp+0D8h+var_40]
0x18003c043  xor     rcx, rsp; StackCookie
0x18003c046  call    __security_check_cookie
0x18003c04b  add     rsp, 0D0h
0x18003c052  pop     rsi
0x18003c053  retn
0x18003c054  mov     eax, 57h ; 'W'
0x18003c059  jmp     short loc_18003C03B
0x18003c05b  mov     eax, 54Fh
0x18003c060  jmp     short loc_18003C033
0x18003c062  mov     r14d, 54Fh
0x18003c068  jmp     loc_18003BF9B
0x18003c06d  mov     rcx, [rsi+8]
0x18003c071  mov     r9b, 32h ; '2'
0x18003c074  mov     edx, 0FDh
0x18003c079  jmp     loc_18003BF8D
0x18003c07e  xor     edx, edx
0x18003c080  jmp     loc_18003BEE8
0x18003c085  mov     rcx, [rsi+8]
0x18003c089  mov     r9b, 6Eh ; 'n'
0x18003c08c  mov     r8d, eax
0x18003c08f  mov     edx, 0FDh
0x18003c094  jmp     loc_18003BF96
0x18003c099  test    dword ptr [rcx+58h], 40051555h
0x18003c0a0  ja      short loc_18003C0DF
0x18003c0a2  mov     r14d, 80090308h
0x18003c0a8  mov     edx, 0FAh
0x18003c0ad  mov     r8d, r14d
0x18003c0b0  mov     r9b, 32h ; '2'
0x18003c0b3  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18003c0b8  jmp     loc_18003BFA0
0x18003c0bd  mov     r14d, 80090308h
0x18003c0c3  mov     r9b, 32h ; '2'
0x18003c0c6  mov     r8d, r14d
0x18003c0c9  mov     edx, 0FAh
0x18003c0ce  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18003c0d3  jmp     loc_18003BFA8
0x18003c0d8  cmp     edi, r14d
0x18003c0db  jb      short loc_18003C0A2
0x18003c0dd  jmp     short loc_18003C099
0x18003c0df  cmp     dword ptr [rcx+5Ch], 4Eh ; 'N'
0x18003c0e3  jnz     short loc_18003C0A2
0x18003c0e5  movzx   eax, byte ptr [rcx+0CF8h]
0x18003c0ec  cmp     r14b, al
0x18003c0ef  jnz     short loc_18003C0A2
0x18003c0f1  mov     rdx, [rcx+0CF0h]; Source2
0x18003c0f8  test    rdx, rdx
0x18003c0fb  jnz     loc_18008EEAC
0x18003c101  mov     r14d, 80090304h
0x18003c107  jmp     loc_18003BFA0
0x18003c10c  mov     rcx, [rsi+8]
0x18003c110  jmp     short loc_18003C0A2
0x18003c112  mov     rax, [rsi+8]
0x18003c116  test    dword ptr [rax+58h], 800A2AAAh
0x18003c11d  jz      loc_18008EED0
0x18003c123  mov     r14d, 80090308h
0x18003c129  mov     r9b, 2Ah ; '*'
0x18003c12c  mov     r8d, r14d
0x18003c12f  mov     edx, 0FAh
0x18003c134  mov     rcx, rax
0x18003c137  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18003c13c  jmp     loc_18003BFA0
0x18003c141  mov     rcx, [rsi+8]
0x18003c145  mov     r9b, 32h ; '2'
0x18003c148  mov     edx, 0FAh
0x18003c14d  jmp     loc_18003BF8D
0x18003c152  xor     ecx, ecx
0x18003c154  jmp     loc_18003BEC0
0x18003c159  xor     eax, eax
0x18003c15b  jmp     loc_18003BED3
0x18003c160  mov     r14d, 0Eh
0x18003c166  jmp     loc_18003BFA0
  ... truncated ...
```
