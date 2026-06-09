# CArbitratorConfiguration::Init(void)

- ea: `0x1800b35c4`
- end: `0x1800b38b5`
- name: `?Init@CArbitratorConfiguration@@QEAAXXZ`
- size: `753`
- prototype: `void __fastcall(CArbitratorConfiguration *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180093ec4`

## callees

- `0x18006abcc`
- `0x180085c70`
- `0x180086358`
- `0x18008846c`
- `0x18008a658`
- `0x1800b35c4`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b3731`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b3731`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b368d`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b368d`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b37dd`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b37dd`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b37d1`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b37d1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b371f`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b37c6`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b388a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b371f`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b37c6`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b388a`
- `wbemcomn!GetMemLogObject` at `0x1800b361b`
- `wbemcomn!GetMemLogObject` at `0x1800b36b9`
- `wbemcomn!GetMemLogObject` at `0x1800b3760`
- `wbemcomn!GetMemLogObject` at `0x1800b3824`
- `wbemcomn!GetMemLogObject` at `0x1800b361b`
- `wbemcomn!GetMemLogObject` at `0x1800b36b9`
- `wbemcomn!GetMemLogObject` at `0x1800b3760`
- `wbemcomn!GetMemLogObject` at `0x1800b3824`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3629`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b36c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b376e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3832`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3629`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b36c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b376e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b3832`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b360c`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b360c`

## string_xrefs

- `0x1800b367c`: `__ArbitratorConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CArbitratorConfiguration::Init(CArbitratorConfiguration *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  int i; // ebx
  __int64 v6; // rdx
  CMemoryLog *v7; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v10[40]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v11[864]; // [rsp+80h] [rbp-80h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v11);
  CSystemClass::Init((CSystemClass *)v11);
  if ( CWbemClass::CreateDerivedClass(this, (struct CWbemClass *)v11, 0, 0) == -2147217402 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        626,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v9, 8, L"__ArbitratorConfiguration");
  if ( (*(unsigned int (__fastcall **)(CArbitratorConfiguration *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
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
        627,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v9);
  CVar::CVar((CVar *)v9, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CArbitratorConfiguration *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 984LL))(
         this,
         L"singleton",
         v9,
         19) == -2147217402 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        628,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v9);
  CVar::CVar((CVar *)v10);
  CVar::SetAsNull((CVar *)v10);
  for ( i = 0; ; ++i )
  {
    v6 = (__int64)*(&g_arbitratorConfigurationDefaults + 2 * i);
    if ( !v6 )
      break;
    if ( (*(unsigned int (__fastcall **)(CArbitratorConfiguration *, __int64, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
           this,
           v6,
           v10,
           19) == -2147217402 )
    {
      v7 = GetMemLogObject();
      CMemoryLog::Write(v7, -2);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          629,
          WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
  }
  CVar::~CVar((CVar *)v10);
  CSystemEventClass::~CSystemEventClass((CSystemEventClass *)v11);
}

```

## disassembly

