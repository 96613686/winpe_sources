# ConfigMgr::SetAdapStatusObject(IWmiDbHandle *,IWmiDbSession *)

- ea: `0x1800a6d08`
- end: `0x1800a7247`
- name: `?SetAdapStatusObject@ConfigMgr@@SAJPEAUIWmiDbHandle@@PEAUIWmiDbSession@@@Z`
- size: `1343`
- prototype: `__int64 __fastcall(struct IWmiDbHandle *, struct IWmiDbSession *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a7250`

## callees

- `0x18000b140`
- `0x180011700`
- `0x18003cfe0`
- `0x18004b934`
- `0x180093be8`
- `0x1800a3e60`
- `0x1800a6d08`
- `0x1800b2c10`
- `0x1800b2fe4`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a6d68`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a6e33`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a6d68`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a6e33`
- `wbemcomn!GetMemLogObject` at `0x1800a6dc7`
- `wbemcomn!GetMemLogObject` at `0x1800a6eae`
- `wbemcomn!GetMemLogObject` at `0x1800a6f4c`
- `wbemcomn!GetMemLogObject` at `0x1800a6fe3`
- `wbemcomn!GetMemLogObject` at `0x1800a7081`
- `wbemcomn!GetMemLogObject` at `0x1800a7127`
- `wbemcomn!GetMemLogObject` at `0x1800a71e4`
- `wbemcomn!GetMemLogObject` at `0x1800a6dc7`
- `wbemcomn!GetMemLogObject` at `0x1800a6eae`
- `wbemcomn!GetMemLogObject` at `0x1800a6f4c`
- `wbemcomn!GetMemLogObject` at `0x1800a6fe3`
- `wbemcomn!GetMemLogObject` at `0x1800a7081`
- `wbemcomn!GetMemLogObject` at `0x1800a7127`
- `wbemcomn!GetMemLogObject` at `0x1800a71e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a6dd7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a6ebe`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a6f57`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a6fee`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a708c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a7132`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a71ef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a6dd7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a6ebe`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a6f57`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a6fee`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a708c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a7132`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a71ef`
- `FastProx!?QueryInterface@CWbemObject@@UEAAJAEBU_GUID@@PEAPEAX@Z` at `0x1800a6f3c`
- `FastProx!?QueryInterface@CWbemObject@@UEAAJAEBU_GUID@@PEAPEAX@Z` at `0x1800a7071`
- `FastProx!?QueryInterface@CWbemObject@@UEAAJAEBU_GUID@@PEAPEAX@Z` at `0x1800a6f3c`
- `FastProx!?QueryInterface@CWbemObject@@UEAAJAEBU_GUID@@PEAPEAX@Z` at `0x1800a7071`
- `FastProx!??0CWbemInstance@@QEAA@XZ` at `0x1800a6e4c`
- `FastProx!??0CWbemInstance@@QEAA@XZ` at `0x1800a6e4c`
- `FastProx!??0CWbemClass@@QEAA@XZ` at `0x1800a6d81`
- `FastProx!??0CWbemClass@@QEAA@XZ` at `0x1800a6d81`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall ConfigMgr::SetAdapStatusObject(struct IWmiDbHandle *a1, struct IWmiDbSession *a2)
{
  CProviderClass *v5; // rax
  CProviderClass *v6; // rbx
  CMemoryLog *MemLogObject; // rax
  CAdapStatusInstance *v8; // rax
  CAdapStatusInstance *v9; // rdi
  CMemoryLog *v10; // rax
  int v11; // ebx
  const struct _GUID *v12; // r8
  CMemoryLog *v13; // rax
  int v14; // ebx
  CMemoryLog *v15; // rax
  const struct _GUID *v16; // r8
  CMemoryLog *v17; // rax
  unsigned int v18; // ebx
  CMemoryLog *v19; // rax
  void *v20; // [rsp+38h] [rbp-40h] BYREF
  void *v21; // [rsp+40h] [rbp-38h] BYREF
  void *v22; // [rsp+48h] [rbp-30h] BYREF
  struct IWbemClassObject *v23; // [rsp+50h] [rbp-28h] BYREF
  _QWORD v24[4]; // [rsp+58h] [rbp-20h] BYREF
  CProviderClass *v25; // [rsp+90h] [rbp+18h] BYREF
  CAdapStatusInstance *v26; // [rsp+98h] [rbp+20h] BYREF

  v23 = 0;
  if ( (int)CRepository::GetObjectW(a2, a1, L"__AdapStatus=@", 0, &v23) >= 0 && v23 )
  {
    ((void (__fastcall *)(struct IWbemClassObject *))v23->lpVtbl->Release)(v23);
    return 0;
  }
  v5 = (CProviderClass *)CWin32DefaultArena::WbemMemAlloc(0x360u);
  v6 = v5;
  v25 = v5;
  if ( v5 )
  {
    CWbemClass::CWbemClass(v5);
    *(_QWORD *)v6 = &CMethodEventClass::`vftable'{for `_IWmiObject'};
    *((_QWORD *)v6 + 1) = &CThisNamespaceInstance::`vftable'{for `IMarshal'};
    *((_QWORD *)v6 + 2) = &CParametersClass::`vftable'{for `IWbemPropertySource'};
    *((_QWORD *)v6 + 3) = &CFilterConsumerBindingClass::`vftable'{for `IErrorInfo'};
    *((_QWORD *)v6 + 4) = &CEventFilterClass::`vftable'{for `IWbemConstructClassObject'};
  }
  else
  {
    v6 = 0;
  }
  if ( !v6 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  v25 = v6;
  CAdapStatusClass::Init(v6);
  v8 = (CAdapStatusInstance *)CWin32DefaultArena::WbemMemAlloc(0x2A0u);
  v9 = v8;
  v26 = v8;
  if ( v8 )
  {
    CWbemInstance::CWbemInstance(v8);
    *(_QWORD *)v9 = &CThisNamespaceInstance::`vftable'{for `_IWmiObject'};
    *((_QWORD *)v9 + 1) = &CThisNamespaceInstance::`vftable'{for `IMarshal'};
    *((_QWORD *)v9 + 2) = &CParametersClass::`vftable'{for `IWbemPropertySource'};
    *((_QWORD *)v9 + 3) = &CFilterConsumerBindingClass::`vftable'{for `IErrorInfo'};
    *((_QWORD *)v9 + 4) = &CCacheControlInstance::`vftable'{for `IWbemConstructClassObject'};
    *((_QWORD *)v9 + 19) = &CAdapStatusInstance::`vftable'{for `CInstancePartContainer'};
    *((_QWORD *)v9 + 20) = &CSystemConfigInstance::`vftable'{for `CClassPartContainer'};
  }
  else
  {
    v9 = 0;
  }
  if ( !v9 )
  {
    v10 = GetMemLogObject();
    CMemoryLog::Write(v10, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, 2147749894LL);
    }
    CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(&v25);
    return 2147749894LL;
  }
  v26 = v9;
  CAdapStatusInstance::Init(v9, v6);
  v21 = 0;
  v11 = CWbemObject::QueryInterface(v6, &IID_IWbemClassObject, &v21);
  if ( v11 < 0 )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, v11);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
        (unsigned int)v11);
    }
    CDeleteMe<CAdapStatusInstance>::~CDeleteMe<CAdapStatusInstance>(&v26);
    CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(&v25);
    return (unsigned int)v11;
  }
  v20 = v21;
  v14 = CRepository::PutObject(a2, a1, v12, v21, 0x1000u);
  if ( v14 < 0 )
  {
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, v14);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
        (unsigned int)v14);
    }
