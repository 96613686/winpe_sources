# CPropertyProviderRegistrationClass::Init(void)

- ea: `0x1800b82c0`
- end: `0x1800b8636`
- name: `?Init@CPropertyProviderRegistrationClass@@QEAAXXZ`
- size: `886`
- prototype: `void __fastcall(CPropertyProviderRegistrationClass *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`

## callees

- `0x180069744`
- `0x180085c70`
- `0x180086358`
- `0x18008846c`
- `0x18008a658`
- `0x1800b82c0`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b8427`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b854c`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b8427`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b854c`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b838f`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b838f`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b85ea`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b85f6`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b8602`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b85ea`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b85f6`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b8602`
- `wbemcomn!GetMemLogObject` at `0x1800b831d`
- `wbemcomn!GetMemLogObject` at `0x1800b83bb`
- `wbemcomn!GetMemLogObject` at `0x1800b8456`
- `wbemcomn!GetMemLogObject` at `0x1800b84df`
- `wbemcomn!GetMemLogObject` at `0x1800b8584`
- `wbemcomn!GetMemLogObject` at `0x1800b831d`
- `wbemcomn!GetMemLogObject` at `0x1800b83bb`
- `wbemcomn!GetMemLogObject` at `0x1800b8456`
- `wbemcomn!GetMemLogObject` at `0x1800b84df`
- `wbemcomn!GetMemLogObject` at `0x1800b8584`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b832b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b83c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b8464`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b84ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b8592`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b832b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b83c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b8464`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b84ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b8592`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b830e`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b830e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CPropertyProviderRegistrationClass::Init(CPropertyProviderRegistrationClass *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  CMemoryLog *v6; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v9[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v10[40]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v11[864]; // [rsp+A0h] [rbp-60h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v11);
  CProviderRegistrationClass::Init((CProviderRegistrationClass *)v11);
  if ( CWbemClass::CreateDerivedClass(this, (struct CWbemClass *)v11, 0, 0) == -2147217402 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        127,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v10, 8, L"__PropertyProviderRegistration");
  if ( (*(unsigned int (__fastcall **)(CPropertyProviderRegistrationClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
         this,
         L"__CLASS",
         v10,
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
        128,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8, 0, 11);
  if ( (*(unsigned int (__fastcall **)(CPropertyProviderRegistrationClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"SupportsPut",
         v8,
         11) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        129,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( (*(unsigned int (__fastcall **)(CPropertyProviderRegistrationClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"SupportsGet",
         v8,
         11) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        130,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CPropertyProviderRegistrationClass *, const wchar_t *, const wchar_t *, _QWORD, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"Provider",
         L"key",
         0,
         v9) == -2147217402 )
  {
    v6 = GetMemLogObject();
    CMemoryLog::Write(v6, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        131,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v9);
  CVar::~CVar((CVar *)v8);
  CVar::~CVar((CVar *)v10);
  CSystemEventClass::~CSystemEventClass((CSystemEventClass *)v11);
}

```

## disassembly

