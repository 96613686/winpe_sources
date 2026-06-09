# DllGetClassObject

- ea: `0x180029980`
- end: `0x180029af8`
- name: `DllGetClassObject`
- size: `376`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180029980`
- `0x180029b00`
- `0x180029c90`
- `0x18005f1a4`
- `0x1800ca010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180029a51`
- `RPCRT4!NdrDllGetClassObject` at `0x180029a51`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800299a6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800299a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rax
  const struct _GUID *v8; // r9
  _QWORD *v9; // rdx
  __int64 v10; // rcx
  int CacheEntry; // eax
  HRESULT ClassObject; // ebx
  __int64 v13; // rax
  Windows::UI::Core::CWindowServerFactory *v14; // rax
  __int64 (__fastcall ***v15)(_QWORD, const IID *const, LPVOID *); // rax
  __int64 (__fastcall ***v16)(_QWORD, const IID *const, LPVOID *); // rdi
  struct IUnknown **pPSFactoryBuffer; // [rsp+28h] [rbp-30h]
  int v19; // [rsp+70h] [rbp+18h] BYREF

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180135658 = 1;
  *ppv = 0;
  v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                 + 32LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                             + 8);
  v7 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                         + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  while ( 1 )
  {
    if ( (unsigned __int64)v6 >= v7 )
    {
      CacheEntry = -2147221231;
      goto LABEL_9;
    }
    v8 = *v6;
    if ( *v6 )
    {
      v9 = *(_QWORD **)v8->Data4;
      v10 = *v9 - *(_QWORD *)&rclsid->Data1;
      if ( *v9 == *(_QWORD *)&rclsid->Data1 )
        v10 = v9[1] - *(_QWORD *)rclsid->Data4;
      if ( !v10 )
        break;
    }
    ++v6;
  }
  v19 = 1;
  CacheEntry = Microsoft::WRL::Details::GetCacheEntry(
                 (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
                 (struct Microsoft::WRL::Details::ModuleBase *)&v19,
                 &riid->Data1,
                 v8,
                 ppv,
                 pPSFactoryBuffer);
LABEL_9:
  if ( !CacheEntry )
    return 0;
  ClassObject = NdrDllGetClassObject(
                  rclsid,
                  riid,
                  ppv,
                  (const ProxyFileInfo **)&aProxyFileList,
                  &CLSID_PSFactoryBuffer,
                  &gPFactory);
  if ( ClassObject )
  {
    v13 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&GUID_4d3bd4b7_ad22_4dc4_b889_311dae0d8aeb.Data1;
    if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&GUID_4d3bd4b7_ad22_4dc4_b889_311dae0d8aeb.Data1 )
      v13 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)GUID_4d3bd4b7_ad22_4dc4_b889_311dae0d8aeb.Data4;
    if ( !v13 )
    {
      v14 = (Windows::UI::Core::CWindowServerFactory *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
      if ( v14 )
      {
        v15 = (__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *))Windows::UI::Core::CWindowServerFactory::CWindowServerFactory(v14);
        v16 = v15;
        if ( v15 )
        {
          ClassObject = (**v15)(v15, riid, ppv);
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *)))(*v16)[2])(v16);
        }
      }
    }
  }
  return ClassObject;
}

```

## disassembly

