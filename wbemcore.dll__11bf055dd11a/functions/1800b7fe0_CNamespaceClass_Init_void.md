# CNamespaceClass::Init(void)

- ea: `0x1800b7fe0`
- end: `0x1800b82b7`
- name: `?Init@CNamespaceClass@@QEAAXXZ`
- size: `727`
- prototype: `void __fastcall(CNamespaceClass *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006adb4`

## callees

- `0x18006abcc`
- `0x180085c70`
- `0x180086358`
- `0x18008846c`
- `0x18008a658`
- `0x1800b7fe0`
- `0x1800ce510`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b81d6`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b81d6`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b80af`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b80af`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b8144`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b8144`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b8138`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b8138`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b826b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b8277`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b8283`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b826b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b8277`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b8283`
- `wbemcomn!GetMemLogObject` at `0x1800b803d`
- `wbemcomn!GetMemLogObject` at `0x1800b80d2`
- `wbemcomn!GetMemLogObject` at `0x1800b8169`
- `wbemcomn!GetMemLogObject` at `0x1800b8205`
- `wbemcomn!GetMemLogObject` at `0x1800b803d`
- `wbemcomn!GetMemLogObject` at `0x1800b80d2`
- `wbemcomn!GetMemLogObject` at `0x1800b8169`
- `wbemcomn!GetMemLogObject` at `0x1800b8205`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b804b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b80e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b8177`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b8213`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b804b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b80e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b8177`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b8213`
- `FastProx!?SetPropQualifier@CWbemClass@@UEAAJPEBG0JPEAVCVar@@@Z` at `0x1800b81fb`
- `FastProx!?SetPropQualifier@CWbemClass@@UEAAJPEBG0JPEAVCVar@@@Z` at `0x1800b81fb`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800b80c8`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800b815f`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800b80c8`
- `FastProx!?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z` at `0x1800b815f`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b802e`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b802e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CNamespaceClass::Init(CNamespaceClass *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v7[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v8[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v9[40]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v10[864]; // [rsp+A0h] [rbp-60h] BYREF

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
        28,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, 8, L"__NAMESPACE");
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
        29,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v7);
  CVar::SetAsNull((CVar *)v7);
  if ( CWbemClass::SetPropValue(this, L"Name", (struct CVar *)v7, 8) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8, -1, 11);
  if ( CWbemClass::SetPropQualifier(this, L"Name", L"key", 0, (struct CVar *)v8) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v8);
  CVar::~CVar((CVar *)v7);
  CVar::~CVar((CVar *)v9);
  CSystemEventClass::~CSystemEventClass((CSystemEventClass *)v10);
}

