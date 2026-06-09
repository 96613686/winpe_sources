# CEventConsumerProviderRegistrationClass::Init(void)

- ea: `0x1800684dc`
- end: `0x1800687cf`
- name: `?Init@CEventConsumerProviderRegistrationClass@@QEAAXXZ`
- size: `755`
- prototype: `void __fastcall(CEventConsumerProviderRegistrationClass *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`

## callees

- `0x1800684dc`
- `0x180069744`
- `0x180085c70`
- `0x18008846c`
- `0x18008a658`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800686e4`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800686e4`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800685ab`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800685ab`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x180068649`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x180068649`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18006863d`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18006863d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180068782`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006878e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006879a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180068782`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006878e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006879a`
- `wbemcomn!GetMemLogObject` at `0x180068539`
- `wbemcomn!GetMemLogObject` at `0x1800685d7`
- `wbemcomn!GetMemLogObject` at `0x180068677`
- `wbemcomn!GetMemLogObject` at `0x18006871c`
- `wbemcomn!GetMemLogObject` at `0x180068539`
- `wbemcomn!GetMemLogObject` at `0x1800685d7`
- `wbemcomn!GetMemLogObject` at `0x180068677`
- `wbemcomn!GetMemLogObject` at `0x18006871c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180068547`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800685e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180068685`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006872a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180068547`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800685e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180068685`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006872a`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x1800687a5`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x1800687a5`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x18006852a`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x18006852a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CEventConsumerProviderRegistrationClass::Init(CEventConsumerProviderRegistrationClass *this)
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
        139,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, 8, L"__EventConsumerProviderRegistration");
  if ( (*(unsigned int (__fastcall **)(CEventConsumerProviderRegistrationClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
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
        140,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v7);
  CVar::SetAsNull((CVar *)v7);
  if ( (*(unsigned int (__fastcall **)(CEventConsumerProviderRegistrationClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"ConsumerClassNames",
         v7,
         8200) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        141,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CEventConsumerProviderRegistrationClass *, const wchar_t *, const wchar_t *, _QWORD, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"Provider",
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
        142,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v8);
  CVar::~CVar((CVar *)v7);
  CVar::~CVar((CVar *)v9);
  CWbemClass::~CWbemClass((CWbemClass *)v10);
}

```

## disassembly

