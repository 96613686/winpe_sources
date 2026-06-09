# CCIM_InstDeletion::InnerInit(ushort *)

- ea: `0x1800bc490`
- end: `0x1800bc7d5`
- name: `?InnerInit@CCIM_InstDeletion@@QEAAXPEAG@Z`
- size: `837`
- prototype: `void __fastcall(CCIM_InstDeletion *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800b41a8`

## callees

- `0x18008846c`
- `0x18008a658`
- `0x1800bc490`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800bc55a`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800bc55a`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc4be`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc5ef`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc681`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc713`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc4be`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc5ef`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc681`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800bc713`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc549`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc799`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc7a4`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc7af`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc7ba`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc549`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc799`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc7a4`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc7af`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800bc7ba`
- `wbemcomn!GetMemLogObject` at `0x1800bc4e5`
- `wbemcomn!GetMemLogObject` at `0x1800bc57f`
- `wbemcomn!GetMemLogObject` at `0x1800bc611`
- `wbemcomn!GetMemLogObject` at `0x1800bc6a3`
- `wbemcomn!GetMemLogObject` at `0x1800bc735`
- `wbemcomn!GetMemLogObject` at `0x1800bc4e5`
- `wbemcomn!GetMemLogObject` at `0x1800bc57f`
- `wbemcomn!GetMemLogObject` at `0x1800bc611`
- `wbemcomn!GetMemLogObject` at `0x1800bc6a3`
- `wbemcomn!GetMemLogObject` at `0x1800bc735`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc4f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc58d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc61f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc6b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc743`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc4f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc58d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc61f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc6b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bc743`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc575`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc607`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc699`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc72b`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc575`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc607`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc699`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc72b`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc4d6`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800bc4d6`

## string_xrefs

- `0x1800bc68f`: `UMLPackagePath`
- `0x1800bc703`: `CIM_InstDeletion notifies when an existing instance is deleted.`

## pseudocode

