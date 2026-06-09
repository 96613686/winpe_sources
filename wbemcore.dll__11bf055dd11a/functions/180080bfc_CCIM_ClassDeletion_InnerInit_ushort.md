# CCIM_ClassDeletion::InnerInit(ushort *)

- ea: `0x180080bfc`
- end: `0x180080f41`
- name: `?InnerInit@CCIM_ClassDeletion@@QEAAXPEAG@Z`
- size: `837`
- prototype: `void __fastcall(CCIM_ClassDeletion *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180080b18`

## callees

- `0x180080bfc`
- `0x18008846c`
- `0x18008a658`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x180080cc6`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x180080cc6`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x180080c2a`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x180080d5b`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x180080ded`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x180080e7f`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x180080c2a`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x180080d5b`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x180080ded`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x180080e7f`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180080cb5`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180080f05`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180080f10`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180080f1b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180080f26`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180080cb5`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180080f05`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180080f10`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180080f1b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180080f26`
- `wbemcomn!GetMemLogObject` at `0x180080c51`
- `wbemcomn!GetMemLogObject` at `0x180080ceb`
- `wbemcomn!GetMemLogObject` at `0x180080d7d`
- `wbemcomn!GetMemLogObject` at `0x180080e0f`
- `wbemcomn!GetMemLogObject` at `0x180080ea1`
- `wbemcomn!GetMemLogObject` at `0x180080c51`
- `wbemcomn!GetMemLogObject` at `0x180080ceb`
- `wbemcomn!GetMemLogObject` at `0x180080d7d`
- `wbemcomn!GetMemLogObject` at `0x180080e0f`
- `wbemcomn!GetMemLogObject` at `0x180080ea1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080c5f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080cf9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080d8b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080e1d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080eaf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080c5f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080cf9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080d8b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080e1d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080eaf`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x180080ce1`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x180080d73`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x180080e05`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x180080e97`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x180080ce1`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x180080d73`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x180080e05`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x180080e97`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x180080c42`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x180080c42`

## string_xrefs

