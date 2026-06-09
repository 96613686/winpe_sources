# CEventProviderRegistrationClass::Init(void)

- ea: `0x1800b6844`
- end: `0x1800b6b36`
- name: `?Init@CEventProviderRegistrationClass@@QEAAXXZ`
- size: `754`
- prototype: `void __fastcall(CEventProviderRegistrationClass *__hidden this)`
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
- `0x1800b6844`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b69ac`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b69ac`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b6913`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b6913`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b6a56`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b6a56`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b6a4a`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b6a4a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b6aea`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b6af6`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b6b02`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b6aea`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b6af6`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b6b02`
- `wbemcomn!GetMemLogObject` at `0x1800b68a1`
- `wbemcomn!GetMemLogObject` at `0x1800b693f`
- `wbemcomn!GetMemLogObject` at `0x1800b69e4`
- `wbemcomn!GetMemLogObject` at `0x1800b6a84`
- `wbemcomn!GetMemLogObject` at `0x1800b68a1`
- `wbemcomn!GetMemLogObject` at `0x1800b693f`
- `wbemcomn!GetMemLogObject` at `0x1800b69e4`
- `wbemcomn!GetMemLogObject` at `0x1800b6a84`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b68af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b694d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b69f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b6a92`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b68af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b694d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b69f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b6a92`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b6892`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b6892`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CEventProviderRegistrationClass::Init(CEventProviderRegistrationClass *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v7[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v8[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v9[40]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v10[864]; // [rsp+A0h] [rbp-60h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v10);
  CProviderRegistrationClass::Init((CProviderRegistrationClass *)v10);
  if ( CWbemClass::CreateDerivedClass(this, (struct CWbemClass *)v10, 0, 0) == -2147217402 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        135,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, 8, L"__EventProviderRegistration");
  if ( (*(unsigned int (__fastcall **)(CEventProviderRegistrationClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
         this,
         L"__CLASS",
         v9,
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
        136,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CEventProviderRegistrationClass *, const wchar_t *, const wchar_t *, _QWORD, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"Provider",
         L"key",
         0,
         v8) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        137,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v7);
  CVar::SetAsNull((CVar *)v7);
  if ( (*(unsigned int (__fastcall **)(CEventProviderRegistrationClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"EventQueryList",
         v7,
         8200) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        138,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v7);
  CVar::~CVar((CVar *)v8);
  CVar::~CVar((CVar *)v9);
  CSystemEventClass::~CSystemEventClass((CSystemEventClass *)v10);
}

```

## disassembly

