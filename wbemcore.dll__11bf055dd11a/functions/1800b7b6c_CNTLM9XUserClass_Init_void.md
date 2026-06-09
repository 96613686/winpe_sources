# CNTLM9XUserClass::Init(void)

- ea: `0x1800b7b6c`
- end: `0x1800b7fd7`
- name: `?Init@CNTLM9XUserClass@@QEAAXXZ`
- size: `1131`
- prototype: `void __fastcall(CNTLM9XUserClass *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`

## callees

- `0x18007b484`
- `0x180085c70`
- `0x180086358`
- `0x18008846c`
- `0x18008a658`
- `0x1800b7b6c`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b7c37`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b7d6d`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b7c37`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b7d6d`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b7cd3`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b7cd3`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b7cc7`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b7cc7`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b7f94`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b7fa0`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b7fac`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b7f94`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b7fa0`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b7fac`
- `wbemcomn!GetMemLogObject` at `0x1800b7bc3`
- `wbemcomn!GetMemLogObject` at `0x1800b7c63`
- `wbemcomn!GetMemLogObject` at `0x1800b7cfe`
- `wbemcomn!GetMemLogObject` at `0x1800b7d99`
- `wbemcomn!GetMemLogObject` at `0x1800b7e24`
- `wbemcomn!GetMemLogObject` at `0x1800b7ea8`
- `wbemcomn!GetMemLogObject` at `0x1800b7f2e`
- `wbemcomn!GetMemLogObject` at `0x1800b7bc3`
- `wbemcomn!GetMemLogObject` at `0x1800b7c63`
- `wbemcomn!GetMemLogObject` at `0x1800b7cfe`
- `wbemcomn!GetMemLogObject` at `0x1800b7d99`
- `wbemcomn!GetMemLogObject` at `0x1800b7e24`
- `wbemcomn!GetMemLogObject` at `0x1800b7ea8`
- `wbemcomn!GetMemLogObject` at `0x1800b7f2e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7bd1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7c6f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7d0c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7da7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7e30`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7eb6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7f3c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7bd1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7c6f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7d0c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7da7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7e30`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7eb6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b7f3c`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b7bb4`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b7bb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CNTLM9XUserClass::Init(CNTLM9XUserClass *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  CMemoryLog *v6; // rax
  CMemoryLog *v7; // rax
  CMemoryLog *v8; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v11[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v12[40]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v13[864]; // [rsp+A0h] [rbp-60h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v13);
  CSecurityBaseClass::Init((CSecurityBaseClass *)v13);
  if ( CWbemClass::CreateDerivedClass(this, (struct CWbemClass *)v13, 0, 0) == -2147217402 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        348,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v12, 8, L"__NTLMUser9X");
  if ( (*(unsigned int (__fastcall **)(CNTLM9XUserClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
         this,
         L"__CLASS",
         v12,
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
        349,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v10);
  CVar::SetAsNull((CVar *)v10);
  if ( (*(unsigned int (__fastcall **)(CNTLM9XUserClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"Name",
         v10,
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
        350,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v11, 8, L".");
  if ( (*(unsigned int (__fastcall **)(CNTLM9XUserClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"Authority",
         v11,
         8) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        351,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( (*(unsigned int (__fastcall **)(CNTLM9XUserClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"Flags",
         v10,
         3) == -2147217402 )
  {
    v6 = GetMemLogObject();
    CMemoryLog::Write(v6, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        352,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( (*(unsigned int (__fastcall **)(CNTLM9XUserClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"Mask",
         v10,
         3) == -2147217402 )
  {
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        353,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  if ( (*(unsigned int (__fastcall **)(CNTLM9XUserClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"Type",
         v10,
         3) == -2147217402 )
  {
    v8 = GetMemLogObject();
    CMemoryLog::Write(v8, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        354,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v11);
  CVar::~CVar((CVar *)v10);
  CVar::~CVar((CVar *)v12);
  CSystemEventClass::~CSystemEventClass((CSystemEventClass *)v13);
}

```

## disassembly

