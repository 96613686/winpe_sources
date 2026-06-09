# CSrmRegistryKey::GetValue(ushort const *,ulong *,bool)

- ea: `0x18001a9f8`
- end: `0x18001ae28`
- name: `?GetValue@CSrmRegistryKey@@QEAA_NPEBGPEAK_N@Z`
- size: `1072`
- prototype: `char __fastcall(HKEY *this, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000a460`
- `0x18000a704`

## callees

- `0x1800054c0`
- `0x1800161e8`
- `0x18001623c`
- `0x180016564`
- `0x1800191ec`
- `0x1800195f0`
- `0x180019b84`
- `0x18001a9f8`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001aad3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ab95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001aad3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ab95`

## string_xrefs

- `0x18001aa36`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18001ac60`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18001acf2`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18001ad6d`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18001ade6`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18001aa42`: `CSrmRegistryKey::GetValue`
- `0x18001ac52`: `CSrmRegistryKey::GetValue`
- `0x18001ace4`: `CSrmRegistryKey::GetValue`
- `0x18001ad5f`: `CSrmRegistryKey::GetValue`
- `0x18001add8`: `CSrmRegistryKey::GetValue`

## pseudocode

```c
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
0x18001a9f8  push    rbp
0x18001a9fa  push    rbx
0x18001a9fb  push    rsi
0x18001a9fc  push    rdi
0x18001a9fd  push    r12
0x18001a9ff  push    r14
0x18001aa01  push    r15
0x18001aa03  lea     rbp, [rsp-150h]
0x18001aa0b  sub     rsp, 250h
0x18001aa12  mov     rax, cs:__security_cookie
0x18001aa19  xor     rax, rsp
0x18001aa1c  mov     [rbp+180h+var_40], rax
0x18001aa23  mov     r15, r8
0x18001aa26  mov     rsi, rdx
0x18001aa29  mov     rdi, rcx
0x18001aa2c  lea     rax, [rsp+280h+var_210]
0x18001aa31  mov     [rsp+280h+var_218], rax
0x18001aa36  lea     rax, aBaseFsFsrmUtil_3; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x18001aa3d  mov     [rsp+280h+var_210], rax
0x18001aa42  lea     rax, aCsrmregistryke; "CSrmRegistryKey::GetValue"
0x18001aa49  mov     [rsp+280h+var_208], rax
0x18001aa4e  lea     rax, aSrmregsc; "SRMREGSC"
0x18001aa55  mov     [rbp+180h+var_200], rax
0x18001aa59  mov     [rbp+180h+var_1F8], 275h
0x18001aa60  mov     [rbp+180h+var_1F4], 11h
0x18001aa67  mov     [rbp+180h+var_1F0], 0FFh
0x18001aa6e  mov     [rbp+180h+var_188], 1000000h
0x18001aa75  xor     edx, edx; Val
0x18001aa77  lea     r8d, [rdx+60h]; Size
0x18001aa7b  lea     rcx, [rbp+180h+var_1E8]; void *
0x18001aa7f  call    memset_0
0x18001aa84  nop
0x18001aa85  xor     r8d, r8d
0x18001aa88  lea     rdx, [rsp+280h+var_210]
0x18001aa8d  lea     rcx, [rbp+180h+var_F0]
0x18001aa94  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001aa99  nop
0x18001aa9a  mov     dword ptr [r15], 0
0x18001aaa1  mov     [rsp+280h+Type], 0
0x18001aaa9  mov     [rsp+280h+cbData], 0
0x18001aab1  lea     rax, [rsp+280h+cbData]
0x18001aab6  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18001aabb  mov     [rsp+280h+lpData], 0; lpData
0x18001aac4  lea     r9, [rsp+280h+Type]; lpType
0x18001aac9  xor     r8d, r8d; lpReserved
0x18001aacc  mov     rdx, rsi; lpValueName
0x18001aacf  mov     rcx, [rdi+8]; hKey
0x18001aad3  call    cs:__imp_RegQueryValueExW
0x18001aad9  mov     ebx, eax
0x18001aadb  cmp     eax, 2
0x18001aade  jnz     short loc_18001AB2E
0x18001aae0  lea     rax, aFalse; "FALSE"
0x18001aae7  mov     [rsp+280h+lpData], rax
0x18001aaec  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x18001aaf3  mov     r8d, 0AAh; unsigned int
0x18001aaf9  lea     rdx, aReturn; "RETURN"
0x18001ab00  lea     rcx, [rbp+180h+var_F0]; this
0x18001ab07  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x18001ab0c  nop
0x18001ab0d  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001ab14  mov     [rbp+180h+var_F0], rax
0x18001ab1b  lea     rcx, [rbp+180h+var_F0]; this
0x18001ab22  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001ab27  xor     al, al
0x18001ab29  jmp     loc_18001ABF1
0x18001ab2e  test    ebx, ebx
0x18001ab30  jz      short loc_18001AB3E
0x18001ab32  cmp     ebx, 0EAh
0x18001ab38  jnz     loc_18001ACA4
0x18001ab3e  mov     r14d, [rsp+280h+Type]
0x18001ab43  mov     r12d, 4
0x18001ab49  cmp     r14d, r12d
0x18001ab4c  jnz     loc_18001AD36
0x18001ab52  cmp     [rsp+280h+cbData], r12d
0x18001ab57  jnz     loc_18001ADAF
0x18001ab5d  mov     [rsp+280h+var_224], 0
0x18001ab65  mov     [rsp+280h+var_228], r12d
0x18001ab6a  mov     dword ptr [rsp+280h+Data], 0
0x18001ab72  lea     rax, [rsp+280h+var_228]
0x18001ab77  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18001ab7c  lea     rax, [rsp+280h+Data]
0x18001ab81  mov     [rsp+280h+lpData], rax; lpData
0x18001ab86  lea     r9, [rsp+280h+var_224]; lpType
0x18001ab8b  xor     r8d, r8d; lpReserved
0x18001ab8e  mov     rdx, rsi; lpValueName
0x18001ab91  mov     rcx, [rdi+8]; hKey
0x18001ab95  call    cs:__imp_RegQueryValueExW
0x18001ab9b  mov     ebx, eax
0x18001ab9d  test    eax, eax
0x18001ab9f  jnz     short loc_18001AC12
0x18001aba1  mov     eax, dword ptr [rsp+280h+Data]
0x18001aba5  mov     [r15], eax
0x18001aba8  lea     rax, aTrue; "TRUE"
0x18001abaf  mov     [rsp+280h+lpData], rax
0x18001abb4  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x18001abbb  mov     r8d, 0AAh; unsigned int
0x18001abc1  lea     rdx, aReturn; "RETURN"
0x18001abc8  lea     rcx, [rbp+180h+var_F0]; this
0x18001abcf  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x18001abd4  nop
0x18001abd5  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001abdc  mov     [rbp+180h+var_F0], rax
0x18001abe3  lea     rcx, [rbp+180h+var_F0]; this
0x18001abea  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001abef  mov     al, 1
0x18001abf1  mov     rcx, [rbp+180h+var_40]
0x18001abf8  xor     rcx, rsp; StackCookie
0x18001abfb  call    __security_check_cookie
0x18001ac00  add     rsp, 250h
0x18001ac07  pop     r15
0x18001ac09  pop     r14
0x18001ac0b  pop     r12
0x18001ac0d  pop     rdi
0x18001ac0e  pop     rsi
0x18001ac0f  pop     rbx
0x18001ac10  pop     rbp
0x18001ac11  retn
0x18001ac12  mov     r14d, [rsp+280h+var_228]
0x18001ac17  mov     r15d, [rsp+280h+var_224]
0x18001ac1c  lea     rcx, [rdi+10h]; this
0x18001ac20  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x18001ac25  mov     r12, rax
0x18001ac28  mov     rdi, [rdi+8]
0x18001ac2c  test    ebx, ebx
0x18001ac2e  jle     short loc_18001AC39
0x18001ac30  movzx   ebx, bx
0x18001ac33  or      ebx, 80070000h
0x18001ac39  lea     rax, [rbp+180h+var_180]
0x18001ac3d  mov     [rsp+280h+var_218], rax
0x18001ac42  mov     dword ptr [rsp+280h+lpcbData], 11h
0x18001ac4a  mov     dword ptr [rsp+280h+lpData], 2ADh
0x18001ac52  lea     r9, aCsrmregistryke; "CSrmRegistryKey::GetValue"
0x18001ac59  lea     r8, aSrmregsc; "SRMREGSC"
0x18001ac60  lea     rdx, aBaseFsFsrmUtil_3; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x18001ac67  lea     rcx, [rbp+180h+var_180]
0x18001ac6b  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18001ac70  nop
0x18001ac71  mov     [rsp+280h+var_240], r14d
0x18001ac76  mov     dword ptr [rsp+280h+var_248], r15d
0x18001ac7b  mov     [rsp+280h+var_250], rsi
0x18001ac80  mov     [rsp+280h+lpcbData], r12
0x18001ac85  mov     [rsp+280h+lpData], rdi
0x18001ac8a  lea     r9, aRegqueryvaluee; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x18001ac91  mov     r8d, ebx
0x18001ac94  mov     rdx, rax
0x18001ac97  lea     rcx, [rbp+180h+var_F0]
0x18001ac9e  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x18001aca4  mov     r14d, [rsp+280h+cbData]
0x18001aca9  mov     r15d, [rsp+280h+Type]
0x18001acae  lea     rcx, [rdi+10h]; this
0x18001acb2  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x18001acb7  mov     r12, rax
0x18001acba  mov     rdi, [rdi+8]
0x18001acbe  test    ebx, ebx
0x18001acc0  jle     short loc_18001ACCB
0x18001acc2  movzx   ebx, bx
0x18001acc5  or      ebx, 80070000h
0x18001accb  lea     rax, [rbp+180h+var_180]
0x18001accf  mov     [rsp+280h+var_218], rax
0x18001acd4  mov     dword ptr [rsp+280h+lpcbData], 11h
0x18001acdc  mov     dword ptr [rsp+280h+lpData], 295h
0x18001ace4  lea     r9, aCsrmregistryke; "CSrmRegistryKey::GetValue"
0x18001aceb  lea     r8, aSrmregsc; "SRMREGSC"
0x18001acf2  lea     rdx, aBaseFsFsrmUtil_3; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x18001acf9  lea     rcx, [rbp+180h+var_180]
0x18001acfd  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18001ad02  nop
0x18001ad03  mov     [rsp+280h+var_240], r14d
0x18001ad08  mov     dword ptr [rsp+280h+var_248], r15d
0x18001ad0d  mov     [rsp+280h+var_250], rsi
0x18001ad12  mov     [rsp+280h+lpcbData], r12
0x18001ad17  mov     [rsp+280h+lpData], rdi
0x18001ad1c  lea     r9, aRegqueryvaluee; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x18001ad23  mov     r8d, ebx
0x18001ad26  mov     rdx, rax
0x18001ad29  lea     rcx, [rbp+180h+var_F0]
0x18001ad30  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x18001ad36  lea     rcx, [rdi+10h]; this
0x18001ad3a  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x18001ad3f  mov     rbx, rax
0x18001ad42  mov     rdi, [rdi+8]
0x18001ad46  lea     rax, [rbp+180h+var_180]
0x18001ad4a  mov     [rsp+280h+var_218], rax
0x18001ad4f  mov     dword ptr [rsp+280h+lpcbData], 11h
0x18001ad57  mov     dword ptr [rsp+280h+lpData], 29Bh
0x18001ad5f  lea     r9, aCsrmregistryke; "CSrmRegistryKey::GetValue"
0x18001ad66  lea     r8, aSrmregsc; "SRMREGSC"
0x18001ad6d  lea     rdx, aBaseFsFsrmUtil_3; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x18001ad74  lea     rcx, [rbp+180h+var_180]
0x18001ad78  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18001ad7d  nop
0x18001ad7e  mov     [rsp+280h+var_248], rsi
0x18001ad83  mov     [rsp+280h+var_250], rbx
0x18001ad88  mov     [rsp+280h+lpcbData], rdi
0x18001ad8d  mov     dword ptr [rsp+280h+lpData], r14d
0x18001ad92  lea     r9, aUnexpectedType; "Unexpected type %lu for a DWORD value 0"...
0x18001ad99  mov     r8d, 80045316h
0x18001ad9f  mov     rdx, rax
0x18001ada2  lea     rcx, [rbp+180h+var_F0]
0x18001ada9  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18001adaf  lea     rcx, [rdi+10h]; this
0x18001adb3  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x18001adb8  mov     rbx, rax
0x18001adbb  mov     rdi, [rdi+8]
0x18001adbf  lea     rax, [rbp+180h+var_180]
0x18001adc3  mov     [rsp+280h+var_218], rax
0x18001adc8  mov     dword ptr [rsp+280h+lpcbData], 11h
0x18001add0  mov     dword ptr [rsp+280h+lpData], 29Eh
0x18001add8  lea     r9, aCsrmregistryke; "CSrmRegistryKey::GetValue"
0x18001addf  lea     r8, aSrmregsc; "SRMREGSC"
0x18001ade6  lea     rdx, aBaseFsFsrmUtil_3; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x18001aded  lea     rcx, [rbp+180h+var_180]
0x18001adf1  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18001adf6  nop
0x18001adf7  mov     [rsp+280h+var_248], rsi
0x18001adfc  mov     [rsp+280h+var_250], rbx
0x18001ae01  mov     [rsp+280h+lpcbData], rdi
0x18001ae06  mov     dword ptr [rsp+280h+lpData], r12d
0x18001ae0b  lea     r9, aUnexpectedSize; "Unexpected size %lu for a DWORD value 0"...
0x18001ae12  mov     r8d, 80045316h
0x18001ae18  mov     rdx, rax
0x18001ae1b  lea     rcx, [rbp+180h+var_F0]
0x18001ae22  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
