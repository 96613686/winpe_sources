# ClusApi::Group::CreateResource(wchar_t const *,wchar_t const *,CLUSTER_RESOURCE_CREATE_FLAGS,std::shared_ptr<ClusApi::IResource> *)

- ea: `0x180031f20`
- end: `0x180031fd8`
- name: `?CreateResource@Group@ClusApi@@UEAAJPEB_W0W4CLUSTER_RESOURCE_CREATE_FLAGS@@PEAV?$shared_ptr@UIResource@ClusApi@@@std@@@Z`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180027ca4`
- `0x180028a58`
- `0x180031f20`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031f69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031f69`
- `CLUSAPI!CreateClusterResource` at `0x180031f3d`
- `CLUSAPI!CreateClusterResource` at `0x180031f3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClusApi::Group::CreateResource(HGROUP *a1, const WCHAR *a2, const WCHAR *a3, DWORD a4, __int64 a5)
{
  HRESOURCE ClusterResource; // rbx
  signed int Object; // edi
  signed int LastError; // eax
  __int64 v10; // rax
  HRESOURCE v12; // [rsp+50h] [rbp+8h] BYREF

  v12 = 0;
  ClusterResource = CreateClusterResource(a1[4], a2, a3, a4);
  cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(&v12);
  v12 = ClusterResource;
  if ( (unsigned __int64)ClusterResource - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    Object = 0;
LABEL_6:
    if ( a5 )
    {
      v10 = (*((__int64 (__fastcall **)(HGROUP *))*a1 + 10))(a1);
      Object = ClusApi::ObjectFactory::ObjectFactoryT<_HRESOURCE *,ClusApi::Resource,std::shared_ptr<ClusApi::IResource>>::CreateObject(
                 v10,
                 ClusterResource,
                 a2,
                 a5);
      if ( Object >= 0 )
        ClusterResource = 0;
      v12 = ClusterResource;
    }
    goto LABEL_10;
  }
  LastError = GetLastError();
  Object = LastError;
  if ( LastError > 0 )
    Object = (unsigned __int16)LastError | 0x80070000;
  if ( Object >= 0 )
    goto LABEL_6;
LABEL_10:
  cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(&v12);
  return (unsigned int)Object;
}

```

## disassembly

```asm
0x180031f20  push    rbx
0x180031f22  push    rbp
0x180031f23  push    rdi
0x180031f24  push    r14
0x180031f26  sub     rsp, 28h
0x180031f2a  mov     rbp, rdx
0x180031f2d  mov     r14, rcx
0x180031f30  mov     [rsp+48h+arg_0], 0
0x180031f39  mov     rcx, [rcx+20h]; hGroup
0x180031f3d  call    cs:__imp_CreateClusterResource
0x180031f44  nop     dword ptr [rax+rax+00h]
0x180031f49  mov     rbx, rax
0x180031f4c  lea     rcx, [rsp+48h+arg_0]
0x180031f51  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x180031f56  mov     [rsp+48h+arg_0], rbx
0x180031f5b  lea     rax, [rbx-1]
0x180031f5f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180031f63  ja      short loc_180031F69
0x180031f65  xor     edi, edi
0x180031f67  jmp     short loc_180031F88
0x180031f69  call    cs:__imp_GetLastError
0x180031f70  nop     dword ptr [rax+rax+00h]
0x180031f75  mov     edi, eax
0x180031f77  test    eax, eax
0x180031f79  jle     short loc_180031F84
0x180031f7b  movzx   edi, ax
0x180031f7e  or      edi, 80070000h
0x180031f84  test    edi, edi
0x180031f86  js      short loc_180031FC1
0x180031f88  cmp     [rsp+48h+arg_20], 0
0x180031f8e  jz      short loc_180031FC1
0x180031f90  mov     rax, [r14]
0x180031f93  mov     rcx, r14
0x180031f96  mov     rax, [rax+50h]
0x180031f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f9f  mov     r9, [rsp+48h+arg_20]
0x180031fa4  mov     r8, rbp
0x180031fa7  mov     rdx, rbx
0x180031faa  mov     rcx, rax
0x180031fad  call    ?CreateObject@?$ObjectFactoryT@PEAU_HRESOURCE@@VResource@ClusApi@@V?$shared_ptr@UIResource@ClusApi@@@std@@@ObjectFactory@ClusApi@@SAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@PEAU_HRESOURCE@@PEB_WPEAV?$shared_ptr@UIResource@ClusApi@@@5@@Z; ClusApi::ObjectFactory::ObjectFactoryT<_HRESOURCE *,ClusApi::Resource,std::shared_ptr<ClusApi::IResource>>::CreateObject(std::shared_ptr<ClusApi::ICluster> const &,_HRESOURCE *,wchar_t const *,std::shared_ptr<ClusApi::IResource> *)
0x180031fb2  mov     edi, eax
0x180031fb4  xor     ecx, ecx
0x180031fb6  test    eax, eax
0x180031fb8  cmovns  rbx, rcx
0x180031fbc  mov     [rsp+48h+arg_0], rbx
0x180031fc1  lea     rcx, [rsp+48h+arg_0]
0x180031fc6  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x180031fcb  mov     eax, edi
0x180031fcd  add     rsp, 28h
0x180031fd1  pop     r14
0x180031fd3  pop     rdi
0x180031fd4  pop     rbp
0x180031fd5  pop     rbx
0x180031fd6  retn
```
