# CErrorObjectClass::Init(void)

- ea: `0x18007fab0`
- end: `0x18008004e`
- name: `?Init@CErrorObjectClass@@QEAAXXZ`
- size: `1438`
- prototype: `void __fastcall(CErrorObjectClass *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000a4e0`
- `0x18006adb4`

## callees

- `0x18000b140`
- `0x18007fab0`
- `0x180080054`
- `0x180085c70`
- `0x18008846c`
- `0x18008a658`
- `0x1800ce510`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x18007fbd0`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x18007fbd0`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18007fcba`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18007fcba`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007fcae`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007fcae`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180080015`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180080021`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180080015`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180080021`
- `wbemcomn!GetMemLogObject` at `0x18007fb0b`
- `wbemcomn!GetMemLogObject` at `0x18007fbf9`
- `wbemcomn!GetMemLogObject` at `0x18007fce2`
- `wbemcomn!GetMemLogObject` at `0x18007fdb6`
- `wbemcomn!GetMemLogObject` at `0x18007fe8a`
- `wbemcomn!GetMemLogObject` at `0x18007ff5e`
- `wbemcomn!GetMemLogObject` at `0x18007fb0b`
- `wbemcomn!GetMemLogObject` at `0x18007fbf9`
- `wbemcomn!GetMemLogObject` at `0x18007fce2`
- `wbemcomn!GetMemLogObject` at `0x18007fdb6`
- `wbemcomn!GetMemLogObject` at `0x18007fe8a`
- `wbemcomn!GetMemLogObject` at `0x18007ff5e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007fb19`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007fc05`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007fcf0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007fdc4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007fe98`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ff6c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007fb19`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007fc05`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007fcf0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007fdc4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007fe98`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ff6c`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18007fbe9`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18007fcd2`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18007fda6`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18007fe7a`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18007ff4e`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18007fbe9`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18007fcd2`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18007fda6`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18007fe7a`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18007ff4e`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x18008002d`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x18008002d`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x18007fafb`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x18007fafb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CErrorObjectClass::Init(CErrorObjectClass *this)
{
  int DerivedClass; // edi
  CMemoryLog *MemLogObject; // rax
  int v4; // edi
  CMemoryLog *v5; // rax
  int v6; // edi
  CMemoryLog *v7; // rax
  int v8; // edi
  CMemoryLog *v9; // rax
  int v10; // edi
  CMemoryLog *v11; // rax
  int v12; // ebx
  CMemoryLog *v13; // rax
  char pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v15[32]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v16[40]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v17[864]; // [rsp+70h] [rbp-90h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v17);
  CNotifyStatusClass::Init((CNotifyStatusClass *)v17);
  DerivedClass = CWbemClass::CreateDerivedClass(this, (struct CWbemClass *)v17, 0, 0);
  if ( DerivedClass < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( DerivedClass == -2147217402 )
    {
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          562,
          WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        563,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        (unsigned int)DerivedClass);
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v16, 8, L"__ExtendedStatus");
  v4 = CWbemClass::SetPropValue(this, L"__CLASS", (struct CVar *)v16, 0);
  if ( v4 < 0 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( v4 == -2147217402 )
    {
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          564,
          WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        565,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        (unsigned int)v4);
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v15);
  CVar::SetAsNull((CVar *)v15);
  v6 = CWbemClass::SetPropValue(this, L"ProviderName", (struct CVar *)v15, 8);
  if ( v6 < 0 )
  {
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, -2);
    if ( v6 == -2147217402 )
    {
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          566,
          WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        567,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        (unsigned int)v6);
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  v8 = CWbemClass::SetPropValue(this, L"Operation", (struct CVar *)v15, 8);
  if ( v8 < 0 )
  {
    v9 = GetMemLogObject();
    CMemoryLog::Write(v9, -2);
    if ( v8 == -2147217402 )
    {
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          568,
          WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        569,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        (unsigned int)v8);
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  v10 = CWbemClass::SetPropValue(this, L"ParameterInfo", (struct CVar *)v15, 8);
  if ( v10 < 0 )
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, -2);
    if ( v10 == -2147217402 )
    {
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          570,
          WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        571,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        (unsigned int)v10);
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  v12 = CWbemClass::SetPropValue(this, L"Description", (struct CVar *)v15, 8);
  if ( v12 < 0 )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, -2);
    if ( v12 == -2147217402 )
    {
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          572,
          WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        573,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        (unsigned int)v12);
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v15);
  CVar::~CVar((CVar *)v16);
  CWbemClass::~CWbemClass((CWbemClass *)v17);
}

```

## disassembly

