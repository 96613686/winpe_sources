# CollectorService::GetSubscriptionRunTimeStatus(ushort const *,ushort const *,tag_EcRpcMetadataPropertyList &,ulong)

- ea: `0x180004760`
- end: `0x180004b78`
- name: `?GetSubscriptionRunTimeStatus@CollectorService@@QEAAXPEBG0AEAUtag_EcRpcMetadataPropertyList@@K@Z`
- size: `1048`
- prototype: `void __fastcall(CollectorService *this, const unsigned __int16 *, unsigned __int16 *, struct tag_EcRpcMetadataPropertyList *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180003660`

## callees

- `0x18000195c`
- `0x1800024f0`
- `0x180002510`
- `0x1800032dc`
- `0x180003430`
- `0x180003a50`
- `0x180003be8`
- `0x180003cc8`
- `0x180003d48`
- `0x180004288`
- `0x180004760`
- `0x180005d7c`
- `0x18000da2c`
- `0x18000ff3c`
- `0x1800145cc`
- `0x180015dd4`
- `0x1800161e4`
- `0x1800189e8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180004916`
- `msvcrt!_wcsicmp` at `0x180004916`
- `RPCRT4!RpcRevertToSelf` at `0x1800047b2`
- `RPCRT4!RpcImpersonateClient` at `0x18000478c`
- `RPCRT4!RpcImpersonateClient` at `0x18000478c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800047cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800047cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004854`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004854`

## string_xrefs

- `0x180004a21`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x180004aaa`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x180004b30`: `admin\wmi\events\forwarding\collector\service\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CollectorService::GetSubscriptionRunTimeStatus(
        CollectorService *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct tag_EcRpcMetadataPropertyList *a4,
        unsigned int a5)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx
  bool v11; // bl
  HKEY v12; // r8
  const unsigned __int16 *v13; // r9
  __int64 v14; // rcx
  struct tag_EcRpcMetadataPropertyList *v15; // rax
  __int64 v16; // r14
  _BYTE *v17; // rax
  unsigned __int64 v18; // rbx
  const wchar_t *v19; // rcx
  __int64 v20; // rax
  bool v21; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v22; // [rsp+44h] [rbp-BCh] BYREF
  void **pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  char v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  int v28; // [rsp+70h] [rbp-90h]
  int v29; // [rsp+74h] [rbp-8Ch]
  int v30; // [rsp+78h] [rbp-88h]
  char v31[8]; // [rsp+80h] [rbp-80h] BYREF
  void (__fastcall *v32)(struct tag_EcRpcMetadataPropertyList *); // [rsp+88h] [rbp-78h]
  struct tag_EcRpcMetadataPropertyList *v33; // [rsp+90h] [rbp-70h]
  _BYTE v34[8]; // [rsp+98h] [rbp-68h] BYREF
  RPC_STATUS (__stdcall *v35)(); // [rsp+A0h] [rbp-60h]
  char *v36; // [rsp+A8h] [rbp-58h]
  _BYTE v37[24]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v38[24]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v39; // [rsp+E0h] [rbp-20h]
  __int64 v40; // [rsp+E8h] [rbp-18h]

  CollectorService::WaitForInit(this);
  v9 = RpcImpersonateClient(0);
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, v9);
    }
    v24 = 0;
    v25 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v26 = 0;
    v27 = 0;
    v28 = v10;
    v29 = -1;
    v30 = 833;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  _EventSources::_EventSources((_EventSources *)v37);
  v21 = 1;
  v11 = 0;
  v34[0] = 0;
  v35 = RpcRevertToSelf;
  v36 = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  SubscriptionConfigReader::SubscriptionConfigReader((SubscriptionConfigReader *)v31, a2, v12, v13);
  SubscriptionConfigReader::GetEnabled((SubscriptionConfigReader *)v31, &v21);
  v22 = 0;
  if ( ConfigBase::GetRegEnumValue(
         (ConfigBase *)v31,
         L"SubscriptionType",
         (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueSubscriptionType,
         &v22) )
  {
    v11 = v22 == 0;
  }
  if ( a3 )
  {
    ValidateRegKeyName(a3);
    if ( !SubscriptionConfigReader::GetEventSource((SubscriptionConfigReader *)v31, a3, (struct _EventSources *)v37, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, 1168);
      }
      v24 = 0;
      v25 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
      v26 = 0;
      v27 = 0;
      v28 = 1168;
      v29 = -1;
      v30 = 865;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  ConfigBase::~ConfigBase((ConfigBase *)v31);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v34);
  v14 = 16;
  v15 = a4;
  do
  {
    *(_BYTE *)v15 = 0;
    v15 = (struct tag_EcRpcMetadataPropertyList *)((char *)v15 + 1);
    --v14;
  }
  while ( v14 );
  *(_DWORD *)a4 = 7;
  v16 = 168;
  v17 = operator new(0xA8u);
  *((_QWORD *)a4 + 1) = v17;
  v31[0] = 0;
  v32 = CleanupMetadataPropList;
  v33 = a4;
  do
  {
    *v17++ = 0;
    --v16;
  }
  while ( v16 );
  if ( v21 )
  {
    if ( v11 || !a3 )
    {
      SubscriptionManager::GetSubscriptionRunTimeStatus(*(SubscriptionManager **)this, a2, a3, a4, a5);
    }
    else
    {
      v18 = 0;
      if ( !v39 )
        goto LABEL_34;
      while ( 1 )
      {
        v19 = (const wchar_t *)(v40 + 32 * v18);
        if ( *((_QWORD *)v19 + 3) >= 8u )
          v19 = *(const wchar_t **)v19;
        if ( !_wcsicmp(v19, a3) )
          break;
        if ( ++v18 >= v39 )
          goto LABEL_23;
      }
      v20 = std::vector<bool>::operator[](v38, v34, v18);
      if ( ((1 << *(_QWORD *)(v20 + 8)) & **(_DWORD **)v20) != 0 )
        SubscriptionManager::GetSubscriptionRunTimeStatus(*(SubscriptionManager **)this, a2, a3, a4, a5);
      else
        SetRunTimeStatus(a4, EcRuntimeStatusActiveStatusDisabled, 0, 0, 0, 0, 0);
LABEL_23:
      if ( v18 >= v39 )
      {
LABEL_34:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, 1168);
        }
        v24 = 0;
        v25 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
        v26 = 0;
        v27 = 0;
        v28 = 1168;
        v29 = -1;
        v30 = 920;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::GenericException *)&pExceptionObject;
      }
    }
  }
  else
  {
    SetRunTimeStatus(a4, EcRuntimeStatusActiveStatusDisabled, 0, 0, 0, 0, 0);
  }
  v31[0] = 1;
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v31);
  _EventSources::~_EventSources((_EventSources *)v37);
}

