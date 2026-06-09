# CAutoSid::CreateBasicSid(WELL_KNOWN_SID_TYPE)

- ea: `0x18003c8d8`
- end: `0x18003cb06`
- name: `?CreateBasicSid@CAutoSid@@QEAAXW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `558`
- prototype: `void __fastcall(CAutoSid *this, enum WELL_KNOWN_SID_TYPE)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ced0`

## callees

- `0x18000212c`
- `0x180002138`
- `0x1800036e8`
- `0x1800048f8`
- `0x1800049b4`
- `0x180033a8c`
- `0x180033c78`
- `0x18003c8d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ca57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ca57`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ca0e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ca0e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003c972`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003ca4d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003c972`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003ca4d`

## string_xrefs

- `0x18003c8f5`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003c901`: `CAutoSid::CreateBasicSid`
- `0x18003c9d0`: `CreateWellKnownSidType`
- `0x18003cab1`: `CreateWellKnownSidType`

## pseudocode

```c
void __fastcall CAutoSid::CreateBasicSid(CAutoSid *this, enum WELL_KNOWN_SID_TYPE a2)
{
  signed int LastError; // eax
  DWORD v5; // ebx
  HLOCAL v6; // rax
  HLOCAL v7; // rbx
  signed int v8; // eax
  void **v9; // [rsp+20h] [rbp-E0h] BYREF
  HLOCAL v10; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v11; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v12; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v13; // [rsp+40h] [rbp-C0h]
  int v14; // [rsp+48h] [rbp-B8h]
  int v15; // [rsp+4Ch] [rbp-B4h]
  int v16; // [rsp+50h] [rbp-B0h]
  _BYTE v17[120]; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+D0h] [rbp-30h]
  LPVOID v19; // [rsp+E0h] [rbp-20h] BYREF
  signed int v20; // [rsp+E8h] [rbp-18h]
  DWORD cbSid; // [rsp+190h] [rbp+90h] BYREF
  int pExceptionObject; // [rsp+198h] [rbp+98h] BYREF

  v11 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v12 = L"CAutoSid::CreateBasicSid";
  v13 = L"SECSECRC";
  v14 = 879;
  v15 = 11;
  v16 = 255;
  v18 = 0x1000000;
  memset_0(v17, 0, sizeof(v17));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v19, (__int64)&v11, 0);
  cbSid = 0;
  CreateWellKnownSid(a2, 0, 0, &cbSid);
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v20 = LastError;
    v11 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v12 = L"CAutoSid::CreateBasicSid";
    v13 = L"SECSECRC";
    v14 = 892;
    v15 = 11;
    v16 = 255;
    v18 = 0x1000000;
    memset_0(v17, 0, sizeof(v17));
    CVssFunctionTracer::CheckForError(&v19, &v11, L"CreateWellKnownSidType");
  }
  v10 = 0;
  v9 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v5 = cbSid;
  CVssAutoGenericValue_Storage<void *,0,void * (*)(void *),&void * LocalFree(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close(&v9);
  v6 = LocalAlloc(0, v5);
  v7 = v6;
  v10 = v6;
  if ( !v6 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  if ( !CreateWellKnownSid(a2, 0, v6, &cbSid) )
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v20 = v8;
    v11 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v12 = L"CAutoSid::CreateBasicSid";
    v13 = L"SECSECRC";
    v14 = 901;
    v15 = 11;
    v16 = 255;
    v18 = 0x1000000;
    memset_0(v17, 0, sizeof(v17));
    CVssFunctionTracer::CheckForError(&v19, &v11, L"CreateWellKnownSidType");
  }
  v10 = 0;
  CVssAutoGenericValue_Storage<void *,0,void * (*)(void *),&void * LocalFree(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close(this);
  *((_QWORD *)this + 1) = v7;
  CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>(&v9);
  CVssFunctionTracer::~CVssFunctionTracer(&v19);
}

```

## disassembly

```asm
0x18003c8d8  mov     [rsp-8+arg_0], rbx
0x18003c8dd  push    rbp
0x18003c8de  push    rsi
0x18003c8df  push    rdi
0x18003c8e0  push    r12
0x18003c8e2  push    r13
0x18003c8e4  lea     rbp, [rsp-50h]
0x18003c8e9  sub     rsp, 150h
0x18003c8f0  mov     esi, edx
0x18003c8f2  mov     rdi, rcx
0x18003c8f5  lea     r12, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003c8fc  mov     [rsp+170h+var_140], r12
0x18003c901  lea     r13, aCautosidCreate; "CAutoSid::CreateBasicSid"
0x18003c908  mov     [rsp+170h+var_138], r13
0x18003c90d  lea     rbx, aSecsecrc; "SECSECRC"
0x18003c914  mov     [rsp+170h+var_130], rbx
0x18003c919  mov     [rsp+170h+var_128], 36Fh
0x18003c921  mov     [rsp+170h+var_124], 0Bh
0x18003c929  mov     [rsp+170h+var_120], 0FFh
0x18003c931  mov     [rbp+70h+var_A0], 1000000h
0x18003c938  xor     edx, edx; Val
0x18003c93a  lea     r8d, [rdx+78h]; Size
0x18003c93e  lea     rcx, [rsp+170h+var_118]; void *
0x18003c943  call    memset_0
0x18003c948  xor     r8d, r8d
0x18003c94b  lea     rdx, [rsp+170h+var_140]
0x18003c950  lea     rcx, [rbp+70h+var_90]
0x18003c954  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003c959  nop
0x18003c95a  mov     [rbp+70h+cbSid], 0
0x18003c964  lea     r9, [rbp+70h+cbSid]; cbSid
0x18003c96b  xor     r8d, r8d; pSid
0x18003c96e  xor     edx, edx; DomainSid
0x18003c970  mov     ecx, esi; WellKnownSidType
0x18003c972  call    cs:__imp_CreateWellKnownSid
0x18003c978  call    cs:__imp_GetLastError
0x18003c97e  cmp     eax, 7Ah ; 'z'
0x18003c981  jz      short loc_18003C9E5
0x18003c983  test    eax, eax
0x18003c985  jle     short loc_18003C98F
0x18003c987  movzx   eax, ax
0x18003c98a  or      eax, 80070000h
0x18003c98f  mov     [rbp+70h+var_88], eax
0x18003c992  mov     [rsp+170h+var_140], r12
0x18003c997  mov     [rsp+170h+var_138], r13
0x18003c99c  mov     [rsp+170h+var_130], rbx
0x18003c9a1  mov     [rsp+170h+var_128], 37Ch
0x18003c9a9  mov     [rsp+170h+var_124], 0Bh
0x18003c9b1  mov     [rsp+170h+var_120], 0FFh
0x18003c9b9  mov     [rbp+70h+var_A0], 1000000h
0x18003c9c0  xor     edx, edx; Val
0x18003c9c2  lea     r8d, [rdx+78h]; Size
0x18003c9c6  lea     rcx, [rsp+170h+var_118]; void *
0x18003c9cb  call    memset_0
0x18003c9d0  lea     r8, aCreatewellknow_0; "CreateWellKnownSidType"
0x18003c9d7  lea     rdx, [rsp+170h+var_140]
0x18003c9dc  lea     rcx, [rbp+70h+var_90]
0x18003c9e0  call    ?CheckForError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForError(CVssDebugInfo,ushort const *)
0x18003c9e5  mov     [rsp+170h+var_148], 0
0x18003c9ee  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x18003c9f5  mov     [rsp+170h+var_150], rax
0x18003c9fa  mov     ebx, [rbp+70h+cbSid]
0x18003ca00  lea     rcx, [rsp+170h+var_150]
0x18003ca05  call    ?Close@?$CVssAutoGenericValue_Storage@PEAX$0A@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<void *,0,void * (*)(void *),&LocalFree(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::Close(void)
0x18003ca0a  mov     edx, ebx; uBytes
0x18003ca0c  xor     ecx, ecx; uFlags
0x18003ca0e  call    cs:__imp_LocalAlloc
0x18003ca14  mov     rbx, rax
0x18003ca17  mov     [rsp+170h+var_148], rax
0x18003ca1c  test    rax, rax
0x18003ca1f  jnz     short loc_18003CA3F
0x18003ca21  mov     [rbp+70h+pExceptionObject], 8007000Eh
0x18003ca2b  lea     rdx, _TI1J; pThrowInfo
0x18003ca32  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x18003ca39  call    _CxxThrowException_0
0x18003ca3f  lea     r9, [rbp+70h+cbSid]; cbSid
0x18003ca46  mov     r8, rbx; pSid
0x18003ca49  xor     edx, edx; DomainSid
0x18003ca4b  mov     ecx, esi; WellKnownSidType
0x18003ca4d  call    cs:__imp_CreateWellKnownSid
0x18003ca53  test    eax, eax
0x18003ca55  jnz     short loc_18003CAC6
0x18003ca57  call    cs:__imp_GetLastError
0x18003ca5d  test    eax, eax
0x18003ca5f  jle     short loc_18003CA69
0x18003ca61  movzx   eax, ax
0x18003ca64  or      eax, 80070000h
0x18003ca69  mov     [rbp+70h+var_88], eax
0x18003ca6c  mov     [rsp+170h+var_140], r12
0x18003ca71  mov     [rsp+170h+var_138], r13
0x18003ca76  lea     rax, aSecsecrc; "SECSECRC"
0x18003ca7d  mov     [rsp+170h+var_130], rax
0x18003ca82  mov     [rsp+170h+var_128], 385h
0x18003ca8a  mov     [rsp+170h+var_124], 0Bh
0x18003ca92  mov     [rsp+170h+var_120], 0FFh
0x18003ca9a  mov     [rbp+70h+var_A0], 1000000h
0x18003caa1  xor     edx, edx; Val
0x18003caa3  lea     r8d, [rdx+78h]; Size
0x18003caa7  lea     rcx, [rsp+170h+var_118]; void *
0x18003caac  call    memset_0
0x18003cab1  lea     r8, aCreatewellknow_0; "CreateWellKnownSidType"
0x18003cab8  lea     rdx, [rsp+170h+var_140]
0x18003cabd  lea     rcx, [rbp+70h+var_90]
0x18003cac1  call    ?CheckForError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForError(CVssDebugInfo,ushort const *)
0x18003cac6  mov     [rsp+170h+var_148], 0
0x18003cacf  mov     rcx, rdi
0x18003cad2  call    ?Close@?$CVssAutoGenericValue_Storage@PEAX$0A@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<void *,0,void * (*)(void *),&LocalFree(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::Close(void)
0x18003cad7  mov     [rdi+8], rbx
0x18003cadb  lea     rcx, [rsp+170h+var_150]
0x18003cae0  call    ??1?$CVssAuto@PEAU_SID@@V?$CVssAllocatingPtr_Storage@PEAU_SID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6APEAX_K@Z$1?LocalAllocate@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>(void)
0x18003cae5  nop
0x18003cae6  lea     rcx, [rbp+70h+var_90]; this
0x18003caea  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003caef  mov     rbx, [rsp+170h+arg_0]
0x18003caf7  add     rsp, 150h
0x18003cafe  pop     r13
0x18003cb00  pop     r12
0x18003cb02  pop     rdi
0x18003cb03  pop     rsi
0x18003cb04  pop     rbp
0x18003cb05  retn
```
