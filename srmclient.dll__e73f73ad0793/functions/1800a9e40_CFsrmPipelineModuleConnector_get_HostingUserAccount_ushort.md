# CFsrmPipelineModuleConnector::get_HostingUserAccount(ushort * *)

- ea: `0x1800a9e40`
- end: `0x1800aa1fd`
- name: `?get_HostingUserAccount@CFsrmPipelineModuleConnector@@UEAAJPEAPEAG@Z`
- size: `957`
- prototype: `__int64 __fastcall(CFsrmPipelineModuleConnector *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800020ba`
- `0x18006febc`
- `0x1800700b8`
- `0x180074048`
- `0x180077704`
- `0x180081e14`
- `0x180082600`
- `0x180082ae8`
- `0x1800a9e40`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800aa102`
- `ole32!CoTaskMemFree` at `0x1800aa117`
- `ole32!CoTaskMemFree` at `0x1800aa102`
- `ole32!CoTaskMemFree` at `0x1800aa117`
- `OLEAUT32!__imp_SysAllocString` at `0x1800aa00e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800aa00e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aa0f6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aa0f6`
- `KERNEL32!LocalFree` at `0x1800aa136`
- `KERNEL32!LocalFree` at `0x1800aa150`
- `KERNEL32!LocalFree` at `0x1800aa168`
- `KERNEL32!LocalFree` at `0x1800aa136`
- `KERNEL32!LocalFree` at `0x1800aa150`
- `KERNEL32!LocalFree` at `0x1800aa168`

## string_xrefs

- `0x1800a9e7e`: `base\fs\fsrm\service\modulewrp\connector.cpp`
- `0x1800aa04c`: `base\fs\fsrm\service\modulewrp\connector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
__int64 __fastcall CFsrmPipelineModuleConnector::get_HostingUserAccount(
        CFsrmPipelineModuleConnector *this,
        unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  void **ClientTokenUser; // rdi
  __int64 v5; // r8
  unsigned __int16 i; // cx
  unsigned __int16 *v7; // rbx
  BSTR v9; // [rsp+48h] [rbp-1E0h] BYREF
  OLECHAR *psz; // [rsp+50h] [rbp-1D8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-1D0h] BYREF
  void **v12; // [rsp+60h] [rbp-1C8h]
  void **v13; // [rsp+68h] [rbp-1C0h]
  void **v14; // [rsp+70h] [rbp-1B8h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-1B0h]
  int v16; // [rsp+80h] [rbp-1A8h]
  int pExceptionObject; // [rsp+88h] [rbp-1A0h] BYREF
  const unsigned __int16 **v18; // [rsp+90h] [rbp-198h]
  const unsigned __int16 *v19; // [rsp+98h] [rbp-190h] BYREF
  const unsigned __int16 *v20; // [rsp+A0h] [rbp-188h]
  const unsigned __int16 *v21; // [rsp+A8h] [rbp-180h]
  int v22; // [rsp+B0h] [rbp-178h]
  int v23; // [rsp+B4h] [rbp-174h]
  int v24; // [rsp+B8h] [rbp-170h]
  _QWORD v25[12]; // [rsp+C0h] [rbp-168h] BYREF
  int v26; // [rsp+120h] [rbp-108h]
  void **v27; // [rsp+140h] [rbp-E8h] BYREF
  int v28; // [rsp+148h] [rbp-E0h]

  v18 = &v19;
  v19 = L"base\\fs\\fsrm\\service\\modulewrp\\connector.cpp";
  v20 = L"CFsrmPipelineModuleConnector::get_HostingUserAccount";
  v21 = L"INSTCONC";
  v22 = 110;
  v23 = 24;
  v24 = 255;
  v26 = 0x1000000;
  memset_0(v25, 0, sizeof(v25));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v27, (const struct CSrmDebugInfo *)&v19, 0);
  if ( a2 )
  {
    *a2 = 0;
    v12 = &CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable';
    ClientTokenUser = (void **)GetClientTokenUserInformation<_TOKEN_USER>(0);
    v13 = ClientTokenUser;
    hMem = 0;
    v14 = &CAutoSid::`vftable';
    v16 = 8;
    CAutoSid::CopyFromSid((CAutoSid *)&v14, *ClientTokenUser);
    pv = 0;
    psz = 0;
    CAutoSid::GetAccountName((CAutoSid *)&v14, (unsigned __int16 **)&pv, &psz);
    if ( psz )
    {
      v9 = SysAllocString(psz);
      if ( !v9 )
      {
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
    }
    else
    {
      v9 = 0;
    }
    CSrmComBSTR::Append((CSrmComBSTR *)&v9, L"\\", 1);
    if ( pv )
    {
      v5 = -1;
      do
        ++v5;
      while ( *((_WORD *)pv + v5) );
    }
    else
    {
      LODWORD(v5) = 0;
    }
    CSrmComBSTR::Append((CSrmComBSTR *)&v9, (const unsigned __int16 *)pv, v5);
    v18 = &v19;
    v19 = L"base\\fs\\fsrm\\service\\modulewrp\\connector.cpp";
    v20 = L"CFsrmPipelineModuleConnector::get_HostingUserAccount";
    v21 = L"INSTCONC";
    v22 = 136;
    v23 = 24;
    v24 = 255;
    v26 = 0x1000000;
    for ( i = 0; i < 0xCu; ++i )
      v25[i] = 0;
    v7 = v9;
    CSrmFunctionTracer::Trace(&v27, &v19, L"Account: %s", v9);
    v9 = 0;
    *a2 = v7;
    SysFreeString(0);
    CoTaskMemFree(psz);
    psz = 0;
    CoTaskMemFree(pv);
    pv = 0;
    v14 = &CSrmAuto<_SID *,CSrmAutoGenericValue_Storage<_SID *,0,void * (*)(void *),&void * LocalFree(void *),_SID * & (*)(_SID * &),&public: static _SID * & DTyper<_SID *>::Identity(_SID * &)>>::`vftable';
    if ( hMem )
      LocalFree(hMem);
    v14 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
    hMem = 0;
    v12 = &CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable';
    if ( ClientTokenUser )
      LocalFree(ClientTokenUser);
    v12 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
    v13 = 0;
    v3 = v28;
    v27 = &CSrmFunctionTracer::`vftable';
  }
  else
  {
    v3 = -2147024809;
    v28 = -2147024809;
    v27 = &CSrmFunctionTracer::`vftable';
  }
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v27);
  return v3;
}