```asm
0x180029980  push    rbx
0x180029982  push    rbp
0x180029983  push    rsi
0x180029984  push    rdi
0x180029985  sub     rsp, 38h
0x180029989  mov     rsi, r8
0x18002998c  mov     rbp, rdx
0x18002998f  mov     rdi, rcx
0x180029992  xor     r9d, r9d; Context
0x180029995  xor     r8d, r8d; Parameter
0x180029998  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18002999f  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800299a6  call    cs:__imp_InitOnceExecuteOnce
0x1800299ac  mov     cs:byte_180135658, 1
0x1800299b3  mov     qword ptr [rsi], 0
0x1800299ba  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800299c1  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800299c8  mov     rax, [rax+20h]
0x1800299cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299d1  lea     rbx, [rax+8]
0x1800299d5  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800299dc  mov     rax, [rcx+28h]
0x1800299e0  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800299e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299ec  cmp     rbx, rax
0x1800299ef  jnb     short loc_180029A1C
0x1800299f1  mov     r9, [rbx]; struct _GUID *
0x1800299f4  test    r9, r9
0x1800299f7  jz      short loc_180029A16
0x1800299f9  mov     rdx, [r9+8]
0x1800299fd  mov     rcx, [rdx]
0x180029a00  sub     rcx, [rdi]
0x180029a03  jnz     short loc_180029A0D
0x180029a05  mov     rcx, [rdx+8]
0x180029a09  sub     rcx, [rdi+8]
0x180029a0d  test    rcx, rcx
0x180029a10  jz      loc_180029ACE
0x180029a16  add     rbx, 8
0x180029a1a  jmp     short loc_1800299EC
0x180029a1c  mov     eax, 80040111h
0x180029a21  test    eax, eax
0x180029a23  jz      loc_180029AF4
0x180029a29  lea     rax, gPFactory
0x180029a30  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180029a35  lea     rax, CLSID_PSFactoryBuffer
0x180029a3c  mov     [rsp+58h+pclsid], rax; pclsid
0x180029a41  lea     r9, aProxyFileList; pProxyFileList
0x180029a48  mov     r8, rsi; ppv
0x180029a4b  mov     rdx, rbp; riid
0x180029a4e  mov     rcx, rdi; rclsid
0x180029a51  call    cs:__imp_NdrDllGetClassObject
0x180029a57  mov     ebx, eax
0x180029a59  test    eax, eax
0x180029a5b  jz      short loc_180029AC3
0x180029a5d  mov     rax, [rdi]
0x180029a60  sub     rax, qword ptr cs:_GUID_4d3bd4b7_ad22_4dc4_b889_311dae0d8aeb.Data1
0x180029a67  jnz     short loc_180029A74
0x180029a69  mov     rax, [rdi+8]
0x180029a6d  sub     rax, qword ptr cs:_GUID_4d3bd4b7_ad22_4dc4_b889_311dae0d8aeb.Data4
0x180029a74  test    rax, rax
0x180029a77  jnz     short loc_180029AC3
0x180029a79  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029a80  lea     ecx, [rax+18h]; unsigned __int64
0x180029a83  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180029a88  test    rax, rax
0x180029a8b  jz      short loc_180029AC3
0x180029a8d  mov     rcx, rax; this
0x180029a90  call    ??0CWindowServerFactory@Core@UI@Windows@@QEAA@XZ; Windows::UI::Core::CWindowServerFactory::CWindowServerFactory(void)
0x180029a95  mov     rdi, rax
0x180029a98  test    rax, rax
0x180029a9b  jz      short loc_180029AC3
0x180029a9d  mov     rcx, [rax]
0x180029aa0  mov     rax, [rcx]
0x180029aa3  mov     r8, rsi
0x180029aa6  mov     rdx, rbp
0x180029aa9  mov     rcx, rdi
0x180029aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ab1  mov     ebx, eax
0x180029ab3  mov     rcx, [rdi]
0x180029ab6  mov     rax, [rcx+10h]
0x180029aba  mov     rcx, rdi
0x180029abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ac2  nop
0x180029ac3  mov     eax, ebx
0x180029ac5  add     rsp, 38h
0x180029ac9  pop     rdi
0x180029aca  pop     rsi
0x180029acb  pop     rbp
0x180029acc  pop     rbx
0x180029acd  retn
0x180029ace  mov     [rsp+58h+arg_10], 1
0x180029ad6  mov     [rsp+58h+pclsid], rsi; Ptr
0x180029adb  mov     r8, rbp; unsigned int *
0x180029ade  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x180029ae3  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180029aea  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180029aef  jmp     loc_180029A21
0x180029af4  xor     ebx, ebx
0x180029af6  jmp     short loc_180029AC3
```
