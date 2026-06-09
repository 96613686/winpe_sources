# ClusApi::Resource::GetStoragePool(std::shared_ptr<ClusApi::IStoragePool> *)

- ea: `0x180031520`
- end: `0x18003176b`
- name: `?GetStoragePool@Resource@ClusApi@@UEAAJPEAV?$shared_ptr@UIStoragePool@ClusApi@@@std@@@Z`
- size: `587`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180002ae0`
- `0x180002f00`
- `0x18000b8e4`
- `0x18000ca34`
- `0x18000d618`
- `0x18000d6dc`
- `0x180020710`
- `0x18002085c`
- `0x180031520`
- `0x180033910`
- `0x18004af90`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800315a2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800315a2`

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
0x180031520  mov     [rsp-8+arg_10], rbx
0x180031525  mov     [rsp-8+arg_18], rsi
0x18003152a  push    rbp
0x18003152b  push    rdi
0x18003152c  push    r15
0x18003152e  lea     rbp, [rsp-47h]
0x180031533  sub     rsp, 0A0h
0x18003153a  mov     rax, cs:__security_cookie
0x180031541  xor     rax, rsp
0x180031544  mov     [rbp+57h+var_20], rax
0x180031548  mov     rsi, rdx
0x18003154b  mov     rdi, rcx
0x18003154e  lea     rcx, [rbp+57h+var_40]
0x180031552  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180031557  nop
0x180031558  mov     rax, [rdi]
0x18003155b  lea     rdx, [rbp+57h+var_40]
0x18003155f  mov     rcx, rdi
0x180031562  mov     rax, [rax+70h]
0x180031566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003156b  mov     ebx, eax
0x18003156d  test    eax, eax
0x18003156f  js      loc_18003173C
0x180031575  lea     rcx, [rbp+57h+var_40]
0x180031579  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003157e  mov     r8, rax; lpString1
0x180031581  or      r9d, 0FFFFFFFFh; cchCount1
0x180031585  mov     [rsp+0B0h+cchCount2], r9d; cchCount2
0x18003158a  lea     rax, String2; "Storage Pool"
0x180031591  mov     [rsp+0B0h+lpString2], rax; lpString2
0x180031596  lea     r15d, [r9+2]
0x18003159a  mov     edx, r15d; dwCmpFlags
0x18003159d  mov     ecx, 400h; Locale
0x1800315a2  call    cs:__imp_CompareStringW
0x1800315a8  cmp     eax, 2
0x1800315ab  jnz     loc_180031737
0x1800315b1  xorps   xmm0, xmm0
0x1800315b4  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x1800315b9  lea     rcx, [rdi+28h]
0x1800315bd  lea     rdx, [rbp+57h+var_50]
0x1800315c1  call    ?shared_from_this@?$enable_shared_from_this@VNode@ClusApi@@@std@@QEAA?AV?$shared_ptr@VNode@ClusApi@@@2@XZ; std::enable_shared_from_this<ClusApi::Node>::shared_from_this(void)
0x1800315c6  nop
0x1800315c7  mov     rcx, [rax]
0x1800315ca  test    rcx, rcx
0x1800315cd  jz      short loc_1800315D3
0x1800315cf  add     rcx, 8
0x1800315d3  mov     [rbp+57h+var_70], rcx
0x1800315d7  mov     rdx, [rax+8]
0x1800315db  mov     [rbp+57h+var_70+8], rdx
0x1800315df  mov     qword ptr [rax], 0
0x1800315e6  mov     qword ptr [rax+8], 0
0x1800315ee  test    rcx, rcx
0x1800315f1  jz      short loc_18003163D
0x1800315f3  mov     ecx, 0B0h; Size
0x1800315f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800315fd  mov     rbx, rax
0x180031600  mov     [rbp+57h+var_80], rax
0x180031604  xorps   xmm0, xmm0
0x180031607  movups  xmmword ptr [rax], xmm0
0x18003160a  mov     [rax+8], r15d
0x18003160e  mov     [rax+0Ch], r15d
0x180031612  lea     rax, ??_7?$_Ref_count_obj2@VResourceStoragePoolItem@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::ResourceStoragePoolItem>::`vftable'
0x180031619  mov     [rbx], rax
0x18003161c  lea     rdi, [rbx+10h]
0x180031620  lea     rdx, [rbp+57h+var_70]
0x180031624  mov     rcx, rdi
0x180031627  call    ??$_Construct_in_place@VResourceStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResource@ClusApi@@@std@@@std@@YAXAEAVResourceStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResource@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::ResourceStoragePoolItem,std::shared_ptr<ClusApi::IResource> const &>(ClusApi::ResourceStoragePoolItem &,std::shared_ptr<ClusApi::IResource> const &)
0x18003162c  nop
0x18003162d  mov     [rbp+57h+var_60], rdi
0x180031631  mov     [rbp+57h+var_60+8], rbx
0x180031635  xor     ebx, ebx
0x180031637  mov     rdx, [rbp+57h+var_70+8]
0x18003163b  jmp     short loc_180031646
0x18003163d  mov     ebx, 80070057h
0x180031642  mov     rdi, [rbp+57h+var_60]
0x180031646  test    rdx, rdx
0x180031649  jz      short loc_180031654
0x18003164b  mov     rcx, rdx; this
0x18003164e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031653  nop
0x180031654  mov     rcx, [rbp+57h+var_48]; this
0x180031658  test    rcx, rcx
0x18003165b  jz      short loc_180031662
0x18003165d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031662  test    ebx, ebx
0x180031664  js      loc_180031727
0x18003166a  xorps   xmm0, xmm0
0x18003166d  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180031672  test    rdi, rdi
0x180031675  jz      loc_180031710
0x18003167b  mov     ecx, 20h ; ' '; Size
0x180031680  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031685  mov     rdi, rax
0x180031688  mov     [rbp+57h+var_80], rax
0x18003168c  xorps   xmm0, xmm0
0x18003168f  movups  xmmword ptr [rax], xmm0
0x180031692  mov     [rax+8], r15d
0x180031696  mov     [rax+0Ch], r15d
0x18003169a  lea     rax, ??_7?$_Ref_count_obj2@VStorageParser@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::StorageParser>::`vftable'
0x1800316a1  mov     [rdi], rax
0x1800316a4  lea     rcx, [rdi+10h]
0x1800316a8  lea     rdx, [rbp+57h+var_60]
0x1800316ac  call    ??$_Construct_in_place@VSharedVolumeParser@ClusApi@@AEBV?$shared_ptr@UISharedVolumeStorageItem@ClusApi@@@std@@@std@@YAXAEAVSharedVolumeParser@ClusApi@@AEBV?$shared_ptr@UISharedVolumeStorageItem@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::SharedVolumeParser,std::shared_ptr<ClusApi::ISharedVolumeStorageItem> const &>(ClusApi::SharedVolumeParser &,std::shared_ptr<ClusApi::ISharedVolumeStorageItem> const &)
0x1800316b1  mov     [rbp+57h+var_70], rcx
0x1800316b5  mov     [rbp+57h+var_70+8], rdi
0x1800316b9  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x1800316be  lea     rdx, [rbp+57h+var_80]
0x1800316c2  call    ?Parse@StorageParser@ClusApi@@QEAAJPEAV?$shared_ptr@UIStorage@ClusApi@@@std@@@Z; ClusApi::StorageParser::Parse(std::shared_ptr<ClusApi::IStorage> *)
0x1800316c7  mov     ebx, eax
0x1800316c9  test    eax, eax
0x1800316cb  js      short loc_180031700
0x1800316cd  mov     rax, [rbp+57h+var_80]
0x1800316d1  test    rax, rax
0x1800316d4  jz      short loc_180031700
0x1800316d6  mov     rcx, [rbp+57h+var_80+8]
0x1800316da  test    rcx, rcx
0x1800316dd  jz      short loc_1800316E8
0x1800316df  lock add [rcx+8], r15d
0x1800316e4  mov     rcx, [rbp+57h+var_80+8]
0x1800316e8  mov     [rsi], rax
0x1800316eb  mov     rax, [rsi+8]
0x1800316ef  mov     [rsi+8], rcx
0x1800316f3  test    rax, rax
0x1800316f6  jz      short loc_180031704
0x1800316f8  mov     rcx, rax; this
0x1800316fb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031700  mov     rcx, [rbp+57h+var_80+8]; this
0x180031704  test    rcx, rcx
0x180031707  jz      short loc_180031719
0x180031709  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003170e  jmp     short loc_180031719
0x180031710  mov     ebx, 80070057h
0x180031715  mov     rdi, [rbp+57h+var_70+8]
0x180031719  test    rdi, rdi
0x18003171c  jz      short loc_180031727
0x18003171e  mov     rcx, rdi; this
0x180031721  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031726  nop
0x180031727  mov     rcx, [rbp+57h+var_60+8]; this
0x18003172b  test    rcx, rcx
0x18003172e  jz      short loc_18003173C
0x180031730  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031735  jmp     short loc_18003173C
0x180031737  mov     ebx, 80070032h
0x18003173c  lea     rcx, [rbp+57h+var_40]
0x180031740  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031745  mov     eax, ebx
0x180031747  mov     rcx, [rbp+57h+var_20]
0x18003174b  xor     rcx, rsp; StackCookie
0x18003174e  call    __security_check_cookie
0x180031753  lea     r11, [rsp+0B0h+var_10]
0x18003175b  mov     rbx, [r11+30h]
0x18003175f  mov     rsi, [r11+38h]
0x180031763  mov     rsp, r11
0x180031766  pop     r15
0x180031768  pop     rdi
0x180031769  pop     rbp
0x18003176a  retn
```
