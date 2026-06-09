# CThisNamespaceClass::Init(void)

- ea: `0x18006a8f4`
- end: `0x18006abc3`
- name: `?Init@CThisNamespaceClass@@QEAAXXZ`
- size: `719`
- prototype: `void __fastcall(CThisNamespaceClass *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`
- `0x18007bbec`

## callees

- `0x18006a8f4`
- `0x18006abcc`
- `0x180085c70`
- `0x18008846c`
- `0x18008a658`
- `0x1800ce510`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x18006aaea`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x18006aaea`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x18006a9c3`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x18006a9c3`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18006aa58`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18006aa58`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18006aa4c`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18006aa4c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006ab76`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006ab82`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006ab8e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006ab76`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006ab82`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006ab8e`
- `wbemcomn!GetMemLogObject` at `0x18006a951`
- `wbemcomn!GetMemLogObject` at `0x18006a9e6`
- `wbemcomn!GetMemLogObject` at `0x18006aa7d`
- `wbemcomn!GetMemLogObject` at `0x18006ab10`
- `wbemcomn!GetMemLogObject` at `0x18006a951`
- `wbemcomn!GetMemLogObject` at `0x18006a9e6`
- `wbemcomn!GetMemLogObject` at `0x18006aa7d`
- `wbemcomn!GetMemLogObject` at `0x18006ab10`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006a95f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006a9f4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006aa8b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006ab1e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006a95f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006a9f4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006aa8b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006ab1e`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18006ab06`
- `FastProx!?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18006ab06`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18006a9dc`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18006aa73`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18006a9dc`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x18006aa73`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x18006ab99`
- `FastProx!??1CWbemClass@@UEAA@XZ` at `0x18006ab99`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x18006a942`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x18006a942`

## string_xrefs

- `0x18006aa69`: `SECURITY_DESCRIPTOR`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CThisNamespaceClass::Init(CThisNamespaceClass *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  char pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v7[32]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v8[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v9[40]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v10[864]; // [rsp+90h] [rbp-70h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v10);
  CSystemClass::Init((CSystemClass *)v10);
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
        10,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, 8, L"__thisNAMESPACE");
  if ( CWbemClass::SetPropValue(this, L"__CLASS", (struct CVar *)v9, 0) == -2147217402 )
  {
    v3 = GetMemLogObject();
    CMemoryLog::Write(v3, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v7);
  CVar::SetAsNull((CVar *)v7);
  if ( CWbemClass::SetPropValue(this, L"SECURITY_DESCRIPTOR", (struct CVar *)v7, 8209) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8, -1, 11);
  if ( CWbemClass::SetQualifier(this, L"singleton", (struct CVar *)v8, 19) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v8);
  CVar::~CVar((CVar *)v7);
  CVar::~CVar((CVar *)v9);
  CWbemClass::~CWbemClass((CWbemClass *)v10);
}

```

## disassembly

