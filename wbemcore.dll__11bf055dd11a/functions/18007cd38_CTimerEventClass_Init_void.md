# CTimerEventClass::Init(void)

- ea: `0x18007cd38`
- end: `0x18007d003`
- name: `?Init@CTimerEventClass@@QEAAXXZ`
- size: `715`
- prototype: `void __fastcall(CTimerEventClass *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`

## callees

- `0x18007cd38`
- `0x18007d388`
- `0x180085c70`
- `0x18008846c`
- `0x18008a658`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x18007ce07`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x18007ce07`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18007cea5`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18007cea5`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007ce99`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007ce99`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007cfc2`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007cfce`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007cfc2`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007cfce`
- `wbemcomn!GetMemLogObject` at `0x18007cd95`
- `wbemcomn!GetMemLogObject` at `0x18007ce33`
- `wbemcomn!GetMemLogObject` at `0x18007ced3`
- `wbemcomn!GetMemLogObject` at `0x18007cf5c`
- `wbemcomn!GetMemLogObject` at `0x18007cd95`
- `wbemcomn!GetMemLogObject` at `0x18007ce33`
- `wbemcomn!GetMemLogObject` at `0x18007ced3`
- `wbemcomn!GetMemLogObject` at `0x18007cf5c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007cda3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ce41`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007cee1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007cf6a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007cda3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ce41`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007cee1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007cf6a`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x18007cfd9`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x18007cfd9`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x18007cd86`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x18007cd86`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CTimerEventClass::Init(CTimerEventClass *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v7[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v8[40]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v9[864]; // [rsp+80h] [rbp-80h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v9);
  CEventClass::Init((CEventClass *)v9);
  if ( CWbemClass::CreateDerivedClass(this, (struct CWbemClass *)v9, 0, 0) == -2147217402 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        216,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8, 8, L"__TimerEvent");
  if ( (*(unsigned int (__fastcall **)(CTimerEventClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
         this,
         L"__CLASS",
         v8,
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
        217,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v7);
  CVar::SetAsNull((CVar *)v7);
  if ( (*(unsigned int (__fastcall **)(CTimerEventClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"TimerId",
         v7,
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
        218,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( (*(unsigned int (__fastcall **)(CTimerEventClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"NumFirings",
         v7,
         19) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        219,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v7);
  CVar::~CVar((CVar *)v8);
  CWbemClass::~CWbemClass((CWbemClass *)v9);
}

```

## disassembly

```asm
0x18007cd38  mov     [rsp-8+arg_8], rbx
0x18007cd3d  mov     [rsp-8+arg_10], rdi
0x18007cd42  push    rbp
0x18007cd43  lea     rbp, [rsp-2F0h]
0x18007cd4b  sub     rsp, 3F0h
0x18007cd52  mov     rax, cs:__security_cookie
0x18007cd59  xor     rax, rsp
0x18007cd5c  mov     [rbp+2F0h+var_10], rax
0x18007cd63  mov     rbx, rcx
0x18007cd66  lea     rcx, [rbp+2F0h+var_370]; this
0x18007cd6a  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x18007cd6f  nop
0x18007cd70  lea     rcx, [rbp+2F0h+var_370]; this
0x18007cd74  call    ?Init@CEventClass@@QEAAXXZ; CEventClass::Init(void)
0x18007cd79  xor     r9d, r9d
0x18007cd7c  xor     r8d, r8d
0x18007cd7f  lea     rdx, [rbp+2F0h+var_370]
0x18007cd83  mov     rcx, rbx
0x18007cd86  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x18007cd8c  mov     edi, 80041006h
0x18007cd91  cmp     eax, edi
0x18007cd93  jnz     short loc_18007CDF6
0x18007cd95  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007cd9b  mov     edx, 0FFFFFFFEh
0x18007cda0  mov     rcx, rax
0x18007cda3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007cda9  lea     rax, WPP_GLOBAL_Control
0x18007cdb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cdb7  cmp     rcx, rax
0x18007cdba  jz      short loc_18007CDE4
0x18007cdbc  test    byte ptr [rcx+1Ch], 1
0x18007cdc0  jz      short loc_18007CDE4
0x18007cdc2  cmp     byte ptr [rcx+19h], 2
0x18007cdc6  jb      short loc_18007CDE4
0x18007cdc8  mov     edx, 0D8h
0x18007cdcd  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007cdd4  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007cddb  mov     rcx, [rcx+10h]
0x18007cddf  call    WPP_SF_s
0x18007cde4  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007cdeb  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x18007cdf0  call    _CxxThrowException_0
0x18007cdf6  lea     r8, aTimerevent; "__TimerEvent"
0x18007cdfd  mov     edx, 8
0x18007ce02  lea     rcx, [rsp+3F0h+var_398]
0x18007ce07  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x18007ce0d  nop
0x18007ce0e  mov     rax, [rbx]
0x18007ce11  xor     r9d, r9d
0x18007ce14  lea     r8, [rsp+3F0h+var_398]
0x18007ce19  lea     rdx, aClass_0; "__CLASS"
0x18007ce20  mov     rcx, rbx
0x18007ce23  mov     rax, [rax+368h]
0x18007ce2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ce2f  cmp     eax, edi
0x18007ce31  jnz     short loc_18007CE94
0x18007ce33  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007ce39  mov     edx, 0FFFFFFFEh
0x18007ce3e  mov     rcx, rax
0x18007ce41  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007ce47  lea     rax, WPP_GLOBAL_Control
0x18007ce4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ce55  cmp     rcx, rax
0x18007ce58  jz      short loc_18007CE82
0x18007ce5a  test    byte ptr [rcx+1Ch], 1
0x18007ce5e  jz      short loc_18007CE82
0x18007ce60  cmp     byte ptr [rcx+19h], 2
0x18007ce64  jb      short loc_18007CE82
0x18007ce66  mov     edx, 0D9h
0x18007ce6b  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007ce72  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007ce79  mov     rcx, [rcx+10h]
0x18007ce7d  call    WPP_SF_s
0x18007ce82  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007ce89  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x18007ce8e  call    _CxxThrowException_0
0x18007ce94  lea     rcx, [rsp+3F0h+var_3B8]
0x18007ce99  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18007ce9f  nop
0x18007cea0  lea     rcx, [rsp+3F0h+var_3B8]
0x18007cea5  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x18007ceab  mov     rax, [rbx]
0x18007ceae  mov     r9d, 8
0x18007ceb4  lea     r8, [rsp+3F0h+var_3B8]
0x18007ceb9  lea     rdx, aTimerid; "TimerId"
0x18007cec0  mov     rcx, rbx
0x18007cec3  mov     rax, [rax+368h]
0x18007ceca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cecf  cmp     eax, edi
0x18007ced1  jnz     short loc_18007CF34
0x18007ced3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007ced9  mov     edx, 0FFFFFFFEh
0x18007cede  mov     rcx, rax
0x18007cee1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007cee7  lea     rax, WPP_GLOBAL_Control
0x18007ceee  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cef5  cmp     rcx, rax
0x18007cef8  jz      short loc_18007CF22
0x18007cefa  test    byte ptr [rcx+1Ch], 1
0x18007cefe  jz      short loc_18007CF22
0x18007cf00  cmp     byte ptr [rcx+19h], 2
0x18007cf04  jb      short loc_18007CF22
0x18007cf06  mov     edx, 0DAh
0x18007cf0b  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007cf12  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007cf19  mov     rcx, [rcx+10h]
0x18007cf1d  call    WPP_SF_s
0x18007cf22  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007cf29  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x18007cf2e  call    _CxxThrowException_0
0x18007cf34  mov     rax, [rbx]
0x18007cf37  mov     r9d, 13h
0x18007cf3d  lea     r8, [rsp+3F0h+var_3B8]
0x18007cf42  lea     rdx, aNumfirings; "NumFirings"
0x18007cf49  mov     rcx, rbx
0x18007cf4c  mov     rax, [rax+368h]
0x18007cf53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cf58  cmp     eax, edi
0x18007cf5a  jnz     short loc_18007CFBD
0x18007cf5c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007cf62  mov     edx, 0FFFFFFFEh
0x18007cf67  mov     rcx, rax
0x18007cf6a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007cf70  lea     rax, WPP_GLOBAL_Control
0x18007cf77  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cf7e  cmp     rcx, rax
0x18007cf81  jz      short loc_18007CFAB
0x18007cf83  test    byte ptr [rcx+1Ch], 1
0x18007cf87  jz      short loc_18007CFAB
0x18007cf89  cmp     byte ptr [rcx+19h], 2
0x18007cf8d  jb      short loc_18007CFAB
0x18007cf8f  mov     edx, 0DBh
0x18007cf94  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007cf9b  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007cfa2  mov     rcx, [rcx+10h]
0x18007cfa6  call    WPP_SF_s
0x18007cfab  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007cfb2  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x18007cfb7  call    _CxxThrowException_0
0x18007cfbd  lea     rcx, [rsp+3F0h+var_3B8]
0x18007cfc2  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18007cfc8  nop
0x18007cfc9  lea     rcx, [rsp+3F0h+var_398]
0x18007cfce  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18007cfd4  nop
0x18007cfd5  lea     rcx, [rbp+2F0h+var_370]
0x18007cfd9  call    cs:__imp_??1CWbemClass@@UEAA@XZ; CWbemClass::~CWbemClass(void)
0x18007cfdf  mov     rcx, [rbp+2F0h+var_10]
0x18007cfe6  xor     rcx, rsp; StackCookie
0x18007cfe9  call    __security_check_cookie
0x18007cfee  lea     r11, [rsp+3F0h+var_s0]
0x18007cff6  mov     rbx, [r11+18h]
0x18007cffa  mov     rdi, [r11+20h]
0x18007cffe  mov     rsp, r11
0x18007d001  pop     rbp
0x18007d002  retn
```
