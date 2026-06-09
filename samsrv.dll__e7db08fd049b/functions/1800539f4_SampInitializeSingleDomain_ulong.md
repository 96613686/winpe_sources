# SampInitializeSingleDomain(ulong)

- ea: `0x1800539f4`
- end: `0x180053e7b`
- name: `?SampInitializeSingleDomain@@YAJK@Z`
- size: `1159`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180053844`

## callees

- `0x180002960`
- `0x1800213d0`
- `0x180022bd0`
- `0x180024d6c`
- `0x180027e24`
- `0x1800372ac`
- `0x18003c670`
- `0x180050960`
- `0x180053118`
- `0x1800539f4`
- `0x180059a74`
- `0x18008af7c`
- `0x1800ad9e0`
- `0x1800bb794`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180053d4f`
- `ntdll!RtlEqualSid` at `0x180053d4f`
- `ntdll!NtClose` at `0x180053ab4`
- `ntdll!NtClose` at `0x180053ab4`
- `ntdll!RtlpNtOpenKey` at `0x180053b75`
- `ntdll!RtlpNtOpenKey` at `0x180053b75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053d73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053df3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053d73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053df3`

## pseudocode

```c
__int64 __fastcall SampInitializeSingleDomain(unsigned int a1)
{
  __int64 v1; // r15
  __int64 Context; // rax
  __int64 v3; // rbx
  __int64 v4; // rsi
  struct _UNICODE_STRING *v5; // r13
  int v6; // edi
  PUNICODE_STRING v7; // rcx
  void *v8; // rcx
  __int64 v9; // rdx
  struct _UNICODE_STRING *v11; // rcx
  unsigned int v12; // eax
  char *v13; // rdx
  NTSTATUS v14; // eax
  int FixedAttributes; // eax
  int v16; // edx
  struct _PSAMP_DEFINED_DOMAINS *v17; // r12
  _OWORD *v18; // rdi
  __int64 v19; // rcx
  _OWORD *v20; // rax
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  PSID v34; // rdi
  struct _PSAMP_DEFINED_DOMAINS *v35; // rax
  unsigned __int8 v36; // r8
  int v37; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *Src; // [rsp+A8h] [rbp+48h] BYREF
  PSID Sid1; // [rsp+B0h] [rbp+50h]

  v1 = a1;
  Sid1 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Src = 0;
  Context = SampCreateContext(1, a1, 1);
  v3 = 1360 * v1;
  v4 = Context;
  v5 = (struct _UNICODE_STRING *)(Context + 160);
  if ( !Context )
  {
    v6 = -1073741670;
    goto LABEL_3;
  }
  v11 = (struct _UNICODE_STRING *)(Context + 160);
  v12 = *(_DWORD *)(Context + 192) & 0xFFFFFFFD;
  v13 = (char *)SampDefinedDomains + 32;
  *(_DWORD *)(v4 + 200) = v1;
  *(_DWORD *)(v4 + 192) = v12 | 1;
  v6 = SampBuildDomainKeyName(v11, (struct _UNICODE_STRING *)&v13[v3]);
  if ( v6 < 0 )
  {
    v5->Buffer = 0;
    goto LABEL_3;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = SampKey;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = v5;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v14 = RtlpNtOpenKey((HANDLE)(v4 + 152), 0x2001Fu, &ObjectAttributes, 0);
  v6 = v14;
  if ( v14 >= 0 )
  {
    FixedAttributes = SampGetFixedAttributes(v4, 0, &Src);
    v6 = FixedAttributes;
    if ( FixedAttributes >= 0 )
    {
      v17 = SampDefinedDomains;
      v18 = (_OWORD *)((char *)SampDefinedDomains + v3 + 496);
      memmove_0(v18, Src, 0x170u);
      v19 = 2;
      v20 = (_OWORD *)((char *)v17 + v3 + 128);
      do
      {
        v21 = v18[1];
        *v20 = *v18;
        v22 = v18[2];
        v20[1] = v21;
        v23 = v18[3];
        v20[2] = v22;
        v24 = v18[4];
        v20[3] = v23;
        v25 = v18[5];
        v20[4] = v24;
        v26 = v18[6];
        v20[5] = v25;
        v27 = v18[7];
        v18 += 8;
        v20[6] = v26;
        v20[7] = v27;
        v20 += 8;
        --v19;
      }
      while ( v19 );
      v28 = v18[1];
      *v20 = *v18;
      *((_BYTE *)v17 + v3 + 864) = 1;
      v29 = v18[2];
      v20[1] = v28;
      v30 = v18[3];
      v20[2] = v29;
      v31 = v18[4];
      v20[3] = v30;
      v32 = v18[5];
      v20[4] = v31;
      v33 = v18[6];
      v20[5] = v32;
      v20[6] = v33;
      *(_DWORD *)((char *)v17 + v3 + 1308) = *(_DWORD *)((char *)v17 + v3 + 588);
      FixedAttributes = SampGetSidAttribute((struct _SAMP_OBJECT *)v4, 1u);
      v6 = FixedAttributes;
      if ( FixedAttributes >= 0 )
      {
        v34 = Sid1;
        if ( RtlEqualSid(Sid1, *(PSID *)((char *)SampDefinedDomains + v3 + 8)) == 1 )
        {
          LocalFree(v34);
        }
        else
        {
          v35 = SampDefinedDomains;
          if ( *(_DWORD *)((char *)SampDefinedDomains + v3 + 1352) )
          {
            LocalFree(*(HLOCAL *)((char *)SampDefinedDomains + v3 + 8));
            v35 = SampDefinedDomains;
          }
          *(_QWORD *)((char *)v35 + v3 + 8) = v34;
          *(_DWORD *)((char *)v35 + v3 + 1352) = 1;
          if ( SampProductType != NtProductLanManNt || (v36 = 1, (_DWORD)v1 != 1) )
            v36 = 0;
          v37 = SampSetAccountDomainPolicy((struct _UNICODE_STRING *)((char *)v35 + v3 + 16), v34, v36);
          if ( v37 < 0 )
          {
            v7 = WPP_GLOBAL_Control;
            if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
              && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[3].Buffer,
                145,
                &WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids,
                (unsigned int)v37);
              v7 = WPP_GLOBAL_Control;
            }
            v6 = -1073741692;
            goto LABEL_4;
          }
        }
        v6 = SampInitializeDomainDescriptors(v1);
        if ( v6 >= 0 )
        {
          *(_QWORD *)((char *)SampDefinedDomains + v3) = v4;
          v6 = SampInitializeDisplayInformation(v1);
          if ( v6 >= 0 )
          {
            if ( *((_BYTE *)SampDefinedDomains + v3 + 1296) )
              *((_BYTE *)SampDefinedDomains + v3 + 1336) = 0;
            else
              *((_BYTE *)SampDefinedDomains + v3 + 1336) = SampIsExtendedSidModeEmulated(0);
            v7 = WPP_GLOBAL_Control;
            if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            {
              v9 = 146;
              goto LABEL_13;
            }
            return (unsigned int)v6;
          }
          *(_QWORD *)((char *)SampDefinedDomains + v3) = 0;
        }
        goto LABEL_3;
      }
      v7 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 )
        goto LABEL_7;
      if ( HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      {
LABEL_4:
        if ( (*(_BYTE *)(&v7[4].MaximumLength + 1) & 1) != 0 && HIBYTE(v7[4].Length) >= 2u )
        {
          WPP_SF_ZD(
            v7[3].Buffer,
            147,
            (unsigned int)&WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids,
            v3 + (_DWORD)SampDefinedDomains + 16,
            v6);
          v7 = WPP_GLOBAL_Control;
        }
LABEL_7:
        if ( v4 )
        {
          SampFreeUnicodeString(v5);
          v8 = *(void **)(v4 + 152);
          if ( v8 != (void *)-1LL )
            NtClose(v8);
          v7 = WPP_GLOBAL_Control;
        }
        if ( (*(_DWORD *)(&v7[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          v9 = 148;
LABEL_13:
          WPP_SF_Dd(v7[3].Buffer, v9, &WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids, (unsigned int)v6, v6);
          return (unsigned int)v6;
        }
        return (unsigned int)v6;
      }
      v16 = 144;
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 )
        goto LABEL_7;
      if ( HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
        goto LABEL_4;
      v16 = 143;
    }
    WPP_SF_ZD(
      v7[3].Buffer,
      v16,
      (unsigned int)&WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids,
      v3 + (_DWORD)SampDefinedDomains + 16,
      FixedAttributes);
LABEL_3:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_4;
  }
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 141, &WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids, (unsigned int)v14);
  *(_QWORD *)(v4 + 152) = -1;
  v7 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v9 = 142;
    goto LABEL_13;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800539f4  mov     [rsp-38h+arg_0], rbx
0x1800539f9  push    rbp
0x1800539fa  push    rsi
0x1800539fb  push    rdi
0x1800539fc  push    r12
0x1800539fe  push    r13
0x180053a00  push    r14
0x180053a02  push    r15
0x180053a04  mov     rbp, rsp
0x180053a07  sub     rsp, 60h
0x180053a0b  xorps   xmm0, xmm0
0x180053a0e  mov     r15d, ecx
0x180053a11  xor     r12d, r12d
0x180053a14  mov     edx, ecx
0x180053a16  mov     r8b, 1
0x180053a19  mov     [rbp+Sid1], r12
0x180053a1d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180053a21  mov     [rbp+Src], r12
0x180053a25  lea     ecx, [r12+1]
0x180053a2a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180053a2e  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180053a32  call    ?SampCreateContext@@YAPEAU_SAMP_OBJECT@@W4_SAMP_OBJECT_TYPE@@KE@Z; SampCreateContext(_SAMP_OBJECT_TYPE,ulong,uchar)
0x180053a37  imul    rbx, r15, 550h
0x180053a3e  lea     r14, WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids
0x180053a45  mov     rsi, rax
0x180053a48  lea     r13, [rax+0A0h]
0x180053a4f  test    rax, rax
0x180053a52  jnz     loc_180053AFC
0x180053a58  mov     edi, 0C000009Ah
0x180053a5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a64  test    byte ptr [rcx+44h], 1
0x180053a68  jz      short loc_180053A9A
0x180053a6a  cmp     byte ptr [rcx+41h], 2
0x180053a6e  jb      short loc_180053A9A
0x180053a70  mov     r9, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180053a77  mov     edx, 93h
0x180053a7c  mov     rcx, [rcx+38h]
0x180053a80  add     r9, 10h
0x180053a84  add     r9, rbx
0x180053a87  mov     [rsp+60h+var_40], edi
0x180053a8b  mov     r8, r14
0x180053a8e  call    WPP_SF_ZD
0x180053a93  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a9a  test    rsi, rsi
0x180053a9d  jz      short loc_180053AC1
0x180053a9f  mov     rcx, r13
0x180053aa2  call    SampFreeUnicodeString
0x180053aa7  mov     rcx, [rsi+98h]; Handle
0x180053aae  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180053ab2  jz      short loc_180053ABA
0x180053ab4  call    cs:__imp_NtClose
0x180053aba  mov     rcx, cs:WPP_GLOBAL_Control
0x180053ac1  test    dword ptr [rcx+44h], 20000h
0x180053ac8  jz      short loc_180053AE2
0x180053aca  mov     edx, 94h
0x180053acf  mov     rcx, [rcx+38h]
0x180053ad3  mov     r9d, edi
0x180053ad6  mov     r8, r14
0x180053ad9  mov     [rsp+60h+var_40], edi
0x180053add  call    WPP_SF_Dd
0x180053ae2  mov     rbx, [rsp+60h+arg_0]
0x180053aea  mov     eax, edi
0x180053aec  add     rsp, 60h
0x180053af0  pop     r15
0x180053af2  pop     r14
0x180053af4  pop     r13
0x180053af6  pop     r12
0x180053af8  pop     rdi
0x180053af9  pop     rsi
0x180053afa  pop     rbp
0x180053afb  retn
0x180053afc  mov     eax, [rax+0C0h]
0x180053b02  mov     rcx, r13; struct _UNICODE_STRING *
0x180053b05  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180053b0c  and     eax, 0FFFFFFFDh
0x180053b0f  add     rdx, 20h ; ' '
0x180053b13  mov     [rsi+0C8h], r15d
0x180053b1a  or      eax, 1
0x180053b1d  add     rdx, rbx; struct _UNICODE_STRING *
0x180053b20  mov     [rsi+0C0h], eax
0x180053b26  call    ?SampBuildDomainKeyName@@YAJPEAU_UNICODE_STRING@@0@Z; SampBuildDomainKeyName(_UNICODE_STRING *,_UNICODE_STRING *)
0x180053b2b  mov     edi, eax
0x180053b2d  test    eax, eax
0x180053b2f  jns     short loc_180053B3A
0x180053b31  mov     [r13+8], r12
0x180053b35  jmp     loc_180053A5D
0x180053b3a  mov     rax, cs:SampKey
0x180053b41  lea     r12, [rsi+98h]
0x180053b48  xorps   xmm0, xmm0
0x180053b4b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180053b52  mov     rcx, r12; KeyHandle
0x180053b55  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180053b59  xor     r9d, r9d; Unused
0x180053b5c  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180053b63  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180053b67  mov     [rbp+ObjectAttributes.ObjectName], r13
0x180053b6b  mov     edx, 2001Fh; DesiredAccess
0x180053b70  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180053b75  call    cs:__imp_RtlpNtOpenKey
0x180053b7b  mov     edi, eax
0x180053b7d  test    eax, eax
0x180053b7f  jns     short loc_180053BD5
0x180053b81  mov     rcx, cs:WPP_GLOBAL_Control
0x180053b88  lea     r14, WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids
0x180053b8f  test    byte ptr [rcx+44h], 1
0x180053b93  jz      short loc_180053BAF
0x180053b95  cmp     byte ptr [rcx+41h], 2
0x180053b99  jb      short loc_180053BAF
0x180053b9b  mov     rcx, [rcx+38h]
0x180053b9f  mov     edx, 8Dh
0x180053ba4  mov     r9d, eax
0x180053ba7  mov     r8, r14
0x180053baa  call    WPP_SF_d
0x180053baf  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x180053bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180053bbe  test    dword ptr [rcx+44h], 20000h
0x180053bc5  jz      loc_180053AE2
0x180053bcb  mov     edx, 8Eh
0x180053bd0  jmp     loc_180053ACF
0x180053bd5  lea     r8, [rbp+Src]
0x180053bd9  xor     edx, edx
0x180053bdb  mov     rcx, rsi
0x180053bde  call    SampGetFixedAttributes
0x180053be3  mov     edi, eax
0x180053be5  test    eax, eax
0x180053be7  jns     short loc_180053C2C
0x180053be9  mov     rcx, cs:WPP_GLOBAL_Control
0x180053bf0  test    byte ptr [rcx+44h], 1
0x180053bf4  jz      loc_180053A9A
0x180053bfa  cmp     byte ptr [rcx+41h], 2
0x180053bfe  jb      loc_180053A64
0x180053c04  mov     edx, 8Fh
0x180053c09  mov     r9, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180053c10  mov     r8, r14
0x180053c13  mov     rcx, [rcx+38h]
0x180053c17  add     r9, 10h
0x180053c1b  add     r9, rbx
0x180053c1e  mov     [rsp+60h+var_40], eax
0x180053c22  call    WPP_SF_ZD
0x180053c27  jmp     loc_180053A5D
0x180053c2c  mov     r12, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180053c33  mov     r8d, 170h; Size
0x180053c39  mov     rdx, [rbp+Src]; Src
0x180053c3d  lea     rdi, [r12+1F0h]
0x180053c45  add     rdi, rbx
0x180053c48  mov     rcx, rdi; void *
0x180053c4b  call    memmove_0
0x180053c50  mov     ecx, 2
0x180053c55  lea     rax, [r12+80h]
0x180053c5d  add     rax, rbx
0x180053c60  lea     edx, [rcx+7Eh]
0x180053c63  movups  xmm0, xmmword ptr [rdi]
0x180053c66  movups  xmm1, xmmword ptr [rdi+10h]
0x180053c6a  movups  xmmword ptr [rax], xmm0
0x180053c6d  movups  xmm0, xmmword ptr [rdi+20h]
0x180053c71  movups  xmmword ptr [rax+10h], xmm1
0x180053c75  movups  xmm1, xmmword ptr [rdi+30h]
0x180053c79  movups  xmmword ptr [rax+20h], xmm0
0x180053c7d  movups  xmm0, xmmword ptr [rdi+40h]
0x180053c81  movups  xmmword ptr [rax+30h], xmm1
0x180053c85  movups  xmm1, xmmword ptr [rdi+50h]
0x180053c89  movups  xmmword ptr [rax+40h], xmm0
0x180053c8d  movups  xmm0, xmmword ptr [rdi+60h]
0x180053c91  movups  xmmword ptr [rax+50h], xmm1
0x180053c95  movups  xmm1, xmmword ptr [rdi+70h]
0x180053c99  add     rdi, rdx
0x180053c9c  movups  xmmword ptr [rax+60h], xmm0
0x180053ca0  movups  xmmword ptr [rax+70h], xmm1
0x180053ca4  add     rax, rdx
0x180053ca7  sub     rcx, 1
0x180053cab  jnz     short loc_180053C63
0x180053cad  movups  xmm0, xmmword ptr [rdi]
0x180053cb0  lea     edx, [rcx+1]; unsigned int
0x180053cb3  mov     r8b, 1
0x180053cb6  movups  xmm1, xmmword ptr [rdi+10h]
0x180053cba  lea     r9, [rbp+Sid1]
0x180053cbe  mov     rcx, rsi; struct _SAMP_OBJECT *
0x180053cc1  movups  xmmword ptr [rax], xmm0
0x180053cc4  mov     byte ptr [rbx+r12+360h], 1
0x180053ccd  movups  xmm0, xmmword ptr [rdi+20h]
0x180053cd1  movups  xmmword ptr [rax+10h], xmm1
0x180053cd5  movups  xmm1, xmmword ptr [rdi+30h]
0x180053cd9  movups  xmmword ptr [rax+20h], xmm0
0x180053cdd  movups  xmm0, xmmword ptr [rdi+40h]
0x180053ce1  movups  xmmword ptr [rax+30h], xmm1
0x180053ce5  movups  xmm1, xmmword ptr [rdi+50h]
0x180053ce9  movups  xmmword ptr [rax+40h], xmm0
0x180053ced  movups  xmm0, xmmword ptr [rdi+60h]
0x180053cf1  movups  xmmword ptr [rax+50h], xmm1
0x180053cf5  movups  xmmword ptr [rax+60h], xmm0
0x180053cf9  mov     eax, [rbx+r12+24Ch]
0x180053d01  mov     [rbx+r12+51Ch], eax
0x180053d09  call    SampGetSidAttribute
0x180053d0e  xor     r12d, r12d
0x180053d11  mov     edi, eax
0x180053d13  test    eax, eax
0x180053d15  jns     short loc_180053D3C
0x180053d17  mov     rcx, cs:WPP_GLOBAL_Control
0x180053d1e  test    byte ptr [rcx+44h], 1
0x180053d22  jz      loc_180053A9A
0x180053d28  cmp     byte ptr [rcx+41h], 2
0x180053d2c  jb      loc_180053A64
0x180053d32  mov     edx, 90h
0x180053d37  jmp     loc_180053C09
0x180053d3c  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180053d43  mov     rdi, [rbp+Sid1]
0x180053d47  mov     rcx, rdi; Sid1
0x180053d4a  mov     rdx, [rbx+rdx+8]; Sid2
0x180053d4f  call    cs:__imp_RtlEqualSid
0x180053d55  cmp     al, 1
0x180053d57  jz      loc_180053DF0
0x180053d5d  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180053d64  cmp     [rbx+rax+548h], r12d
0x180053d6c  jz      short loc_180053D80
0x180053d6e  mov     rcx, [rbx+rax+8]; hMem
0x180053d73  call    cs:__imp_LocalFree
0x180053d79  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180053d80  mov     [rbx+rax+8], rdi
0x180053d85  mov     dword ptr [rbx+rax+548h], 1
0x180053d90  cmp     cs:?SampProductType@@3W4_NT_PRODUCT_TYPE@@A, 2; _NT_PRODUCT_TYPE SampProductType
0x180053d97  jnz     short loc_180053DA2
0x180053d99  mov     r8b, 1
0x180053d9c  cmp     r15d, 1
0x180053da0  jz      short loc_180053DA5
0x180053da2  mov     r8b, r12b; unsigned __int8
0x180053da5  lea     rcx, [rbx+10h]
0x180053da9  mov     rdx, rdi; void *
0x180053dac  add     rcx, rax; struct _UNICODE_STRING *
0x180053daf  call    ?SampSetAccountDomainPolicy@@YAJPEAU_UNICODE_STRING@@PEAXE@Z; SampSetAccountDomainPolicy(_UNICODE_STRING *,void *,uchar)
0x180053db4  test    eax, eax
0x180053db6  jns     short loc_180053DF9
0x180053db8  mov     rcx, cs:WPP_GLOBAL_Control
0x180053dbf  test    byte ptr [rcx+44h], 1
0x180053dc3  jz      short loc_180053DE6
0x180053dc5  cmp     byte ptr [rcx+41h], 2
0x180053dc9  jb      short loc_180053DE6
0x180053dcb  mov     rcx, [rcx+38h]
0x180053dcf  mov     edx, 91h
0x180053dd4  mov     r9d, eax
0x180053dd7  mov     r8, r14
0x180053dda  call    WPP_SF_d
0x180053ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x180053de6  mov     edi, 0C0000084h
0x180053deb  jmp     loc_180053A64
0x180053df0  mov     rcx, rdi; hMem
0x180053df3  call    cs:__imp_LocalFree
0x180053df9  mov     ecx, r15d; unsigned int
0x180053dfc  call    ?SampInitializeDomainDescriptors@@YAJK@Z; SampInitializeDomainDescriptors(ulong)
0x180053e01  mov     edi, eax
0x180053e03  test    eax, eax
0x180053e05  js      loc_180053A5D
0x180053e0b  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180053e12  mov     ecx, r15d; unsigned int
0x180053e15  mov     [rbx+rax], rsi
0x180053e19  call    ?SampInitializeDisplayInformation@@YAJK@Z; SampInitializeDisplayInformation(ulong)
0x180053e1e  mov     edi, eax
0x180053e20  test    eax, eax
0x180053e22  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180053e29  jns     short loc_180053E34
0x180053e2b  mov     [rbx+rax], r12
0x180053e2f  jmp     loc_180053A5D
0x180053e34  cmp     [rbx+rax+510h], r12b
0x180053e3c  jz      short loc_180053E48
0x180053e3e  mov     [rbx+rax+538h], r12b
0x180053e46  jmp     short loc_180053E5D
0x180053e48  xor     ecx, ecx; unsigned int *
0x180053e4a  call    ?SampIsExtendedSidModeEmulated@@YAEPEAK@Z; SampIsExtendedSidModeEmulated(ulong *)
0x180053e4f  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180053e56  mov     [rbx+rcx+538h], al
0x180053e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180053e64  test    dword ptr [rcx+44h], 20000h
0x180053e6b  jz      loc_180053AE2
0x180053e71  mov     edx, 92h
0x180053e76  jmp     loc_180053ACF
```
