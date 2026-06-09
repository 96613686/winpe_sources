# CVssSidCollection::IsSidAllowedToFire(void *)

- ea: `0x140031760`
- end: `0x140031cbe`
- name: `?IsSidAllowedToFire@CVssSidCollection@@QEAA_NPEAX@Z`
- size: `1374`
- prototype: `bool(CVssSidCollection *__hidden this, void *)`
- caller_count: `8`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001b9f0`
- `0x14002e580`
- `0x14002f950`
- `0x140054e30`
- `0x140055590`
- `0x1400a7860`
- `0x1400a79c0`
- `0x1400a85f0`

## callees

- `0x14000e640`
- `0x1400138e0`
- `0x1400139c0`
- `0x140013c60`
- `0x140031760`
- `0x140031cd0`
- `0x14003a8f0`
- `0x140091560`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140031938`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140031b4f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140031938`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140031b4f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140031915`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140031915`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1400318f8`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1400318f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003181f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140031a09`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003181f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140031a09`
- `VssTrace!__imp_VssTraceMessage` at `0x140031b9e`
- `VssTrace!__imp_VssTraceMessage` at `0x140031b9e`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140031ac4`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140031b1e`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140031ac4`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140031b1e`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003185a`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003185a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400319d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400319e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400319f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400319ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140031af8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400319d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400319e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400319f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400319ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140031af8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140031bec`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140031bec`

## string_xrefs

- `0x140031796`: `base\stor\vss\modules\sec\security.cxx`
- `0x140031c2c`: `base\stor\vss\modules\sec\security.cxx`
- `0x1400317a1`: `CVssSidCollection::IsSidAllowedToFire`
- `0x140031c37`: `CVssSidCollection::IsSidAllowedToFire`
- `0x140031c9a`: `WriterSid: %s was %s %s to fire`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall CVssSidCollection::IsSidAllowedToFire(PACL *this, void *a2)
{
  int v4; // r15d
  __int64 v5; // rax
  unsigned int v6; // r12d
  unsigned int v7; // ebx
  __int64 i; // rbx
  void *v9; // rcx
  char v10; // r13
  char v11; // di
  int v12; // eax
  DWORD v13; // ebx
  bool v14; // r14
  const wchar_t *v15; // rax
  DWORD v16; // esi
  const wchar_t *v18; // rbx
  const wchar_t *v19; // rsi
  __int16 v20; // ax
  __int64 v21; // [rsp+20h] [rbp-E0h]
  __int64 v22; // [rsp+28h] [rbp-D8h]
  __int64 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  __int64 v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pAce; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v29; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v30; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v31; // [rsp+78h] [rbp-88h]
  unsigned int v32; // [rsp+80h] [rbp-80h]
  unsigned int v33; // [rsp+84h] [rbp-7Ch]
  const wchar_t *v34; // [rsp+88h] [rbp-78h]
  unsigned int v35; // [rsp+90h] [rbp-70h]
  DWORD TickCount; // [rsp+94h] [rbp-6Ch]
  unsigned int v37; // [rsp+98h] [rbp-68h]
  LPVOID pv[2]; // [rsp+A0h] [rbp-60h]
  LPVOID v39[2]; // [rsp+B0h] [rbp-50h]
  __int64 v40; // [rsp+C0h] [rbp-40h]
  void **v41; // [rsp+D0h] [rbp-30h] BYREF
  LPWSTR StringSid; // [rsp+D8h] [rbp-28h] BYREF
  const unsigned __int16 *v43; // [rsp+E0h] [rbp-20h] BYREF
  const wchar_t *v44; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v45; // [rsp+F0h] [rbp-10h]
  int v46; // [rsp+F8h] [rbp-8h]
  int v47; // [rsp+FCh] [rbp-4h]
  int v48; // [rsp+100h] [rbp+0h]
  LPVOID v49[2]; // [rsp+108h] [rbp+8h] BYREF
  __int128 v50; // [rsp+118h] [rbp+18h]
  __int128 v51; // [rsp+128h] [rbp+28h]
  __int128 v52; // [rsp+138h] [rbp+38h]
  __int128 v53; // [rsp+148h] [rbp+48h]
  __int128 v54; // [rsp+158h] [rbp+58h]
  __int128 v55; // [rsp+168h] [rbp+68h]
  __int64 v56; // [rsp+178h] [rbp+78h]
  int v57; // [rsp+180h] [rbp+80h]
  __int64 pAclInformation; // [rsp+188h] [rbp+88h] BYREF
  int v59; // [rsp+190h] [rbp+90h]

  v43 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v44 = L"CVssSidCollection::IsSidAllowedToFire";
  v45 = L"SECSECRC";
  v46 = 1767;
  v47 = 11;
  v48 = 255;
  v4 = 0;
  v57 = 0x1000000;
  *(_OWORD *)v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v29 = 0;
  v34 = L"CVssSidCollection::IsSidAllowedToFire";
  v30 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v31 = L"SECSECRC";
  v32 = 1767;
  v33 = 11;
  TickCount = GetTickCount();
  v28[1] = -1;
  v37 = 255;
  v28[0] = 0;
  v40 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v39 = 0;
  v26 = 0;
  if ( (int)VssGetTracingContextPerThread(&v26) < 0 || (int)VssSetTracingContextPerThread(v28) < 0 )
  {
    v5 = v40;
  }
  else
  {
    v5 = v26;
    v40 = v26;
  }
  if ( v5 )
    v35 = *(_DWORD *)(v5 + 48) + 1;
  else
    v35 = 0;
  v6 = 160;
  v7 = 160;
  if ( v37 != 255 )
    v7 = v37;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v28, v33) )
    VssTraceMessage(v30, v31, v32, v35, v33, v34, L"ENTER", v7, 0);
  for ( i = 0; i != 15; ++i )
  {
    v9 = v49[i];
    if ( v9 )
    {
      CoTaskMemFree(v9);
      v49[i] = 0;
    }
  }
  pAclInformation = 0;
  v59 = 0;
  pAce = 0;
  v10 = 0;
  v11 = 0;
  GetAclInformation(this[4], &pAclInformation, 0xCu, AclSizeInformation);
  v12 = pAclInformation;
  while ( 1 )
  {
    v13 = 0;
    if ( v12 )
      break;
LABEL_21:
    if ( (unsigned int)++v4 >= 2 )
      goto LABEL_22;
  }
  while ( 1 )
  {
    GetAce(this[4], v13, &pAce);
    if ( *(_BYTE *)pAce )
      break;
    if ( v4 )
    {
      if ( !CVssSidCollection::ExpandForVerification(
              (CVssSidCollection *)this,
              (struct CVssFunctionTracer *)v28,
              a2,
              (char *)pAce + 8) )
        goto LABEL_20;
LABEL_18:
      v11 = 1;
      goto LABEL_20;
    }
    if ( EqualSid(a2, (char *)pAce + 8) )
      goto LABEL_18;
LABEL_20:
    ++v13;
    v12 = pAclInformation;
    if ( v13 >= (unsigned int)pAclInformation )
      goto LABEL_21;
  }
  if ( *(_BYTE *)pAce != 1 )
    goto LABEL_20;
  if ( !v4 )
  {
    if ( EqualSid(a2, (char *)pAce + 8) )
      goto LABEL_40;
    goto LABEL_20;
  }
  if ( !CVssSidCollection::ExpandForVerification(
          (CVssSidCollection *)this,
          (struct CVssFunctionTracer *)v28,
          a2,
          (char *)pAce + 8) )
    goto LABEL_20;
LABEL_40:
  v10 = 1;
LABEL_22:
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v28, v33) )
  {
    StringSid = 0;
    v41 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
    CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v41);
    if ( !ConvertSidToStringSidW(a2, &StringSid) )
    {
LABEL_51:
      CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v41);
      goto LABEL_23;
    }
    if ( !v11 || v10 )
    {
      v18 = L"denied";
      if ( !v11 )
      {
        v19 = L"implicitely";
        if ( !v10 )
          goto LABEL_48;
      }
    }
    else
    {
      v18 = L"allowed";
    }
    v19 = L"explicitely";
LABEL_48:
    v43 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v44 = L"CVssSidCollection::IsSidAllowedToFire";
    v45 = L"SECSECRC";
    v46 = 1857;
    v47 = 11;
    v48 = 255;
    v57 = 0x1000000;
    memset_0(v49, 0, 0x78u);
    v20 = 15;
    do
      --v20;
    while ( v20 );
    CVssFunctionTracer::Trace(v28, &v43, L"WriterSid: %s was %s %s to fire", StringSid, v19, v18);
    goto LABEL_51;
  }
LABEL_23:
  v14 = v11 && !v10;
  v15 = L"TRUE";
  if ( !v14 )
    v15 = L"FALSE";
  CVssFunctionTracer::TraceInternalWithFormat((CVssFunctionTracer *)v28, L"RETURN", 0xAAu, L"Returning BOOL: %s", v15);
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v39[0]);
  v39[0] = 0;
  CoTaskMemFree(v39[1]);
  v39[1] = 0;
  v16 = GetTickCount() - TickCount;
  if ( v37 != 255 )
    v6 = v37;
  LODWORD(v25) = v16;
  LODWORD(v24) = v16 % 0x3E8;
  LODWORD(v23) = v16 / 0x3E8 % 0x3C;
  LODWORD(v22) = v16 / 0xEA60 % 0x3C;
  LODWORD(v21) = v16 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v28,
    L"EXIT",
    v6,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v21,
    v22,
    v23,
    v24,
    v25,
    v29);
  VssSetTracingContextPerThread(v40);
  return v14;
}

```

