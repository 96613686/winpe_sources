# CSpecificCacheControlClass::Init(ushort const *)

- ea: `0x1800ba2a0`
- end: `0x1800ba636`
- name: `?Init@CSpecificCacheControlClass@@QEAAXPEBG@Z`
- size: `918`
- prototype: `void __fastcall(CSpecificCacheControlClass *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180093cf0`

## callees

- `0x180085c70`
- `0x180086358`
- `0x18008846c`
- `0x18008a658`
- `0x1800b4370`
- `0x1800ba2a0`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800ba54c`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800ba54c`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800ba36c`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800ba4a4`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800ba36c`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800ba4a4`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800ba407`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800ba407`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800ba3fb`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800ba3fb`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800ba5e1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800ba5ed`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800ba5f9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800ba604`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800ba5e1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800ba5ed`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800ba5f9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800ba604`
- `wbemcomn!GetMemLogObject` at `0x1800ba2fd`
- `wbemcomn!GetMemLogObject` at `0x1800ba397`
- `wbemcomn!GetMemLogObject` at `0x1800ba435`
- `wbemcomn!GetMemLogObject` at `0x1800ba4df`
- `wbemcomn!GetMemLogObject` at `0x1800ba57b`
- `wbemcomn!GetMemLogObject` at `0x1800ba2fd`
- `wbemcomn!GetMemLogObject` at `0x1800ba397`
- `wbemcomn!GetMemLogObject` at `0x1800ba435`
- `wbemcomn!GetMemLogObject` at `0x1800ba4df`
- `wbemcomn!GetMemLogObject` at `0x1800ba57b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ba30b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ba3a3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ba443`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ba4ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ba589`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ba30b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ba3a3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ba443`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ba4ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ba589`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800ba2ee`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800ba2ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CSpecificCacheControlClass::Init(CSpecificCacheControlClass *this, unsigned __int16 *a2)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v5; // rax
  CMemoryLog *v6; // rax
  CMemoryLog *v7; // rax
  CMemoryLog *v8; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v11[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v12[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v13[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v14[864]; // [rsp+C0h] [rbp-40h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v14);
  CCacheControlClass::Init((CCacheControlClass *)v14);
  if ( CWbemClass::CreateDerivedClass(this, (struct CWbemClass *)v14, 0, 0) == -2147217402 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        181,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v13, 8, a2);
  if ( (*(unsigned int (__fastcall **)(CSpecificCacheControlClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
         this,
         L"__CLASS",
         v13,
         0) == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        182,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v10);
  CVar::SetAsNull((CVar *)v10);
  if ( (*(unsigned int (__fastcall **)(CSpecificCacheControlClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
         this,
         L"ClearAfter",
         v10,
         101) == -2147217402 )
  {
    v6 = GetMemLogObject();
    CMemoryLog::Write(v6, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        183,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v12, 8, L"interval");
  if ( (*(unsigned int (__fastcall **)(CSpecificCacheControlClass *, const wchar_t *, const wchar_t *, __int64, _BYTE *))(*(_QWORD *)this + 888LL))(
         this,
         L"ClearAfter",
         L"SUBTYPE",
         3,
         v12) == -2147217402 )
  {
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        184,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v11, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CSpecificCacheControlClass *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 984LL))(
         this,
         L"singleton",
         v11,
         19) == -2147217402 )
  {
    v8 = GetMemLogObject();
    CMemoryLog::Write(v8, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        185,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v11);
  CVar::~CVar((CVar *)v12);
  CVar::~CVar((CVar *)v10);
  CVar::~CVar((CVar *)v13);
  CSystemEventClass::~CSystemEventClass((CSystemEventClass *)v14);
}

```

## disassembly

```asm
0x1800ba2a0  mov     [rsp-8+arg_10], rbx
0x1800ba2a5  push    rbp
0x1800ba2a6  push    rsi
0x1800ba2a7  push    rdi
0x1800ba2a8  lea     rbp, [rsp-330h]
0x1800ba2b0  sub     rsp, 430h
0x1800ba2b7  mov     rax, cs:__security_cookie
0x1800ba2be  xor     rax, rsp
0x1800ba2c1  mov     [rbp+340h+var_20], rax
0x1800ba2c8  mov     rdi, rdx
0x1800ba2cb  mov     rbx, rcx
0x1800ba2ce  lea     rcx, [rbp+340h+var_380]; this
0x1800ba2d2  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800ba2d7  nop
0x1800ba2d8  lea     rcx, [rbp+340h+var_380]; this
0x1800ba2dc  call    ?Init@CCacheControlClass@@QEAAXXZ; CCacheControlClass::Init(void)
0x1800ba2e1  xor     r9d, r9d
0x1800ba2e4  xor     r8d, r8d
0x1800ba2e7  lea     rdx, [rbp+340h+var_380]
0x1800ba2eb  mov     rcx, rbx
0x1800ba2ee  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800ba2f4  mov     esi, 80041006h
0x1800ba2f9  cmp     eax, esi
0x1800ba2fb  jnz     short loc_1800BA35E
0x1800ba2fd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800ba303  mov     edx, 0FFFFFFFEh
0x1800ba308  mov     rcx, rax
0x1800ba30b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800ba311  lea     rax, WPP_GLOBAL_Control
0x1800ba318  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba31f  cmp     rcx, rax
0x1800ba322  jz      short loc_1800BA34C
0x1800ba324  test    byte ptr [rcx+1Ch], 1
0x1800ba328  jz      short loc_1800BA34C
0x1800ba32a  cmp     byte ptr [rcx+19h], 2
0x1800ba32e  jb      short loc_1800BA34C
0x1800ba330  mov     edx, 0B5h
0x1800ba335  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800ba33c  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800ba343  mov     rcx, [rcx+10h]
0x1800ba347  call    WPP_SF_s
0x1800ba34c  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800ba353  lea     rcx, [rsp+440h+pExceptionObject]; pExceptionObject
0x1800ba358  call    _CxxThrowException_0
0x1800ba35e  mov     r8, rdi
0x1800ba361  mov     edi, 8
0x1800ba366  mov     edx, edi
0x1800ba368  lea     rcx, [rbp+340h+var_3A8]
0x1800ba36c  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800ba372  nop
0x1800ba373  mov     rax, [rbx]
0x1800ba376  xor     r9d, r9d
0x1800ba379  lea     r8, [rbp+340h+var_3A8]
0x1800ba37d  lea     rdx, aClass_0; "__CLASS"
0x1800ba384  mov     rcx, rbx
0x1800ba387  mov     rax, [rax+368h]
0x1800ba38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba393  cmp     eax, esi
0x1800ba395  jnz     short loc_1800BA3F6
0x1800ba397  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800ba39d  lea     edx, [rdi-0Ah]
0x1800ba3a0  mov     rcx, rax
0x1800ba3a3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800ba3a9  lea     rax, WPP_GLOBAL_Control
0x1800ba3b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba3b7  cmp     rcx, rax
0x1800ba3ba  jz      short loc_1800BA3E4
0x1800ba3bc  test    byte ptr [rcx+1Ch], 1
0x1800ba3c0  jz      short loc_1800BA3E4
0x1800ba3c2  cmp     byte ptr [rcx+19h], 2
0x1800ba3c6  jb      short loc_1800BA3E4
0x1800ba3c8  mov     edx, 0B6h
0x1800ba3cd  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800ba3d4  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800ba3db  mov     rcx, [rcx+10h]
0x1800ba3df  call    WPP_SF_s
0x1800ba3e4  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800ba3eb  lea     rcx, [rsp+440h+pExceptionObject]; pExceptionObject
0x1800ba3f0  call    _CxxThrowException_0
0x1800ba3f6  lea     rcx, [rsp+440h+var_408]
0x1800ba3fb  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800ba401  nop
0x1800ba402  lea     rcx, [rsp+440h+var_408]
0x1800ba407  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800ba40d  mov     rax, [rbx]
0x1800ba410  mov     r9d, 65h ; 'e'
0x1800ba416  lea     r8, [rsp+440h+var_408]
0x1800ba41b  lea     rdx, aClearafter; "ClearAfter"
0x1800ba422  mov     rcx, rbx
0x1800ba425  mov     rax, [rax+368h]
0x1800ba42c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba431  cmp     eax, esi
0x1800ba433  jnz     short loc_1800BA496
0x1800ba435  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800ba43b  mov     edx, 0FFFFFFFEh
0x1800ba440  mov     rcx, rax
0x1800ba443  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800ba449  lea     rax, WPP_GLOBAL_Control
0x1800ba450  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba457  cmp     rcx, rax
0x1800ba45a  jz      short loc_1800BA484
0x1800ba45c  test    byte ptr [rcx+1Ch], 1
0x1800ba460  jz      short loc_1800BA484
0x1800ba462  cmp     byte ptr [rcx+19h], 2
0x1800ba466  jb      short loc_1800BA484
0x1800ba468  mov     edx, 0B7h
0x1800ba46d  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800ba474  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800ba47b  mov     rcx, [rcx+10h]
0x1800ba47f  call    WPP_SF_s
0x1800ba484  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800ba48b  lea     rcx, [rsp+440h+pExceptionObject]; pExceptionObject
0x1800ba490  call    _CxxThrowException_0
0x1800ba496  lea     r8, aInterval; "interval"
0x1800ba49d  mov     edx, edi
0x1800ba49f  lea     rcx, [rsp+440h+var_3C8]
0x1800ba4a4  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800ba4aa  nop
0x1800ba4ab  mov     rax, [rbx]
0x1800ba4ae  lea     rcx, [rsp+440h+var_3C8]
0x1800ba4b3  mov     [rsp+440h+var_420], rcx
0x1800ba4b8  mov     r9d, 3
0x1800ba4be  lea     r8, aSubtype; "SUBTYPE"
0x1800ba4c5  lea     rdx, aClearafter; "ClearAfter"
0x1800ba4cc  mov     rcx, rbx
0x1800ba4cf  mov     rax, [rax+378h]
0x1800ba4d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba4db  cmp     eax, esi
0x1800ba4dd  jnz     short loc_1800BA540
0x1800ba4df  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800ba4e5  mov     edx, 0FFFFFFFEh
0x1800ba4ea  mov     rcx, rax
0x1800ba4ed  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800ba4f3  lea     rax, WPP_GLOBAL_Control
0x1800ba4fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba501  cmp     rcx, rax
0x1800ba504  jz      short loc_1800BA52E
0x1800ba506  test    byte ptr [rcx+1Ch], 1
0x1800ba50a  jz      short loc_1800BA52E
0x1800ba50c  cmp     byte ptr [rcx+19h], 2
0x1800ba510  jb      short loc_1800BA52E
0x1800ba512  mov     edx, 0B8h
0x1800ba517  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800ba51e  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800ba525  mov     rcx, [rcx+10h]
0x1800ba529  call    WPP_SF_s
0x1800ba52e  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800ba535  lea     rcx, [rsp+440h+pExceptionObject]; pExceptionObject
0x1800ba53a  call    _CxxThrowException_0
0x1800ba540  or      edx, 0FFFFFFFFh
0x1800ba543  lea     r8d, [rdx+0Ch]
0x1800ba547  lea     rcx, [rsp+440h+var_3E8]
0x1800ba54c  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800ba552  nop
0x1800ba553  mov     rax, [rbx]
0x1800ba556  mov     r9d, 13h
0x1800ba55c  lea     r8, [rsp+440h+var_3E8]
0x1800ba561  lea     rdx, aSingleton; "singleton"
0x1800ba568  mov     rcx, rbx
0x1800ba56b  mov     rax, [rax+3D8h]
0x1800ba572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba577  cmp     eax, esi
0x1800ba579  jnz     short loc_1800BA5DC
0x1800ba57b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800ba581  mov     edx, 0FFFFFFFEh
0x1800ba586  mov     rcx, rax
0x1800ba589  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800ba58f  lea     rax, WPP_GLOBAL_Control
0x1800ba596  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba59d  cmp     rcx, rax
0x1800ba5a0  jz      short loc_1800BA5CA
0x1800ba5a2  test    byte ptr [rcx+1Ch], 1
0x1800ba5a6  jz      short loc_1800BA5CA
0x1800ba5a8  cmp     byte ptr [rcx+19h], 2
0x1800ba5ac  jb      short loc_1800BA5CA
0x1800ba5ae  mov     edx, 0B9h
0x1800ba5b3  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800ba5ba  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800ba5c1  mov     rcx, [rcx+10h]
0x1800ba5c5  call    WPP_SF_s
0x1800ba5ca  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800ba5d1  lea     rcx, [rsp+440h+pExceptionObject]; pExceptionObject
0x1800ba5d6  call    _CxxThrowException_0
0x1800ba5dc  lea     rcx, [rsp+440h+var_3E8]
0x1800ba5e1  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800ba5e7  nop
0x1800ba5e8  lea     rcx, [rsp+440h+var_3C8]
0x1800ba5ed  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800ba5f3  nop
0x1800ba5f4  lea     rcx, [rsp+440h+var_408]
0x1800ba5f9  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800ba5ff  nop
0x1800ba600  lea     rcx, [rbp+340h+var_3A8]
0x1800ba604  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800ba60a  nop
0x1800ba60b  lea     rcx, [rbp+340h+var_380]; this
0x1800ba60f  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800ba614  mov     rcx, [rbp+340h+var_20]
0x1800ba61b  xor     rcx, rsp; StackCookie
0x1800ba61e  call    __security_check_cookie
0x1800ba623  mov     rbx, [rsp+440h+arg_10]
0x1800ba62b  add     rsp, 430h
0x1800ba632  pop     rdi
0x1800ba633  pop     rsi
0x1800ba634  pop     rbp
0x1800ba635  retn
```
