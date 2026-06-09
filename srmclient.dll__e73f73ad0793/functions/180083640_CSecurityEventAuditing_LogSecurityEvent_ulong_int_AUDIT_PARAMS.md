# CSecurityEventAuditing::LogSecurityEvent(ulong,int,_AUDIT_PARAMS *)

- ea: `0x180083640`
- end: `0x18008388a`
- name: `?LogSecurityEvent@CSecurityEventAuditing@@SAXKHPEAU_AUDIT_PARAMS@@@Z`
- size: `586`
- prototype: `void __fastcall(DWORD dwAuditId, int, struct _AUDIT_PARAMS *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180083890`

## callees

- `0x18006febc`
- `0x1800700b8`
- `0x180074048`
- `0x180081e14`
- `0x180083640`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180083770`
- `KERNEL32!GetLastError` at `0x180083770`
- `KERNEL32!LocalFree` at `0x180083822`
- `KERNEL32!LocalFree` at `0x180083822`
- `AUTHZ!AuthzReportSecurityEventFromParams` at `0x180083762`
- `AUTHZ!AuthzReportSecurityEventFromParams` at `0x180083762`

## string_xrefs

- `0x180083677`: `base\fs\fsrm\utilities\security\srmsec.cpp`
- `0x180083783`: `base\fs\fsrm\utilities\security\srmsec.cpp`
- `0x180083800`: `AuthzReportSecurityEventFromParams failed %#x`
- `0x180083683`: `CSecurityEventAuditing::LogSecurityEvent`
- `0x18008378f`: `CSecurityEventAuditing::LogSecurityEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CSecurityEventAuditing::LogSecurityEvent(DWORD dwAuditId, int a2, struct _AUDIT_PARAMS *a3)
{
  void **ClientTokenUser; // rbx
  void *v7; // r9
  __int64 LastError; // r9
  unsigned __int16 v9; // cx
  int v10; // [rsp+58h] [rbp-1A0h] BYREF
  const unsigned __int16 **v11; // [rsp+60h] [rbp-198h]
  const unsigned __int16 *v12; // [rsp+68h] [rbp-190h] BYREF
  const unsigned __int16 *v13; // [rsp+70h] [rbp-188h]
  const unsigned __int16 *v14; // [rsp+78h] [rbp-180h]
  int v15; // [rsp+80h] [rbp-178h]
  int v16; // [rsp+84h] [rbp-174h]
  int v17; // [rsp+88h] [rbp-170h]
  _QWORD v18[12]; // [rsp+90h] [rbp-168h] BYREF
  int v19; // [rsp+F0h] [rbp-108h]
  _com_error *v20; // [rsp+F8h] [rbp-100h] BYREF
  const exception *v21; // [rsp+100h] [rbp-F8h] BYREF
  _QWORD v22[5]; // [rsp+110h] [rbp-E8h] BYREF
  unsigned int v23; // [rsp+13Ch] [rbp-BCh]

  v11 = &v12;
  v12 = L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp";
  v13 = L"CSecurityEventAuditing::LogSecurityEvent";
  v14 = L"SECSECRC";
  v15 = 1141;
  v16 = 17;
  v17 = 255;
  v19 = 0x1000000;
  memset_0(v18, 0, sizeof(v18));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v22, (const struct CSrmDebugInfo *)&v12, 0);
  try
  {
    ClientTokenUser = 0;
    v7 = 0;
    if ( a2 )
    {
      ClientTokenUser = (void **)GetClientTokenUserInformation<_TOKEN_USER>(1);
      v7 = *ClientTokenUser;
    }
    if ( !AuthzReportSecurityEventFromParams(0, 0, dwAuditId, v7, a3) )
    {
      LastError = GetLastError();
      v11 = &v12;
      v12 = L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp";
      v13 = L"CSecurityEventAuditing::LogSecurityEvent";
      v14 = L"SECSECRC";
      v15 = 1161;
      v16 = 17;
      v17 = 255;
      v9 = 0;
      v19 = 0x1000000;
      while ( v9 < 0xCu )
        v18[v9++] = 0;
      CSrmFunctionTracer::Trace(v22, &v12, L"AuthzReportSecurityEventFromParams failed %#x", LastError);
    }
    if ( ClientTokenUser )
      LocalFree(ClientTokenUser);
  }
  catch ( long v10 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)v22,
      v10,
      L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
      L"SECSECRC",
      L"CSecurityEventAuditing::LogSecurityEvent",
      0x48Cu,
      v23);
  }
  catch ( _com_error *v20 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)v22,
      v20,
      L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
      L"SECSECRC",
      L"CSecurityEventAuditing::LogSecurityEvent",
      0x48Cu,
      v23);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)v22,
      L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
      L"SECSECRC",
      L"CSecurityEventAuditing::LogSecurityEvent",
      0x48Cu,
      v23);
  }
  catch ( const exception *v21 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)v22,
      v21,
      L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
      L"SECSECRC",
      L"CSecurityEventAuditing::LogSecurityEvent",
      0x48Cu,
      v23);
  }
  v22[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v22);
}

```