## disassembly

```asm
0x140031760  mov     [rsp-8+arg_10], rbx
0x140031765  push    rbp
0x140031766  push    rsi
0x140031767  push    rdi
0x140031768  push    r12
0x14003176a  push    r13
0x14003176c  push    r14
0x14003176e  push    r15
0x140031770  lea     rbp, [rsp-0A0h]
0x140031778  sub     rsp, 1A0h
0x14003177f  mov     rax, cs:__security_cookie
0x140031786  xor     rax, rsp
0x140031789  mov     [rbp+0D0h+var_38], rax
0x140031790  mov     r14, rdx
0x140031793  mov     rsi, rcx
0x140031796  lea     rcx, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14003179d  mov     [rbp+0D0h+var_F0], rcx
0x1400317a1  lea     rdx, aCvsssidcollect_0; "CVssSidCollection::IsSidAllowedToFire"
0x1400317a8  mov     [rbp+0D0h+var_E8], rdx
0x1400317ac  lea     r8, aSecsecrc; "SECSECRC"
0x1400317b3  mov     [rbp+0D0h+var_E0], r8
0x1400317b7  mov     [rbp+0D0h+var_D8], 6E7h
0x1400317be  mov     [rbp+0D0h+var_D4], 0Bh
0x1400317c5  mov     [rbp+0D0h+var_D0], 0FFh
0x1400317cc  xor     r15d, r15d
0x1400317cf  mov     [rbp+0D0h+var_50], 1000000h
0x1400317d9  xorps   xmm0, xmm0
0x1400317dc  xor     eax, eax
0x1400317de  movups  xmmword ptr [rbp+0D0h+var_C8], xmm0
0x1400317e2  movups  [rbp+0D0h+var_B8], xmm0
0x1400317e6  movups  [rbp+0D0h+var_A8], xmm0
0x1400317ea  movups  [rbp+0D0h+var_98], xmm0
0x1400317ee  movups  [rbp+0D0h+var_88], xmm0
0x1400317f2  movups  [rbp+0D0h+var_78], xmm0
0x1400317f6  movups  [rbp+0D0h+var_68], xmm0
0x1400317fa  mov     [rbp+0D0h+var_58], rax
0x1400317fe  mov     [rsp+1D0h+var_168], r15d
0x140031803  mov     [rbp+0D0h+var_148], rdx
0x140031807  mov     [rsp+1D0h+var_160], rcx
0x14003180c  mov     [rsp+1D0h+var_158], r8
0x140031811  mov     [rbp+0D0h+var_150], 6E7h
0x140031818  mov     [rbp+0D0h+var_14C], 0Bh
0x14003181f  call    cs:__imp_GetTickCount
0x140031825  mov     [rbp+0D0h+var_13C], eax
0x140031828  mov     [rsp+1D0h+var_16C], 0FFFFFFFFh
0x140031830  mov     [rbp+0D0h+var_138], 0FFh
0x140031837  mov     [rsp+1D0h+var_170], r15d
0x14003183c  mov     [rbp+0D0h+var_110], r15
0x140031840  xorps   xmm0, xmm0
0x140031843  movdqa  xmmword ptr [rbp+0D0h+pv], xmm0
0x140031848  xorps   xmm1, xmm1
0x14003184b  movdqa  xmmword ptr [rbp+0D0h+var_120], xmm1
0x140031850  mov     [rsp+1D0h+var_180], r15
0x140031855  lea     rcx, [rsp+1D0h+var_180]
0x14003185a  call    cs:__imp_VssGetTracingContextPerThread
0x140031860  test    eax, eax
0x140031862  jns     loc_140031B19
0x140031868  mov     rax, [rbp+0D0h+var_110]
0x14003186c  test    rax, rax
0x14003186f  jz      loc_140031B5E
0x140031875  mov     eax, [rax+30h]
0x140031878  inc     eax
0x14003187a  mov     [rbp+0D0h+var_140], eax
0x14003187d  mov     r12d, 0A0h
0x140031883  mov     ebx, r12d
0x140031886  cmp     [rbp+0D0h+var_138], 0FFh
0x14003188d  cmovnz  ebx, [rbp+0D0h+var_138]
0x140031891  mov     edx, [rbp+0D0h+var_14C]; unsigned int
0x140031894  lea     rcx, [rsp+1D0h+var_170]; this
0x140031899  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14003189e  test    eax, eax
0x1400318a0  jnz     loc_140031B67
0x1400318a6  mov     rbx, r15
0x1400318a9  nop     dword ptr [rax+00000000h]
0x1400318b0  mov     rcx, [rbp+rbx*8+0D0h+var_C8]; pv
0x1400318b5  test    rcx, rcx
0x1400318b8  jnz     loc_140031AF8
0x1400318be  inc     rbx
0x1400318c1  cmp     rbx, 0Fh
0x1400318c5  jnz     short loc_1400318B0
0x1400318c7  xor     eax, eax
0x1400318c9  mov     [rbp+0D0h+pAclInformation], rax
0x1400318d0  mov     [rbp+0D0h+var_40], eax
0x1400318d6  mov     [rsp+1D0h+pAce], r15
0x1400318db  xor     r13b, r13b
0x1400318de  xor     dil, dil
0x1400318e1  mov     r9d, 2; dwAclInformationClass
0x1400318e7  mov     r8d, 0Ch; nAclInformationLength
0x1400318ed  lea     rdx, [rbp+0D0h+pAclInformation]; pAclInformation
0x1400318f4  mov     rcx, [rsi+20h]; pAcl
0x1400318f8  call    cs:__imp_GetAclInformation
0x1400318fe  mov     eax, dword ptr [rbp+0D0h+pAclInformation]
0x140031904  xor     ebx, ebx
0x140031906  test    eax, eax
0x140031908  jz      short loc_14003196B
0x14003190a  lea     r8, [rsp+1D0h+pAce]; pAce
0x14003190f  mov     edx, ebx; dwAceIndex
0x140031911  mov     rcx, [rsi+20h]; pAcl
0x140031915  call    cs:__imp_GetAce
0x14003191b  mov     r9, [rsp+1D0h+pAce]
0x140031920  movzx   ecx, byte ptr [r9]
0x140031924  test    ecx, ecx
0x140031926  jnz     loc_140031B3A
0x14003192c  test    r15d, r15d
0x14003192f  jnz     short loc_140031947
0x140031931  lea     rdx, [r9+8]; pSid2
0x140031935  mov     rcx, r14; pSid1
0x140031938  call    cs:__imp_EqualSid
0x14003193e  test    eax, eax
0x140031940  jz      short loc_14003195F
0x140031942  mov     dil, 1
0x140031945  jmp     short loc_14003195F
0x140031947  add     r9, 8; void *
0x14003194b  mov     r8, r14; void *
0x14003194e  lea     rdx, [rsp+1D0h+var_170]; struct CVssFunctionTracer *
0x140031953  mov     rcx, rsi; this
0x140031956  call    ?ExpandForVerification@CVssSidCollection@@AEAA_NAEAVCVssFunctionTracer@@PEAX1@Z; CVssSidCollection::ExpandForVerification(CVssFunctionTracer &,void *,void *)
0x14003195b  test    al, al
0x14003195d  jnz     short loc_140031942
0x14003195f  inc     ebx
0x140031961  mov     eax, dword ptr [rbp+0D0h+pAclInformation]
0x140031967  cmp     ebx, eax
0x140031969  jb      short loc_14003190A
0x14003196b  inc     r15d
0x14003196e  cmp     r15d, 2
0x140031972  jb      short loc_140031904
0x140031974  mov     edx, [rbp+0D0h+var_14C]; unsigned int
0x140031977  lea     rcx, [rsp+1D0h+var_170]; this
0x14003197c  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140031981  xor     r15d, r15d
0x140031984  test    eax, eax
0x140031986  jnz     loc_140031BCD
0x14003198c  test    dil, dil
0x14003198f  jnz     loc_140031B08
0x140031995  xor     r14b, r14b
0x140031998  lea     rcx, aFalse; "FALSE"
0x14003199f  lea     rax, aTrue; "TRUE"
0x1400319a6  test    r14b, r14b
0x1400319a9  cmovz   rax, rcx
0x1400319ad  mov     [rsp+1D0h+var_1B0], rax
0x1400319b2  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x1400319b9  mov     r8d, 0AAh; unsigned int
0x1400319bf  lea     rdx, aReturn; "RETURN"
0x1400319c6  lea     rcx, [rsp+1D0h+var_170]; this
0x1400319cb  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1400319d0  nop
0x1400319d1  mov     rcx, [rbp+0D0h+pv]; pv
0x1400319d5  call    cs:__imp_CoTaskMemFree
0x1400319db  mov     [rbp+0D0h+pv], r15
0x1400319df  mov     rcx, [rbp+0D0h+pv+8]; pv
0x1400319e3  call    cs:__imp_CoTaskMemFree
0x1400319e9  mov     [rbp+0D0h+pv+8], r15
0x1400319ed  mov     rcx, [rbp+0D0h+var_120]; pv
0x1400319f1  call    cs:__imp_CoTaskMemFree
0x1400319f7  mov     [rbp+0D0h+var_120], r15
0x1400319fb  mov     rcx, [rbp+0D0h+var_120+8]; pv
0x1400319ff  call    cs:__imp_CoTaskMemFree
0x140031a05  mov     [rbp+0D0h+var_120+8], r15
0x140031a09  call    cs:__imp_GetTickCount
0x140031a0f  mov     esi, eax
0x140031a11  sub     esi, [rbp+0D0h+var_13C]
0x140031a14  mov     eax, 10624DD3h
0x140031a19  mul     esi
0x140031a1b  mov     edi, edx
0x140031a1d  shr     edi, 6
0x140031a20  mov     eax, 88888889h
0x140031a25  mul     edi
0x140031a27  shr     edx, 5
0x140031a2a  imul    ecx, edx, 3Ch ; '<'
0x140031a2d  mov     ebx, edi
0x140031a2f  sub     ebx, ecx
0x140031a31  mov     eax, 45E7B273h
0x140031a36  mul     esi
0x140031a38  mov     r11d, edx
0x140031a3b  shr     r11d, 0Eh
0x140031a3f  mov     eax, 88888889h
0x140031a44  mul     r11d
0x140031a47  shr     edx, 5
0x140031a4a  imul    ecx, edx, 3Ch ; '<'
0x140031a4d  sub     r11d, ecx
0x140031a50  mov     eax, 95217CB1h
0x140031a55  mul     esi
0x140031a57  mov     r10d, edx
0x140031a5a  shr     r10d, 15h
0x140031a5e  mov     eax, 88888889h
0x140031a63  mul     r10d
0x140031a66  shr     edx, 5
0x140031a69  imul    eax, edx, 3Ch ; '<'
0x140031a6c  sub     r10d, eax
0x140031a6f  mov     r9d, [rsp+1D0h+var_168]
0x140031a74  cmp     [rbp+0D0h+var_138], 0FFh
0x140031a7b  cmovnz  r12d, [rbp+0D0h+var_138]
0x140031a80  imul    ecx, edi, 3E8h
0x140031a86  mov     edx, esi
0x140031a88  sub     edx, ecx
0x140031a8a  mov     [rsp+1D0h+var_188], r9d
0x140031a8f  mov     dword ptr [rsp+1D0h+var_190], esi
0x140031a93  mov     dword ptr [rsp+1D0h+var_198], edx
0x140031a97  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x140031a9b  mov     dword ptr [rsp+1D0h+var_1A8], r11d
0x140031aa0  mov     dword ptr [rsp+1D0h+var_1B0], r10d
0x140031aa5  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140031aac  mov     r8d, r12d; unsigned int
0x140031aaf  lea     rdx, aExit; "EXIT"
0x140031ab6  lea     rcx, [rsp+1D0h+var_170]; this
0x140031abb  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140031ac0  mov     rcx, [rbp+0D0h+var_110]
0x140031ac4  call    cs:__imp_VssSetTracingContextPerThread
0x140031aca  movzx   eax, r14b
0x140031ace  mov     rcx, [rbp+0D0h+var_38]
0x140031ad5  xor     rcx, rsp; StackCookie
0x140031ad8  call    __security_check_cookie
0x140031add  mov     rbx, [rsp+1D0h+arg_10]
0x140031ae5  add     rsp, 1A0h
0x140031aec  pop     r15
0x140031aee  pop     r14
0x140031af0  pop     r13
0x140031af2  pop     r12
0x140031af4  pop     rdi
0x140031af5  pop     rsi
0x140031af6  pop     rbp
0x140031af7  retn
0x140031af8  call    cs:__imp_CoTaskMemFree
0x140031afe  mov     [rbp+rbx*8+0D0h+var_C8], r15
0x140031b03  jmp     loc_1400318BE
0x140031b08  test    r13b, r13b
0x140031b0b  jnz     loc_140031995
0x140031b11  mov     r14b, 1
0x140031b14  jmp     loc_140031998
0x140031b19  lea     rcx, [rsp+1D0h+var_170]
0x140031b1e  call    cs:__imp_VssSetTracingContextPerThread
0x140031b24  test    eax, eax
0x140031b26  js      loc_140031868
0x140031b2c  mov     rax, [rsp+1D0h+var_180]
0x140031b31  mov     [rbp+0D0h+var_110], rax
0x140031b35  jmp     loc_14003186C
0x140031b3a  cmp     ecx, 1
0x140031b3d  jnz     loc_14003195F
0x140031b43  test    r15d, r15d
0x140031b46  jnz     short loc_140031BA9
0x140031b48  lea     rdx, [r9+8]; pSid2
0x140031b4c  mov     rcx, r14; pSid1
0x140031b4f  call    cs:__imp_EqualSid
0x140031b55  test    eax, eax
0x140031b57  jnz     short loc_140031BC5
0x140031b59  jmp     loc_14003195F
0x140031b5e  mov     [rbp+0D0h+var_140], r15d
0x140031b62  jmp     loc_14003187D
0x140031b67  mov     [rsp+1D0h+var_190], r15
0x140031b6c  mov     dword ptr [rsp+1D0h+var_198], ebx
0x140031b70  lea     rax, aEnter; "ENTER"
0x140031b77  mov     [rsp+1D0h+var_1A0], rax
0x140031b7c  mov     rax, [rbp+0D0h+var_148]
0x140031b80  mov     [rsp+1D0h+var_1A8], rax
0x140031b85  mov     eax, [rbp+0D0h+var_14C]
0x140031b88  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x140031b8c  mov     r9d, [rbp+0D0h+var_140]
0x140031b90  mov     r8d, [rbp+0D0h+var_150]
0x140031b94  mov     rdx, [rsp+1D0h+var_158]
0x140031b99  mov     rcx, [rsp+1D0h+var_160]
0x140031b9e  call    cs:__imp_VssTraceMessage
0x140031ba4  jmp     loc_1400318A6
0x140031ba9  add     r9, 8; void *
0x140031bad  mov     r8, r14; void *
0x140031bb0  lea     rdx, [rsp+1D0h+var_170]; struct CVssFunctionTracer *
0x140031bb5  mov     rcx, rsi; this
0x140031bb8  call    ?ExpandForVerification@CVssSidCollection@@AEAA_NAEAVCVssFunctionTracer@@PEAX1@Z; CVssSidCollection::ExpandForVerification(CVssFunctionTracer &,void *,void *)
0x140031bbd  test    al, al
0x140031bbf  jz      loc_14003195F
0x140031bc5  mov     r13b, 1
0x140031bc8  jmp     loc_140031974
0x140031bcd  mov     [rbp+0D0h+StringSid], r15
0x140031bd1  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x140031bd8  mov     [rbp+0D0h+var_100], rax
0x140031bdc  lea     rcx, [rbp+0D0h+var_100]
0x140031be0  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void * (*)(void *),&LocalFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x140031be5  lea     rdx, [rbp+0D0h+StringSid]; StringSid
0x140031be9  mov     rcx, r14; Sid
0x140031bec  call    cs:__imp_ConvertSidToStringSidW
0x140031bf2  test    eax, eax
0x140031bf4  jz      loc_140031CAF
0x140031bfa  test    dil, dil
0x140031bfd  jz      short loc_140031C0D
0x140031bff  test    r13b, r13b
0x140031c02  jnz     short loc_140031C0D
0x140031c04  lea     rbx, aAllowed; "allowed"
0x140031c0b  jmp     short loc_140031C25
0x140031c0d  lea     rbx, aDenied; "denied"
0x140031c14  test    dil, dil
0x140031c17  jnz     short loc_140031C25
0x140031c19  test    r13b, r13b
0x140031c1c  lea     rsi, aImplicitely; "implicitely"
0x140031c23  jz      short loc_140031C2C
0x140031c25  lea     rsi, aExplicitely; "explicitely"
0x140031c2c  lea     rax, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x140031c33  mov     [rbp+0D0h+var_F0], rax
0x140031c37  lea     rax, aCvsssidcollect_0; "CVssSidCollection::IsSidAllowedToFire"
0x140031c3e  mov     [rbp+0D0h+var_E8], rax
0x140031c42  lea     rax, aSecsecrc; "SECSECRC"
0x140031c49  mov     [rbp+0D0h+var_E0], rax
  ... truncated ...
```
