# CVssSidCollection::AddUser(ushort const *,VSS_ACCESS_CONTROL)

- ea: `0x18003c090`
- end: `0x18003c4a4`
- name: `?AddUser@CVssSidCollection@@AEAAXPEBGW4VSS_ACCESS_CONTROL@@@Z`
- size: `1044`
- prototype: `void __fastcall(__int64, const WCHAR *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ced0`

## callees

- `0x18000212c`
- `0x180002138`
- `0x1800036e8`
- `0x1800049b4`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x1800367b8`
- `0x18003bc08`
- `0x18003c090`
- `0x18003c764`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c328`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c2cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c2cc`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18003c187`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18003c31e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18003c187`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18003c31e`

## string_xrefs

- `0x18003c0b8`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003c1c6`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003c236`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003c330`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003c39c`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003c0c4`: `CVssSidCollection::AddUser`
- `0x18003c1d2`: `CVssSidCollection::AddUser`
- `0x18003c242`: `CVssSidCollection::AddUser`
- `0x18003c33c`: `CVssSidCollection::AddUser`
- `0x18003c3a8`: `CVssSidCollection::AddUser`
- `0x18003c3ff`: `LookupAccountName fails to give SID size for %s, fReturn %d, winerror %d, dwSid %d, dwDomain %d. This key value is ignored.`
- `0x18003c217`: `User %s specified under VssAccessControl key doesn't exist. This key value is ignored.`
- `0x18003c284`: `LookupAccountName fails for %s, winerror %d. This key value in VssAccessControl is ignored.`

## pseudocode

```c
void __fastcall CVssSidCollection::AddUser(__int64 a1, const WCHAR *a2, int a3)
{
  BOOL v6; // r15d
  DWORD LastError; // eax
  DWORD v8; // ebx
  DWORD v9; // r14d
  DWORD v10; // esi
  const wchar_t *v11; // r8
  __int64 v12; // rbx
  WCHAR *v13; // rax
  LPDWORD cchReferencedDomainName; // [rsp+20h] [rbp-E0h]
  PSID_NAME_USE peUse; // [rsp+28h] [rbp-D8h]
  int pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE v17; // [rsp+48h] [rbp-B8h] BYREF
  void **v18; // [rsp+50h] [rbp-B0h] BYREF
  PSID Sid; // [rsp+58h] [rbp-A8h]
  void **v20; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR *v21; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v22; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v23; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v24; // [rsp+80h] [rbp-80h]
  int v25; // [rsp+88h] [rbp-78h]
  int v26; // [rsp+8Ch] [rbp-74h]
  int v27; // [rsp+90h] [rbp-70h]
  _BYTE v28[120]; // [rsp+98h] [rbp-68h] BYREF
  int v29; // [rsp+110h] [rbp+10h]
  LPVOID v30[20]; // [rsp+120h] [rbp+20h] BYREF
  DWORD v31; // [rsp+1D8h] [rbp+D8h] BYREF
  DWORD cbSid; // [rsp+1E8h] [rbp+E8h] BYREF

  v22 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v23 = L"CVssSidCollection::AddUser";
  v24 = L"SECSECRC";
  v25 = 1390;
  v26 = 11;
  v27 = 255;
  v29 = 0x1000000;
  memset_0(v28, 0, sizeof(v28));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v30, (__int64)&v22, 0);
  Sid = 0;
  v18 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v21 = 0;
  v20 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v17 = SidTypeInvalid;
  v31 = 0;
  cbSid = 0;
  if ( !a2 || !*a2 )
  {
    v22 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v23 = L"CVssSidCollection::AddUser";
    v24 = L"SECSECRC";
    v25 = 1405;
    v26 = 11;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    CVssFunctionTracer::Throw(v30, &v22, 2147549183LL, L"Invalid user name argument");
  }
  v6 = LookupAccountNameLocalW(a2, 0, &cbSid, 0, &v31, &v17);
  LastError = GetLastError();
  v8 = LastError;
  v9 = v31;
  v10 = cbSid;
  if ( v6 || !cbSid || !v31 )
  {
    v22 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v23 = L"CVssSidCollection::AddUser";
    v24 = L"SECSECRC";
    v25 = 1412;
    v26 = 11;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    LODWORD(peUse) = v8;
    LODWORD(cchReferencedDomainName) = v6;
    CVssFunctionTracer::Trace(
      v30,
      &v22,
      L"LookupAccountName fails to give SID size for %s, fReturn %d, winerror %d, dwSid %d, dwDomain %d. This key value is ignored.",
      a2,
      cchReferencedDomainName,
      peUse,
      v10,
      v9);
    goto LABEL_17;
  }
  if ( LastError == 1332 )
  {
    v22 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v23 = L"CVssSidCollection::AddUser";
    v24 = L"SECSECRC";
    v25 = 1417;
    v26 = 11;
    v27 = 255;
    v29 = 0x1000000;
    memset_0(v28, 0, sizeof(v28));
    CVssFunctionTracer::Trace(
      v30,
      &v22,
      L"User %s specified under VssAccessControl key doesn't exist. This key value is ignored.",
      a2);
  }
  else
  {
    if ( LastError == 122 )
    {
      CVssAllocatingPtr_Storage<void *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>::AllocateBytes(
        &v18,
        cbSid);
      v12 = v31;
      CVssAutoGenericValue_Storage<void *,0,void * (*)(void *),&void * LocalFree(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close(&v20);
      v13 = (WCHAR *)LocalAlloc(0, 2 * v12 + 2);
      v21 = v13;
      if ( !v13 )
      {
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
      if ( LookupAccountNameLocalW(a2, Sid, &cbSid, v13, &v31, &v17) )
      {
        CVssSidCollection::AddSid(a1, Sid, a3);
        goto LABEL_17;
      }
      v8 = GetLastError();
      v22 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v23 = L"CVssSidCollection::AddUser";
      v24 = L"SECSECRC";
      v25 = 1440;
      v26 = 11;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      v11 = L"LookupAccountName fails unexpectedly for %s, winerror %d. Account ignored.";
    }
    else
    {
      v22 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v23 = L"CVssSidCollection::AddUser";
      v24 = L"SECSECRC";
      v25 = 1422;
      v26 = 11;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      v11 = L"LookupAccountName fails for %s, winerror %d. This key value in VssAccessControl is ignored.";
    }
    LODWORD(cchReferencedDomainName) = v8;
    CVssFunctionTracer::Trace(v30, &v22, v11, a2, cchReferencedDomainName);
  }
LABEL_17:
  CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>(&v20);
  CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>(&v18);
  CVssFunctionTracer::~CVssFunctionTracer(v30);
}

```

