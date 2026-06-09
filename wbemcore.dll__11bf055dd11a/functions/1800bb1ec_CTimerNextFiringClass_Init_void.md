# CTimerNextFiringClass::Init(void)

- ea: `0x1800bb1ec`
- end: `0x1800bb5fc`
- name: `?Init@CTimerNextFiringClass@@QEAAXXZ`
- size: `1040`
- prototype: `void __fastcall(CTimerNextFiringClass *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`

## callees

- `0x18006a6b8`
- `0x180085c70`
- `0x180086358`
- `0x18008846c`
- `0x18008a658`
- `0x1800bb1ec`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800bb47d`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800bb47d`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bb2bb`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bb2bb`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800bb359`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800bb359`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800bb34d`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800bb34d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb5b0`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb5bc`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb5c8`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb5b0`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb5bc`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb5c8`
- `wbemcomn!GetMemLogObject` at `0x1800bb249`
- `wbemcomn!GetMemLogObject` at `0x1800bb2e7`
- `wbemcomn!GetMemLogObject` at `0x1800bb387`
- `wbemcomn!GetMemLogObject` at `0x1800bb410`
- `wbemcomn!GetMemLogObject` at `0x1800bb4b5`
- `wbemcomn!GetMemLogObject` at `0x1800bb54a`
- `wbemcomn!GetMemLogObject` at `0x1800bb249`
- `wbemcomn!GetMemLogObject` at `0x1800bb2e7`
- `wbemcomn!GetMemLogObject` at `0x1800bb387`
- `wbemcomn!GetMemLogObject` at `0x1800bb410`
- `wbemcomn!GetMemLogObject` at `0x1800bb4b5`
- `wbemcomn!GetMemLogObject` at `0x1800bb54a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb257`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb2f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb395`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb41e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb4c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb558`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb257`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb2f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb395`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb41e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb4c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb558`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800bb23a`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800bb23a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CTimerNextFiringClass::Init(CTimerNextFiringClass *this)
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
  CIndicationRelatedClass::Init((CIndicationRelatedClass *)v12);
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
        322,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v11, 8, L"__TimerNextFiring");
  if ( (*(unsigned int (__fastcall **)(CTimerNextFiringClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
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
        323,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9);
  CVar::SetAsNull((CVar *)v9);
  if ( (*(unsigned int (__fastcall **)(CTimerNextFiringClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this
                                                                                                  + 872LL))(
         this,
         L"TimerId",
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
        324,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( (*(unsigned int (__fastcall **)(CTimerNextFiringClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this
                                                                                                  + 872LL))(
         this,
         L"NextEvent64BitTime",
         v9,
         20) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        325,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v10, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CTimerNextFiringClass *, const wchar_t *, const wchar_t *, _QWORD, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"TimerId",
         L"key",
         0,
         v10) == -2147217402 )
  {
    v6 = GetMemLogObject();
    CMemoryLog::Write(v6, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        326,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( (*(unsigned int (__fastcall **)(CTimerNextFiringClass *, const wchar_t *, const wchar_t *, __int64, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"NextEvent64BitTime",
         L"not_null",
         19,
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
        327,
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
0x1800bb1ec  mov     [rsp-8+arg_8], rbx
0x1800bb1f1  mov     [rsp-8+arg_10], rdi
0x1800bb1f6  push    rbp
0x1800bb1f7  lea     rbp, [rsp-310h]
0x1800bb1ff  sub     rsp, 410h
0x1800bb206  mov     rax, cs:__security_cookie
0x1800bb20d  xor     rax, rsp
0x1800bb210  mov     [rbp+310h+var_10], rax
0x1800bb217  mov     rbx, rcx
0x1800bb21a  lea     rcx, [rbp+310h+var_370]; this
0x1800bb21e  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800bb223  nop
0x1800bb224  lea     rcx, [rbp+310h+var_370]; this
0x1800bb228  call    ?Init@CIndicationRelatedClass@@QEAAXXZ; CIndicationRelatedClass::Init(void)
0x1800bb22d  xor     r9d, r9d
0x1800bb230  xor     r8d, r8d
0x1800bb233  lea     rdx, [rbp+310h+var_370]
0x1800bb237  mov     rcx, rbx
0x1800bb23a  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800bb240  mov     edi, 80041006h
0x1800bb245  cmp     eax, edi
0x1800bb247  jnz     short loc_1800BB2AA
0x1800bb249  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bb24f  mov     edx, 0FFFFFFFEh
0x1800bb254  mov     rcx, rax
0x1800bb257  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bb25d  lea     rax, WPP_GLOBAL_Control
0x1800bb264  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb26b  cmp     rcx, rax
0x1800bb26e  jz      short loc_1800BB298
0x1800bb270  test    byte ptr [rcx+1Ch], 1
0x1800bb274  jz      short loc_1800BB298
0x1800bb276  cmp     byte ptr [rcx+19h], 2
0x1800bb27a  jb      short loc_1800BB298
0x1800bb27c  mov     edx, 142h
0x1800bb281  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bb288  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bb28f  mov     rcx, [rcx+10h]
0x1800bb293  call    WPP_SF_s
0x1800bb298  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bb29f  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800bb2a4  call    _CxxThrowException_0
0x1800bb2aa  lea     r8, aTimernextfirin; "__TimerNextFiring"
0x1800bb2b1  mov     edx, 8
0x1800bb2b6  lea     rcx, [rsp+410h+var_398]
0x1800bb2bb  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800bb2c1  nop
0x1800bb2c2  mov     rax, [rbx]
0x1800bb2c5  xor     r9d, r9d
0x1800bb2c8  lea     r8, [rsp+410h+var_398]
0x1800bb2cd  lea     rdx, aClass_0; "__CLASS"
0x1800bb2d4  mov     rcx, rbx
0x1800bb2d7  mov     rax, [rax+368h]
0x1800bb2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb2e3  cmp     eax, edi
0x1800bb2e5  jnz     short loc_1800BB348
0x1800bb2e7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bb2ed  mov     edx, 0FFFFFFFEh
0x1800bb2f2  mov     rcx, rax
0x1800bb2f5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bb2fb  lea     rax, WPP_GLOBAL_Control
0x1800bb302  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb309  cmp     rcx, rax
0x1800bb30c  jz      short loc_1800BB336
0x1800bb30e  test    byte ptr [rcx+1Ch], 1
0x1800bb312  jz      short loc_1800BB336
0x1800bb314  cmp     byte ptr [rcx+19h], 2
0x1800bb318  jb      short loc_1800BB336
0x1800bb31a  mov     edx, 143h
0x1800bb31f  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bb326  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bb32d  mov     rcx, [rcx+10h]
0x1800bb331  call    WPP_SF_s
0x1800bb336  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bb33d  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800bb342  call    _CxxThrowException_0
0x1800bb348  lea     rcx, [rsp+410h+var_3D8]
0x1800bb34d  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800bb353  nop
0x1800bb354  lea     rcx, [rsp+410h+var_3D8]
0x1800bb359  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800bb35f  mov     rax, [rbx]
0x1800bb362  mov     r9d, 8
0x1800bb368  lea     r8, [rsp+410h+var_3D8]
0x1800bb36d  lea     rdx, aTimerid; "TimerId"
0x1800bb374  mov     rcx, rbx
0x1800bb377  mov     rax, [rax+368h]
0x1800bb37e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb383  cmp     eax, edi
0x1800bb385  jnz     short loc_1800BB3E8
0x1800bb387  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bb38d  mov     edx, 0FFFFFFFEh
0x1800bb392  mov     rcx, rax
0x1800bb395  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bb39b  lea     rax, WPP_GLOBAL_Control
0x1800bb3a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb3a9  cmp     rcx, rax
0x1800bb3ac  jz      short loc_1800BB3D6
0x1800bb3ae  test    byte ptr [rcx+1Ch], 1
0x1800bb3b2  jz      short loc_1800BB3D6
0x1800bb3b4  cmp     byte ptr [rcx+19h], 2
0x1800bb3b8  jb      short loc_1800BB3D6
0x1800bb3ba  mov     edx, 144h
0x1800bb3bf  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bb3c6  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bb3cd  mov     rcx, [rcx+10h]
0x1800bb3d1  call    WPP_SF_s
0x1800bb3d6  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bb3dd  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800bb3e2  call    _CxxThrowException_0
0x1800bb3e8  mov     rax, [rbx]
0x1800bb3eb  mov     r9d, 14h
0x1800bb3f1  lea     r8, [rsp+410h+var_3D8]
0x1800bb3f6  lea     rdx, aNextevent64bit; "NextEvent64BitTime"
0x1800bb3fd  mov     rcx, rbx
0x1800bb400  mov     rax, [rax+368h]
0x1800bb407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb40c  cmp     eax, edi
0x1800bb40e  jnz     short loc_1800BB471
0x1800bb410  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bb416  mov     edx, 0FFFFFFFEh
0x1800bb41b  mov     rcx, rax
0x1800bb41e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bb424  lea     rax, WPP_GLOBAL_Control
0x1800bb42b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb432  cmp     rcx, rax
0x1800bb435  jz      short loc_1800BB45F
0x1800bb437  test    byte ptr [rcx+1Ch], 1
0x1800bb43b  jz      short loc_1800BB45F
0x1800bb43d  cmp     byte ptr [rcx+19h], 2
0x1800bb441  jb      short loc_1800BB45F
0x1800bb443  mov     edx, 145h
0x1800bb448  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bb44f  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bb456  mov     rcx, [rcx+10h]
0x1800bb45a  call    WPP_SF_s
0x1800bb45f  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bb466  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800bb46b  call    _CxxThrowException_0
0x1800bb471  or      edx, 0FFFFFFFFh
0x1800bb474  lea     r8d, [rdx+0Ch]
0x1800bb478  lea     rcx, [rsp+410h+var_3B8]
0x1800bb47d  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800bb483  nop
0x1800bb484  mov     rax, [rbx]
0x1800bb487  lea     rcx, [rsp+410h+var_3B8]
0x1800bb48c  mov     [rsp+410h+var_3F0], rcx
0x1800bb491  xor     r9d, r9d
0x1800bb494  lea     r8, aKey; "key"
0x1800bb49b  lea     rdx, aTimerid; "TimerId"
0x1800bb4a2  mov     rcx, rbx
0x1800bb4a5  mov     rax, [rax+378h]
0x1800bb4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb4b1  cmp     eax, edi
0x1800bb4b3  jnz     short loc_1800BB516
0x1800bb4b5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bb4bb  mov     edx, 0FFFFFFFEh
0x1800bb4c0  mov     rcx, rax
0x1800bb4c3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bb4c9  lea     rax, WPP_GLOBAL_Control
0x1800bb4d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb4d7  cmp     rcx, rax
0x1800bb4da  jz      short loc_1800BB504
0x1800bb4dc  test    byte ptr [rcx+1Ch], 1
0x1800bb4e0  jz      short loc_1800BB504
0x1800bb4e2  cmp     byte ptr [rcx+19h], 2
0x1800bb4e6  jb      short loc_1800BB504
0x1800bb4e8  mov     edx, 146h
0x1800bb4ed  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bb4f4  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bb4fb  mov     rcx, [rcx+10h]
0x1800bb4ff  call    WPP_SF_s
0x1800bb504  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bb50b  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800bb510  call    _CxxThrowException_0
0x1800bb516  mov     rax, [rbx]
0x1800bb519  lea     rcx, [rsp+410h+var_3B8]
0x1800bb51e  mov     [rsp+410h+var_3F0], rcx
0x1800bb523  mov     r9d, 13h
0x1800bb529  lea     r8, aNotNull; "not_null"
0x1800bb530  lea     rdx, aNextevent64bit; "NextEvent64BitTime"
0x1800bb537  mov     rcx, rbx
0x1800bb53a  mov     rax, [rax+378h]
0x1800bb541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb546  cmp     eax, edi
0x1800bb548  jnz     short loc_1800BB5AB
0x1800bb54a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bb550  mov     edx, 0FFFFFFFEh
0x1800bb555  mov     rcx, rax
0x1800bb558  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bb55e  lea     rax, WPP_GLOBAL_Control
0x1800bb565  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb56c  cmp     rcx, rax
0x1800bb56f  jz      short loc_1800BB599
0x1800bb571  test    byte ptr [rcx+1Ch], 1
0x1800bb575  jz      short loc_1800BB599
0x1800bb577  cmp     byte ptr [rcx+19h], 2
0x1800bb57b  jb      short loc_1800BB599
0x1800bb57d  mov     edx, 147h
0x1800bb582  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bb589  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bb590  mov     rcx, [rcx+10h]
0x1800bb594  call    WPP_SF_s
0x1800bb599  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bb5a0  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800bb5a5  call    _CxxThrowException_0
0x1800bb5ab  lea     rcx, [rsp+410h+var_3B8]
0x1800bb5b0  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bb5b6  nop
0x1800bb5b7  lea     rcx, [rsp+410h+var_3D8]
0x1800bb5bc  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bb5c2  nop
0x1800bb5c3  lea     rcx, [rsp+410h+var_398]
0x1800bb5c8  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bb5ce  nop
0x1800bb5cf  lea     rcx, [rbp+310h+var_370]; this
0x1800bb5d3  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800bb5d8  mov     rcx, [rbp+310h+var_10]
0x1800bb5df  xor     rcx, rsp; StackCookie
0x1800bb5e2  call    __security_check_cookie
0x1800bb5e7  lea     r11, [rsp+410h+var_s0]
0x1800bb5ef  mov     rbx, [r11+18h]
0x1800bb5f3  mov     rdi, [r11+20h]
0x1800bb5f7  mov     rsp, r11
0x1800bb5fa  pop     rbp
0x1800bb5fb  retn
```
