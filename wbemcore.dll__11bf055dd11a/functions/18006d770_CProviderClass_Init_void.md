# CProviderClass::Init(void)

- ea: `0x18006d770`
- end: `0x18006dae9`
- name: `?Init@CProviderClass@@QEAAXXZ`
- size: `889`
- prototype: `void __fastcall(CProviderClass *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`
- `0x18006daf0`

## callees

- `0x18006abcc`
- `0x18006d770`
- `0x180085c70`
- `0x18008846c`
- `0x18008a658`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x18006d978`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x18006d978`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x18006d83f`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x18006d83f`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18006d8dd`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18006d8dd`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18006d8d1`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18006d8d1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006da9c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006daa8`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006dab4`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006da9c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006daa8`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006dab4`
- `wbemcomn!GetMemLogObject` at `0x18006d7cd`
- `wbemcomn!GetMemLogObject` at `0x18006d86b`
- `wbemcomn!GetMemLogObject` at `0x18006d90b`
- `wbemcomn!GetMemLogObject` at `0x18006d9b0`
- `wbemcomn!GetMemLogObject` at `0x18006da36`
- `wbemcomn!GetMemLogObject` at `0x18006d7cd`
- `wbemcomn!GetMemLogObject` at `0x18006d86b`
- `wbemcomn!GetMemLogObject` at `0x18006d90b`
- `wbemcomn!GetMemLogObject` at `0x18006d9b0`
- `wbemcomn!GetMemLogObject` at `0x18006da36`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006d7db`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006d879`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006d919`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006d9be`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006da44`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006d7db`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006d879`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006d919`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006d9be`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006da44`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x18006dabf`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x18006dabf`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x18006d7be`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x18006d7be`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CProviderClass::Init(CProviderClass *this)
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
  CSystemClass::Init((CSystemClass *)v11);
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
        35,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v10, 8, L"__Provider");
  if ( (*(unsigned int (__fastcall **)(CProviderClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
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
        36,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9);
  CVar::SetAsNull((CVar *)v9);
  if ( (*(unsigned int (__fastcall **)(CProviderClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"Name",
         v9,
         8) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CProviderClass *, const wchar_t *, const wchar_t *, _QWORD, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"Name",
         L"key",
         0,
         v8) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( (*(unsigned int (__fastcall **)(CProviderClass *, const wchar_t *, _BYTE *, _QWORD))(*(_QWORD *)this + 984LL))(
         this,
         L"abstract",
         v8,
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
        39,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v8);
  CVar::~CVar((CVar *)v9);
  CVar::~CVar((CVar *)v10);
  CWbemClass::~CWbemClass((CWbemClass *)v11);
}

```

## disassembly

