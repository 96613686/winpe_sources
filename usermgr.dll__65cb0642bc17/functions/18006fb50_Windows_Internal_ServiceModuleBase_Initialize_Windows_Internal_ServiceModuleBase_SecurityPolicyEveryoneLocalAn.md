# Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)

- ea: `0x18006fb50`
- end: `0x18006fdd2`
- name: `??$Initialize@USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z`
- size: `642`
- prototype: `__int64 __fastcall(Windows::Internal::ServiceModuleBase *this, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180070c00`

## callees

- `0x1800088e8`
- `0x18000ce48`
- `0x18006fb50`
- `0x18006fdd8`
- `0x180074030`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fc19`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fd34`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fc19`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fd34`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18006fb70`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18006fb70`

## string_xrefs

- `0x18006fb87`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18006fbc3`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18006fc2d`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18006fc85`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18006fcdd`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18006fd48`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18006fda7`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>(
        Windows::Internal::ServiceModuleBase *this,
        char a2)
{
  int v4; // eax
  unsigned int v5; // edi
  int v7; // eax
  HRESULT v8; // eax
  int v9; // eax
  int v10; // eax
  HRESULT Instance; // eax
  int v12; // eax
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  LPVOID v16; // [rsp+80h] [rbp+8h] BYREF

  v4 = RoInitialize(1);
  v5 = v4;
  *((_DWORD *)this + 4) = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v4,
      ppv);
    Windows::Internal::ServiceModuleBase::Uninitialize(this);
    return v5;
  }
  if ( a2 )
  {
    v7 = Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote>();
    v5 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v7,
        ppv);
      Windows::Internal::ServiceModuleBase::Uninitialize(this);
      return v5;
    }
    v16 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    v8 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v16);
    v5 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v8,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
      Windows::Internal::ServiceModuleBase::Uninitialize(this);
      return v5;
    }
    v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v16 + 24LL))(v16, 1, 2);
    v5 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v9,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
      Windows::Internal::ServiceModuleBase::Uninitialize(this);
      return v5;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  }
  v10 = (*(__int64 (__fastcall **)(Windows::Internal::ServiceModuleBase *))(*(_QWORD *)this + 32LL))(this);
  v5 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v10,
      ppv);
    Windows::Internal::ServiceModuleBase::Uninitialize(this);
    return v5;
  }
  (*(void (__fastcall **)(Windows::Internal::ServiceModuleBase *))(*(_QWORD *)this + 16LL))(this);
  *((_BYTE *)this + 20) = 1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
  Instance = CoCreateInstance(
               &CLSID_ContextSwitcher,
               0,
               1u,
               &GUID_000001da_0000_0000_c000_000000000046,
               (LPVOID *)this + 3);
  v5 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)Instance,
      ppva);
    Windows::Internal::ServiceModuleBase::Uninitialize(this);
    return v5;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct tagComCallData *), Windows::Internal::ServiceModuleBase *, GUID *))(**((_QWORD **)this + 3) + 24LL))(
          *((_QWORD *)this + 3),
          Windows::Internal::ServiceModuleBase::ConnectCallbackThunk,
          this,
          &IID_IContextCallback);
  v5 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v12,
      5);
    Windows::Internal::ServiceModuleBase::Uninitialize(this);
    return v5;
  }
  return 0;
}

