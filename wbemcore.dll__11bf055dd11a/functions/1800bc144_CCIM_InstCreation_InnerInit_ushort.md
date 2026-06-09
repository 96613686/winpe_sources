# CCIM_InstCreation::InnerInit(ushort *)

- ea: `0x1800bc144`
- end: `0x1800bc489`
- name: `?InnerInit@CCIM_InstCreation@@QEAAXPEAG@Z`
- size: `837`
- prototype: `void __fastcall(CCIM_InstCreation *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800b40c4`

## callees

- `0x18008846c`
- `0x18008a658`
- `0x1800bc144`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800bc20e`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800bc20e`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc172`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc2a3`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc335`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc3c7`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc172`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc2a3`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc335`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc3c7`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc1fd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc44d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc458`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc463`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc46e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc1fd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc44d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc458`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc463`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc46e`
- `wbemcomn!GetMemLogObject` at `0x1800bc199`
- `wbemcomn!GetMemLogObject` at `0x1800bc233`
- `wbemcomn!GetMemLogObject` at `0x1800bc2c5`
- `wbemcomn!GetMemLogObject` at `0x1800bc357`
- `wbemcomn!GetMemLogObject` at `0x1800bc3e9`
- `wbemcomn!GetMemLogObject` at `0x1800bc199`
- `wbemcomn!GetMemLogObject` at `0x1800bc233`
- `wbemcomn!GetMemLogObject` at `0x1800bc2c5`
- `wbemcomn!GetMemLogObject` at `0x1800bc357`
- `wbemcomn!GetMemLogObject` at `0x1800bc3e9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc1a7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc241`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc2d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc365`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc3f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc1a7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc241`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc2d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc365`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc3f7`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc229`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc2bb`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc34d`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc3df`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc229`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc2bb`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc34d`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc3df`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc18a`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc18a`

## string_xrefs

- `0x1800bc343`: `UMLPackagePath`
- `0x1800bc3b7`: `CIM_InstCreation notifies when a new instance is created.`

## pseudocode

```c
void __fastcall CCIM_InstCreation::InnerInit(CCIM_InstCreation *this, unsigned __int16 *a2)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  CMemoryLog *v6; // rax
  CMemoryLog *v7; // rax
  _BYTE v8[32]; // [rsp+28h] [rbp-49h] BYREF
  _BYTE v9[32]; // [rsp+48h] [rbp-29h] BYREF
  _BYTE v10[32]; // [rsp+68h] [rbp-9h] BYREF
  _BYTE v11[32]; // [rsp+88h] [rbp+17h] BYREF
  _BYTE v12[32]; // [rsp+A8h] [rbp+37h] BYREF
  unsigned __int16 *pExceptionObject; // [rsp+E0h] [rbp+6Fh] BYREF

  pExceptionObject = a2;
  CVar::CVar((CVar *)v8, 8, L"CIM_InstCreation");
  if ( CWbemClass::SetPropValue(this, L"__CLASS", (struct CVar *)v8, 0) == -2147217402 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        724,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v8);
  CVar::CVar((CVar *)v12, -1, 11);
  if ( CWbemClass::SetQualifier(this, L"Indication", (struct CVar *)v12, 19) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        725,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v11, 8, L"2.6.0");
  if ( CWbemClass::SetQualifier(this, L"Version", (struct CVar *)v11, 0) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        726,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v10, 8, L"CIM::Event");
  if ( CWbemClass::SetQualifier(this, L"UMLPackagePath", (struct CVar *)v10, 0) == -2147217402 )
  {
    v6 = GetMemLogObject();
    CMemoryLog::Write(v6, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        727,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, 8, L"CIM_InstCreation notifies when a new instance is created.");
  if ( CWbemClass::SetQualifier(this, L"Description", (struct CVar *)v9, 0) == -2147217402 )
  {
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        728,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v9);
  CVar::~CVar((CVar *)v10);
  CVar::~CVar((CVar *)v11);
  CVar::~CVar((CVar *)v12);
}

