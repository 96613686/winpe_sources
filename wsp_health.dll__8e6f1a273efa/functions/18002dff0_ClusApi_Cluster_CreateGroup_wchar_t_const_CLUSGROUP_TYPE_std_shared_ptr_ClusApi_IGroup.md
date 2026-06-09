# ClusApi::Cluster::CreateGroup(wchar_t const *,CLUSGROUP_TYPE,std::shared_ptr<ClusApi::IGroup> *)

- ea: `0x18002dff0`
- end: `0x18002e0f1`
- name: `?CreateGroup@Cluster@ClusApi@@UEAAJPEB_WW4CLUSGROUP_TYPE@@PEAV?$shared_ptr@UIGroup@ClusApi@@@std@@@Z`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000bc64`
- `0x180023d84`
- `0x180024a40`
- `0x18002dff0`
- `0x180034a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e03f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e03f`
- `CLUSAPI!CreateClusterGroupEx` at `0x18002e021`
- `CLUSAPI!CreateClusterGroupEx` at `0x18002e021`

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
0x18002dff0  mov     [rsp-18h+arg_8], rbx
0x18002dff5  mov     [rsp-18h+arg_10], rsi
0x18002dffa  push    rbp
0x18002dffb  push    rdi
0x18002dffc  push    r14
0x18002dffe  mov     rbp, rsp
0x18002e001  sub     rsp, 50h
0x18002e005  mov     r14, r9
0x18002e008  mov     rsi, rdx
0x18002e00b  mov     rdi, rcx
0x18002e00e  mov     [rbp+arg_0], 1
0x18002e015  mov     [rbp+arg_4], r8d
0x18002e019  lea     r8, [rbp+arg_0]
0x18002e01d  mov     rcx, [rcx+18h]
0x18002e021  call    cs:__imp_CreateClusterGroupEx
0x18002e028  nop     dword ptr [rax+rax+00h]
0x18002e02d  mov     rbx, rax
0x18002e030  mov     [rbp+var_30], rax
0x18002e034  inc     rax
0x18002e037  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e03d  jnz     short loc_18002E05C
0x18002e03f  call    cs:__imp_GetLastError
0x18002e046  nop     dword ptr [rax+rax+00h]
0x18002e04b  mov     ebx, eax
0x18002e04d  test    eax, eax
0x18002e04f  jle     short loc_18002E0D0
0x18002e051  movzx   ebx, ax
0x18002e054  or      ebx, 80070000h
0x18002e05a  jmp     short loc_18002E0D0
0x18002e05c  lea     rcx, [rdi+8]
0x18002e060  lea     rdx, [rbp+var_18]
0x18002e064  call    ?shared_from_this@?$enable_shared_from_this@VNode@ClusApi@@@std@@QEAA?AV?$shared_ptr@VNode@ClusApi@@@2@XZ; std::enable_shared_from_this<ClusApi::Node>::shared_from_this(void)
0x18002e069  mov     rdx, rax
0x18002e06c  mov     rcx, [rax]
0x18002e06f  xor     edi, edi
0x18002e071  test    rcx, rcx
0x18002e074  jz      short loc_18002E080
0x18002e076  add     rcx, 8
0x18002e07a  mov     [rbp+var_28], rcx
0x18002e07e  jmp     short loc_18002E084
0x18002e080  mov     [rbp+var_28], rdi
0x18002e084  mov     rax, [rax+8]
0x18002e088  mov     [rbp+var_20], rax
0x18002e08c  mov     [rdx], rdi
0x18002e08f  mov     [rdx+8], rdi
0x18002e093  mov     r9, r14
0x18002e096  mov     r8, rsi
0x18002e099  mov     rdx, rbx
0x18002e09c  lea     rcx, [rbp+var_28]
0x18002e0a0  call    ?CreateObject@?$ObjectFactoryT@PEAU_HGROUP@@VGroup@ClusApi@@V?$shared_ptr@UIGroup@ClusApi@@@std@@@ObjectFactory@ClusApi@@SAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@PEAU_HGROUP@@PEB_WPEAV?$shared_ptr@UIGroup@ClusApi@@@5@@Z; ClusApi::ObjectFactory::ObjectFactoryT<_HGROUP *,ClusApi::Group,std::shared_ptr<ClusApi::IGroup>>::CreateObject(std::shared_ptr<ClusApi::ICluster> const &,_HGROUP *,wchar_t const *,std::shared_ptr<ClusApi::IGroup> *)
0x18002e0a5  mov     esi, eax
0x18002e0a7  mov     rcx, [rbp+var_20]; this
0x18002e0ab  test    rcx, rcx
0x18002e0ae  jz      short loc_18002E0B6
0x18002e0b0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002e0b5  nop
0x18002e0b6  mov     rcx, [rbp+var_10]; this
0x18002e0ba  test    rcx, rcx
0x18002e0bd  jz      short loc_18002E0C4
0x18002e0bf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002e0c4  test    esi, esi
0x18002e0c6  cmovns  rbx, rdi
0x18002e0ca  mov     [rbp+var_30], rbx
0x18002e0ce  mov     ebx, esi
0x18002e0d0  lea     rcx, [rbp+var_30]
0x18002e0d4  call    ?Close@?$AutoHandle@PEAU_HGROUP@@H$1?CloseClusterGroup@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUP *,int,&CloseClusterGroup(_HGROUP *),0>::Close(void)
0x18002e0d9  mov     eax, ebx
0x18002e0db  lea     r11, [rsp+50h+var_s0]
0x18002e0e0  mov     rbx, [r11+28h]
0x18002e0e4  mov     rsi, [r11+30h]
0x18002e0e8  mov     rsp, r11
0x18002e0eb  pop     r14
0x18002e0ed  pop     rdi
0x18002e0ee  pop     rbp
0x18002e0ef  retn
```
