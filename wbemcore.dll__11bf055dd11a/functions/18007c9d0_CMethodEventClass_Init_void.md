# CMethodEventClass::Init(void)

- ea: `0x18007c9d0`
- end: `0x18007cd32`
- name: `?Init@CMethodEventClass@@QEAAXXZ`
- size: `866`
- prototype: `void __fastcall(CMethodEventClass *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`

## callees

- `0x18007c9d0`
- `0x18007d00c`
- `0x180085c70`
- `0x18008846c`
- `0x18008a658`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x18007caad`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x18007caad`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18007cb4b`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18007cb4b`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007cb3f`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007cb3f`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007ccf1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007ccfd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007ccf1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007ccfd`
- `wbemcomn!GetMemLogObject` at `0x18007ca3b`
- `wbemcomn!GetMemLogObject` at `0x18007cad9`
- `wbemcomn!GetMemLogObject` at `0x18007cb79`
- `wbemcomn!GetMemLogObject` at `0x18007cc02`
- `wbemcomn!GetMemLogObject` at `0x18007cc8b`
- `wbemcomn!GetMemLogObject` at `0x18007ca3b`
- `wbemcomn!GetMemLogObject` at `0x18007cad9`
- `wbemcomn!GetMemLogObject` at `0x18007cb79`
- `wbemcomn!GetMemLogObject` at `0x18007cc02`
- `wbemcomn!GetMemLogObject` at `0x18007cc8b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ca49`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007cae7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007cb87`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007cc10`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007cc99`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ca49`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007cae7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007cb87`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007cc10`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007cc99`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x18007cd08`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x18007cd08`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x18007ca2c`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x18007ca2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CMethodEventClass::Init(CMethodEventClass *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  CMemoryLog *v6; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v9[40]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v10[864]; // [rsp+80h] [rbp-80h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v10);
  CGenericDataEventClass::Init((CGenericDataEventClass *)v10, L"object", L"Instance");
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
        211,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, 8, L"__MethodInvocationEvent");
  if ( (*(unsigned int (__fastcall **)(CMethodEventClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
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
        212,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8);
  CVar::SetAsNull((CVar *)v8);
  if ( (*(unsigned int (__fastcall **)(CMethodEventClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"Method",
         v8,
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
        213,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( (*(unsigned int (__fastcall **)(CMethodEventClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"PreCall",
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
        214,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( (*(unsigned int (__fastcall **)(CMethodEventClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"Parameters",
         v8,
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
        215,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v8);
  CVar::~CVar((CVar *)v9);
  CWbemClass::~CWbemClass((CWbemClass *)v10);
}

```

## disassembly

