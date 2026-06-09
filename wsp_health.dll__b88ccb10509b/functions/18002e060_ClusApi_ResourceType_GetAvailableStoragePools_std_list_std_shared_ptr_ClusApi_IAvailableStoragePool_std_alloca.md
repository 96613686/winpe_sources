# ClusApi::ResourceType::GetAvailableStoragePools(std::list<std::shared_ptr<ClusApi::IAvailableStoragePool>,std::allocator<std::shared_ptr<ClusApi::IAvailableStoragePool>>> *)

- ea: `0x18002e060`
- end: `0x18002e191`
- name: `?GetAvailableStoragePools@ResourceType@ClusApi@@UEAAJPEAV?$list@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@@2@@std@@@Z`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002f00`
- `0x18000b8e4`
- `0x18000d618`
- `0x180020114`
- `0x18002ad94`
- `0x18002e060`
- `0x180033910`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e0a4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e0a4`

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
0x18002e060  push    rbp
0x18002e062  push    rbx
0x18002e063  push    rsi
0x18002e064  push    rdi
0x18002e065  mov     rbp, rsp
0x18002e068  sub     rsp, 68h
0x18002e06c  mov     rsi, rdx
0x18002e06f  mov     rbx, rcx
0x18002e072  xorps   xmm0, xmm0
0x18002e075  movdqu  xmmword ptr [rbp+var_28], xmm0
0x18002e07a  add     rcx, 38h ; '8'
0x18002e07e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002e083  or      r9d, 0FFFFFFFFh; cchCount1
0x18002e087  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x18002e08c  lea     rcx, String2; "Storage Pool"
0x18002e093  mov     [rsp+68h+lpString2], rcx; lpString2
0x18002e098  mov     r8, rax; lpString1
0x18002e09b  lea     edx, [r9+2]; dwCmpFlags
0x18002e09f  mov     ecx, 400h; Locale
0x18002e0a4  call    cs:__imp_CompareStringW
0x18002e0aa  cmp     eax, 2
0x18002e0ad  jz      short loc_18002E0B9
0x18002e0af  mov     ebx, 800710DDh
0x18002e0b4  jmp     loc_18002E178
0x18002e0b9  lea     rcx, [rbx+18h]
0x18002e0bd  lea     rdx, [rbp+var_18]
0x18002e0c1  call    ?shared_from_this@?$enable_shared_from_this@VNode@ClusApi@@@std@@QEAA?AV?$shared_ptr@VNode@ClusApi@@@2@XZ; std::enable_shared_from_this<ClusApi::Node>::shared_from_this(void)
0x18002e0c6  mov     rdx, rax
0x18002e0c9  mov     rcx, [rax]
0x18002e0cc  test    rcx, rcx
0x18002e0cf  jz      short loc_18002E0D5
0x18002e0d1  add     rcx, 8
0x18002e0d5  mov     [rbp+var_38], rcx
0x18002e0d9  mov     rax, [rax+8]
0x18002e0dd  mov     [rbp+var_30], rax
0x18002e0e1  mov     qword ptr [rdx], 0
0x18002e0e8  mov     qword ptr [rdx+8], 0
0x18002e0f0  test    rcx, rcx
0x18002e0f3  jz      short loc_18002E145
0x18002e0f5  mov     ecx, 0D0h; Size
0x18002e0fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e0ff  mov     rdi, rax
0x18002e102  mov     [rbp+arg_0], rax
0x18002e106  xorps   xmm0, xmm0
0x18002e109  movups  xmmword ptr [rax], xmm0
0x18002e10c  mov     dword ptr [rax+8], 1
0x18002e113  mov     dword ptr [rax+0Ch], 1
0x18002e11a  lea     rax, ??_7?$_Ref_count_obj2@VAvailableStoragePoolItem@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::AvailableStoragePoolItem>::`vftable'
0x18002e121  mov     [rdi], rax
0x18002e124  lea     rbx, [rdi+10h]
0x18002e128  lea     rdx, [rbp+var_38]
0x18002e12c  mov     rcx, rbx
0x18002e12f  call    ??$_Construct_in_place@VAvailableStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResourceType@ClusApi@@@std@@@std@@YAXAEAVAvailableStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResourceType@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::AvailableStoragePoolItem,std::shared_ptr<ClusApi::IResourceType> const &>(ClusApi::AvailableStoragePoolItem &,std::shared_ptr<ClusApi::IResourceType> const &)
0x18002e134  nop
0x18002e135  mov     [rbp+var_28], rbx
0x18002e139  mov     [rbp+var_28+8], rdi
0x18002e13d  xor     ebx, ebx
0x18002e13f  mov     rax, [rbp+var_30]
0x18002e143  jmp     short loc_18002E14A
0x18002e145  mov     ebx, 80070057h
0x18002e14a  test    rax, rax
0x18002e14d  jz      short loc_18002E158
0x18002e14f  mov     rcx, rax; this
0x18002e152  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002e157  nop
0x18002e158  mov     rcx, [rbp+var_10]; this
0x18002e15c  test    rcx, rcx
0x18002e15f  jz      short loc_18002E166
0x18002e161  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002e166  test    ebx, ebx
0x18002e168  js      short loc_18002E178
0x18002e16a  mov     r8, rsi
0x18002e16d  lea     rdx, [rbp+var_28]
0x18002e171  call    ??$GetStorageList@UIAvailableStoragePool@ClusApi@@@ResourceType@ClusApi@@AEAAJAEBV?$shared_ptr@UIStorageItem@ClusApi@@@std@@PEAV?$list@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@@2@@3@@Z; ClusApi::ResourceType::GetStorageList<ClusApi::IAvailableStoragePool>(std::shared_ptr<ClusApi::IStorageItem> const &,std::list<std::shared_ptr<ClusApi::IAvailableStoragePool>> *)
0x18002e176  mov     ebx, eax
0x18002e178  mov     rcx, [rbp+var_28+8]; this
0x18002e17c  test    rcx, rcx
0x18002e17f  jz      short loc_18002E186
0x18002e181  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002e186  mov     eax, ebx
0x18002e188  add     rsp, 68h
0x18002e18c  pop     rdi
0x18002e18d  pop     rsi
0x18002e18e  pop     rbx
0x18002e18f  pop     rbp
0x18002e190  retn
```