- `0x180080dfb`: `UMLPackagePath`
- `0x180080e6f`: `CIM_ClassDeletion notifies when a class is deleted from the schema.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CCIM_ClassDeletion::InnerInit(CCIM_ClassDeletion *this, unsigned __int16 *a2)
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
  CVar::CVar((CVar *)v8, 8, L"CIM_ClassDeletion");
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
        709,
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
        710,
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
        711,
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
        712,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, 8, L"CIM_ClassDeletion notifies when a class is deleted from the schema.");
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
        713,
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
0x180080bfc  mov     rax, rsp
0x180080bff  mov     [rax+8], rbx
0x180080c03  mov     [rax+18h], rdi
0x180080c07  mov     [rax+10h], rdx
0x180080c0b  push    rbp
0x180080c0c  lea     rbp, [rax-5Fh]
0x180080c10  sub     rsp, 0C0h
0x180080c17  mov     rbx, rcx
0x180080c1a  lea     r8, aCimClassdeleti_0; "CIM_ClassDeletion"
0x180080c21  mov     edx, 8
0x180080c26  lea     rcx, [rbp+57h+var_A0]
0x180080c2a  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x180080c30  nop
0x180080c31  xor     r9d, r9d
0x180080c34  lea     r8, [rbp+57h+var_A0]
0x180080c38  lea     rdx, aClass_0; "__CLASS"
0x180080c3f  mov     rcx, rbx
0x180080c42  call    cs:__imp_?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetPropValue(ushort const *,CVar *,long)
0x180080c48  mov     edi, 80041006h
0x180080c4d  cmp     eax, edi
0x180080c4f  jnz     short loc_180080CB1
0x180080c51  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180080c57  mov     edx, 0FFFFFFFEh
0x180080c5c  mov     rcx, rax
0x180080c5f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180080c65  lea     rax, WPP_GLOBAL_Control
0x180080c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180080c73  cmp     rcx, rax
0x180080c76  jz      short loc_180080CA0
0x180080c78  test    byte ptr [rcx+1Ch], 1
0x180080c7c  jz      short loc_180080CA0
0x180080c7e  cmp     byte ptr [rcx+19h], 2
0x180080c82  jb      short loc_180080CA0
0x180080c84  mov     edx, 2C5h
0x180080c89  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180080c90  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x180080c97  mov     rcx, [rcx+10h]
0x180080c9b  call    WPP_SF_s
0x180080ca0  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180080ca7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180080cab  call    _CxxThrowException_0
0x180080cb1  lea     rcx, [rbp+57h+var_A0]
0x180080cb5  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180080cbb  or      edx, 0FFFFFFFFh
0x180080cbe  lea     r8d, [rdx+0Ch]
0x180080cc2  lea     rcx, [rbp+57h+var_20]
0x180080cc6  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x180080ccc  nop
0x180080ccd  mov     r9d, 13h
0x180080cd3  lea     r8, [rbp+57h+var_20]
0x180080cd7  lea     rdx, aIndication; "Indication"
0x180080cde  mov     rcx, rbx
0x180080ce1  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x180080ce7  cmp     eax, edi
0x180080ce9  jnz     short loc_180080D4B
0x180080ceb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180080cf1  mov     edx, 0FFFFFFFEh
0x180080cf6  mov     rcx, rax
0x180080cf9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180080cff  lea     rax, WPP_GLOBAL_Control
0x180080d06  mov     rcx, cs:WPP_GLOBAL_Control
0x180080d0d  cmp     rcx, rax
0x180080d10  jz      short loc_180080D3A
0x180080d12  test    byte ptr [rcx+1Ch], 1
0x180080d16  jz      short loc_180080D3A
0x180080d18  cmp     byte ptr [rcx+19h], 2
0x180080d1c  jb      short loc_180080D3A
0x180080d1e  mov     edx, 2C6h
0x180080d23  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180080d2a  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x180080d31  mov     rcx, [rcx+10h]
0x180080d35  call    WPP_SF_s
0x180080d3a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180080d41  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180080d45  call    _CxxThrowException_0
0x180080d4b  lea     r8, a260; "2.6.0"
0x180080d52  mov     edx, 8
0x180080d57  lea     rcx, [rbp+57h+var_40]
0x180080d5b  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x180080d61  nop
0x180080d62  xor     r9d, r9d
0x180080d65  lea     r8, [rbp+57h+var_40]
0x180080d69  lea     rdx, aVersion; "Version"
0x180080d70  mov     rcx, rbx
0x180080d73  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x180080d79  cmp     eax, edi
0x180080d7b  jnz     short loc_180080DDD
0x180080d7d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180080d83  mov     edx, 0FFFFFFFEh
0x180080d88  mov     rcx, rax
0x180080d8b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180080d91  lea     rax, WPP_GLOBAL_Control
0x180080d98  mov     rcx, cs:WPP_GLOBAL_Control
0x180080d9f  cmp     rcx, rax
0x180080da2  jz      short loc_180080DCC
0x180080da4  test    byte ptr [rcx+1Ch], 1
0x180080da8  jz      short loc_180080DCC
0x180080daa  cmp     byte ptr [rcx+19h], 2
0x180080dae  jb      short loc_180080DCC
0x180080db0  mov     edx, 2C7h
0x180080db5  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180080dbc  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x180080dc3  mov     rcx, [rcx+10h]
0x180080dc7  call    WPP_SF_s
0x180080dcc  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180080dd3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180080dd7  call    _CxxThrowException_0
0x180080ddd  lea     r8, aCimEvent; "CIM::Event"
0x180080de4  mov     edx, 8
0x180080de9  lea     rcx, [rbp+57h+var_60]
0x180080ded  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x180080df3  nop
0x180080df4  xor     r9d, r9d
0x180080df7  lea     r8, [rbp+57h+var_60]
0x180080dfb  lea     rdx, aUmlpackagepath; "UMLPackagePath"
0x180080e02  mov     rcx, rbx
0x180080e05  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x180080e0b  cmp     eax, edi
0x180080e0d  jnz     short loc_180080E6F
0x180080e0f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180080e15  mov     edx, 0FFFFFFFEh
0x180080e1a  mov     rcx, rax
0x180080e1d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180080e23  lea     rax, WPP_GLOBAL_Control
0x180080e2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180080e31  cmp     rcx, rax
0x180080e34  jz      short loc_180080E5E
0x180080e36  test    byte ptr [rcx+1Ch], 1
0x180080e3a  jz      short loc_180080E5E
0x180080e3c  cmp     byte ptr [rcx+19h], 2
0x180080e40  jb      short loc_180080E5E
0x180080e42  mov     edx, 2C8h
0x180080e47  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180080e4e  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x180080e55  mov     rcx, [rcx+10h]
0x180080e59  call    WPP_SF_s
0x180080e5e  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180080e65  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180080e69  call    _CxxThrowException_0
0x180080e6f  lea     r8, aCimClassdeleti; "CIM_ClassDeletion notifies when a class"...
0x180080e76  mov     edx, 8
0x180080e7b  lea     rcx, [rbp+57h+var_80]
0x180080e7f  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x180080e85  nop
0x180080e86  xor     r9d, r9d
0x180080e89  lea     r8, [rbp+57h+var_80]
0x180080e8d  lea     rdx, aDescription; "Description"
0x180080e94  mov     rcx, rbx
0x180080e97  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x180080e9d  cmp     eax, edi
0x180080e9f  jnz     short loc_180080F01
0x180080ea1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180080ea7  mov     edx, 0FFFFFFFEh
0x180080eac  mov     rcx, rax
0x180080eaf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180080eb5  lea     rax, WPP_GLOBAL_Control
0x180080ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x180080ec3  cmp     rcx, rax
0x180080ec6  jz      short loc_180080EF0
0x180080ec8  test    byte ptr [rcx+1Ch], 1
0x180080ecc  jz      short loc_180080EF0
0x180080ece  cmp     byte ptr [rcx+19h], 2
0x180080ed2  jb      short loc_180080EF0
0x180080ed4  mov     edx, 2C9h
0x180080ed9  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180080ee0  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x180080ee7  mov     rcx, [rcx+10h]
0x180080eeb  call    WPP_SF_s
0x180080ef0  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180080ef7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180080efb  call    _CxxThrowException_0
0x180080f01  lea     rcx, [rbp+57h+var_80]
0x180080f05  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180080f0b  nop
0x180080f0c  lea     rcx, [rbp+57h+var_60]
0x180080f10  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180080f16  nop
0x180080f17  lea     rcx, [rbp+57h+var_40]
0x180080f1b  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180080f21  nop
0x180080f22  lea     rcx, [rbp+57h+var_20]
0x180080f26  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180080f2c  lea     r11, [rsp+0C0h+var_s0]
0x180080f34  mov     rbx, [r11+10h]
0x180080f38  mov     rdi, [r11+20h]
0x180080f3c  mov     rsp, r11
0x180080f3f  pop     rbp
0x180080f40  retn
```