```asm
0x1800b7b6c  push    rbp
0x1800b7b6e  push    rbx
0x1800b7b6f  push    rsi
0x1800b7b70  push    rdi
0x1800b7b71  lea     rbp, [rsp-318h]
0x1800b7b79  sub     rsp, 418h
0x1800b7b80  mov     rax, cs:__security_cookie
0x1800b7b87  xor     rax, rsp
0x1800b7b8a  mov     [rbp+330h+var_30], rax
0x1800b7b91  mov     rbx, rcx
0x1800b7b94  lea     rcx, [rbp+330h+var_390]; this
0x1800b7b98  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800b7b9d  nop
0x1800b7b9e  lea     rcx, [rbp+330h+var_390]; this
0x1800b7ba2  call    ?Init@CSecurityBaseClass@@QEAAXXZ; CSecurityBaseClass::Init(void)
0x1800b7ba7  xor     r9d, r9d
0x1800b7baa  xor     r8d, r8d
0x1800b7bad  lea     rdx, [rbp+330h+var_390]
0x1800b7bb1  mov     rcx, rbx
0x1800b7bb4  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800b7bba  mov     edi, 80041006h
0x1800b7bbf  cmp     eax, edi
0x1800b7bc1  jnz     short loc_1800B7C24
0x1800b7bc3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b7bc9  mov     edx, 0FFFFFFFEh
0x1800b7bce  mov     rcx, rax
0x1800b7bd1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b7bd7  lea     rax, WPP_GLOBAL_Control
0x1800b7bde  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7be5  cmp     rcx, rax
0x1800b7be8  jz      short loc_1800B7C12
0x1800b7bea  test    byte ptr [rcx+1Ch], 1
0x1800b7bee  jz      short loc_1800B7C12
0x1800b7bf0  cmp     byte ptr [rcx+19h], 2
0x1800b7bf4  jb      short loc_1800B7C12
0x1800b7bf6  mov     edx, 15Ch
0x1800b7bfb  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b7c02  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b7c09  mov     rcx, [rcx+10h]
0x1800b7c0d  call    WPP_SF_s
0x1800b7c12  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b7c19  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b7c1e  call    _CxxThrowException_0
0x1800b7c24  lea     r8, aNtlmuser9x; "__NTLMUser9X"
0x1800b7c2b  mov     esi, 8
0x1800b7c30  mov     edx, esi
0x1800b7c32  lea     rcx, [rsp+430h+var_3B8]
0x1800b7c37  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b7c3d  nop
0x1800b7c3e  mov     rax, [rbx]
0x1800b7c41  xor     r9d, r9d
0x1800b7c44  lea     r8, [rsp+430h+var_3B8]
0x1800b7c49  lea     rdx, aClass_0; "__CLASS"
0x1800b7c50  mov     rcx, rbx
0x1800b7c53  mov     rax, [rax+368h]
0x1800b7c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7c5f  cmp     eax, edi
0x1800b7c61  jnz     short loc_1800B7CC2
0x1800b7c63  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b7c69  lea     edx, [rsi-0Ah]
0x1800b7c6c  mov     rcx, rax
0x1800b7c6f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b7c75  lea     rax, WPP_GLOBAL_Control
0x1800b7c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7c83  cmp     rcx, rax
0x1800b7c86  jz      short loc_1800B7CB0
0x1800b7c88  test    byte ptr [rcx+1Ch], 1
0x1800b7c8c  jz      short loc_1800B7CB0
0x1800b7c8e  cmp     byte ptr [rcx+19h], 2
0x1800b7c92  jb      short loc_1800B7CB0
0x1800b7c94  mov     edx, 15Dh
0x1800b7c99  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b7ca0  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b7ca7  mov     rcx, [rcx+10h]
0x1800b7cab  call    WPP_SF_s
0x1800b7cb0  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b7cb7  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b7cbc  call    _CxxThrowException_0
0x1800b7cc2  lea     rcx, [rsp+430h+var_3F8]
0x1800b7cc7  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800b7ccd  nop
0x1800b7cce  lea     rcx, [rsp+430h+var_3F8]
0x1800b7cd3  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800b7cd9  mov     rax, [rbx]
0x1800b7cdc  mov     r9d, esi
0x1800b7cdf  lea     r8, [rsp+430h+var_3F8]
0x1800b7ce4  lea     rdx, aName; "Name"
0x1800b7ceb  mov     rcx, rbx
0x1800b7cee  mov     rax, [rax+368h]
0x1800b7cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7cfa  cmp     eax, edi
0x1800b7cfc  jnz     short loc_1800B7D5F
0x1800b7cfe  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b7d04  mov     edx, 0FFFFFFFEh
0x1800b7d09  mov     rcx, rax
0x1800b7d0c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b7d12  lea     rax, WPP_GLOBAL_Control
0x1800b7d19  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7d20  cmp     rcx, rax
0x1800b7d23  jz      short loc_1800B7D4D
0x1800b7d25  test    byte ptr [rcx+1Ch], 1
0x1800b7d29  jz      short loc_1800B7D4D
0x1800b7d2b  cmp     byte ptr [rcx+19h], 2
0x1800b7d2f  jb      short loc_1800B7D4D
0x1800b7d31  mov     edx, 15Eh
0x1800b7d36  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b7d3d  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b7d44  mov     rcx, [rcx+10h]
0x1800b7d48  call    WPP_SF_s
0x1800b7d4d  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b7d54  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b7d59  call    _CxxThrowException_0
0x1800b7d5f  lea     r8, asc_1800EB7D4; "."
0x1800b7d66  mov     edx, esi
0x1800b7d68  lea     rcx, [rsp+430h+var_3D8]
0x1800b7d6d  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b7d73  nop
0x1800b7d74  mov     rax, [rbx]
0x1800b7d77  mov     r9d, esi
0x1800b7d7a  lea     r8, [rsp+430h+var_3D8]
0x1800b7d7f  lea     rdx, aAuthority; "Authority"
0x1800b7d86  mov     rcx, rbx
0x1800b7d89  mov     rax, [rax+368h]
0x1800b7d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7d95  cmp     eax, edi
0x1800b7d97  jnz     short loc_1800B7DFA
0x1800b7d99  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b7d9f  mov     edx, 0FFFFFFFEh
0x1800b7da4  mov     rcx, rax
0x1800b7da7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b7dad  lea     rax, WPP_GLOBAL_Control
0x1800b7db4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7dbb  cmp     rcx, rax
0x1800b7dbe  jz      short loc_1800B7DE8
0x1800b7dc0  test    byte ptr [rcx+1Ch], 1
0x1800b7dc4  jz      short loc_1800B7DE8
0x1800b7dc6  cmp     byte ptr [rcx+19h], 2
0x1800b7dca  jb      short loc_1800B7DE8
0x1800b7dcc  mov     edx, 15Fh
0x1800b7dd1  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b7dd8  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b7ddf  mov     rcx, [rcx+10h]
0x1800b7de3  call    WPP_SF_s
0x1800b7de8  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b7def  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b7df4  call    _CxxThrowException_0
0x1800b7dfa  mov     rax, [rbx]
0x1800b7dfd  mov     esi, 3
0x1800b7e02  mov     r9d, esi
0x1800b7e05  lea     r8, [rsp+430h+var_3F8]
0x1800b7e0a  lea     rdx, aFlags; "Flags"
0x1800b7e11  mov     rcx, rbx
0x1800b7e14  mov     rax, [rax+368h]
0x1800b7e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7e20  cmp     eax, edi
0x1800b7e22  jnz     short loc_1800B7E83
0x1800b7e24  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b7e2a  lea     edx, [rsi-5]
0x1800b7e2d  mov     rcx, rax
0x1800b7e30  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b7e36  lea     rax, WPP_GLOBAL_Control
0x1800b7e3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7e44  cmp     rcx, rax
0x1800b7e47  jz      short loc_1800B7E71
0x1800b7e49  test    byte ptr [rcx+1Ch], 1
0x1800b7e4d  jz      short loc_1800B7E71
0x1800b7e4f  cmp     byte ptr [rcx+19h], 2
0x1800b7e53  jb      short loc_1800B7E71
0x1800b7e55  mov     edx, 160h
0x1800b7e5a  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b7e61  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b7e68  mov     rcx, [rcx+10h]
0x1800b7e6c  call    WPP_SF_s
0x1800b7e71  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b7e78  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b7e7d  call    _CxxThrowException_0
0x1800b7e83  mov     rax, [rbx]
0x1800b7e86  mov     r9d, esi
0x1800b7e89  lea     r8, [rsp+430h+var_3F8]
0x1800b7e8e  lea     rdx, aMask; "Mask"
0x1800b7e95  mov     rcx, rbx
0x1800b7e98  mov     rax, [rax+368h]
0x1800b7e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7ea4  cmp     eax, edi
0x1800b7ea6  jnz     short loc_1800B7F09
0x1800b7ea8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b7eae  mov     edx, 0FFFFFFFEh
0x1800b7eb3  mov     rcx, rax
0x1800b7eb6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b7ebc  lea     rax, WPP_GLOBAL_Control
0x1800b7ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7eca  cmp     rcx, rax
0x1800b7ecd  jz      short loc_1800B7EF7
0x1800b7ecf  test    byte ptr [rcx+1Ch], 1
0x1800b7ed3  jz      short loc_1800B7EF7
0x1800b7ed5  cmp     byte ptr [rcx+19h], 2
0x1800b7ed9  jb      short loc_1800B7EF7
0x1800b7edb  mov     edx, 161h
0x1800b7ee0  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b7ee7  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b7eee  mov     rcx, [rcx+10h]
0x1800b7ef2  call    WPP_SF_s
0x1800b7ef7  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b7efe  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b7f03  call    _CxxThrowException_0
0x1800b7f09  mov     rax, [rbx]
0x1800b7f0c  mov     r9d, esi
0x1800b7f0f  lea     r8, [rsp+430h+var_3F8]
0x1800b7f14  lea     rdx, aType; "Type"
0x1800b7f1b  mov     rcx, rbx
0x1800b7f1e  mov     rax, [rax+368h]
0x1800b7f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7f2a  cmp     eax, edi
0x1800b7f2c  jnz     short loc_1800B7F8F
0x1800b7f2e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b7f34  mov     edx, 0FFFFFFFEh
0x1800b7f39  mov     rcx, rax
0x1800b7f3c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b7f42  lea     rax, WPP_GLOBAL_Control
0x1800b7f49  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7f50  cmp     rcx, rax
0x1800b7f53  jz      short loc_1800B7F7D
0x1800b7f55  test    byte ptr [rcx+1Ch], 1
0x1800b7f59  jz      short loc_1800B7F7D
0x1800b7f5b  cmp     byte ptr [rcx+19h], 2
0x1800b7f5f  jb      short loc_1800B7F7D
0x1800b7f61  mov     edx, 162h
0x1800b7f66  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b7f6d  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b7f74  mov     rcx, [rcx+10h]
0x1800b7f78  call    WPP_SF_s
0x1800b7f7d  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b7f84  lea     rcx, [rsp+430h+pExceptionObject]; pExceptionObject
0x1800b7f89  call    _CxxThrowException_0
0x1800b7f8f  lea     rcx, [rsp+430h+var_3D8]
0x1800b7f94  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b7f9a  nop
0x1800b7f9b  lea     rcx, [rsp+430h+var_3F8]
0x1800b7fa0  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b7fa6  nop
0x1800b7fa7  lea     rcx, [rsp+430h+var_3B8]
0x1800b7fac  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b7fb2  nop
0x1800b7fb3  lea     rcx, [rbp+330h+var_390]; this
0x1800b7fb7  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800b7fbc  mov     rcx, [rbp+330h+var_30]
0x1800b7fc3  xor     rcx, rsp; StackCookie
0x1800b7fc6  call    __security_check_cookie
0x1800b7fcb  add     rsp, 418h
0x1800b7fd2  pop     rdi
0x1800b7fd3  pop     rsi
0x1800b7fd4  pop     rbx
0x1800b7fd5  pop     rbp
0x1800b7fd6  retn
```