```asm
0x18007c9d0  mov     [rsp-8+arg_8], rbx
0x18007c9d5  mov     [rsp-8+arg_10], rdi
0x18007c9da  push    rbp
0x18007c9db  lea     rbp, [rsp-2F0h]
0x18007c9e3  sub     rsp, 3F0h
0x18007c9ea  mov     rax, cs:__security_cookie
0x18007c9f1  xor     rax, rsp
0x18007c9f4  mov     [rbp+2F0h+var_10], rax
0x18007c9fb  mov     rbx, rcx
0x18007c9fe  lea     rcx, [rbp+2F0h+var_370]; this
0x18007ca02  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x18007ca07  nop
0x18007ca08  lea     r8, aInstance; "Instance"
0x18007ca0f  lea     rdx, aObject_0; "object"
0x18007ca16  lea     rcx, [rbp+2F0h+var_370]; this
0x18007ca1a  call    ?Init@CGenericDataEventClass@@QEAAXPEAG0@Z; CGenericDataEventClass::Init(ushort *,ushort *)
0x18007ca1f  xor     r9d, r9d
0x18007ca22  xor     r8d, r8d
0x18007ca25  lea     rdx, [rbp+2F0h+var_370]
0x18007ca29  mov     rcx, rbx
0x18007ca2c  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x18007ca32  mov     edi, 80041006h
0x18007ca37  cmp     eax, edi
0x18007ca39  jnz     short loc_18007CA9C
0x18007ca3b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007ca41  mov     edx, 0FFFFFFFEh
0x18007ca46  mov     rcx, rax
0x18007ca49  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007ca4f  lea     rax, WPP_GLOBAL_Control
0x18007ca56  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ca5d  cmp     rcx, rax
0x18007ca60  jz      short loc_18007CA8A
0x18007ca62  test    byte ptr [rcx+1Ch], 1
0x18007ca66  jz      short loc_18007CA8A
0x18007ca68  cmp     byte ptr [rcx+19h], 2
0x18007ca6c  jb      short loc_18007CA8A
0x18007ca6e  mov     edx, 0D3h
0x18007ca73  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007ca7a  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007ca81  mov     rcx, [rcx+10h]
0x18007ca85  call    WPP_SF_s
0x18007ca8a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007ca91  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x18007ca96  call    _CxxThrowException_0
0x18007ca9c  lea     r8, aMethodinvocati; "__MethodInvocationEvent"
0x18007caa3  mov     edx, 8
0x18007caa8  lea     rcx, [rsp+3F0h+var_398]
0x18007caad  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x18007cab3  nop
0x18007cab4  mov     rax, [rbx]
0x18007cab7  xor     r9d, r9d
0x18007caba  lea     r8, [rsp+3F0h+var_398]
0x18007cabf  lea     rdx, aClass_0; "__CLASS"
0x18007cac6  mov     rcx, rbx
0x18007cac9  mov     rax, [rax+368h]
0x18007cad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cad5  cmp     eax, edi
0x18007cad7  jnz     short loc_18007CB3A
0x18007cad9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007cadf  mov     edx, 0FFFFFFFEh
0x18007cae4  mov     rcx, rax
0x18007cae7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007caed  lea     rax, WPP_GLOBAL_Control
0x18007caf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cafb  cmp     rcx, rax
0x18007cafe  jz      short loc_18007CB28
0x18007cb00  test    byte ptr [rcx+1Ch], 1
0x18007cb04  jz      short loc_18007CB28
0x18007cb06  cmp     byte ptr [rcx+19h], 2
0x18007cb0a  jb      short loc_18007CB28
0x18007cb0c  mov     edx, 0D4h
0x18007cb11  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007cb18  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007cb1f  mov     rcx, [rcx+10h]
0x18007cb23  call    WPP_SF_s
0x18007cb28  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007cb2f  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x18007cb34  call    _CxxThrowException_0
0x18007cb3a  lea     rcx, [rsp+3F0h+var_3B8]
0x18007cb3f  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18007cb45  nop
0x18007cb46  lea     rcx, [rsp+3F0h+var_3B8]
0x18007cb4b  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x18007cb51  mov     rax, [rbx]
0x18007cb54  mov     r9d, 8
0x18007cb5a  lea     r8, [rsp+3F0h+var_3B8]
0x18007cb5f  lea     rdx, aMethod; "Method"
0x18007cb66  mov     rcx, rbx
0x18007cb69  mov     rax, [rax+368h]
0x18007cb70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb75  cmp     eax, edi
0x18007cb77  jnz     short loc_18007CBDA
0x18007cb79  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007cb7f  mov     edx, 0FFFFFFFEh
0x18007cb84  mov     rcx, rax
0x18007cb87  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007cb8d  lea     rax, WPP_GLOBAL_Control
0x18007cb94  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cb9b  cmp     rcx, rax
0x18007cb9e  jz      short loc_18007CBC8
0x18007cba0  test    byte ptr [rcx+1Ch], 1
0x18007cba4  jz      short loc_18007CBC8
0x18007cba6  cmp     byte ptr [rcx+19h], 2
0x18007cbaa  jb      short loc_18007CBC8
0x18007cbac  mov     edx, 0D5h
0x18007cbb1  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007cbb8  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007cbbf  mov     rcx, [rcx+10h]
0x18007cbc3  call    WPP_SF_s
0x18007cbc8  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007cbcf  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x18007cbd4  call    _CxxThrowException_0
0x18007cbda  mov     rax, [rbx]
0x18007cbdd  mov     r9d, 0Bh
0x18007cbe3  lea     r8, [rsp+3F0h+var_3B8]
0x18007cbe8  lea     rdx, aPrecall; "PreCall"
0x18007cbef  mov     rcx, rbx
0x18007cbf2  mov     rax, [rax+368h]
0x18007cbf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cbfe  cmp     eax, edi
0x18007cc00  jnz     short loc_18007CC63
0x18007cc02  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007cc08  mov     edx, 0FFFFFFFEh
0x18007cc0d  mov     rcx, rax
0x18007cc10  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007cc16  lea     rax, WPP_GLOBAL_Control
0x18007cc1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cc24  cmp     rcx, rax
0x18007cc27  jz      short loc_18007CC51
0x18007cc29  test    byte ptr [rcx+1Ch], 1
0x18007cc2d  jz      short loc_18007CC51
0x18007cc2f  cmp     byte ptr [rcx+19h], 2
0x18007cc33  jb      short loc_18007CC51
0x18007cc35  mov     edx, 0D6h
0x18007cc3a  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007cc41  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007cc48  mov     rcx, [rcx+10h]
0x18007cc4c  call    WPP_SF_s
0x18007cc51  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007cc58  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x18007cc5d  call    _CxxThrowException_0
0x18007cc63  mov     rax, [rbx]
0x18007cc66  mov     r9d, 0Dh
0x18007cc6c  lea     r8, [rsp+3F0h+var_3B8]
0x18007cc71  lea     rdx, aParameters; "Parameters"
0x18007cc78  mov     rcx, rbx
0x18007cc7b  mov     rax, [rax+368h]
0x18007cc82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cc87  cmp     eax, edi
0x18007cc89  jnz     short loc_18007CCEC
0x18007cc8b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007cc91  mov     edx, 0FFFFFFFEh
0x18007cc96  mov     rcx, rax
0x18007cc99  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007cc9f  lea     rax, WPP_GLOBAL_Control
0x18007cca6  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ccad  cmp     rcx, rax
0x18007ccb0  jz      short loc_18007CCDA
0x18007ccb2  test    byte ptr [rcx+1Ch], 1
0x18007ccb6  jz      short loc_18007CCDA
0x18007ccb8  cmp     byte ptr [rcx+19h], 2
0x18007ccbc  jb      short loc_18007CCDA
0x18007ccbe  mov     edx, 0D7h
0x18007ccc3  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007ccca  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007ccd1  mov     rcx, [rcx+10h]
0x18007ccd5  call    WPP_SF_s
0x18007ccda  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007cce1  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x18007cce6  call    _CxxThrowException_0
0x18007ccec  lea     rcx, [rsp+3F0h+var_3B8]
0x18007ccf1  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18007ccf7  nop
0x18007ccf8  lea     rcx, [rsp+3F0h+var_398]
0x18007ccfd  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18007cd03  nop
0x18007cd04  lea     rcx, [rbp+2F0h+var_370]
0x18007cd08  call    cs:__imp_??1CWbemClass@@UEAA@XZ; CWbemClass::~CWbemClass(void)
0x18007cd0e  mov     rcx, [rbp+2F0h+var_10]
0x18007cd15  xor     rcx, rsp; StackCookie
0x18007cd18  call    __security_check_cookie
0x18007cd1d  lea     r11, [rsp+3F0h+var_s0]
0x18007cd25  mov     rbx, [r11+18h]
0x18007cd29  mov     rdi, [r11+20h]
0x18007cd2d  mov     rsp, r11
0x18007cd30  pop     rbp
0x18007cd31  retn
```
