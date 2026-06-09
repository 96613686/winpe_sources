# CEventDroppedEventClass::Init(void)

- ea: `0x1800b5b90`
- end: `0x1800b5fc9`
- name: `?Init@CEventDroppedEventClass@@QEAAXXZ`
- size: `1081`
- prototype: `void __fastcall(CEventDroppedEventClass *__hidden this)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`
- `0x1800b4eb0`
- `0x1800b8c60`
- `0x1800b8f30`

## callees

- `0x18007c6c0`
- `0x180085c70`
- `0x180086358`
- `0x18008846c`
- `0x18008a658`
- `0x1800b5b90`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b5c5e`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b5e24`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b5ed1`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b5c5e`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b5e24`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b5ed1`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b5cfb`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b5cfb`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b5cef`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b5cef`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b5f72`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b5f7e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b5f8a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b5f95`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b5f72`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b5f7e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b5f8a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b5f95`
- `wbemcomn!GetMemLogObject` at `0x1800b5bed`
- `wbemcomn!GetMemLogObject` at `0x1800b5c89`
- `wbemcomn!GetMemLogObject` at `0x1800b5d29`
- `wbemcomn!GetMemLogObject` at `0x1800b5db2`
- `wbemcomn!GetMemLogObject` at `0x1800b5e5f`
- `wbemcomn!GetMemLogObject` at `0x1800b5f0c`
- `wbemcomn!GetMemLogObject` at `0x1800b5bed`
- `wbemcomn!GetMemLogObject` at `0x1800b5c89`
- `wbemcomn!GetMemLogObject` at `0x1800b5d29`
- `wbemcomn!GetMemLogObject` at `0x1800b5db2`
- `wbemcomn!GetMemLogObject` at `0x1800b5e5f`
- `wbemcomn!GetMemLogObject` at `0x1800b5f0c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5bfb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5c97`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5d37`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5dc0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5e6d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5f1a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5bfb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5c97`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5d37`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5dc0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5e6d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5f1a`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b5bde`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b5bde`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CEventDroppedEventClass::Init(CEventDroppedEventClass *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  CMemoryLog *v6; // rax
  CMemoryLog *v7; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v10[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v11[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v12[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v13[864]; // [rsp+C0h] [rbp-40h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v13);
  CSystemEventClass::Init((CSystemEventClass *)v13);
  if ( CWbemClass::CreateDerivedClass(this, (struct CWbemClass *)v13, 0, 0) == -2147217402 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        226,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v12, 8, L"__EventDroppedEvent");
  if ( (*(unsigned int (__fastcall **)(CEventDroppedEventClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
         this,
         L"__CLASS",
         v12,
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
        227,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9);
  CVar::SetAsNull((CVar *)v9);
  if ( (*(unsigned int (__fastcall **)(CEventDroppedEventClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"Event",
         v9,
         13) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        228,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( (*(unsigned int (__fastcall **)(CEventDroppedEventClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"IntendedConsumer",
         v9,
         102) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        229,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v11, 8, L"object:__Event");
  if ( (*(unsigned int (__fastcall **)(CEventDroppedEventClass *, const wchar_t *, const wchar_t *, __int64, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"Event",
         L"CIMTYPE",
         3,
         v11) == -2147217402 )
  {
    v6 = GetMemLogObject();
    CMemoryLog::Write(v6, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        230,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v10, 8, L"ref:__EventConsumer");
  if ( (*(unsigned int (__fastcall **)(CEventDroppedEventClass *, const wchar_t *, const wchar_t *, __int64, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"IntendedConsumer",
         L"CIMTYPE",
         3,
         v10) == -2147217402 )
  {
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        231,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v10);
  CVar::~CVar((CVar *)v11);
  CVar::~CVar((CVar *)v9);
  CVar::~CVar((CVar *)v12);
  CSystemEventClass::~CSystemEventClass((CSystemEventClass *)v13);
}

```

## disassembly

```asm
0x1800b5b90  mov     [rsp-8+arg_8], rbx
0x1800b5b95  mov     [rsp-8+arg_10], rdi
0x1800b5b9a  push    rbp
0x1800b5b9b  lea     rbp, [rsp-330h]
0x1800b5ba3  sub     rsp, 430h
0x1800b5baa  mov     rax, cs:__security_cookie
0x1800b5bb1  xor     rax, rsp
0x1800b5bb4  mov     [rbp+330h+var_10], rax
0x1800b5bbb  mov     rbx, rcx
0x1800b5bbe  lea     rcx, [rbp+330h+var_370]; this
0x1800b5bc2  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800b5bc7  nop
0x1800b5bc8  lea     rcx, [rbp+330h+var_370]; this
0x1800b5bcc  call    ?Init@CSystemEventClass@@QEAAXXZ; CSystemEventClass::Init(void)
0x1800b5bd1  xor     r9d, r9d
0x1800b5bd4  xor     r8d, r8d
0x1800b5bd7  lea     rdx, [rbp+330h+var_370]
0x1800b5bdb  mov     rcx, rbx
0x1800b5bde  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800b5be4  mov     edi, 80041006h
0x1800b5be9  cmp     eax, edi
0x1800b5beb  jnz     short loc_1800B5C4E
0x1800b5bed  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b5bf3  mov     edx, 0FFFFFFFEh
0x1800b5bf8  mov     rcx, rax
0x1800b5bfb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b5c01  lea     rax, WPP_GLOBAL_Control
0x1800b5c08  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5c0f  cmp     rcx, rax
0x1800b5c12  jz      short loc_1800B5C3C
0x1800b5c14  test    byte ptr [rcx+1Ch], 1
0x1800b5c18  jz      short loc_1800B5C3C
0x1800b5c1a  cmp     byte ptr [rcx+19h], 2
0x1800b5c1e  jb      short loc_1800B5C3C
0x1800b5c20  mov     edx, 0E2h
0x1800b5c25  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b5c2c  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b5c33  mov     rcx, [rcx+10h]
0x1800b5c37  call    WPP_SF_s
0x1800b5c3c  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b5c43  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b5c48  call    _CxxThrowException_0
0x1800b5c4e  lea     r8, aEventdroppedev; "__EventDroppedEvent"
0x1800b5c55  mov     edx, 8
0x1800b5c5a  lea     rcx, [rbp+330h+var_398]
0x1800b5c5e  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b5c64  nop
0x1800b5c65  mov     rax, [rbx]
0x1800b5c68  xor     r9d, r9d
0x1800b5c6b  lea     r8, [rbp+330h+var_398]
0x1800b5c6f  lea     rdx, aClass_0; "__CLASS"
0x1800b5c76  mov     rcx, rbx
0x1800b5c79  mov     rax, [rax+368h]
0x1800b5c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5c85  cmp     eax, edi
0x1800b5c87  jnz     short loc_1800B5CEA
0x1800b5c89  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b5c8f  mov     edx, 0FFFFFFFEh
0x1800b5c94  mov     rcx, rax
0x1800b5c97  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b5c9d  lea     rax, WPP_GLOBAL_Control
0x1800b5ca4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5cab  cmp     rcx, rax
0x1800b5cae  jz      short loc_1800B5CD8
0x1800b5cb0  test    byte ptr [rcx+1Ch], 1
0x1800b5cb4  jz      short loc_1800B5CD8
0x1800b5cb6  cmp     byte ptr [rcx+19h], 2
0x1800b5cba  jb      short loc_1800B5CD8
0x1800b5cbc  mov     edx, 0E3h
0x1800b5cc1  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b5cc8  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b5ccf  mov     rcx, [rcx+10h]
0x1800b5cd3  call    WPP_SF_s
0x1800b5cd8  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b5cdf  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b5ce4  call    _CxxThrowException_0
0x1800b5cea  lea     rcx, [rsp+430h+var_3F8]
0x1800b5cef  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800b5cf5  nop
0x1800b5cf6  lea     rcx, [rsp+430h+var_3F8]
0x1800b5cfb  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800b5d01  mov     rax, [rbx]
0x1800b5d04  mov     r9d, 0Dh
0x1800b5d0a  lea     r8, [rsp+430h+var_3F8]
0x1800b5d0f  lea     rdx, aEvent_0; "Event"
0x1800b5d16  mov     rcx, rbx
0x1800b5d19  mov     rax, [rax+368h]
0x1800b5d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5d25  cmp     eax, edi
0x1800b5d27  jnz     short loc_1800B5D8A
0x1800b5d29  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b5d2f  mov     edx, 0FFFFFFFEh
0x1800b5d34  mov     rcx, rax
0x1800b5d37  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b5d3d  lea     rax, WPP_GLOBAL_Control
0x1800b5d44  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5d4b  cmp     rcx, rax
0x1800b5d4e  jz      short loc_1800B5D78
0x1800b5d50  test    byte ptr [rcx+1Ch], 1
0x1800b5d54  jz      short loc_1800B5D78
0x1800b5d56  cmp     byte ptr [rcx+19h], 2
0x1800b5d5a  jb      short loc_1800B5D78
0x1800b5d5c  mov     edx, 0E4h
0x1800b5d61  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b5d68  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b5d6f  mov     rcx, [rcx+10h]
0x1800b5d73  call    WPP_SF_s
0x1800b5d78  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b5d7f  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b5d84  call    _CxxThrowException_0
0x1800b5d8a  mov     rax, [rbx]
0x1800b5d8d  mov     r9d, 66h ; 'f'
0x1800b5d93  lea     r8, [rsp+430h+var_3F8]
0x1800b5d98  lea     rdx, aIntendedconsum; "IntendedConsumer"
0x1800b5d9f  mov     rcx, rbx
0x1800b5da2  mov     rax, [rax+368h]
0x1800b5da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5dae  cmp     eax, edi
0x1800b5db0  jnz     short loc_1800B5E13
0x1800b5db2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b5db8  mov     edx, 0FFFFFFFEh
0x1800b5dbd  mov     rcx, rax
0x1800b5dc0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b5dc6  lea     rax, WPP_GLOBAL_Control
0x1800b5dcd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5dd4  cmp     rcx, rax
0x1800b5dd7  jz      short loc_1800B5E01
0x1800b5dd9  test    byte ptr [rcx+1Ch], 1
0x1800b5ddd  jz      short loc_1800B5E01
0x1800b5ddf  cmp     byte ptr [rcx+19h], 2
0x1800b5de3  jb      short loc_1800B5E01
0x1800b5de5  mov     edx, 0E5h
0x1800b5dea  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b5df1  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b5df8  mov     rcx, [rcx+10h]
0x1800b5dfc  call    WPP_SF_s
0x1800b5e01  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b5e08  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b5e0d  call    _CxxThrowException_0
0x1800b5e13  lea     r8, aObjectEvent; "object:__Event"
0x1800b5e1a  mov     edx, 8
0x1800b5e1f  lea     rcx, [rsp+430h+var_3B8]
0x1800b5e24  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b5e2a  nop
0x1800b5e2b  mov     rax, [rbx]
0x1800b5e2e  lea     rcx, [rsp+430h+var_3B8]
0x1800b5e33  mov     [rsp+430h+var_410], rcx
0x1800b5e38  mov     r9d, 3
0x1800b5e3e  lea     r8, aCimtype_0; "CIMTYPE"
0x1800b5e45  lea     rdx, aEvent_0; "Event"
0x1800b5e4c  mov     rcx, rbx
0x1800b5e4f  mov     rax, [rax+378h]
0x1800b5e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5e5b  cmp     eax, edi
0x1800b5e5d  jnz     short loc_1800B5EC0
0x1800b5e5f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b5e65  mov     edx, 0FFFFFFFEh
0x1800b5e6a  mov     rcx, rax
0x1800b5e6d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b5e73  lea     rax, WPP_GLOBAL_Control
0x1800b5e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5e81  cmp     rcx, rax
0x1800b5e84  jz      short loc_1800B5EAE
0x1800b5e86  test    byte ptr [rcx+1Ch], 1
0x1800b5e8a  jz      short loc_1800B5EAE
0x1800b5e8c  cmp     byte ptr [rcx+19h], 2
0x1800b5e90  jb      short loc_1800B5EAE
0x1800b5e92  mov     edx, 0E6h
0x1800b5e97  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b5e9e  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b5ea5  mov     rcx, [rcx+10h]
0x1800b5ea9  call    WPP_SF_s
0x1800b5eae  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b5eb5  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b5eba  call    _CxxThrowException_0
0x1800b5ec0  lea     r8, aRefEventconsum; "ref:__EventConsumer"
0x1800b5ec7  mov     edx, 8
0x1800b5ecc  lea     rcx, [rsp+430h+var_3D8]
0x1800b5ed1  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b5ed7  nop
0x1800b5ed8  mov     rax, [rbx]
0x1800b5edb  lea     rcx, [rsp+430h+var_3D8]
0x1800b5ee0  mov     [rsp+430h+var_410], rcx
0x1800b5ee5  mov     r9d, 3
0x1800b5eeb  lea     r8, aCimtype_0; "CIMTYPE"
0x1800b5ef2  lea     rdx, aIntendedconsum; "IntendedConsumer"
0x1800b5ef9  mov     rcx, rbx
0x1800b5efc  mov     rax, [rax+378h]
0x1800b5f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5f08  cmp     eax, edi
0x1800b5f0a  jnz     short loc_1800B5F6D
0x1800b5f0c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b5f12  mov     edx, 0FFFFFFFEh
0x1800b5f17  mov     rcx, rax
0x1800b5f1a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b5f20  lea     rax, WPP_GLOBAL_Control
0x1800b5f27  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5f2e  cmp     rcx, rax
0x1800b5f31  jz      short loc_1800B5F5B
0x1800b5f33  test    byte ptr [rcx+1Ch], 1
0x1800b5f37  jz      short loc_1800B5F5B
0x1800b5f39  cmp     byte ptr [rcx+19h], 2
0x1800b5f3d  jb      short loc_1800B5F5B
0x1800b5f3f  mov     edx, 0E7h
0x1800b5f44  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b5f4b  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b5f52  mov     rcx, [rcx+10h]
0x1800b5f56  call    WPP_SF_s
0x1800b5f5b  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b5f62  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b5f67  call    _CxxThrowException_0
0x1800b5f6d  lea     rcx, [rsp+430h+var_3D8]
0x1800b5f72  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b5f78  nop
0x1800b5f79  lea     rcx, [rsp+430h+var_3B8]
0x1800b5f7e  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b5f84  nop
0x1800b5f85  lea     rcx, [rsp+430h+var_3F8]
0x1800b5f8a  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b5f90  nop
0x1800b5f91  lea     rcx, [rbp+330h+var_398]
0x1800b5f95  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b5f9b  nop
0x1800b5f9c  lea     rcx, [rbp+330h+var_370]; this
0x1800b5fa0  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800b5fa5  mov     rcx, [rbp+330h+var_10]
0x1800b5fac  xor     rcx, rsp; StackCookie
0x1800b5faf  call    __security_check_cookie
0x1800b5fb4  lea     r11, [rsp+430h+var_s0]
0x1800b5fbc  mov     rbx, [r11+18h]
0x1800b5fc0  mov     rdi, [r11+20h]
0x1800b5fc4  mov     rsp, r11
0x1800b5fc7  pop     rbp
0x1800b5fc8  retn
```
