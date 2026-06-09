# ClusApi::ResourceType::GetAvailableStoragePools(std::list<std::shared_ptr<ClusApi::IAvailableStoragePool>,std::allocator<std::shared_ptr<ClusApi::IAvailableStoragePool>>> *)

- ea: `0x180032e90`
- end: `0x180032fc8`
- name: `?GetAvailableStoragePools@ResourceType@ClusApi@@UEAAJPEAV?$list@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@@2@@std@@@Z`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002af4`
- `0x18000c5c4`
- `0x18000e14c`
- `0x180024b08`
- `0x18002f994`
- `0x180032e90`
- `0x1800388d4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180032ed4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180032ed4`

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
0x180032e90  push    rbp
0x180032e92  push    rbx
0x180032e93  push    rsi
0x180032e94  push    rdi
0x180032e95  mov     rbp, rsp
0x180032e98  sub     rsp, 68h
0x180032e9c  mov     rsi, rdx
0x180032e9f  mov     rbx, rcx
0x180032ea2  xorps   xmm0, xmm0
0x180032ea5  movdqu  xmmword ptr [rbp+var_28], xmm0
0x180032eaa  add     rcx, 38h ; '8'
0x180032eae  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180032eb3  or      r9d, 0FFFFFFFFh; cchCount1
0x180032eb7  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x180032ebc  lea     rcx, String2; "Storage Pool"
0x180032ec3  mov     [rsp+68h+lpString2], rcx; lpString2
0x180032ec8  mov     r8, rax; lpString1
0x180032ecb  lea     edx, [r9+2]; dwCmpFlags
0x180032ecf  mov     ecx, 400h; Locale
0x180032ed4  call    cs:__imp_CompareStringW
0x180032edb  nop     dword ptr [rax+rax+00h]
0x180032ee0  cmp     eax, 2
0x180032ee3  jz      short loc_180032EEF
0x180032ee5  mov     ebx, 800710DDh
0x180032eea  jmp     loc_180032FAE
0x180032eef  lea     rcx, [rbx+18h]
0x180032ef3  lea     rdx, [rbp+var_18]
0x180032ef7  call    ?shared_from_this@?$enable_shared_from_this@VNode@ClusApi@@@std@@QEAA?AV?$shared_ptr@VNode@ClusApi@@@2@XZ; std::enable_shared_from_this<ClusApi::Node>::shared_from_this(void)
0x180032efc  mov     rdx, rax
0x180032eff  mov     rcx, [rax]
0x180032f02  test    rcx, rcx
0x180032f05  jz      short loc_180032F0B
0x180032f07  add     rcx, 8
0x180032f0b  mov     [rbp+var_38], rcx
0x180032f0f  mov     rax, [rax+8]
0x180032f13  mov     [rbp+var_30], rax
0x180032f17  mov     qword ptr [rdx], 0
0x180032f1e  mov     qword ptr [rdx+8], 0
0x180032f26  test    rcx, rcx
0x180032f29  jz      short loc_180032F7B
0x180032f2b  mov     ecx, 0D0h; Size
0x180032f30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032f35  mov     rdi, rax
0x180032f38  mov     [rbp+arg_0], rax
0x180032f3c  xorps   xmm0, xmm0
0x180032f3f  movups  xmmword ptr [rax], xmm0
0x180032f42  mov     dword ptr [rax+8], 1
0x180032f49  mov     dword ptr [rax+0Ch], 1
0x180032f50  lea     rax, ??_7?$_Ref_count_obj2@VAvailableStoragePoolItem@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::AvailableStoragePoolItem>::`vftable'
0x180032f57  mov     [rdi], rax
0x180032f5a  lea     rbx, [rdi+10h]
0x180032f5e  lea     rdx, [rbp+var_38]
0x180032f62  mov     rcx, rbx
0x180032f65  call    ??$_Construct_in_place@VAvailableStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResourceType@ClusApi@@@std@@@std@@YAXAEAVAvailableStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResourceType@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::AvailableStoragePoolItem,std::shared_ptr<ClusApi::IResourceType> const &>(ClusApi::AvailableStoragePoolItem &,std::shared_ptr<ClusApi::IResourceType> const &)
0x180032f6a  nop
0x180032f6b  mov     [rbp+var_28], rbx
0x180032f6f  mov     [rbp+var_28+8], rdi
0x180032f73  xor     ebx, ebx
0x180032f75  mov     rax, [rbp+var_30]
0x180032f79  jmp     short loc_180032F80
0x180032f7b  mov     ebx, 80070057h
0x180032f80  test    rax, rax
0x180032f83  jz      short loc_180032F8E
0x180032f85  mov     rcx, rax; this
0x180032f88  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032f8d  nop
0x180032f8e  mov     rcx, [rbp+var_10]; this
0x180032f92  test    rcx, rcx
0x180032f95  jz      short loc_180032F9C
0x180032f97  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032f9c  test    ebx, ebx
0x180032f9e  js      short loc_180032FAE
0x180032fa0  mov     r8, rsi
0x180032fa3  lea     rdx, [rbp+var_28]
0x180032fa7  call    ??$GetStorageList@UIAvailableStoragePool@ClusApi@@@ResourceType@ClusApi@@AEAAJAEBV?$shared_ptr@UIStorageItem@ClusApi@@@std@@PEAV?$list@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@@2@@3@@Z; ClusApi::ResourceType::GetStorageList<ClusApi::IAvailableStoragePool>(std::shared_ptr<ClusApi::IStorageItem> const &,std::list<std::shared_ptr<ClusApi::IAvailableStoragePool>> *)
0x180032fac  mov     ebx, eax
0x180032fae  mov     rcx, [rbp+var_28+8]; this
0x180032fb2  test    rcx, rcx
0x180032fb5  jz      short loc_180032FBC
0x180032fb7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032fbc  mov     eax, ebx
0x180032fbe  add     rsp, 68h
0x180032fc2  pop     rdi
0x180032fc3  pop     rsi
0x180032fc4  pop     rbx
0x180032fc5  pop     rbp
0x180032fc6  retn
```