## disassembly

```asm
0x18003c090  mov     [rsp-8+arg_0], rbx
0x18003c095  push    rbp
0x18003c096  push    rsi
0x18003c097  push    rdi
0x18003c098  push    r12
0x18003c09a  push    r13
0x18003c09c  push    r14
0x18003c09e  push    r15
0x18003c0a0  lea     rbp, [rsp-90h]
0x18003c0a8  sub     rsp, 190h
0x18003c0af  mov     r12d, r8d
0x18003c0b2  mov     rdi, rdx
0x18003c0b5  mov     r13, rcx
0x18003c0b8  lea     rsi, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003c0bf  mov     [rsp+1C0h+var_150], rsi
0x18003c0c4  lea     r14, aCvsssidcollect_1; "CVssSidCollection::AddUser"
0x18003c0cb  mov     [rsp+1C0h+var_148], r14
0x18003c0d0  lea     r15, aSecsecrc; "SECSECRC"
0x18003c0d7  mov     [rbp+0C0h+var_140], r15
0x18003c0db  mov     [rbp+0C0h+var_138], 56Eh
0x18003c0e2  mov     [rbp+0C0h+var_134], 0Bh
0x18003c0e9  mov     [rbp+0C0h+var_130], 0FFh
0x18003c0f0  xor     ebx, ebx
0x18003c0f2  mov     [rbp+0C0h+var_B0], 1000000h
0x18003c0f9  xor     edx, edx; Val
0x18003c0fb  lea     r8d, [rbx+78h]; Size
0x18003c0ff  lea     rcx, [rbp+0C0h+var_128]; void *
0x18003c103  call    memset_0
0x18003c108  xor     r8d, r8d
0x18003c10b  lea     rdx, [rsp+1C0h+var_150]
0x18003c110  lea     rcx, [rbp+0C0h+var_A0]
0x18003c114  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003c119  nop
0x18003c11a  mov     [rsp+1C0h+Sid], rbx
0x18003c11f  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x18003c126  mov     [rsp+1C0h+var_170], rax
0x18003c12b  mov     [rsp+1C0h+var_158], rbx
0x18003c130  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x18003c137  mov     [rsp+1C0h+var_160], rax
0x18003c13c  mov     [rsp+1C0h+var_178], 7
0x18003c144  mov     [rbp+0C0h+arg_8], ebx
0x18003c14a  mov     [rbp+0C0h+cbSid], ebx
0x18003c150  test    rdi, rdi
0x18003c153  jz      loc_18003C44F
0x18003c159  cmp     [rdi], bx
0x18003c15c  jz      loc_18003C44F
0x18003c162  lea     rax, [rsp+1C0h+var_178]
0x18003c167  mov     [rsp+1C0h+peUse], rax; peUse
0x18003c16c  lea     rax, [rbp+0C0h+arg_8]
0x18003c173  mov     [rsp+1C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003c178  xor     r9d, r9d; ReferencedDomainName
0x18003c17b  lea     r8, [rbp+0C0h+cbSid]; cbSid
0x18003c182  xor     edx, edx; Sid
0x18003c184  mov     rcx, rdi; lpAccountName
0x18003c187  call    cs:__imp_LookupAccountNameLocalW
0x18003c18d  mov     r15d, eax
0x18003c190  call    cs:__imp_GetLastError
0x18003c196  mov     ebx, eax
0x18003c198  mov     r14d, [rbp+0C0h+arg_8]
0x18003c19f  mov     esi, [rbp+0C0h+cbSid]
0x18003c1a5  test    r15d, r15d
0x18003c1a8  jnz     loc_18003C39C
0x18003c1ae  test    esi, esi
0x18003c1b0  jz      loc_18003C39C
0x18003c1b6  test    r14d, r14d
0x18003c1b9  jz      loc_18003C39C
0x18003c1bf  cmp     eax, 534h
0x18003c1c4  jnz     short loc_18003C231
0x18003c1c6  lea     rax, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003c1cd  mov     [rsp+1C0h+var_150], rax
0x18003c1d2  lea     rax, aCvsssidcollect_1; "CVssSidCollection::AddUser"
0x18003c1d9  mov     [rsp+1C0h+var_148], rax
0x18003c1de  lea     rax, aSecsecrc; "SECSECRC"
0x18003c1e5  mov     [rbp+0C0h+var_140], rax
0x18003c1e9  mov     [rbp+0C0h+var_138], 589h
0x18003c1f0  mov     [rbp+0C0h+var_134], 0Bh
0x18003c1f7  mov     [rbp+0C0h+var_130], 0FFh
0x18003c1fe  mov     [rbp+0C0h+var_B0], 1000000h
0x18003c205  xor     edx, edx; Val
0x18003c207  lea     r8d, [r15+78h]; Size
0x18003c20b  lea     rcx, [rbp+0C0h+var_128]; void *
0x18003c20f  call    memset_0
0x18003c214  mov     r9, rdi
0x18003c217  lea     r8, aUserSSpecified; "User %s specified under VssAccessContro"...
0x18003c21e  lea     rdx, [rsp+1C0h+var_150]
0x18003c223  lea     rcx, [rbp+0C0h+var_A0]
0x18003c227  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003c22c  jmp     loc_18003C415
0x18003c231  cmp     ebx, 7Ah ; 'z'
0x18003c234  jz      short loc_18003C2A5
0x18003c236  lea     rax, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003c23d  mov     [rsp+1C0h+var_150], rax
0x18003c242  lea     rax, aCvsssidcollect_1; "CVssSidCollection::AddUser"
0x18003c249  mov     [rsp+1C0h+var_148], rax
0x18003c24e  lea     rax, aSecsecrc; "SECSECRC"
0x18003c255  mov     [rbp+0C0h+var_140], rax
0x18003c259  mov     [rbp+0C0h+var_138], 58Eh
0x18003c260  mov     [rbp+0C0h+var_134], 0Bh
0x18003c267  mov     [rbp+0C0h+var_130], 0FFh
0x18003c26e  mov     [rbp+0C0h+var_B0], 1000000h
0x18003c275  xor     edx, edx; Val
0x18003c277  lea     r8d, [rdx+78h]; Size
0x18003c27b  lea     rcx, [rbp+0C0h+var_128]; void *
0x18003c27f  call    memset_0
0x18003c284  lea     r8, aLookupaccountn_2; "LookupAccountName fails for %s, winerro"...
0x18003c28b  mov     r9, rdi
0x18003c28e  mov     dword ptr [rsp+1C0h+cchReferencedDomainName], ebx
0x18003c292  lea     rdx, [rsp+1C0h+var_150]
0x18003c297  lea     rcx, [rbp+0C0h+var_A0]
0x18003c29b  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003c2a0  jmp     loc_18003C415
0x18003c2a5  mov     rdx, rsi
0x18003c2a8  lea     rcx, [rsp+1C0h+var_170]
0x18003c2ad  call    ?AllocateBytes@?$CVssAllocatingPtr_Storage@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6APEAX_K@Z$1?LocalAllocate@@YAPEAX1@Z@@QEAAX_K@Z; CVssAllocatingPtr_Storage<void *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>::AllocateBytes(unsigned __int64)
0x18003c2b2  mov     ebx, [rbp+0C0h+arg_8]
0x18003c2b8  lea     rcx, [rsp+1C0h+var_160]
0x18003c2bd  call    ?Close@?$CVssAutoGenericValue_Storage@PEAX$0A@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<void *,0,void * (*)(void *),&LocalFree(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::Close(void)
0x18003c2c2  lea     rdx, ds:2[rbx*2]; uBytes
0x18003c2ca  xor     ecx, ecx; uFlags
0x18003c2cc  call    cs:__imp_LocalAlloc
0x18003c2d2  mov     [rsp+1C0h+var_158], rax
0x18003c2d7  test    rax, rax
0x18003c2da  jnz     short loc_18003C2F6
0x18003c2dc  mov     [rsp+1C0h+pExceptionObject], 8007000Eh
0x18003c2e4  lea     rdx, _TI1J; pThrowInfo
0x18003c2eb  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x18003c2f0  call    _CxxThrowException_0
0x18003c2f6  lea     rcx, [rsp+1C0h+var_178]
0x18003c2fb  mov     [rsp+1C0h+peUse], rcx; peUse
0x18003c300  lea     rcx, [rbp+0C0h+arg_8]
0x18003c307  mov     [rsp+1C0h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18003c30c  mov     r9, rax; ReferencedDomainName
0x18003c30f  lea     r8, [rbp+0C0h+cbSid]; cbSid
0x18003c316  mov     rdx, [rsp+1C0h+Sid]; Sid
0x18003c31b  mov     rcx, rdi; lpAccountName
0x18003c31e  call    cs:__imp_LookupAccountNameLocalW
0x18003c324  test    eax, eax
0x18003c326  jnz     short loc_18003C38A
0x18003c328  call    cs:__imp_GetLastError
0x18003c32e  mov     ebx, eax
0x18003c330  lea     rax, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003c337  mov     [rsp+1C0h+var_150], rax
0x18003c33c  lea     rax, aCvsssidcollect_1; "CVssSidCollection::AddUser"
0x18003c343  mov     [rsp+1C0h+var_148], rax
0x18003c348  lea     rax, aSecsecrc; "SECSECRC"
0x18003c34f  mov     [rbp+0C0h+var_140], rax
0x18003c353  mov     [rbp+0C0h+var_138], 5A0h
0x18003c35a  mov     [rbp+0C0h+var_134], 0Bh
0x18003c361  mov     [rbp+0C0h+var_130], 0FFh
0x18003c368  mov     [rbp+0C0h+var_B0], 1000000h
0x18003c36f  xor     edx, edx; Val
0x18003c371  lea     r8d, [rdx+78h]; Size
0x18003c375  lea     rcx, [rbp+0C0h+var_128]; void *
0x18003c379  call    memset_0
0x18003c37e  lea     r8, aLookupaccountn_0; "LookupAccountName fails unexpectedly fo"...
0x18003c385  jmp     loc_18003C28B
0x18003c38a  mov     r8d, r12d
0x18003c38d  mov     rdx, [rsp+1C0h+Sid]
0x18003c392  mov     rcx, r13
0x18003c395  call    ?AddSid@CVssSidCollection@@AEAAXPEAXW4VSS_ACCESS_CONTROL@@@Z; CVssSidCollection::AddSid(void *,VSS_ACCESS_CONTROL)
0x18003c39a  jmp     short loc_18003C415
0x18003c39c  lea     rax, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003c3a3  mov     [rsp+1C0h+var_150], rax
0x18003c3a8  lea     rax, aCvsssidcollect_1; "CVssSidCollection::AddUser"
0x18003c3af  mov     [rsp+1C0h+var_148], rax
0x18003c3b4  lea     rax, aSecsecrc; "SECSECRC"
0x18003c3bb  mov     [rbp+0C0h+var_140], rax
0x18003c3bf  mov     [rbp+0C0h+var_138], 584h
0x18003c3c6  mov     [rbp+0C0h+var_134], 0Bh
0x18003c3cd  mov     [rbp+0C0h+var_130], 0FFh
0x18003c3d4  mov     [rbp+0C0h+var_B0], 1000000h
0x18003c3db  xor     edx, edx; Val
0x18003c3dd  lea     r8d, [rdx+78h]; Size
0x18003c3e1  lea     rcx, [rbp+0C0h+var_128]; void *
0x18003c3e5  call    memset_0
0x18003c3ea  mov     [rsp+1C0h+var_188], r14d
0x18003c3ef  mov     [rsp+1C0h+var_190], esi
0x18003c3f3  mov     dword ptr [rsp+1C0h+peUse], ebx
0x18003c3f7  mov     dword ptr [rsp+1C0h+cchReferencedDomainName], r15d
0x18003c3fc  mov     r9, rdi
0x18003c3ff  lea     r8, aLookupaccountn_1; "LookupAccountName fails to give SID siz"...
0x18003c406  lea     rdx, [rsp+1C0h+var_150]
0x18003c40b  lea     rcx, [rbp+0C0h+var_A0]
0x18003c40f  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003c414  nop
0x18003c415  lea     rcx, [rsp+1C0h+var_160]
0x18003c41a  call    ??1?$CVssAuto@PEAU_SID@@V?$CVssAllocatingPtr_Storage@PEAU_SID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6APEAX_K@Z$1?LocalAllocate@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>(void)
0x18003c41f  nop
0x18003c420  lea     rcx, [rsp+1C0h+var_170]
0x18003c425  call    ??1?$CVssAuto@PEAU_SID@@V?$CVssAllocatingPtr_Storage@PEAU_SID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6APEAX_K@Z$1?LocalAllocate@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>(void)
0x18003c42a  nop
0x18003c42b  lea     rcx, [rbp+0C0h+var_A0]; this
0x18003c42f  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003c434  mov     rbx, [rsp+1C0h+arg_0]
0x18003c43c  add     rsp, 190h
0x18003c443  pop     r15
0x18003c445  pop     r14
0x18003c447  pop     r13
0x18003c449  pop     r12
0x18003c44b  pop     rdi
0x18003c44c  pop     rsi
0x18003c44d  pop     rbp
0x18003c44e  retn
0x18003c44f  mov     [rsp+1C0h+var_150], rsi
0x18003c454  mov     [rsp+1C0h+var_148], r14
0x18003c459  mov     [rbp+0C0h+var_140], r15
0x18003c45d  mov     [rbp+0C0h+var_138], 57Dh
0x18003c464  mov     [rbp+0C0h+var_134], 0Bh
0x18003c46b  mov     [rbp+0C0h+var_130], 0FFh
0x18003c472  mov     [rbp+0C0h+var_B0], 1000000h
0x18003c479  xor     edx, edx; Val
0x18003c47b  lea     r8d, [rdx+78h]; Size
0x18003c47f  lea     rcx, [rbp+0C0h+var_128]; void *
0x18003c483  call    memset_0
0x18003c488  lea     r9, aInvalidUserNam; "Invalid user name argument"
0x18003c48f  mov     r8d, 8000FFFFh
0x18003c495  lea     rdx, [rsp+1C0h+var_150]
0x18003c49a  lea     rcx, [rbp+0C0h+var_A0]
0x18003c49e  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
```
