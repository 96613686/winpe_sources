# VmHandleBrokerManager::CreateHandleBrokerForDevice(_GUID,_GUID,IVmHandleBroker * *)

- ea: `0x1400239d0`
- end: `0x140023e07`
- name: `?CreateHandleBrokerForDevice@VmHandleBrokerManager@@UEAAJU_GUID@@0PEAPEAUIVmHandleBroker@@@Z`
- size: `1079`
- prototype: `__int64 __fastcall(VmHandleBrokerManager *__hidden this, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, struct IVmHandleBroker **)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400226fc`
- `0x140022e84`
- `0x1400239d0`
- `0x140023e10`
- `0x140023f20`
- `0x1400243f0`
- `0x1400246f0`
- `0x140033a7c`
- `0x14005f810`
- `0x1400618f4`
- `0x1400c40e0`
- `0x1400d3310`
- `0x1400d34b0`
- `0x1400d35c4`
- `0x1400d3668`
- `0x1400d36c0`
- `0x1400d372c`
- `0x1400d3968`
- `0x1400e8bc0`
- `0x1400e9e44`
- `0x1400eb008`
- `0x1401332f0`
- `0x140134048`
- `0x1402c4010`

## import_xrefs

- `RPCRT4!UuidCompare` at `0x140023ad1`
- `RPCRT4!UuidCompare` at `0x140023b15`
- `RPCRT4!UuidCompare` at `0x140023be7`
- `RPCRT4!UuidCompare` at `0x140023c38`
- `RPCRT4!UuidCompare` at `0x140023ad1`
- `RPCRT4!UuidCompare` at `0x140023b15`
- `RPCRT4!UuidCompare` at `0x140023be7`
- `RPCRT4!UuidCompare` at `0x140023c38`

## string_xrefs

