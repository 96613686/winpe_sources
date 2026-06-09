# ClusApi::Group::CreateResource(wchar_t const *,wchar_t const *,CLUSTER_RESOURCE_CREATE_FLAGS,std::shared_ptr<ClusApi::IResource> *)

- ea: `0x180030ef0`
- end: `0x180030f9b`
- name: `?CreateResource@Group@ClusApi@@UEAAJPEB_W0W4CLUSTER_RESOURCE_CREATE_FLAGS@@PEAV?$shared_ptr@UIResource@ClusApi@@@std@@@Z`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180026f7c`
- `0x180027d20`
- `0x180030ef0`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030f33`
- `CLUSAPI!CreateClusterResource` at `0x180030f0d`
- `CLUSAPI!CreateClusterResource` at `0x180030f0d`

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
0x180030ef0  push    rbx
0x180030ef2  push    rbp
0x180030ef3  push    rdi
0x180030ef4  push    r14
0x180030ef6  sub     rsp, 28h
0x180030efa  mov     rbp, rdx
0x180030efd  mov     r14, rcx
0x180030f00  mov     [rsp+48h+arg_0], 0
0x180030f09  mov     rcx, [rcx+20h]; hGroup
0x180030f0d  call    cs:__imp_CreateClusterResource
0x180030f13  mov     rbx, rax
0x180030f16  lea     rcx, [rsp+48h+arg_0]
0x180030f1b  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x180030f20  mov     [rsp+48h+arg_0], rbx
0x180030f25  lea     rax, [rbx-1]
0x180030f29  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180030f2d  ja      short loc_180030F33
0x180030f2f  xor     edi, edi
0x180030f31  jmp     short loc_180030F4C
0x180030f33  call    cs:__imp_GetLastError
0x180030f39  mov     edi, eax
0x180030f3b  test    eax, eax
0x180030f3d  jle     short loc_180030F48
0x180030f3f  movzx   edi, ax
0x180030f42  or      edi, 80070000h
0x180030f48  test    edi, edi
0x180030f4a  js      short loc_180030F85
0x180030f4c  cmp     [rsp+48h+arg_20], 0
0x180030f52  jz      short loc_180030F85
0x180030f54  mov     rax, [r14]
0x180030f57  mov     rcx, r14
0x180030f5a  mov     rax, [rax+50h]
0x180030f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f63  mov     r9, [rsp+48h+arg_20]
0x180030f68  mov     r8, rbp
0x180030f6b  mov     rdx, rbx
0x180030f6e  mov     rcx, rax
0x180030f71  call    ?CreateObject@?$ObjectFactoryT@PEAU_HRESOURCE@@VResource@ClusApi@@V?$shared_ptr@UIResource@ClusApi@@@std@@@ObjectFactory@ClusApi@@SAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@PEAU_HRESOURCE@@PEB_WPEAV?$shared_ptr@UIResource@ClusApi@@@5@@Z; ClusApi::ObjectFactory::ObjectFactoryT<_HRESOURCE *,ClusApi::Resource,std::shared_ptr<ClusApi::IResource>>::CreateObject(std::shared_ptr<ClusApi::ICluster> const &,_HRESOURCE *,wchar_t const *,std::shared_ptr<ClusApi::IResource> *)
0x180030f76  mov     edi, eax
0x180030f78  xor     ecx, ecx
0x180030f7a  test    eax, eax
0x180030f7c  cmovns  rbx, rcx
0x180030f80  mov     [rsp+48h+arg_0], rbx
0x180030f85  lea     rcx, [rsp+48h+arg_0]
0x180030f8a  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x180030f8f  mov     eax, edi
0x180030f91  add     rsp, 28h
0x180030f95  pop     r14
0x180030f97  pop     rdi
0x180030f98  pop     rbp
0x180030f99  pop     rbx
0x180030f9a  retn
```
