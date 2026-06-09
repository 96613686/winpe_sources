# CVssSidCollection::AddSid(void *,VSS_ACCESS_CONTROL)

- ea: `0x18003bc08`
- end: `0x18003c08a`
- name: `?AddSid@CVssSidCollection@@AEAAXPEAXW4VSS_ACCESS_CONTROL@@@Z`
- size: `1154`
- prototype: `void __fastcall(__int64, void *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003c090`
- `0x18003c4ac`

## callees

- `0x18000212c`
- `0x1800036e8`
- `0x1800049b4`
- `0x180033a8c`
- `0x180033c78`
- `0x1800356ec`
- `0x18003649c`
- `0x1800367b8`
- `0x180037080`
- `0x18003bc08`
- `0x18003c7b8`
- `0x18003cb0c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003bc97`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003bc97`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003bd2f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003bd2f`

## string_xrefs

- `0x18003bc2f`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003bc3b`: `CVssSidCollection::AddSid`
- `0x18003bcdf`: `Invalid SID passed to AddSid`
- `0x18003bd7b`: `Adding SID %s ...`
- `0x18003be7d`: `m_SDWriters.Deny(...)`
- `0x18003bf7b`: `m_SDWriters.Allow(...)`

## pseudocode

```c
void __fastcall CVssSidCollection::AddSid(__int64 a1, void *a2, int a3)
{
  unsigned int v6; // r8d
  unsigned int v7; // r9d
  int v8; // esi
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  int v11; // esi
  unsigned int v12; // r8d
  unsigned int v13; // r9d
  int v14; // ebx
  int v15; // r14d
  int v16; // esi
  int v17; // ebx
  const unsigned __int16 *v18; // [rsp+20h] [rbp-E0h] BYREF
  const wchar_t *v19; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v20; // [rsp+30h] [rbp-D0h]
  int v21; // [rsp+38h] [rbp-C8h]
  int v22; // [rsp+3Ch] [rbp-C4h]
  int v23; // [rsp+40h] [rbp-C0h]
  _BYTE v24[120]; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+C0h] [rbp-40h]
  void **v26; // [rsp+C8h] [rbp-38h] BYREF
  LPWSTR StringSid; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v28; // [rsp+E0h] [rbp-20h] BYREF
  int v29; // [rsp+E8h] [rbp-18h]

  v18 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v19 = L"CVssSidCollection::AddSid";
  v20 = L"SECSECRC";
  v21 = 1456;
  v22 = 11;
  v23 = 255;
  v25 = 0x1000000;
  memset_0(v24, 0, sizeof(v24));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v28, (__int64)&v18, 0);
  if ( !IsValidSid(a2) )
  {
    v18 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v19 = L"CVssSidCollection::AddSid";
    v20 = L"SECSECRC";
    v21 = 1464;
    v22 = 11;
    v23 = 255;
    v25 = 0x1000000;
    memset_0(v24, 0, sizeof(v24));
    CVssFunctionTracer::Throw(&v28, &v18, 2147549183LL, L"Invalid SID passed to AddSid");
  }
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v28) )
  {
    StringSid = 0;
    v26 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
    CVssAutoGenericValue_Storage<void *,0,void * (*)(void *),&void * LocalFree(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close(&v26);
    if ( ConvertSidToStringSidW(a2, &StringSid) )
    {
      v18 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v19 = L"CVssSidCollection::AddSid";
      v20 = L"SECSECRC";
      v21 = 1475;
      v22 = 11;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::Trace(&v28, &v18, L"Adding SID %s ...", StringSid);
    }
    CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>(&v26);
  }
  if ( a3 )
  {
    if ( (unsigned int)(a3 - 2) <= 1 )
    {
      v15 = CVssSecurityDescriptor::Allow((CVssSecurityDescriptor *)(a1 + 40), a2, v6, v7);
      v29 = v15;
      if ( v15 < 0 )
      {
        v18 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
        v19 = L"CVssSidCollection::AddSid";
        v20 = L"SECSECRC";
        v21 = 1523;
        v22 = 11;
        v23 = 255;
        v25 = 0x1000000;
        memset_0(v24, 0, sizeof(v24));
        CVssFunctionTracer::TranslateGenericError(&v28, &v18, (unsigned int)v15, L"m_SDRequestors.Allow(...)");
      }
      if ( a3 == 3 )
        goto LABEL_18;
    }
    if ( a3 == 1 )
    {
LABEL_18:
      v16 = CVssSecurityDescriptor::Allow((CVssSecurityDescriptor *)(a1 + 8), a2, v6, v7);
      v29 = v16;
      if ( v16 < 0 )
      {
        v18 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
        v19 = L"CVssSidCollection::AddSid";
        v20 = L"SECSECRC";
        v21 = 1536;
        v22 = 11;
        v23 = 255;
        v25 = 0x1000000;
        memset_0(v24, 0, sizeof(v24));
        CVssFunctionTracer::TranslateGenericError(&v28, &v18, (unsigned int)v16, L"m_SDWriters.Allow(...)");
      }
    }
    v17 = CVssSecurityDescriptor::Allow((CVssSecurityDescriptor *)(a1 + 72), a2, v6, v7);
    v29 = v17;
    if ( v17 < 0 )
    {
      v18 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v19 = L"CVssSidCollection::AddSid";
      v20 = L"SECSECRC";
      v21 = 1547;
      v22 = 11;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::TranslateGenericError(&v28, &v18, (unsigned int)v17, L"m_SDBoth.Allow(...)");
    }
  }
  else
  {
    v8 = CVssSecurityDescriptor::Deny((CVssSecurityDescriptor *)(a1 + 40), a2, v6, v7);
    v29 = v8;
    if ( v8 < 0 )
    {
      v18 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v19 = L"CVssSidCollection::AddSid";
      v20 = L"SECSECRC";
      v21 = 1489;
      v22 = 11;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::TranslateGenericError(&v28, &v18, (unsigned int)v8, L"m_SDRequestors.Deny(...)");
    }
    v11 = CVssSecurityDescriptor::Deny((CVssSecurityDescriptor *)(a1 + 8), a2, v9, v10);
    v29 = v11;
    if ( v11 < 0 )
    {
      v18 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v19 = L"CVssSidCollection::AddSid";
      v20 = L"SECSECRC";
      v21 = 1499;
      v22 = 11;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::TranslateGenericError(&v28, &v18, (unsigned int)v11, L"m_SDWriters.Deny(...)");
    }
    v14 = CVssSecurityDescriptor::Deny((CVssSecurityDescriptor *)(a1 + 72), a2, v12, v13);
    v29 = v14;
    if ( v14 < 0 )
    {
      v18 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v19 = L"CVssSidCollection::AddSid";
      v20 = L"SECSECRC";
      v21 = 1509;
      v22 = 11;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::TranslateGenericError(&v28, &v18, (unsigned int)v14, L"m_SDBoth.Deny(...)");
    }
  }
  CVssFunctionTracer::~CVssFunctionTracer(&v28);
}

