# ClusApi::Group::CreateResource(wchar_t const *,wchar_t const *,CLUSTER_RESOURCE_CREATE_FLAGS,std::shared_ptr<ClusApi::IResource> *)

- ea: `0x18002d1e0`
- end: `0x18002d28b`
- name: `?CreateResource@Group@ClusApi@@UEAAJPEB_W0W4CLUSTER_RESOURCE_CREATE_FLAGS@@PEAV?$shared_ptr@UIResource@ClusApi@@@std@@@Z`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002323c`
- `0x180023fe0`
- `0x18002d1e0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d223`
- `CLUSAPI!CreateClusterResource` at `0x18002d1fd`
- `CLUSAPI!CreateClusterResource` at `0x18002d1fd`

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
0x18002d1e0  push    rbx
0x18002d1e2  push    rbp
0x18002d1e3  push    rdi
0x18002d1e4  push    r14
0x18002d1e6  sub     rsp, 28h
0x18002d1ea  mov     rbp, rdx
0x18002d1ed  mov     r14, rcx
0x18002d1f0  mov     [rsp+48h+arg_0], 0
0x18002d1f9  mov     rcx, [rcx+20h]; hGroup
0x18002d1fd  call    cs:__imp_CreateClusterResource
0x18002d203  mov     rbx, rax
0x18002d206  lea     rcx, [rsp+48h+arg_0]
0x18002d20b  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x18002d210  mov     [rsp+48h+arg_0], rbx
0x18002d215  lea     rax, [rbx-1]
0x18002d219  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002d21d  ja      short loc_18002D223
0x18002d21f  xor     edi, edi
0x18002d221  jmp     short loc_18002D23C
0x18002d223  call    cs:__imp_GetLastError
0x18002d229  mov     edi, eax
0x18002d22b  test    eax, eax
0x18002d22d  jle     short loc_18002D238
0x18002d22f  movzx   edi, ax
0x18002d232  or      edi, 80070000h
0x18002d238  test    edi, edi
0x18002d23a  js      short loc_18002D275
0x18002d23c  cmp     [rsp+48h+arg_20], 0
0x18002d242  jz      short loc_18002D275
0x18002d244  mov     rax, [r14]
0x18002d247  mov     rcx, r14
0x18002d24a  mov     rax, [rax+50h]
0x18002d24e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d253  mov     r9, [rsp+48h+arg_20]
0x18002d258  mov     r8, rbp
0x18002d25b  mov     rdx, rbx
0x18002d25e  mov     rcx, rax
0x18002d261  call    ?CreateObject@?$ObjectFactoryT@PEAU_HRESOURCE@@VResource@ClusApi@@V?$shared_ptr@UIResource@ClusApi@@@std@@@ObjectFactory@ClusApi@@SAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@PEAU_HRESOURCE@@PEB_WPEAV?$shared_ptr@UIResource@ClusApi@@@5@@Z; ClusApi::ObjectFactory::ObjectFactoryT<_HRESOURCE *,ClusApi::Resource,std::shared_ptr<ClusApi::IResource>>::CreateObject(std::shared_ptr<ClusApi::ICluster> const &,_HRESOURCE *,wchar_t const *,std::shared_ptr<ClusApi::IResource> *)
0x18002d266  mov     edi, eax
0x18002d268  xor     ecx, ecx
0x18002d26a  test    eax, eax
0x18002d26c  cmovns  rbx, rcx
0x18002d270  mov     [rsp+48h+arg_0], rbx
0x18002d275  lea     rcx, [rsp+48h+arg_0]
0x18002d27a  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x18002d27f  mov     eax, edi
0x18002d281  add     rsp, 28h
0x18002d285  pop     r14
0x18002d287  pop     rdi
0x18002d288  pop     rbp
0x18002d289  pop     rbx
0x18002d28a  retn
```
