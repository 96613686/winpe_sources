# CSrmRegistryKey::GetValue(ushort const *,ulong *,bool)

- ea: `0x180075eb8`
- end: `0x1800762e8`
- name: `?GetValue@CSrmRegistryKey@@QEAA_NPEBGPEAK_N@Z`
- size: `1072`
- prototype: `bool(CSrmRegistryKey *__hidden this, const unsigned __int16 *, unsigned int *, bool)`
- caller_count: `9`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000d8ec`
- `0x1800176f4`
- `0x180053574`
- `0x18005d7f4`
- `0x18008b790`
- `0x18009f134`
- `0x1800a1950`
- `0x1800a6f90`
- `0x1800b0298`

## callees

- `0x18000ac44`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x18007424c`
- `0x180074a04`
- `0x180075eb8`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180075f93`
- `ADVAPI32!RegQueryValueExW` at `0x180076055`
- `ADVAPI32!RegQueryValueExW` at `0x180075f93`
- `ADVAPI32!RegQueryValueExW` at `0x180076055`

## string_xrefs

- `0x180075ef6`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x180076120`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x1800761b2`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18007622d`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x1800762a6`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x180075f02`: `CSrmRegistryKey::GetValue`
- `0x180076112`: `CSrmRegistryKey::GetValue`
- `0x1800761a4`: `CSrmRegistryKey::GetValue`
- `0x18007621f`: `CSrmRegistryKey::GetValue`
- `0x180076298`: `CSrmRegistryKey::GetValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall CSrmRegistryKey::GetValue(HKEY *this, const unsigned __int16 *a2, unsigned int *a3)
{
  int v6; // ebx
  DWORD v8; // r14d
  int v9; // ebx
  DWORD v10; // r14d
  DWORD v11; // r15d
  unsigned __int16 *v12; // r12
  HKEY v13; // rdi
  __int64 v14; // rax
  DWORD v15; // r14d
  DWORD v16; // r15d
  unsigned __int16 *Buffer; // r12
  HKEY v18; // rdi
  __int64 v19; // rax
  unsigned __int16 *v20; // rbx
  HKEY v21; // rdi
  __int64 v22; // rax
  unsigned __int16 *v23; // rbx
  HKEY v24; // rdi
  __int64 v25; // rax
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  LPBYTE lpDataa; // [rsp+20h] [rbp-E0h]
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD lpcbData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v31; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v33; // [rsp+68h] [rbp-98h]
  _QWORD v34[3]; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+88h] [rbp-78h]
  int v36; // [rsp+8Ch] [rbp-74h]
  int v37; // [rsp+90h] [rbp-70h]
  _BYTE v38[96]; // [rsp+98h] [rbp-68h] BYREF
  int v39; // [rsp+F8h] [rbp-8h]
  _BYTE v40[144]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v41[22]; // [rsp+190h] [rbp+90h] BYREF

  v33 = v34;
  v34[0] = L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp";
  v34[1] = L"CSrmRegistryKey::GetValue";
  v34[2] = L"SRMREGSC";
  v35 = 629;
  v36 = 17;
  v37 = 255;
  v39 = 0x1000000;
  memset_0(v38, 0, sizeof(v38));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v41, (const struct CSrmDebugInfo *)v34, 0);
  *a3 = 0;
  Type = 0;
  cbData = 0;
  v6 = RegQueryValueExW(this[1], a2, 0, &Type, 0, &cbData);
  if ( v6 == 2 )
  {
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)v41,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"FALSE");
    v41[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v41);
    return 0;
  }
  else
  {
    if ( v6 && v6 != 234 )
    {
      v15 = cbData;
      v16 = Type;
      Buffer = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)(this + 2));
      v18 = this[1];
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      v33 = v40;
      v19 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v40,
              (__int64)L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
              (__int64)L"SRMREGSC",
              (__int64)L"CSrmRegistryKey::GetValue",
              661,
              17);
      CSrmFunctionTracer::TranslateGenericError(
        v41,
        v19,
        (unsigned int)v6,
        L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu])",
        v18,
        Buffer,
        a2,
        v16,
        v15);
    }
    v8 = Type;
    if ( Type != 4 )
    {
      v20 = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)(this + 2));
      v21 = this[1];
      v33 = v40;
      v22 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v40,
              (__int64)L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
              (__int64)L"SRMREGSC",
              (__int64)L"CSrmRegistryKey::GetValue",
              667,
              17);
      LODWORD(lpData) = v8;
      CSrmFunctionTracer::Throw(
        v41,
        v22,
        2147767062LL,
        L"Unexpected type %lu for a DWORD value 0x%08lx(%s),%s",
        lpData,
        v21,
        v20,
        a2);
    }
    if ( cbData != 4 )
    {
      v23 = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)(this + 2));
      v24 = this[1];
      v33 = v40;
      v25 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v40,
              (__int64)L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
              (__int64)L"SRMREGSC",
              (__int64)L"CSrmRegistryKey::GetValue",
              670,
              17);
      LODWORD(lpDataa) = 4;
      CSrmFunctionTracer::Throw(
        v41,
        v25,
        2147767062LL,
        L"Unexpected size %lu for a DWORD value 0x%08lx(%s),%s",
        lpDataa,
        v24,
        v23,
        a2);
    }
    v31 = 0;
    lpcbData = 4;
    *(_DWORD *)Data = 0;
    v9 = RegQueryValueExW(this[1], a2, 0, &v31, Data, &lpcbData);
    if ( v9 )
    {
      v10 = lpcbData;
      v11 = v31;
      v12 = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)(this + 2));
      v13 = this[1];
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      v33 = v40;
      v14 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v40,
              (__int64)L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
              (__int64)L"SRMREGSC",
              (__int64)L"CSrmRegistryKey::GetValue",
              685,
              17);
      CSrmFunctionTracer::TranslateGenericError(
        v41,
        v14,
        (unsigned int)v9,
        L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu])",
        v13,
        v12,
        a2,
        v11,
        v10);
    }
    *a3 = *(_DWORD *)Data;
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)v41,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"TRUE");
    v41[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v41);
    return 1;
  }
}

```

