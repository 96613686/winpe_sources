# CProviderHostQuotaConfiguration::Init(void)

- ea: `0x1800b863c`
- end: `0x1800b89e5`
- name: `?Init@CProviderHostQuotaConfiguration@@QEAAXXZ`
- size: `937`
- prototype: `void __fastcall(CProviderHostQuotaConfiguration *__hidden this)`
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
- `0x1800b863c`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b87b2`
- `wbemcomn!??0CVar@@QEAA@FH@Z` at `0x1800b87b2`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b870e`
- `wbemcomn!??0CVar@@QEAA@HPEAG@Z` at `0x1800b870e`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b885e`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x1800b885e`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b8852`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800b8852`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b87a0`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b8847`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b89ae`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b87a0`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b8847`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800b89ae`
- `wbemcomn!GetMemLogObject` at `0x1800b869c`
- `wbemcomn!GetMemLogObject` at `0x1800b873a`
- `wbemcomn!GetMemLogObject` at `0x1800b87e1`
- `wbemcomn!GetMemLogObject` at `0x1800b88a9`
- `wbemcomn!GetMemLogObject` at `0x1800b8948`
- `wbemcomn!GetMemLogObject` at `0x1800b869c`
- `wbemcomn!GetMemLogObject` at `0x1800b873a`
- `wbemcomn!GetMemLogObject` at `0x1800b87e1`
- `wbemcomn!GetMemLogObject` at `0x1800b88a9`
- `wbemcomn!GetMemLogObject` at `0x1800b8948`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b86aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b8748`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b87ef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b88b7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b8956`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b86aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b8748`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b87ef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b88b7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800b8956`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b868d`
- `FastProx!?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z` at `0x1800b868d`

## string_xrefs

- `0x1800b86fd`: `__ProviderHostQuotaConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CProviderHostQuotaConfiguration::Init(CProviderHostQuotaConfiguration *this)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v3; // rax
  CMemoryLog *v4; // rax
  int i; // ebx
  __int64 v6; // rdx
  CMemoryLog *v7; // rax
  int j; // ebx
  __int64 v9; // rdx
  CMemoryLog *v10; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[40]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v14[864]; // [rsp+80h] [rbp-80h] BYREF

  CTimerNextFiringClass::CTimerNextFiringClass((CTimerNextFiringClass *)v14);
  CSystemClass::Init((CSystemClass *)v14);
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
        632,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::CVar((CVar *)v12, 8, L"__ProviderHostQuotaConfiguration");
  if ( (*(unsigned int (__fastcall **)(CProviderHostQuotaConfiguration *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
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
        633,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v12);
  CVar::CVar((CVar *)v12, -1, 11);
  if ( (*(unsigned int (__fastcall **)(CProviderHostQuotaConfiguration *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)this + 984LL))(
         this,
         L"singleton",
         v12,
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
        634,
        WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  CVar::~CVar((CVar *)v12);
  CVar::CVar((CVar *)v13);
  CVar::SetAsNull((CVar *)v13);
  for ( i = 0; ; ++i )
  {
    v6 = (__int64)*(&g_ProviderHostQuotaConfigurationDefaultsUint32 + 2 * i);
    if ( !v6 )
      break;
    if ( (*(unsigned int (__fastcall **)(CProviderHostQuotaConfiguration *, __int64, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
           this,
           v6,
           v13,
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
          635,
          WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
  }
  for ( j = 0; ; ++j )
  {
    v9 = (__int64)*(&g_ProviderHostQuotaConfigurationDefaultsUint64 + 2 * j);
    if ( !v9 )
      break;
    if ( (*(unsigned int (__fastcall **)(CProviderHostQuotaConfiguration *, __int64, _BYTE *, __int64))(*(_QWORD *)this + 872LL))(
           this,
           v9,
           v13,
           21) == -2147217402 )
    {
      v10 = GetMemLogObject();
      CMemoryLog::Write(v10, -2);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          636,
          WPP_11abc31364483e5023fa9c492ecbf840_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
  }
  CVar::~CVar((CVar *)v13);
  CSystemEventClass::~CSystemEventClass((CSystemEventClass *)v14);
}

```

## disassembly

```asm
0x1800b863c  mov     [rsp-8+arg_8], rbx
0x1800b8641  mov     [rsp-8+arg_10], rsi
0x1800b8646  push    rbp
0x1800b8647  push    rdi
0x1800b8648  push    r14
0x1800b864a  lea     rbp, [rsp-2F0h]
0x1800b8652  sub     rsp, 3F0h
0x1800b8659  mov     rax, cs:__security_cookie
0x1800b8660  xor     rax, rsp
0x1800b8663  mov     [rbp+300h+var_20], rax
0x1800b866a  mov     rdi, rcx
0x1800b866d  lea     rcx, [rbp+300h+var_380]; this
0x1800b8671  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800b8676  nop
0x1800b8677  lea     rcx, [rbp+300h+var_380]; this
0x1800b867b  call    ?Init@CSystemClass@@QEAAXXZ; CSystemClass::Init(void)
0x1800b8680  xor     r9d, r9d
0x1800b8683  xor     r8d, r8d
0x1800b8686  lea     rdx, [rbp+300h+var_380]
0x1800b868a  mov     rcx, rdi
0x1800b868d  call    cs:__imp_?CreateDerivedClass@CWbemClass@@QEAAJPEAV1@HPEAVCDecorationPart@@@Z; CWbemClass::CreateDerivedClass(CWbemClass *,int,CDecorationPart *)
0x1800b8693  mov     esi, 80041006h
0x1800b8698  cmp     eax, esi
0x1800b869a  jnz     short loc_1800B86FD
0x1800b869c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b86a2  mov     edx, 0FFFFFFFEh
0x1800b86a7  mov     rcx, rax
0x1800b86aa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b86b0  lea     rax, WPP_GLOBAL_Control
0x1800b86b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b86be  cmp     rcx, rax
0x1800b86c1  jz      short loc_1800B86EB
0x1800b86c3  test    byte ptr [rcx+1Ch], 1
0x1800b86c7  jz      short loc_1800B86EB
0x1800b86c9  cmp     byte ptr [rcx+19h], 2
0x1800b86cd  jb      short loc_1800B86EB
0x1800b86cf  mov     edx, 278h
0x1800b86d4  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b86db  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b86e2  mov     rcx, [rcx+10h]
0x1800b86e6  call    WPP_SF_s
0x1800b86eb  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b86f2  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x1800b86f7  call    _CxxThrowException_0
0x1800b86fd  lea     r8, aProviderhostqu; "__ProviderHostQuotaConfiguration"
0x1800b8704  mov     edx, 8
0x1800b8709  lea     rcx, [rsp+400h+var_3C8]
0x1800b870e  call    cs:__imp_??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x1800b8714  nop
0x1800b8715  mov     rax, [rdi]
0x1800b8718  xor     r9d, r9d
0x1800b871b  lea     r8, [rsp+400h+var_3C8]
0x1800b8720  lea     rdx, aClass_0; "__CLASS"
0x1800b8727  mov     rcx, rdi
0x1800b872a  mov     rax, [rax+368h]
0x1800b8731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8736  cmp     eax, esi
0x1800b8738  jnz     short loc_1800B879B
0x1800b873a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b8740  mov     edx, 0FFFFFFFEh
0x1800b8745  mov     rcx, rax
0x1800b8748  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b874e  lea     rax, WPP_GLOBAL_Control
0x1800b8755  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b875c  cmp     rcx, rax
0x1800b875f  jz      short loc_1800B8789
0x1800b8761  test    byte ptr [rcx+1Ch], 1
0x1800b8765  jz      short loc_1800B8789
0x1800b8767  cmp     byte ptr [rcx+19h], 2
0x1800b876b  jb      short loc_1800B8789
0x1800b876d  mov     edx, 279h
0x1800b8772  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b8779  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b8780  mov     rcx, [rcx+10h]
0x1800b8784  call    WPP_SF_s
0x1800b8789  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b8790  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x1800b8795  call    _CxxThrowException_0
0x1800b879b  lea     rcx, [rsp+400h+var_3C8]
0x1800b87a0  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b87a6  or      edx, 0FFFFFFFFh
0x1800b87a9  lea     r8d, [rdx+0Ch]
0x1800b87ad  lea     rcx, [rsp+400h+var_3C8]
0x1800b87b2  call    cs:__imp_??0CVar@@QEAA@FH@Z; CVar::CVar(short,int)
0x1800b87b8  nop
0x1800b87b9  mov     rax, [rdi]
0x1800b87bc  mov     r9d, 13h
0x1800b87c2  lea     r8, [rsp+400h+var_3C8]
0x1800b87c7  lea     rdx, aSingleton; "singleton"
0x1800b87ce  mov     rcx, rdi
0x1800b87d1  mov     rax, [rax+3D8h]
0x1800b87d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b87dd  cmp     eax, esi
0x1800b87df  jnz     short loc_1800B8842
0x1800b87e1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b87e7  mov     edx, 0FFFFFFFEh
0x1800b87ec  mov     rcx, rax
0x1800b87ef  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b87f5  lea     rax, WPP_GLOBAL_Control
0x1800b87fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8803  cmp     rcx, rax
0x1800b8806  jz      short loc_1800B8830
0x1800b8808  test    byte ptr [rcx+1Ch], 1
0x1800b880c  jz      short loc_1800B8830
0x1800b880e  cmp     byte ptr [rcx+19h], 2
0x1800b8812  jb      short loc_1800B8830
0x1800b8814  mov     edx, 27Ah
0x1800b8819  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b8820  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b8827  mov     rcx, [rcx+10h]
0x1800b882b  call    WPP_SF_s
0x1800b8830  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b8837  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x1800b883c  call    _CxxThrowException_0
0x1800b8842  lea     rcx, [rsp+400h+var_3C8]
0x1800b8847  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b884d  lea     rcx, [rsp+400h+var_3A8]
0x1800b8852  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800b8858  nop
0x1800b8859  lea     rcx, [rsp+400h+var_3A8]
0x1800b885e  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x1800b8864  xor     ebx, ebx
0x1800b8866  lea     r14, __ImageBase
0x1800b886d  movsxd  rax, ebx
0x1800b8870  add     rax, rax
0x1800b8873  mov     rdx, rva ?g_ProviderHostQuotaConfigurationDefaultsUint32@@3PAU_unnamed_type_g_ProviderHostQuotaConfigurationDefaultsUint32_@@A[r14+rax*8]; _unnamed_type_g_ProviderHostQuotaConfigurationDefaultsUint32_ near * g_ProviderHostQuotaConfigurationDefaultsUint32 ...
0x1800b887b  test    rdx, rdx
0x1800b887e  jz      loc_1800B890A
0x1800b8884  mov     rax, [rdi]
0x1800b8887  mov     r9d, 13h
0x1800b888d  lea     r8, [rsp+400h+var_3A8]
0x1800b8892  mov     rcx, rdi
0x1800b8895  mov     rax, [rax+368h]
0x1800b889c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b88a1  cmp     eax, esi
0x1800b88a3  jz      short loc_1800B88A9
0x1800b88a5  inc     ebx
0x1800b88a7  jmp     short loc_1800B886D
0x1800b88a9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b88af  mov     edx, 0FFFFFFFEh
0x1800b88b4  mov     rcx, rax
0x1800b88b7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b88bd  lea     rax, WPP_GLOBAL_Control
0x1800b88c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b88cb  cmp     rcx, rax
0x1800b88ce  jz      short loc_1800B88F8
0x1800b88d0  test    byte ptr [rcx+1Ch], 1
0x1800b88d4  jz      short loc_1800B88F8
0x1800b88d6  cmp     byte ptr [rcx+19h], 2
0x1800b88da  jb      short loc_1800B88F8
0x1800b88dc  mov     edx, 27Bh
0x1800b88e1  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b88e8  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b88ef  mov     rcx, [rcx+10h]
0x1800b88f3  call    WPP_SF_s
0x1800b88f8  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b88ff  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x1800b8904  call    _CxxThrowException_0
0x1800b890a  xor     ebx, ebx
0x1800b890c  movsxd  rax, ebx
0x1800b890f  add     rax, rax
0x1800b8912  mov     rdx, rva ?g_ProviderHostQuotaConfigurationDefaultsUint64@@3PAU_unnamed_type_g_ProviderHostQuotaConfigurationDefaultsUint64_@@A[r14+rax*8]; _unnamed_type_g_ProviderHostQuotaConfigurationDefaultsUint64_ near * g_ProviderHostQuotaConfigurationDefaultsUint64 ...
0x1800b891a  test    rdx, rdx
0x1800b891d  jz      loc_1800B89A9
0x1800b8923  mov     rax, [rdi]
0x1800b8926  mov     r9d, 15h
0x1800b892c  lea     r8, [rsp+400h+var_3A8]
0x1800b8931  mov     rcx, rdi
0x1800b8934  mov     rax, [rax+368h]
0x1800b893b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8940  cmp     eax, esi
0x1800b8942  jz      short loc_1800B8948
0x1800b8944  inc     ebx
0x1800b8946  jmp     short loc_1800B890C
0x1800b8948  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800b894e  mov     edx, 0FFFFFFFEh
0x1800b8953  mov     rcx, rax
0x1800b8956  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800b895c  lea     rax, WPP_GLOBAL_Control
0x1800b8963  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b896a  cmp     rcx, rax
0x1800b896d  jz      short loc_1800B8997
0x1800b896f  test    byte ptr [rcx+1Ch], 1
0x1800b8973  jz      short loc_1800B8997
0x1800b8975  cmp     byte ptr [rcx+19h], 2
0x1800b8979  jb      short loc_1800B8997
0x1800b897b  mov     edx, 27Ch
0x1800b8980  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800b8987  lea     r8, WPP_11abc31364483e5023fa9c492ecbf840_Traceguids
0x1800b898e  mov     rcx, [rcx+10h]
0x1800b8992  call    WPP_SF_s
0x1800b8997  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800b899e  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x1800b89a3  call    _CxxThrowException_0
0x1800b89a9  lea     rcx, [rsp+400h+var_3A8]
0x1800b89ae  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800b89b4  nop
0x1800b89b5  lea     rcx, [rbp+300h+var_380]; this
0x1800b89b9  call    ??1CSystemEventClass@@UEAA@XZ; CSystemEventClass::~CSystemEventClass(void)
0x1800b89be  mov     rcx, [rbp+300h+var_20]
0x1800b89c5  xor     rcx, rsp; StackCookie
0x1800b89c8  call    __security_check_cookie
0x1800b89cd  lea     r11, [rsp+400h+var_10]
0x1800b89d5  mov     rbx, [r11+28h]
0x1800b89d9  mov     rsi, [r11+30h]
0x1800b89dd  mov     rsp, r11
0x1800b89e0  pop     r14
0x1800b89e2  pop     rdi
0x1800b89e3  pop     rbp
0x1800b89e4  retn
```
