# CAutoSid::GetAccountName(ushort * *,ushort * *)

- ea: `0x180082ae8`
- end: `0x180082f7a`
- name: `?GetAccountName@CAutoSid@@QEAAHPEAPEAG0@Z`
- size: `1170`
- prototype: `__int64 __fastcall(CAutoSid *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800a9e40`

## callees

- `0x180006a1c`
- `0x18000ad14`
- `0x18006fdf0`
- `0x18006fe68`
- `0x18006febc`
- `0x18007006c`
- `0x1800700b8`
- `0x18007387c`
- `0x18007424c`
- `0x180074874`
- `0x180074a04`
- `0x180082ae8`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180082e40`
- `ole32!CoTaskMemFree` at `0x180082e53`
- `ole32!CoTaskMemFree` at `0x180082e40`
- `ole32!CoTaskMemFree` at `0x180082e53`
- `KERNEL32!GetLastError` at `0x180082bd3`
- `KERNEL32!GetLastError` at `0x180082d26`
- `KERNEL32!GetLastError` at `0x180082bd3`
- `KERNEL32!GetLastError` at `0x180082d26`
- `ADVAPI32!LookupAccountSidW` at `0x180082bcd`
- `ADVAPI32!LookupAccountSidW` at `0x180082d18`
- `ADVAPI32!LookupAccountSidW` at `0x180082bcd`
- `ADVAPI32!LookupAccountSidW` at `0x180082d18`

## string_xrefs

- `0x180082b2a`: `base\fs\fsrm\utilities\security\srmsec.cpp`
- `0x180082d3c`: `base\fs\fsrm\utilities\security\srmsec.cpp`
- `0x180082db1`: `base\fs\fsrm\utilities\security\srmsec.cpp`
- `0x180082b35`: `CAutoSid::GetAccountName`
- `0x180082c4e`: `CAutoSid::GetAccountName`
- `0x180082d48`: `CAutoSid::GetAccountName`
- `0x180082db8`: `CAutoSid::GetAccountName`
- `0x180082f28`: `LookupAccountSid NULL parms`
- `0x180082f60`: `LookupAccountSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CAutoSid::GetAccountName(CAutoSid *this, unsigned __int16 **a2, unsigned __int16 **a3)
{
  signed int LastError; // eax
  unsigned __int64 v8; // rdx
  unsigned __int16 *v9; // rdi
  unsigned __int16 *v10; // rbx
  signed int v11; // eax
  __int64 v12; // rdx
  unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  unsigned int Hr; // ebx
  __int64 v16; // rax
  CSrmDebugInfo *v17; // rax
  unsigned int v18; // r10d
  CSrmDebugInfo *v19; // rax
  unsigned int v20; // r10d
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  LPWSTR ReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR Name; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 **v25; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 **v26; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v27; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v28; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v29; // [rsp+78h] [rbp-88h]
  int v30; // [rsp+80h] [rbp-80h]
  int v31; // [rsp+84h] [rbp-7Ch]
  int v32; // [rsp+88h] [rbp-78h]
  _BYTE v33[96]; // [rsp+90h] [rbp-70h] BYREF
  int v34; // [rsp+F0h] [rbp-10h]
  _QWORD v35[3]; // [rsp+F8h] [rbp-8h] BYREF
  int v36; // [rsp+110h] [rbp+10h]
  int v37; // [rsp+114h] [rbp+14h]
  int v38; // [rsp+118h] [rbp+18h]
  _BYTE v39[96]; // [rsp+120h] [rbp+20h] BYREF
  int v40; // [rsp+180h] [rbp+80h]
  _BYTE v41[152]; // [rsp+188h] [rbp+88h] BYREF
  void **v42; // [rsp+220h] [rbp+120h] BYREF
  int v43; // [rsp+228h] [rbp+128h]

  v25 = (const unsigned __int16 **)v35;
  v35[0] = L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp";
  v35[1] = L"CAutoSid::GetAccountName";
  v35[2] = L"SECSECRC";
  v36 = 1416;
  v37 = 17;
  v38 = 255;
  v40 = 0x1000000;
  memset_0(v39, 0, sizeof(v39));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v42, (const struct CSrmDebugInfo *)v35, 0);
  cchName = 0;
  cchReferencedDomainName = 0;
  *a2 = 0;
  if ( a3 )
    *a3 = 0;
  LookupAccountSidW(0, *((PSID *)this + 1), 0, &cchName, 0, &cchReferencedDomainName, (PSID_NAME_USE)this + 4);
  LastError = GetLastError();
  if ( LastError == 1332 )
  {
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)&v42,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"FALSE");
    v42 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v42);
    return 0;
  }
  else
  {
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v43 = LastError;
      v27 = L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp";
      v28 = L"CAutoSid::GetAccountName";
      v29 = L"SECSECRC";
      v30 = 1449;
      v31 = 17;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      v26 = &v27;
      if ( v43 < 0 )
      {
        v25 = (const unsigned __int16 **)v41;
        v17 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v41, (const struct CSrmDebugInfo *)&v27);
        CSrmFunctionTracer::TranslateError(&v42, v17, v18, L"LookupAccountSid NULL parms");
      }
      CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)&v27);
    }
    Name = 0;
    ReferencedDomainName = 0;
    CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&Name, cchName);
    if ( a3 )
      v8 = cchReferencedDomainName;
    else
      v8 = cchReferencedDomainName + cchName + 1;
    CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&ReferencedDomainName, v8);
    v9 = ReferencedDomainName;
    v10 = Name;
    if ( !LookupAccountSidW(
            0,
            *((PSID *)this + 1),
            Name,
            &cchName,
            ReferencedDomainName,
            &cchReferencedDomainName,
            (PSID_NAME_USE)this + 4) )
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      v43 = v11;
      v27 = L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp";
      v28 = L"CAutoSid::GetAccountName";
      v29 = L"SECSECRC";
      v30 = 1473;
      v31 = 17;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      v25 = &v27;
      if ( v43 < 0 )
      {
        v26 = (const unsigned __int16 **)v41;
        v19 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v41, (const struct CSrmDebugInfo *)&v27);
        CSrmFunctionTracer::TranslateError(&v42, v19, v20, L"LookupAccountSid");
      }
      CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)&v27);
    }
    if ( a3 )
    {
      v14 = v10;
      v10 = 0;
      Name = 0;
      *a2 = v14;
      *a3 = v9;
    }
    else
    {
      v12 = cchReferencedDomainName;
      v13 = &v9[cchReferencedDomainName + 1];
      *v13 = 0;
      v9[v12] = 92;
      v43 = StringCchCatW(v13, cchName + 1, v10);
      if ( v43 < 0 )
      {
        Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v42);
        v26 = (const unsigned __int16 **)v41;
        v16 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v41,
                (__int64)L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
                (__int64)L"SECSECRC",
                (__int64)L"CAutoSid::GetAccountName",
                1491,
                17);
        CSrmFunctionTracer::TranslateGenericError(&v42, v16, Hr, L"StringCchCat");
      }
      *a2 = v9;
    }
    ReferencedDomainName = 0;
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)&v42,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"TRUE");
    CoTaskMemFree(0);
    ReferencedDomainName = 0;
    CoTaskMemFree(v10);
    Name = 0;
    v42 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v42);
    return 1;
  }
}