```

## disassembly

```asm
0x18006fb50  push    rbx
0x18006fb52  push    rbp
0x18006fb53  push    rsi
0x18006fb54  push    rdi
0x18006fb55  sub     rsp, 58h
0x18006fb59  mov     sil, dl
0x18006fb5c  mov     rbx, rcx
0x18006fb5f  mov     [rsp+78h+var_38], rcx
0x18006fb64  mov     ebp, 1
0x18006fb69  mov     [rsp+78h+var_30], bpl
0x18006fb6e  mov     ecx, ebp
0x18006fb70  call    cs:__imp_RoInitialize
0x18006fb76  mov     edi, eax
0x18006fb78  mov     [rbx+10h], eax
0x18006fb7b  test    eax, eax
0x18006fb7d  jns     short loc_18006FBA7
0x18006fb7f  mov     rcx, [rsp+78h]; this
0x18006fb84  mov     r9d, eax; char *
0x18006fb87  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\comservice"...
0x18006fb8e  lea     edx, [rbp+62h]; void *
0x18006fb91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fb96  nop
0x18006fb97  mov     rcx, rbx; this
0x18006fb9a  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18006fb9f  nop
0x18006fba0  mov     eax, edi
0x18006fba2  jmp     loc_18006FDC9
0x18006fba7  test    sil, sil
0x18006fbaa  jz      loc_18006FCC0
0x18006fbb0  call    ??$InitializeSecurity@USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@@ServiceModuleBase@Internal@Windows@@IEAAJXZ; Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote>(void)
0x18006fbb5  mov     edi, eax
0x18006fbb7  test    eax, eax
0x18006fbb9  jns     short loc_18006FBE0
0x18006fbbb  mov     rcx, [rsp+78h]; this
0x18006fbc0  mov     r9d, eax; char *
0x18006fbc3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\comservice"...
0x18006fbca  mov     edx, 6Ch ; 'l'; void *
0x18006fbcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fbd4  nop
0x18006fbd5  mov     rcx, rbx; this
0x18006fbd8  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18006fbdd  nop
0x18006fbde  jmp     short loc_18006FBA0
0x18006fbe0  mov     [rsp+78h+arg_0], 0
0x18006fbec  lea     rcx, [rsp+78h+arg_0]
0x18006fbf4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006fbf9  lea     rax, [rsp+78h+arg_0]
0x18006fc01  mov     [rsp+78h+ppv], rax; int
0x18006fc06  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18006fc0d  mov     r8d, ebp; dwClsContext
0x18006fc10  xor     edx, edx; pUnkOuter
0x18006fc12  lea     rcx, CLSID_GlobalOptions; rclsid
0x18006fc19  call    cs:__imp_CoCreateInstance
0x18006fc1f  mov     edi, eax
0x18006fc21  test    eax, eax
0x18006fc23  jns     short loc_18006FC5B
0x18006fc25  mov     rcx, [rsp+78h]; this
0x18006fc2a  mov     r9d, eax; char *
0x18006fc2d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\comservice"...
0x18006fc34  mov     edx, 73h ; 's'; void *
0x18006fc39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fc3e  nop
0x18006fc3f  lea     rcx, [rsp+78h+arg_0]
0x18006fc47  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006fc4c  nop
0x18006fc4d  mov     rcx, rbx; this
0x18006fc50  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18006fc55  nop
0x18006fc56  jmp     loc_18006FBA0
0x18006fc5b  mov     rcx, [rsp+78h+arg_0]
0x18006fc63  mov     rax, [rcx]
0x18006fc66  mov     r8d, 2
0x18006fc6c  mov     edx, ebp
0x18006fc6e  mov     rax, [rax+18h]
0x18006fc72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fc77  mov     edi, eax
0x18006fc79  test    eax, eax
0x18006fc7b  jns     short loc_18006FCB3
0x18006fc7d  mov     rcx, [rsp+78h]; this
0x18006fc82  mov     r9d, eax; char *
0x18006fc85  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\comservice"...
0x18006fc8c  mov     edx, 74h ; 't'; void *
0x18006fc91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fc96  nop
0x18006fc97  lea     rcx, [rsp+78h+arg_0]
0x18006fc9f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006fca4  nop
0x18006fca5  mov     rcx, rbx; this
0x18006fca8  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18006fcad  nop
0x18006fcae  jmp     loc_18006FBA0
0x18006fcb3  lea     rcx, [rsp+78h+arg_0]
0x18006fcbb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006fcc0  mov     rax, [rbx]
0x18006fcc3  mov     rcx, rbx
0x18006fcc6  mov     rax, [rax+20h]
0x18006fcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fccf  mov     edi, eax
0x18006fcd1  test    eax, eax
0x18006fcd3  jns     short loc_18006FCFD
0x18006fcd5  mov     rcx, [rsp+78h]; this
0x18006fcda  mov     r9d, eax; char *
0x18006fcdd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\comservice"...
0x18006fce4  mov     edx, 7Bh ; '{'; void *
0x18006fce9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fcee  nop
0x18006fcef  mov     rcx, rbx; this
0x18006fcf2  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18006fcf7  nop
0x18006fcf8  jmp     loc_18006FBA0
0x18006fcfd  mov     rax, [rbx]
0x18006fd00  mov     rcx, rbx
0x18006fd03  mov     rax, [rax+10h]
0x18006fd07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd0c  mov     [rbx+14h], bpl
0x18006fd10  lea     rsi, [rbx+18h]
0x18006fd14  mov     rcx, rsi
0x18006fd17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006fd1c  mov     [rsp+78h+ppv], rsi; int
0x18006fd21  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18006fd28  mov     r8d, ebp; dwClsContext
0x18006fd2b  xor     edx, edx; pUnkOuter
0x18006fd2d  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18006fd34  call    cs:__imp_CoCreateInstance
0x18006fd3a  mov     edi, eax
0x18006fd3c  test    eax, eax
0x18006fd3e  jns     short loc_18006FD68
0x18006fd40  mov     rcx, [rsp+78h]; this
0x18006fd45  mov     r9d, eax; char *
0x18006fd48  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\comservice"...
0x18006fd4f  mov     edx, 8Dh; void *
0x18006fd54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fd59  nop
0x18006fd5a  mov     rcx, rbx; this
0x18006fd5d  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18006fd62  nop
0x18006fd63  jmp     loc_18006FBA0
0x18006fd68  mov     rcx, [rsi]
0x18006fd6b  mov     rax, [rcx]
0x18006fd6e  mov     [rsp+78h+var_50], 0
0x18006fd77  mov     dword ptr [rsp+78h+ppv], 5; int
0x18006fd7f  lea     r9, IID_IContextCallback
0x18006fd86  mov     r8, rbx
0x18006fd89  lea     rdx, ?ConnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::ConnectCallbackThunk(tagComCallData *)
0x18006fd90  mov     rax, [rax+18h]
0x18006fd94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd99  mov     edi, eax
0x18006fd9b  test    eax, eax
0x18006fd9d  jns     short loc_18006FDC7
0x18006fd9f  mov     rcx, [rsp+78h]; this
0x18006fda4  mov     r9d, eax; char *
0x18006fda7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\comservice"...
0x18006fdae  mov     edx, 90h; void *
0x18006fdb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fdb8  nop
0x18006fdb9  mov     rcx, rbx; this
0x18006fdbc  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18006fdc1  nop
0x18006fdc2  jmp     loc_18006FBA0
0x18006fdc7  xor     eax, eax
0x18006fdc9  add     rsp, 58h
0x18006fdcd  pop     rdi
0x18006fdce  pop     rsi
0x18006fdcf  pop     rbp
0x18006fdd0  pop     rbx
0x18006fdd1  retn
```