```asm
0x18006a8f4  mov     [rsp-8+arg_8], rbx
0x18006a8f9  mov     [rsp-8+arg_10], rdi
0x18006a8fe  push    rbp
0x18006a8ff  lea     rbp, [rsp-300h]
0x18006a907  sub     rsp, 400h
0x18006a90e  mov     rax, cs:__security_cookie
0x18006a915  xor     rax, rsp
0x18006a918  mov     [rbp+300h+var_10], rax
0x18006a91f  mov     rbx, rcx
0x18006a922  lea     rcx, [rbp+300h+var_370]; this
0x18006a926  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x18006a92b  nop
0x18006a92c  lea     rcx, [rbp+300h+var_370]; this
0x18006a930  call    ?Init@CSystemClass@@QEAAXXZ; CSystemClass::Init(void)
0x18006a935  xor     r9d, r9d
0x18006a938  xor     r8d, r8d
0x18006a93b  lea     rdx, [rbp+300h+var_370]
0x18006a93f  mov     rcx, rbx
0x18006a942  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x18006a948  mov     edi, 80041006h
0x18006a94d  cmp     eax, edi
0x18006a94f  jnz     short loc_18006A9B2
0x18006a951  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006a957  mov     edx, 0FFFFFFFEh
0x18006a95c  mov     rcx, rax
0x18006a95f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006a965  lea     rax, WPP_GLOBAL_Control
0x18006a96c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a973  cmp     rcx, rax
0x18006a976  jz      short loc_18006A9A0
0x18006a978  test    byte ptr [rcx+1Ch], 1
0x18006a97c  jz      short loc_18006A9A0
0x18006a97e  cmp     byte ptr [rcx+19h], 2
0x18006a982  jb      short loc_18006A9A0
0x18006a984  mov     edx, 0Ah
0x18006a989  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18006a990  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18006a997  mov     rcx, [rcx+10h]
0x18006a99b  call    WPP_SF_s
0x18006a9a0  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18006a9a7  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18006a9ac  call    _CxxThrowException_0
0x18006a9b2  lea     r8, aThisnamespace_1; "__thisNAMESPACE"
0x18006a9b9  mov     edx, 8
0x18006a9be  lea     rcx, [rsp+400h+var_398]
0x18006a9c3  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x18006a9c9  nop
0x18006a9ca  xor     r9d, r9d
0x18006a9cd  lea     r8, [rsp+400h+var_398]
0x18006a9d2  lea     rdx, aClass_0; "__CLASS"
0x18006a9d9  mov     rcx, rbx
0x18006a9dc  call    cs:__imp_?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetPropValue(ushort const *,CVar *,long)
0x18006a9e2  cmp     eax, edi
0x18006a9e4  jnz     short loc_18006AA47
0x18006a9e6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006a9ec  mov     edx, 0FFFFFFFEh
0x18006a9f1  mov     rcx, rax
0x18006a9f4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006a9fa  lea     rax, WPP_GLOBAL_Control
0x18006aa01  mov     rcx, cs:WPP_GLOBAL_Control
0x18006aa08  cmp     rcx, rax
0x18006aa0b  jz      short loc_18006AA35
0x18006aa0d  test    byte ptr [rcx+1Ch], 1
0x18006aa11  jz      short loc_18006AA35
0x18006aa13  cmp     byte ptr [rcx+19h], 2
0x18006aa17  jb      short loc_18006AA35
0x18006aa19  mov     edx, 0Bh
0x18006aa1e  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18006aa25  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18006aa2c  mov     rcx, [rcx+10h]
0x18006aa30  call    WPP_SF_s
0x18006aa35  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18006aa3c  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18006aa41  call    _CxxThrowException_0
0x18006aa47  lea     rcx, [rsp+400h+var_3D8]
0x18006aa4c  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18006aa52  nop
0x18006aa53  lea     rcx, [rsp+400h+var_3D8]
0x18006aa58  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x18006aa5e  mov     r9d, 2011h
0x18006aa64  lea     r8, [rsp+400h+var_3D8]
0x18006aa69  lea     rdx, aSecurityDescri; "SECURITY_DESCRIPTOR"
0x18006aa70  mov     rcx, rbx
0x18006aa73  call    cs:__imp_?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetPropValue(ushort const *,CVar *,long)
0x18006aa79  cmp     eax, edi
0x18006aa7b  jnz     short loc_18006AADE
0x18006aa7d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006aa83  mov     edx, 0FFFFFFFEh
0x18006aa88  mov     rcx, rax
0x18006aa8b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006aa91  lea     rax, WPP_GLOBAL_Control
0x18006aa98  mov     rcx, cs:WPP_GLOBAL_Control
0x18006aa9f  cmp     rcx, rax
0x18006aaa2  jz      short loc_18006AACC
0x18006aaa4  test    byte ptr [rcx+1Ch], 1
0x18006aaa8  jz      short loc_18006AACC
0x18006aaaa  cmp     byte ptr [rcx+19h], 2
0x18006aaae  jb      short loc_18006AACC
0x18006aab0  mov     edx, 0Ch
0x18006aab5  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18006aabc  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18006aac3  mov     rcx, [rcx+10h]
0x18006aac7  call    WPP_SF_s
0x18006aacc  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18006aad3  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18006aad8  call    _CxxThrowException_0
0x18006aade  or      edx, 0FFFFFFFFh
0x18006aae1  lea     r8d, [rdx+0Ch]
0x18006aae5  lea     rcx, [rsp+400h+var_3B8]
0x18006aaea  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x18006aaf0  nop
0x18006aaf1  mov     r9d, 13h
0x18006aaf7  lea     r8, [rsp+400h+var_3B8]
0x18006aafc  lea     rdx, aSingleton; "singleton"
0x18006ab03  mov     rcx, rbx
0x18006ab06  call    cs:__imp_?SetQualifier@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetQualifier(ushort const *,CVar *,long)
0x18006ab0c  cmp     eax, edi
0x18006ab0e  jnz     short loc_18006AB71
0x18006ab10  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006ab16  mov     edx, 0FFFFFFFEh
0x18006ab1b  mov     rcx, rax
0x18006ab1e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006ab24  lea     rax, WPP_GLOBAL_Control
0x18006ab2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ab32  cmp     rcx, rax
0x18006ab35  jz      short loc_18006AB5F
0x18006ab37  test    byte ptr [rcx+1Ch], 1
0x18006ab3b  jz      short loc_18006AB5F
0x18006ab3d  cmp     byte ptr [rcx+19h], 2
0x18006ab41  jb      short loc_18006AB5F
0x18006ab43  mov     edx, 0Dh
0x18006ab48  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18006ab4f  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x18006ab56  mov     rcx, [rcx+10h]
0x18006ab5a  call    WPP_SF_s
0x18006ab5f  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18006ab66  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18006ab6b  call    _CxxThrowException_0
0x18006ab71  lea     rcx, [rsp+400h+var_3B8]
0x18006ab76  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18006ab7c  nop
0x18006ab7d  lea     rcx, [rsp+400h+var_3D8]
0x18006ab82  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18006ab88  nop
0x18006ab89  lea     rcx, [rsp+400h+var_398]
0x18006ab8e  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18006ab94  nop
0x18006ab95  lea     rcx, [rbp+300h+var_370]
0x18006ab99  call    cs:__imp_??1CWbemClass@@UEAA@XZ; CWbemClass::~CWbemClass(void)
0x18006ab9f  mov     rcx, [rbp+300h+var_10]
0x18006aba6  xor     rcx, rsp; StackCookie
0x18006aba9  call    __security_check_cookie
0x18006abae  lea     r11, [rsp+400h+var_s0]
0x18006abb6  mov     rbx, [r11+18h]
0x18006abba  mov     rdi, [r11+20h]
0x18006abbe  mov     rsp, r11
0x18006abc1  pop     rbp
0x18006abc2  retn
```
