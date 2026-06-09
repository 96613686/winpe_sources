# ClusApi::Resource::GetStoragePool(std::shared_ptr<ClusApi::IStoragePool> *)

- ea: `0x180036430`
- end: `0x180036682`
- name: `?GetStoragePool@Resource@ClusApi@@UEAAJPEAV?$shared_ptr@UIStoragePool@ClusApi@@@std@@@Z`
- size: `594`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x180002af4`
- `0x18000aa10`
- `0x18000c5c4`
- `0x18000d600`
- `0x18000e14c`
- `0x180025110`
- `0x180025260`
- `0x180036430`
- `0x1800388d4`
- `0x180089a08`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800364b2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800364b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ClusApi::Resource::GetStoragePool(__int64 a1, std::_Ref_count_base **a2)
{
  int v4; // ebx
  const WCHAR *v5; // rax
  __int64 v6; // rax
  std::_Ref_count_base *v7; // rcx
  std::_Ref_count_base *v8; // rdx
  _DWORD *v9; // rbx
  std::_Ref_count_base *v10; // rdi
  std::_Ref_count_base *v11; // rdi
  __int128 v12; // xmm0
  std::_Ref_count_base *v13; // rcx
  std::_Ref_count_base *v14; // rax
  std::_Ref_count_base *v15; // rcx
  std::_Ref_count_base *v16; // rax
  std::_Ref_count_base *v18[2]; // [rsp+30h] [rbp-29h] BYREF
  std::_Ref_count_base *v19[2]; // [rsp+40h] [rbp-19h] BYREF
  std::_Ref_count_base *v20[2]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v21[8]; // [rsp+60h] [rbp+7h] BYREF
  std::_Ref_count_base *v22; // [rsp+68h] [rbp+Fh]
  _BYTE v23[32]; // [rsp+70h] [rbp+17h] BYREF

  std::wstring::wstring(v23);
  v4 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a1 + 112LL))(a1, v23);
  if ( v4 < 0 )
    goto LABEL_29;
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v23);
  if ( CompareStringW(0x400u, 1u, v5, -1, L"Storage Pool", -1) != 2 )
  {
    v4 = -2147024846;
    goto LABEL_29;
  }
  *(_OWORD *)v20 = 0;
  v6 = std::enable_shared_from_this<ClusApi::Node>::shared_from_this(a1 + 40, v21);
  v7 = *(std::_Ref_count_base **)v6;
  if ( *(_QWORD *)v6 )
    v7 = (std::_Ref_count_base *)((char *)v7 + 8);
  v19[0] = v7;
  v8 = *(std::_Ref_count_base **)(v6 + 8);
  v19[1] = v8;
  *(_QWORD *)v6 = 0;
  *(_QWORD *)(v6 + 8) = 0;
  if ( v7 )
  {
    v9 = operator new(0xB0u);
    v18[0] = (std::_Ref_count_base *)v9;
    *(_OWORD *)v9 = 0;
    v9[2] = 1;
    v9[3] = 1;
    *(_QWORD *)v9 = &std::_Ref_count_obj2<ClusApi::ResourceStoragePoolItem>::`vftable';
    v10 = (std::_Ref_count_base *)(v9 + 4);
    std::_Construct_in_place<ClusApi::ResourceStoragePoolItem,std::shared_ptr<ClusApi::IResource> const &>(v9 + 4, v19);
    v20[0] = (std::_Ref_count_base *)(v9 + 4);
    v20[1] = (std::_Ref_count_base *)v9;
    v4 = 0;
    v8 = v19[1];
  }
  else
  {
    v4 = -2147024809;
    v10 = v20[0];
  }
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  if ( v4 >= 0 )
  {
    *(_OWORD *)v19 = 0;
    if ( !v10 )
    {
      v4 = -2147024809;
      v11 = v19[1];
LABEL_24:
      if ( v11 )
        std::_Ref_count_base::_Decref(v11);
      goto LABEL_26;
    }
    v11 = (std::_Ref_count_base *)operator new(0x20u);
    v12 = 0;
    *(_OWORD *)v11 = 0;
    *((_DWORD *)v11 + 2) = 1;
    *((_DWORD *)v11 + 3) = 1;
    *(_QWORD *)v11 = &std::_Ref_count_obj2<ClusApi::StorageParser>::`vftable';
    *(double *)&v12 = std::_Construct_in_place<ClusApi::SharedVolumeParser,std::shared_ptr<ClusApi::ISharedVolumeStorageItem> const &>(
                        (char *)v11 + 16,
                        v20);
    v19[0] = v13;
    v19[1] = v11;
    *(_OWORD *)v18 = v12;
    v4 = ClusApi::StorageParser::Parse(v13, v18);
    if ( v4 >= 0 )
    {
      v14 = v18[0];
      if ( v18[0] )
      {
        v15 = v18[1];
        if ( v18[1] )
        {
          _InterlockedAdd((volatile signed __int32 *)v18[1] + 2, 1u);
          v15 = v18[1];
        }
        *a2 = v14;
        v16 = a2[1];
        a2[1] = v15;
        if ( !v16 )
          goto LABEL_21;
        std::_Ref_count_base::_Decref(v16);
      }
    }
    v15 = v18[1];
LABEL_21:
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    goto LABEL_24;
  }
LABEL_26:
  if ( v20[1] )
    std::_Ref_count_base::_Decref(v20[1]);
LABEL_29:
  std::wstring::_Tidy_deallocate(v23);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180036430  mov     [rsp-8+arg_10], rbx
0x180036435  mov     [rsp-8+arg_18], rsi
0x18003643a  push    rbp
0x18003643b  push    rdi
0x18003643c  push    r15
0x18003643e  lea     rbp, [rsp-47h]
0x180036443  sub     rsp, 0A0h
0x18003644a  mov     rax, cs:__security_cookie
0x180036451  xor     rax, rsp
0x180036454  mov     [rbp+57h+var_20], rax
0x180036458  mov     rsi, rdx
0x18003645b  mov     rdi, rcx
0x18003645e  lea     rcx, [rbp+57h+var_40]
0x180036462  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036467  nop
0x180036468  mov     rax, [rdi]
0x18003646b  lea     rdx, [rbp+57h+var_40]
0x18003646f  mov     rcx, rdi
0x180036472  mov     rax, [rax+70h]
0x180036476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003647b  mov     ebx, eax
0x18003647d  test    eax, eax
0x18003647f  js      loc_180036652
0x180036485  lea     rcx, [rbp+57h+var_40]
0x180036489  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003648e  mov     r8, rax; lpString1
0x180036491  or      r9d, 0FFFFFFFFh; cchCount1
0x180036495  mov     [rsp+0B0h+cchCount2], r9d; cchCount2
0x18003649a  lea     rax, String2; "Storage Pool"
0x1800364a1  mov     [rsp+0B0h+lpString2], rax; lpString2
0x1800364a6  lea     r15d, [r9+2]
0x1800364aa  mov     edx, r15d; dwCmpFlags
0x1800364ad  mov     ecx, 400h; Locale
0x1800364b2  call    cs:__imp_CompareStringW
0x1800364b9  nop     dword ptr [rax+rax+00h]
0x1800364be  cmp     eax, 2
0x1800364c1  jnz     loc_18003664D
0x1800364c7  xorps   xmm0, xmm0
0x1800364ca  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x1800364cf  lea     rcx, [rdi+28h]
0x1800364d3  lea     rdx, [rbp+57h+var_50]
0x1800364d7  call    ?shared_from_this@?$enable_shared_from_this@VNode@ClusApi@@@std@@QEAA?AV?$shared_ptr@VNode@ClusApi@@@2@XZ; std::enable_shared_from_this<ClusApi::Node>::shared_from_this(void)
0x1800364dc  nop
0x1800364dd  mov     rcx, [rax]
0x1800364e0  test    rcx, rcx
0x1800364e3  jz      short loc_1800364E9
0x1800364e5  add     rcx, 8
0x1800364e9  mov     [rbp+57h+var_70], rcx
0x1800364ed  mov     rdx, [rax+8]
0x1800364f1  mov     [rbp+57h+var_70+8], rdx
0x1800364f5  mov     qword ptr [rax], 0
0x1800364fc  mov     qword ptr [rax+8], 0
0x180036504  test    rcx, rcx
0x180036507  jz      short loc_180036553
0x180036509  mov     ecx, 0B0h; Size
0x18003650e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036513  mov     rbx, rax
0x180036516  mov     [rbp+57h+var_80], rax
0x18003651a  xorps   xmm0, xmm0
0x18003651d  movups  xmmword ptr [rax], xmm0
0x180036520  mov     [rax+8], r15d
0x180036524  mov     [rax+0Ch], r15d
0x180036528  lea     rax, ??_7?$_Ref_count_obj2@VResourceStoragePoolItem@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::ResourceStoragePoolItem>::`vftable'
0x18003652f  mov     [rbx], rax
0x180036532  lea     rdi, [rbx+10h]
0x180036536  lea     rdx, [rbp+57h+var_70]
0x18003653a  mov     rcx, rdi
0x18003653d  call    ??$_Construct_in_place@VResourceStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResource@ClusApi@@@std@@@std@@YAXAEAVResourceStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResource@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::ResourceStoragePoolItem,std::shared_ptr<ClusApi::IResource> const &>(ClusApi::ResourceStoragePoolItem &,std::shared_ptr<ClusApi::IResource> const &)
0x180036542  nop
0x180036543  mov     [rbp+57h+var_60], rdi
0x180036547  mov     [rbp+57h+var_60+8], rbx
0x18003654b  xor     ebx, ebx
0x18003654d  mov     rdx, [rbp+57h+var_70+8]
0x180036551  jmp     short loc_18003655C
0x180036553  mov     ebx, 80070057h
0x180036558  mov     rdi, [rbp+57h+var_60]
0x18003655c  test    rdx, rdx
0x18003655f  jz      short loc_18003656A
0x180036561  mov     rcx, rdx; this
0x180036564  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036569  nop
0x18003656a  mov     rcx, [rbp+57h+var_48]; this
0x18003656e  test    rcx, rcx
0x180036571  jz      short loc_180036578
0x180036573  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036578  test    ebx, ebx
0x18003657a  js      loc_18003663D
0x180036580  xorps   xmm0, xmm0
0x180036583  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180036588  test    rdi, rdi
0x18003658b  jz      loc_180036626
0x180036591  mov     ecx, 20h ; ' '; Size
0x180036596  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003659b  mov     rdi, rax
0x18003659e  mov     [rbp+57h+var_80], rax
0x1800365a2  xorps   xmm0, xmm0
0x1800365a5  movups  xmmword ptr [rax], xmm0
0x1800365a8  mov     [rax+8], r15d
0x1800365ac  mov     [rax+0Ch], r15d
0x1800365b0  lea     rax, ??_7?$_Ref_count_obj2@VStorageParser@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::StorageParser>::`vftable'
0x1800365b7  mov     [rdi], rax
0x1800365ba  lea     rcx, [rdi+10h]
0x1800365be  lea     rdx, [rbp+57h+var_60]
0x1800365c2  call    ??$_Construct_in_place@VSharedVolumeParser@ClusApi@@AEBV?$shared_ptr@UISharedVolumeStorageItem@ClusApi@@@std@@@std@@YAXAEAVSharedVolumeParser@ClusApi@@AEBV?$shared_ptr@UISharedVolumeStorageItem@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::SharedVolumeParser,std::shared_ptr<ClusApi::ISharedVolumeStorageItem> const &>(ClusApi::SharedVolumeParser &,std::shared_ptr<ClusApi::ISharedVolumeStorageItem> const &)
0x1800365c7  mov     [rbp+57h+var_70], rcx
0x1800365cb  mov     [rbp+57h+var_70+8], rdi
0x1800365cf  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x1800365d4  lea     rdx, [rbp+57h+var_80]
0x1800365d8  call    ?Parse@StorageParser@ClusApi@@QEAAJPEAV?$shared_ptr@UIStorage@ClusApi@@@std@@@Z; ClusApi::StorageParser::Parse(std::shared_ptr<ClusApi::IStorage> *)
0x1800365dd  mov     ebx, eax
0x1800365df  test    eax, eax
0x1800365e1  js      short loc_180036616
0x1800365e3  mov     rax, [rbp+57h+var_80]
0x1800365e7  test    rax, rax
0x1800365ea  jz      short loc_180036616
0x1800365ec  mov     rcx, [rbp+57h+var_80+8]
0x1800365f0  test    rcx, rcx
0x1800365f3  jz      short loc_1800365FE
0x1800365f5  lock add [rcx+8], r15d
0x1800365fa  mov     rcx, [rbp+57h+var_80+8]
0x1800365fe  mov     [rsi], rax
0x180036601  mov     rax, [rsi+8]
0x180036605  mov     [rsi+8], rcx
0x180036609  test    rax, rax
0x18003660c  jz      short loc_18003661A
0x18003660e  mov     rcx, rax; this
0x180036611  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036616  mov     rcx, [rbp+57h+var_80+8]; this
0x18003661a  test    rcx, rcx
0x18003661d  jz      short loc_18003662F
0x18003661f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036624  jmp     short loc_18003662F
0x180036626  mov     ebx, 80070057h
0x18003662b  mov     rdi, [rbp+57h+var_70+8]
0x18003662f  test    rdi, rdi
0x180036632  jz      short loc_18003663D
0x180036634  mov     rcx, rdi; this
0x180036637  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003663c  nop
0x18003663d  mov     rcx, [rbp+57h+var_60+8]; this
0x180036641  test    rcx, rcx
0x180036644  jz      short loc_180036652
0x180036646  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003664b  jmp     short loc_180036652
0x18003664d  mov     ebx, 80070032h
0x180036652  lea     rcx, [rbp+57h+var_40]
0x180036656  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003665b  mov     eax, ebx
0x18003665d  mov     rcx, [rbp+57h+var_20]
0x180036661  xor     rcx, rsp; StackCookie
0x180036664  call    __security_check_cookie
0x180036669  lea     r11, [rsp+0B0h+var_10]
0x180036671  mov     rbx, [r11+30h]
0x180036675  mov     rsi, [r11+38h]
0x180036679  mov     rsp, r11
0x18003667c  pop     r15
0x18003667e  pop     rdi
0x18003667f  pop     rbp
0x180036680  retn
```
