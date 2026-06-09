# CProviderRegistrationClass::Init(void)

- ea: `0x180069744`
- end: `0x180069ade`
- name: `?Init@CProviderRegistrationClass@@QEAAXXZ`
- size: `922`
- prototype: `void __fastcall(CProviderRegistrationClass *__hidden this)`
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800684dc`
- `0x1800687d8`
- `0x180068a20`
- `0x18006adb4`
- `0x1800b6844`
- `0x1800b82c0`

## callees

- `0x180069744`
- `0x18006abcc`
- `0x180085c70`
- `0x18008846c`
- `0x18008a658`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800699f4`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800699f4`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x180069812`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x18006994f`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x180069812`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x18006994f`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800698af`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800698af`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800698a3`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800698a3`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180069a86`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180069a92`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180069a9e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180069aa9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180069a86`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180069a92`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180069a9e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180069aa9`
- `wbemcomn!GetMemLogObject` at `0x1800697a1`
- `wbemcomn!GetMemLogObject` at `0x18006983d`
- `wbemcomn!GetMemLogObject` at `0x1800698dd`
- `wbemcomn!GetMemLogObject` at `0x180069987`
- `wbemcomn!GetMemLogObject` at `0x180069a20`
- `wbemcomn!GetMemLogObject` at `0x1800697a1`
- `wbemcomn!GetMemLogObject` at `0x18006983d`
- `wbemcomn!GetMemLogObject` at `0x1800698dd`
- `wbemcomn!GetMemLogObject` at `0x180069987`
- `wbemcomn!GetMemLogObject` at `0x180069a20`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800697af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006984b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800698eb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180069995`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180069a2e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800697af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006984b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800698eb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180069995`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180069a2e`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x180069ab4`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x180069ab4`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x180069792`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x180069792`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CProviderRegistrationClass::Init(CProviderRegistrationClass *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  CMemoryLog *v6; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v9[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v10[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v11[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v12[864]; // [rsp+C0h] [rbp-40h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v12);
  CSystemClass::Init((CSystemClass *)v12);
  if ( CWbemClass::CreateDerivedClass(this, (struct CWbemClass *)v12, 0, 0) == -2147217402 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        87,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v11, 8, L"__ProviderRegistration");
  if ( (*(unsigned int (__fastcall **)(CProviderRegistrationClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
         this,
         L"__CLASS",
         v11,
         0) == -2147217402 )
  {
    v3 = GetMemLogObject();
    CMemoryLog::Write(v3, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8);
  CVar::SetAsNull((CVar *)v8);
  if ( (*(unsigned int (__fastcall **)(CProviderRegistrationClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"Provider",
         v8,
         102) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v10, 8, L"ref:__Provider");
  if ( (*(unsigned int (__fastcall **)(CProviderRegistrationClass *, const wchar_t *, const wchar_t *, _QWORD, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"Provider",
         L"cimtype",
         0,
         v10) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CProviderRegistrationClass *, const wchar_t *, _BYTE *, _QWORD))(*(_QWORD *)this + 984LL))(
         this,
         L"abstract",
         v9,
         0) == -2147217402 )
  {
    v6 = GetMemLogObject();
    CMemoryLog::Write(v6, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        91,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v9);
  CVar::~CVar((CVar *)v10);
  CVar::~CVar((CVar *)v8);
  CVar::~CVar((CVar *)v11);
  CWbemClass::~CWbemClass((CWbemClass *)v12);
}

```

## disassembly

