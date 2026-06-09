# CActiveNamespacesClass::Init(void)

- ea: `0x1800b2920`
- end: `0x1800b2c09`
- name: `?Init@CActiveNamespacesClass@@QEAAXXZ`
- size: `745`
- prototype: `void __fastcall(CActiveNamespacesClass *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180093ec4`

## callees

- `0x18006abcc`
- `0x180085c70`
- `0x180086358`
- `0x18008846c`
- `0x18008a658`
- `0x1800b2920`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b2b28`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b2b28`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b29ef`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b29ef`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b2a8d`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b2a8d`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b2a81`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b2a81`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b2bbd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b2bc9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b2bd5`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b2bbd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b2bc9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b2bd5`
- `wbemcomn!GetMemLogObject` at `0x1800b297d`
- `wbemcomn!GetMemLogObject` at `0x1800b2a1b`
- `wbemcomn!GetMemLogObject` at `0x1800b2abb`
- `wbemcomn!GetMemLogObject` at `0x1800b2b57`
- `wbemcomn!GetMemLogObject` at `0x1800b297d`
- `wbemcomn!GetMemLogObject` at `0x1800b2a1b`
- `wbemcomn!GetMemLogObject` at `0x1800b2abb`
- `wbemcomn!GetMemLogObject` at `0x1800b2b57`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b298b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b2a29`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b2ac9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b2b65`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b298b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b2a29`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b2ac9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b2b65`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b296e`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b296e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CActiveNamespacesClass::Init(CActiveNamespacesClass *this)
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
        189,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, 8, L"__ListOfEventActiveNamespaces");
  if ( (*(unsigned int (__fastcall **)(CActiveNamespacesClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
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
        190,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v7);
  CVar::SetAsNull((CVar *)v7);
  if ( (*(unsigned int (__fastcall **)(CActiveNamespacesClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"Namespaces",
         v7,
         8200) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        191,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v8, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CActiveNamespacesClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 984LL))(
         this,
         L"singleton",
         v8,
         19) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        192,
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
0x1800b2920  mov     [rsp-8+arg_8], rbx
0x1800b2925  mov     [rsp-8+arg_10], rdi
0x1800b292a  push    rbp
0x1800b292b  lea     rbp, [rsp-310h]
0x1800b2933  sub     rsp, 410h
0x1800b293a  mov     rax, cs:__security_cookie
0x1800b2941  xor     rax, rsp
0x1800b2944  mov     [rbp+310h+var_10], rax
0x1800b294b  mov     rbx, rcx
0x1800b294e  lea     rcx, [rbp+310h+var_370]; this
0x1800b2952  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800b2957  nop
0x1800b2958  lea     rcx, [rbp+310h+var_370]; this
0x1800b295c  call    ?Init@CSystemClass@@QEAAXXZ; CSystemClass::Init(void)
0x1800b2961  xor     r9d, r9d
0x1800b2964  xor     r8d, r8d
0x1800b2967  lea     rdx, [rbp+310h+var_370]
0x1800b296b  mov     rcx, rbx
0x1800b296e  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800b2974  mov     edi, 80041006h
0x1800b2979  cmp     eax, edi
0x1800b297b  jnz     short loc_1800B29DE
0x1800b297d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b2983  mov     edx, 0FFFFFFFEh
0x1800b2988  mov     rcx, rax
0x1800b298b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b2991  lea     rax, WPP_GLOBAL_Control
0x1800b2998  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b299f  cmp     rcx, rax
0x1800b29a2  jz      short loc_1800B29CC
0x1800b29a4  test    byte ptr [rcx+1Ch], 1
0x1800b29a8  jz      short loc_1800B29CC
0x1800b29aa  cmp     byte ptr [rcx+19h], 2
0x1800b29ae  jb      short loc_1800B29CC
0x1800b29b0  mov     edx, 0BDh
0x1800b29b5  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b29bc  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b29c3  mov     rcx, [rcx+10h]
0x1800b29c7  call    WPP_SF_s
0x1800b29cc  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b29d3  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b29d8  call    _CxxThrowException_0
0x1800b29de  lea     r8, aListofeventact; "__ListOfEventActiveNamespaces"
0x1800b29e5  mov     edx, 8
0x1800b29ea  lea     rcx, [rsp+410h+var_398]
0x1800b29ef  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b29f5  nop
0x1800b29f6  mov     rax, [rbx]
0x1800b29f9  xor     r9d, r9d
0x1800b29fc  lea     r8, [rsp+410h+var_398]
0x1800b2a01  lea     rdx, aClass_0; "__CLASS"
0x1800b2a08  mov     rcx, rbx
0x1800b2a0b  mov     rax, [rax+368h]
0x1800b2a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2a17  cmp     eax, edi
0x1800b2a19  jnz     short loc_1800B2A7C
0x1800b2a1b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b2a21  mov     edx, 0FFFFFFFEh
0x1800b2a26  mov     rcx, rax
0x1800b2a29  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b2a2f  lea     rax, WPP_GLOBAL_Control
0x1800b2a36  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2a3d  cmp     rcx, rax
0x1800b2a40  jz      short loc_1800B2A6A
0x1800b2a42  test    byte ptr [rcx+1Ch], 1
0x1800b2a46  jz      short loc_1800B2A6A
0x1800b2a48  cmp     byte ptr [rcx+19h], 2
0x1800b2a4c  jb      short loc_1800B2A6A
0x1800b2a4e  mov     edx, 0BEh
0x1800b2a53  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b2a5a  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b2a61  mov     rcx, [rcx+10h]
0x1800b2a65  call    WPP_SF_s
0x1800b2a6a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b2a71  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b2a76  call    _CxxThrowException_0
0x1800b2a7c  lea     rcx, [rsp+410h+var_3D8]
0x1800b2a81  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800b2a87  nop
0x1800b2a88  lea     rcx, [rsp+410h+var_3D8]
0x1800b2a8d  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800b2a93  mov     rax, [rbx]
0x1800b2a96  mov     r9d, 2008h
0x1800b2a9c  lea     r8, [rsp+410h+var_3D8]
0x1800b2aa1  lea     rdx, aNamespaces; "Namespaces"
0x1800b2aa8  mov     rcx, rbx
0x1800b2aab  mov     rax, [rax+368h]
0x1800b2ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2ab7  cmp     eax, edi
0x1800b2ab9  jnz     short loc_1800B2B1C
0x1800b2abb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b2ac1  mov     edx, 0FFFFFFFEh
0x1800b2ac6  mov     rcx, rax
0x1800b2ac9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b2acf  lea     rax, WPP_GLOBAL_Control
0x1800b2ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2add  cmp     rcx, rax
0x1800b2ae0  jz      short loc_1800B2B0A
0x1800b2ae2  test    byte ptr [rcx+1Ch], 1
0x1800b2ae6  jz      short loc_1800B2B0A
0x1800b2ae8  cmp     byte ptr [rcx+19h], 2
0x1800b2aec  jb      short loc_1800B2B0A
0x1800b2aee  mov     edx, 0BFh
0x1800b2af3  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b2afa  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b2b01  mov     rcx, [rcx+10h]
0x1800b2b05  call    WPP_SF_s
0x1800b2b0a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b2b11  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b2b16  call    _CxxThrowException_0
0x1800b2b1c  or      edx, 0FFFFFFFFh
0x1800b2b1f  lea     r8d, [rdx+0Ch]
0x1800b2b23  lea     rcx, [rsp+410h+var_3B8]
0x1800b2b28  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800b2b2e  nop
0x1800b2b2f  mov     rax, [rbx]
0x1800b2b32  mov     r9d, 13h
0x1800b2b38  lea     r8, [rsp+410h+var_3B8]
0x1800b2b3d  lea     rdx, aSingleton; "singleton"
0x1800b2b44  mov     rcx, rbx
0x1800b2b47  mov     rax, [rax+3D8h]
0x1800b2b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2b53  cmp     eax, edi
0x1800b2b55  jnz     short loc_1800B2BB8
0x1800b2b57  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b2b5d  mov     edx, 0FFFFFFFEh
0x1800b2b62  mov     rcx, rax
0x1800b2b65  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b2b6b  lea     rax, WPP_GLOBAL_Control
0x1800b2b72  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2b79  cmp     rcx, rax
0x1800b2b7c  jz      short loc_1800B2BA6
0x1800b2b7e  test    byte ptr [rcx+1Ch], 1
0x1800b2b82  jz      short loc_1800B2BA6
0x1800b2b84  cmp     byte ptr [rcx+19h], 2
0x1800b2b88  jb      short loc_1800B2BA6
0x1800b2b8a  mov     edx, 0C0h
0x1800b2b8f  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b2b96  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b2b9d  mov     rcx, [rcx+10h]
0x1800b2ba1  call    WPP_SF_s
0x1800b2ba6  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b2bad  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b2bb2  call    _CxxThrowException_0
0x1800b2bb8  lea     rcx, [rsp+410h+var_3B8]
0x1800b2bbd  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b2bc3  nop
0x1800b2bc4  lea     rcx, [rsp+410h+var_3D8]
0x1800b2bc9  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b2bcf  nop
0x1800b2bd0  lea     rcx, [rsp+410h+var_398]
0x1800b2bd5  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b2bdb  nop
0x1800b2bdc  lea     rcx, [rbp+310h+var_370]; this
0x1800b2be0  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800b2be5  mov     rcx, [rbp+310h+var_10]
0x1800b2bec  xor     rcx, rsp; StackCookie
0x1800b2bef  call    __security_check_cookie
0x1800b2bf4  lea     r11, [rsp+410h+var_s0]
0x1800b2bfc  mov     rbx, [r11+18h]
0x1800b2c00  mov     rdi, [r11+20h]
0x1800b2c04  mov     rsp, r11
0x1800b2c07  pop     rbp
0x1800b2c08  retn
```
