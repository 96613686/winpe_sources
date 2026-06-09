# CConsumerFailureEventClass::Init(void)

- ea: `0x1800b4eb0`
- end: `0x1800b52b9`
- name: `?Init@CConsumerFailureEventClass@@QEAAXXZ`
- size: `1033`
- prototype: `void __fastcall(CConsumerFailureEventClass *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`

## callees

- `0x180085c70`
- `0x180086358`
- `0x18008846c`
- `0x18008a658`
- `0x1800b4eb0`
- `0x1800b5b90`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b4f7f`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b51cf`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b4f7f`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b51cf`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b501d`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b501d`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b5011`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b5011`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b526d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b5279`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b5285`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b526d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b5279`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b5285`
- `wbemcomn!GetMemLogObject` at `0x1800b4f0d`
- `wbemcomn!GetMemLogObject` at `0x1800b4fab`
- `wbemcomn!GetMemLogObject` at `0x1800b504b`
- `wbemcomn!GetMemLogObject` at `0x1800b50d4`
- `wbemcomn!GetMemLogObject` at `0x1800b515d`
- `wbemcomn!GetMemLogObject` at `0x1800b5207`
- `wbemcomn!GetMemLogObject` at `0x1800b4f0d`
- `wbemcomn!GetMemLogObject` at `0x1800b4fab`
- `wbemcomn!GetMemLogObject` at `0x1800b504b`
- `wbemcomn!GetMemLogObject` at `0x1800b50d4`
- `wbemcomn!GetMemLogObject` at `0x1800b515d`
- `wbemcomn!GetMemLogObject` at `0x1800b5207`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b4f1b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b4fb9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5059`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b50e2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b516b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5215`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b4f1b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b4fb9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5059`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b50e2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b516b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b5215`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b4efe`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b4efe`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CConsumerFailureEventClass::Init(CConsumerFailureEventClass *this)
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
  _BYTE v11[40]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v12[864]; // [rsp+A0h] [rbp-60h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v12);
  CEventDroppedEventClass::Init((CEventDroppedEventClass *)v12);
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
        236,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v11, 8, L"__ConsumerFailureEvent");
  if ( (*(unsigned int (__fastcall **)(CConsumerFailureEventClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
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
        237,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9);
  CVar::SetAsNull((CVar *)v9);
  if ( (*(unsigned int (__fastcall **)(CConsumerFailureEventClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"ErrorCode",
         v9,
         19) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        238,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( (*(unsigned int (__fastcall **)(CConsumerFailureEventClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"ErrorDescription",
         v9,
         8) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        239,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( (*(unsigned int (__fastcall **)(CConsumerFailureEventClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"ErrorObject",
         v9,
         13) == -2147217402 )
  {
    v6 = GetMemLogObject();
    CMemoryLog::Write(v6, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        240,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v10, 8, L"object:__ExtendedStatus");
  if ( (*(unsigned int (__fastcall **)(CConsumerFailureEventClass *, const wchar_t *, const wchar_t *, _QWORD, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"ErrorObject",
         L"CIMTYPE",
         0,
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
        241,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v10);
  CVar::~CVar((CVar *)v9);
  CVar::~CVar((CVar *)v11);
  CSystemEventClass::~CSystemEventClass((CSystemEventClass *)v12);
}

```

## disassembly

```asm
0x1800b4eb0  mov     [rsp-8+arg_8], rbx
0x1800b4eb5  mov     [rsp-8+arg_10], rdi
0x1800b4eba  push    rbp
0x1800b4ebb  lea     rbp, [rsp-310h]
0x1800b4ec3  sub     rsp, 410h
0x1800b4eca  mov     rax, cs:__security_cookie
0x1800b4ed1  xor     rax, rsp
0x1800b4ed4  mov     [rbp+310h+var_10], rax
0x1800b4edb  mov     rbx, rcx
0x1800b4ede  lea     rcx, [rbp+310h+var_370]; this
0x1800b4ee2  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800b4ee7  nop
0x1800b4ee8  lea     rcx, [rbp+310h+var_370]; this
0x1800b4eec  call    ?Init@CEventDroppedEventClass@@QEAAXXZ; CEventDroppedEventClass::Init(void)
0x1800b4ef1  xor     r9d, r9d
0x1800b4ef4  xor     r8d, r8d
0x1800b4ef7  lea     rdx, [rbp+310h+var_370]
0x1800b4efb  mov     rcx, rbx
0x1800b4efe  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800b4f04  mov     edi, 80041006h
0x1800b4f09  cmp     eax, edi
0x1800b4f0b  jnz     short loc_1800B4F6E
0x1800b4f0d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b4f13  mov     edx, 0FFFFFFFEh
0x1800b4f18  mov     rcx, rax
0x1800b4f1b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b4f21  lea     rax, WPP_GLOBAL_Control
0x1800b4f28  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4f2f  cmp     rcx, rax
0x1800b4f32  jz      short loc_1800B4F5C
0x1800b4f34  test    byte ptr [rcx+1Ch], 1
0x1800b4f38  jz      short loc_1800B4F5C
0x1800b4f3a  cmp     byte ptr [rcx+19h], 2
0x1800b4f3e  jb      short loc_1800B4F5C
0x1800b4f40  mov     edx, 0ECh
0x1800b4f45  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b4f4c  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b4f53  mov     rcx, [rcx+10h]
0x1800b4f57  call    WPP_SF_s
0x1800b4f5c  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b4f63  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b4f68  call    _CxxThrowException_0
0x1800b4f6e  lea     r8, aConsumerfailur; "__ConsumerFailureEvent"
0x1800b4f75  mov     edx, 8
0x1800b4f7a  lea     rcx, [rsp+410h+var_398]
0x1800b4f7f  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b4f85  nop
0x1800b4f86  mov     rax, [rbx]
0x1800b4f89  xor     r9d, r9d
0x1800b4f8c  lea     r8, [rsp+410h+var_398]
0x1800b4f91  lea     rdx, aClass_0; "__CLASS"
0x1800b4f98  mov     rcx, rbx
0x1800b4f9b  mov     rax, [rax+368h]
0x1800b4fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4fa7  cmp     eax, edi
0x1800b4fa9  jnz     short loc_1800B500C
0x1800b4fab  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b4fb1  mov     edx, 0FFFFFFFEh
0x1800b4fb6  mov     rcx, rax
0x1800b4fb9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b4fbf  lea     rax, WPP_GLOBAL_Control
0x1800b4fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4fcd  cmp     rcx, rax
0x1800b4fd0  jz      short loc_1800B4FFA
0x1800b4fd2  test    byte ptr [rcx+1Ch], 1
0x1800b4fd6  jz      short loc_1800B4FFA
0x1800b4fd8  cmp     byte ptr [rcx+19h], 2
0x1800b4fdc  jb      short loc_1800B4FFA
0x1800b4fde  mov     edx, 0EDh
0x1800b4fe3  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b4fea  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b4ff1  mov     rcx, [rcx+10h]
0x1800b4ff5  call    WPP_SF_s
0x1800b4ffa  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b5001  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b5006  call    _CxxThrowException_0
0x1800b500c  lea     rcx, [rsp+410h+var_3D8]
0x1800b5011  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800b5017  nop
0x1800b5018  lea     rcx, [rsp+410h+var_3D8]
0x1800b501d  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800b5023  mov     rax, [rbx]
0x1800b5026  mov     r9d, 13h
0x1800b502c  lea     r8, [rsp+410h+var_3D8]
0x1800b5031  lea     rdx, aErrorcode; "ErrorCode"
0x1800b5038  mov     rcx, rbx
0x1800b503b  mov     rax, [rax+368h]
0x1800b5042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5047  cmp     eax, edi
0x1800b5049  jnz     short loc_1800B50AC
0x1800b504b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b5051  mov     edx, 0FFFFFFFEh
0x1800b5056  mov     rcx, rax
0x1800b5059  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b505f  lea     rax, WPP_GLOBAL_Control
0x1800b5066  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b506d  cmp     rcx, rax
0x1800b5070  jz      short loc_1800B509A
0x1800b5072  test    byte ptr [rcx+1Ch], 1
0x1800b5076  jz      short loc_1800B509A
0x1800b5078  cmp     byte ptr [rcx+19h], 2
0x1800b507c  jb      short loc_1800B509A
0x1800b507e  mov     edx, 0EEh
0x1800b5083  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b508a  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b5091  mov     rcx, [rcx+10h]
0x1800b5095  call    WPP_SF_s
0x1800b509a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b50a1  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b50a6  call    _CxxThrowException_0
0x1800b50ac  mov     rax, [rbx]
0x1800b50af  mov     r9d, 8
0x1800b50b5  lea     r8, [rsp+410h+var_3D8]
0x1800b50ba  lea     rdx, aErrordescripti; "ErrorDescription"
0x1800b50c1  mov     rcx, rbx
0x1800b50c4  mov     rax, [rax+368h]
0x1800b50cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b50d0  cmp     eax, edi
0x1800b50d2  jnz     short loc_1800B5135
0x1800b50d4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b50da  mov     edx, 0FFFFFFFEh
0x1800b50df  mov     rcx, rax
0x1800b50e2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b50e8  lea     rax, WPP_GLOBAL_Control
0x1800b50ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b50f6  cmp     rcx, rax
0x1800b50f9  jz      short loc_1800B5123
0x1800b50fb  test    byte ptr [rcx+1Ch], 1
0x1800b50ff  jz      short loc_1800B5123
0x1800b5101  cmp     byte ptr [rcx+19h], 2
0x1800b5105  jb      short loc_1800B5123
0x1800b5107  mov     edx, 0EFh
0x1800b510c  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b5113  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b511a  mov     rcx, [rcx+10h]
0x1800b511e  call    WPP_SF_s
0x1800b5123  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b512a  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b512f  call    _CxxThrowException_0
0x1800b5135  mov     rax, [rbx]
0x1800b5138  mov     r9d, 0Dh
0x1800b513e  lea     r8, [rsp+410h+var_3D8]
0x1800b5143  lea     rdx, aErrorobject; "ErrorObject"
0x1800b514a  mov     rcx, rbx
0x1800b514d  mov     rax, [rax+368h]
0x1800b5154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5159  cmp     eax, edi
0x1800b515b  jnz     short loc_1800B51BE
0x1800b515d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b5163  mov     edx, 0FFFFFFFEh
0x1800b5168  mov     rcx, rax
0x1800b516b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b5171  lea     rax, WPP_GLOBAL_Control
0x1800b5178  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b517f  cmp     rcx, rax
0x1800b5182  jz      short loc_1800B51AC
0x1800b5184  test    byte ptr [rcx+1Ch], 1
0x1800b5188  jz      short loc_1800B51AC
0x1800b518a  cmp     byte ptr [rcx+19h], 2
0x1800b518e  jb      short loc_1800B51AC
0x1800b5190  mov     edx, 0F0h
0x1800b5195  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b519c  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b51a3  mov     rcx, [rcx+10h]
0x1800b51a7  call    WPP_SF_s
0x1800b51ac  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b51b3  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b51b8  call    _CxxThrowException_0
0x1800b51be  lea     r8, aObjectExtended; "object:__ExtendedStatus"
0x1800b51c5  mov     edx, 8
0x1800b51ca  lea     rcx, [rsp+410h+var_3B8]
0x1800b51cf  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b51d5  nop
0x1800b51d6  mov     rax, [rbx]
0x1800b51d9  lea     rcx, [rsp+410h+var_3B8]
0x1800b51de  mov     [rsp+410h+var_3F0], rcx
0x1800b51e3  xor     r9d, r9d
0x1800b51e6  lea     r8, aCimtype_0; "CIMTYPE"
0x1800b51ed  lea     rdx, aErrorobject; "ErrorObject"
0x1800b51f4  mov     rcx, rbx
0x1800b51f7  mov     rax, [rax+378h]
0x1800b51fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5203  cmp     eax, edi
0x1800b5205  jnz     short loc_1800B5268
0x1800b5207  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b520d  mov     edx, 0FFFFFFFEh
0x1800b5212  mov     rcx, rax
0x1800b5215  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b521b  lea     rax, WPP_GLOBAL_Control
0x1800b5222  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5229  cmp     rcx, rax
0x1800b522c  jz      short loc_1800B5256
0x1800b522e  test    byte ptr [rcx+1Ch], 1
0x1800b5232  jz      short loc_1800B5256
0x1800b5234  cmp     byte ptr [rcx+19h], 2
0x1800b5238  jb      short loc_1800B5256
0x1800b523a  mov     edx, 0F1h
0x1800b523f  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b5246  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b524d  mov     rcx, [rcx+10h]
0x1800b5251  call    WPP_SF_s
0x1800b5256  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b525d  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b5262  call    _CxxThrowException_0
0x1800b5268  lea     rcx, [rsp+410h+var_3B8]
0x1800b526d  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b5273  nop
0x1800b5274  lea     rcx, [rsp+410h+var_3D8]
0x1800b5279  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b527f  nop
0x1800b5280  lea     rcx, [rsp+410h+var_398]
0x1800b5285  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b528b  nop
0x1800b528c  lea     rcx, [rbp+310h+var_370]; this
0x1800b5290  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800b5295  mov     rcx, [rbp+310h+var_10]
0x1800b529c  xor     rcx, rsp; StackCookie
0x1800b529f  call    __security_check_cookie
0x1800b52a4  lea     r11, [rsp+410h+var_s0]
0x1800b52ac  mov     rbx, [r11+18h]
0x1800b52b0  mov     rdi, [r11+20h]
0x1800b52b4  mov     rsp, r11
0x1800b52b7  pop     rbp
0x1800b52b8  retn
```
