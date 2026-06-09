# CSrmRegistryKey::GetMultiszValue(ushort const *,ushort * *,ulong *,bool)

- ea: `0x180075ab0`
- end: `0x180075eb0`
- name: `?GetMultiszValue@CSrmRegistryKey@@QEAA_NPEBGPEAPEAGPEAK_N@Z`
- size: `1024`
- prototype: `bool __fastcall(CSrmRegistryKey *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned int *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x1800a53a4`

## callees

- `0x18000ac44`
- `0x18000ad14`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x18007424c`
- `0x180074a04`
- `0x180075ab0`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180075cb5`
- `ole32!CoTaskMemFree` at `0x180075cb5`
- `ADVAPI32!RegQueryValueExW` at `0x180075b92`
- `ADVAPI32!RegQueryValueExW` at `0x180075c5f`
- `ADVAPI32!RegQueryValueExW` at `0x180075b92`
- `ADVAPI32!RegQueryValueExW` at `0x180075c5f`

## string_xrefs

- `0x180075aee`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x180075d57`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x180075dee`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x180075e6f`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x180075afa`: `CSrmRegistryKey::GetMultiszValue`
- `0x180075d49`: `CSrmRegistryKey::GetMultiszValue`
- `0x180075de0`: `CSrmRegistryKey::GetMultiszValue`
- `0x180075e61`: `CSrmRegistryKey::GetMultiszValue`
- `0x180075b84`: `ReparsePointTagsToClassify`
- `0x180075c54`: `ReparsePointTagsToClassify`
- `0x180075d71`: `ReparsePointTagsToClassify`
- `0x180075e08`: `ReparsePointTagsToClassify`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall CSrmRegistryKey::GetMultiszValue(
        HKEY *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  int v7; // ebx
  DWORD v9; // esi
  unsigned __int64 v10; // r14
  unsigned __int16 *v11; // rsi
  BYTE *v12; // rax
  signed int v13; // ebx
  DWORD v14; // esi
  DWORD v15; // r14d
  unsigned __int16 *v16; // r15
  HKEY v17; // rdi
  __int64 v18; // rax
  DWORD v19; // esi
  DWORD v20; // r14d
  unsigned __int16 *Buffer; // r15
  HKEY v22; // rdi
  __int64 v23; // rax
  unsigned __int16 *v24; // rbx
  HKEY v25; // rdi
  __int64 v26; // rax
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  LPBYTE v28; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD lpcbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v32; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE *v33; // [rsp+68h] [rbp-98h]
  _QWORD v34[3]; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+88h] [rbp-78h]
  int v36; // [rsp+8Ch] [rbp-74h]
  int v37; // [rsp+90h] [rbp-70h]
  _BYTE v38[96]; // [rsp+98h] [rbp-68h] BYREF
  int v39; // [rsp+F8h] [rbp-8h]
  _BYTE v40[144]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v41[22]; // [rsp+190h] [rbp+90h] BYREF

  v28 = (LPBYTE)v34;
  v34[0] = L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp";
  v34[1] = L"CSrmRegistryKey::GetMultiszValue";
  v34[2] = L"SRMREGSC";
  v35 = 790;
  v36 = 17;
  v37 = 255;
  v39 = 0x1000000;
  memset_0(v38, 0, sizeof(v38));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v41, (const struct CSrmDebugInfo *)v34, 0);
  *a3 = 0;
  Type = 0;
  cbData = 0;
  v7 = RegQueryValueExW(this[1], L"ReparsePointTagsToClassify", 0, &Type, 0, &cbData);
  if ( v7 == 2 )
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
    if ( v7 && v7 != 234 )
    {
      v19 = cbData;
      v20 = Type;
      Buffer = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)(this + 2));
      v22 = this[1];
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      v28 = v40;
      v23 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v40,
              (__int64)L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
              (__int64)L"SRMREGSC",
              (__int64)L"CSrmRegistryKey::GetMultiszValue",
              823,
              17);
      CSrmFunctionTracer::TranslateGenericError(
        v41,
        v23,
        (unsigned int)v7,
        L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu])",
        v22,
        Buffer,
        L"ReparsePointTagsToClassify",
        v20,
        v19);
    }
    v9 = Type;
    if ( Type != 7 )
    {
      v24 = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)(this + 2));
      v25 = this[1];
      v28 = v40;
      v26 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v40,
              (__int64)L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
              (__int64)L"SRMREGSC",
              (__int64)L"CSrmRegistryKey::GetMultiszValue",
              829,
              17);
      LODWORD(lpData) = v9;
      CSrmFunctionTracer::Throw(
        v41,
        v26,
        2147767062LL,
        L"Unexpected type %lu for a binary value 0x%08lx(%s),%s",
        lpData,
        v25,
        v24,
        L"ReparsePointTagsToClassify");
    }
    v28 = 0;
    v10 = cbData >> 1;
    CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&v28, v10);
    v32 = 0;
    lpcbData = 2 * v10;
    v11 = (unsigned __int16 *)v28;
    LODWORD(v12) = RegQueryValueExW(this[1], L"ReparsePointTagsToClassify", 0, &v32, v28, &lpcbData);
    v13 = (int)v12;
    if ( (_DWORD)v12 )
    {
      v14 = lpcbData;
      v15 = v32;
      v16 = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)(this + 2));
      v17 = this[1];
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      v33 = v40;
      v18 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v40,
              (__int64)L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
              (__int64)L"SRMREGSC",
              (__int64)L"CSrmRegistryKey::GetMultiszValue",
              850,
              17);
      CSrmFunctionTracer::TranslateGenericError(
        v41,
        v18,
        (unsigned int)v13,
        L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu])",
        v17,
        v16,
        L"ReparsePointTagsToClassify",
        v15,
        v14);
    }
    v11[v10] = 0;
    v28 = v12;
    *a3 = v11;
    *a4 = lpcbData >> 1;
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)v41,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"TRUE");
    CoTaskMemFree(0);
    v28 = 0;
    v41[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v41);
    return 1;
  }
}