```

## disassembly

```asm
0x1800a9e40  mov     r11, rsp
0x1800a9e43  mov     [r11+8], rbx
0x1800a9e47  mov     [r11+18h], rsi
0x1800a9e4b  push    rdi
0x1800a9e4c  push    r12
0x1800a9e4e  push    r13
0x1800a9e50  push    r14
0x1800a9e52  push    r15
0x1800a9e54  sub     rsp, 200h
0x1800a9e5b  mov     rax, cs:__security_cookie
0x1800a9e62  xor     rax, rsp
0x1800a9e65  mov     [rsp+228h+var_38], rax
0x1800a9e6d  mov     rsi, rdx
0x1800a9e70  lea     rax, [r11-190h]
0x1800a9e77  mov     [r11-198h], rax
0x1800a9e7e  lea     rax, aBaseFsFsrmServ_18; "base\\fs\\fsrm\\service\\modulewrp\\con"...
0x1800a9e85  mov     [r11-190h], rax
0x1800a9e8c  lea     rax, aCfsrmpipelinem_27; "CFsrmPipelineModuleConnector::get_Hosti"...
0x1800a9e93  mov     [r11-188h], rax
0x1800a9e9a  lea     rax, aInstconc; "INSTCONC"
0x1800a9ea1  mov     [r11-180h], rax
0x1800a9ea8  mov     [rsp+228h+var_178], 6Eh ; 'n'
0x1800a9eb3  mov     [rsp+228h+var_174], 18h
0x1800a9ebe  mov     [rsp+228h+var_170], 0FFh
0x1800a9ec9  xor     r14d, r14d
0x1800a9ecc  mov     [rsp+228h+var_108], 1000000h
0x1800a9ed7  lea     ebx, [r14+1]
0x1800a9edb  xor     edx, edx; Val
0x1800a9edd  lea     r8d, [r14+60h]; Size
0x1800a9ee1  lea     rcx, [r11-168h]; void *
0x1800a9ee8  call    memset_0
0x1800a9eed  nop
0x1800a9eee  xor     r8d, r8d
0x1800a9ef1  lea     rdx, [rsp+228h+var_190]
0x1800a9ef9  lea     rcx, [rsp+228h+var_E8]
0x1800a9f01  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800a9f06  nop
0x1800a9f07  test    rsi, rsi
0x1800a9f0a  jnz     short loc_1800A9F2C
0x1800a9f0c  mov     ebx, 80070057h
0x1800a9f11  mov     [rsp+228h+var_E0], ebx
0x1800a9f18  lea     rcx, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800a9f1f  mov     [rsp+228h+var_E8], rcx
0x1800a9f27  jmp     loc_1800AA19A
0x1800a9f2c  mov     [rsi], r14
0x1800a9f2f  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x1800a9f36  mov     [rsp+228h+var_1C8], rax
0x1800a9f3b  mov     [rsp+228h+var_1C0], r14
0x1800a9f40  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAE@@6B@; const CSrmAutoLocalPtr_Storage<uchar *>::`vftable'
0x1800a9f47  mov     [rsp+228h+var_1C8], rax
0x1800a9f4c  lea     r13, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x1800a9f53  mov     [rsp+228h+var_1C8], r13
0x1800a9f58  mov     [rsp+228h+var_1C0], r14
0x1800a9f5d  lea     rax, ??_7?$CSrmAutoLocalPtr@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@6B@; const CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable'
0x1800a9f64  mov     [rsp+228h+var_1C8], rax
0x1800a9f69  xor     ecx, ecx
0x1800a9f6b  call    ??$GetClientTokenUserInformation@U_TOKEN_USER@@@@YAPEAU_TOKEN_USER@@HW4_TOKEN_INFORMATION_CLASS@@@Z; GetClientTokenUserInformation<_TOKEN_USER>(int,_TOKEN_INFORMATION_CLASS)
0x1800a9f70  mov     rdi, rax
0x1800a9f73  mov     [rsp+228h+var_1C0], r14
0x1800a9f78  mov     [rsp+228h+var_1C0], rax
0x1800a9f7d  lea     r12, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x1800a9f84  mov     [rsp+228h+var_1B8], r12
0x1800a9f89  mov     [rsp+228h+hMem], r14
0x1800a9f8e  lea     r15, ??_7?$CSrmAuto@PEAU_SID@@V?$CSrmAutoGenericValue_Storage@PEAU_SID@@$0A@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAU_SID@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<_SID *,CSrmAutoGenericValue_Storage<_SID *,0,void * (*)(void *),&LocalFree(void *),_SID * & (*)(_SID * &),&DTyper<_SID *>::Identity(_SID * &)>>::`vftable'
0x1800a9f95  mov     [rsp+228h+var_1B8], r15
0x1800a9f9a  lea     rax, ??_7CAutoSid@@6B@; const CAutoSid::`vftable'
0x1800a9fa1  mov     [rsp+228h+var_1B8], rax
0x1800a9fa6  mov     [rsp+228h+var_1A8], 8
0x1800a9fb1  mov     rdx, [rdi]; void *
0x1800a9fb4  lea     rcx, [rsp+228h+var_1B8]; this
0x1800a9fb9  call    ?CopyFromSid@CAutoSid@@QEAAXQEAX@Z; CAutoSid::CopyFromSid(void * const)
0x1800a9fbe  mov     [rsp+228h+pv], r14
0x1800a9fc3  mov     [rsp+228h+psz], r14
0x1800a9fc8  lea     r8, [rsp+228h+psz]; unsigned __int16 **
0x1800a9fcd  lea     rdx, [rsp+228h+pv]; unsigned __int16 **
0x1800a9fd2  lea     rcx, [rsp+228h+var_1B8]; this
0x1800a9fd7  call    ?GetAccountName@CAutoSid@@QEAAHPEAPEAG0@Z; CAutoSid::GetAccountName(ushort * *,ushort * *)
0x1800a9fdc  mov     rcx, [rsp+228h+psz]; psz
0x1800a9fe1  test    rcx, rcx
0x1800a9fe4  jnz     short loc_1800AA00E
0x1800a9fe6  mov     [rsp+228h+var_1E0], r14
0x1800a9feb  mov     r8d, ebx; int
0x1800a9fee  lea     rdx, psz; "\\"
0x1800a9ff5  lea     rcx, [rsp+228h+var_1E0]; this
0x1800a9ffa  call    ?Append@CSrmComBSTR@@QEAAJPEBGH@Z; CSrmComBSTR::Append(ushort const *,int)
0x1800a9fff  mov     rdx, [rsp+228h+pv]; unsigned __int16 *
0x1800aa004  test    rdx, rdx
0x1800aa007  jnz     short loc_1800AA024
0x1800aa009  mov     r8d, r14d
0x1800aa00c  jmp     short loc_1800AA032
0x1800aa00e  call    cs:__imp_SysAllocString
0x1800aa014  mov     [rsp+228h+var_1E0], rax
0x1800aa019  test    rax, rax
0x1800aa01c  jz      loc_1800AA1DC
0x1800aa022  jmp     short loc_1800A9FEB
0x1800aa024  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800aa028  inc     r8; int
0x1800aa02b  cmp     [rdx+r8*2], r14w
0x1800aa030  jnz     short loc_1800AA028
0x1800aa032  lea     rcx, [rsp+228h+var_1E0]; this
0x1800aa037  call    ?Append@CSrmComBSTR@@QEAAJPEBGH@Z; CSrmComBSTR::Append(ushort const *,int)
0x1800aa03c  lea     rdx, [rsp+228h+var_190]
0x1800aa044  mov     [rsp+228h+var_198], rdx
0x1800aa04c  lea     rax, aBaseFsFsrmServ_18; "base\\fs\\fsrm\\service\\modulewrp\\con"...
0x1800aa053  mov     [rsp+228h+var_190], rax
0x1800aa05b  lea     rax, aCfsrmpipelinem_27; "CFsrmPipelineModuleConnector::get_Hosti"...
0x1800aa062  mov     [rsp+228h+var_188], rax
0x1800aa06a  lea     rax, aInstconc; "INSTCONC"
0x1800aa071  mov     [rsp+228h+var_180], rax
0x1800aa079  mov     [rsp+228h+var_178], 88h
0x1800aa084  mov     [rsp+228h+var_174], 18h
0x1800aa08f  mov     [rsp+228h+var_170], 0FFh
0x1800aa09a  mov     word ptr [rsp+228h+var_108], r14w
0x1800aa0a3  mov     byte ptr [rsp+228h+var_108+2], r14b
0x1800aa0ab  mov     byte ptr [rsp+228h+var_108+3], bl
0x1800aa0b2  mov     ecx, r14d
0x1800aa0b5  mov     [rsp+228h+var_1E8], cx
0x1800aa0ba  cmp     cx, 0Ch
0x1800aa0be  jnb     short loc_1800AA0D0
0x1800aa0c0  movzx   eax, cx
0x1800aa0c3  mov     [rsp+rax*8+228h+var_168], r14
0x1800aa0cb  add     cx, bx
0x1800aa0ce  jmp     short loc_1800AA0B5
0x1800aa0d0  mov     rbx, [rsp+228h+var_1E0]
0x1800aa0d5  mov     r9, rbx
0x1800aa0d8  lea     r8, aAccountS; "Account: %s"
0x1800aa0df  lea     rcx, [rsp+228h+var_E8]
0x1800aa0e7  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x1800aa0ec  mov     [rsp+228h+var_1E0], r14
0x1800aa0f1  mov     [rsi], rbx
0x1800aa0f4  xor     ecx, ecx; bstrString
0x1800aa0f6  call    cs:__imp_SysFreeString
0x1800aa0fc  nop
0x1800aa0fd  mov     rcx, [rsp+228h+psz]; pv
0x1800aa102  call    cs:__imp_CoTaskMemFree
0x1800aa108  mov     [rsp+228h+psz], r14
0x1800aa10d  mov     [rsp+228h+psz], r14
0x1800aa112  mov     rcx, [rsp+228h+pv]; pv
0x1800aa117  call    cs:__imp_CoTaskMemFree
0x1800aa11d  mov     [rsp+228h+pv], r14
0x1800aa122  mov     [rsp+228h+pv], r14
0x1800aa127  mov     [rsp+228h+var_1B8], r15
0x1800aa12c  mov     rcx, [rsp+228h+hMem]; hMem
0x1800aa131  test    rcx, rcx
0x1800aa134  jz      short loc_1800AA13C
0x1800aa136  call    cs:__imp_LocalFree
0x1800aa13c  mov     [rsp+228h+hMem], r14
0x1800aa141  mov     [rsp+228h+var_1B8], r12
0x1800aa146  mov     rcx, [rsp+228h+hMem]; hMem
0x1800aa14b  test    rcx, rcx
0x1800aa14e  jz      short loc_1800AA156
0x1800aa150  call    cs:__imp_LocalFree
0x1800aa156  mov     [rsp+228h+hMem], r14
0x1800aa15b  mov     [rsp+228h+var_1C8], r13
0x1800aa160  test    rdi, rdi
0x1800aa163  jz      short loc_1800AA16E
0x1800aa165  mov     rcx, rdi; hMem
0x1800aa168  call    cs:__imp_LocalFree
0x1800aa16e  mov     [rsp+228h+var_1C0], r14
0x1800aa173  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x1800aa17a  mov     [rsp+228h+var_1C8], rax
0x1800aa17f  mov     [rsp+228h+var_1C0], r14
0x1800aa184  mov     ebx, [rsp+228h+var_E0]
0x1800aa18b  lea     rcx, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800aa192  mov     [rsp+228h+var_E8], rcx
0x1800aa19a  lea     rcx, [rsp+228h+var_E8]; this
0x1800aa1a2  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800aa1a7  mov     eax, ebx
0x1800aa1a9  mov     rcx, [rsp+228h+var_38]
0x1800aa1b1  xor     rcx, rsp; StackCookie
0x1800aa1b4  call    __security_check_cookie
0x1800aa1b9  lea     r11, [rsp+228h+var_28]
0x1800aa1c1  mov     rbx, [r11+30h]
0x1800aa1c5  mov     rsi, [r11+40h]
0x1800aa1c9  mov     rsp, r11
0x1800aa1cc  pop     r15
0x1800aa1ce  pop     r14
0x1800aa1d0  pop     r13
0x1800aa1d2  pop     r12
0x1800aa1d4  pop     rdi
0x1800aa1d5  retn
0x1800aa1d6  jmp     short loc_1800AA184
0x1800aa1d8  jmp     short loc_1800AA184
0x1800aa1da  jmp     short loc_1800AA184
0x1800aa1dc  mov     [rsp+228h+pExceptionObject], 8007000Eh
0x1800aa1e7  lea     rdx, _TI1J; pThrowInfo
0x1800aa1ee  lea     rcx, [rsp+228h+pExceptionObject]; pExceptionObject
0x1800aa1f6  call    _CxxThrowException_0
```