```asm
0x1800b6844  mov     [rsp-8+arg_8], rbx
0x1800b6849  mov     [rsp-8+arg_10], rdi
0x1800b684e  push    rbp
0x1800b684f  lea     rbp, [rsp-310h]
0x1800b6857  sub     rsp, 410h
0x1800b685e  mov     rax, cs:__security_cookie
0x1800b6865  xor     rax, rsp
0x1800b6868  mov     [rbp+310h+var_10], rax
0x1800b686f  mov     rbx, rcx
0x1800b6872  lea     rcx, [rbp+310h+var_370]; this
0x1800b6876  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800b687b  nop
0x1800b687c  lea     rcx, [rbp+310h+var_370]; this
0x1800b6880  call    ?Init@CProviderRegistrationClass@@QEAAXXZ; CProviderRegistrationClass::Init(void)
0x1800b6885  xor     r9d, r9d
0x1800b6888  xor     r8d, r8d
0x1800b688b  lea     rdx, [rbp+310h+var_370]
0x1800b688f  mov     rcx, rbx
0x1800b6892  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800b6898  mov     edi, 80041006h
0x1800b689d  cmp     eax, edi
0x1800b689f  jnz     short loc_1800B6902
0x1800b68a1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b68a7  mov     edx, 0FFFFFFFEh
0x1800b68ac  mov     rcx, rax
0x1800b68af  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b68b5  lea     rax, WPP_GLOBAL_Control
0x1800b68bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b68c3  cmp     rcx, rax
0x1800b68c6  jz      short loc_1800B68F0
0x1800b68c8  test    byte ptr [rcx+1Ch], 1
0x1800b68cc  jz      short loc_1800B68F0
0x1800b68ce  cmp     byte ptr [rcx+19h], 2
0x1800b68d2  jb      short loc_1800B68F0
0x1800b68d4  mov     edx, 87h
0x1800b68d9  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b68e0  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b68e7  mov     rcx, [rcx+10h]
0x1800b68eb  call    WPP_SF_s
0x1800b68f0  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b68f7  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b68fc  call    _CxxThrowException_0
0x1800b6902  lea     r8, aEventproviderr; "__EventProviderRegistration"
0x1800b6909  mov     edx, 8
0x1800b690e  lea     rcx, [rsp+410h+var_398]
0x1800b6913  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b6919  nop
0x1800b691a  mov     rax, [rbx]
0x1800b691d  xor     r9d, r9d
0x1800b6920  lea     r8, [rsp+410h+var_398]
0x1800b6925  lea     rdx, aClass_0; "__CLASS"
0x1800b692c  mov     rcx, rbx
0x1800b692f  mov     rax, [rax+368h]
0x1800b6936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b693b  cmp     eax, edi
0x1800b693d  jnz     short loc_1800B69A0
0x1800b693f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b6945  mov     edx, 0FFFFFFFEh
0x1800b694a  mov     rcx, rax
0x1800b694d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b6953  lea     rax, WPP_GLOBAL_Control
0x1800b695a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6961  cmp     rcx, rax
0x1800b6964  jz      short loc_1800B698E
0x1800b6966  test    byte ptr [rcx+1Ch], 1
0x1800b696a  jz      short loc_1800B698E
0x1800b696c  cmp     byte ptr [rcx+19h], 2
0x1800b6970  jb      short loc_1800B698E
0x1800b6972  mov     edx, 88h
0x1800b6977  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b697e  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b6985  mov     rcx, [rcx+10h]
0x1800b6989  call    WPP_SF_s
0x1800b698e  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b6995  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b699a  call    _CxxThrowException_0
0x1800b69a0  or      edx, 0FFFFFFFFh
0x1800b69a3  lea     r8d, [rdx+0Ch]
0x1800b69a7  lea     rcx, [rsp+410h+var_3B8]
0x1800b69ac  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800b69b2  nop
0x1800b69b3  mov     rax, [rbx]
0x1800b69b6  lea     rcx, [rsp+410h+var_3B8]
0x1800b69bb  mov     [rsp+410h+var_3F0], rcx
0x1800b69c0  xor     r9d, r9d
0x1800b69c3  lea     r8, aKey; "key"
0x1800b69ca  lea     rdx, aProvider_0; "Provider"
0x1800b69d1  mov     rcx, rbx
0x1800b69d4  mov     rax, [rax+378h]
0x1800b69db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b69e0  cmp     eax, edi
0x1800b69e2  jnz     short loc_1800B6A45
0x1800b69e4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b69ea  mov     edx, 0FFFFFFFEh
0x1800b69ef  mov     rcx, rax
0x1800b69f2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b69f8  lea     rax, WPP_GLOBAL_Control
0x1800b69ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6a06  cmp     rcx, rax
0x1800b6a09  jz      short loc_1800B6A33
0x1800b6a0b  test    byte ptr [rcx+1Ch], 1
0x1800b6a0f  jz      short loc_1800B6A33
0x1800b6a11  cmp     byte ptr [rcx+19h], 2
0x1800b6a15  jb      short loc_1800B6A33
0x1800b6a17  mov     edx, 89h
0x1800b6a1c  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b6a23  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b6a2a  mov     rcx, [rcx+10h]
0x1800b6a2e  call    WPP_SF_s
0x1800b6a33  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b6a3a  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b6a3f  call    _CxxThrowException_0
0x1800b6a45  lea     rcx, [rsp+410h+var_3D8]
0x1800b6a4a  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800b6a50  nop
0x1800b6a51  lea     rcx, [rsp+410h+var_3D8]
0x1800b6a56  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800b6a5c  mov     rax, [rbx]
0x1800b6a5f  mov     r9d, 2008h
0x1800b6a65  lea     r8, [rsp+410h+var_3D8]
0x1800b6a6a  lea     rdx, aEventquerylist; "EventQueryList"
0x1800b6a71  mov     rcx, rbx
0x1800b6a74  mov     rax, [rax+368h]
0x1800b6a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6a80  cmp     eax, edi
0x1800b6a82  jnz     short loc_1800B6AE5
0x1800b6a84  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b6a8a  mov     edx, 0FFFFFFFEh
0x1800b6a8f  mov     rcx, rax
0x1800b6a92  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b6a98  lea     rax, WPP_GLOBAL_Control
0x1800b6a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6aa6  cmp     rcx, rax
0x1800b6aa9  jz      short loc_1800B6AD3
0x1800b6aab  test    byte ptr [rcx+1Ch], 1
0x1800b6aaf  jz      short loc_1800B6AD3
0x1800b6ab1  cmp     byte ptr [rcx+19h], 2
0x1800b6ab5  jb      short loc_1800B6AD3
0x1800b6ab7  mov     edx, 8Ah
0x1800b6abc  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b6ac3  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b6aca  mov     rcx, [rcx+10h]
0x1800b6ace  call    WPP_SF_s
0x1800b6ad3  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b6ada  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b6adf  call    _CxxThrowException_0
0x1800b6ae5  lea     rcx, [rsp+410h+var_3D8]
0x1800b6aea  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b6af0  nop
0x1800b6af1  lea     rcx, [rsp+410h+var_3B8]
0x1800b6af6  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b6afc  nop
0x1800b6afd  lea     rcx, [rsp+410h+var_398]
0x1800b6b02  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b6b08  nop
0x1800b6b09  lea     rcx, [rbp+310h+var_370]; this
0x1800b6b0d  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800b6b12  mov     rcx, [rbp+310h+var_10]
0x1800b6b19  xor     rcx, rsp; StackCookie
0x1800b6b1c  call    __security_check_cookie
0x1800b6b21  lea     r11, [rsp+410h+var_s0]
0x1800b6b29  mov     rbx, [r11+18h]
0x1800b6b2d  mov     rdi, [r11+20h]
0x1800b6b31  mov     rsp, r11
0x1800b6b34  pop     rbp
0x1800b6b35  retn
```