LABEL_33:
    CReleaseMe::release((CReleaseMe *)&v20);
    CDeleteMe<CAdapStatusInstance>::~CDeleteMe<CAdapStatusInstance>(&v26);
    CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(&v25);
    return (unsigned int)v14;
  }
  v22 = 0;
  v14 = CWbemObject::QueryInterface(v9, &IID_IWbemClassObject, &v22);
  if ( v14 < 0 )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, v14);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
        (unsigned int)v14);
    }
    goto LABEL_33;
  }
  v24[0] = v22;
  v18 = CRepository::PutObject(a2, a1, v16, v22, 0x1000u);
  if ( (v18 & 0x80000000) == 0 )
  {
    CReleaseMe::release((CReleaseMe *)v24);
    CReleaseMe::release((CReleaseMe *)&v20);
    CDeleteMe<CAdapStatusInstance>::~CDeleteMe<CAdapStatusInstance>(&v26);
    CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(&v25);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, v18);
    }
    return v18;
  }
  else
  {
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, v18);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, v18);
    }
    CReleaseMe::release((CReleaseMe *)v24);
    CReleaseMe::release((CReleaseMe *)&v20);
    CDeleteMe<CAdapStatusInstance>::~CDeleteMe<CAdapStatusInstance>(&v26);
    CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(&v25);
    return v18;
  }
}