```asm
0x1800684dc  mov     [rsp-8+arg_8], rbx
0x1800684e1  mov     [rsp-8+arg_10], rdi
0x1800684e6  push    rbp
0x1800684e7  lea     rbp, [rsp-310h]
0x1800684ef  sub     rsp, 410h
0x1800684f6  mov     rax, cs:__security_cookie
0x1800684fd  xor     rax, rsp
0x180068500  mov     [rbp+310h+var_10], rax
0x180068507  mov     rbx, rcx
0x18006850a  lea     rcx, [rbp+310h+var_370]; this
0x18006850e  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x180068513  nop
0x180068514  lea     rcx, [rbp+310h+var_370]; this
0x180068518  call    ?Init@CProviderRegistrationClass@@QEAAXXZ; CProviderRegistrationClass::Init(void)
0x18006851d  xor     r9d, r9d
0x180068520  xor     r8d, r8d
0x180068523  lea     rdx, [rbp+310h+var_370]
0x180068527  mov     rcx, rbx
0x18006852a  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x180068530  mov     edi, 80041006h
0x180068535  cmp     eax, edi
0x180068537  jnz     short loc_18006859A
0x180068539  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006853f  mov     edx, 0FFFFFFFEh
0x180068544  mov     rcx, rax
0x180068547  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006854d  lea     rax, WPP_GLOBAL_Control
0x180068554  mov     rcx, cs:WPP_GLOBAL_Control
0x18006855b  cmp     rcx, rax
0x18006855e  jz      short loc_180068588
0x180068560  test    byte ptr [rcx+1Ch], 1
0x180068564  jz      short loc_180068588
0x180068566  cmp     byte ptr [rcx+19h], 2
0x18006856a  jb      short loc_180068588
0x18006856c  mov     edx, 8Bh
0x180068571  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180068578  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18006857f  mov     rcx, [rcx+10h]
0x180068583  call    WPP_SF_s
0x180068588  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18006858f  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x180068594  call    _CxxThrowException_0
0x18006859a  lea     r8, aEventconsumerp_0; "__EventConsumerProviderRegistration"
0x1800685a1  mov     edx, 8
0x1800685a6  lea     rcx, [rsp+410h+var_398]
0x1800685ab  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800685b1  nop
0x1800685b2  mov     rax, [rbx]
0x1800685b5  xor     r9d, r9d
0x1800685b8  lea     r8, [rsp+410h+var_398]
0x1800685bd  lea     rdx, aClass_0; "__CLASS"
0x1800685c4  mov     rcx, rbx
0x1800685c7  mov     rax, [rax+368h]
0x1800685ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800685d3  cmp     eax, edi
0x1800685d5  jnz     short loc_180068638
0x1800685d7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800685dd  mov     edx, 0FFFFFFFEh
0x1800685e2  mov     rcx, rax
0x1800685e5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800685eb  lea     rax, WPP_GLOBAL_Control
0x1800685f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800685f9  cmp     rcx, rax
0x1800685fc  jz      short loc_180068626
0x1800685fe  test    byte ptr [rcx+1Ch], 1
0x180068602  jz      short loc_180068626
0x180068604  cmp     byte ptr [rcx+19h], 2
0x180068608  jb      short loc_180068626
0x18006860a  mov     edx, 8Ch
0x18006860f  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180068616  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18006861d  mov     rcx, [rcx+10h]
0x180068621  call    WPP_SF_s
0x180068626  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18006862d  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x180068632  call    _CxxThrowException_0
0x180068638  lea     rcx, [rsp+410h+var_3D8]
0x18006863d  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180068643  nop
0x180068644  lea     rcx, [rsp+410h+var_3D8]
0x180068649  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x18006864f  mov     rax, [rbx]
0x180068652  mov     r9d, 2008h
0x180068658  lea     r8, [rsp+410h+var_3D8]
0x18006865d  lea     rdx, aConsumerclassn; "ConsumerClassNames"
0x180068664  mov     rcx, rbx
0x180068667  mov     rax, [rax+368h]
0x18006866e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068673  cmp     eax, edi
0x180068675  jnz     short loc_1800686D8
0x180068677  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006867d  mov     edx, 0FFFFFFFEh
0x180068682  mov     rcx, rax
0x180068685  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006868b  lea     rax, WPP_GLOBAL_Control
0x180068692  mov     rcx, cs:WPP_GLOBAL_Control
0x180068699  cmp     rcx, rax
0x18006869c  jz      short loc_1800686C6
0x18006869e  test    byte ptr [rcx+1Ch], 1
0x1800686a2  jz      short loc_1800686C6
0x1800686a4  cmp     byte ptr [rcx+19h], 2
0x1800686a8  jb      short loc_1800686C6
0x1800686aa  mov     edx, 8Dh
0x1800686af  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800686b6  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800686bd  mov     rcx, [rcx+10h]
0x1800686c1  call    WPP_SF_s
0x1800686c6  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800686cd  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800686d2  call    _CxxThrowException_0
0x1800686d8  or      edx, 0FFFFFFFFh
0x1800686db  lea     r8d, [rdx+0Ch]
0x1800686df  lea     rcx, [rsp+410h+var_3B8]
0x1800686e4  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800686ea  nop
0x1800686eb  mov     rax, [rbx]
0x1800686ee  lea     rcx, [rsp+410h+var_3B8]
0x1800686f3  mov     [rsp+410h+var_3F0], rcx
0x1800686f8  xor     r9d, r9d
0x1800686fb  lea     r8, aKey; "key"
0x180068702  lea     rdx, aProvider_0; "Provider"
0x180068709  mov     rcx, rbx
0x18006870c  mov     rax, [rax+378h]
0x180068713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068718  cmp     eax, edi
0x18006871a  jnz     short loc_18006877D
0x18006871c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180068722  mov     edx, 0FFFFFFFEh
0x180068727  mov     rcx, rax
0x18006872a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180068730  lea     rax, WPP_GLOBAL_Control
0x180068737  mov     rcx, cs:WPP_GLOBAL_Control
0x18006873e  cmp     rcx, rax
0x180068741  jz      short loc_18006876B
0x180068743  test    byte ptr [rcx+1Ch], 1
0x180068747  jz      short loc_18006876B
0x180068749  cmp     byte ptr [rcx+19h], 2
0x18006874d  jb      short loc_18006876B
0x18006874f  mov     edx, 8Eh
0x180068754  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18006875b  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x180068762  mov     rcx, [rcx+10h]
0x180068766  call    WPP_SF_s
0x18006876b  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180068772  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x180068777  call    _CxxThrowException_0
0x18006877d  lea     rcx, [rsp+410h+var_3B8]
0x180068782  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180068788  nop
0x180068789  lea     rcx, [rsp+410h+var_3D8]
0x18006878e  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180068794  nop
0x180068795  lea     rcx, [rsp+410h+var_398]
0x18006879a  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800687a0  nop
0x1800687a1  lea     rcx, [rbp+310h+var_370]
0x1800687a5  call    cs:__imp_??1CWbemClass@@UEAA@XZ; CWbemClass::~CWbemClass(void)
0x1800687ab  mov     rcx, [rbp+310h+var_10]
0x1800687b2  xor     rcx, rsp; StackCookie
0x1800687b5  call    __security_check_cookie
0x1800687ba  lea     r11, [rsp+410h+var_s0]
0x1800687c2  mov     rbx, [r11+18h]
0x1800687c6  mov     rdi, [r11+20h]
0x1800687ca  mov     rsp, r11
0x1800687cd  pop     rbp
0x1800687ce  retn
```
