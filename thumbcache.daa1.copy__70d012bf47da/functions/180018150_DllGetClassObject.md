# DllGetClassObject

- ea: `0x180018150`
- end: `0x1800182d9`
- name: `DllGetClassObject`
- size: `393`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180018150`
- `0x1800182e0`
- `0x180018328`
- `0x180035860`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800181ad`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800181ad`
- `RPCRT4!NdrDllGetClassObject` at `0x180018189`
- `RPCRT4!NdrDllGetClassObject` at `0x180018189`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int ClassObject; // edi
  const struct _GUID **v7; // rbx
  unsigned __int64 v8; // rax
  const struct _GUID *v9; // r9
  _QWORD *v10; // rdx
  __int64 v11; // rcx
  char *v12; // rbx
  struct IUnknown **v14; // [rsp+28h] [rbp-20h]
  int v15; // [rsp+68h] [rbp+20h] BYREF

  ClassObject = NdrDllGetClassObject(
                  rclsid,
                  riid,
                  ppv,
                  (const ProxyFileInfo **)&aProxyFileList,
                  &CLSID_PSFactoryBuffer,
                  &gPFactory);
  if ( ClassObject < 0 )
  {
    InitOnceExecuteOnce(
      &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
      _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_180062B08 = 1;
    *ppv = 0;
    v7 = (const struct _GUID **)((*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                   + 32LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                               + 8);
    v8 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                           + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
    while ( 1 )
    {
      if ( (unsigned __int64)v7 >= v8 )
      {
        ClassObject = -2147221231;
        goto LABEL_10;
      }
      v9 = *v7;
      if ( *v7 )
      {
        v10 = *(_QWORD **)v9->Data4;
        v11 = *v10 - *(_QWORD *)&rclsid->Data1;
        if ( *v10 == *(_QWORD *)&rclsid->Data1 )
          v11 = v10[1] - *(_QWORD *)rclsid->Data4;
        if ( !v11 )
          break;
      }
      ++v7;
    }
    v15 = 1;
    ClassObject = Microsoft::WRL::Details::GetCacheEntry(
                    (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
                    (struct Microsoft::WRL::Details::ModuleBase *)&v15,
                    &riid->Data1,
                    v9,
                    ppv,
                    v14);
LABEL_10:
    if ( ClassObject < 0 )
    {
      ClassObject = -2147024882;
      v12 = (char *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v12 )
      {
        *(_QWORD *)v12 = &CThumbCacheClassFactory::`vftable';
        *((_DWORD *)v12 + 2) = 1;
        DllAddRef();
      }
      else
      {
        v12 = 0;
      }
      if ( v12 )
      {
        *(IID *)(v12 + 12) = *rclsid;
        ClassObject = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v12)(v12, riid, ppv);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
  }
  return ClassObject;
}

```

## disassembly

```asm
0x180018150  mov     r11, rsp
0x180018153  mov     [r11+8], rbx
0x180018157  mov     [r11+10h], rbp
0x18001815b  push    rsi
0x18001815c  push    rdi
0x18001815d  push    r14
0x18001815f  sub     rsp, 30h
0x180018163  mov     r14, r8
0x180018166  mov     rbp, rdx
0x180018169  mov     rsi, rcx
0x18001816c  lea     rax, gPFactory
0x180018173  mov     [r11-20h], rax
0x180018177  lea     rax, CLSID_PSFactoryBuffer
0x18001817e  mov     [r11-28h], rax
0x180018182  lea     r9, aProxyFileList; pProxyFileList
0x180018189  call    cs:__imp_NdrDllGetClassObject
0x18001818f  mov     edi, eax
0x180018191  test    eax, eax
0x180018193  jns     loc_18001829C
0x180018199  xor     r9d, r9d; Context
0x18001819c  xor     r8d, r8d; Parameter
0x18001819f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800181a6  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800181ad  call    cs:__imp_InitOnceExecuteOnce
0x1800181b3  mov     cs:byte_180062B08, 1
0x1800181ba  mov     qword ptr [r14], 0
0x1800181c1  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800181c8  lea     rdi, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800181cf  mov     rcx, rdi
0x1800181d2  mov     rax, [rax+20h]
0x1800181d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181db  lea     rbx, [rax+8]
0x1800181df  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800181e6  mov     rax, [rcx+28h]
0x1800181ea  mov     rcx, rdi
0x1800181ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181f2  cmp     rbx, rax
0x1800181f5  jnb     short loc_180018222
0x1800181f7  mov     r9, [rbx]; struct _GUID *
0x1800181fa  test    r9, r9
0x1800181fd  jz      short loc_18001821C
0x1800181ff  mov     rdx, [r9+8]
0x180018203  mov     rcx, [rdx]
0x180018206  sub     rcx, [rsi]
0x180018209  jnz     short loc_180018213
0x18001820b  mov     rcx, [rdx+8]
0x18001820f  sub     rcx, [rsi+8]
0x180018213  test    rcx, rcx
0x180018216  jz      loc_1800182B1
0x18001821c  add     rbx, 8
0x180018220  jmp     short loc_1800181F2
0x180018222  mov     edi, 80040111h
0x180018227  test    edi, edi
0x180018229  jns     short loc_18001829C
0x18001822b  mov     edi, 8007000Eh
0x180018230  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018237  mov     ecx, 20h ; ' '; unsigned __int64
0x18001823c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018241  mov     rbx, rax
0x180018244  test    rax, rax
0x180018247  jz      loc_1800182D5
0x18001824d  lea     rax, ??_7CThumbCacheClassFactory@@6B@; const CThumbCacheClassFactory::`vftable'
0x180018254  mov     [rbx], rax
0x180018257  mov     dword ptr [rbx+8], 1
0x18001825e  call    DllAddRef
0x180018263  nop
0x180018264  test    rbx, rbx
0x180018267  jz      short loc_180018287
0x180018269  movups  xmm0, xmmword ptr [rsi]
0x18001826c  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x180018271  mov     rax, [rbx]
0x180018274  mov     r8, r14
0x180018277  mov     rdx, rbp
0x18001827a  mov     rcx, rbx
0x18001827d  mov     rax, [rax]
0x180018280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018285  mov     edi, eax
0x180018287  test    rbx, rbx
0x18001828a  jz      short loc_18001829C
0x18001828c  mov     rax, [rbx]
0x18001828f  mov     rcx, rbx
0x180018292  mov     rax, [rax+10h]
0x180018296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001829b  nop
0x18001829c  mov     eax, edi
0x18001829e  mov     rbx, [rsp+48h+arg_0]
0x1800182a3  mov     rbp, [rsp+48h+arg_8]
0x1800182a8  add     rsp, 30h
0x1800182ac  pop     r14
0x1800182ae  pop     rdi
0x1800182af  pop     rsi
0x1800182b0  retn
0x1800182b1  mov     [rsp+48h+arg_18], 1
0x1800182b9  mov     [rsp+48h+Ptr], r14; Ptr
0x1800182be  mov     r8, rbp; unsigned int *
0x1800182c1  lea     rdx, [rsp+48h+arg_18]; struct Microsoft::WRL::Details::ModuleBase *
0x1800182c6  mov     rcx, rdi; this
0x1800182c9  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x1800182ce  mov     edi, eax
0x1800182d0  jmp     loc_180018227
0x1800182d5  xor     ebx, ebx
0x1800182d7  jmp     short loc_180018264
```