- `0x140023a17`: `VmHandleBrokerManagerCreateBroker`
- `0x140023a82`: `onecore\vm\common\vmhandlebroker\manager\vmhandlebrokermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall VmHandleBrokerManager::CreateHandleBrokerForDevice(
        VmHandleBrokerManager *this,
        struct _GUID *a2,
        struct _GUID *a3,
        struct IVmHandleBroker **a4)
{
  char *v8; // rsi
  UUID *v9; // rdi
  UUID *v10; // rbx
  const char *v11; // r9
  __int64 result; // rax
  struct IVmHandleBroker **v13; // rax
  struct IVmHandleBroker *v14; // rdx
  __int64 v15; // rcx
  UUID *v16; // rdi
  UUID *v17; // rbx
  __int64 v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rcx
  int v21; // r9d
  __int64 v22; // rax
  __int64 v23; // rdi
  int v24; // [rsp+20h] [rbp-218h]
  struct IVmHandleBroker *v25; // [rsp+30h] [rbp-208h]
  UUID Uuid2; // [rsp+40h] [rbp-1F8h] BYREF
  UUID Uuid1; // [rsp+50h] [rbp-1E8h] BYREF
  UUID v28; // [rsp+60h] [rbp-1D8h] BYREF
  UUID v29; // [rsp+78h] [rbp-1C0h] BYREF
  __int64 v30; // [rsp+88h] [rbp-1B0h]
  RPC_STATUS Status[4]; // [rsp+90h] [rbp-1A8h] BYREF
  void **v32; // [rsp+A0h] [rbp-198h] BYREF
  _BYTE v33[272]; // [rsp+A8h] [rbp-190h] BYREF
  _BYTE v34[8]; // [rsp+1B8h] [rbp-80h] BYREF
  _BYTE v35[48]; // [rsp+1C0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  memset_0(&v32, 0, 0x150u);
  wil::ActivityBase<VmHandleBrokerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmHandleBrokerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v32);
  try
  {
    v32 = &VmHandleBrokerTraceProvider::VmHandleBrokerManagerCreateBroker::`vftable';
    Uuid2 = *a3;
    Uuid1 = *a2;
    VmHandleBrokerTraceProvider::VmHandleBrokerManagerCreateBroker::StartActivity(
      (VmHandleBrokerTraceProvider::VmHandleBrokerManagerCreateBroker *)&v32,
      &Uuid1,
      &Uuid2);
    VmHandleBrokerManager::ThrowIfInvalidBrokerManager(this);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"onecore\\vm\\common\\vmhandlebroker\\manager\\vmhandlebrokermanager.cpp",
        (const char *)0x80004003LL,
        v24);
    v8 = (char *)this + 56;
    Uuid2 = *a2;
    v9 = (UUID *)*((_QWORD *)this + 7);
    v10 = *(UUID **)v9->Data4;
    for ( *(_DWORD *)&v29.Data4[4] = 0; !v10[1].Data4[1]; v10 = *(UUID **)&v10->Data1 )
    {
      Status[0] = 0;
      if ( UuidCompare(v10 + 2, &Uuid2, Status) >= 0 )
        v9 = v10;
      else
        ++v10;
    }
    if ( v9[1].Data4[1] || (Status[0] = 0, UuidCompare(&Uuid2, v9 + 2, Status) < 0) || v9 == *(UUID **)v8 )
    {
      v13 = (struct IVmHandleBroker **)wil::MakeOrThrow<VmHandleBroker,_GUID &,_GUID const &>(Status, a2, a3);
      v14 = *v13;
      *v13 = 0;
      v25 = v14;
      v15 = *(_QWORD *)Status;
      if ( *(_QWORD *)Status )
      {
        *(_QWORD *)Status = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      Uuid1 = *a2;
      v16 = *(UUID **)v8;
      v17 = *(UUID **)(*(_QWORD *)v8 + 8LL);
      v28 = (UUID)(unsigned __int64)v17;
      while ( !v17[1].Data4[1] )
      {
        *(_QWORD *)&v28.Data1 = v17;
        Status[0] = 0;
        if ( UuidCompare(v17 + 2, &Uuid1, Status) >= 0 )
        {
          *(_DWORD *)v28.Data4 = 1;
          v16 = v17;
        }
        else
        {
          *(_DWORD *)v28.Data4 = 0;
          ++v17;
        }
        v17 = *(UUID **)&v17->Data1;
      }
      if ( v16[1].Data4[1] || (Status[0] = 0, UuidCompare(&Uuid1, v16 + 2, Status) < 0) )
      {
        std::_Tree<std::_Tmap_traits<Vml::VmGuid,wil::com_ptr_t<IVmHandleBroker,wil::err_exception_policy>,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,wil::com_ptr_t<IVmHandleBroker,wil::err_exception_policy>>>,0>>::_Check_grow_by_1((char *)this + 56);
        v18 = *(_QWORD *)v8;
        *(_QWORD *)&Uuid2.Data1 = (char *)this + 56;
        *(_QWORD *)Uuid2.Data4 = 0;
        v19 = std::allocator<std::_Tree_node<std::pair<Vml::VmGuid const,wil::com_ptr_t<IVmHandleBroker,wil::err_exception_policy>>,void *>>::allocate();
        *(UUID *)(v19 + 32) = Uuid1;
        wil::com_ptr_t<IVmHandleBrokerManager,wil::err_exception_policy>::com_ptr_t<IVmHandleBrokerManager,wil::err_exception_policy>(
          v19 + 48,
          v25);
        *(_QWORD *)v19 = v18;
        *(_QWORD *)(v19 + 8) = v18;
        *(_QWORD *)(v19 + 16) = v18;
        *(_WORD *)(v19 + 24) = 0;
        Uuid2 = v28;
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Schema::VirtualMachines::Resources::Vpci::VirtualPciDevice>>>::_Insert_node(
          (char *)this + 56,
          &Uuid2,
          v19);
      }
      Uuid2 = *a2;
      std::_Tree<std::_Tmap_traits<Vml::VmGuid,Vml::VmGuid,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,Vml::VmGuid>>,0>>::_Find_lower_bound<Vml::VmGuid>(
        (char *)this + 72,
        &v29,
        &Uuid2);
      if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<Vml::VmGuid,Vml::VmGuid,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,Vml::VmGuid>>,0>>::_Lower_bound_duplicate<Vml::VmGuid>(
                               v20,
                               v30,
                               &Uuid2) )
      {
        std::_Tree<std::_Tmap_traits<Vml::VmGuid,Vml::VmGuid,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,Vml::VmGuid>>,0>>::_Check_grow_by_1((char *)this + 72);
        *(_QWORD *)Status = a3;
        *(_QWORD *)&Uuid1.Data1 = &Uuid2;
        v22 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Vml::VmGuid const,Vml::VmGuid>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Vml::VmGuid const,Vml::VmGuid>,void *>>>(
                (unsigned int)&v28,
                (int)this + 72,
                *((_QWORD *)this + 9),
                v21,
                (__int64)&Uuid1,
                (__int64)Status);
        v23 = *(_QWORD *)(v22 + 8);
        *(_QWORD *)(v22 + 8) = 0;
        if ( *(_QWORD *)v28.Data4 )
          std::_Deallocate<16>(*(_QWORD *)v28.Data4, 64);
        Uuid1 = v29;
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Schema::VirtualMachines::Resources::Vpci::VirtualPciDevice>>>::_Insert_node(
          (char *)this + 72,
          &Uuid1,
          v23);
      }
      *a4 = v25;
      wil::ActivityBase<VmHandleBrokerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v32);
      v32 = &VmHandleBrokerTraceProvider::VmHandleBrokerManagerCreateBroker::`vftable';
      wil::ActivityBase<VmHandleBrokerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v32);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v35);
      wil::details::shared_object<wil::ActivityBase<VmHandleBrokerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<VmHandleBrokerTraceProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v34);
      wil::ActivityBase<VmHandleBrokerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<VmHandleBrokerTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<VmHandleBrokerTraceProvider,_TlgReflectorTag_Param0IsProviderType>(v33);
      result = 0;
    }
    else
    {
      VmHandleBrokerTraceProvider::VmHandleBrokerManagerCreateBroker::~VmHandleBrokerManagerCreateBroker((VmHandleBrokerTraceProvider::VmHandleBrokerManagerCreateBroker *)&v32);
      result = 2147942583LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2D,
                           (unsigned int)"onecore\\vm\\common\\vmhandlebroker\\manager\\vmhandlebrokermanager.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x1400239d0  push    rbx
0x1400239d2  push    rsi
0x1400239d3  push    rdi
0x1400239d4  push    r12
0x1400239d6  push    r13
0x1400239d8  push    r14
0x1400239da  push    r15
0x1400239dc  sub     rsp, 200h
0x1400239e3  mov     rax, cs:__security_cookie
0x1400239ea  xor     rax, rsp
0x1400239ed  mov     [rsp+238h+var_48], rax
0x1400239f5  mov     r15, r9
0x1400239f8  mov     r12, r8
0x1400239fb  mov     r14, rdx
0x1400239fe  mov     r13, rcx
0x140023a01  xor     edx, edx; Val
0x140023a03  mov     r8d, 150h; Size
0x140023a09  lea     rcx, [rsp+238h+var_198]; void *
0x140023a11  call    memset_0
0x140023a16  nop
0x140023a17  lea     rdx, aVmhandlebroker_4; "VmHandleBrokerManagerCreateBroker"
0x140023a1e  lea     rcx, [rsp+238h+var_198]; struct wil::details::IFailureCallback *
0x140023a26  call    ??0?$ActivityBase@VVmHandleBrokerTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmHandleBrokerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmHandleBrokerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140023a2b  lea     rax, ??_7VmHandleBrokerManagerCreateBroker@VmHandleBrokerTraceProvider@@6B@; const VmHandleBrokerTraceProvider::VmHandleBrokerManagerCreateBroker::`vftable'
0x140023a32  mov     [rsp+238h+var_198], rax
0x140023a3a  movups  xmm0, xmmword ptr [r12]
0x140023a3f  movdqu  xmmword ptr [rsp+238h+Uuid2.Data1], xmm0
0x140023a45  movups  xmm1, xmmword ptr [r14]
0x140023a49  movdqu  xmmword ptr [rsp+238h+Uuid1.Data1], xmm1
0x140023a4f  lea     r8, [rsp+238h+Uuid2]; struct _GUID
0x140023a54  lea     rdx, [rsp+238h+Uuid1]; struct _GUID
0x140023a59  lea     rcx, [rsp+238h+var_198]; this
0x140023a61  call    ?StartActivity@VmHandleBrokerManagerCreateBroker@VmHandleBrokerTraceProvider@@QEAAXU_GUID@@0@Z; VmHandleBrokerTraceProvider::VmHandleBrokerManagerCreateBroker::StartActivity(_GUID,_GUID)
0x140023a66  nop
0x140023a67  mov     rcx, r13; this
0x140023a6a  call    ?ThrowIfInvalidBrokerManager@VmHandleBrokerManager@@AEAAXXZ; VmHandleBrokerManager::ThrowIfInvalidBrokerManager(void)
0x140023a6f  mov     rcx, [rsp+238h]; this
0x140023a77  test    r15, r15
0x140023a7a  jnz     short loc_140023A92
0x140023a7c  mov     r9d, 80004003h; char *
0x140023a82  lea     r8, aOnecoreVmCommo_36; "onecore\\vm\\common\\vmhandlebroker\\ma"...
0x140023a89  lea     edx, [r15+1Ch]; void *
0x140023a8d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140023a92  lea     rsi, [r13+38h]
0x140023a96  movups  xmm0, xmmword ptr [r14]
0x140023a9a  movdqu  xmmword ptr [rsp+238h+Uuid2.Data1], xmm0
0x140023aa0  mov     rdi, [rsi]
0x140023aa3  mov     rbx, [rdi+8]
0x140023aa7  xor     eax, eax
0x140023aa9  mov     dword ptr [rsp+238h+var_1C0+0Ch], eax
0x140023ab0  cmp     [rbx+19h], al
0x140023ab3  jnz     short loc_140023AF3
0x140023ab5  mov     [rsp+238h+Status], 0
0x140023ac0  lea     rcx, [rbx+20h]; Uuid1
0x140023ac4  lea     r8, [rsp+238h+Status]; Status
0x140023acc  lea     rdx, [rsp+238h+Uuid2]; Uuid2
0x140023ad1  call    cs:__imp_UuidCompare
0x140023ad8  nop     dword ptr [rax+rax+00h]
0x140023add  test    eax, eax
0x140023adf  jns     short loc_140023AE7
0x140023ae1  add     rbx, 10h
0x140023ae5  jmp     short loc_140023AEA
0x140023ae7  mov     rdi, rbx
0x140023aea  mov     rbx, [rbx]
0x140023aed  cmp     byte ptr [rbx+19h], 0
0x140023af1  jz      short loc_140023AB5
0x140023af3  cmp     byte ptr [rdi+19h], 0
0x140023af7  jnz     short loc_140023B41
0x140023af9  mov     [rsp+238h+Status], 0
0x140023b04  lea     rdx, [rdi+20h]; Uuid2
0x140023b08  lea     r8, [rsp+238h+Status]; Status
0x140023b10  lea     rcx, [rsp+238h+Uuid2]; Uuid1
0x140023b15  call    cs:__imp_UuidCompare
0x140023b1c  nop     dword ptr [rax+rax+00h]
0x140023b21  test    eax, eax
0x140023b23  js      short loc_140023B41
0x140023b25  cmp     rdi, [rsi]
0x140023b28  jz      short loc_140023B41
0x140023b2a  lea     rcx, [rsp+238h+var_198]; this
0x140023b32  call    ??1VmHandleBrokerManagerCreateBroker@VmHandleBrokerTraceProvider@@QEAA@XZ; VmHandleBrokerTraceProvider::VmHandleBrokerManagerCreateBroker::~VmHandleBrokerManagerCreateBroker(void)
0x140023b37  mov     eax, 800700B7h
0x140023b3c  jmp     loc_140023DE3
0x140023b41  mov     [rsp+238h+var_208], 0
0x140023b4a  mov     r8, r12
0x140023b4d  mov     rdx, r14
0x140023b50  lea     rcx, [rsp+238h+Status]
0x140023b58  call    ??$MakeOrThrow@VVmHandleBroker@@AEAU_GUID@@AEBU2@@wil@@YA?AV?$ComPtr@VVmHandleBroker@@@WRL@Microsoft@@AEAU_GUID@@AEBU4@@Z; wil::MakeOrThrow<VmHandleBroker,_GUID &,_GUID const &>(_GUID &,_GUID const &)
0x140023b5d  mov     rdx, [rax]
0x140023b60  xor     r8d, r8d
0x140023b63  mov     [rax], r8
0x140023b66  mov     rcx, [rsp+238h+var_208]
0x140023b6b  mov     [rsp+238h+var_208], rdx
0x140023b70  test    rcx, rcx
0x140023b73  jz      short loc_140023B84
0x140023b75  mov     rax, [rcx]
0x140023b78  mov     rax, [rax+10h]
0x140023b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023b81  xor     r8d, r8d
0x140023b84  mov     rcx, qword ptr [rsp+238h+Status]
0x140023b8c  test    rcx, rcx
0x140023b8f  jz      short loc_140023BA8
0x140023b91  mov     qword ptr [rsp+238h+Status], r8
0x140023b99  mov     rax, [rcx]
0x140023b9c  mov     rax, [rax+10h]
0x140023ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023ba5  xor     r8d, r8d
0x140023ba8  movups  xmm0, xmmword ptr [r14]
0x140023bac  movdqu  xmmword ptr [rsp+238h+Uuid1.Data1], xmm0
0x140023bb2  mov     rdi, [rsi]
0x140023bb5  mov     rbx, [rdi+8]
0x140023bb9  mov     qword ptr [rsp+238h+var_1D8.Data1], rbx
0x140023bbe  mov     qword ptr [rsp+238h+var_1D8.Data4], 0
0x140023bc7  jmp     short loc_140023C13
0x140023bc9  mov     qword ptr [rsp+238h+var_1D8.Data1], rbx
0x140023bce  mov     [rsp+238h+Status], r8d
0x140023bd6  lea     rcx, [rbx+20h]; Uuid1
0x140023bda  lea     r8, [rsp+238h+Status]; Status
0x140023be2  lea     rdx, [rsp+238h+Uuid1]; Uuid2
0x140023be7  call    cs:__imp_UuidCompare
0x140023bee  nop     dword ptr [rax+rax+00h]
0x140023bf3  xor     r8d, r8d
0x140023bf6  test    eax, eax
0x140023bf8  jns     short loc_140023C05
0x140023bfa  mov     dword ptr [rsp+238h+var_1D8.Data4], r8d
0x140023bff  add     rbx, 10h
0x140023c03  jmp     short loc_140023C10
0x140023c05  mov     dword ptr [rsp+238h+var_1D8.Data4], 1
0x140023c0d  mov     rdi, rbx
0x140023c10  mov     rbx, [rbx]
0x140023c13  cmp     [rbx+19h], r8b
0x140023c17  jz      short loc_140023BC9
0x140023c19  cmp     [rdi+19h], r8b
0x140023c1d  jnz     short loc_140023C48
0x140023c1f  mov     [rsp+238h+Status], r8d
0x140023c27  lea     rdx, [rdi+20h]; Uuid2
0x140023c2b  lea     r8, [rsp+238h+Status]; Status
0x140023c33  lea     rcx, [rsp+238h+Uuid1]; Uuid1
0x140023c38  call    cs:__imp_UuidCompare
0x140023c3f  nop     dword ptr [rax+rax+00h]
0x140023c44  test    eax, eax
0x140023c46  jns     short loc_140023CAD
0x140023c48  mov     rcx, rsi
0x140023c4b  call    ?_Check_grow_by_1@?$_Tree@V?$_Tmap_traits@VVmGuid@Vml@@V?$com_ptr_t@UIVmHandleBroker@@Uerr_exception_policy@wil@@@wil@@U?$less@VVmGuid@Vml@@@std@@V?$allocator@U?$pair@$$CBVVmGuid@Vml@@V?$com_ptr_t@UIVmHandleBroker@@Uerr_exception_policy@wil@@@wil@@@std@@@6@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<Vml::VmGuid,wil::com_ptr_t<IVmHandleBroker,wil::err_exception_policy>,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,wil::com_ptr_t<IVmHandleBroker,wil::err_exception_policy>>>,0>>::_Check_grow_by_1(void)
0x140023c50  mov     rdi, [rsi]
0x140023c53  mov     qword ptr [rsp+238h+Uuid2.Data1], rsi
0x140023c58  mov     qword ptr [rsp+238h+Uuid2.Data4], 0
0x140023c61  call    ?allocate@?$allocator@U?$_Tree_node@U?$pair@$$CBVVmGuid@Vml@@V?$com_ptr_t@UIVmHandleBroker@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVVmGuid@Vml@@V?$com_ptr_t@UIVmHandleBroker@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@_K@Z; std::allocator<std::_Tree_node<std::pair<Vml::VmGuid const,wil::com_ptr_t<IVmHandleBroker,wil::err_exception_policy>>,void *>>::allocate(unsigned __int64)
0x140023c66  mov     rbx, rax
0x140023c69  movups  xmm0, xmmword ptr [rsp+238h+Uuid1.Data1]
0x140023c6e  movdqu  xmmword ptr [rax+20h], xmm0
0x140023c73  lea     rcx, [rax+30h]
0x140023c77  mov     rdx, [rsp+238h+var_208]
0x140023c7c  call    ??0?$com_ptr_t@UIVmHandleBrokerManager@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIVmHandleBrokerManager@@@Z; wil::com_ptr_t<IVmHandleBrokerManager,wil::err_exception_policy>::com_ptr_t<IVmHandleBrokerManager,wil::err_exception_policy>(IVmHandleBrokerManager *)
0x140023c81  mov     [rbx], rdi
0x140023c84  mov     [rbx+8], rdi
0x140023c88  mov     [rbx+10h], rdi
0x140023c8c  mov     word ptr [rbx+18h], 0
0x140023c92  movups  xmm0, xmmword ptr [rsp+238h+var_1D8.Data1]
0x140023c97  movdqu  xmmword ptr [rsp+238h+Uuid2.Data1], xmm0
0x140023c9d  mov     r8, rbx
0x140023ca0  lea     rdx, [rsp+238h+Uuid2]
0x140023ca5  mov     rcx, rsi
0x140023ca8  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVirtualPciDevice@Vpci@Resources@VirtualMachines@Schema@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVirtualPciDevice@Vpci@Resources@VirtualMachines@Schema@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVirtualPciDevice@Vpci@Resources@VirtualMachines@Schema@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Schema::VirtualMachines::Resources::Vpci::VirtualPciDevice>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,Schema::VirtualMachines::Resources::Vpci::VirtualPciDevice>,void *> *>,std::_Tree_node<std::pair<std::wstring const,Schema::VirtualMachines::Resources::Vpci::VirtualPciDevice>,void *> * const)
0x140023cad  lea     rbx, [r13+48h]
0x140023cb1  movups  xmm0, xmmword ptr [r14]
0x140023cb5  movdqu  xmmword ptr [rsp+238h+Uuid2.Data1], xmm0
0x140023cbb  lea     r8, [rsp+238h+Uuid2]
0x140023cc0  lea     rdx, [rsp+238h+var_1C0]
0x140023cc5  mov     rcx, rbx
0x140023cc8  call    ??$_Find_lower_bound@VVmGuid@Vml@@@?$_Tree@V?$_Tmap_traits@VVmGuid@Vml@@V12@U?$less@VVmGuid@Vml@@@std@@V?$allocator@U?$pair@$$CBVVmGuid@Vml@@V12@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVVmGuid@Vml@@V12@@std@@PEAX@std@@@1@AEBVVmGuid@Vml@@@Z; std::_Tree<std::_Tmap_traits<Vml::VmGuid,Vml::VmGuid,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,Vml::VmGuid>>,0>>::_Find_lower_bound<Vml::VmGuid>(Vml::VmGuid const &)
0x140023ccd  lea     r8, [rsp+238h+Uuid2]
0x140023cd2  mov     rdx, [rsp+238h+var_1B0]
0x140023cda  call    ??$_Lower_bound_duplicate@VVmGuid@Vml@@@?$_Tree@V?$_Tmap_traits@VVmGuid@Vml@@V12@U?$less@VVmGuid@Vml@@@std@@V?$allocator@U?$pair@$$CBVVmGuid@Vml@@V12@@std@@@4@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBVVmGuid@Vml@@V12@@std@@PEAX@1@AEBVVmGuid@Vml@@@Z; std::_Tree<std::_Tmap_traits<Vml::VmGuid,Vml::VmGuid,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,Vml::VmGuid>>,0>>::_Lower_bound_duplicate<Vml::VmGuid>(std::_Tree_node<std::pair<Vml::VmGuid const,Vml::VmGuid>,void *> * const,Vml::VmGuid const &)
0x140023cdf  test    al, al
0x140023ce1  jnz     short loc_140023D5F
0x140023ce3  mov     rcx, rbx
0x140023ce6  call    ?_Check_grow_by_1@?$_Tree@V?$_Tmap_traits@VVmGuid@Vml@@V12@U?$less@VVmGuid@Vml@@@std@@V?$allocator@U?$pair@$$CBVVmGuid@Vml@@V12@@std@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<Vml::VmGuid,Vml::VmGuid,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,Vml::VmGuid>>,0>>::_Check_grow_by_1(void)
0x140023ceb  mov     qword ptr [rsp+238h+Status], r12
0x140023cf3  lea     rax, [rsp+238h+Uuid2]
0x140023cf8  mov     qword ptr [rsp+238h+Uuid1.Data1], rax
0x140023cfd  lea     rax, [rsp+238h+Status]
0x140023d05  mov     [rsp+238h+var_210], rax
0x140023d0a  lea     rax, [rsp+238h+Uuid1]
0x140023d0f  mov     [rsp+238h+var_218], rax
0x140023d14  mov     r8, [rbx]
0x140023d17  mov     rdx, rbx
0x140023d1a  lea     rcx, [rsp+238h+var_1D8]
0x140023d1f  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@$$QEAVVmGuid@Vml@@@1@V?$tuple@AEBU_GUID@@@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBVVmGuid@Vml@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVVmGuid@Vml@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVVmGuid@Vml@@V12@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@$$QEAVVmGuid@Vml@@@1@$$QEAV?$tuple@AEBU_GUID@@@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Vml::VmGuid const,Vml::VmGuid>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Vml::VmGuid const,Vml::VmGuid>,void *>>>(std::allocator<std::_Tree_node<std::pair<Vml::VmGuid const,Vml::VmGuid>,void *>> &,std::_Tree_node<std::pair<Vml::VmGuid const,Vml::VmGuid>,void *> *,std::piecewise_construct_t const &,std::tuple<Vml::VmGuid &&> &&,std::tuple<_GUID const &> &&)
0x140023d24  mov     rdi, [rax+8]
0x140023d28  mov     qword ptr [rax+8], 0
0x140023d30  mov     rcx, qword ptr [rsp+238h+var_1D8.Data4]
0x140023d35  test    rcx, rcx
0x140023d38  jz      short loc_140023D44
0x140023d3a  mov     edx, 40h ; '@'
0x140023d3f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140023d44  movups  xmm0, [rsp+238h+var_1C0]
0x140023d49  movdqu  xmmword ptr [rsp+238h+Uuid1.Data1], xmm0
0x140023d4f  mov     r8, rdi
0x140023d52  lea     rdx, [rsp+238h+Uuid1]
0x140023d57  mov     rcx, rbx
0x140023d5a  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVirtualPciDevice@Vpci@Resources@VirtualMachines@Schema@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVirtualPciDevice@Vpci@Resources@VirtualMachines@Schema@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVirtualPciDevice@Vpci@Resources@VirtualMachines@Schema@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Schema::VirtualMachines::Resources::Vpci::VirtualPciDevice>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,Schema::VirtualMachines::Resources::Vpci::VirtualPciDevice>,void *> *>,std::_Tree_node<std::pair<std::wstring const,Schema::VirtualMachines::Resources::Vpci::VirtualPciDevice>,void *> * const)
0x140023d5f  mov     rax, [rsp+238h+var_208]
0x140023d64  mov     [rsp+238h+var_208], 0
0x140023d6d  mov     [r15], rax
0x140023d70  lea     rcx, [rsp+238h+var_198]
0x140023d78  call    ?Stop@?$ActivityBase@VVmHandleBrokerTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmHandleBrokerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140023d7d  nop
0x140023d7e  mov     rcx, [rsp+238h+var_208]
0x140023d83  test    rcx, rcx
0x140023d86  jz      short loc_140023D95
0x140023d88  mov     rax, [rcx]
0x140023d8b  mov     rax, [rax+10h]
0x140023d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023d94  nop
0x140023d95  lea     rax, ??_7VmHandleBrokerManagerCreateBroker@VmHandleBrokerTraceProvider@@6B@; const VmHandleBrokerTraceProvider::VmHandleBrokerManagerCreateBroker::`vftable'
0x140023d9c  mov     [rsp+238h+var_198], rax
0x140023da4  lea     rcx, [rsp+238h+var_198]
0x140023dac  call    ?Destroy@?$ActivityBase@VVmHandleBrokerTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<VmHandleBrokerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140023db1  lea     rcx, [rsp+238h+var_78]; this
0x140023db9  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140023dbe  lea     rcx, [rsp+238h+var_80]
0x140023dc6  call    ?reset@?$shared_object@V?$ActivityData@VVmHandleBrokerTraceProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VVmHandleBrokerTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<VmHandleBrokerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<VmHandleBrokerTraceProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x140023dcb  lea     rcx, [rsp+238h+var_190]
0x140023dd3  call    ??1?$ActivityData@VVmHandleBrokerTraceProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VVmHandleBrokerTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<VmHandleBrokerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<VmHandleBrokerTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<VmHandleBrokerTraceProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x140023dd8  xor     eax, eax
0x140023dda  jmp     short loc_140023DE3
0x140023ddc  mov     eax, [rsp+238h+Status]
0x140023de3  mov     rcx, [rsp+238h+var_48]
0x140023deb  xor     rcx, rsp; StackCookie
0x140023dee  call    __security_check_cookie
0x140023df3  add     rsp, 200h
0x140023dfa  pop     r15
0x140023dfc  pop     r14
0x140023dfe  pop     r13
0x140023e00  pop     r12
0x140023e02  pop     rdi
0x140023e03  pop     rsi
0x140023e04  pop     rbx
0x140023e05  retn
```