## disassembly

```asm
0x180075eb8  push    rbp
0x180075eba  push    rbx
0x180075ebb  push    rsi
0x180075ebc  push    rdi
0x180075ebd  push    r12
0x180075ebf  push    r14
0x180075ec1  push    r15
0x180075ec3  lea     rbp, [rsp-150h]
0x180075ecb  sub     rsp, 250h
0x180075ed2  mov     rax, cs:__security_cookie
0x180075ed9  xor     rax, rsp
0x180075edc  mov     [rbp+180h+var_40], rax
0x180075ee3  mov     r15, r8
0x180075ee6  mov     rsi, rdx
0x180075ee9  mov     rdi, rcx
0x180075eec  lea     rax, [rsp+280h+var_210]
0x180075ef1  mov     [rsp+280h+var_218], rax
0x180075ef6  lea     rax, aBaseFsFsrmUtil_16; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x180075efd  mov     [rsp+280h+var_210], rax
0x180075f02  lea     rax, aCsrmregistryke; "CSrmRegistryKey::GetValue"
0x180075f09  mov     [rsp+280h+var_208], rax
0x180075f0e  lea     rax, aSrmregsc; "SRMREGSC"
0x180075f15  mov     [rbp+180h+var_200], rax
0x180075f19  mov     [rbp+180h+var_1F8], 275h
0x180075f20  mov     [rbp+180h+var_1F4], 11h
0x180075f27  mov     [rbp+180h+var_1F0], 0FFh
0x180075f2e  mov     [rbp+180h+var_188], 1000000h
0x180075f35  xor     edx, edx; Val
0x180075f37  lea     r8d, [rdx+60h]; Size
0x180075f3b  lea     rcx, [rbp+180h+var_1E8]; void *
0x180075f3f  call    memset_0
0x180075f44  nop
0x180075f45  xor     r8d, r8d
0x180075f48  lea     rdx, [rsp+280h+var_210]
0x180075f4d  lea     rcx, [rbp+180h+var_F0]
0x180075f54  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180075f59  nop
0x180075f5a  mov     dword ptr [r15], 0
0x180075f61  mov     [rsp+280h+Type], 0
0x180075f69  mov     [rsp+280h+cbData], 0
0x180075f71  lea     rax, [rsp+280h+cbData]
0x180075f76  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180075f7b  mov     [rsp+280h+lpData], 0; lpData
0x180075f84  lea     r9, [rsp+280h+Type]; lpType
0x180075f89  xor     r8d, r8d; lpReserved
0x180075f8c  mov     rdx, rsi; lpValueName
0x180075f8f  mov     rcx, [rdi+8]; hKey
0x180075f93  call    cs:__imp_RegQueryValueExW
0x180075f99  mov     ebx, eax
0x180075f9b  cmp     eax, 2
0x180075f9e  jnz     short loc_180075FEE
0x180075fa0  lea     rax, aFalse; "FALSE"
0x180075fa7  mov     [rsp+280h+lpData], rax
0x180075fac  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180075fb3  mov     r8d, 0AAh; unsigned int
0x180075fb9  lea     rdx, aReturn; "RETURN"
0x180075fc0  lea     rcx, [rbp+180h+var_F0]; this
0x180075fc7  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180075fcc  nop
0x180075fcd  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180075fd4  mov     [rbp+180h+var_F0], rax
0x180075fdb  lea     rcx, [rbp+180h+var_F0]; this
0x180075fe2  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180075fe7  xor     al, al
0x180075fe9  jmp     loc_1800760B1
0x180075fee  test    ebx, ebx
0x180075ff0  jz      short loc_180075FFE
0x180075ff2  cmp     ebx, 0EAh
0x180075ff8  jnz     loc_180076164
0x180075ffe  mov     r14d, [rsp+280h+Type]
0x180076003  mov     r12d, 4
0x180076009  cmp     r14d, r12d
0x18007600c  jnz     loc_1800761F6
0x180076012  cmp     [rsp+280h+cbData], r12d
0x180076017  jnz     loc_18007626F
0x18007601d  mov     [rsp+280h+var_224], 0
0x180076025  mov     [rsp+280h+var_228], r12d
0x18007602a  mov     dword ptr [rsp+280h+Data], 0
0x180076032  lea     rax, [rsp+280h+var_228]
0x180076037  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18007603c  lea     rax, [rsp+280h+Data]
0x180076041  mov     [rsp+280h+lpData], rax; lpData
0x180076046  lea     r9, [rsp+280h+var_224]; lpType
0x18007604b  xor     r8d, r8d; lpReserved
0x18007604e  mov     rdx, rsi; lpValueName
0x180076051  mov     rcx, [rdi+8]; hKey
0x180076055  call    cs:__imp_RegQueryValueExW
0x18007605b  mov     ebx, eax
0x18007605d  test    eax, eax
0x18007605f  jnz     short loc_1800760D2
0x180076061  mov     eax, dword ptr [rsp+280h+Data]
0x180076065  mov     [r15], eax
0x180076068  lea     rax, aTrue_0; "TRUE"
0x18007606f  mov     [rsp+280h+lpData], rax
0x180076074  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x18007607b  mov     r8d, 0AAh; unsigned int
0x180076081  lea     rdx, aReturn; "RETURN"
0x180076088  lea     rcx, [rbp+180h+var_F0]; this
0x18007608f  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180076094  nop
0x180076095  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007609c  mov     [rbp+180h+var_F0], rax
0x1800760a3  lea     rcx, [rbp+180h+var_F0]; this
0x1800760aa  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800760af  mov     al, 1
0x1800760b1  mov     rcx, [rbp+180h+var_40]
0x1800760b8  xor     rcx, rsp; StackCookie
0x1800760bb  call    __security_check_cookie
0x1800760c0  add     rsp, 250h
0x1800760c7  pop     r15
0x1800760c9  pop     r14
0x1800760cb  pop     r12
0x1800760cd  pop     rdi
0x1800760ce  pop     rsi
0x1800760cf  pop     rbx
0x1800760d0  pop     rbp
0x1800760d1  retn
0x1800760d2  mov     r14d, [rsp+280h+var_228]
0x1800760d7  mov     r15d, [rsp+280h+var_224]
0x1800760dc  lea     rcx, [rdi+10h]; this
0x1800760e0  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x1800760e5  mov     r12, rax
0x1800760e8  mov     rdi, [rdi+8]
0x1800760ec  test    ebx, ebx
0x1800760ee  jle     short loc_1800760F9
0x1800760f0  movzx   ebx, bx
0x1800760f3  or      ebx, 80070000h
0x1800760f9  lea     rax, [rbp+180h+var_180]
0x1800760fd  mov     [rsp+280h+var_218], rax
0x180076102  mov     dword ptr [rsp+280h+lpcbData], 11h
0x18007610a  mov     dword ptr [rsp+280h+lpData], 2ADh
0x180076112  lea     r9, aCsrmregistryke; "CSrmRegistryKey::GetValue"
0x180076119  lea     r8, aSrmregsc; "SRMREGSC"
0x180076120  lea     rdx, aBaseFsFsrmUtil_16; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x180076127  lea     rcx, [rbp+180h+var_180]
0x18007612b  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180076130  nop
0x180076131  mov     [rsp+280h+var_240], r14d
0x180076136  mov     dword ptr [rsp+280h+var_248], r15d
0x18007613b  mov     [rsp+280h+var_250], rsi
0x180076140  mov     [rsp+280h+lpcbData], r12
0x180076145  mov     [rsp+280h+lpData], rdi
0x18007614a  lea     r9, aRegqueryvaluee; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x180076151  mov     r8d, ebx
0x180076154  mov     rdx, rax
0x180076157  lea     rcx, [rbp+180h+var_F0]
0x18007615e  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x180076164  mov     r14d, [rsp+280h+cbData]
0x180076169  mov     r15d, [rsp+280h+Type]
0x18007616e  lea     rcx, [rdi+10h]; this
0x180076172  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180076177  mov     r12, rax
0x18007617a  mov     rdi, [rdi+8]
0x18007617e  test    ebx, ebx
0x180076180  jle     short loc_18007618B
0x180076182  movzx   ebx, bx
0x180076185  or      ebx, 80070000h
0x18007618b  lea     rax, [rbp+180h+var_180]
0x18007618f  mov     [rsp+280h+var_218], rax
0x180076194  mov     dword ptr [rsp+280h+lpcbData], 11h
0x18007619c  mov     dword ptr [rsp+280h+lpData], 295h
0x1800761a4  lea     r9, aCsrmregistryke; "CSrmRegistryKey::GetValue"
0x1800761ab  lea     r8, aSrmregsc; "SRMREGSC"
0x1800761b2  lea     rdx, aBaseFsFsrmUtil_16; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x1800761b9  lea     rcx, [rbp+180h+var_180]
0x1800761bd  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800761c2  nop
0x1800761c3  mov     [rsp+280h+var_240], r14d
0x1800761c8  mov     dword ptr [rsp+280h+var_248], r15d
0x1800761cd  mov     [rsp+280h+var_250], rsi
0x1800761d2  mov     [rsp+280h+lpcbData], r12
0x1800761d7  mov     [rsp+280h+lpData], rdi
0x1800761dc  lea     r9, aRegqueryvaluee; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x1800761e3  mov     r8d, ebx
0x1800761e6  mov     rdx, rax
0x1800761e9  lea     rcx, [rbp+180h+var_F0]
0x1800761f0  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x1800761f6  lea     rcx, [rdi+10h]; this
0x1800761fa  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x1800761ff  mov     rbx, rax
0x180076202  mov     rdi, [rdi+8]
0x180076206  lea     rax, [rbp+180h+var_180]
0x18007620a  mov     [rsp+280h+var_218], rax
0x18007620f  mov     dword ptr [rsp+280h+lpcbData], 11h
0x180076217  mov     dword ptr [rsp+280h+lpData], 29Bh
0x18007621f  lea     r9, aCsrmregistryke; "CSrmRegistryKey::GetValue"
0x180076226  lea     r8, aSrmregsc; "SRMREGSC"
0x18007622d  lea     rdx, aBaseFsFsrmUtil_16; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x180076234  lea     rcx, [rbp+180h+var_180]
0x180076238  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007623d  nop
0x18007623e  mov     [rsp+280h+var_248], rsi
0x180076243  mov     [rsp+280h+var_250], rbx
0x180076248  mov     [rsp+280h+lpcbData], rdi
0x18007624d  mov     dword ptr [rsp+280h+lpData], r14d
0x180076252  lea     r9, aUnexpectedType_1; "Unexpected type %lu for a DWORD value 0"...
0x180076259  mov     r8d, 80045316h
0x18007625f  mov     rdx, rax
0x180076262  lea     rcx, [rbp+180h+var_F0]
0x180076269  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18007626f  lea     rcx, [rdi+10h]; this
0x180076273  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180076278  mov     rbx, rax
0x18007627b  mov     rdi, [rdi+8]
0x18007627f  lea     rax, [rbp+180h+var_180]
0x180076283  mov     [rsp+280h+var_218], rax
0x180076288  mov     dword ptr [rsp+280h+lpcbData], 11h
0x180076290  mov     dword ptr [rsp+280h+lpData], 29Eh
0x180076298  lea     r9, aCsrmregistryke; "CSrmRegistryKey::GetValue"
0x18007629f  lea     r8, aSrmregsc; "SRMREGSC"
0x1800762a6  lea     rdx, aBaseFsFsrmUtil_16; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x1800762ad  lea     rcx, [rbp+180h+var_180]
0x1800762b1  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800762b6  nop
0x1800762b7  mov     [rsp+280h+var_248], rsi
0x1800762bc  mov     [rsp+280h+var_250], rbx
0x1800762c1  mov     [rsp+280h+lpcbData], rdi
0x1800762c6  mov     dword ptr [rsp+280h+lpData], r12d
0x1800762cb  lea     r9, aUnexpectedSize; "Unexpected size %lu for a DWORD value 0"...
0x1800762d2  mov     r8d, 80045316h
0x1800762d8  mov     rdx, rax
0x1800762db  lea     rcx, [rbp+180h+var_F0]
0x1800762e2  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