```asm
0x18006d770  mov     [rsp-8+arg_8], rbx
0x18006d775  mov     [rsp-8+arg_10], rdi
0x18006d77a  push    rbp
0x18006d77b  lea     rbp, [rsp-310h]
0x18006d783  sub     rsp, 410h
0x18006d78a  mov     rax, cs:__security_cookie
0x18006d791  xor     rax, rsp
0x18006d794  mov     [rbp+310h+var_10], rax
0x18006d79b  mov     rbx, rcx
0x18006d79e  lea     rcx, [rbp+310h+var_370]; this
0x18006d7a2  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x18006d7a7  nop
0x18006d7a8  lea     rcx, [rbp+310h+var_370]; this
0x18006d7ac  call    ?Init@CSystemClass@@QEAAXXZ; CSystemClass::Init(void)
0x18006d7b1  xor     r9d, r9d
0x18006d7b4  xor     r8d, r8d
0x18006d7b7  lea     rdx, [rbp+310h+var_370]
0x18006d7bb  mov     rcx, rbx
0x18006d7be  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x18006d7c4  mov     edi, 80041006h
0x18006d7c9  cmp     eax, edi
0x18006d7cb  jnz     short loc_18006D82E
0x18006d7cd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006d7d3  mov     edx, 0FFFFFFFEh
0x18006d7d8  mov     rcx, rax
0x18006d7db  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006d7e1  lea     rax, WPP_GLOBAL_Control
0x18006d7e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d7ef  cmp     rcx, rax
0x18006d7f2  jz      short loc_18006D81C
0x18006d7f4  test    byte ptr [rcx+1Ch], 1
0x18006d7f8  jz      short loc_18006D81C
0x18006d7fa  cmp     byte ptr [rcx+19h], 2
0x18006d7fe  jb      short loc_18006D81C
0x18006d800  mov     edx, 23h ; '#'
0x18006d805  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18006d80c  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18006d813  mov     rcx, [rcx+10h]
0x18006d817  call    WPP_SF_s
0x18006d81c  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18006d823  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x18006d828  call    _CxxThrowException_0
0x18006d82e  lea     r8, aProvider_1; "__Provider"
0x18006d835  mov     edx, 8
0x18006d83a  lea     rcx, [rsp+410h+var_398]
0x18006d83f  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x18006d845  nop
0x18006d846  mov     rax, [rbx]
0x18006d849  xor     r9d, r9d
0x18006d84c  lea     r8, [rsp+410h+var_398]
0x18006d851  lea     rdx, aClass_0; "__CLASS"
0x18006d858  mov     rcx, rbx
0x18006d85b  mov     rax, [rax+368h]
0x18006d862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d867  cmp     eax, edi
0x18006d869  jnz     short loc_18006D8CC
0x18006d86b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006d871  mov     edx, 0FFFFFFFEh
0x18006d876  mov     rcx, rax
0x18006d879  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006d87f  lea     rax, WPP_GLOBAL_Control
0x18006d886  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d88d  cmp     rcx, rax
0x18006d890  jz      short loc_18006D8BA
0x18006d892  test    byte ptr [rcx+1Ch], 1
0x18006d896  jz      short loc_18006D8BA
0x18006d898  cmp     byte ptr [rcx+19h], 2
0x18006d89c  jb      short loc_18006D8BA
0x18006d89e  mov     edx, 24h ; '$'
0x18006d8a3  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18006d8aa  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18006d8b1  mov     rcx, [rcx+10h]
0x18006d8b5  call    WPP_SF_s
0x18006d8ba  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18006d8c1  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x18006d8c6  call    _CxxThrowException_0
0x18006d8cc  lea     rcx, [rsp+410h+var_3B8]
0x18006d8d1  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18006d8d7  nop
0x18006d8d8  lea     rcx, [rsp+410h+var_3B8]
0x18006d8dd  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x18006d8e3  mov     rax, [rbx]
0x18006d8e6  mov     r9d, 8
0x18006d8ec  lea     r8, [rsp+410h+var_3B8]
0x18006d8f1  lea     rdx, aName; "Name"
0x18006d8f8  mov     rcx, rbx
0x18006d8fb  mov     rax, [rax+368h]
0x18006d902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d907  cmp     eax, edi
0x18006d909  jnz     short loc_18006D96C
0x18006d90b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006d911  mov     edx, 0FFFFFFFEh
0x18006d916  mov     rcx, rax
0x18006d919  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006d91f  lea     rax, WPP_GLOBAL_Control
0x18006d926  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d92d  cmp     rcx, rax
0x18006d930  jz      short loc_18006D95A
0x18006d932  test    byte ptr [rcx+1Ch], 1
0x18006d936  jz      short loc_18006D95A
0x18006d938  cmp     byte ptr [rcx+19h], 2
0x18006d93c  jb      short loc_18006D95A
0x18006d93e  mov     edx, 25h ; '%'
0x18006d943  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18006d94a  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18006d951  mov     rcx, [rcx+10h]
0x18006d955  call    WPP_SF_s
0x18006d95a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18006d961  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x18006d966  call    _CxxThrowException_0
0x18006d96c  or      edx, 0FFFFFFFFh
0x18006d96f  lea     r8d, [rdx+0Ch]
0x18006d973  lea     rcx, [rsp+410h+var_3D8]
0x18006d978  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x18006d97e  nop
0x18006d97f  mov     rax, [rbx]
0x18006d982  lea     rcx, [rsp+410h+var_3D8]
0x18006d987  mov     [rsp+410h+var_3F0], rcx
0x18006d98c  xor     r9d, r9d
0x18006d98f  lea     r8, aKey; "key"
0x18006d996  lea     rdx, aName; "Name"
0x18006d99d  mov     rcx, rbx
0x18006d9a0  mov     rax, [rax+378h]
0x18006d9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d9ac  cmp     eax, edi
0x18006d9ae  jnz     short loc_18006DA11
0x18006d9b0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006d9b6  mov     edx, 0FFFFFFFEh
0x18006d9bb  mov     rcx, rax
0x18006d9be  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006d9c4  lea     rax, WPP_GLOBAL_Control
0x18006d9cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d9d2  cmp     rcx, rax
0x18006d9d5  jz      short loc_18006D9FF
0x18006d9d7  test    byte ptr [rcx+1Ch], 1
0x18006d9db  jz      short loc_18006D9FF
0x18006d9dd  cmp     byte ptr [rcx+19h], 2
0x18006d9e1  jb      short loc_18006D9FF
0x18006d9e3  mov     edx, 26h ; '&'
0x18006d9e8  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18006d9ef  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18006d9f6  mov     rcx, [rcx+10h]
0x18006d9fa  call    WPP_SF_s
0x18006d9ff  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18006da06  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x18006da0b  call    _CxxThrowException_0
0x18006da11  mov     rax, [rbx]
0x18006da14  xor     r9d, r9d
0x18006da17  lea     r8, [rsp+410h+var_3D8]
0x18006da1c  lea     rdx, aAbstract_1; "abstract"
0x18006da23  mov     rcx, rbx
0x18006da26  mov     rax, [rax+3D8h]
0x18006da2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006da32  cmp     eax, edi
0x18006da34  jnz     short loc_18006DA97
0x18006da36  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006da3c  mov     edx, 0FFFFFFFEh
0x18006da41  mov     rcx, rax
0x18006da44  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006da4a  lea     rax, WPP_GLOBAL_Control
0x18006da51  mov     rcx, cs:WPP_GLOBAL_Control
0x18006da58  cmp     rcx, rax
0x18006da5b  jz      short loc_18006DA85
0x18006da5d  test    byte ptr [rcx+1Ch], 1
0x18006da61  jz      short loc_18006DA85
0x18006da63  cmp     byte ptr [rcx+19h], 2
0x18006da67  jb      short loc_18006DA85
0x18006da69  mov     edx, 27h ; '''
0x18006da6e  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18006da75  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18006da7c  mov     rcx, [rcx+10h]
0x18006da80  call    WPP_SF_s
0x18006da85  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18006da8c  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x18006da91  call    _CxxThrowException_0
0x18006da97  lea     rcx, [rsp+410h+var_3D8]
0x18006da9c  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18006daa2  nop
0x18006daa3  lea     rcx, [rsp+410h+var_3B8]
0x18006daa8  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18006daae  nop
0x18006daaf  lea     rcx, [rsp+410h+var_398]
0x18006dab4  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18006daba  nop
0x18006dabb  lea     rcx, [rbp+310h+var_370]
0x18006dabf  call    cs:__imp_??1CWbemClass@@UEAA@XZ; CWbemClass::~CWbemClass(void)
0x18006dac5  mov     rcx, [rbp+310h+var_10]
0x18006dacc  xor     rcx, rsp; StackCookie
0x18006dacf  call    __security_check_cookie
0x18006dad4  lea     r11, [rsp+410h+var_s0]
0x18006dadc  mov     rbx, [r11+18h]
0x18006dae0  mov     rdi, [r11+20h]
0x18006dae4  mov     rsp, r11
0x18006dae7  pop     rbp
0x18006dae8  retn
```
