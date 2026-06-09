# CCIMOMIdentificationClass::Init(void)

- ea: `0x1800b3a1c`
- end: `0x1800b3ef3`
- name: `?Init@CCIMOMIdentificationClass@@QEAAXXZ`
- size: `1239`
- prototype: `void __fastcall(CCIMOMIdentificationClass *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180093ec4`

## callees

- `0x18006abcc`
- `0x180085c70`
- `0x180086358`
- `0x18008846c`
- `0x18008a658`
- `0x1800a3fc4`
- `0x1800b3a1c`
- `0x1800bd010`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b3e10`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b3e10`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b3ae6`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b3cf2`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b3ae6`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b3cf2`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x1800b3b82`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x1800b3b82`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1800b3ebd`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1800b3ebd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b3ea5`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b3eb1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b3ec8`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b3ea5`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b3eb1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b3ec8`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x1800b3b89`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x1800b3b89`
- `wbemcomn!GetMemLogObject` at `0x1800b3a73`
- `wbemcomn!GetMemLogObject` at `0x1800b3b11`
- `wbemcomn!GetMemLogObject` at `0x1800b3bbb`
- `wbemcomn!GetMemLogObject` at `0x1800b3c44`
- `wbemcomn!GetMemLogObject` at `0x1800b3d1e`
- `wbemcomn!GetMemLogObject` at `0x1800b3da3`
- `wbemcomn!GetMemLogObject` at `0x1800b3e3f`
- `wbemcomn!GetMemLogObject` at `0x1800b3a73`
- `wbemcomn!GetMemLogObject` at `0x1800b3b11`
- `wbemcomn!GetMemLogObject` at `0x1800b3bbb`
- `wbemcomn!GetMemLogObject` at `0x1800b3c44`
- `wbemcomn!GetMemLogObject` at `0x1800b3d1e`
- `wbemcomn!GetMemLogObject` at `0x1800b3da3`
- `wbemcomn!GetMemLogObject` at `0x1800b3e3f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3a81`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3b1d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3bc9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3c52`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3d2c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3db1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3e4d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3a81`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3b1d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3bc9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3c52`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3d2c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3db1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3e4d`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b3a64`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b3a64`

## string_xrefs

- `0x1800b3d04`: `VersionUsedToCreateDB`
- `0x1800b3cac`: `Working Directory`
- `0x1800b3cc4`: `SetupDate`
- `0x1800b3c29`: `SetupDateTime`
- `0x1800b3cbd`: `SetupDateTime`
- `0x1800b3ba7`: `WorkingDirectory`
- `0x1800b3ca5`: `WorkingDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CCIMOMIdentificationClass::Init(CCIMOMIdentificationClass *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  unsigned __int16 *v5; // rdx
  unsigned __int16 *v6; // rcx
  unsigned int v7; // r9d
  CMemoryLog *v8; // rax
  CMemoryLog *v9; // rax
  CMemoryLog *v10; // rax
  CMemoryLog *v11; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[24]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v14[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v17[864]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v18[264]; // [rsp+410h] [rbp+310h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v17);
  CSystemClass::Init((CSystemClass *)v17);
  if ( CWbemClass::CreateDerivedClass(this, (struct CWbemClass *)v17, 0, 0) == -2147217402 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        143,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v16, 8, L"__CIMOMIdentification");
  if ( (*(unsigned int (__fastcall **)(CCIMOMIdentificationClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
         this,
         L"__CLASS",
         v16,
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
        144,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  Registry::Registry((Registry *)v13, L"Software\\Microsoft\\WBEM\\CIMOM", 1u);
  if ( (unsigned __int8)CWbemInstallObject::IsOffline() )
  {
    if ( (*(unsigned int (__fastcall **)(CCIMOMIdentificationClass *, const unsigned __int16 *, _QWORD, _QWORD, int))(*(_QWORD *)this + 40LL))(
           this,
           L"WorkingDirectory",
           0,
           0,
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
          145,
          WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
    if ( (*(unsigned int (__fastcall **)(CCIMOMIdentificationClass *, const unsigned __int16 *, _QWORD, _QWORD, int))(*(_QWORD *)this + 40LL))(
           this,
           L"SetupDateTime",
           0,
           0,
           8) == -2147217402 )
    {
      v8 = GetMemLogObject();
      CMemoryLog::Write(v8, -2);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          146,
          WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
  }
  else
  {
    CCIMOMIdentificationClass::SetPropFromReg(this, (struct Registry *)v13, L"Working Directory", L"WorkingDirectory");
    CCIMOMIdentificationClass::SetPropFromReg(this, (struct Registry *)v13, L"SetupDate", L"SetupDateTime");
  }
  ConfigMgr::GetDllVersion(v6, v5, v18, v7);
  CVar::CVar((CVar *)v15, 8, v18);
  if ( (*(unsigned int (__fastcall **)(CCIMOMIdentificationClass *, const unsigned __int16 *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"VersionUsedToCreateDB",
         v15,
         8) == -2147217402 )
  {
    v9 = GetMemLogObject();
    CMemoryLog::Write(v9, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        147,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( (*(unsigned int (__fastcall **)(CCIMOMIdentificationClass *, const unsigned __int16 *, _QWORD, _QWORD, int))(*(_QWORD *)this + 40LL))(
         this,
         L"VersionCurrentlyRunning",
         0,
         0,
         8) == -2147217402 )
  {
    v10 = GetMemLogObject();
    CMemoryLog::Write(v10, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        148,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v14, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CCIMOMIdentificationClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 984LL))(
         this,
         L"singleton",
         v14,
         19) == -2147217402 )
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        149,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v14);
  CVar::~CVar((CVar *)v15);
  Registry::~Registry((Registry *)v13);
  CVar::~CVar((CVar *)v16);
  CSystemEventClass::~CSystemEventClass((CSystemEventClass *)v17);
}

```

## disassembly

```asm
0x1800b3a1c  push    rbp
0x1800b3a1e  push    rbx
0x1800b3a1f  push    rsi
0x1800b3a20  push    rdi
0x1800b3a21  lea     rbp, [rsp-538h]
0x1800b3a29  sub     rsp, 638h
0x1800b3a30  mov     rax, cs:__security_cookie
0x1800b3a37  xor     rax, rsp
0x1800b3a3a  mov     [rbp+550h+var_30], rax
0x1800b3a41  mov     rbx, rcx
0x1800b3a44  lea     rcx, [rbp+550h+var_5A0]; this
0x1800b3a48  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800b3a4d  nop
0x1800b3a4e  lea     rcx, [rbp+550h+var_5A0]; this
0x1800b3a52  call    ?Init@CSystemClass@@QEAAXXZ; CSystemClass::Init(void)
0x1800b3a57  xor     r9d, r9d
0x1800b3a5a  xor     r8d, r8d
0x1800b3a5d  lea     rdx, [rbp+550h+var_5A0]
0x1800b3a61  mov     rcx, rbx
0x1800b3a64  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800b3a6a  mov     edi, 80041006h
0x1800b3a6f  cmp     eax, edi
0x1800b3a71  jnz     short loc_1800B3AD4
0x1800b3a73  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b3a79  mov     edx, 0FFFFFFFEh
0x1800b3a7e  mov     rcx, rax
0x1800b3a81  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b3a87  lea     rax, WPP_GLOBAL_Control
0x1800b3a8e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3a95  cmp     rcx, rax
0x1800b3a98  jz      short loc_1800B3AC2
0x1800b3a9a  test    byte ptr [rcx+1Ch], 1
0x1800b3a9e  jz      short loc_1800B3AC2
0x1800b3aa0  cmp     byte ptr [rcx+19h], 2
0x1800b3aa4  jb      short loc_1800B3AC2
0x1800b3aa6  mov     edx, 8Fh
0x1800b3aab  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b3ab2  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b3ab9  mov     rcx, [rcx+10h]
0x1800b3abd  call    WPP_SF_s
0x1800b3ac2  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b3ac9  lea     rcx, [rsp+650h+pExceptionObject]; pExceptionObject
0x1800b3ace  call    _CxxThrowException_0
0x1800b3ad4  lea     r8, aCimomidentific_0; "__CIMOMIdentification"
0x1800b3adb  mov     esi, 8
0x1800b3ae0  mov     edx, esi
0x1800b3ae2  lea     rcx, [rbp+550h+var_5C0]
0x1800b3ae6  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b3aec  nop
0x1800b3aed  mov     rax, [rbx]
0x1800b3af0  xor     r9d, r9d
0x1800b3af3  lea     r8, [rbp+550h+var_5C0]
0x1800b3af7  lea     rdx, aClass_0; "__CLASS"
0x1800b3afe  mov     rcx, rbx
0x1800b3b01  mov     rax, [rax+368h]
0x1800b3b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3b0d  cmp     eax, edi
0x1800b3b0f  jnz     short loc_1800B3B70
0x1800b3b11  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b3b17  lea     edx, [rsi-0Ah]
0x1800b3b1a  mov     rcx, rax
0x1800b3b1d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b3b23  lea     rax, WPP_GLOBAL_Control
0x1800b3b2a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3b31  cmp     rcx, rax
0x1800b3b34  jz      short loc_1800B3B5E
0x1800b3b36  test    byte ptr [rcx+1Ch], 1
0x1800b3b3a  jz      short loc_1800B3B5E
0x1800b3b3c  cmp     byte ptr [rcx+19h], 2
0x1800b3b40  jb      short loc_1800B3B5E
0x1800b3b42  mov     edx, 90h
0x1800b3b47  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b3b4e  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b3b55  mov     rcx, [rcx+10h]
0x1800b3b59  call    WPP_SF_s
0x1800b3b5e  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b3b65  lea     rcx, [rsp+650h+pExceptionObject]; pExceptionObject
0x1800b3b6a  call    _CxxThrowException_0
0x1800b3b70  mov     r8d, 1
0x1800b3b76  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\WBEM\\CIMOM"
0x1800b3b7d  lea     rcx, [rsp+650h+var_618]
0x1800b3b82  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x1800b3b88  nop
0x1800b3b89  call    cs:__imp_?IsOffline@CWbemInstallObject@@SA_NXZ; CWbemInstallObject::IsOffline(void)
0x1800b3b8f  mov     rcx, rbx; this
0x1800b3b92  test    al, al
0x1800b3b94  jz      loc_1800B3CA5
0x1800b3b9a  mov     rax, [rbx]
0x1800b3b9d  mov     [rsp+650h+var_630], esi
0x1800b3ba1  xor     r9d, r9d
0x1800b3ba4  xor     r8d, r8d
0x1800b3ba7  lea     rdx, aWorkingdirecto; "WorkingDirectory"
0x1800b3bae  mov     rax, [rax+28h]
0x1800b3bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3bb7  cmp     eax, edi
0x1800b3bb9  jnz     short loc_1800B3C1C
0x1800b3bbb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b3bc1  mov     edx, 0FFFFFFFEh
0x1800b3bc6  mov     rcx, rax
0x1800b3bc9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b3bcf  lea     rax, WPP_GLOBAL_Control
0x1800b3bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3bdd  cmp     rcx, rax
0x1800b3be0  jz      short loc_1800B3C0A
0x1800b3be2  test    byte ptr [rcx+1Ch], 1
0x1800b3be6  jz      short loc_1800B3C0A
0x1800b3be8  cmp     byte ptr [rcx+19h], 2
0x1800b3bec  jb      short loc_1800B3C0A
0x1800b3bee  mov     edx, 91h
0x1800b3bf3  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b3bfa  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b3c01  mov     rcx, [rcx+10h]
0x1800b3c05  call    WPP_SF_s
0x1800b3c0a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b3c11  lea     rcx, [rsp+650h+pExceptionObject]; pExceptionObject
0x1800b3c16  call    _CxxThrowException_0
0x1800b3c1c  mov     rax, [rbx]
0x1800b3c1f  mov     [rsp+650h+var_630], esi
0x1800b3c23  xor     r9d, r9d
0x1800b3c26  xor     r8d, r8d
0x1800b3c29  lea     rdx, aSetupdatetime; "SetupDateTime"
0x1800b3c30  mov     rcx, rbx
0x1800b3c33  mov     rax, [rax+28h]
0x1800b3c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3c3c  cmp     eax, edi
0x1800b3c3e  jnz     loc_1800B3CD8
0x1800b3c44  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b3c4a  mov     edx, 0FFFFFFFEh
0x1800b3c4f  mov     rcx, rax
0x1800b3c52  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b3c58  lea     rax, WPP_GLOBAL_Control
0x1800b3c5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3c66  cmp     rcx, rax
0x1800b3c69  jz      short loc_1800B3C93
0x1800b3c6b  test    byte ptr [rcx+1Ch], 1
0x1800b3c6f  jz      short loc_1800B3C93
0x1800b3c71  cmp     byte ptr [rcx+19h], 2
0x1800b3c75  jb      short loc_1800B3C93
0x1800b3c77  mov     edx, 92h
0x1800b3c7c  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b3c83  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b3c8a  mov     rcx, [rcx+10h]
0x1800b3c8e  call    WPP_SF_s
0x1800b3c93  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b3c9a  lea     rcx, [rsp+650h+pExceptionObject]; pExceptionObject
0x1800b3c9f  call    _CxxThrowException_0
0x1800b3ca5  lea     r9, aWorkingdirecto; "WorkingDirectory"
0x1800b3cac  lea     r8, aWorkingDirecto; "Working Directory"
0x1800b3cb3  lea     rdx, [rsp+650h+var_618]; struct Registry *
0x1800b3cb8  call    ?SetPropFromReg@CCIMOMIdentificationClass@@AEAAXPEAVRegistry@@PEAG1@Z; CCIMOMIdentificationClass::SetPropFromReg(Registry *,ushort *,ushort *)
0x1800b3cbd  lea     r9, aSetupdatetime; "SetupDateTime"
0x1800b3cc4  lea     r8, aSetupdate; "SetupDate"
0x1800b3ccb  lea     rdx, [rsp+650h+var_618]; struct Registry *
0x1800b3cd0  mov     rcx, rbx; this
0x1800b3cd3  call    ?SetPropFromReg@CCIMOMIdentificationClass@@AEAAXPEAVRegistry@@PEAG1@Z; CCIMOMIdentificationClass::SetPropFromReg(Registry *,ushort *,ushort *)
0x1800b3cd8  lea     r8, [rbp+550h+var_240]; unsigned __int16 *
0x1800b3cdf  call    ?GetDllVersion@ConfigMgr@@SAHPEAG00K@Z; ConfigMgr::GetDllVersion(ushort *,ushort *,ushort *,ulong)
0x1800b3ce4  lea     r8, [rbp+550h+var_240]
0x1800b3ceb  mov     edx, esi
0x1800b3ced  lea     rcx, [rsp+650h+var_5E0]
0x1800b3cf2  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b3cf8  nop
0x1800b3cf9  mov     rax, [rbx]
0x1800b3cfc  mov     r9d, esi
0x1800b3cff  lea     r8, [rsp+650h+var_5E0]
0x1800b3d04  lea     rdx, aVersionusedtoc; "VersionUsedToCreateDB"
0x1800b3d0b  mov     rcx, rbx
0x1800b3d0e  mov     rax, [rax+368h]
0x1800b3d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3d1a  cmp     eax, edi
0x1800b3d1c  jnz     short loc_1800B3D7F
0x1800b3d1e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b3d24  mov     edx, 0FFFFFFFEh
0x1800b3d29  mov     rcx, rax
0x1800b3d2c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b3d32  lea     rax, WPP_GLOBAL_Control
0x1800b3d39  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3d40  cmp     rcx, rax
0x1800b3d43  jz      short loc_1800B3D6D
0x1800b3d45  test    byte ptr [rcx+1Ch], 1
0x1800b3d49  jz      short loc_1800B3D6D
0x1800b3d4b  cmp     byte ptr [rcx+19h], 2
0x1800b3d4f  jb      short loc_1800B3D6D
0x1800b3d51  mov     edx, 93h
0x1800b3d56  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b3d5d  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b3d64  mov     rcx, [rcx+10h]
0x1800b3d68  call    WPP_SF_s
0x1800b3d6d  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b3d74  lea     rcx, [rsp+650h+pExceptionObject]; pExceptionObject
0x1800b3d79  call    _CxxThrowException_0
0x1800b3d7f  mov     rax, [rbx]
0x1800b3d82  mov     [rsp+650h+var_630], esi
0x1800b3d86  xor     r9d, r9d
0x1800b3d89  xor     r8d, r8d
0x1800b3d8c  lea     rdx, aVersioncurrent; "VersionCurrentlyRunning"
0x1800b3d93  mov     rcx, rbx
0x1800b3d96  mov     rax, [rax+28h]
0x1800b3d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3d9f  cmp     eax, edi
0x1800b3da1  jnz     short loc_1800B3E04
0x1800b3da3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b3da9  mov     edx, 0FFFFFFFEh
0x1800b3dae  mov     rcx, rax
0x1800b3db1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b3db7  lea     rax, WPP_GLOBAL_Control
0x1800b3dbe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3dc5  cmp     rcx, rax
0x1800b3dc8  jz      short loc_1800B3DF2
0x1800b3dca  test    byte ptr [rcx+1Ch], 1
0x1800b3dce  jz      short loc_1800B3DF2
0x1800b3dd0  cmp     byte ptr [rcx+19h], 2
0x1800b3dd4  jb      short loc_1800B3DF2
0x1800b3dd6  mov     edx, 94h
0x1800b3ddb  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b3de2  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b3de9  mov     rcx, [rcx+10h]
0x1800b3ded  call    WPP_SF_s
0x1800b3df2  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b3df9  lea     rcx, [rsp+650h+pExceptionObject]; pExceptionObject
0x1800b3dfe  call    _CxxThrowException_0
0x1800b3e04  or      edx, 0FFFFFFFFh
0x1800b3e07  lea     r8d, [rdx+0Ch]
0x1800b3e0b  lea     rcx, [rsp+650h+var_600]
0x1800b3e10  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800b3e16  nop
0x1800b3e17  mov     rax, [rbx]
0x1800b3e1a  mov     r9d, 13h
0x1800b3e20  lea     r8, [rsp+650h+var_600]
0x1800b3e25  lea     rdx, aSingleton; "singleton"
0x1800b3e2c  mov     rcx, rbx
0x1800b3e2f  mov     rax, [rax+3D8h]
0x1800b3e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e3b  cmp     eax, edi
0x1800b3e3d  jnz     short loc_1800B3EA0
0x1800b3e3f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b3e45  mov     edx, 0FFFFFFFEh
0x1800b3e4a  mov     rcx, rax
0x1800b3e4d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b3e53  lea     rax, WPP_GLOBAL_Control
0x1800b3e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3e61  cmp     rcx, rax
0x1800b3e64  jz      short loc_1800B3E8E
0x1800b3e66  test    byte ptr [rcx+1Ch], 1
0x1800b3e6a  jz      short loc_1800B3E8E
0x1800b3e6c  cmp     byte ptr [rcx+19h], 2
0x1800b3e70  jb      short loc_1800B3E8E
0x1800b3e72  mov     edx, 95h
0x1800b3e77  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b3e7e  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b3e85  mov     rcx, [rcx+10h]
0x1800b3e89  call    WPP_SF_s
0x1800b3e8e  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b3e95  lea     rcx, [rsp+650h+pExceptionObject]; pExceptionObject
0x1800b3e9a  call    _CxxThrowException_0
0x1800b3ea0  lea     rcx, [rsp+650h+var_600]
0x1800b3ea5  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b3eab  nop
0x1800b3eac  lea     rcx, [rsp+650h+var_5E0]
0x1800b3eb1  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b3eb7  nop
0x1800b3eb8  lea     rcx, [rsp+650h+var_618]
0x1800b3ebd  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x1800b3ec3  nop
0x1800b3ec4  lea     rcx, [rbp+550h+var_5C0]
0x1800b3ec8  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b3ece  nop
0x1800b3ecf  lea     rcx, [rbp+550h+var_5A0]; this
0x1800b3ed3  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800b3ed8  mov     rcx, [rbp+550h+var_30]
0x1800b3edf  xor     rcx, rsp; StackCookie
0x1800b3ee2  call    __security_check_cookie
0x1800b3ee7  add     rsp, 638h
0x1800b3eee  pop     rdi
0x1800b3eef  pop     rsi
0x1800b3ef0  pop     rbx
0x1800b3ef1  pop     rbp
0x1800b3ef2  retn
```