## disassembly

```asm
0x180083640  mov     [rsp+arg_8], rbx
0x180083645  push    rsi
0x180083646  push    rdi
0x180083647  push    r12
0x180083649  push    r13
0x18008364b  push    r14
0x18008364d  sub     rsp, 1D0h
0x180083654  mov     rax, cs:__security_cookie
0x18008365b  xor     rax, rsp
0x18008365e  mov     [rsp+1F8h+var_38], rax
0x180083666  mov     r14, r8
0x180083669  mov     edi, edx
0x18008366b  mov     esi, ecx
0x18008366d  lea     rax, [rsp+1F8h+var_190]
0x180083672  mov     [rsp+1F8h+var_198], rax
0x180083677  lea     rax, aBaseFsFsrmUtil_11; "base\\fs\\fsrm\\utilities\\security\\sr"...
0x18008367e  mov     [rsp+1F8h+var_190], rax
0x180083683  lea     rax, aCsecurityevent_0; "CSecurityEventAuditing::LogSecurityEven"...
0x18008368a  mov     [rsp+1F8h+var_188], rax
0x18008368f  lea     rax, aSecsecrc; "SECSECRC"
0x180083696  mov     [rsp+1F8h+var_180], rax
0x18008369b  mov     [rsp+1F8h+var_178], 475h
0x1800836a6  mov     [rsp+1F8h+var_174], 11h
0x1800836b1  mov     [rsp+1F8h+var_170], 0FFh
0x1800836bc  mov     [rsp+1F8h+var_108], 1000000h
0x1800836c7  xor     edx, edx; Val
0x1800836c9  lea     r8d, [rdx+60h]; Size
0x1800836cd  lea     rcx, [rsp+1F8h+var_168]; void *
0x1800836d5  call    memset_0
0x1800836da  nop
0x1800836db  xor     r8d, r8d
0x1800836de  lea     rdx, [rsp+1F8h+var_190]
0x1800836e3  lea     rcx, [rsp+1F8h+var_E8]
0x1800836eb  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800836f0  nop
0x1800836f1  lea     r13, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x1800836f8  mov     [rsp+1F8h+var_1B0], r13
0x1800836fd  mov     [rsp+1F8h+var_1A8], 0
0x180083706  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAE@@6B@; const CSrmAutoLocalPtr_Storage<uchar *>::`vftable'
0x18008370d  mov     [rsp+1F8h+var_1B0], rax
0x180083712  lea     r12, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x180083719  mov     [rsp+1F8h+var_1B0], r12
0x18008371e  xor     ebx, ebx
0x180083720  mov     [rsp+1F8h+var_1A8], rbx
0x180083725  lea     rax, ??_7?$CSrmAutoLocalPtr@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@6B@; const CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable'
0x18008372c  mov     [rsp+1F8h+var_1B0], rax
0x180083731  xor     r9d, r9d
0x180083734  test    edi, edi
0x180083736  lea     edi, [rbx+1]
0x180083739  jz      short loc_180083756
0x18008373b  mov     ecx, edi
0x18008373d  call    ??$GetClientTokenUserInformation@U_TOKEN_USER@@@@YAPEAU_TOKEN_USER@@HW4_TOKEN_INFORMATION_CLASS@@@Z; GetClientTokenUserInformation<_TOKEN_USER>(int,_TOKEN_INFORMATION_CLASS)
0x180083742  mov     rbx, rax
0x180083745  mov     [rsp+1F8h+var_1A8], 0
0x18008374e  mov     [rsp+1F8h+var_1A8], rax
0x180083753  mov     r9, [rax]; pUserSid
0x180083756  mov     [rsp+1F8h+pParams], r14; pParams
0x18008375b  mov     r8d, esi; dwAuditId
0x18008375e  xor     edx, edx; hEventProvider
0x180083760  xor     ecx, ecx; dwFlags
0x180083762  call    cs:__imp_AuthzReportSecurityEventFromParams
0x180083768  test    eax, eax
0x18008376a  jnz     loc_180083815
0x180083770  call    cs:__imp_GetLastError
0x180083776  mov     r9d, eax
0x180083779  lea     rdx, [rsp+1F8h+var_190]
0x18008377e  mov     [rsp+1F8h+var_198], rdx
0x180083783  lea     rax, aBaseFsFsrmUtil_11; "base\\fs\\fsrm\\utilities\\security\\sr"...
0x18008378a  mov     [rsp+1F8h+var_190], rax
0x18008378f  lea     rax, aCsecurityevent_0; "CSecurityEventAuditing::LogSecurityEven"...
0x180083796  mov     [rsp+1F8h+var_188], rax
0x18008379b  lea     rax, aSecsecrc; "SECSECRC"
0x1800837a2  mov     [rsp+1F8h+var_180], rax
0x1800837a7  mov     [rsp+1F8h+var_178], 489h
0x1800837b2  mov     [rsp+1F8h+var_174], 11h
0x1800837bd  mov     [rsp+1F8h+var_170], 0FFh
0x1800837c8  xor     ecx, ecx
0x1800837ca  mov     word ptr [rsp+1F8h+var_108], cx
0x1800837d2  mov     byte ptr [rsp+1F8h+var_108+2], cl
0x1800837d9  mov     byte ptr [rsp+1F8h+var_108+3], dil
0x1800837e1  mov     [rsp+1F8h+var_1B8], cx
0x1800837e6  cmp     cx, 0Ch
0x1800837ea  jnb     short loc_180083800
0x1800837ec  movzx   eax, cx
0x1800837ef  mov     [rsp+rax*8+1F8h+var_168], 0
0x1800837fb  add     cx, di
0x1800837fe  jmp     short loc_1800837E1
0x180083800  lea     r8, aAuthzreportsec; "AuthzReportSecurityEventFromParams fail"...
0x180083807  lea     rcx, [rsp+1F8h+var_E8]
0x18008380f  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180083814  nop
0x180083815  mov     [rsp+1F8h+var_1B0], r12
0x18008381a  test    rbx, rbx
0x18008381d  jz      short loc_180083828
0x18008381f  mov     rcx, rbx; hMem
0x180083822  call    cs:__imp_LocalFree
0x180083828  mov     [rsp+1F8h+var_1A8], 0
0x180083831  mov     [rsp+1F8h+var_1B0], r13
0x180083836  mov     [rsp+1F8h+var_1A8], 0
0x18008383f  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180083846  mov     [rsp+1F8h+var_E8], rax
0x18008384e  lea     rcx, [rsp+1F8h+var_E8]; this
0x180083856  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18008385b  mov     rcx, [rsp+1F8h+var_38]
0x180083863  xor     rcx, rsp; StackCookie
0x180083866  call    __security_check_cookie
0x18008386b  mov     rbx, [rsp+1F8h+arg_8]
0x180083873  add     rsp, 1D0h
0x18008387a  pop     r14
0x18008387c  pop     r13
0x18008387e  pop     r12
0x180083880  pop     rdi
0x180083881  pop     rsi
0x180083882  retn
0x180083883  jmp     short loc_18008383F
0x180083885  jmp     short loc_18008383F
0x180083887  jmp     short loc_18008383F
```