```

## disassembly

```asm
0x1800a6d08  mov     r11, rsp
0x1800a6d0b  mov     [r11+8], rbx
0x1800a6d0f  push    rsi
0x1800a6d10  push    rdi
0x1800a6d11  push    r14
0x1800a6d13  sub     rsp, 60h
0x1800a6d17  mov     rsi, rdx
0x1800a6d1a  mov     r14, rcx
0x1800a6d1d  mov     qword ptr [r11-28h], 0
0x1800a6d25  lea     rax, [r11-28h]
0x1800a6d29  mov     [r11-58h], rax
0x1800a6d2d  xor     r9d, r9d; unsigned int
0x1800a6d30  lea     r8, aAdapstatus_1; "__AdapStatus=@"
0x1800a6d37  mov     rdx, rcx; struct IWmiDbHandle *
0x1800a6d3a  mov     rcx, rsi; struct IWmiDbSession *
0x1800a6d3d  call    ?GetObjectW@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGKPEAPEAUIWbemClassObject@@@Z; CRepository::GetObjectW(IWmiDbSession *,IWmiDbHandle *,ushort const *,ulong,IWbemClassObject * *)
0x1800a6d42  test    eax, eax
0x1800a6d44  js      short loc_1800A6D63
0x1800a6d46  mov     rcx, [rsp+78h+var_28]
0x1800a6d4b  test    rcx, rcx
0x1800a6d4e  jz      short loc_1800A6D63
0x1800a6d50  mov     rax, [rcx]
0x1800a6d53  mov     rax, [rax+10h]
0x1800a6d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6d5c  xor     eax, eax
0x1800a6d5e  jmp     loc_1800A7235
0x1800a6d63  mov     ecx, 360h
0x1800a6d68  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800a6d6e  mov     rbx, rax
0x1800a6d71  mov     [rsp+78h+arg_10], rax
0x1800a6d79  test    rax, rax
0x1800a6d7c  jz      short loc_1800A6DC0
0x1800a6d7e  mov     rcx, rax
0x1800a6d81  call    cs:__imp_??0CWbemClass@@QEAA@XZ; CWbemClass::CWbemClass(void)
0x1800a6d87  nop
0x1800a6d88  lea     rax, ??_7CMethodEventClass@@6B_IWmiObject@@@; const CMethodEventClass::`vftable'{for `_IWmiObject'}
0x1800a6d8f  mov     [rbx], rax
0x1800a6d92  lea     rax, ??_7CThisNamespaceInstance@@6BIMarshal@@@; const CThisNamespaceInstance::`vftable'{for `IMarshal'}
0x1800a6d99  mov     [rbx+8], rax
0x1800a6d9d  lea     rax, ??_7CParametersClass@@6BIWbemPropertySource@@@; const CParametersClass::`vftable'{for `IWbemPropertySource'}
0x1800a6da4  mov     [rbx+10h], rax
0x1800a6da8  lea     rax, ??_7CFilterConsumerBindingClass@@6BIErrorInfo@@@; const CFilterConsumerBindingClass::`vftable'{for `IErrorInfo'}
0x1800a6daf  mov     [rbx+18h], rax
0x1800a6db3  lea     rax, ??_7CEventFilterClass@@6BIWbemConstructClassObject@@@; const CEventFilterClass::`vftable'{for `IWbemConstructClassObject'}
0x1800a6dba  mov     [rbx+20h], rax
0x1800a6dbe  jmp     short loc_1800A6DC2
0x1800a6dc0  xor     ebx, ebx
0x1800a6dc2  test    rbx, rbx
0x1800a6dc5  jnz     short loc_1800A6E1E
0x1800a6dc7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a6dcd  mov     ebx, 80041006h
0x1800a6dd2  mov     edx, ebx
0x1800a6dd4  mov     rcx, rax
0x1800a6dd7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a6ddd  lea     rax, WPP_GLOBAL_Control
0x1800a6de4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6deb  cmp     rcx, rax
0x1800a6dee  jz      short loc_1800A6E17
0x1800a6df0  test    byte ptr [rcx+1Ch], 1
0x1800a6df4  jz      short loc_1800A6E17
0x1800a6df6  cmp     byte ptr [rcx+19h], 2
0x1800a6dfa  jb      short loc_1800A6E17
0x1800a6dfc  mov     edx, 2Bh ; '+'
0x1800a6e01  mov     r9d, 80041006h
0x1800a6e07  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800a6e0e  mov     rcx, [rcx+10h]
0x1800a6e12  call    WPP_SF_d
0x1800a6e17  mov     eax, ebx
0x1800a6e19  jmp     loc_1800A7235
0x1800a6e1e  mov     [rsp+78h+arg_10], rbx
0x1800a6e26  mov     rcx, rbx; this
0x1800a6e29  call    ?Init@CAdapStatusClass@@QEAAXXZ; CAdapStatusClass::Init(void)
0x1800a6e2e  mov     ecx, 2A0h
0x1800a6e33  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800a6e39  mov     rdi, rax
0x1800a6e3c  mov     [rsp+78h+arg_18], rax
0x1800a6e44  test    rax, rax
0x1800a6e47  jz      short loc_1800A6EA7
0x1800a6e49  mov     rcx, rax
0x1800a6e4c  call    cs:__imp_??0CWbemInstance@@QEAA@XZ; CWbemInstance::CWbemInstance(void)
0x1800a6e52  nop
0x1800a6e53  lea     rax, ??_7CThisNamespaceInstance@@6B_IWmiObject@@@; const CThisNamespaceInstance::`vftable'{for `_IWmiObject'}
0x1800a6e5a  mov     [rdi], rax
0x1800a6e5d  lea     rax, ??_7CThisNamespaceInstance@@6BIMarshal@@@; const CThisNamespaceInstance::`vftable'{for `IMarshal'}
0x1800a6e64  mov     [rdi+8], rax
0x1800a6e68  lea     rax, ??_7CParametersClass@@6BIWbemPropertySource@@@; const CParametersClass::`vftable'{for `IWbemPropertySource'}
0x1800a6e6f  mov     [rdi+10h], rax
0x1800a6e73  lea     rax, ??_7CFilterConsumerBindingClass@@6BIErrorInfo@@@; const CFilterConsumerBindingClass::`vftable'{for `IErrorInfo'}
0x1800a6e7a  mov     [rdi+18h], rax
0x1800a6e7e  lea     rax, ??_7CCacheControlInstance@@6BIWbemConstructClassObject@@@; const CCacheControlInstance::`vftable'{for `IWbemConstructClassObject'}
0x1800a6e85  mov     [rdi+20h], rax
0x1800a6e89  lea     rax, ??_7CAdapStatusInstance@@6BCInstancePartContainer@@@; const CAdapStatusInstance::`vftable'{for `CInstancePartContainer'}
0x1800a6e90  mov     [rdi+98h], rax
0x1800a6e97  lea     rax, ??_7CSystemConfigInstance@@6BCClassPartContainer@@@; const CSystemConfigInstance::`vftable'{for `CClassPartContainer'}
0x1800a6e9e  mov     [rdi+0A0h], rax
0x1800a6ea5  jmp     short loc_1800A6EA9
0x1800a6ea7  xor     edi, edi
0x1800a6ea9  test    rdi, rdi
0x1800a6eac  jnz     short loc_1800A6F11
0x1800a6eae  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a6eb4  mov     ebx, 80041006h
0x1800a6eb9  mov     edx, ebx
0x1800a6ebb  mov     rcx, rax
0x1800a6ebe  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a6ec4  lea     rax, WPP_GLOBAL_Control
0x1800a6ecb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6ed2  cmp     rcx, rax
0x1800a6ed5  jz      short loc_1800A6EFD
0x1800a6ed7  test    byte ptr [rcx+1Ch], 1
0x1800a6edb  jz      short loc_1800A6EFD
0x1800a6edd  cmp     byte ptr [rcx+19h], 2
0x1800a6ee1  jb      short loc_1800A6EFD
0x1800a6ee3  lea     edx, [rdi+2Ch]
0x1800a6ee6  mov     r9d, 80041006h
0x1800a6eec  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800a6ef3  mov     rcx, [rcx+10h]
0x1800a6ef7  call    WPP_SF_d
0x1800a6efc  nop
0x1800a6efd  lea     rcx, [rsp+78h+arg_10]
0x1800a6f05  call    ??1?$CDeleteMe@VCSystemConfigClass@@@@QEAA@XZ; CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(void)
0x1800a6f0a  mov     eax, ebx
0x1800a6f0c  jmp     loc_1800A7235
0x1800a6f11  mov     [rsp+78h+arg_18], rdi
0x1800a6f19  mov     rdx, rbx; struct CAdapStatusClass *
0x1800a6f1c  mov     rcx, rdi; this
0x1800a6f1f  call    ?Init@CAdapStatusInstance@@QEAAXPEAVCAdapStatusClass@@@Z; CAdapStatusInstance::Init(CAdapStatusClass *)
0x1800a6f24  mov     [rsp+78h+var_38], 0
0x1800a6f2d  lea     r8, [rsp+78h+var_38]
0x1800a6f32  lea     rdx, IID_IWbemClassObject
0x1800a6f39  mov     rcx, rbx
0x1800a6f3c  call    cs:__imp_?QueryInterface@CWbemObject@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWbemObject::QueryInterface(_GUID const &,void * *)
0x1800a6f42  mov     ebx, eax
0x1800a6f44  mov     [rsp+78h+var_48], eax
0x1800a6f48  test    eax, eax
0x1800a6f4a  jns     short loc_1800A6FB7
0x1800a6f4c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a6f52  mov     edx, ebx
0x1800a6f54  mov     rcx, rax
0x1800a6f57  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a6f5d  lea     rax, WPP_GLOBAL_Control
0x1800a6f64  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6f6b  cmp     rcx, rax
0x1800a6f6e  jz      short loc_1800A6F95
0x1800a6f70  test    byte ptr [rcx+1Ch], 1
0x1800a6f74  jz      short loc_1800A6F95
0x1800a6f76  cmp     byte ptr [rcx+19h], 2
0x1800a6f7a  jb      short loc_1800A6F95
0x1800a6f7c  mov     edx, 2Dh ; '-'
0x1800a6f81  mov     r9d, ebx
0x1800a6f84  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800a6f8b  mov     rcx, [rcx+10h]
0x1800a6f8f  call    WPP_SF_d
0x1800a6f94  nop
0x1800a6f95  lea     rcx, [rsp+78h+arg_18]
0x1800a6f9d  call    ??1?$CDeleteMe@VCAdapStatusInstance@@@@QEAA@XZ; CDeleteMe<CAdapStatusInstance>::~CDeleteMe<CAdapStatusInstance>(void)
0x1800a6fa2  nop
0x1800a6fa3  lea     rcx, [rsp+78h+arg_10]
0x1800a6fab  call    ??1?$CDeleteMe@VCSystemConfigClass@@@@QEAA@XZ; CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(void)
0x1800a6fb0  mov     eax, ebx
0x1800a6fb2  jmp     loc_1800A7235
0x1800a6fb7  mov     rax, [rsp+78h+var_38]
0x1800a6fbc  mov     [rsp+78h+var_40], rax
0x1800a6fc1  mov     [rsp+78h+var_58], 1000h; unsigned int
0x1800a6fc9  mov     r9, [rsp+78h+var_38]; void *
0x1800a6fce  mov     rdx, r14; struct IWmiDbHandle *
0x1800a6fd1  mov     rcx, rsi; struct IWmiDbSession *
0x1800a6fd4  call    ?PutObject@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@AEBU_GUID@@PEAXK@Z; CRepository::PutObject(IWmiDbSession *,IWmiDbHandle *,_GUID const &,void *,ulong)
0x1800a6fd9  mov     ebx, eax
0x1800a6fdb  mov     [rsp+78h+var_48], eax
0x1800a6fdf  test    eax, eax
0x1800a6fe1  jns     short loc_1800A7059
0x1800a6fe3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a6fe9  mov     edx, ebx
0x1800a6feb  mov     rcx, rax
0x1800a6fee  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a6ff4  lea     rax, WPP_GLOBAL_Control
0x1800a6ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7002  cmp     rcx, rax
0x1800a7005  jz      short loc_1800A702C
0x1800a7007  test    byte ptr [rcx+1Ch], 1
0x1800a700b  jz      short loc_1800A702C
0x1800a700d  cmp     byte ptr [rcx+19h], 2
0x1800a7011  jb      short loc_1800A702C
0x1800a7013  mov     edx, 2Eh ; '.'
0x1800a7018  mov     r9d, ebx
0x1800a701b  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800a7022  mov     rcx, [rcx+10h]
0x1800a7026  call    WPP_SF_d
0x1800a702b  nop
0x1800a702c  lea     rcx, [rsp+78h+var_40]; this
0x1800a7031  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800a7036  nop
0x1800a7037  lea     rcx, [rsp+78h+arg_18]
0x1800a703f  call    ??1?$CDeleteMe@VCAdapStatusInstance@@@@QEAA@XZ; CDeleteMe<CAdapStatusInstance>::~CDeleteMe<CAdapStatusInstance>(void)
0x1800a7044  nop
0x1800a7045  lea     rcx, [rsp+78h+arg_10]
0x1800a704d  call    ??1?$CDeleteMe@VCSystemConfigClass@@@@QEAA@XZ; CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(void)
0x1800a7052  mov     eax, ebx
0x1800a7054  jmp     loc_1800A7235
0x1800a7059  mov     [rsp+78h+var_30], 0
0x1800a7062  lea     r8, [rsp+78h+var_30]
0x1800a7067  lea     rdx, IID_IWbemClassObject
0x1800a706e  mov     rcx, rdi
0x1800a7071  call    cs:__imp_?QueryInterface@CWbemObject@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWbemObject::QueryInterface(_GUID const &,void * *)
0x1800a7077  mov     ebx, eax
0x1800a7079  mov     [rsp+78h+var_48], eax
0x1800a707d  test    eax, eax
0x1800a707f  jns     short loc_1800A70F7
0x1800a7081  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a7087  mov     edx, ebx
0x1800a7089  mov     rcx, rax
0x1800a708c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a7092  lea     rax, WPP_GLOBAL_Control
0x1800a7099  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a70a0  cmp     rcx, rax
0x1800a70a3  jz      short loc_1800A70CA
0x1800a70a5  test    byte ptr [rcx+1Ch], 1
0x1800a70a9  jz      short loc_1800A70CA
0x1800a70ab  cmp     byte ptr [rcx+19h], 2
0x1800a70af  jb      short loc_1800A70CA
0x1800a70b1  mov     edx, 2Fh ; '/'
0x1800a70b6  mov     r9d, ebx
0x1800a70b9  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800a70c0  mov     rcx, [rcx+10h]
0x1800a70c4  call    WPP_SF_d
0x1800a70c9  nop
0x1800a70ca  lea     rcx, [rsp+78h+var_40]; this
0x1800a70cf  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800a70d4  nop
0x1800a70d5  lea     rcx, [rsp+78h+arg_18]
0x1800a70dd  call    ??1?$CDeleteMe@VCAdapStatusInstance@@@@QEAA@XZ; CDeleteMe<CAdapStatusInstance>::~CDeleteMe<CAdapStatusInstance>(void)
0x1800a70e2  nop
0x1800a70e3  lea     rcx, [rsp+78h+arg_10]
0x1800a70eb  call    ??1?$CDeleteMe@VCSystemConfigClass@@@@QEAA@XZ; CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(void)
0x1800a70f0  mov     eax, ebx
0x1800a70f2  jmp     loc_1800A7235
0x1800a70f7  mov     rax, [rsp+78h+var_30]
0x1800a70fc  mov     [rsp+78h+var_20], rax
0x1800a7101  mov     [rsp+78h+var_58], 1000h; unsigned int
0x1800a7109  mov     r9, [rsp+78h+var_30]; void *
0x1800a710e  mov     rdx, r14; struct IWmiDbHandle *
0x1800a7111  mov     rcx, rsi; struct IWmiDbSession *
0x1800a7114  call    ?PutObject@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@AEBU_GUID@@PEAXK@Z; CRepository::PutObject(IWmiDbSession *,IWmiDbHandle *,_GUID const &,void *,ulong)
0x1800a7119  mov     ebx, eax
0x1800a711b  mov     [rsp+78h+var_48], eax
0x1800a711f  test    eax, eax
0x1800a7121  jns     loc_1800A71A8
0x1800a7127  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a712d  mov     edx, ebx
0x1800a712f  mov     rcx, rax
0x1800a7132  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a7138  lea     rax, WPP_GLOBAL_Control
0x1800a713f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7146  cmp     rcx, rax
0x1800a7149  jz      short loc_1800A7170
0x1800a714b  test    byte ptr [rcx+1Ch], 1
0x1800a714f  jz      short loc_1800A7170
0x1800a7151  cmp     byte ptr [rcx+19h], 2
0x1800a7155  jb      short loc_1800A7170
0x1800a7157  mov     edx, 30h ; '0'
0x1800a715c  mov     r9d, ebx
0x1800a715f  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800a7166  mov     rcx, [rcx+10h]
0x1800a716a  call    WPP_SF_d
0x1800a716f  nop
0x1800a7170  lea     rcx, [rsp+78h+var_20]; this
0x1800a7175  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800a717a  nop
0x1800a717b  lea     rcx, [rsp+78h+var_40]; this
0x1800a7180  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800a7185  nop
0x1800a7186  lea     rcx, [rsp+78h+arg_18]
0x1800a718e  call    ??1?$CDeleteMe@VCAdapStatusInstance@@@@QEAA@XZ; CDeleteMe<CAdapStatusInstance>::~CDeleteMe<CAdapStatusInstance>(void)
0x1800a7193  nop
0x1800a7194  lea     rcx, [rsp+78h+arg_10]
0x1800a719c  call    ??1?$CDeleteMe@VCSystemConfigClass@@@@QEAA@XZ; CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(void)
0x1800a71a1  mov     eax, ebx
0x1800a71a3  jmp     loc_1800A7235
0x1800a71a8  lea     rcx, [rsp+78h+var_20]; this
0x1800a71ad  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800a71b2  nop
0x1800a71b3  lea     rcx, [rsp+78h+var_40]; this
0x1800a71b8  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800a71bd  nop
0x1800a71be  lea     rcx, [rsp+78h+arg_18]
0x1800a71c6  call    ??1?$CDeleteMe@VCAdapStatusInstance@@@@QEAA@XZ; CDeleteMe<CAdapStatusInstance>::~CDeleteMe<CAdapStatusInstance>(void)
0x1800a71cb  nop
0x1800a71cc  lea     rcx, [rsp+78h+arg_10]
0x1800a71d4  call    ??1?$CDeleteMe@VCSystemConfigClass@@@@QEAA@XZ; CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(void)
0x1800a71d9  nop
0x1800a71da  jmp     short loc_1800A71E0
0x1800a71dc  mov     ebx, [rsp+78h+var_48]
0x1800a71e0  test    ebx, ebx
0x1800a71e2  jns     short loc_1800A71F5
0x1800a71e4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a71ea  mov     edx, ebx
0x1800a71ec  mov     rcx, rax
0x1800a71ef  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a71f5  lea     rax, WPP_GLOBAL_Control
0x1800a71fc  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