```

## disassembly

```asm
0x18003bc08  mov     [rsp-8+arg_0], rbx
0x18003bc0d  mov     [rsp-8+arg_8], rsi
0x18003bc12  push    rbp
0x18003bc13  push    rdi
0x18003bc14  push    r12
0x18003bc16  push    r13
0x18003bc18  push    r14
0x18003bc1a  lea     rbp, [rsp-50h]
0x18003bc1f  sub     rsp, 150h
0x18003bc26  mov     esi, r8d
0x18003bc29  mov     rbx, rdx
0x18003bc2c  mov     rdi, rcx
0x18003bc2f  lea     r12, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003bc36  mov     [rsp+170h+var_150], r12
0x18003bc3b  lea     r13, aCvsssidcollect_0; "CVssSidCollection::AddSid"
0x18003bc42  mov     [rsp+170h+var_148], r13
0x18003bc47  lea     r14, aSecsecrc; "SECSECRC"
0x18003bc4e  mov     [rsp+170h+var_140], r14
0x18003bc53  mov     [rsp+170h+var_138], 5B0h
0x18003bc5b  mov     [rsp+170h+var_134], 0Bh
0x18003bc63  mov     [rsp+170h+var_130], 0FFh
0x18003bc6b  mov     [rbp+70h+var_B0], 1000000h
0x18003bc72  xor     edx, edx; Val
0x18003bc74  lea     r8d, [rdx+78h]; Size
0x18003bc78  lea     rcx, [rsp+170h+var_128]; void *
0x18003bc7d  call    memset_0
0x18003bc82  xor     r8d, r8d
0x18003bc85  lea     rdx, [rsp+170h+var_150]
0x18003bc8a  lea     rcx, [rbp+70h+var_90]
0x18003bc8e  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003bc93  nop
0x18003bc94  mov     rcx, rbx; pSid
0x18003bc97  call    cs:__imp_IsValidSid
0x18003bc9d  test    eax, eax
0x18003bc9f  jnz     short loc_18003BCFB
0x18003bca1  mov     [rsp+170h+var_150], r12
0x18003bca6  mov     [rsp+170h+var_148], r13
0x18003bcab  mov     [rsp+170h+var_140], r14
0x18003bcb0  mov     [rsp+170h+var_138], 5B8h
0x18003bcb8  mov     [rsp+170h+var_134], 0Bh
0x18003bcc0  mov     [rsp+170h+var_130], 0FFh
0x18003bcc8  mov     [rbp+70h+var_B0], 1000000h
0x18003bccf  xor     edx, edx; Val
0x18003bcd1  lea     r8d, [rax+78h]; Size
0x18003bcd5  lea     rcx, [rsp+170h+var_128]; void *
0x18003bcda  call    memset_0
0x18003bcdf  lea     r9, aInvalidSidPass; "Invalid SID passed to AddSid"
0x18003bce6  mov     r8d, 8000FFFFh
0x18003bcec  lea     rdx, [rsp+170h+var_150]
0x18003bcf1  lea     rcx, [rbp+70h+var_90]
0x18003bcf5  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003bcfb  lea     rcx, [rbp+70h+var_90]; this
0x18003bcff  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x18003bd04  test    eax, eax
0x18003bd06  jz      loc_18003BD99
0x18003bd0c  mov     [rbp+70h+StringSid], 0
0x18003bd14  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x18003bd1b  mov     [rbp+70h+var_A8], rax
0x18003bd1f  lea     rcx, [rbp+70h+var_A8]
0x18003bd23  call    ?Close@?$CVssAutoGenericValue_Storage@PEAX$0A@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<void *,0,void * (*)(void *),&LocalFree(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::Close(void)
0x18003bd28  lea     rdx, [rbp+70h+StringSid]; StringSid
0x18003bd2c  mov     rcx, rbx; Sid
0x18003bd2f  call    cs:__imp_ConvertSidToStringSidW
0x18003bd35  test    eax, eax
0x18003bd37  jz      short loc_18003BD90
0x18003bd39  mov     [rsp+170h+var_150], r12
0x18003bd3e  mov     [rsp+170h+var_148], r13
0x18003bd43  mov     [rsp+170h+var_140], r14
0x18003bd48  mov     [rsp+170h+var_138], 5C3h
0x18003bd50  mov     [rsp+170h+var_134], 0Bh
0x18003bd58  mov     [rsp+170h+var_130], 0FFh
0x18003bd60  mov     [rbp+70h+var_B0], 1000000h
0x18003bd67  xor     edx, edx; Val
0x18003bd69  lea     r8d, [rdx+78h]; Size
0x18003bd6d  lea     rcx, [rsp+170h+var_128]; void *
0x18003bd72  call    memset_0
0x18003bd77  mov     r9, [rbp+70h+StringSid]
0x18003bd7b  lea     r8, aAddingSidS; "Adding SID %s ..."
0x18003bd82  lea     rdx, [rsp+170h+var_150]
0x18003bd87  lea     rcx, [rbp+70h+var_90]
0x18003bd8b  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003bd90  lea     rcx, [rbp+70h+var_A8]
0x18003bd94  call    ??1?$CVssAuto@PEAU_SID@@V?$CVssAllocatingPtr_Storage@PEAU_SID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6APEAX_K@Z$1?LocalAllocate@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>(void)
0x18003bd99  test    esi, esi
0x18003bd9b  jnz     loc_18003BEED
0x18003bda1  lea     rcx, [rdi+28h]; this
0x18003bda5  mov     rdx, rbx; void *
0x18003bda8  call    ?Deny@CVssSecurityDescriptor@@QEAAJPEAXKK@Z; CVssSecurityDescriptor::Deny(void *,ulong,ulong)
0x18003bdad  mov     esi, eax
0x18003bdaf  mov     [rbp+70h+var_88], eax
0x18003bdb2  test    eax, eax
0x18003bdb4  js      loc_18003BE96
0x18003bdba  lea     rcx, [rdi+8]; this
0x18003bdbe  mov     rdx, rbx; void *
0x18003bdc1  call    ?Deny@CVssSecurityDescriptor@@QEAAJPEAXKK@Z; CVssSecurityDescriptor::Deny(void *,ulong,ulong)
0x18003bdc6  mov     esi, eax
0x18003bdc8  mov     [rbp+70h+var_88], eax
0x18003bdcb  test    eax, eax
0x18003bdcd  js      short loc_18003BE3F
0x18003bdcf  lea     rcx, [rdi+48h]; this
0x18003bdd3  mov     rdx, rbx; void *
0x18003bdd6  call    ?Deny@CVssSecurityDescriptor@@QEAAJPEAXKK@Z; CVssSecurityDescriptor::Deny(void *,ulong,ulong)
0x18003bddb  mov     ebx, eax
0x18003bddd  mov     [rbp+70h+var_88], eax
0x18003bde0  test    eax, eax
0x18003bde2  jns     loc_18003C007
0x18003bde8  mov     [rsp+170h+var_150], r12
0x18003bded  mov     [rsp+170h+var_148], r13
0x18003bdf2  mov     [rsp+170h+var_140], r14
0x18003bdf7  mov     [rsp+170h+var_138], 5E5h
0x18003bdff  mov     [rsp+170h+var_134], 0Bh
0x18003be07  mov     [rsp+170h+var_130], 0FFh
0x18003be0f  mov     [rbp+70h+var_B0], 1000000h
0x18003be16  xor     edx, edx; Val
0x18003be18  lea     r8d, [rdx+78h]; Size
0x18003be1c  lea     rcx, [rsp+170h+var_128]; void *
0x18003be21  call    memset_0
0x18003be26  lea     r9, aMSdbothDeny; "m_SDBoth.Deny(...)"
0x18003be2d  mov     r8d, ebx
0x18003be30  lea     rdx, [rsp+170h+var_150]
0x18003be35  lea     rcx, [rbp+70h+var_90]
0x18003be39  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003be3f  mov     [rsp+170h+var_150], r12
0x18003be44  mov     [rsp+170h+var_148], r13
0x18003be49  mov     [rsp+170h+var_140], r14
0x18003be4e  mov     [rsp+170h+var_138], 5DBh
0x18003be56  mov     [rsp+170h+var_134], 0Bh
0x18003be5e  mov     [rsp+170h+var_130], 0FFh
0x18003be66  mov     [rbp+70h+var_B0], 1000000h
0x18003be6d  xor     edx, edx; Val
0x18003be6f  lea     r8d, [rdx+78h]; Size
0x18003be73  lea     rcx, [rsp+170h+var_128]; void *
0x18003be78  call    memset_0
0x18003be7d  lea     r9, aMSdwritersDeny; "m_SDWriters.Deny(...)"
0x18003be84  mov     r8d, esi
0x18003be87  lea     rdx, [rsp+170h+var_150]
0x18003be8c  lea     rcx, [rbp+70h+var_90]
0x18003be90  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003be96  mov     [rsp+170h+var_150], r12
0x18003be9b  mov     [rsp+170h+var_148], r13
0x18003bea0  mov     [rsp+170h+var_140], r14
0x18003bea5  mov     [rsp+170h+var_138], 5D1h
0x18003bead  mov     [rsp+170h+var_134], 0Bh
0x18003beb5  mov     [rsp+170h+var_130], 0FFh
0x18003bebd  mov     [rbp+70h+var_B0], 1000000h
0x18003bec4  xor     edx, edx; Val
0x18003bec6  lea     r8d, [rdx+78h]; Size
0x18003beca  lea     rcx, [rsp+170h+var_128]; void *
0x18003becf  call    memset_0
0x18003bed4  lea     r9, aMSdrequestorsD; "m_SDRequestors.Deny(...)"
0x18003bedb  mov     r8d, esi
0x18003bede  lea     rdx, [rsp+170h+var_150]
0x18003bee3  lea     rcx, [rbp+70h+var_90]
0x18003bee7  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003beed  lea     eax, [rsi-2]
0x18003bef0  cmp     eax, 1
0x18003bef3  ja      short loc_18003BF14
0x18003bef5  lea     rcx, [rdi+28h]; this
0x18003bef9  mov     rdx, rbx; void *
0x18003befc  call    ?Allow@CVssSecurityDescriptor@@QEAAJPEAXKK@Z; CVssSecurityDescriptor::Allow(void *,ulong,ulong)
0x18003bf01  mov     r14d, eax
0x18003bf04  mov     [rbp+70h+var_88], eax
0x18003bf07  test    eax, eax
0x18003bf09  js      loc_18003BF94
0x18003bf0f  cmp     esi, 3
0x18003bf12  jz      short loc_18003BF1D
0x18003bf14  cmp     esi, 1
0x18003bf17  jnz     loc_18003BFF2
0x18003bf1d  lea     rcx, [rdi+8]; this
0x18003bf21  mov     rdx, rbx; void *
0x18003bf24  call    ?Allow@CVssSecurityDescriptor@@QEAAJPEAXKK@Z; CVssSecurityDescriptor::Allow(void *,ulong,ulong)
0x18003bf29  mov     esi, eax
0x18003bf2b  mov     [rbp+70h+var_88], eax
0x18003bf2e  test    eax, eax
0x18003bf30  jns     loc_18003BFF2
0x18003bf36  mov     [rsp+170h+var_150], r12
0x18003bf3b  mov     [rsp+170h+var_148], r13
0x18003bf40  lea     rax, aSecsecrc; "SECSECRC"
0x18003bf47  mov     [rsp+170h+var_140], rax
0x18003bf4c  mov     [rsp+170h+var_138], 600h
0x18003bf54  mov     [rsp+170h+var_134], 0Bh
0x18003bf5c  mov     [rsp+170h+var_130], 0FFh
0x18003bf64  mov     [rbp+70h+var_B0], 1000000h
0x18003bf6b  xor     edx, edx; Val
0x18003bf6d  lea     r8d, [rdx+78h]; Size
0x18003bf71  lea     rcx, [rsp+170h+var_128]; void *
0x18003bf76  call    memset_0
0x18003bf7b  lea     r9, aMSdwritersAllo; "m_SDWriters.Allow(...)"
0x18003bf82  mov     r8d, esi
0x18003bf85  lea     rdx, [rsp+170h+var_150]
0x18003bf8a  lea     rcx, [rbp+70h+var_90]
0x18003bf8e  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003bf94  mov     [rsp+170h+var_150], r12
0x18003bf99  mov     [rsp+170h+var_148], r13
0x18003bf9e  lea     rax, aSecsecrc; "SECSECRC"
0x18003bfa5  mov     [rsp+170h+var_140], rax
0x18003bfaa  mov     [rsp+170h+var_138], 5F3h
0x18003bfb2  mov     [rsp+170h+var_134], 0Bh
0x18003bfba  mov     [rsp+170h+var_130], 0FFh
0x18003bfc2  mov     [rbp+70h+var_B0], 1000000h
0x18003bfc9  xor     edx, edx; Val
0x18003bfcb  lea     r8d, [rdx+78h]; Size
0x18003bfcf  lea     rcx, [rsp+170h+var_128]; void *
0x18003bfd4  call    memset_0
0x18003bfd9  lea     r9, aMSdrequestorsA; "m_SDRequestors.Allow(...)"
0x18003bfe0  mov     r8d, r14d
0x18003bfe3  lea     rdx, [rsp+170h+var_150]
0x18003bfe8  lea     rcx, [rbp+70h+var_90]
0x18003bfec  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003bff2  lea     rcx, [rdi+48h]; this
0x18003bff6  mov     rdx, rbx; void *
0x18003bff9  call    ?Allow@CVssSecurityDescriptor@@QEAAJPEAXKK@Z; CVssSecurityDescriptor::Allow(void *,ulong,ulong)
0x18003bffe  mov     ebx, eax
0x18003c000  mov     [rbp+70h+var_88], eax
0x18003c003  test    eax, eax
0x18003c005  js      short loc_18003C02C
0x18003c007  lea     rcx, [rbp+70h+var_90]; this
0x18003c00b  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003c010  lea     r11, [rsp+170h+var_20]
0x18003c018  mov     rbx, [r11+30h]
0x18003c01c  mov     rsi, [r11+38h]
0x18003c020  mov     rsp, r11
0x18003c023  pop     r14
0x18003c025  pop     r13
0x18003c027  pop     r12
0x18003c029  pop     rdi
0x18003c02a  pop     rbp
0x18003c02b  retn
0x18003c02c  mov     [rsp+170h+var_150], r12
0x18003c031  mov     [rsp+170h+var_148], r13
0x18003c036  lea     rax, aSecsecrc; "SECSECRC"
0x18003c03d  mov     [rsp+170h+var_140], rax
0x18003c042  mov     [rsp+170h+var_138], 60Bh
0x18003c04a  mov     [rsp+170h+var_134], 0Bh
0x18003c052  mov     [rsp+170h+var_130], 0FFh
0x18003c05a  mov     [rbp+70h+var_B0], 1000000h
0x18003c061  xor     edx, edx; Val
0x18003c063  lea     r8d, [rdx+78h]; Size
0x18003c067  lea     rcx, [rsp+170h+var_128]; void *
0x18003c06c  call    memset_0
0x18003c071  lea     r9, aMSdbothAllow; "m_SDBoth.Allow(...)"
0x18003c078  mov     r8d, ebx
0x18003c07b  lea     rdx, [rsp+170h+var_150]
0x18003c080  lea     rcx, [rbp+70h+var_90]
0x18003c084  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
```
