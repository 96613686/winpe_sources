# CCIM_ClassCreation::InnerInit(ushort *)

- ea: `0x1800bb848`
- end: `0x1800bbb8d`
- name: `?InnerInit@CCIM_ClassCreation@@QEAAXPEAG@Z`
- size: `837`
- prototype: `void __fastcall(CCIM_ClassCreation *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800b3efc`

## callees

- `0x18008846c`
- `0x18008a658`
- `0x1800bb848`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800bb912`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800bb912`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bb876`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bb9a7`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bba39`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bbacb`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bb876`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bb9a7`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bba39`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bbacb`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb901`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bbb51`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bbb5c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bbb67`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bbb72`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bb901`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bbb51`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bbb5c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bbb67`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bbb72`
- `wbemcomn!GetMemLogObject` at `0x1800bb89d`
- `wbemcomn!GetMemLogObject` at `0x1800bb937`
- `wbemcomn!GetMemLogObject` at `0x1800bb9c9`
- `wbemcomn!GetMemLogObject` at `0x1800bba5b`
- `wbemcomn!GetMemLogObject` at `0x1800bbaed`
- `wbemcomn!GetMemLogObject` at `0x1800bb89d`
- `wbemcomn!GetMemLogObject` at `0x1800bb937`
- `wbemcomn!GetMemLogObject` at `0x1800bb9c9`
- `wbemcomn!GetMemLogObject` at `0x1800bba5b`
- `wbemcomn!GetMemLogObject` at `0x1800bbaed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb8ab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb945`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb9d7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bba69`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bbafb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb8ab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb945`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bb9d7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bba69`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bbafb`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bb92d`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bb9bf`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bba51`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bbae3`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bb92d`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bb9bf`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bba51`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bbae3`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bb88e`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bb88e`

## string_xrefs

