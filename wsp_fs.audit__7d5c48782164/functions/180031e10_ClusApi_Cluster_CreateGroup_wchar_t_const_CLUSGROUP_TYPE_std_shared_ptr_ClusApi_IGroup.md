# ClusApi::Cluster::CreateGroup(wchar_t const *,CLUSGROUP_TYPE,std::shared_ptr<ClusApi::IGroup> *)

- ea: `0x180031e10`
- end: `0x180031f11`
- name: `?CreateGroup@Cluster@ClusApi@@UEAAJPEB_WW4CLUSGROUP_TYPE@@PEAV?$shared_ptr@UIGroup@ClusApi@@@std@@@Z`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000c5c4`
- `0x180027bc4`
- `0x180028880`
- `0x180031e10`
- `0x1800388d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e5f`
- `CLUSAPI!CreateClusterGroupEx` at `0x180031e41`
- `CLUSAPI!CreateClusterGroupEx` at `0x180031e41`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ClusApi::Cluster::CreateGroup(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v7; // rbx
  signed int LastError; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  int v11; // esi
  __int64 v13; // [rsp+20h] [rbp-30h] BYREF
  __int64 v14; // [rsp+28h] [rbp-28h] BYREF
  std::_Ref_count_base *v15; // [rsp+30h] [rbp-20h]
  _BYTE v16[8]; // [rsp+38h] [rbp-18h] BYREF
  std::_Ref_count_base *v17; // [rsp+40h] [rbp-10h]
  int v18; // [rsp+70h] [rbp+20h] BYREF
  int v19; // [rsp+74h] [rbp+24h]

  v18 = 1;
  v19 = a3;
  v7 = CreateClusterGroupEx(*(_QWORD *)(a1 + 24), a2, &v18);
  v13 = v7;
  if ( ((v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v10 = std::enable_shared_from_this<ClusApi::Node>::shared_from_this(a1 + 8, v16);
    if ( *(_QWORD *)v10 )
      v14 = *(_QWORD *)v10 + 8LL;
    else
      v14 = 0;
    v15 = *(std::_Ref_count_base **)(v10 + 8);
    *(_QWORD *)v10 = 0;
    *(_QWORD *)(v10 + 8) = 0;
    v11 = ((__int64 (__fastcall *)(__int64 *, __int64, __int64, __int64, __int64))ClusApi::ObjectFactory::ObjectFactoryT<_HGROUP *,ClusApi::Group,std::shared_ptr<ClusApi::IGroup>>::CreateObject)(
            &v14,
            v7,
            a2,
            a4,
            v13);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v11 >= 0 )
      v7 = 0;
    v13 = v7;
    v9 = v11;
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  cxl::AutoHandle<_HGROUP *,int,&int CloseClusterGroup(_HGROUP *),0>::Close(&v13);
  return v9;
}

```

## disassembly

```asm
0x180031e10  mov     [rsp-18h+arg_8], rbx
0x180031e15  mov     [rsp-18h+arg_10], rsi
0x180031e1a  push    rbp
0x180031e1b  push    rdi
0x180031e1c  push    r14
0x180031e1e  mov     rbp, rsp
0x180031e21  sub     rsp, 50h
0x180031e25  mov     r14, r9
0x180031e28  mov     rsi, rdx
0x180031e2b  mov     rdi, rcx
0x180031e2e  mov     [rbp+arg_0], 1
0x180031e35  mov     [rbp+arg_4], r8d
0x180031e39  lea     r8, [rbp+arg_0]
0x180031e3d  mov     rcx, [rcx+18h]
0x180031e41  call    cs:__imp_CreateClusterGroupEx
0x180031e48  nop     dword ptr [rax+rax+00h]
0x180031e4d  mov     rbx, rax
0x180031e50  mov     [rbp+var_30], rax
0x180031e54  inc     rax
0x180031e57  test    rax, 0FFFFFFFFFFFFFFFEh
0x180031e5d  jnz     short loc_180031E7C
0x180031e5f  call    cs:__imp_GetLastError
0x180031e66  nop     dword ptr [rax+rax+00h]
0x180031e6b  mov     ebx, eax
0x180031e6d  test    eax, eax
0x180031e6f  jle     short loc_180031EF0
0x180031e71  movzx   ebx, ax
0x180031e74  or      ebx, 80070000h
0x180031e7a  jmp     short loc_180031EF0
0x180031e7c  lea     rcx, [rdi+8]
0x180031e80  lea     rdx, [rbp+var_18]
0x180031e84  call    ?shared_from_this@?$enable_shared_from_this@VNode@ClusApi@@@std@@QEAA?AV?$shared_ptr@VNode@ClusApi@@@2@XZ; std::enable_shared_from_this<ClusApi::Node>::shared_from_this(void)
0x180031e89  mov     rdx, rax
0x180031e8c  mov     rcx, [rax]
0x180031e8f  xor     edi, edi
0x180031e91  test    rcx, rcx
0x180031e94  jz      short loc_180031EA0
0x180031e96  add     rcx, 8
0x180031e9a  mov     [rbp+var_28], rcx
0x180031e9e  jmp     short loc_180031EA4
0x180031ea0  mov     [rbp+var_28], rdi
0x180031ea4  mov     rax, [rax+8]
0x180031ea8  mov     [rbp+var_20], rax
0x180031eac  mov     [rdx], rdi
0x180031eaf  mov     [rdx+8], rdi
0x180031eb3  mov     r9, r14
0x180031eb6  mov     r8, rsi
0x180031eb9  mov     rdx, rbx
0x180031ebc  lea     rcx, [rbp+var_28]
0x180031ec0  call    ?CreateObject@?$ObjectFactoryT@PEAU_HGROUP@@VGroup@ClusApi@@V?$shared_ptr@UIGroup@ClusApi@@@std@@@ObjectFactory@ClusApi@@SAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@PEAU_HGROUP@@PEB_WPEAV?$shared_ptr@UIGroup@ClusApi@@@5@@Z; ClusApi::ObjectFactory::ObjectFactoryT<_HGROUP *,ClusApi::Group,std::shared_ptr<ClusApi::IGroup>>::CreateObject(std::shared_ptr<ClusApi::ICluster> const &,_HGROUP *,wchar_t const *,std::shared_ptr<ClusApi::IGroup> *)
0x180031ec5  mov     esi, eax
0x180031ec7  mov     rcx, [rbp+var_20]; this
0x180031ecb  test    rcx, rcx
0x180031ece  jz      short loc_180031ED6
0x180031ed0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031ed5  nop
0x180031ed6  mov     rcx, [rbp+var_10]; this
0x180031eda  test    rcx, rcx
0x180031edd  jz      short loc_180031EE4
0x180031edf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031ee4  test    esi, esi
0x180031ee6  cmovns  rbx, rdi
0x180031eea  mov     [rbp+var_30], rbx
0x180031eee  mov     ebx, esi
0x180031ef0  lea     rcx, [rbp+var_30]
0x180031ef4  call    ?Close@?$AutoHandle@PEAU_HGROUP@@H$1?CloseClusterGroup@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUP *,int,&CloseClusterGroup(_HGROUP *),0>::Close(void)
0x180031ef9  mov     eax, ebx
0x180031efb  lea     r11, [rsp+50h+var_s0]
0x180031f00  mov     rbx, [r11+28h]
0x180031f04  mov     rsi, [r11+30h]
0x180031f08  mov     rsp, r11
0x180031f0b  pop     r14
0x180031f0d  pop     rdi
0x180031f0e  pop     rbp
0x180031f0f  retn
```
