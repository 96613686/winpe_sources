# CEventClass::Init(void)

- ea: `0x18007d388`
- end: `0x18007d706`
- name: `?Init@CEventClass@@QEAAXXZ`
- size: `894`
- prototype: `void __fastcall(CEventClass *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`
- `0x18007c848`
- `0x18007cd38`
- `0x18007d00c`

## callees

- `0x18006a6b8`
- `0x18007d388`
- `0x180085c70`
- `0x18008846c`
- `0x18008a658`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x18007d624`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x18007d624`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x18007d457`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x18007d457`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18007d4f5`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18007d589`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18007d4f5`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18007d589`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007d4e9`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007d4e9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007d6b9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007d6c5`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007d6d1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007d6b9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007d6c5`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007d6d1`
- `wbemcomn!GetMemLogObject` at `0x18007d3e5`
- `wbemcomn!GetMemLogObject` at `0x18007d483`
- `wbemcomn!GetMemLogObject` at `0x18007d523`
- `wbemcomn!GetMemLogObject` at `0x18007d5b7`
- `wbemcomn!GetMemLogObject` at `0x18007d653`
- `wbemcomn!GetMemLogObject` at `0x18007d3e5`
- `wbemcomn!GetMemLogObject` at `0x18007d483`
- `wbemcomn!GetMemLogObject` at `0x18007d523`
- `wbemcomn!GetMemLogObject` at `0x18007d5b7`
- `wbemcomn!GetMemLogObject` at `0x18007d653`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007d3f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007d491`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007d531`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007d5c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007d661`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007d3f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007d491`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007d531`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007d5c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007d661`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x18007d6dc`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x18007d6dc`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x18007d3d6`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x18007d3d6`

## string_xrefs