- `0x1800bba47`: `UMLPackagePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CCIM_ClassCreation::InnerInit(CCIM_ClassCreation *this, unsigned __int16 *a2)
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
  CVar::CVar((CVar *)v8, 8, L"CIM_ClassCreation");
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
        703,
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
        704,
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
        705,
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
        706,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, 8, L"CIM_ClassCreation notifies when a new class is defined in the schema.");
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
        707,
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
0x1800bb848  mov     rax, rsp
0x1800bb84b  mov     [rax+8], rbx
0x1800bb84f  mov     [rax+18h], rdi
0x1800bb853  mov     [rax+10h], rdx
0x1800bb857  push    rbp
0x1800bb858  lea     rbp, [rax-5Fh]
0x1800bb85c  sub     rsp, 0C0h
0x1800bb863  mov     rbx, rcx
0x1800bb866  lea     r8, aCimClasscreati; "CIM_ClassCreation"
0x1800bb86d  mov     edx, 8
0x1800bb872  lea     rcx, [rbp+57h+var_A0]
0x1800bb876  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800bb87c  nop
0x1800bb87d  xor     r9d, r9d
0x1800bb880  lea     r8, [rbp+57h+var_A0]
0x1800bb884  lea     rdx, aClass_0; "__CLASS"
0x1800bb88b  mov     rcx, rbx
0x1800bb88e  call    cs:__imp_?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetPropValue(ushort const *,CVar *,long)
0x1800bb894  mov     edi, 80041006h
0x1800bb899  cmp     eax, edi
0x1800bb89b  jnz     short loc_1800BB8FD
0x1800bb89d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bb8a3  mov     edx, 0FFFFFFFEh
0x1800bb8a8  mov     rcx, rax
0x1800bb8ab  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bb8b1  lea     rax, WPP_GLOBAL_Control
0x1800bb8b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb8bf  cmp     rcx, rax
0x1800bb8c2  jz      short loc_1800BB8EC
0x1800bb8c4  test    byte ptr [rcx+1Ch], 1
0x1800bb8c8  jz      short loc_1800BB8EC
0x1800bb8ca  cmp     byte ptr [rcx+19h], 2
0x1800bb8ce  jb      short loc_1800BB8EC
0x1800bb8d0  mov     edx, 2BFh
0x1800bb8d5  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bb8dc  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bb8e3  mov     rcx, [rcx+10h]
0x1800bb8e7  call    WPP_SF_s
0x1800bb8ec  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bb8f3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bb8f7  call    _CxxThrowException_0
0x1800bb8fd  lea     rcx, [rbp+57h+var_A0]
0x1800bb901  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bb907  or      edx, 0FFFFFFFFh
0x1800bb90a  lea     r8d, [rdx+0Ch]
0x1800bb90e  lea     rcx, [rbp+57h+var_20]
0x1800bb912  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800bb918  nop
0x1800bb919  mov     r9d, 13h
0x1800bb91f  lea     r8, [rbp+57h+var_20]
0x1800bb923  lea     rdx, aIndication; "Indication"
0x1800bb92a  mov     rcx, rbx
0x1800bb92d  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x1800bb933  cmp     eax, edi
0x1800bb935  jnz     short loc_1800BB997
0x1800bb937  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bb93d  mov     edx, 0FFFFFFFEh
0x1800bb942  mov     rcx, rax
0x1800bb945  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bb94b  lea     rax, WPP_GLOBAL_Control
0x1800bb952  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb959  cmp     rcx, rax
0x1800bb95c  jz      short loc_1800BB986
0x1800bb95e  test    byte ptr [rcx+1Ch], 1
0x1800bb962  jz      short loc_1800BB986
0x1800bb964  cmp     byte ptr [rcx+19h], 2
0x1800bb968  jb      short loc_1800BB986
0x1800bb96a  mov     edx, 2C0h
0x1800bb96f  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bb976  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bb97d  mov     rcx, [rcx+10h]
0x1800bb981  call    WPP_SF_s
0x1800bb986  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bb98d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bb991  call    _CxxThrowException_0
0x1800bb997  lea     r8, a260; "2.6.0"
0x1800bb99e  mov     edx, 8
0x1800bb9a3  lea     rcx, [rbp+57h+var_40]
0x1800bb9a7  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800bb9ad  nop
0x1800bb9ae  xor     r9d, r9d
0x1800bb9b1  lea     r8, [rbp+57h+var_40]
0x1800bb9b5  lea     rdx, aVersion; "Version"
0x1800bb9bc  mov     rcx, rbx
0x1800bb9bf  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x1800bb9c5  cmp     eax, edi
0x1800bb9c7  jnz     short loc_1800BBA29
0x1800bb9c9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bb9cf  mov     edx, 0FFFFFFFEh
0x1800bb9d4  mov     rcx, rax
0x1800bb9d7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bb9dd  lea     rax, WPP_GLOBAL_Control
0x1800bb9e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb9eb  cmp     rcx, rax
0x1800bb9ee  jz      short loc_1800BBA18
0x1800bb9f0  test    byte ptr [rcx+1Ch], 1
0x1800bb9f4  jz      short loc_1800BBA18
0x1800bb9f6  cmp     byte ptr [rcx+19h], 2
0x1800bb9fa  jb      short loc_1800BBA18
0x1800bb9fc  mov     edx, 2C1h
0x1800bba01  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bba08  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bba0f  mov     rcx, [rcx+10h]
0x1800bba13  call    WPP_SF_s
0x1800bba18  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bba1f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bba23  call    _CxxThrowException_0
0x1800bba29  lea     r8, aCimEvent; "CIM::Event"
0x1800bba30  mov     edx, 8
0x1800bba35  lea     rcx, [rbp+57h+var_60]
0x1800bba39  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800bba3f  nop
0x1800bba40  xor     r9d, r9d
0x1800bba43  lea     r8, [rbp+57h+var_60]
0x1800bba47  lea     rdx, aUmlpackagepath; "UMLPackagePath"
0x1800bba4e  mov     rcx, rbx
0x1800bba51  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x1800bba57  cmp     eax, edi
0x1800bba59  jnz     short loc_1800BBABB
0x1800bba5b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bba61  mov     edx, 0FFFFFFFEh
0x1800bba66  mov     rcx, rax
0x1800bba69  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bba6f  lea     rax, WPP_GLOBAL_Control
0x1800bba76  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bba7d  cmp     rcx, rax
0x1800bba80  jz      short loc_1800BBAAA
0x1800bba82  test    byte ptr [rcx+1Ch], 1
0x1800bba86  jz      short loc_1800BBAAA
0x1800bba88  cmp     byte ptr [rcx+19h], 2
0x1800bba8c  jb      short loc_1800BBAAA
0x1800bba8e  mov     edx, 2C2h
0x1800bba93  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bba9a  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bbaa1  mov     rcx, [rcx+10h]
0x1800bbaa5  call    WPP_SF_s
0x1800bbaaa  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bbab1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bbab5  call    _CxxThrowException_0
0x1800bbabb  lea     r8, aCimClasscreati_0; "CIM_ClassCreation notifies when a new c"...
0x1800bbac2  mov     edx, 8
0x1800bbac7  lea     rcx, [rbp+57h+var_80]
0x1800bbacb  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800bbad1  nop
0x1800bbad2  xor     r9d, r9d
0x1800bbad5  lea     r8, [rbp+57h+var_80]
0x1800bbad9  lea     rdx, aDescription; "Description"
0x1800bbae0  mov     rcx, rbx
0x1800bbae3  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x1800bbae9  cmp     eax, edi
0x1800bbaeb  jnz     short loc_1800BBB4D
0x1800bbaed  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bbaf3  mov     edx, 0FFFFFFFEh
0x1800bbaf8  mov     rcx, rax
0x1800bbafb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bbb01  lea     rax, WPP_GLOBAL_Control
0x1800bbb08  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bbb0f  cmp     rcx, rax
0x1800bbb12  jz      short loc_1800BBB3C
0x1800bbb14  test    byte ptr [rcx+1Ch], 1
0x1800bbb18  jz      short loc_1800BBB3C
0x1800bbb1a  cmp     byte ptr [rcx+19h], 2
0x1800bbb1e  jb      short loc_1800BBB3C
0x1800bbb20  mov     edx, 2C3h
0x1800bbb25  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bbb2c  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bbb33  mov     rcx, [rcx+10h]
0x1800bbb37  call    WPP_SF_s
0x1800bbb3c  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bbb43  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bbb47  call    _CxxThrowException_0
0x1800bbb4d  lea     rcx, [rbp+57h+var_80]
0x1800bbb51  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bbb57  nop
0x1800bbb58  lea     rcx, [rbp+57h+var_60]
0x1800bbb5c  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bbb62  nop
0x1800bbb63  lea     rcx, [rbp+57h+var_40]
0x1800bbb67  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bbb6d  nop
0x1800bbb6e  lea     rcx, [rbp+57h+var_20]
0x1800bbb72  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bbb78  lea     r11, [rsp+0C0h+var_s0]
0x1800bbb80  mov     rbx, [r11+10h]
0x1800bbb84  mov     rdi, [r11+20h]
0x1800bbb88  mov     rsp, r11
0x1800bbb8b  pop     rbp
0x1800bbb8c  retn
```
