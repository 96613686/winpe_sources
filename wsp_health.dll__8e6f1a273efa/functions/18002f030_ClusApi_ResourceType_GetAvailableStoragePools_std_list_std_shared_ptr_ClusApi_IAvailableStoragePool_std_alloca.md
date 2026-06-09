# ClusApi::ResourceType::GetAvailableStoragePools(std::list<std::shared_ptr<ClusApi::IAvailableStoragePool>,std::allocator<std::shared_ptr<ClusApi::IAvailableStoragePool>>> *)

- ea: `0x18002f030`
- end: `0x18002f168`
- name: `?GetAvailableStoragePools@ResourceType@ClusApi@@UEAAJPEAV?$list@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@@2@@std@@@Z`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002f70`
- `0x18000bc64`
- `0x18000da34`
- `0x180020cf8`
- `0x18002bb54`
- `0x18002f030`
- `0x180034a10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f074`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f074`

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
0x18002f030  push    rbp
0x18002f032  push    rbx
0x18002f033  push    rsi
0x18002f034  push    rdi
0x18002f035  mov     rbp, rsp
0x18002f038  sub     rsp, 68h
0x18002f03c  mov     rsi, rdx
0x18002f03f  mov     rbx, rcx
0x18002f042  xorps   xmm0, xmm0
0x18002f045  movdqu  xmmword ptr [rbp+var_28], xmm0
0x18002f04a  add     rcx, 38h ; '8'
0x18002f04e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002f053  or      r9d, 0FFFFFFFFh; cchCount1
0x18002f057  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x18002f05c  lea     rcx, String2; "Storage Pool"
0x18002f063  mov     [rsp+68h+lpString2], rcx; lpString2
0x18002f068  mov     r8, rax; lpString1
0x18002f06b  lea     edx, [r9+2]; dwCmpFlags
0x18002f06f  mov     ecx, 400h; Locale
0x18002f074  call    cs:__imp_CompareStringW
0x18002f07b  nop     dword ptr [rax+rax+00h]
0x18002f080  cmp     eax, 2
0x18002f083  jz      short loc_18002F08F
0x18002f085  mov     ebx, 800710DDh
0x18002f08a  jmp     loc_18002F14E
0x18002f08f  lea     rcx, [rbx+18h]
0x18002f093  lea     rdx, [rbp+var_18]
0x18002f097  call    ?shared_from_this@?$enable_shared_from_this@VNode@ClusApi@@@std@@QEAA?AV?$shared_ptr@VNode@ClusApi@@@2@XZ; std::enable_shared_from_this<ClusApi::Node>::shared_from_this(void)
0x18002f09c  mov     rdx, rax
0x18002f09f  mov     rcx, [rax]
0x18002f0a2  test    rcx, rcx
0x18002f0a5  jz      short loc_18002F0AB
0x18002f0a7  add     rcx, 8
0x18002f0ab  mov     [rbp+var_38], rcx
0x18002f0af  mov     rax, [rax+8]
0x18002f0b3  mov     [rbp+var_30], rax
0x18002f0b7  mov     qword ptr [rdx], 0
0x18002f0be  mov     qword ptr [rdx+8], 0
0x18002f0c6  test    rcx, rcx
0x18002f0c9  jz      short loc_18002F11B
0x18002f0cb  mov     ecx, 0D0h; Size
0x18002f0d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f0d5  mov     rdi, rax
0x18002f0d8  mov     [rbp+arg_0], rax
0x18002f0dc  xorps   xmm0, xmm0
0x18002f0df  movups  xmmword ptr [rax], xmm0
0x18002f0e2  mov     dword ptr [rax+8], 1
0x18002f0e9  mov     dword ptr [rax+0Ch], 1
0x18002f0f0  lea     rax, ??_7?$_Ref_count_obj2@VAvailableStoragePoolItem@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::AvailableStoragePoolItem>::`vftable'
0x18002f0f7  mov     [rdi], rax
0x18002f0fa  lea     rbx, [rdi+10h]
0x18002f0fe  lea     rdx, [rbp+var_38]
0x18002f102  mov     rcx, rbx
0x18002f105  call    ??$_Construct_in_place@VAvailableStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResourceType@ClusApi@@@std@@@std@@YAXAEAVAvailableStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResourceType@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::AvailableStoragePoolItem,std::shared_ptr<ClusApi::IResourceType> const &>(ClusApi::AvailableStoragePoolItem &,std::shared_ptr<ClusApi::IResourceType> const &)
0x18002f10a  nop
0x18002f10b  mov     [rbp+var_28], rbx
0x18002f10f  mov     [rbp+var_28+8], rdi
0x18002f113  xor     ebx, ebx
0x18002f115  mov     rax, [rbp+var_30]
0x18002f119  jmp     short loc_18002F120
0x18002f11b  mov     ebx, 80070057h
0x18002f120  test    rax, rax
0x18002f123  jz      short loc_18002F12E
0x18002f125  mov     rcx, rax; this
0x18002f128  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f12d  nop
0x18002f12e  mov     rcx, [rbp+var_10]; this
0x18002f132  test    rcx, rcx
0x18002f135  jz      short loc_18002F13C
0x18002f137  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f13c  test    ebx, ebx
0x18002f13e  js      short loc_18002F14E
0x18002f140  mov     r8, rsi
0x18002f143  lea     rdx, [rbp+var_28]
0x18002f147  call    ??$GetStorageList@UIAvailableStoragePool@ClusApi@@@ResourceType@ClusApi@@AEAAJAEBV?$shared_ptr@UIStorageItem@ClusApi@@@std@@PEAV?$list@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIAvailableStoragePool@ClusApi@@@std@@@2@@3@@Z; ClusApi::ResourceType::GetStorageList<ClusApi::IAvailableStoragePool>(std::shared_ptr<ClusApi::IStorageItem> const &,std::list<std::shared_ptr<ClusApi::IAvailableStoragePool>> *)
0x18002f14c  mov     ebx, eax
0x18002f14e  mov     rcx, [rbp+var_28+8]; this
0x18002f152  test    rcx, rcx
0x18002f155  jz      short loc_18002F15C
0x18002f157  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f15c  mov     eax, ebx
0x18002f15e  add     rsp, 68h
0x18002f162  pop     rdi
0x18002f163  pop     rsi
0x18002f164  pop     rbx
0x18002f165  pop     rbp
0x18002f166  retn
```
