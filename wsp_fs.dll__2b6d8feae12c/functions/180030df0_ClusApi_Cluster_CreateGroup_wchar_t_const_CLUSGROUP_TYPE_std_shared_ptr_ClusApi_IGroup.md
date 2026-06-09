# ClusApi::Cluster::CreateGroup(wchar_t const *,CLUSGROUP_TYPE,std::shared_ptr<ClusApi::IGroup> *)

- ea: `0x180030df0`
- end: `0x180030ee4`
- name: `?CreateGroup@Cluster@ClusApi@@UEAAJPEB_WW4CLUSGROUP_TYPE@@PEAV?$shared_ptr@UIGroup@ClusApi@@@std@@@Z`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000c284`
- `0x180026ebc`
- `0x180027b48`
- `0x180030df0`
- `0x180037604`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e39`
- `CLUSAPI!CreateClusterGroupEx` at `0x180030e21`
- `CLUSAPI!CreateClusterGroupEx` at `0x180030e21`

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
0x180030df0  mov     [rsp-18h+arg_8], rbx
0x180030df5  mov     [rsp-18h+arg_10], rsi
0x180030dfa  push    rbp
0x180030dfb  push    rdi
0x180030dfc  push    r14
0x180030dfe  mov     rbp, rsp
0x180030e01  sub     rsp, 50h
0x180030e05  mov     r14, r9
0x180030e08  mov     rsi, rdx
0x180030e0b  mov     rdi, rcx
0x180030e0e  mov     [rbp+arg_0], 1
0x180030e15  mov     [rbp+arg_4], r8d
0x180030e19  lea     r8, [rbp+arg_0]
0x180030e1d  mov     rcx, [rcx+18h]
0x180030e21  call    cs:__imp_CreateClusterGroupEx
0x180030e27  mov     rbx, rax
0x180030e2a  mov     [rbp+var_30], rax
0x180030e2e  inc     rax
0x180030e31  test    rax, 0FFFFFFFFFFFFFFFEh
0x180030e37  jnz     short loc_180030E50
0x180030e39  call    cs:__imp_GetLastError
0x180030e3f  mov     ebx, eax
0x180030e41  test    eax, eax
0x180030e43  jle     short loc_180030EC4
0x180030e45  movzx   ebx, ax
0x180030e48  or      ebx, 80070000h
0x180030e4e  jmp     short loc_180030EC4
0x180030e50  lea     rcx, [rdi+8]
0x180030e54  lea     rdx, [rbp+var_18]
0x180030e58  call    ?shared_from_this@?$enable_shared_from_this@VNode@ClusApi@@@std@@QEAA?AV?$shared_ptr@VNode@ClusApi@@@2@XZ; std::enable_shared_from_this<ClusApi::Node>::shared_from_this(void)
0x180030e5d  mov     rdx, rax
0x180030e60  mov     rcx, [rax]
0x180030e63  xor     edi, edi
0x180030e65  test    rcx, rcx
0x180030e68  jz      short loc_180030E74
0x180030e6a  add     rcx, 8
0x180030e6e  mov     [rbp+var_28], rcx
0x180030e72  jmp     short loc_180030E78
0x180030e74  mov     [rbp+var_28], rdi
0x180030e78  mov     rax, [rax+8]
0x180030e7c  mov     [rbp+var_20], rax
0x180030e80  mov     [rdx], rdi
0x180030e83  mov     [rdx+8], rdi
0x180030e87  mov     r9, r14
0x180030e8a  mov     r8, rsi
0x180030e8d  mov     rdx, rbx
0x180030e90  lea     rcx, [rbp+var_28]
0x180030e94  call    ?CreateObject@?$ObjectFactoryT@PEAU_HGROUP@@VGroup@ClusApi@@V?$shared_ptr@UIGroup@ClusApi@@@std@@@ObjectFactory@ClusApi@@SAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@PEAU_HGROUP@@PEB_WPEAV?$shared_ptr@UIGroup@ClusApi@@@5@@Z; ClusApi::ObjectFactory::ObjectFactoryT<_HGROUP *,ClusApi::Group,std::shared_ptr<ClusApi::IGroup>>::CreateObject(std::shared_ptr<ClusApi::ICluster> const &,_HGROUP *,wchar_t const *,std::shared_ptr<ClusApi::IGroup> *)
0x180030e99  mov     esi, eax
0x180030e9b  mov     rcx, [rbp+var_20]; this
0x180030e9f  test    rcx, rcx
0x180030ea2  jz      short loc_180030EAA
0x180030ea4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180030ea9  nop
0x180030eaa  mov     rcx, [rbp+var_10]; this
0x180030eae  test    rcx, rcx
0x180030eb1  jz      short loc_180030EB8
0x180030eb3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180030eb8  test    esi, esi
0x180030eba  cmovns  rbx, rdi
0x180030ebe  mov     [rbp+var_30], rbx
0x180030ec2  mov     ebx, esi
0x180030ec4  lea     rcx, [rbp+var_30]
0x180030ec8  call    ?Close@?$AutoHandle@PEAU_HGROUP@@H$1?CloseClusterGroup@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUP *,int,&CloseClusterGroup(_HGROUP *),0>::Close(void)
0x180030ecd  mov     eax, ebx
0x180030ecf  lea     r11, [rsp+50h+var_s0]
0x180030ed4  mov     rbx, [r11+28h]
0x180030ed8  mov     rsi, [r11+30h]
0x180030edc  mov     rsp, r11
0x180030edf  pop     r14
0x180030ee1  pop     rdi
0x180030ee2  pop     rbp
0x180030ee3  retn
```