```asm
0x1800b82c0  mov     [rsp-8+arg_8], rbx
0x1800b82c5  mov     [rsp-8+arg_10], rdi
0x1800b82ca  push    rbp
0x1800b82cb  lea     rbp, [rsp-310h]
0x1800b82d3  sub     rsp, 410h
0x1800b82da  mov     rax, cs:__security_cookie
0x1800b82e1  xor     rax, rsp
0x1800b82e4  mov     [rbp+310h+var_10], rax
0x1800b82eb  mov     rbx, rcx
0x1800b82ee  lea     rcx, [rbp+310h+var_370]; this
0x1800b82f2  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800b82f7  nop
0x1800b82f8  lea     rcx, [rbp+310h+var_370]; this
0x1800b82fc  call    ?Init@CProviderRegistrationClass@@QEAAXXZ; CProviderRegistrationClass::Init(void)
0x1800b8301  xor     r9d, r9d
0x1800b8304  xor     r8d, r8d
0x1800b8307  lea     rdx, [rbp+310h+var_370]
0x1800b830b  mov     rcx, rbx
0x1800b830e  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800b8314  mov     edi, 80041006h
0x1800b8319  cmp     eax, edi
0x1800b831b  jnz     short loc_1800B837E
0x1800b831d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b8323  mov     edx, 0FFFFFFFEh
0x1800b8328  mov     rcx, rax
0x1800b832b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b8331  lea     rax, WPP_GLOBAL_Control
0x1800b8338  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b833f  cmp     rcx, rax
0x1800b8342  jz      short loc_1800B836C
0x1800b8344  test    byte ptr [rcx+1Ch], 1
0x1800b8348  jz      short loc_1800B836C
0x1800b834a  cmp     byte ptr [rcx+19h], 2
0x1800b834e  jb      short loc_1800B836C
0x1800b8350  mov     edx, 7Fh
0x1800b8355  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b835c  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b8363  mov     rcx, [rcx+10h]
0x1800b8367  call    WPP_SF_s
0x1800b836c  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b8373  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b8378  call    _CxxThrowException_0
0x1800b837e  lea     r8, aPropertyprovid; "__PropertyProviderRegistration"
0x1800b8385  mov     edx, 8
0x1800b838a  lea     rcx, [rsp+410h+var_398]
0x1800b838f  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b8395  nop
0x1800b8396  mov     rax, [rbx]
0x1800b8399  xor     r9d, r9d
0x1800b839c  lea     r8, [rsp+410h+var_398]
0x1800b83a1  lea     rdx, aClass_0; "__CLASS"
0x1800b83a8  mov     rcx, rbx
0x1800b83ab  mov     rax, [rax+368h]
0x1800b83b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b83b7  cmp     eax, edi
0x1800b83b9  jnz     short loc_1800B841C
0x1800b83bb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b83c1  mov     edx, 0FFFFFFFEh
0x1800b83c6  mov     rcx, rax
0x1800b83c9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b83cf  lea     rax, WPP_GLOBAL_Control
0x1800b83d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b83dd  cmp     rcx, rax
0x1800b83e0  jz      short loc_1800B840A
0x1800b83e2  test    byte ptr [rcx+1Ch], 1
0x1800b83e6  jz      short loc_1800B840A
0x1800b83e8  cmp     byte ptr [rcx+19h], 2
0x1800b83ec  jb      short loc_1800B840A
0x1800b83ee  mov     edx, 80h
0x1800b83f3  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b83fa  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b8401  mov     rcx, [rcx+10h]
0x1800b8405  call    WPP_SF_s
0x1800b840a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b8411  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b8416  call    _CxxThrowException_0
0x1800b841c  xor     edx, edx
0x1800b841e  lea     r8d, [rdx+0Bh]
0x1800b8422  lea     rcx, [rsp+410h+var_3D8]
0x1800b8427  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800b842d  nop
0x1800b842e  mov     rax, [rbx]
0x1800b8431  mov     r9d, 0Bh
0x1800b8437  lea     r8, [rsp+410h+var_3D8]
0x1800b843c  lea     rdx, aSupportsput; "SupportsPut"
0x1800b8443  mov     rcx, rbx
0x1800b8446  mov     rax, [rax+368h]
0x1800b844d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8452  cmp     eax, edi
0x1800b8454  jnz     short loc_1800B84B7
0x1800b8456  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b845c  mov     edx, 0FFFFFFFEh
0x1800b8461  mov     rcx, rax
0x1800b8464  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b846a  lea     rax, WPP_GLOBAL_Control
0x1800b8471  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8478  cmp     rcx, rax
0x1800b847b  jz      short loc_1800B84A5
0x1800b847d  test    byte ptr [rcx+1Ch], 1
0x1800b8481  jz      short loc_1800B84A5
0x1800b8483  cmp     byte ptr [rcx+19h], 2
0x1800b8487  jb      short loc_1800B84A5
0x1800b8489  mov     edx, 81h
0x1800b848e  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b8495  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b849c  mov     rcx, [rcx+10h]
0x1800b84a0  call    WPP_SF_s
0x1800b84a5  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b84ac  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b84b1  call    _CxxThrowException_0
0x1800b84b7  mov     rax, [rbx]
0x1800b84ba  mov     r9d, 0Bh
0x1800b84c0  lea     r8, [rsp+410h+var_3D8]
0x1800b84c5  lea     rdx, aSupportsget; "SupportsGet"
0x1800b84cc  mov     rcx, rbx
0x1800b84cf  mov     rax, [rax+368h]
0x1800b84d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b84db  cmp     eax, edi
0x1800b84dd  jnz     short loc_1800B8540
0x1800b84df  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b84e5  mov     edx, 0FFFFFFFEh
0x1800b84ea  mov     rcx, rax
0x1800b84ed  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b84f3  lea     rax, WPP_GLOBAL_Control
0x1800b84fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8501  cmp     rcx, rax
0x1800b8504  jz      short loc_1800B852E
0x1800b8506  test    byte ptr [rcx+1Ch], 1
0x1800b850a  jz      short loc_1800B852E
0x1800b850c  cmp     byte ptr [rcx+19h], 2
0x1800b8510  jb      short loc_1800B852E
0x1800b8512  mov     edx, 82h
0x1800b8517  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b851e  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b8525  mov     rcx, [rcx+10h]
0x1800b8529  call    WPP_SF_s
0x1800b852e  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b8535  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b853a  call    _CxxThrowException_0
0x1800b8540  or      edx, 0FFFFFFFFh
0x1800b8543  lea     r8d, [rdx+0Ch]
0x1800b8547  lea     rcx, [rsp+410h+var_3B8]
0x1800b854c  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800b8552  nop
0x1800b8553  mov     rax, [rbx]
0x1800b8556  lea     rcx, [rsp+410h+var_3B8]
0x1800b855b  mov     [rsp+410h+var_3F0], rcx
0x1800b8560  xor     r9d, r9d
0x1800b8563  lea     r8, aKey; "key"
0x1800b856a  lea     rdx, aProvider_0; "Provider"
0x1800b8571  mov     rcx, rbx
0x1800b8574  mov     rax, [rax+378h]
0x1800b857b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8580  cmp     eax, edi
0x1800b8582  jnz     short loc_1800B85E5
0x1800b8584  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b858a  mov     edx, 0FFFFFFFEh
0x1800b858f  mov     rcx, rax
0x1800b8592  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b8598  lea     rax, WPP_GLOBAL_Control
0x1800b859f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b85a6  cmp     rcx, rax
0x1800b85a9  jz      short loc_1800B85D3
0x1800b85ab  test    byte ptr [rcx+1Ch], 1
0x1800b85af  jz      short loc_1800B85D3
0x1800b85b1  cmp     byte ptr [rcx+19h], 2
0x1800b85b5  jb      short loc_1800B85D3
0x1800b85b7  mov     edx, 83h
0x1800b85bc  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b85c3  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b85ca  mov     rcx, [rcx+10h]
0x1800b85ce  call    WPP_SF_s
0x1800b85d3  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b85da  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b85df  call    _CxxThrowException_0
0x1800b85e5  lea     rcx, [rsp+410h+var_3B8]
0x1800b85ea  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b85f0  nop
0x1800b85f1  lea     rcx, [rsp+410h+var_3D8]
0x1800b85f6  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b85fc  nop
0x1800b85fd  lea     rcx, [rsp+410h+var_398]
0x1800b8602  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b8608  nop
0x1800b8609  lea     rcx, [rbp+310h+var_370]; this
0x1800b860d  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800b8612  mov     rcx, [rbp+310h+var_10]
0x1800b8619  xor     rcx, rsp; StackCookie
0x1800b861c  call    __security_check_cookie
0x1800b8621  lea     r11, [rsp+410h+var_s0]
0x1800b8629  mov     rbx, [r11+18h]
0x1800b862d  mov     rdi, [r11+20h]
0x1800b8631  mov     rsp, r11
0x1800b8634  pop     rbp
0x1800b8635  retn
```