```

## disassembly

```asm
0x180004760  push    rbp
0x180004762  push    rbx
0x180004763  push    rsi
0x180004764  push    rdi
0x180004765  push    r12
0x180004767  push    r13
0x180004769  push    r14
0x18000476b  push    r15
0x18000476d  lea     rbp, [rsp-38h]
0x180004772  sub     rsp, 138h
0x180004779  mov     rdi, r9
0x18000477c  mov     rsi, r8
0x18000477f  mov     r12, rdx
0x180004782  mov     r15, rcx
0x180004785  call    ?WaitForInit@CollectorService@@AEAAXXZ; CollectorService::WaitForInit(void)
0x18000478a  xor     ecx, ecx; BindingHandle
0x18000478c  call    cs:__imp_RpcImpersonateClient
0x180004792  mov     ebx, eax
0x180004794  xor     r13d, r13d
0x180004797  test    eax, eax
0x180004799  jnz     loc_180004AF2
0x18000479f  lea     rcx, [rbp+70h+var_C0]; this
0x1800047a3  call    ??0_EventSources@@QEAA@XZ; _EventSources::_EventSources(void)
0x1800047a8  nop
0x1800047a9  mov     [rsp+170h+var_130], 1
0x1800047ae  movzx   ebx, r13b
0x1800047b2  mov     rax, cs:__imp_RpcRevertToSelf
0x1800047b9  mov     [rbp+70h+var_D8], r13b
0x1800047bd  mov     [rbp+70h+var_D0], rax
0x1800047c1  lea     r14, [r15+18h]
0x1800047c5  mov     [rbp+70h+var_C8], r14
0x1800047c9  mov     rcx, r14; lpCriticalSection
0x1800047cc  call    cs:__imp_EnterCriticalSection
0x1800047d2  nop
0x1800047d3  mov     rdx, r12; unsigned __int16 *
0x1800047d6  lea     rcx, [rbp+70h+var_F0]; this
0x1800047da  call    ??0SubscriptionConfigReader@@QEAA@PEBGPEAUHKEY__@@0@Z; SubscriptionConfigReader::SubscriptionConfigReader(ushort const *,HKEY__ *,ushort const *)
0x1800047df  nop
0x1800047e0  lea     rdx, [rsp+170h+var_130]; bool *
0x1800047e5  lea     rcx, [rbp+70h+var_F0]; this
0x1800047e9  call    ?GetEnabled@SubscriptionConfigReader@@QEBA_NAEA_N@Z; SubscriptionConfigReader::GetEnabled(bool &)
0x1800047ee  mov     [rsp+170h+var_12C], r13d
0x1800047f3  lea     r9, [rsp+170h+var_12C]; unsigned int *
0x1800047f8  lea     r8, ?EnumNameValueSubscriptionType@@3PAU_ENUM_NAMEVALUE_PAIR@@A; struct _ENUM_NAMEVALUE_PAIR *
0x1800047ff  lea     rdx, aSubscriptionty; "SubscriptionType"
0x180004806  lea     rcx, [rbp+70h+var_F0]; this
0x18000480a  call    ?GetRegEnumValue@ConfigBase@@IEBA_NPEBGPEAU_ENUM_NAMEVALUE_PAIR@@AEAK@Z; ConfigBase::GetRegEnumValue(ushort const *,_ENUM_NAMEVALUE_PAIR *,ulong &)
0x18000480f  test    al, al
0x180004811  jz      short loc_18000481F
0x180004813  cmp     [rsp+170h+var_12C], r13d
0x180004818  lea     eax, [r13+1]
0x18000481c  cmovz   ebx, eax
0x18000481f  test    rsi, rsi
0x180004822  jz      short loc_180004847
0x180004824  mov     rcx, rsi; unsigned __int16 *
0x180004827  call    ?ValidateRegKeyName@@YAXPEBG@Z; ValidateRegKeyName(ushort const *)
0x18000482c  xor     r9d, r9d; bool
0x18000482f  lea     r8, [rbp+70h+var_C0]; struct _EventSources *
0x180004833  mov     rdx, rsi; unsigned __int16 *
0x180004836  lea     rcx, [rbp+70h+var_F0]; this
0x18000483a  call    ?GetEventSource@SubscriptionConfigReader@@QEBA_NPEBGAEAU_EventSources@@_N@Z; SubscriptionConfigReader::GetEventSource(ushort const *,_EventSources &,bool)
0x18000483f  test    al, al
0x180004841  jz      loc_1800049E0
0x180004847  lea     rcx, [rbp+70h+var_F0]; this
0x18000484b  call    ??1ConfigBase@@UEAA@XZ; ConfigBase::~ConfigBase(void)
0x180004850  nop
0x180004851  mov     rcx, r14; lpCriticalSection
0x180004854  call    cs:__imp_LeaveCriticalSection
0x18000485a  nop
0x18000485b  lea     rcx, [rbp+70h+var_D8]
0x18000485f  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x180004864  mov     ecx, 10h
0x180004869  mov     rax, rdi
0x18000486c  lea     edx, [rcx-0Fh]
0x18000486f  mov     [rax], r13b
0x180004872  add     rax, rdx
0x180004875  sub     rcx, rdx
0x180004878  jnz     short loc_18000486F
0x18000487a  mov     dword ptr [rdi], 7
0x180004880  mov     r14d, 0A8h
0x180004886  mov     ecx, r14d; dwBytes
0x180004889  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000488e  mov     [rdi+8], rax
0x180004892  mov     [rbp+70h+var_F0], r13b
0x180004896  lea     rcx, ?CleanupMetadataPropList@@YAXPEAUtag_EcRpcMetadataPropertyList@@@Z; CleanupMetadataPropList(tag_EcRpcMetadataPropertyList *)
0x18000489d  mov     [rbp+70h+var_E8], rcx
0x1800048a1  mov     [rbp+70h+var_E0], rdi
0x1800048a5  mov     ecx, 1
0x1800048aa  mov     [rax], r13b
0x1800048ad  add     rax, rcx
0x1800048b0  sub     r14, rcx
0x1800048b3  jnz     short loc_1800048AA
0x1800048b5  cmp     [rsp+170h+var_130], r13b
0x1800048ba  jnz     short loc_1800048E0
0x1800048bc  mov     [rsp+170h+var_140], r13; unsigned __int64
0x1800048c1  mov     [rsp+170h+var_148], r13; unsigned __int64
0x1800048c6  mov     qword ptr [rsp+170h+var_150], r13; unsigned __int64
0x1800048cb  xor     r9d, r9d; unsigned __int16 *
0x1800048ce  xor     r8d, r8d; unsigned int
0x1800048d1  mov     edx, ecx; enum _EC_SUBSCRIPTION_RUNTIME_STATUS_ACTIVE_STATUS
0x1800048d3  mov     rcx, rdi; struct tag_EcRpcMetadataPropertyList *
0x1800048d6  call    ?SetRunTimeStatus@@YAXAEAUtag_EcRpcMetadataPropertyList@@W4_EC_SUBSCRIPTION_RUNTIME_STATUS_ACTIVE_STATUS@@KPEBG_K33@Z; SetRunTimeStatus(tag_EcRpcMetadataPropertyList &,_EC_SUBSCRIPTION_RUNTIME_STATUS_ACTIVE_STATUS,ulong,ushort const *,unsigned __int64,unsigned __int64,unsigned __int64)
0x1800048db  jmp     loc_1800049B5
0x1800048e0  test    bl, bl
0x1800048e2  jnz     loc_18000499A
0x1800048e8  test    rsi, rsi
0x1800048eb  jz      loc_18000499A
0x1800048f1  mov     rbx, r13
0x1800048f4  cmp     [rbp+70h+var_90], r13
0x1800048f8  jbe     loc_180004A69
0x1800048fe  mov     rcx, rbx
0x180004901  shl     rcx, 5
0x180004905  add     rcx, [rbp+70h+var_88]
0x180004909  cmp     qword ptr [rcx+18h], 8
0x18000490e  jb      short loc_180004913
0x180004910  mov     rcx, [rcx]; String1
0x180004913  mov     rdx, rsi; String2
0x180004916  call    cs:__imp__wcsicmp
0x18000491c  test    eax, eax
0x18000491e  jz      short loc_18000492B
0x180004920  inc     rbx
0x180004923  cmp     rbx, [rbp+70h+var_90]
0x180004927  jb      short loc_1800048FE
0x180004929  jmp     short loc_18000498E
0x18000492b  mov     r8, rbx
0x18000492e  lea     rdx, [rbp+70h+var_D8]
0x180004932  lea     rcx, [rbp+70h+var_A8]
0x180004936  call    ??A?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@1@_K@Z; std::vector<bool>::operator[](unsigned __int64)
0x18000493b  mov     rcx, [rax+8]
0x18000493f  mov     r10d, 1
0x180004945  mov     edx, r10d
0x180004948  shl     edx, cl
0x18000494a  mov     rax, [rax]
0x18000494d  test    [rax], edx
0x18000494f  jz      short loc_18000496E
0x180004951  mov     eax, [rbp+70h+arg_20]
0x180004957  mov     [rsp+170h+var_150], eax; unsigned int
0x18000495b  mov     r9, rdi; struct tag_EcRpcMetadataPropertyList *
0x18000495e  mov     r8, rsi; unsigned __int16 *
0x180004961  mov     rdx, r12; unsigned __int16 *
0x180004964  mov     rcx, [r15]; this
0x180004967  call    ?GetSubscriptionRunTimeStatus@SubscriptionManager@@QEAAXPEBG0AEAUtag_EcRpcMetadataPropertyList@@K@Z; SubscriptionManager::GetSubscriptionRunTimeStatus(ushort const *,ushort const *,tag_EcRpcMetadataPropertyList &,ulong)
0x18000496c  jmp     short loc_18000498E
0x18000496e  mov     [rsp+170h+var_140], r13; unsigned __int64
0x180004973  mov     [rsp+170h+var_148], r13; unsigned __int64
0x180004978  mov     qword ptr [rsp+170h+var_150], r13; unsigned __int64
0x18000497d  xor     r9d, r9d; unsigned __int16 *
0x180004980  xor     r8d, r8d; unsigned int
0x180004983  mov     edx, r10d; enum _EC_SUBSCRIPTION_RUNTIME_STATUS_ACTIVE_STATUS
0x180004986  mov     rcx, rdi; struct tag_EcRpcMetadataPropertyList *
0x180004989  call    ?SetRunTimeStatus@@YAXAEAUtag_EcRpcMetadataPropertyList@@W4_EC_SUBSCRIPTION_RUNTIME_STATUS_ACTIVE_STATUS@@KPEBG_K33@Z; SetRunTimeStatus(tag_EcRpcMetadataPropertyList &,_EC_SUBSCRIPTION_RUNTIME_STATUS_ACTIVE_STATUS,ulong,ushort const *,unsigned __int64,unsigned __int64,unsigned __int64)
0x18000498e  cmp     rbx, [rbp+70h+var_90]
0x180004992  jnb     loc_180004A69
0x180004998  jmp     short loc_1800049B5
0x18000499a  mov     eax, [rbp+70h+arg_20]
0x1800049a0  mov     [rsp+170h+var_150], eax; unsigned int
0x1800049a4  mov     r9, rdi; struct tag_EcRpcMetadataPropertyList *
0x1800049a7  mov     r8, rsi; unsigned __int16 *
0x1800049aa  mov     rdx, r12; unsigned __int16 *
0x1800049ad  mov     rcx, [r15]; this
0x1800049b0  call    ?GetSubscriptionRunTimeStatus@SubscriptionManager@@QEAAXPEBG0AEAUtag_EcRpcMetadataPropertyList@@K@Z; SubscriptionManager::GetSubscriptionRunTimeStatus(ushort const *,ushort const *,tag_EcRpcMetadataPropertyList &,ulong)
0x1800049b5  mov     [rbp+70h+var_F0], 1
0x1800049b9  lea     rcx, [rbp+70h+var_F0]
0x1800049bd  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x1800049c2  nop
0x1800049c3  lea     rcx, [rbp+70h+var_C0]; this
0x1800049c7  call    ??1_EventSources@@QEAA@XZ; _EventSources::~_EventSources(void)
0x1800049cc  add     rsp, 138h
0x1800049d3  pop     r15
0x1800049d5  pop     r14
0x1800049d7  pop     r13
0x1800049d9  pop     r12
0x1800049db  pop     rdi
0x1800049dc  pop     rsi
0x1800049dd  pop     rbx
0x1800049de  pop     rbp
0x1800049df  retn
0x1800049e0  lea     rcx, WPP_GLOBAL_Control
0x1800049e7  mov     ebx, 490h
0x1800049ec  mov     rax, cs:WPP_GLOBAL_Control
0x1800049f3  cmp     rax, rcx
0x1800049f6  jz      short loc_180004A1C
0x1800049f8  test    byte ptr [rax+1Ch], 10h
0x1800049fc  jz      short loc_180004A1C
0x1800049fe  cmp     byte ptr [rax+19h], 2
0x180004a02  jb      short loc_180004A1C
0x180004a04  mov     edx, 21h ; '!'
0x180004a09  mov     r9d, ebx
0x180004a0c  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x180004a13  mov     rcx, [rax+10h]
0x180004a17  call    WPP_SF_D
0x180004a1c  mov     [rsp+170h+var_120], r13b
0x180004a21  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180004a28  mov     [rsp+170h+var_118], rax
0x180004a2d  mov     [rsp+170h+var_110], r13
0x180004a32  mov     [rsp+170h+var_108], r13
0x180004a37  mov     [rsp+170h+var_100], ebx
0x180004a3b  mov     [rsp+170h+var_FC], 0FFFFFFFFh
0x180004a43  mov     [rsp+170h+var_F8], 361h
0x180004a4b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180004a52  mov     [rsp+170h+pExceptionObject], rax
0x180004a57  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180004a5e  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x180004a63  call    _CxxThrowException_0
0x180004a69  lea     rcx, WPP_GLOBAL_Control
0x180004a70  mov     ebx, 490h
0x180004a75  mov     rax, cs:WPP_GLOBAL_Control
0x180004a7c  cmp     rax, rcx
0x180004a7f  jz      short loc_180004AA5
0x180004a81  test    byte ptr [rax+1Ch], 10h
0x180004a85  jz      short loc_180004AA5
0x180004a87  cmp     byte ptr [rax+19h], 2
0x180004a8b  jb      short loc_180004AA5
0x180004a8d  mov     edx, 22h ; '"'
0x180004a92  mov     r9d, ebx
0x180004a95  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x180004a9c  mov     rcx, [rax+10h]
0x180004aa0  call    WPP_SF_D
0x180004aa5  mov     [rsp+170h+var_120], r13b
0x180004aaa  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180004ab1  mov     [rsp+170h+var_118], rax
0x180004ab6  mov     [rsp+170h+var_110], r13
0x180004abb  mov     [rsp+170h+var_108], r13
0x180004ac0  mov     [rsp+170h+var_100], ebx
0x180004ac4  mov     [rsp+170h+var_FC], 0FFFFFFFFh
0x180004acc  mov     [rsp+170h+var_F8], 398h
0x180004ad4  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180004adb  mov     [rsp+170h+pExceptionObject], rax
0x180004ae0  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180004ae7  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x180004aec  call    _CxxThrowException_0
0x180004af2  lea     rcx, WPP_GLOBAL_Control
0x180004af9  mov     r10, cs:WPP_GLOBAL_Control
0x180004b00  cmp     r10, rcx
0x180004b03  jz      short loc_180004B2B
0x180004b05  test    byte ptr [r10+1Ch], 10h
0x180004b0a  jz      short loc_180004B2B
0x180004b0c  cmp     byte ptr [r10+19h], 2
0x180004b11  jb      short loc_180004B2B
0x180004b13  mov     edx, 20h ; ' '
0x180004b18  mov     r9d, ebx
0x180004b1b  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x180004b22  mov     rcx, [r10+10h]
0x180004b26  call    WPP_SF_D
0x180004b2b  mov     [rsp+170h+var_120], r13b
0x180004b30  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180004b37  mov     [rsp+170h+var_118], rax
0x180004b3c  mov     [rsp+170h+var_110], r13
0x180004b41  mov     [rsp+170h+var_108], r13
0x180004b46  mov     [rsp+170h+var_100], ebx
0x180004b4a  mov     [rsp+170h+var_FC], 0FFFFFFFFh
0x180004b52  mov     [rsp+170h+var_F8], 341h
0x180004b5a  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180004b61  mov     [rsp+170h+pExceptionObject], rax
0x180004b66  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180004b6d  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x180004b72  call    _CxxThrowException_0
```
