# ClusApi::ResourceType::GetAvailableStoragePools(std::list<std::shared_ptr<ClusApi::IAvailableStoragePool>,std::allocator<std::shared_ptr<ClusApi::IAvailableStoragePool>>> *)

- ea: `0x180031db0`
- end: `0x180031ee1`
- name: `?GetAvailableStoragePools@ResourceType@ClusApi@@UEAAJPEAV?$list@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@@2@@std@@@Z`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002a94`
- `0x18000c284`
- `0x18000dd74`
- `0x180023e24`
- `0x18002ead4`
- `0x180031db0`
- `0x180037604`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031df4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031df4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ClusApi::ResourceType::GetAvailableStoragePools(__int64 a1, __int64 a2)
{
  const WCHAR *v4; // rax
  int v5; // ebx
  _QWORD *v6; // rax
  _QWORD *v7; // rdx
  __int64 v8; // rcx
  std::_Ref_count_base *v9; // rax
  std::_Ref_count_base *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-38h] BYREF
  std::_Ref_count_base *v13; // [rsp+38h] [rbp-30h]
  std::_Ref_count_base *v14[2]; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v15[8]; // [rsp+50h] [rbp-18h] BYREF
  std::_Ref_count_base *v16; // [rsp+58h] [rbp-10h]
  _DWORD *v17; // [rsp+90h] [rbp+28h]

  *(_OWORD *)v14 = 0;
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 56);
  if ( CompareStringW(0x400u, 1u, v4, -1, L"Storage Pool", -1) == 2 )
  {
    v6 = (_QWORD *)std::enable_shared_from_this<ClusApi::Node>::shared_from_this(a1 + 24, v15);
    v7 = v6;
    v8 = *v6;
    if ( *v6 )
      v8 += 8;
    v12 = v8;
    v9 = (std::_Ref_count_base *)v6[1];
    v13 = v9;
    *v7 = 0;
    v7[1] = 0;
    if ( v8 )
    {
      v17 = operator new(0xD0u);
      *(_OWORD *)v17 = 0;
      v17[2] = 1;
      v17[3] = 1;
      *(_QWORD *)v17 = &std::_Ref_count_obj2<ClusApi::AvailableStoragePoolItem>::`vftable';
      std::_Construct_in_place<ClusApi::AvailableStoragePoolItem,std::shared_ptr<ClusApi::IResourceType> const &>(
        v17 + 4,
        &v12);
      v14[0] = (std::_Ref_count_base *)(v17 + 4);
      v14[1] = (std::_Ref_count_base *)v17;
      v5 = 0;
      v9 = v13;
    }
    else
    {
      v5 = -2147024809;
    }
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    v10 = v16;
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    if ( v5 >= 0 )
      v5 = ClusApi::ResourceType::GetStorageList<ClusApi::IAvailableStoragePool>(v10, v14, a2);
  }
  else
  {
    v5 = -2147020579;
  }
  if ( v14[1] )
    std::_Ref_count_base::_Decref(v14[1]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180031db0  push    rbp
0x180031db2  push    rbx
0x180031db3  push    rsi
0x180031db4  push    rdi
0x180031db5  mov     rbp, rsp
0x180031db8  sub     rsp, 68h
0x180031dbc  mov     rsi, rdx
0x180031dbf  mov     rbx, rcx
0x180031dc2  xorps   xmm0, xmm0
0x180031dc5  movdqu  xmmword ptr [rbp+var_28], xmm0
0x180031dca  add     rcx, 38h ; '8'
0x180031dce  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180031dd3  or      r9d, 0FFFFFFFFh; cchCount1
0x180031dd7  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x180031ddc  lea     rcx, String2; "Storage Pool"
0x180031de3  mov     [rsp+68h+lpString2], rcx; lpString2
0x180031de8  mov     r8, rax; lpString1
0x180031deb  lea     edx, [r9+2]; dwCmpFlags
0x180031def  mov     ecx, 400h; Locale
0x180031df4  call    cs:__imp_CompareStringW
0x180031dfa  cmp     eax, 2
0x180031dfd  jz      short loc_180031E09
0x180031dff  mov     ebx, 800710DDh
0x180031e04  jmp     loc_180031EC8
0x180031e09  lea     rcx, [rbx+18h]
0x180031e0d  lea     rdx, [rbp+var_18]
0x180031e11  call    ?shared_from_this@?$enable_shared_from_this@VNode@ClusApi@@@std@@QEAA?AV?$shared_ptr@VNode@ClusApi@@@2@XZ; std::enable_shared_from_this<ClusApi::Node>::shared_from_this(void)
0x180031e16  mov     rdx, rax
0x180031e19  mov     rcx, [rax]
0x180031e1c  test    rcx, rcx
0x180031e1f  jz      short loc_180031E25
0x180031e21  add     rcx, 8
0x180031e25  mov     [rbp+var_38], rcx
0x180031e29  mov     rax, [rax+8]
0x180031e2d  mov     [rbp+var_30], rax
0x180031e31  mov     qword ptr [rdx], 0
0x180031e38  mov     qword ptr [rdx+8], 0
0x180031e40  test    rcx, rcx
0x180031e43  jz      short loc_180031E95
0x180031e45  mov     ecx, 0D0h; Size
0x180031e4a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031e4f  mov     rdi, rax
0x180031e52  mov     [rbp+arg_0], rax
0x180031e56  xorps   xmm0, xmm0
0x180031e59  movups  xmmword ptr [rax], xmm0
0x180031e5c  mov     dword ptr [rax+8], 1
0x180031e63  mov     dword ptr [rax+0Ch], 1
0x180031e6a  lea     rax, ??_7?$_Ref_count_obj2@VAvailableStoragePoolItem@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::AvailableStoragePoolItem>::`vftable'
0x180031e71  mov     [rdi], rax
0x180031e74  lea     rbx, [rdi+10h]
0x180031e78  lea     rdx, [rbp+var_38]
0x180031e7c  mov     rcx, rbx
0x180031e7f  call    ??$_Construct_in_place@VAvailableStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResourceType@ClusApi@@@std@@@std@@YAXAEAVAvailableStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResourceType@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::AvailableStoragePoolItem,std::shared_ptr<ClusApi::IResourceType> const &>(ClusApi::AvailableStoragePoolItem &,std::shared_ptr<ClusApi::IResourceType> const &)
0x180031e84  nop
0x180031e85  mov     [rbp+var_28], rbx
0x180031e89  mov     [rbp+var_28+8], rdi
0x180031e8d  xor     ebx, ebx
0x180031e8f  mov     rax, [rbp+var_30]
0x180031e93  jmp     short loc_180031E9A
0x180031e95  mov     ebx, 80070057h
0x180031e9a  test    rax, rax
0x180031e9d  jz      short loc_180031EA8
0x180031e9f  mov     rcx, rax; this
0x180031ea2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031ea7  nop
0x180031ea8  mov     rcx, [rbp+var_10]; this
0x180031eac  test    rcx, rcx
0x180031eaf  jz      short loc_180031EB6
0x180031eb1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031eb6  test    ebx, ebx
0x180031eb8  js      short loc_180031EC8
0x180031eba  mov     r8, rsi
0x180031ebd  lea     rdx, [rbp+var_28]
0x180031ec1  call    ??$GetStorageList@UIAvailableStoragePool@ClusApi@@@ResourceType@ClusApi@@AEAAJAEBV?$shared_ptr@UIStorageItem@ClusApi@@@std@@PEAV?$list@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@@2@@3@@Z; ClusApi::ResourceType::GetStorageList<ClusApi::IAvailableStoragePool>(std::shared_ptr<ClusApi::IStorageItem> const &,std::list<std::shared_ptr<ClusApi::IAvailableStoragePool>> *)
0x180031ec6  mov     ebx, eax
0x180031ec8  mov     rcx, [rbp+var_28+8]; this
0x180031ecc  test    rcx, rcx
0x180031ecf  jz      short loc_180031ED6
0x180031ed1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031ed6  mov     eax, ebx
0x180031ed8  add     rsp, 68h
0x180031edc  pop     rdi
0x180031edd  pop     rsi
0x180031ede  pop     rbx
0x180031edf  pop     rbp
0x180031ee0  retn
```
