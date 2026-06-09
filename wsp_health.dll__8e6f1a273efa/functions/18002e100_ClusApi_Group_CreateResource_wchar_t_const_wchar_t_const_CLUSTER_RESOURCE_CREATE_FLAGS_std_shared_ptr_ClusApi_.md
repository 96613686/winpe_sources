# ClusApi::Group::CreateResource(wchar_t const *,wchar_t const *,CLUSTER_RESOURCE_CREATE_FLAGS,std::shared_ptr<ClusApi::IResource> *)

- ea: `0x18002e100`
- end: `0x18002e1b8`
- name: `?CreateResource@Group@ClusApi@@UEAAJPEB_W0W4CLUSTER_RESOURCE_CREATE_FLAGS@@PEAV?$shared_ptr@UIResource@ClusApi@@@std@@@Z`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180023e64`
- `0x180024c18`
- `0x18002e100`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e149`
- `CLUSAPI!CreateClusterResource` at `0x18002e11d`
- `CLUSAPI!CreateClusterResource` at `0x18002e11d`

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
0x18002e100  push    rbx
0x18002e102  push    rbp
0x18002e103  push    rdi
0x18002e104  push    r14
0x18002e106  sub     rsp, 28h
0x18002e10a  mov     rbp, rdx
0x18002e10d  mov     r14, rcx
0x18002e110  mov     [rsp+48h+arg_0], 0
0x18002e119  mov     rcx, [rcx+20h]; hGroup
0x18002e11d  call    cs:__imp_CreateClusterResource
0x18002e124  nop     dword ptr [rax+rax+00h]
0x18002e129  mov     rbx, rax
0x18002e12c  lea     rcx, [rsp+48h+arg_0]
0x18002e131  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x18002e136  mov     [rsp+48h+arg_0], rbx
0x18002e13b  lea     rax, [rbx-1]
0x18002e13f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002e143  ja      short loc_18002E149
0x18002e145  xor     edi, edi
0x18002e147  jmp     short loc_18002E168
0x18002e149  call    cs:__imp_GetLastError
0x18002e150  nop     dword ptr [rax+rax+00h]
0x18002e155  mov     edi, eax
0x18002e157  test    eax, eax
0x18002e159  jle     short loc_18002E164
0x18002e15b  movzx   edi, ax
0x18002e15e  or      edi, 80070000h
0x18002e164  test    edi, edi
0x18002e166  js      short loc_18002E1A1
0x18002e168  cmp     [rsp+48h+arg_20], 0
0x18002e16e  jz      short loc_18002E1A1
0x18002e170  mov     rax, [r14]
0x18002e173  mov     rcx, r14
0x18002e176  mov     rax, [rax+50h]
0x18002e17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e17f  mov     r9, [rsp+48h+arg_20]
0x18002e184  mov     r8, rbp
0x18002e187  mov     rdx, rbx
0x18002e18a  mov     rcx, rax
0x18002e18d  call    ?CreateObject@?$ObjectFactoryT@PEAU_HRESOURCE@@VResource@ClusApi@@V?$shared_ptr@UIResource@ClusApi@@@std@@@ObjectFactory@ClusApi@@SAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@PEAU_HRESOURCE@@PEB_WPEAV?$shared_ptr@UIResource@ClusApi@@@5@@Z; ClusApi::ObjectFactory::ObjectFactoryT<_HRESOURCE *,ClusApi::Resource,std::shared_ptr<ClusApi::IResource>>::CreateObject(std::shared_ptr<ClusApi::ICluster> const &,_HRESOURCE *,wchar_t const *,std::shared_ptr<ClusApi::IResource> *)
0x18002e192  mov     edi, eax
0x18002e194  xor     ecx, ecx
0x18002e196  test    eax, eax
0x18002e198  cmovns  rbx, rcx
0x18002e19c  mov     [rsp+48h+arg_0], rbx
0x18002e1a1  lea     rcx, [rsp+48h+arg_0]
0x18002e1a6  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x18002e1ab  mov     eax, edi
0x18002e1ad  add     rsp, 28h
0x18002e1b1  pop     r14
0x18002e1b3  pop     rdi
0x18002e1b4  pop     rbp
0x18002e1b5  pop     rbx
0x18002e1b6  retn
```