```

## disassembly

```asm
0x1800b7fe0  mov     [rsp-8+arg_8], rbx
0x1800b7fe5  mov     [rsp-8+arg_10], rdi
0x1800b7fea  push    rbp
0x1800b7feb  lea     rbp, [rsp-310h]
0x1800b7ff3  sub     rsp, 410h
0x1800b7ffa  mov     rax, cs:__security_cookie
0x1800b8001  xor     rax, rsp
0x1800b8004  mov     [rbp+310h+var_10], rax
0x1800b800b  mov     rbx, rcx
0x1800b800e  lea     rcx, [rbp+310h+var_370]; this
0x1800b8012  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800b8017  nop
0x1800b8018  lea     rcx, [rbp+310h+var_370]; this
0x1800b801c  call    ?Init@CSystemClass@@QEAAXXZ; CSystemClass::Init(void)
0x1800b8021  xor     r9d, r9d
0x1800b8024  xor     r8d, r8d
0x1800b8027  lea     rdx, [rbp+310h+var_370]
0x1800b802b  mov     rcx, rbx
0x1800b802e  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800b8034  mov     edi, 80041006h
0x1800b8039  cmp     eax, edi
0x1800b803b  jnz     short loc_1800B809E
0x1800b803d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b8043  mov     edx, 0FFFFFFFEh
0x1800b8048  mov     rcx, rax
0x1800b804b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b8051  lea     rax, WPP_GLOBAL_Control
0x1800b8058  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b805f  cmp     rcx, rax
0x1800b8062  jz      short loc_1800B808C
0x1800b8064  test    byte ptr [rcx+1Ch], 1
0x1800b8068  jz      short loc_1800B808C
0x1800b806a  cmp     byte ptr [rcx+19h], 2
0x1800b806e  jb      short loc_1800B808C
0x1800b8070  mov     edx, 1Ch
0x1800b8075  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b807c  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b8083  mov     rcx, [rcx+10h]
0x1800b8087  call    WPP_SF_s
0x1800b808c  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b8093  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b8098  call    _CxxThrowException_0
0x1800b809e  lea     r8, aNamespace_1; "__NAMESPACE"
0x1800b80a5  mov     edx, 8
0x1800b80aa  lea     rcx, [rsp+410h+var_398]
0x1800b80af  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b80b5  nop
0x1800b80b6  xor     r9d, r9d
0x1800b80b9  lea     r8, [rsp+410h+var_398]
0x1800b80be  lea     rdx, aClass_0; "__CLASS"
0x1800b80c5  mov     rcx, rbx
0x1800b80c8  call    cs:__imp_?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetPropValue(ushort const *,CVar *,long)
0x1800b80ce  cmp     eax, edi
0x1800b80d0  jnz     short loc_1800B8133
0x1800b80d2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b80d8  mov     edx, 0FFFFFFFEh
0x1800b80dd  mov     rcx, rax
0x1800b80e0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b80e6  lea     rax, WPP_GLOBAL_Control
0x1800b80ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b80f4  cmp     rcx, rax
0x1800b80f7  jz      short loc_1800B8121
0x1800b80f9  test    byte ptr [rcx+1Ch], 1
0x1800b80fd  jz      short loc_1800B8121
0x1800b80ff  cmp     byte ptr [rcx+19h], 2
0x1800b8103  jb      short loc_1800B8121
0x1800b8105  mov     edx, 1Dh
0x1800b810a  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b8111  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b8118  mov     rcx, [rcx+10h]
0x1800b811c  call    WPP_SF_s
0x1800b8121  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b8128  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b812d  call    _CxxThrowException_0
0x1800b8133  lea     rcx, [rsp+410h+var_3D8]
0x1800b8138  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800b813e  nop
0x1800b813f  lea     rcx, [rsp+410h+var_3D8]
0x1800b8144  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800b814a  mov     r9d, 8
0x1800b8150  lea     r8, [rsp+410h+var_3D8]
0x1800b8155  lea     rdx, aName; "Name"
0x1800b815c  mov     rcx, rbx
0x1800b815f  call    cs:__imp_?SetPropValue@CWbemClass@@UEAAJPEBGPEAVCVar@@J@Z; CWbemClass::SetPropValue(ushort const *,CVar *,long)
0x1800b8165  cmp     eax, edi
0x1800b8167  jnz     short loc_1800B81CA
0x1800b8169  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b816f  mov     edx, 0FFFFFFFEh
0x1800b8174  mov     rcx, rax
0x1800b8177  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b817d  lea     rax, WPP_GLOBAL_Control
0x1800b8184  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b818b  cmp     rcx, rax
0x1800b818e  jz      short loc_1800B81B8
0x1800b8190  test    byte ptr [rcx+1Ch], 1
0x1800b8194  jz      short loc_1800B81B8
0x1800b8196  cmp     byte ptr [rcx+19h], 2
0x1800b819a  jb      short loc_1800B81B8
0x1800b819c  mov     edx, 1Eh
0x1800b81a1  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b81a8  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b81af  mov     rcx, [rcx+10h]
0x1800b81b3  call    WPP_SF_s
0x1800b81b8  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b81bf  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b81c4  call    _CxxThrowException_0
0x1800b81ca  or      edx, 0FFFFFFFFh
0x1800b81cd  lea     r8d, [rdx+0Ch]
0x1800b81d1  lea     rcx, [rsp+410h+var_3B8]
0x1800b81d6  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800b81dc  nop
0x1800b81dd  lea     rax, [rsp+410h+var_3B8]
0x1800b81e2  mov     [rsp+410h+var_3F0], rax
0x1800b81e7  xor     r9d, r9d
0x1800b81ea  lea     r8, aKey; "key"
0x1800b81f1  lea     rdx, aName; "Name"
0x1800b81f8  mov     rcx, rbx
0x1800b81fb  call    cs:__imp_?SetPropQualifier@CWbemClass@@UEAAJPEBG0JPEAVCVar@@@Z; CWbemClass::SetPropQualifier(ushort const *,ushort const *,long,CVar *)
0x1800b8201  cmp     eax, edi
0x1800b8203  jnz     short loc_1800B8266
0x1800b8205  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b820b  mov     edx, 0FFFFFFFEh
0x1800b8210  mov     rcx, rax
0x1800b8213  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b8219  lea     rax, WPP_GLOBAL_Control
0x1800b8220  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8227  cmp     rcx, rax
0x1800b822a  jz      short loc_1800B8254
0x1800b822c  test    byte ptr [rcx+1Ch], 1
0x1800b8230  jz      short loc_1800B8254
0x1800b8232  cmp     byte ptr [rcx+19h], 2
0x1800b8236  jb      short loc_1800B8254
0x1800b8238  mov     edx, 1Fh
0x1800b823d  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b8244  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b824b  mov     rcx, [rcx+10h]
0x1800b824f  call    WPP_SF_s
0x1800b8254  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b825b  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b8260  call    _CxxThrowException_0
0x1800b8266  lea     rcx, [rsp+410h+var_3B8]
0x1800b826b  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b8271  nop
0x1800b8272  lea     rcx, [rsp+410h+var_3D8]
0x1800b8277  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b827d  nop
0x1800b827e  lea     rcx, [rsp+410h+var_398]
0x1800b8283  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b8289  nop
0x1800b828a  lea     rcx, [rbp+310h+var_370]; this
0x1800b828e  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800b8293  mov     rcx, [rbp+310h+var_10]
0x1800b829a  xor     rcx, rsp; StackCookie
0x1800b829d  call    __security_check_cookie
0x1800b82a2  lea     r11, [rsp+410h+var_s0]
0x1800b82aa  mov     rbx, [r11+18h]
0x1800b82ae  mov     rdi, [r11+20h]
0x1800b82b2  mov     rsp, r11
0x1800b82b5  pop     rbp
0x1800b82b6  retn
```