```

## disassembly

```asm
0x1800bc144  mov     rax, rsp
0x1800bc147  mov     [rax+8], rbx
0x1800bc14b  mov     [rax+18h], rdi
0x1800bc14f  mov     [rax+10h], rdx
0x1800bc153  push    rbp
0x1800bc154  lea     rbp, [rax-5Fh]
0x1800bc158  sub     rsp, 0C0h
0x1800bc15f  mov     rbx, rcx
0x1800bc162  lea     r8, aCimInstcreatio; "CIM_InstCreation"
0x1800bc169  mov     edx, 8
0x1800bc16e  lea     rcx, [rbp+57h+var_A0]
0x1800bc172  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800bc178  nop
0x1800bc179  xor     r9d, r9d
0x1800bc17c  lea     r8, [rbp+57h+var_A0]
0x1800bc180  lea     rdx, aClass_0; "__CLASS"
0x1800bc187  mov     rcx, rbx
0x1800bc18a  call    cs:__imp_?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetPropValue(ushort const *,CVar *,long)
0x1800bc190  mov     edi, 80041006h
0x1800bc195  cmp     eax, edi
0x1800bc197  jnz     short loc_1800BC1F9
0x1800bc199  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bc19f  mov     edx, 0FFFFFFFEh
0x1800bc1a4  mov     rcx, rax
0x1800bc1a7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bc1ad  lea     rax, WPP_GLOBAL_Control
0x1800bc1b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc1bb  cmp     rcx, rax
0x1800bc1be  jz      short loc_1800BC1E8
0x1800bc1c0  test    byte ptr [rcx+1Ch], 1
0x1800bc1c4  jz      short loc_1800BC1E8
0x1800bc1c6  cmp     byte ptr [rcx+19h], 2
0x1800bc1ca  jb      short loc_1800BC1E8
0x1800bc1cc  mov     edx, 2D4h
0x1800bc1d1  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bc1d8  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bc1df  mov     rcx, [rcx+10h]
0x1800bc1e3  call    WPP_SF_s
0x1800bc1e8  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bc1ef  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bc1f3  call    _CxxThrowException_0
0x1800bc1f9  lea     rcx, [rbp+57h+var_A0]
0x1800bc1fd  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bc203  or      edx, 0FFFFFFFFh
0x1800bc206  lea     r8d, [rdx+0Ch]
0x1800bc20a  lea     rcx, [rbp+57h+var_20]
0x1800bc20e  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800bc214  nop
0x1800bc215  mov     r9d, 13h
0x1800bc21b  lea     r8, [rbp+57h+var_20]
0x1800bc21f  lea     rdx, aIndication; "Indication"
0x1800bc226  mov     rcx, rbx
0x1800bc229  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x1800bc22f  cmp     eax, edi
0x1800bc231  jnz     short loc_1800BC293
0x1800bc233  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bc239  mov     edx, 0FFFFFFFEh
0x1800bc23e  mov     rcx, rax
0x1800bc241  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bc247  lea     rax, WPP_GLOBAL_Control
0x1800bc24e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc255  cmp     rcx, rax
0x1800bc258  jz      short loc_1800BC282
0x1800bc25a  test    byte ptr [rcx+1Ch], 1
0x1800bc25e  jz      short loc_1800BC282
0x1800bc260  cmp     byte ptr [rcx+19h], 2
0x1800bc264  jb      short loc_1800BC282
0x1800bc266  mov     edx, 2D5h
0x1800bc26b  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bc272  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bc279  mov     rcx, [rcx+10h]
0x1800bc27d  call    WPP_SF_s
0x1800bc282  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bc289  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bc28d  call    _CxxThrowException_0
0x1800bc293  lea     r8, a260; "2.6.0"
0x1800bc29a  mov     edx, 8
0x1800bc29f  lea     rcx, [rbp+57h+var_40]
0x1800bc2a3  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800bc2a9  nop
0x1800bc2aa  xor     r9d, r9d
0x1800bc2ad  lea     r8, [rbp+57h+var_40]
0x1800bc2b1  lea     rdx, aVersion; "Version"
0x1800bc2b8  mov     rcx, rbx
0x1800bc2bb  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x1800bc2c1  cmp     eax, edi
0x1800bc2c3  jnz     short loc_1800BC325
0x1800bc2c5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bc2cb  mov     edx, 0FFFFFFFEh
0x1800bc2d0  mov     rcx, rax
0x1800bc2d3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bc2d9  lea     rax, WPP_GLOBAL_Control
0x1800bc2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc2e7  cmp     rcx, rax
0x1800bc2ea  jz      short loc_1800BC314
0x1800bc2ec  test    byte ptr [rcx+1Ch], 1
0x1800bc2f0  jz      short loc_1800BC314
0x1800bc2f2  cmp     byte ptr [rcx+19h], 2
0x1800bc2f6  jb      short loc_1800BC314
0x1800bc2f8  mov     edx, 2D6h
0x1800bc2fd  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bc304  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bc30b  mov     rcx, [rcx+10h]
0x1800bc30f  call    WPP_SF_s
0x1800bc314  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bc31b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bc31f  call    _CxxThrowException_0
0x1800bc325  lea     r8, aCimEvent; "CIM::Event"
0x1800bc32c  mov     edx, 8
0x1800bc331  lea     rcx, [rbp+57h+var_60]
0x1800bc335  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800bc33b  nop
0x1800bc33c  xor     r9d, r9d
0x1800bc33f  lea     r8, [rbp+57h+var_60]
0x1800bc343  lea     rdx, aUmlpackagepath; "UMLPackagePath"
0x1800bc34a  mov     rcx, rbx
0x1800bc34d  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x1800bc353  cmp     eax, edi
0x1800bc355  jnz     short loc_1800BC3B7
0x1800bc357  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bc35d  mov     edx, 0FFFFFFFEh
0x1800bc362  mov     rcx, rax
0x1800bc365  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bc36b  lea     rax, WPP_GLOBAL_Control
0x1800bc372  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc379  cmp     rcx, rax
0x1800bc37c  jz      short loc_1800BC3A6
0x1800bc37e  test    byte ptr [rcx+1Ch], 1
0x1800bc382  jz      short loc_1800BC3A6
0x1800bc384  cmp     byte ptr [rcx+19h], 2
0x1800bc388  jb      short loc_1800BC3A6
0x1800bc38a  mov     edx, 2D7h
0x1800bc38f  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bc396  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bc39d  mov     rcx, [rcx+10h]
0x1800bc3a1  call    WPP_SF_s
0x1800bc3a6  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bc3ad  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bc3b1  call    _CxxThrowException_0
0x1800bc3b7  lea     r8, aCimInstcreatio_0; "CIM_InstCreation notifies when a new in"...
0x1800bc3be  mov     edx, 8
0x1800bc3c3  lea     rcx, [rbp+57h+var_80]
0x1800bc3c7  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800bc3cd  nop
0x1800bc3ce  xor     r9d, r9d
0x1800bc3d1  lea     r8, [rbp+57h+var_80]
0x1800bc3d5  lea     rdx, aDescription; "Description"
0x1800bc3dc  mov     rcx, rbx
0x1800bc3df  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x1800bc3e5  cmp     eax, edi
0x1800bc3e7  jnz     short loc_1800BC449
0x1800bc3e9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bc3ef  mov     edx, 0FFFFFFFEh
0x1800bc3f4  mov     rcx, rax
0x1800bc3f7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bc3fd  lea     rax, WPP_GLOBAL_Control
0x1800bc404  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc40b  cmp     rcx, rax
0x1800bc40e  jz      short loc_1800BC438
0x1800bc410  test    byte ptr [rcx+1Ch], 1
0x1800bc414  jz      short loc_1800BC438
0x1800bc416  cmp     byte ptr [rcx+19h], 2
0x1800bc41a  jb      short loc_1800BC438
0x1800bc41c  mov     edx, 2D8h
0x1800bc421  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bc428  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bc42f  mov     rcx, [rcx+10h]
0x1800bc433  call    WPP_SF_s
0x1800bc438  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bc43f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bc443  call    _CxxThrowException_0
0x1800bc449  lea     rcx, [rbp+57h+var_80]
0x1800bc44d  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bc453  nop
0x1800bc454  lea     rcx, [rbp+57h+var_60]
0x1800bc458  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bc45e  nop
0x1800bc45f  lea     rcx, [rbp+57h+var_40]
0x1800bc463  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bc469  nop
0x1800bc46a  lea     rcx, [rbp+57h+var_20]
0x1800bc46e  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bc474  lea     r11, [rsp+0C0h+var_s0]
0x1800bc47c  mov     rbx, [r11+10h]
0x1800bc480  mov     rdi, [r11+20h]
0x1800bc484  mov     rsp, r11
0x1800bc487  pop     rbp
0x1800bc488  retn
```