- `0x18007d59d`: `SECURITY_DESCRIPTOR`
- `0x18007d509`: `TIME_CREATED`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CEventClass::Init(CEventClass *this)
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
  CIndicationRelatedClass::Init((CIndicationRelatedClass *)v11);
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
        196,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v10, 8, L"__Event");
  if ( (*(unsigned int (__fastcall **)(CEventClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
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
        197,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8);
  CVar::SetAsNull((CVar *)v8);
  if ( (*(unsigned int (__fastcall **)(CEventClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"TIME_CREATED",
         v8,
         21) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        198,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::SetAsNull((CVar *)v8);
  if ( (*(unsigned int (__fastcall **)(CEventClass *, const unsigned __int16 *, _BYTE *, __int64))(*(_QWORD *)this
                                                                                                 + 872LL))(
         this,
         L"SECURITY_DESCRIPTOR",
         v8,
         8209) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        199,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CEventClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 984LL))(
         this,
         L"abstract",
         v9,
         19) == -2147217402 )
  {
    v6 = GetMemLogObject();
    CMemoryLog::Write(v6, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        200,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v9);
  CVar::~CVar((CVar *)v8);
  CVar::~CVar((CVar *)v10);
  CWbemClass::~CWbemClass((CWbemClass *)v11);
}

```

## disassembly

```asm
0x18007d388  mov     [rsp-8+arg_8], rbx
0x18007d38d  mov     [rsp-8+arg_10], rdi
0x18007d392  push    rbp
0x18007d393  lea     rbp, [rsp-310h]
0x18007d39b  sub     rsp, 410h
0x18007d3a2  mov     rax, cs:__security_cookie
0x18007d3a9  xor     rax, rsp
0x18007d3ac  mov     [rbp+310h+var_10], rax
0x18007d3b3  mov     rbx, rcx
0x18007d3b6  lea     rcx, [rbp+310h+var_370]; this
0x18007d3ba  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x18007d3bf  nop
0x18007d3c0  lea     rcx, [rbp+310h+var_370]; this
0x18007d3c4  call    ?Init@CIndicationRelatedClass@@QEAAXXZ; CIndicationRelatedClass::Init(void)
0x18007d3c9  xor     r9d, r9d
0x18007d3cc  xor     r8d, r8d
0x18007d3cf  lea     rdx, [rbp+310h+var_370]
0x18007d3d3  mov     rcx, rbx
0x18007d3d6  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x18007d3dc  mov     edi, 80041006h
0x18007d3e1  cmp     eax, edi
0x18007d3e3  jnz     short loc_18007D446
0x18007d3e5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007d3eb  mov     edx, 0FFFFFFFEh
0x18007d3f0  mov     rcx, rax
0x18007d3f3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007d3f9  lea     rax, WPP_GLOBAL_Control
0x18007d400  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d407  cmp     rcx, rax
0x18007d40a  jz      short loc_18007D434
0x18007d40c  test    byte ptr [rcx+1Ch], 1
0x18007d410  jz      short loc_18007D434
0x18007d412  cmp     byte ptr [rcx+19h], 2
0x18007d416  jb      short loc_18007D434
0x18007d418  mov     edx, 0C4h
0x18007d41d  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007d424  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007d42b  mov     rcx, [rcx+10h]
0x18007d42f  call    WPP_SF_s
0x18007d434  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007d43b  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x18007d440  call    _CxxThrowException_0
0x18007d446  lea     r8, aEvent; "__Event"
0x18007d44d  mov     edx, 8
0x18007d452  lea     rcx, [rsp+410h+var_398]
0x18007d457  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x18007d45d  nop
0x18007d45e  mov     rax, [rbx]
0x18007d461  xor     r9d, r9d
0x18007d464  lea     r8, [rsp+410h+var_398]
0x18007d469  lea     rdx, aClass_0; "__CLASS"
0x18007d470  mov     rcx, rbx
0x18007d473  mov     rax, [rax+368h]
0x18007d47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d47f  cmp     eax, edi
0x18007d481  jnz     short loc_18007D4E4
0x18007d483  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007d489  mov     edx, 0FFFFFFFEh
0x18007d48e  mov     rcx, rax
0x18007d491  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007d497  lea     rax, WPP_GLOBAL_Control
0x18007d49e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d4a5  cmp     rcx, rax
0x18007d4a8  jz      short loc_18007D4D2
0x18007d4aa  test    byte ptr [rcx+1Ch], 1
0x18007d4ae  jz      short loc_18007D4D2
0x18007d4b0  cmp     byte ptr [rcx+19h], 2
0x18007d4b4  jb      short loc_18007D4D2
0x18007d4b6  mov     edx, 0C5h
0x18007d4bb  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007d4c2  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007d4c9  mov     rcx, [rcx+10h]
0x18007d4cd  call    WPP_SF_s
0x18007d4d2  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007d4d9  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x18007d4de  call    _CxxThrowException_0
0x18007d4e4  lea     rcx, [rsp+410h+var_3D8]
0x18007d4e9  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18007d4ef  nop
0x18007d4f0  lea     rcx, [rsp+410h+var_3D8]
0x18007d4f5  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x18007d4fb  mov     rax, [rbx]
0x18007d4fe  mov     r9d, 15h
0x18007d504  lea     r8, [rsp+410h+var_3D8]
0x18007d509  lea     rdx, aTimeCreated; "TIME_CREATED"
0x18007d510  mov     rcx, rbx
0x18007d513  mov     rax, [rax+368h]
0x18007d51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d51f  cmp     eax, edi
0x18007d521  jnz     short loc_18007D584
0x18007d523  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007d529  mov     edx, 0FFFFFFFEh
0x18007d52e  mov     rcx, rax
0x18007d531  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007d537  lea     rax, WPP_GLOBAL_Control
0x18007d53e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d545  cmp     rcx, rax
0x18007d548  jz      short loc_18007D572
0x18007d54a  test    byte ptr [rcx+1Ch], 1
0x18007d54e  jz      short loc_18007D572
0x18007d550  cmp     byte ptr [rcx+19h], 2
0x18007d554  jb      short loc_18007D572
0x18007d556  mov     edx, 0C6h
0x18007d55b  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007d562  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007d569  mov     rcx, [rcx+10h]
0x18007d56d  call    WPP_SF_s
0x18007d572  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007d579  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x18007d57e  call    _CxxThrowException_0
0x18007d584  lea     rcx, [rsp+410h+var_3D8]
0x18007d589  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x18007d58f  mov     rax, [rbx]
0x18007d592  mov     r9d, 2011h
0x18007d598  lea     r8, [rsp+410h+var_3D8]
0x18007d59d  lea     rdx, aSecurityDescri; "SECURITY_DESCRIPTOR"
0x18007d5a4  mov     rcx, rbx
0x18007d5a7  mov     rax, [rax+368h]
0x18007d5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d5b3  cmp     eax, edi
0x18007d5b5  jnz     short loc_18007D618
0x18007d5b7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007d5bd  mov     edx, 0FFFFFFFEh
0x18007d5c2  mov     rcx, rax
0x18007d5c5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007d5cb  lea     rax, WPP_GLOBAL_Control
0x18007d5d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d5d9  cmp     rcx, rax
0x18007d5dc  jz      short loc_18007D606
0x18007d5de  test    byte ptr [rcx+1Ch], 1
0x18007d5e2  jz      short loc_18007D606
0x18007d5e4  cmp     byte ptr [rcx+19h], 2
0x18007d5e8  jb      short loc_18007D606
0x18007d5ea  mov     edx, 0C7h
0x18007d5ef  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007d5f6  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007d5fd  mov     rcx, [rcx+10h]
0x18007d601  call    WPP_SF_s
0x18007d606  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007d60d  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x18007d612  call    _CxxThrowException_0
0x18007d618  or      edx, 0FFFFFFFFh
0x18007d61b  lea     r8d, [rdx+0Ch]
0x18007d61f  lea     rcx, [rsp+410h+var_3B8]
0x18007d624  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x18007d62a  nop
0x18007d62b  mov     rax, [rbx]
0x18007d62e  mov     r9d, 13h
0x18007d634  lea     r8, [rsp+410h+var_3B8]
0x18007d639  lea     rdx, aAbstract_1; "abstract"
0x18007d640  mov     rcx, rbx
0x18007d643  mov     rax, [rax+3D8h]
0x18007d64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d64f  cmp     eax, edi
0x18007d651  jnz     short loc_18007D6B4
0x18007d653  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007d659  mov     edx, 0FFFFFFFEh
0x18007d65e  mov     rcx, rax
0x18007d661  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007d667  lea     rax, WPP_GLOBAL_Control
0x18007d66e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d675  cmp     rcx, rax
0x18007d678  jz      short loc_18007D6A2
0x18007d67a  test    byte ptr [rcx+1Ch], 1
0x18007d67e  jz      short loc_18007D6A2
0x18007d680  cmp     byte ptr [rcx+19h], 2
0x18007d684  jb      short loc_18007D6A2
0x18007d686  mov     edx, 0C8h
0x18007d68b  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007d692  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007d699  mov     rcx, [rcx+10h]
0x18007d69d  call    WPP_SF_s
0x18007d6a2  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007d6a9  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x18007d6ae  call    _CxxThrowException_0
0x18007d6b4  lea     rcx, [rsp+410h+var_3B8]
0x18007d6b9  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18007d6bf  nop
0x18007d6c0  lea     rcx, [rsp+410h+var_3D8]
0x18007d6c5  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18007d6cb  nop
0x18007d6cc  lea     rcx, [rsp+410h+var_398]
0x18007d6d1  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18007d6d7  nop
0x18007d6d8  lea     rcx, [rbp+310h+var_370]
0x18007d6dc  call    cs:__imp_??1CWbemClass@@UEAA@XZ; CWbemClass::~CWbemClass(void)
0x18007d6e2  mov     rcx, [rbp+310h+var_10]
0x18007d6e9  xor     rcx, rsp; StackCookie
0x18007d6ec  call    __security_check_cookie
0x18007d6f1  lea     r11, [rsp+410h+var_s0]
0x18007d6f9  mov     rbx, [r11+18h]
0x18007d6fd  mov     rdi, [r11+20h]
0x18007d701  mov     rsp, r11
0x18007d704  pop     rbp
0x18007d705  retn
```