```asm
0x18007fab0  push    rbp
0x18007fab2  push    rbx
0x18007fab3  push    rsi
0x18007fab4  push    rdi
0x18007fab5  lea     rbp, [rsp-2E8h]
0x18007fabd  sub     rsp, 3E8h
0x18007fac4  mov     rax, cs:__security_cookie
0x18007facb  xor     rax, rsp
0x18007face  mov     [rbp+300h+var_30], rax
0x18007fad5  mov     rbx, rcx
0x18007fad8  lea     rcx, [rsp+400h+var_390]; this
0x18007fadd  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x18007fae2  nop
0x18007fae3  lea     rcx, [rsp+400h+var_390]; this
0x18007fae8  call    ?Init@CNotifyStatusClass@@QEAAXXZ; CNotifyStatusClass::Init(void)
0x18007faed  xor     r9d, r9d
0x18007faf0  xor     r8d, r8d
0x18007faf3  lea     rdx, [rsp+400h+var_390]
0x18007faf8  mov     rcx, rbx
0x18007fafb  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x18007fb01  mov     edi, eax
0x18007fb03  test    eax, eax
0x18007fb05  jns     loc_18007FBBD
0x18007fb0b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007fb11  mov     edx, 0FFFFFFFEh
0x18007fb16  mov     rcx, rax
0x18007fb19  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007fb1f  cmp     edi, 80041006h
0x18007fb25  jnz     short loc_18007FB74
0x18007fb27  lea     rax, WPP_GLOBAL_Control
0x18007fb2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fb35  cmp     rcx, rax
0x18007fb38  jz      short loc_18007FB62
0x18007fb3a  test    byte ptr [rcx+1Ch], 1
0x18007fb3e  jz      short loc_18007FB62
0x18007fb40  cmp     byte ptr [rcx+19h], 2
0x18007fb44  jb      short loc_18007FB62
0x18007fb46  mov     edx, 232h
0x18007fb4b  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007fb52  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007fb59  mov     rcx, [rcx+10h]
0x18007fb5d  call    WPP_SF_s
0x18007fb62  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007fb69  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18007fb6e  call    _CxxThrowException_0
0x18007fb74  lea     rax, WPP_GLOBAL_Control
0x18007fb7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fb82  cmp     rcx, rax
0x18007fb85  jz      short loc_18007FBAB
0x18007fb87  test    byte ptr [rcx+1Ch], 1
0x18007fb8b  jz      short loc_18007FBAB
0x18007fb8d  cmp     byte ptr [rcx+19h], 2
0x18007fb91  jb      short loc_18007FBAB
0x18007fb93  mov     edx, 233h
0x18007fb98  mov     r9d, edi
0x18007fb9b  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007fba2  mov     rcx, [rcx+10h]
0x18007fba6  call    WPP_SF_d
0x18007fbab  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18007fbb2  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18007fbb7  call    _CxxThrowException_0
0x18007fbbd  lea     r8, aExtendedstatus; "__ExtendedStatus"
0x18007fbc4  mov     esi, 8
0x18007fbc9  mov     edx, esi
0x18007fbcb  lea     rcx, [rsp+400h+var_3B8]
0x18007fbd0  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x18007fbd6  nop
0x18007fbd7  xor     r9d, r9d
0x18007fbda  lea     r8, [rsp+400h+var_3B8]
0x18007fbdf  lea     rdx, aClass_0; "__CLASS"
0x18007fbe6  mov     rcx, rbx
0x18007fbe9  call    cs:__imp_?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetPropValue(ushort const *,CVar *,long)
0x18007fbef  mov     edi, eax
0x18007fbf1  test    eax, eax
0x18007fbf3  jns     loc_18007FCA9
0x18007fbf9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007fbff  lea     edx, [rsi-0Ah]
0x18007fc02  mov     rcx, rax
0x18007fc05  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007fc0b  cmp     edi, 80041006h
0x18007fc11  jnz     short loc_18007FC60
0x18007fc13  lea     rax, WPP_GLOBAL_Control
0x18007fc1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fc21  cmp     rcx, rax
0x18007fc24  jz      short loc_18007FC4E
0x18007fc26  test    byte ptr [rcx+1Ch], 1
0x18007fc2a  jz      short loc_18007FC4E
0x18007fc2c  cmp     byte ptr [rcx+19h], 2
0x18007fc30  jb      short loc_18007FC4E
0x18007fc32  mov     edx, 234h
0x18007fc37  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007fc3e  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007fc45  mov     rcx, [rcx+10h]
0x18007fc49  call    WPP_SF_s
0x18007fc4e  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007fc55  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18007fc5a  call    _CxxThrowException_0
0x18007fc60  lea     rax, WPP_GLOBAL_Control
0x18007fc67  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fc6e  cmp     rcx, rax
0x18007fc71  jz      short loc_18007FC97
0x18007fc73  test    byte ptr [rcx+1Ch], 1
0x18007fc77  jz      short loc_18007FC97
0x18007fc79  cmp     byte ptr [rcx+19h], 2
0x18007fc7d  jb      short loc_18007FC97
0x18007fc7f  mov     edx, 235h
0x18007fc84  mov     r9d, edi
0x18007fc87  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007fc8e  mov     rcx, [rcx+10h]
0x18007fc92  call    WPP_SF_d
0x18007fc97  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18007fc9e  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18007fca3  call    _CxxThrowException_0
0x18007fca9  lea     rcx, [rsp+400h+var_3D8]
0x18007fcae  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18007fcb4  nop
0x18007fcb5  lea     rcx, [rsp+400h+var_3D8]
0x18007fcba  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x18007fcc0  mov     r9d, esi
0x18007fcc3  lea     r8, [rsp+400h+var_3D8]
0x18007fcc8  lea     rdx, aProvidername; "ProviderName"
0x18007fccf  mov     rcx, rbx
0x18007fcd2  call    cs:__imp_?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetPropValue(ushort const *,CVar *,long)
0x18007fcd8  mov     edi, eax
0x18007fcda  test    eax, eax
0x18007fcdc  jns     loc_18007FD94
0x18007fce2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007fce8  mov     edx, 0FFFFFFFEh
0x18007fced  mov     rcx, rax
0x18007fcf0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007fcf6  cmp     edi, 80041006h
0x18007fcfc  jnz     short loc_18007FD4B
0x18007fcfe  lea     rax, WPP_GLOBAL_Control
0x18007fd05  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fd0c  cmp     rcx, rax
0x18007fd0f  jz      short loc_18007FD39
0x18007fd11  test    byte ptr [rcx+1Ch], 1
0x18007fd15  jz      short loc_18007FD39
0x18007fd17  cmp     byte ptr [rcx+19h], 2
0x18007fd1b  jb      short loc_18007FD39
0x18007fd1d  mov     edx, 236h
0x18007fd22  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007fd29  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007fd30  mov     rcx, [rcx+10h]
0x18007fd34  call    WPP_SF_s
0x18007fd39  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007fd40  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18007fd45  call    _CxxThrowException_0
0x18007fd4b  lea     rax, WPP_GLOBAL_Control
0x18007fd52  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fd59  cmp     rcx, rax
0x18007fd5c  jz      short loc_18007FD82
0x18007fd5e  test    byte ptr [rcx+1Ch], 1
0x18007fd62  jz      short loc_18007FD82
0x18007fd64  cmp     byte ptr [rcx+19h], 2
0x18007fd68  jb      short loc_18007FD82
0x18007fd6a  mov     edx, 237h
0x18007fd6f  mov     r9d, edi
0x18007fd72  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007fd79  mov     rcx, [rcx+10h]
0x18007fd7d  call    WPP_SF_d
0x18007fd82  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18007fd89  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18007fd8e  call    _CxxThrowException_0
0x18007fd94  mov     r9d, esi
0x18007fd97  lea     r8, [rsp+400h+var_3D8]
0x18007fd9c  lea     rdx, aOperation; "Operation"
0x18007fda3  mov     rcx, rbx
0x18007fda6  call    cs:__imp_?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetPropValue(ushort const *,CVar *,long)
0x18007fdac  mov     edi, eax
0x18007fdae  test    eax, eax
0x18007fdb0  jns     loc_18007FE68
0x18007fdb6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007fdbc  mov     edx, 0FFFFFFFEh
0x18007fdc1  mov     rcx, rax
0x18007fdc4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007fdca  cmp     edi, 80041006h
0x18007fdd0  jnz     short loc_18007FE1F
0x18007fdd2  lea     rax, WPP_GLOBAL_Control
0x18007fdd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fde0  cmp     rcx, rax
0x18007fde3  jz      short loc_18007FE0D
0x18007fde5  test    byte ptr [rcx+1Ch], 1
0x18007fde9  jz      short loc_18007FE0D
0x18007fdeb  cmp     byte ptr [rcx+19h], 2
0x18007fdef  jb      short loc_18007FE0D
0x18007fdf1  mov     edx, 238h
0x18007fdf6  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007fdfd  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007fe04  mov     rcx, [rcx+10h]
0x18007fe08  call    WPP_SF_s
0x18007fe0d  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007fe14  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18007fe19  call    _CxxThrowException_0
0x18007fe1f  lea     rax, WPP_GLOBAL_Control
0x18007fe26  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fe2d  cmp     rcx, rax
0x18007fe30  jz      short loc_18007FE56
0x18007fe32  test    byte ptr [rcx+1Ch], 1
0x18007fe36  jz      short loc_18007FE56
0x18007fe38  cmp     byte ptr [rcx+19h], 2
0x18007fe3c  jb      short loc_18007FE56
0x18007fe3e  mov     edx, 239h
0x18007fe43  mov     r9d, edi
0x18007fe46  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007fe4d  mov     rcx, [rcx+10h]
0x18007fe51  call    WPP_SF_d
0x18007fe56  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18007fe5d  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18007fe62  call    _CxxThrowException_0
0x18007fe68  mov     r9d, esi
0x18007fe6b  lea     r8, [rsp+400h+var_3D8]
0x18007fe70  lea     rdx, aParameterinfo; "ParameterInfo"
0x18007fe77  mov     rcx, rbx
0x18007fe7a  call    cs:__imp_?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetPropValue(ushort const *,CVar *,long)
0x18007fe80  mov     edi, eax
0x18007fe82  test    eax, eax
0x18007fe84  jns     loc_18007FF3C
0x18007fe8a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007fe90  mov     edx, 0FFFFFFFEh
0x18007fe95  mov     rcx, rax
0x18007fe98  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007fe9e  cmp     edi, 80041006h
0x18007fea4  jnz     short loc_18007FEF3
0x18007fea6  lea     rax, WPP_GLOBAL_Control
0x18007fead  mov     rcx, cs:WPP_GLOBAL_Control
0x18007feb4  cmp     rcx, rax
0x18007feb7  jz      short loc_18007FEE1
0x18007feb9  test    byte ptr [rcx+1Ch], 1
0x18007febd  jz      short loc_18007FEE1
0x18007febf  cmp     byte ptr [rcx+19h], 2
0x18007fec3  jb      short loc_18007FEE1
0x18007fec5  mov     edx, 23Ah
0x18007feca  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007fed1  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007fed8  mov     rcx, [rcx+10h]
0x18007fedc  call    WPP_SF_s
0x18007fee1  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007fee8  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18007feed  call    _CxxThrowException_0
0x18007fef3  lea     rax, WPP_GLOBAL_Control
0x18007fefa  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ff01  cmp     rcx, rax
0x18007ff04  jz      short loc_18007FF2A
0x18007ff06  test    byte ptr [rcx+1Ch], 1
0x18007ff0a  jz      short loc_18007FF2A
0x18007ff0c  cmp     byte ptr [rcx+19h], 2
0x18007ff10  jb      short loc_18007FF2A
0x18007ff12  mov     edx, 23Bh
0x18007ff17  mov     r9d, edi
0x18007ff1a  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007ff21  mov     rcx, [rcx+10h]
0x18007ff25  call    WPP_SF_d
0x18007ff2a  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18007ff31  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18007ff36  call    _CxxThrowException_0
0x18007ff3c  mov     r9d, esi
0x18007ff3f  lea     r8, [rsp+400h+var_3D8]
0x18007ff44  lea     rdx, aDescription; "Description"
0x18007ff4b  mov     rcx, rbx
0x18007ff4e  call    cs:__imp_?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetPropValue(ushort const *,CVar *,long)
0x18007ff54  mov     ebx, eax
0x18007ff56  test    eax, eax
0x18007ff58  jns     loc_180080010
0x18007ff5e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007ff64  mov     edx, 0FFFFFFFEh
0x18007ff69  mov     rcx, rax
0x18007ff6c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007ff72  cmp     ebx, 80041006h
0x18007ff78  jnz     short loc_18007FFC7
0x18007ff7a  lea     rax, WPP_GLOBAL_Control
0x18007ff81  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ff88  cmp     rcx, rax
0x18007ff8b  jz      short loc_18007FFB5
0x18007ff8d  test    byte ptr [rcx+1Ch], 1
0x18007ff91  jz      short loc_18007FFB5
0x18007ff93  cmp     byte ptr [rcx+19h], 2
0x18007ff97  jb      short loc_18007FFB5
0x18007ff99  mov     edx, 23Ch
0x18007ff9e  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007ffa5  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007ffac  mov     rcx, [rcx+10h]
0x18007ffb0  call    WPP_SF_s
0x18007ffb5  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18007ffbc  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18007ffc1  call    _CxxThrowException_0
0x18007ffc7  lea     rax, WPP_GLOBAL_Control
0x18007ffce  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ffd5  cmp     rcx, rax
0x18007ffd8  jz      short loc_18007FFFE
0x18007ffda  test    byte ptr [rcx+1Ch], 1
0x18007ffde  jz      short loc_18007FFFE
0x18007ffe0  cmp     byte ptr [rcx+19h], 2
0x18007ffe4  jb      short loc_18007FFFE
0x18007ffe6  mov     edx, 23Dh
0x18007ffeb  mov     r9d, ebx
0x18007ffee  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18007fff5  mov     rcx, [rcx+10h]
0x18007fff9  call    WPP_SF_d
0x18007fffe  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
  ... truncated ...
```