```

## disassembly

```asm
0x180082ae8  mov     [rsp-8+arg_18], rbx
0x180082aed  push    rbp
0x180082aee  push    rsi
0x180082aef  push    rdi
0x180082af0  push    r12
0x180082af2  push    r13
0x180082af4  push    r14
0x180082af6  push    r15
0x180082af8  lea     rbp, [rsp-1E0h]
0x180082b00  sub     rsp, 2E0h
0x180082b07  mov     rax, cs:__security_cookie
0x180082b0e  xor     rax, rsp
0x180082b11  mov     [rbp+210h+var_40], rax
0x180082b18  mov     rsi, r8
0x180082b1b  mov     r14, rdx
0x180082b1e  mov     r15, rcx
0x180082b21  lea     rax, [rbp+210h+var_218]
0x180082b25  mov     [rsp+310h+var_2B8], rax
0x180082b2a  lea     rdi, aBaseFsFsrmUtil_11; "base\\fs\\fsrm\\utilities\\security\\sr"...
0x180082b31  mov     [rbp+210h+var_218], rdi
0x180082b35  lea     rax, aCautosidGetacc; "CAutoSid::GetAccountName"
0x180082b3c  mov     [rbp+210h+var_210], rax
0x180082b40  lea     rax, aSecsecrc; "SECSECRC"
0x180082b47  mov     [rbp+210h+var_208], rax
0x180082b4b  mov     [rbp+210h+var_200], 588h
0x180082b52  mov     [rbp+210h+var_1FC], 11h
0x180082b59  mov     [rbp+210h+var_1F8], 0FFh
0x180082b60  xor     r12d, r12d
0x180082b63  mov     [rbp+210h+var_190], 1000000h
0x180082b6d  xor     edx, edx; Val
0x180082b6f  lea     r8d, [r12+60h]; Size
0x180082b74  lea     rcx, [rbp+210h+var_1F0]; void *
0x180082b78  call    memset_0
0x180082b7d  nop
0x180082b7e  xor     r8d, r8d
0x180082b81  lea     rdx, [rbp+210h+var_218]
0x180082b85  lea     rcx, [rbp+210h+var_F0]
0x180082b8c  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180082b91  nop
0x180082b92  mov     [rsp+310h+cchName], r12d
0x180082b97  mov     [rsp+310h+var_2D0], r12d
0x180082b9c  mov     [r14], r12
0x180082b9f  test    rsi, rsi
0x180082ba2  jz      short loc_180082BA7
0x180082ba4  mov     [rsi], r12
0x180082ba7  lea     rbx, [r15+10h]
0x180082bab  mov     [rsp+310h+peUse], rbx; peUse
0x180082bb0  lea     rax, [rsp+310h+var_2D0]
0x180082bb5  mov     [rsp+310h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180082bba  mov     [rsp+310h+ReferencedDomainName], r12; ReferencedDomainName
0x180082bbf  lea     r9, [rsp+310h+cchName]; cchName
0x180082bc4  xor     r8d, r8d; Name
0x180082bc7  mov     rdx, [r15+8]; Sid
0x180082bcb  xor     ecx, ecx; lpSystemName
0x180082bcd  call    cs:__imp_LookupAccountSidW
0x180082bd3  call    cs:__imp_GetLastError
0x180082bd9  cmp     eax, 534h
0x180082bde  jnz     short loc_180082C2E
0x180082be0  lea     rax, aFalse; "FALSE"
0x180082be7  mov     [rsp+310h+ReferencedDomainName], rax
0x180082bec  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180082bf3  mov     r8d, 0AAh; unsigned int
0x180082bf9  lea     rdx, aReturn; "RETURN"
0x180082c00  lea     rcx, [rbp+210h+var_F0]; this
0x180082c07  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180082c0c  nop
0x180082c0d  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180082c14  mov     [rbp+210h+var_F0], rax
0x180082c1b  lea     rcx, [rbp+210h+var_F0]; this
0x180082c22  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180082c27  xor     eax, eax
0x180082c29  jmp     loc_180082E82
0x180082c2e  mov     r13d, 80070000h
0x180082c34  cmp     eax, 7Ah ; 'z'
0x180082c37  jz      short loc_180082CB5
0x180082c39  test    eax, eax
0x180082c3b  jle     short loc_180082C43
0x180082c3d  movzx   eax, ax
0x180082c40  or      eax, r13d
0x180082c43  mov     [rbp+210h+var_E8], eax
0x180082c49  mov     [rsp+310h+var_2A8], rdi
0x180082c4e  lea     rax, aCautosidGetacc; "CAutoSid::GetAccountName"
0x180082c55  mov     [rsp+310h+var_2A0], rax
0x180082c5a  lea     rax, aSecsecrc; "SECSECRC"
0x180082c61  mov     [rsp+310h+var_298], rax
0x180082c66  mov     [rbp+210h+var_290], 5A9h
0x180082c6d  mov     [rbp+210h+var_28C], 11h
0x180082c74  mov     [rbp+210h+var_288], 0FFh
0x180082c7b  mov     [rbp+210h+var_220], 1000000h
0x180082c82  xor     edx, edx; Val
0x180082c84  lea     r8d, [rdx+60h]; Size
0x180082c88  lea     rcx, [rbp+210h+var_280]; void *
0x180082c8c  call    memset_0
0x180082c91  lea     rax, [rsp+310h+var_2A8]
0x180082c96  mov     [rsp+310h+var_2B0], rax
0x180082c9b  mov     r10d, [rbp+210h+var_E8]
0x180082ca2  test    r10d, r10d
0x180082ca5  js      loc_180082F0A
0x180082cab  lea     rcx, [rsp+310h+var_2A8]; this
0x180082cb0  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180082cb5  mov     [rsp+310h+Name], r12
0x180082cba  mov     [rsp+310h+var_2C8], r12
0x180082cbf  mov     edx, [rsp+310h+cchName]; unsigned __int64
0x180082cc3  lea     rcx, [rsp+310h+Name]; this
0x180082cc8  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x180082ccd  test    rsi, rsi
0x180082cd0  jnz     short loc_180082CDE
0x180082cd2  mov     edx, [rsp+310h+cchName]
0x180082cd6  inc     edx
0x180082cd8  add     edx, [rsp+310h+var_2D0]
0x180082cdc  jmp     short loc_180082CE2
0x180082cde  mov     edx, [rsp+310h+var_2D0]; unsigned __int64
0x180082ce2  lea     rcx, [rsp+310h+var_2C8]; this
0x180082ce7  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x180082cec  mov     [rsp+310h+peUse], rbx; peUse
0x180082cf1  lea     rax, [rsp+310h+var_2D0]
0x180082cf6  mov     [rsp+310h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180082cfb  mov     rdi, [rsp+310h+var_2C8]
0x180082d00  mov     [rsp+310h+ReferencedDomainName], rdi; ReferencedDomainName
0x180082d05  lea     r9, [rsp+310h+cchName]; cchName
0x180082d0a  mov     rbx, [rsp+310h+Name]
0x180082d0f  mov     r8, rbx; Name
0x180082d12  mov     rdx, [r15+8]; Sid
0x180082d16  xor     ecx, ecx; lpSystemName
0x180082d18  call    cs:__imp_LookupAccountSidW
0x180082d1e  test    eax, eax
0x180082d20  jnz     loc_180082DB1
0x180082d26  call    cs:__imp_GetLastError
0x180082d2c  test    eax, eax
0x180082d2e  jle     short loc_180082D36
0x180082d30  movzx   eax, ax
0x180082d33  or      eax, r13d
0x180082d36  mov     [rbp+210h+var_E8], eax
0x180082d3c  lea     r15, aBaseFsFsrmUtil_11; "base\\fs\\fsrm\\utilities\\security\\sr"...
0x180082d43  mov     [rsp+310h+var_2A8], r15
0x180082d48  lea     r13, aCautosidGetacc; "CAutoSid::GetAccountName"
0x180082d4f  mov     [rsp+310h+var_2A0], r13
0x180082d54  lea     rax, aSecsecrc; "SECSECRC"
0x180082d5b  mov     [rsp+310h+var_298], rax
0x180082d60  mov     [rbp+210h+var_290], 5C1h
0x180082d67  mov     [rbp+210h+var_28C], 11h
0x180082d6e  mov     [rbp+210h+var_288], 0FFh
0x180082d75  mov     [rbp+210h+var_220], 1000000h
0x180082d7c  xor     edx, edx; Val
0x180082d7e  lea     r8d, [rdx+60h]; Size
0x180082d82  lea     rcx, [rbp+210h+var_280]; void *
0x180082d86  call    memset_0
0x180082d8b  lea     rax, [rsp+310h+var_2A8]
0x180082d90  mov     [rsp+310h+var_2B8], rax
0x180082d95  mov     r10d, [rbp+210h+var_E8]
0x180082d9c  test    r10d, r10d
0x180082d9f  js      loc_180082F42
0x180082da5  lea     rcx, [rsp+310h+var_2A8]; this
0x180082daa  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180082daf  jmp     short loc_180082DBF
0x180082db1  lea     r15, aBaseFsFsrmUtil_11; "base\\fs\\fsrm\\utilities\\security\\sr"...
0x180082db8  lea     r13, aCautosidGetacc; "CAutoSid::GetAccountName"
0x180082dbf  test    rsi, rsi
0x180082dc2  jnz     short loc_180082DFB
0x180082dc4  mov     edx, [rsp+310h+var_2D0]
0x180082dc8  lea     rcx, [rdx+1]
0x180082dcc  lea     rcx, [rdi+rcx*2]; unsigned __int16 *
0x180082dd0  mov     [rcx], r12w
0x180082dd4  mov     word ptr [rdi+rdx*2], 5Ch ; '\'
0x180082dda  mov     edx, [rsp+310h+cchName]
0x180082dde  inc     edx; unsigned __int64
0x180082de0  mov     r8, rbx; unsigned __int16 *
0x180082de3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180082de8  mov     [rbp+210h+var_E8], eax
0x180082dee  test    eax, eax
0x180082df0  js      loc_180082EAC
0x180082df6  mov     [r14], rdi
0x180082df9  jmp     short loc_180082E0C
0x180082dfb  mov     rax, rbx
0x180082dfe  mov     rbx, r12
0x180082e01  mov     [rsp+310h+Name], rbx
0x180082e06  mov     [r14], rax
0x180082e09  mov     [rsi], rdi
0x180082e0c  mov     [rsp+310h+var_2C8], r12
0x180082e11  lea     rax, aTrue_0; "TRUE"
0x180082e18  mov     [rsp+310h+ReferencedDomainName], rax
0x180082e1d  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180082e24  mov     r8d, 0AAh; unsigned int
0x180082e2a  lea     rdx, aReturn; "RETURN"
0x180082e31  lea     rcx, [rbp+210h+var_F0]; this
0x180082e38  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180082e3d  nop
0x180082e3e  xor     ecx, ecx; pv
0x180082e40  call    cs:__imp_CoTaskMemFree
0x180082e46  mov     [rsp+310h+var_2C8], r12
0x180082e4b  mov     [rsp+310h+var_2C8], r12
0x180082e50  mov     rcx, rbx; pv
0x180082e53  call    cs:__imp_CoTaskMemFree
0x180082e59  mov     [rsp+310h+Name], r12
0x180082e5e  mov     [rsp+310h+Name], r12
0x180082e63  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180082e6a  mov     [rbp+210h+var_F0], rax
0x180082e71  lea     rcx, [rbp+210h+var_F0]; this
0x180082e78  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180082e7d  mov     eax, 1
0x180082e82  mov     rcx, [rbp+210h+var_40]
0x180082e89  xor     rcx, rsp; StackCookie
0x180082e8c  call    __security_check_cookie
0x180082e91  mov     rbx, [rsp+310h+arg_18]
0x180082e99  add     rsp, 2E0h
0x180082ea0  pop     r15
0x180082ea2  pop     r14
0x180082ea4  pop     r13
0x180082ea6  pop     r12
0x180082ea8  pop     rdi
0x180082ea9  pop     rsi
0x180082eaa  pop     rbp
0x180082eab  retn
0x180082eac  lea     rcx, [rbp+210h+var_F0]; this
0x180082eb3  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180082eb8  mov     ebx, eax
0x180082eba  lea     rax, [rbp+210h+var_188]
0x180082ec1  mov     [rsp+310h+var_2B0], rax
0x180082ec6  mov     dword ptr [rsp+310h+cchReferencedDomainName], 11h
0x180082ece  mov     dword ptr [rsp+310h+ReferencedDomainName], 5D3h
0x180082ed6  mov     r9, r13
0x180082ed9  lea     r8, aSecsecrc; "SECSECRC"
0x180082ee0  mov     rdx, r15
0x180082ee3  lea     rcx, [rbp+210h+var_188]
0x180082eea  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180082eef  nop
0x180082ef0  lea     r9, aStringcchcat; "StringCchCat"
0x180082ef7  mov     r8d, ebx
0x180082efa  mov     rdx, rax
0x180082efd  lea     rcx, [rbp+210h+var_F0]
0x180082f04  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x180082f0a  lea     rax, [rbp+210h+var_188]
0x180082f11  mov     [rsp+310h+var_2B8], rax
0x180082f16  lea     rdx, [rsp+310h+var_2A8]; struct CSrmDebugInfo *
0x180082f1b  lea     rcx, [rbp+210h+var_188]; this
0x180082f22  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180082f27  nop
0x180082f28  lea     r9, aLookupaccounts; "LookupAccountSid NULL parms"
0x180082f2f  mov     r8d, r10d
0x180082f32  mov     rdx, rax
0x180082f35  lea     rcx, [rbp+210h+var_F0]
0x180082f3c  call    ?TranslateError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBG@Z; CSrmFunctionTracer::TranslateError(CSrmDebugInfo,long,ushort const *)
0x180082f42  lea     rax, [rbp+210h+var_188]
0x180082f49  mov     [rsp+310h+var_2B0], rax
0x180082f4e  lea     rdx, [rsp+310h+var_2A8]; struct CSrmDebugInfo *
0x180082f53  lea     rcx, [rbp+210h+var_188]; this
0x180082f5a  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180082f5f  nop
0x180082f60  lea     r9, aLookupaccounts_0; "LookupAccountSid"
0x180082f67  mov     r8d, r10d
0x180082f6a  mov     rdx, rax
0x180082f6d  lea     rcx, [rbp+210h+var_F0]
0x180082f74  call    ?TranslateError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBG@Z; CSrmFunctionTracer::TranslateError(CSrmDebugInfo,long,ushort const *)
```