```asm
0x1800b35c4  push    rbp
0x1800b35c6  push    rbx
0x1800b35c7  push    rsi
0x1800b35c8  push    rdi
0x1800b35c9  lea     rbp, [rsp-2F8h]
0x1800b35d1  sub     rsp, 3F8h
0x1800b35d8  mov     rax, cs:__security_cookie
0x1800b35df  xor     rax, rsp
0x1800b35e2  mov     [rbp+310h+var_30], rax
0x1800b35e9  mov     rdi, rcx
0x1800b35ec  lea     rcx, [rbp+310h+var_390]; this
0x1800b35f0  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800b35f5  nop
0x1800b35f6  lea     rcx, [rbp+310h+var_390]; this
0x1800b35fa  call    ?Init@CSystemClass@@QEAAXXZ; CSystemClass::Init(void)
0x1800b35ff  xor     r9d, r9d
0x1800b3602  xor     r8d, r8d
0x1800b3605  lea     rdx, [rbp+310h+var_390]
0x1800b3609  mov     rcx, rdi
0x1800b360c  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800b3612  mov     esi, 80041006h
0x1800b3617  cmp     eax, esi
0x1800b3619  jnz     short loc_1800B367C
0x1800b361b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b3621  mov     edx, 0FFFFFFFEh
0x1800b3626  mov     rcx, rax
0x1800b3629  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b362f  lea     rax, WPP_GLOBAL_Control
0x1800b3636  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b363d  cmp     rcx, rax
0x1800b3640  jz      short loc_1800B366A
0x1800b3642  test    byte ptr [rcx+1Ch], 1
0x1800b3646  jz      short loc_1800B366A
0x1800b3648  cmp     byte ptr [rcx+19h], 2
0x1800b364c  jb      short loc_1800B366A
0x1800b364e  mov     edx, 272h
0x1800b3653  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b365a  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b3661  mov     rcx, [rcx+10h]
0x1800b3665  call    WPP_SF_s
0x1800b366a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b3671  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b3676  call    _CxxThrowException_0
0x1800b367c  lea     r8, aArbitratorconf; "__ArbitratorConfiguration"
0x1800b3683  mov     edx, 8
0x1800b3688  lea     rcx, [rsp+410h+var_3D8]
0x1800b368d  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b3693  nop
0x1800b3694  mov     rax, [rdi]
0x1800b3697  xor     r9d, r9d
0x1800b369a  lea     r8, [rsp+410h+var_3D8]
0x1800b369f  lea     rdx, aClass_0; "__CLASS"
0x1800b36a6  mov     rcx, rdi
0x1800b36a9  mov     rax, [rax+368h]
0x1800b36b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b36b5  cmp     eax, esi
0x1800b36b7  jnz     short loc_1800B371A
0x1800b36b9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b36bf  mov     edx, 0FFFFFFFEh
0x1800b36c4  mov     rcx, rax
0x1800b36c7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b36cd  lea     rax, WPP_GLOBAL_Control
0x1800b36d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b36db  cmp     rcx, rax
0x1800b36de  jz      short loc_1800B3708
0x1800b36e0  test    byte ptr [rcx+1Ch], 1
0x1800b36e4  jz      short loc_1800B3708
0x1800b36e6  cmp     byte ptr [rcx+19h], 2
0x1800b36ea  jb      short loc_1800B3708
0x1800b36ec  mov     edx, 273h
0x1800b36f1  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b36f8  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b36ff  mov     rcx, [rcx+10h]
0x1800b3703  call    WPP_SF_s
0x1800b3708  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b370f  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b3714  call    _CxxThrowException_0
0x1800b371a  lea     rcx, [rsp+410h+var_3D8]
0x1800b371f  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b3725  or      edx, 0FFFFFFFFh
0x1800b3728  lea     r8d, [rdx+0Ch]
0x1800b372c  lea     rcx, [rsp+410h+var_3D8]
0x1800b3731  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800b3737  nop
0x1800b3738  mov     rax, [rdi]
0x1800b373b  mov     r9d, 13h
0x1800b3741  lea     r8, [rsp+410h+var_3D8]
0x1800b3746  lea     rdx, aSingleton; "singleton"
0x1800b374d  mov     rcx, rdi
0x1800b3750  mov     rax, [rax+3D8h]
0x1800b3757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b375c  cmp     eax, esi
0x1800b375e  jnz     short loc_1800B37C1
0x1800b3760  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b3766  mov     edx, 0FFFFFFFEh
0x1800b376b  mov     rcx, rax
0x1800b376e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b3774  lea     rax, WPP_GLOBAL_Control
0x1800b377b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3782  cmp     rcx, rax
0x1800b3785  jz      short loc_1800B37AF
0x1800b3787  test    byte ptr [rcx+1Ch], 1
0x1800b378b  jz      short loc_1800B37AF
0x1800b378d  cmp     byte ptr [rcx+19h], 2
0x1800b3791  jb      short loc_1800B37AF
0x1800b3793  mov     edx, 274h
0x1800b3798  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b379f  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b37a6  mov     rcx, [rcx+10h]
0x1800b37aa  call    WPP_SF_s
0x1800b37af  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b37b6  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b37bb  call    _CxxThrowException_0
0x1800b37c1  lea     rcx, [rsp+410h+var_3D8]
0x1800b37c6  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b37cc  lea     rcx, [rsp+410h+var_3B8]
0x1800b37d1  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800b37d7  nop
0x1800b37d8  lea     rcx, [rsp+410h+var_3B8]
0x1800b37dd  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800b37e3  xor     ebx, ebx
0x1800b37e5  movsxd  rax, ebx
0x1800b37e8  add     rax, rax
0x1800b37eb  lea     rdx, ?g_arbitratorConfigurationDefaults@@3PAU_unnamed_type_g_arbitratorConfigurationDefaults_@@A; _unnamed_type_g_arbitratorConfigurationDefaults_ near * g_arbitratorConfigurationDefaults
0x1800b37f2  mov     rdx, [rdx+rax*8]
0x1800b37f6  test    rdx, rdx
0x1800b37f9  jz      loc_1800B3885
0x1800b37ff  mov     rax, [rdi]
0x1800b3802  mov     r9d, 13h
0x1800b3808  lea     r8, [rsp+410h+var_3B8]
0x1800b380d  mov     rcx, rdi
0x1800b3810  mov     rax, [rax+368h]
0x1800b3817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b381c  cmp     eax, esi
0x1800b381e  jz      short loc_1800B3824
0x1800b3820  inc     ebx
0x1800b3822  jmp     short loc_1800B37E5
0x1800b3824  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b382a  mov     edx, 0FFFFFFFEh
0x1800b382f  mov     rcx, rax
0x1800b3832  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b3838  lea     rax, WPP_GLOBAL_Control
0x1800b383f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3846  cmp     rcx, rax
0x1800b3849  jz      short loc_1800B3873
0x1800b384b  test    byte ptr [rcx+1Ch], 1
0x1800b384f  jz      short loc_1800B3873
0x1800b3851  cmp     byte ptr [rcx+19h], 2
0x1800b3855  jb      short loc_1800B3873
0x1800b3857  mov     edx, 275h
0x1800b385c  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b3863  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b386a  mov     rcx, [rcx+10h]
0x1800b386e  call    WPP_SF_s
0x1800b3873  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b387a  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x1800b387f  call    _CxxThrowException_0
0x1800b3885  lea     rcx, [rsp+410h+var_3B8]
0x1800b388a  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b3890  nop
0x1800b3891  lea     rcx, [rbp+310h+var_390]; this
0x1800b3895  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800b389a  mov     rcx, [rbp+310h+var_30]
0x1800b38a1  xor     rcx, rsp; StackCookie
0x1800b38a4  call    __security_check_cookie
0x1800b38a9  add     rsp, 3F8h
0x1800b38b0  pop     rdi
0x1800b38b1  pop     rsi
0x1800b38b2  pop     rbx
0x1800b38b3  pop     rbp
0x1800b38b4  retn
```
