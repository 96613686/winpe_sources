# ClusApi::Cluster::CreateGroup(wchar_t const *,CLUSGROUP_TYPE,std::shared_ptr<ClusApi::IGroup> *)

- ea: `0x18002d0e0`
- end: `0x18002d1d4`
- name: `?CreateGroup@Cluster@ClusApi@@UEAAJPEB_WW4CLUSGROUP_TYPE@@PEAV?$shared_ptr@UIGroup@ClusApi@@@std@@@Z`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000b8e4`
- `0x18002317c`
- `0x180023e08`
- `0x18002d0e0`
- `0x180033910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d129`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d129`
- `CLUSAPI!CreateClusterGroupEx` at `0x18002d111`
- `CLUSAPI!CreateClusterGroupEx` at `0x18002d111`

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
0x18002d0e0  mov     [rsp-18h+arg_8], rbx
0x18002d0e5  mov     [rsp-18h+arg_10], rsi
0x18002d0ea  push    rbp
0x18002d0eb  push    rdi
0x18002d0ec  push    r14
0x18002d0ee  mov     rbp, rsp
0x18002d0f1  sub     rsp, 50h
0x18002d0f5  mov     r14, r9
0x18002d0f8  mov     rsi, rdx
0x18002d0fb  mov     rdi, rcx
0x18002d0fe  mov     [rbp+arg_0], 1
0x18002d105  mov     [rbp+arg_4], r8d
0x18002d109  lea     r8, [rbp+arg_0]
0x18002d10d  mov     rcx, [rcx+18h]
0x18002d111  call    cs:__imp_CreateClusterGroupEx
0x18002d117  mov     rbx, rax
0x18002d11a  mov     [rbp+var_30], rax
0x18002d11e  inc     rax
0x18002d121  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002d127  jnz     short loc_18002D140
0x18002d129  call    cs:__imp_GetLastError
0x18002d12f  mov     ebx, eax
0x18002d131  test    eax, eax
0x18002d133  jle     short loc_18002D1B4
0x18002d135  movzx   ebx, ax
0x18002d138  or      ebx, 80070000h
0x18002d13e  jmp     short loc_18002D1B4
0x18002d140  lea     rcx, [rdi+8]
0x18002d144  lea     rdx, [rbp+var_18]
0x18002d148  call    ?shared_from_this@?$enable_shared_from_this@VNode@ClusApi@@@std@@QEAA?AV?$shared_ptr@VNode@ClusApi@@@2@XZ; std::enable_shared_from_this<ClusApi::Node>::shared_from_this(void)
0x18002d14d  mov     rdx, rax
0x18002d150  mov     rcx, [rax]
0x18002d153  xor     edi, edi
0x18002d155  test    rcx, rcx
0x18002d158  jz      short loc_18002D164
0x18002d15a  add     rcx, 8
0x18002d15e  mov     [rbp+var_28], rcx
0x18002d162  jmp     short loc_18002D168
0x18002d164  mov     [rbp+var_28], rdi
0x18002d168  mov     rax, [rax+8]
0x18002d16c  mov     [rbp+var_20], rax
0x18002d170  mov     [rdx], rdi
0x18002d173  mov     [rdx+8], rdi
0x18002d177  mov     r9, r14
0x18002d17a  mov     r8, rsi
0x18002d17d  mov     rdx, rbx
0x18002d180  lea     rcx, [rbp+var_28]
0x18002d184  call    ?CreateObject@?$ObjectFactoryT@PEAU_HGROUP@@VGroup@ClusApi@@V?$shared_ptr@UIGroup@ClusApi@@@std@@@ObjectFactory@ClusApi@@SAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@PEAU_HGROUP@@PEB_WPEAV?$shared_ptr@UIGroup@ClusApi@@@5@@Z; ClusApi::ObjectFactory::ObjectFactoryT<_HGROUP *,ClusApi::Group,std::shared_ptr<ClusApi::IGroup>>::CreateObject(std::shared_ptr<ClusApi::ICluster> const &,_HGROUP *,wchar_t const *,std::shared_ptr<ClusApi::IGroup> *)
0x18002d189  mov     esi, eax
0x18002d18b  mov     rcx, [rbp+var_20]; this
0x18002d18f  test    rcx, rcx
0x18002d192  jz      short loc_18002D19A
0x18002d194  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002d199  nop
0x18002d19a  mov     rcx, [rbp+var_10]; this
0x18002d19e  test    rcx, rcx
0x18002d1a1  jz      short loc_18002D1A8
0x18002d1a3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002d1a8  test    esi, esi
0x18002d1aa  cmovns  rbx, rdi
0x18002d1ae  mov     [rbp+var_30], rbx
0x18002d1b2  mov     ebx, esi
0x18002d1b4  lea     rcx, [rbp+var_30]
0x18002d1b8  call    ?Close@?$AutoHandle@PEAU_HGROUP@@H$1?CloseClusterGroup@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUP *,int,&CloseClusterGroup(_HGROUP *),0>::Close(void)
0x18002d1bd  mov     eax, ebx
0x18002d1bf  lea     r11, [rsp+50h+var_s0]
0x18002d1c4  mov     rbx, [r11+28h]
0x18002d1c8  mov     rsi, [r11+30h]
0x18002d1cc  mov     rsp, r11
0x18002d1cf  pop     r14
0x18002d1d1  pop     rdi
0x18002d1d2  pop     rbp
0x18002d1d3  retn
```