```asm
0x180069744  mov     [rsp-8+arg_8], rbx
0x180069749  mov     [rsp-8+arg_10], rdi
0x18006974e  push    rbp
0x18006974f  lea     rbp, [rsp-330h]
0x180069757  sub     rsp, 430h
0x18006975e  mov     rax, cs:__security_cookie
0x180069765  xor     rax, rsp
0x180069768  mov     [rbp+330h+var_10], rax
0x18006976f  mov     rbx, rcx
0x180069772  lea     rcx, [rbp+330h+var_370]; this
0x180069776  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x18006977b  nop
0x18006977c  lea     rcx, [rbp+330h+var_370]; this
0x180069780  call    ?Init@CSystemClass@@QEAAXXZ; CSystemClass::Init(void)
0x180069785  xor     r9d, r9d
0x180069788  xor     r8d, r8d
0x18006978b  lea     rdx, [rbp+330h+var_370]
0x18006978f  mov     rcx, rbx
0x180069792  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x180069798  mov     edi, 80041006h
0x18006979d  cmp     eax, edi
0x18006979f  jnz     short loc_180069802
0x1800697a1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800697a7  mov     edx, 0FFFFFFFEh
0x1800697ac  mov     rcx, rax
0x1800697af  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800697b5  lea     rax, WPP_GLOBAL_Control
0x1800697bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800697c3  cmp     rcx, rax
0x1800697c6  jz      short loc_1800697F0
0x1800697c8  test    byte ptr [rcx+1Ch], 1
0x1800697cc  jz      short loc_1800697F0
0x1800697ce  cmp     byte ptr [rcx+19h], 2
0x1800697d2  jb      short loc_1800697F0
0x1800697d4  mov     edx, 57h ; 'W'
0x1800697d9  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800697e0  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800697e7  mov     rcx, [rcx+10h]
0x1800697eb  call    WPP_SF_s
0x1800697f0  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800697f7  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800697fc  call    _CxxThrowException_0
0x180069802  lea     r8, aProviderregist; "__ProviderRegistration"
0x180069809  mov     edx, 8
0x18006980e  lea     rcx, [rbp+330h+var_398]
0x180069812  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x180069818  nop
0x180069819  mov     rax, [rbx]
0x18006981c  xor     r9d, r9d
0x18006981f  lea     r8, [rbp+330h+var_398]
0x180069823  lea     rdx, aClass_0; "__CLASS"
0x18006982a  mov     rcx, rbx
0x18006982d  mov     rax, [rax+368h]
0x180069834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069839  cmp     eax, edi
0x18006983b  jnz     short loc_18006989E
0x18006983d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180069843  mov     edx, 0FFFFFFFEh
0x180069848  mov     rcx, rax
0x18006984b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180069851  lea     rax, WPP_GLOBAL_Control
0x180069858  mov     rcx, cs:WPP_GLOBAL_Control
0x18006985f  cmp     rcx, rax
0x180069862  jz      short loc_18006988C
0x180069864  test    byte ptr [rcx+1Ch], 1
0x180069868  jz      short loc_18006988C
0x18006986a  cmp     byte ptr [rcx+19h], 2
0x18006986e  jb      short loc_18006988C
0x180069870  mov     edx, 58h ; 'X'
0x180069875  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18006987c  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x180069883  mov     rcx, [rcx+10h]
0x180069887  call    WPP_SF_s
0x18006988c  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180069893  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x180069898  call    _CxxThrowException_0
0x18006989e  lea     rcx, [rsp+430h+var_3F8]
0x1800698a3  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800698a9  nop
0x1800698aa  lea     rcx, [rsp+430h+var_3F8]
0x1800698af  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800698b5  mov     rax, [rbx]
0x1800698b8  mov     r9d, 66h ; 'f'
0x1800698be  lea     r8, [rsp+430h+var_3F8]
0x1800698c3  lea     rdx, aProvider_0; "Provider"
0x1800698ca  mov     rcx, rbx
0x1800698cd  mov     rax, [rax+368h]
0x1800698d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698d9  cmp     eax, edi
0x1800698db  jnz     short loc_18006993E
0x1800698dd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800698e3  mov     edx, 0FFFFFFFEh
0x1800698e8  mov     rcx, rax
0x1800698eb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800698f1  lea     rax, WPP_GLOBAL_Control
0x1800698f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800698ff  cmp     rcx, rax
0x180069902  jz      short loc_18006992C
0x180069904  test    byte ptr [rcx+1Ch], 1
0x180069908  jz      short loc_18006992C
0x18006990a  cmp     byte ptr [rcx+19h], 2
0x18006990e  jb      short loc_18006992C
0x180069910  mov     edx, 59h ; 'Y'
0x180069915  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18006991c  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x180069923  mov     rcx, [rcx+10h]
0x180069927  call    WPP_SF_s
0x18006992c  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180069933  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x180069938  call    _CxxThrowException_0
0x18006993e  lea     r8, aRefProvider; "ref:__Provider"
0x180069945  mov     edx, 8
0x18006994a  lea     rcx, [rsp+430h+var_3B8]
0x18006994f  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x180069955  nop
0x180069956  mov     rax, [rbx]
0x180069959  lea     rcx, [rsp+430h+var_3B8]
0x18006995e  mov     [rsp+430h+var_410], rcx
0x180069963  xor     r9d, r9d
0x180069966  lea     r8, aCimtype; "cimtype"
0x18006996d  lea     rdx, aProvider_0; "Provider"
0x180069974  mov     rcx, rbx
0x180069977  mov     rax, [rax+378h]
0x18006997e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069983  cmp     eax, edi
0x180069985  jnz     short loc_1800699E8
0x180069987  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006998d  mov     edx, 0FFFFFFFEh
0x180069992  mov     rcx, rax
0x180069995  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006999b  lea     rax, WPP_GLOBAL_Control
0x1800699a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800699a9  cmp     rcx, rax
0x1800699ac  jz      short loc_1800699D6
0x1800699ae  test    byte ptr [rcx+1Ch], 1
0x1800699b2  jz      short loc_1800699D6
0x1800699b4  cmp     byte ptr [rcx+19h], 2
0x1800699b8  jb      short loc_1800699D6
0x1800699ba  mov     edx, 5Ah ; 'Z'
0x1800699bf  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800699c6  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800699cd  mov     rcx, [rcx+10h]
0x1800699d1  call    WPP_SF_s
0x1800699d6  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800699dd  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800699e2  call    _CxxThrowException_0
0x1800699e8  or      edx, 0FFFFFFFFh
0x1800699eb  lea     r8d, [rdx+0Ch]
0x1800699ef  lea     rcx, [rsp+430h+var_3D8]
0x1800699f4  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800699fa  nop
0x1800699fb  mov     rax, [rbx]
0x1800699fe  xor     r9d, r9d
0x180069a01  lea     r8, [rsp+430h+var_3D8]
0x180069a06  lea     rdx, aAbstract_1; "abstract"
0x180069a0d  mov     rcx, rbx
0x180069a10  mov     rax, [rax+3D8h]
0x180069a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a1c  cmp     eax, edi
0x180069a1e  jnz     short loc_180069A81
0x180069a20  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180069a26  mov     edx, 0FFFFFFFEh
0x180069a2b  mov     rcx, rax
0x180069a2e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180069a34  lea     rax, WPP_GLOBAL_Control
0x180069a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180069a42  cmp     rcx, rax
0x180069a45  jz      short loc_180069A6F
0x180069a47  test    byte ptr [rcx+1Ch], 1
0x180069a4b  jz      short loc_180069A6F
0x180069a4d  cmp     byte ptr [rcx+19h], 2
0x180069a51  jb      short loc_180069A6F
0x180069a53  mov     edx, 5Bh ; '['
0x180069a58  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180069a5f  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x180069a66  mov     rcx, [rcx+10h]
0x180069a6a  call    WPP_SF_s
0x180069a6f  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180069a76  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x180069a7b  call    _CxxThrowException_0
0x180069a81  lea     rcx, [rsp+430h+var_3D8]
0x180069a86  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180069a8c  nop
0x180069a8d  lea     rcx, [rsp+430h+var_3B8]
0x180069a92  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180069a98  nop
0x180069a99  lea     rcx, [rsp+430h+var_3F8]
0x180069a9e  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180069aa4  nop
0x180069aa5  lea     rcx, [rbp+330h+var_398]
0x180069aa9  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180069aaf  nop
0x180069ab0  lea     rcx, [rbp+330h+var_370]
0x180069ab4  call    cs:__imp_??1CWbemClass@@UEAA@XZ; CWbemClass::~CWbemClass(void)
0x180069aba  mov     rcx, [rbp+330h+var_10]
0x180069ac1  xor     rcx, rsp; StackCookie
0x180069ac4  call    __security_check_cookie
0x180069ac9  lea     r11, [rsp+430h+var_s0]
0x180069ad1  mov     rbx, [r11+18h]
0x180069ad5  mov     rdi, [r11+20h]
0x180069ad9  mov     rsp, r11
0x180069adc  pop     rbp
0x180069add  retn
```