```c
void __fastcall CCIM_InstDeletion::InnerInit(CCIM_InstDeletion *this, unsigned __int16 *a2)
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
  CVar::CVar((CVar *)v8, 8, L"CIM_InstDeletion");
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
        730,
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
        731,
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
        732,
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
        733,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, 8, L"CIM_InstDeletion notifies when an existing instance is deleted.");
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
        734,
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
0x1800bc490  mov     rax, rsp
0x1800bc493  mov     [rax+8], rbx
0x1800bc497  mov     [rax+18h], rdi
0x1800bc49b  mov     [rax+10h], rdx
0x1800bc49f  push    rbp
0x1800bc4a0  lea     rbp, [rax-5Fh]
0x1800bc4a4  sub     rsp, 0C0h
0x1800bc4ab  mov     rbx, rcx
0x1800bc4ae  lea     r8, aCimInstdeletio; "CIM_InstDeletion"
0x1800bc4b5  mov     edx, 8
0x1800bc4ba  lea     rcx, [rbp+57h+var_A0]
0x1800bc4be  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800bc4c4  nop
0x1800bc4c5  xor     r9d, r9d
0x1800bc4c8  lea     r8, [rbp+57h+var_A0]
0x1800bc4cc  lea     rdx, aClass_0; "__CLASS"
0x1800bc4d3  mov     rcx, rbx
0x1800bc4d6  call    cs:__imp_?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetPropValue(ushort const *,CVar *,long)
0x1800bc4dc  mov     edi, 80041006h
0x1800bc4e1  cmp     eax, edi
0x1800bc4e3  jnz     short loc_1800BC545
0x1800bc4e5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bc4eb  mov     edx, 0FFFFFFFEh
0x1800bc4f0  mov     rcx, rax
0x1800bc4f3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bc4f9  lea     rax, WPP_GLOBAL_Control
0x1800bc500  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc507  cmp     rcx, rax
0x1800bc50a  jz      short loc_1800BC534
0x1800bc50c  test    byte ptr [rcx+1Ch], 1
0x1800bc510  jz      short loc_1800BC534
0x1800bc512  cmp     byte ptr [rcx+19h], 2
0x1800bc516  jb      short loc_1800BC534
0x1800bc518  mov     edx, 2DAh
0x1800bc51d  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bc524  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bc52b  mov     rcx, [rcx+10h]
0x1800bc52f  call    WPP_SF_s
0x1800bc534  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bc53b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bc53f  call    _CxxThrowException_0
0x1800bc545  lea     rcx, [rbp+57h+var_A0]
0x1800bc549  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bc54f  or      edx, 0FFFFFFFFh
0x1800bc552  lea     r8d, [rdx+0Ch]
0x1800bc556  lea     rcx, [rbp+57h+var_20]
0x1800bc55a  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800bc560  nop
0x1800bc561  mov     r9d, 13h
0x1800bc567  lea     r8, [rbp+57h+var_20]
0x1800bc56b  lea     rdx, aIndication; "Indication"
0x1800bc572  mov     rcx, rbx
0x1800bc575  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x1800bc57b  cmp     eax, edi
0x1800bc57d  jnz     short loc_1800BC5DF
0x1800bc57f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bc585  mov     edx, 0FFFFFFFEh
0x1800bc58a  mov     rcx, rax
0x1800bc58d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bc593  lea     rax, WPP_GLOBAL_Control
0x1800bc59a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc5a1  cmp     rcx, rax
0x1800bc5a4  jz      short loc_1800BC5CE
0x1800bc5a6  test    byte ptr [rcx+1Ch], 1
0x1800bc5aa  jz      short loc_1800BC5CE
0x1800bc5ac  cmp     byte ptr [rcx+19h], 2
0x1800bc5b0  jb      short loc_1800BC5CE
0x1800bc5b2  mov     edx, 2DBh
0x1800bc5b7  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bc5be  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bc5c5  mov     rcx, [rcx+10h]
0x1800bc5c9  call    WPP_SF_s
0x1800bc5ce  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bc5d5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bc5d9  call    _CxxThrowException_0
0x1800bc5df  lea     r8, a260; "2.6.0"
0x1800bc5e6  mov     edx, 8
0x1800bc5eb  lea     rcx, [rbp+57h+var_40]
0x1800bc5ef  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800bc5f5  nop
0x1800bc5f6  xor     r9d, r9d
0x1800bc5f9  lea     r8, [rbp+57h+var_40]
0x1800bc5fd  lea     rdx, aVersion; "Version"
0x1800bc604  mov     rcx, rbx
0x1800bc607  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x1800bc60d  cmp     eax, edi
0x1800bc60f  jnz     short loc_1800BC671
0x1800bc611  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bc617  mov     edx, 0FFFFFFFEh
0x1800bc61c  mov     rcx, rax
0x1800bc61f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bc625  lea     rax, WPP_GLOBAL_Control
0x1800bc62c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc633  cmp     rcx, rax
0x1800bc636  jz      short loc_1800BC660
0x1800bc638  test    byte ptr [rcx+1Ch], 1
0x1800bc63c  jz      short loc_1800BC660
0x1800bc63e  cmp     byte ptr [rcx+19h], 2
0x1800bc642  jb      short loc_1800BC660
0x1800bc644  mov     edx, 2DCh
0x1800bc649  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bc650  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bc657  mov     rcx, [rcx+10h]
0x1800bc65b  call    WPP_SF_s
0x1800bc660  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bc667  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bc66b  call    _CxxThrowException_0
0x1800bc671  lea     r8, aCimEvent; "CIM::Event"
0x1800bc678  mov     edx, 8
0x1800bc67d  lea     rcx, [rbp+57h+var_60]
0x1800bc681  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800bc687  nop
0x1800bc688  xor     r9d, r9d
0x1800bc68b  lea     r8, [rbp+57h+var_60]
0x1800bc68f  lea     rdx, aUmlpackagepath; "UMLPackagePath"
0x1800bc696  mov     rcx, rbx
0x1800bc699  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x1800bc69f  cmp     eax, edi
0x1800bc6a1  jnz     short loc_1800BC703
0x1800bc6a3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bc6a9  mov     edx, 0FFFFFFFEh
0x1800bc6ae  mov     rcx, rax
0x1800bc6b1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bc6b7  lea     rax, WPP_GLOBAL_Control
0x1800bc6be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc6c5  cmp     rcx, rax
0x1800bc6c8  jz      short loc_1800BC6F2
0x1800bc6ca  test    byte ptr [rcx+1Ch], 1
0x1800bc6ce  jz      short loc_1800BC6F2
0x1800bc6d0  cmp     byte ptr [rcx+19h], 2
0x1800bc6d4  jb      short loc_1800BC6F2
0x1800bc6d6  mov     edx, 2DDh
0x1800bc6db  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bc6e2  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bc6e9  mov     rcx, [rcx+10h]
0x1800bc6ed  call    WPP_SF_s
0x1800bc6f2  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bc6f9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bc6fd  call    _CxxThrowException_0
0x1800bc703  lea     r8, aCimInstdeletio_0; "CIM_InstDeletion notifies when an exist"...
0x1800bc70a  mov     edx, 8
0x1800bc70f  lea     rcx, [rbp+57h+var_80]
0x1800bc713  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800bc719  nop
0x1800bc71a  xor     r9d, r9d
0x1800bc71d  lea     r8, [rbp+57h+var_80]
0x1800bc721  lea     rdx, aDescription; "Description"
0x1800bc728  mov     rcx, rbx
0x1800bc72b  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x1800bc731  cmp     eax, edi
0x1800bc733  jnz     short loc_1800BC795
0x1800bc735  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bc73b  mov     edx, 0FFFFFFFEh
0x1800bc740  mov     rcx, rax
0x1800bc743  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bc749  lea     rax, WPP_GLOBAL_Control
0x1800bc750  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc757  cmp     rcx, rax
0x1800bc75a  jz      short loc_1800BC784
0x1800bc75c  test    byte ptr [rcx+1Ch], 1
0x1800bc760  jz      short loc_1800BC784
0x1800bc762  cmp     byte ptr [rcx+19h], 2
0x1800bc766  jb      short loc_1800BC784
0x1800bc768  mov     edx, 2DEh
0x1800bc76d  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800bc774  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800bc77b  mov     rcx, [rcx+10h]
0x1800bc77f  call    WPP_SF_s
0x1800bc784  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800bc78b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bc78f  call    _CxxThrowException_0
0x1800bc795  lea     rcx, [rbp+57h+var_80]
0x1800bc799  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bc79f  nop
0x1800bc7a0  lea     rcx, [rbp+57h+var_60]
0x1800bc7a4  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bc7aa  nop
0x1800bc7ab  lea     rcx, [rbp+57h+var_40]
0x1800bc7af  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bc7b5  nop
0x1800bc7b6  lea     rcx, [rbp+57h+var_20]
0x1800bc7ba  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800bc7c0  lea     r11, [rsp+0C0h+var_s0]
0x1800bc7c8  mov     rbx, [r11+10h]
0x1800bc7cc  mov     rdi, [r11+20h]
0x1800bc7d0  mov     rsp, r11
0x1800bc7d3  pop     rbp
0x1800bc7d4  retn
```
