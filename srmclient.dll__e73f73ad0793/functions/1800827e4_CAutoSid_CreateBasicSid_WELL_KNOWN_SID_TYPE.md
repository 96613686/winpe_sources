# CAutoSid::CreateBasicSid(WELL_KNOWN_SID_TYPE)

- ea: `0x1800827e4`
- end: `0x180082ae1`
- name: `?CreateBasicSid@CAutoSid@@QEAAXW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `765`
- prototype: `void __fastcall(CAutoSid *__hidden this, enum WELL_KNOWN_SID_TYPE)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180096d3c`

## callees

- `0x18006fdf0`
- `0x18006febc`
- `0x18007006c`
- `0x1800700b8`
- `0x180074874`
- `0x180082388`
- `0x1800827e4`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180082898`
- `KERNEL32!GetLastError` at `0x180082983`
- `KERNEL32!GetLastError` at `0x180082898`
- `KERNEL32!GetLastError` at `0x180082983`
- `KERNEL32!LocalFree` at `0x180082a1d`
- `KERNEL32!LocalFree` at `0x180082a1d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180082892`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180082975`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180082892`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180082975`

## string_xrefs

- `0x18008281a`: `base\fs\fsrm\utilities\security\srmsec.cpp`
- `0x180082825`: `CAutoSid::CreateBasicSid`
- `0x1800829a0`: `CAutoSid::CreateBasicSid`
- `0x180082a95`: `CreateWellKnownSidType`
- `0x180082ac7`: `CreateWellKnownSidType`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CAutoSid::CreateBasicSid(CAutoSid *this, enum WELL_KNOWN_SID_TYPE a2)
{
  signed int LastError; // eax
  PSID v4; // rdi
  signed int v5; // eax
  void *v6; // rcx
  CSrmDebugInfo *v7; // rax
  unsigned int v8; // r10d
  CSrmDebugInfo *v9; // rax
  unsigned int v10; // r10d
  DWORD cbSid; // [rsp+20h] [rbp-E0h] BYREF
  void **v12; // [rsp+28h] [rbp-D8h] BYREF
  PSID pSid; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 **v14; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 **v15; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v16; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v17; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+64h] [rbp-9Ch]
  int v21; // [rsp+68h] [rbp-98h]
  _BYTE v22[96]; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+D0h] [rbp-30h]
  _QWORD v24[3]; // [rsp+D8h] [rbp-28h] BYREF
  int v25; // [rsp+F0h] [rbp-10h]
  int v26; // [rsp+F4h] [rbp-Ch]
  int v27; // [rsp+F8h] [rbp-8h]
  _BYTE v28[96]; // [rsp+100h] [rbp+0h] BYREF
  int v29; // [rsp+160h] [rbp+60h]
  _BYTE v30[152]; // [rsp+168h] [rbp+68h] BYREF
  void **v31; // [rsp+200h] [rbp+100h] BYREF
  int v32; // [rsp+208h] [rbp+108h]

  v14 = (const unsigned __int16 **)v24;
  v24[0] = L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp";
  v24[1] = L"CAutoSid::CreateBasicSid";
  v24[2] = L"SECSECRC";
  v25 = 1238;
  v26 = 17;
  v27 = 255;
  v29 = 0x1000000;
  memset_0(v28, 0, sizeof(v28));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v31, (const struct CSrmDebugInfo *)v24, 0);
  cbSid = 0;
  CreateWellKnownSid(WinNullSid, 0, 0, &cbSid);
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v32 = LastError;
    v16 = L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp";
    v17 = L"CAutoSid::CreateBasicSid";
    v18 = L"SECSECRC";
    v19 = 1248;
    v20 = 17;
    v21 = 255;
    v23 = 0x1000000;
    memset_0(v22, 0, sizeof(v22));
    v15 = &v16;
    if ( v32 < 0 )
    {
      v14 = (const unsigned __int16 **)v30;
      v7 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v30, (const struct CSrmDebugInfo *)&v16);
      CSrmFunctionTracer::TranslateError(&v31, v7, v8, L"CreateWellKnownSidType");
    }
    CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)&v16);
  }
  pSid = 0;
  v12 = &CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable';
  CSrmAutoLocalPtr_Storage<_SID *>::AllocateBytes(&v12, cbSid);
  v4 = pSid;
  if ( !CreateWellKnownSid(WinNullSid, 0, pSid, &cbSid) )
  {
    v5 = GetLastError();
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    v32 = v5;
    v16 = L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp";
    v17 = L"CAutoSid::CreateBasicSid";
    v18 = L"SECSECRC";
    v19 = 1257;
    v20 = 17;
    v21 = 255;
    v23 = 0x1000000;
    memset_0(v22, 0, sizeof(v22));
    v14 = &v16;
    if ( v32 < 0 )
    {
      v15 = (const unsigned __int16 **)v30;
      v9 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v30, (const struct CSrmDebugInfo *)&v16);
      CSrmFunctionTracer::TranslateError(&v31, v9, v10, L"CreateWellKnownSidType");
    }
    CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)&v16);
  }
  pSid = 0;
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
    LocalFree(v6);
  *((_QWORD *)this + 1) = v4;
  v12 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
  pSid = 0;
  v31 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v31);
}

```