```

## disassembly

```asm
0x180075ab0  push    rbp
0x180075ab2  push    rbx
0x180075ab3  push    rsi
0x180075ab4  push    rdi
0x180075ab5  push    r12
0x180075ab7  push    r14
0x180075ab9  push    r15
0x180075abb  lea     rbp, [rsp-150h]
0x180075ac3  sub     rsp, 250h
0x180075aca  mov     rax, cs:__security_cookie
0x180075ad1  xor     rax, rsp
0x180075ad4  mov     [rbp+180h+var_40], rax
0x180075adb  mov     r12, r9
0x180075ade  mov     r15, r8
0x180075ae1  mov     rdi, rcx
0x180075ae4  lea     rax, [rsp+280h+var_210]
0x180075ae9  mov     [rsp+280h+var_230], rax
0x180075aee  lea     rax, aBaseFsFsrmUtil_16; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x180075af5  mov     [rsp+280h+var_210], rax
0x180075afa  lea     rax, aCsrmregistryke_3; "CSrmRegistryKey::GetMultiszValue"
0x180075b01  mov     [rsp+280h+var_208], rax
0x180075b06  lea     rax, aSrmregsc; "SRMREGSC"
0x180075b0d  mov     [rbp+180h+var_200], rax
0x180075b11  mov     [rbp+180h+var_1F8], 316h
0x180075b18  mov     [rbp+180h+var_1F4], 11h
0x180075b1f  mov     [rbp+180h+var_1F0], 0FFh
0x180075b26  mov     [rbp+180h+var_188], 1000000h
0x180075b2d  xor     edx, edx; Val
0x180075b2f  lea     r8d, [rdx+60h]; Size
0x180075b33  lea     rcx, [rbp+180h+var_1E8]; void *
0x180075b37  call    memset_0
0x180075b3c  nop
0x180075b3d  xor     r8d, r8d
0x180075b40  lea     rdx, [rsp+280h+var_210]
0x180075b45  lea     rcx, [rbp+180h+var_F0]
0x180075b4c  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180075b51  nop
0x180075b52  mov     qword ptr [r15], 0
0x180075b59  mov     [rsp+280h+Type], 0
0x180075b61  mov     [rsp+280h+cbData], 0
0x180075b69  lea     rax, [rsp+280h+cbData]
0x180075b6e  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180075b73  mov     [rsp+280h+lpData], 0; lpData
0x180075b7c  lea     r9, [rsp+280h+Type]; lpType
0x180075b81  xor     r8d, r8d; lpReserved
0x180075b84  lea     r14, ValueName; "ReparsePointTagsToClassify"
0x180075b8b  mov     rdx, r14; lpValueName
0x180075b8e  mov     rcx, [rdi+8]; hKey
0x180075b92  call    cs:__imp_RegQueryValueExW
0x180075b98  mov     ebx, eax
0x180075b9a  cmp     eax, 2
0x180075b9d  jnz     short loc_180075BED
0x180075b9f  lea     rax, aFalse; "FALSE"
0x180075ba6  mov     [rsp+280h+lpData], rax
0x180075bab  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180075bb2  mov     r8d, 0AAh; unsigned int
0x180075bb8  lea     rdx, aReturn; "RETURN"
0x180075bbf  lea     rcx, [rbp+180h+var_F0]; this
0x180075bc6  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180075bcb  nop
0x180075bcc  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180075bd3  mov     [rbp+180h+var_F0], rax
0x180075bda  lea     rcx, [rbp+180h+var_F0]; this
0x180075be1  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180075be6  xor     al, al
0x180075be8  jmp     loc_180075CE9
0x180075bed  test    ebx, ebx
0x180075bef  jz      short loc_180075BFD
0x180075bf1  cmp     ebx, 0EAh
0x180075bf7  jnz     loc_180075DA1
0x180075bfd  mov     esi, [rsp+280h+Type]
0x180075c01  cmp     esi, 7
0x180075c04  jnz     loc_180075E38
0x180075c0a  mov     [rsp+280h+var_230], 0
0x180075c13  mov     eax, [rsp+280h+cbData]
0x180075c17  shr     eax, 1
0x180075c19  mov     r14d, eax
0x180075c1c  mov     edx, eax; unsigned __int64
0x180075c1e  lea     rcx, [rsp+280h+var_230]; this
0x180075c23  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x180075c28  mov     [rsp+280h+var_21C], 0
0x180075c30  lea     eax, [r14+r14]
0x180075c34  mov     [rsp+280h+var_220], eax
0x180075c38  lea     rax, [rsp+280h+var_220]
0x180075c3d  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180075c42  mov     rsi, [rsp+280h+var_230]
0x180075c47  mov     [rsp+280h+lpData], rsi; lpData
0x180075c4c  lea     r9, [rsp+280h+var_21C]; lpType
0x180075c51  xor     r8d, r8d; lpReserved
0x180075c54  lea     rdx, ValueName; "ReparsePointTagsToClassify"
0x180075c5b  mov     rcx, [rdi+8]; hKey
0x180075c5f  call    cs:__imp_RegQueryValueExW
0x180075c65  mov     ebx, eax
0x180075c67  test    eax, eax
0x180075c69  jnz     loc_180075D0A
0x180075c6f  mov     [rsi+r14*2], ax
0x180075c74  mov     [rsp+280h+var_230], rax
0x180075c79  mov     [r15], rsi
0x180075c7c  mov     eax, [rsp+280h+var_220]
0x180075c80  shr     eax, 1
0x180075c82  mov     [r12], eax
0x180075c86  lea     rax, aTrue_0; "TRUE"
0x180075c8d  mov     [rsp+280h+lpData], rax
0x180075c92  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180075c99  mov     r8d, 0AAh; unsigned int
0x180075c9f  lea     rdx, aReturn; "RETURN"
0x180075ca6  lea     rcx, [rbp+180h+var_F0]; this
0x180075cad  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180075cb2  nop
0x180075cb3  xor     ecx, ecx; pv
0x180075cb5  call    cs:__imp_CoTaskMemFree
0x180075cbb  mov     [rsp+280h+var_230], 0
0x180075cc4  mov     [rsp+280h+var_230], 0
0x180075ccd  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180075cd4  mov     [rbp+180h+var_F0], rax
0x180075cdb  lea     rcx, [rbp+180h+var_F0]; this
0x180075ce2  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180075ce7  mov     al, 1
0x180075ce9  mov     rcx, [rbp+180h+var_40]
0x180075cf0  xor     rcx, rsp; StackCookie
0x180075cf3  call    __security_check_cookie
0x180075cf8  add     rsp, 250h
0x180075cff  pop     r15
0x180075d01  pop     r14
0x180075d03  pop     r12
0x180075d05  pop     rdi
0x180075d06  pop     rsi
0x180075d07  pop     rbx
0x180075d08  pop     rbp
0x180075d09  retn
0x180075d0a  mov     esi, [rsp+280h+var_220]
0x180075d0e  mov     r14d, [rsp+280h+var_21C]
0x180075d13  lea     rcx, [rdi+10h]; this
0x180075d17  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180075d1c  mov     r15, rax
0x180075d1f  mov     rdi, [rdi+8]
0x180075d23  test    ebx, ebx
0x180075d25  jle     short loc_180075D30
0x180075d27  movzx   ebx, bx
0x180075d2a  or      ebx, 80070000h
0x180075d30  lea     rax, [rbp+180h+var_180]
0x180075d34  mov     [rsp+280h+var_218], rax
0x180075d39  mov     dword ptr [rsp+280h+lpcbData], 11h
0x180075d41  mov     dword ptr [rsp+280h+lpData], 352h
0x180075d49  lea     r9, aCsrmregistryke_3; "CSrmRegistryKey::GetMultiszValue"
0x180075d50  lea     r8, aSrmregsc; "SRMREGSC"
0x180075d57  lea     rdx, aBaseFsFsrmUtil_16; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x180075d5e  lea     rcx, [rbp+180h+var_180]
0x180075d62  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180075d67  nop
0x180075d68  mov     [rsp+280h+var_240], esi
0x180075d6c  mov     dword ptr [rsp+280h+var_248], r14d
0x180075d71  lea     rcx, ValueName; "ReparsePointTagsToClassify"
0x180075d78  mov     [rsp+280h+var_250], rcx
0x180075d7d  mov     [rsp+280h+lpcbData], r15
0x180075d82  mov     [rsp+280h+lpData], rdi
0x180075d87  lea     r9, aRegqueryvaluee; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x180075d8e  mov     r8d, ebx
0x180075d91  mov     rdx, rax
0x180075d94  lea     rcx, [rbp+180h+var_F0]
0x180075d9b  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x180075da1  mov     esi, [rsp+280h+cbData]
0x180075da5  mov     r14d, [rsp+280h+Type]
0x180075daa  lea     rcx, [rdi+10h]; this
0x180075dae  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180075db3  mov     r15, rax
0x180075db6  mov     rdi, [rdi+8]
0x180075dba  test    ebx, ebx
0x180075dbc  jle     short loc_180075DC7
0x180075dbe  movzx   ebx, bx
0x180075dc1  or      ebx, 80070000h
0x180075dc7  lea     rax, [rbp+180h+var_180]
0x180075dcb  mov     [rsp+280h+var_230], rax
0x180075dd0  mov     dword ptr [rsp+280h+lpcbData], 11h
0x180075dd8  mov     dword ptr [rsp+280h+lpData], 337h
0x180075de0  lea     r9, aCsrmregistryke_3; "CSrmRegistryKey::GetMultiszValue"
0x180075de7  lea     r8, aSrmregsc; "SRMREGSC"
0x180075dee  lea     rdx, aBaseFsFsrmUtil_16; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x180075df5  lea     rcx, [rbp+180h+var_180]
0x180075df9  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180075dfe  nop
0x180075dff  mov     [rsp+280h+var_240], esi
0x180075e03  mov     dword ptr [rsp+280h+var_248], r14d
0x180075e08  lea     rcx, ValueName; "ReparsePointTagsToClassify"
0x180075e0f  mov     [rsp+280h+var_250], rcx
0x180075e14  mov     [rsp+280h+lpcbData], r15
0x180075e19  mov     [rsp+280h+lpData], rdi
0x180075e1e  lea     r9, aRegqueryvaluee; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x180075e25  mov     r8d, ebx
0x180075e28  mov     rdx, rax
0x180075e2b  lea     rcx, [rbp+180h+var_F0]
0x180075e32  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x180075e38  lea     rcx, [rdi+10h]; this
0x180075e3c  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180075e41  mov     rbx, rax
0x180075e44  mov     rdi, [rdi+8]
0x180075e48  lea     rax, [rbp+180h+var_180]
0x180075e4c  mov     [rsp+280h+var_230], rax
0x180075e51  mov     dword ptr [rsp+280h+lpcbData], 11h
0x180075e59  mov     dword ptr [rsp+280h+lpData], 33Dh
0x180075e61  lea     r9, aCsrmregistryke_3; "CSrmRegistryKey::GetMultiszValue"
0x180075e68  lea     r8, aSrmregsc; "SRMREGSC"
0x180075e6f  lea     rdx, aBaseFsFsrmUtil_16; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x180075e76  lea     rcx, [rbp+180h+var_180]
0x180075e7a  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180075e7f  nop
0x180075e80  mov     [rsp+280h+var_248], r14
0x180075e85  mov     [rsp+280h+var_250], rbx
0x180075e8a  mov     [rsp+280h+lpcbData], rdi
0x180075e8f  mov     dword ptr [rsp+280h+lpData], esi
0x180075e93  lea     r9, aUnexpectedType_0; "Unexpected type %lu for a binary value "...
0x180075e9a  mov     r8d, 80045316h
0x180075ea0  mov     rdx, rax
0x180075ea3  lea     rcx, [rbp+180h+var_F0]
0x180075eaa  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