## disassembly

```asm
0x1800827e4  push    rbp
0x1800827e6  push    rbx
0x1800827e7  push    rdi
0x1800827e8  push    r13
0x1800827ea  push    r14
0x1800827ec  push    r15
0x1800827ee  lea     rbp, [rsp-1C8h]
0x1800827f6  sub     rsp, 2C8h
0x1800827fd  mov     rax, cs:__security_cookie
0x180082804  xor     rax, rsp
0x180082807  mov     [rbp+1F0h+var_40], rax
0x18008280e  mov     rbx, rcx
0x180082811  lea     rax, [rbp+1F0h+var_218]
0x180082815  mov     [rsp+2F0h+var_2B8], rax
0x18008281a  lea     r13, aBaseFsFsrmUtil_11; "base\\fs\\fsrm\\utilities\\security\\sr"...
0x180082821  mov     [rbp+1F0h+var_218], r13
0x180082825  lea     rdi, aCautosidCreate; "CAutoSid::CreateBasicSid"
0x18008282c  mov     [rbp+1F0h+var_210], rdi
0x180082830  lea     r14, aSecsecrc; "SECSECRC"
0x180082837  mov     [rbp+1F0h+var_208], r14
0x18008283b  mov     [rbp+1F0h+var_200], 4D6h
0x180082842  mov     r15d, 11h
0x180082848  mov     [rbp+1F0h+var_1FC], r15d
0x18008284c  mov     [rbp+1F0h+var_1F8], 0FFh
0x180082853  mov     [rbp+1F0h+var_190], 1000000h
0x18008285a  xor     edx, edx; Val
0x18008285c  lea     r8d, [r15+4Fh]; Size
0x180082860  lea     rcx, [rbp+1F0h+var_1F0]; void *
0x180082864  call    memset_0
0x180082869  nop
0x18008286a  xor     r8d, r8d
0x18008286d  lea     rdx, [rbp+1F0h+var_218]
0x180082871  lea     rcx, [rbp+1F0h+var_F0]
0x180082878  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18008287d  nop
0x18008287e  mov     [rsp+2F0h+cbSid], 0
0x180082886  lea     r9, [rsp+2F0h+cbSid]; cbSid
0x18008288b  xor     r8d, r8d; pSid
0x18008288e  xor     edx, edx; DomainSid
0x180082890  xor     ecx, ecx; WellKnownSidType
0x180082892  call    cs:__imp_CreateWellKnownSid
0x180082898  call    cs:__imp_GetLastError
0x18008289e  cmp     eax, 7Ah ; 'z'
0x1800828a1  jz      short loc_180082914
0x1800828a3  test    eax, eax
0x1800828a5  jle     short loc_1800828AF
0x1800828a7  movzx   eax, ax
0x1800828aa  or      eax, 80070000h
0x1800828af  mov     [rbp+1F0h+var_E8], eax
0x1800828b5  mov     [rsp+2F0h+var_2A8], r13
0x1800828ba  mov     [rsp+2F0h+var_2A0], rdi
0x1800828bf  mov     [rsp+2F0h+var_298], r14
0x1800828c4  mov     [rsp+2F0h+var_290], 4E0h
0x1800828cc  mov     [rsp+2F0h+var_28C], r15d
0x1800828d1  mov     [rsp+2F0h+var_288], 0FFh
0x1800828d9  mov     [rbp+1F0h+var_220], 1000000h
0x1800828e0  xor     edx, edx; Val
0x1800828e2  lea     r8d, [rdx+60h]; Size
0x1800828e6  lea     rcx, [rsp+2F0h+var_280]; void *
0x1800828eb  call    memset_0
0x1800828f0  lea     rax, [rsp+2F0h+var_2A8]
0x1800828f5  mov     [rsp+2F0h+var_2B0], rax
0x1800828fa  mov     r10d, [rbp+1F0h+var_E8]
0x180082901  test    r10d, r10d
0x180082904  js      loc_180082A7D
0x18008290a  lea     rcx, [rsp+2F0h+var_2A8]; this
0x18008290f  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180082914  lea     r14, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x18008291b  mov     [rsp+2F0h+var_2C8], r14
0x180082920  mov     [rsp+2F0h+pSid], 0
0x180082929  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAE@@6B@; const CSrmAutoLocalPtr_Storage<uchar *>::`vftable'
0x180082930  mov     [rsp+2F0h+var_2C8], rax
0x180082935  lea     r15, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x18008293c  mov     [rsp+2F0h+var_2C8], r15
0x180082941  mov     [rsp+2F0h+pSid], 0
0x18008294a  lea     rax, ??_7?$CSrmAutoLocalPtr@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@6B@; const CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable'
0x180082951  mov     [rsp+2F0h+var_2C8], rax
0x180082956  mov     edx, [rsp+2F0h+cbSid]
0x18008295a  lea     rcx, [rsp+2F0h+var_2C8]
0x18008295f  call    ?AllocateBytes@?$CSrmAutoLocalPtr_Storage@PEAU_SID@@@@QEAAX_K@Z; CSrmAutoLocalPtr_Storage<_SID *>::AllocateBytes(unsigned __int64)
0x180082964  lea     r9, [rsp+2F0h+cbSid]; cbSid
0x180082969  mov     rdi, [rsp+2F0h+pSid]
0x18008296e  mov     r8, rdi; pSid
0x180082971  xor     edx, edx; DomainSid
0x180082973  xor     ecx, ecx; WellKnownSidType
0x180082975  call    cs:__imp_CreateWellKnownSid
0x18008297b  test    eax, eax
0x18008297d  jnz     loc_180082A0B
0x180082983  call    cs:__imp_GetLastError
0x180082989  test    eax, eax
0x18008298b  jle     short loc_180082995
0x18008298d  movzx   eax, ax
0x180082990  or      eax, 80070000h
0x180082995  mov     [rbp+1F0h+var_E8], eax
0x18008299b  mov     [rsp+2F0h+var_2A8], r13
0x1800829a0  lea     rax, aCautosidCreate; "CAutoSid::CreateBasicSid"
0x1800829a7  mov     [rsp+2F0h+var_2A0], rax
0x1800829ac  lea     rax, aSecsecrc; "SECSECRC"
0x1800829b3  mov     [rsp+2F0h+var_298], rax
0x1800829b8  mov     [rsp+2F0h+var_290], 4E9h
0x1800829c0  mov     [rsp+2F0h+var_28C], 11h
0x1800829c8  mov     [rsp+2F0h+var_288], 0FFh
0x1800829d0  mov     [rbp+1F0h+var_220], 1000000h
0x1800829d7  xor     edx, edx; Val
0x1800829d9  lea     r8d, [rdx+60h]; Size
0x1800829dd  lea     rcx, [rsp+2F0h+var_280]; void *
0x1800829e2  call    memset_0
0x1800829e7  lea     rax, [rsp+2F0h+var_2A8]
0x1800829ec  mov     [rsp+2F0h+var_2B8], rax
0x1800829f1  mov     r10d, [rbp+1F0h+var_E8]
0x1800829f8  test    r10d, r10d
0x1800829fb  js      loc_180082AAF
0x180082a01  lea     rcx, [rsp+2F0h+var_2A8]; this
0x180082a06  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180082a0b  mov     [rsp+2F0h+pSid], 0
0x180082a14  mov     rcx, [rbx+8]; hMem
0x180082a18  test    rcx, rcx
0x180082a1b  jz      short loc_180082A23
0x180082a1d  call    cs:__imp_LocalFree
0x180082a23  mov     [rbx+8], rdi
0x180082a27  mov     [rsp+2F0h+var_2C8], r15
0x180082a2c  mov     [rsp+2F0h+pSid], 0
0x180082a35  mov     [rsp+2F0h+var_2C8], r14
0x180082a3a  mov     [rsp+2F0h+pSid], 0
0x180082a43  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180082a4a  mov     [rbp+1F0h+var_F0], rax
0x180082a51  lea     rcx, [rbp+1F0h+var_F0]; this
0x180082a58  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180082a5d  mov     rcx, [rbp+1F0h+var_40]
0x180082a64  xor     rcx, rsp; StackCookie
0x180082a67  call    __security_check_cookie
0x180082a6c  add     rsp, 2C8h
0x180082a73  pop     r15
0x180082a75  pop     r14
0x180082a77  pop     r13
0x180082a79  pop     rdi
0x180082a7a  pop     rbx
0x180082a7b  pop     rbp
0x180082a7c  retn
0x180082a7d  lea     rax, [rbp+1F0h+var_188]
0x180082a81  mov     [rsp+2F0h+var_2B8], rax
0x180082a86  lea     rdx, [rsp+2F0h+var_2A8]; struct CSrmDebugInfo *
0x180082a8b  lea     rcx, [rbp+1F0h+var_188]; this
0x180082a8f  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180082a94  nop
0x180082a95  lea     r9, aCreatewellknow; "CreateWellKnownSidType"
0x180082a9c  mov     r8d, r10d
0x180082a9f  mov     rdx, rax
0x180082aa2  lea     rcx, [rbp+1F0h+var_F0]
0x180082aa9  call    ?TranslateError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBG@Z; CSrmFunctionTracer::TranslateError(CSrmDebugInfo,long,ushort const *)
0x180082aaf  lea     rax, [rbp+1F0h+var_188]
0x180082ab3  mov     [rsp+2F0h+var_2B0], rax
0x180082ab8  lea     rdx, [rsp+2F0h+var_2A8]; struct CSrmDebugInfo *
0x180082abd  lea     rcx, [rbp+1F0h+var_188]; this
0x180082ac1  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180082ac6  nop
0x180082ac7  lea     r9, aCreatewellknow; "CreateWellKnownSidType"
0x180082ace  mov     r8d, r10d
0x180082ad1  mov     rdx, rax
0x180082ad4  lea     rcx, [rbp+1F0h+var_F0]
0x180082adb  call    ?TranslateError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBG@Z; CSrmFunctionTracer::TranslateError(CSrmDebugInfo,long,ushort const *)
```
