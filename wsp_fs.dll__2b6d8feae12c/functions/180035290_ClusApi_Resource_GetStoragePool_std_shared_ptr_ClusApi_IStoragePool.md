# ClusApi::Resource::GetStoragePool(std::shared_ptr<ClusApi::IStoragePool> *)

- ea: `0x180035290`
- end: `0x1800354db`
- name: `?GetStoragePool@Resource@ClusApi@@UEAAJPEAV?$shared_ptr@UIStoragePool@ClusApi@@@std@@@Z`
- size: `587`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180002a70`
- `0x180002a94`
- `0x18000a6dc`
- `0x18000c284`
- `0x18000d298`
- `0x18000dd74`
- `0x180024420`
- `0x18002456c`
- `0x180035290`
- `0x180037604`
- `0x180087880`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180035312`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180035312`

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
0x180035290  mov     [rsp-8+arg_10], rbx
0x180035295  mov     [rsp-8+arg_18], rsi
0x18003529a  push    rbp
0x18003529b  push    rdi
0x18003529c  push    r15
0x18003529e  lea     rbp, [rsp-47h]
0x1800352a3  sub     rsp, 0A0h
0x1800352aa  mov     rax, cs:__security_cookie
0x1800352b1  xor     rax, rsp
0x1800352b4  mov     [rbp+57h+var_20], rax
0x1800352b8  mov     rsi, rdx
0x1800352bb  mov     rdi, rcx
0x1800352be  lea     rcx, [rbp+57h+var_40]
0x1800352c2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800352c7  nop
0x1800352c8  mov     rax, [rdi]
0x1800352cb  lea     rdx, [rbp+57h+var_40]
0x1800352cf  mov     rcx, rdi
0x1800352d2  mov     rax, [rax+70h]
0x1800352d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800352db  mov     ebx, eax
0x1800352dd  test    eax, eax
0x1800352df  js      loc_1800354AC
0x1800352e5  lea     rcx, [rbp+57h+var_40]
0x1800352e9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800352ee  mov     r8, rax; lpString1
0x1800352f1  or      r9d, 0FFFFFFFFh; cchCount1
0x1800352f5  mov     [rsp+0B0h+cchCount2], r9d; cchCount2
0x1800352fa  lea     rax, String2; "Storage Pool"
0x180035301  mov     [rsp+0B0h+lpString2], rax; lpString2
0x180035306  lea     r15d, [r9+2]
0x18003530a  mov     edx, r15d; dwCmpFlags
0x18003530d  mov     ecx, 400h; Locale
0x180035312  call    cs:__imp_CompareStringW
0x180035318  cmp     eax, 2
0x18003531b  jnz     loc_1800354A7
0x180035321  xorps   xmm0, xmm0
0x180035324  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x180035329  lea     rcx, [rdi+28h]
0x18003532d  lea     rdx, [rbp+57h+var_50]
0x180035331  call    ?shared_from_this@?$enable_shared_from_this@VNode@ClusApi@@@std@@QEAA?AV?$shared_ptr@VNode@ClusApi@@@2@XZ; std::enable_shared_from_this<ClusApi::Node>::shared_from_this(void)
0x180035336  nop
0x180035337  mov     rcx, [rax]
0x18003533a  test    rcx, rcx
0x18003533d  jz      short loc_180035343
0x18003533f  add     rcx, 8
0x180035343  mov     [rbp+57h+var_70], rcx
0x180035347  mov     rdx, [rax+8]
0x18003534b  mov     [rbp+57h+var_70+8], rdx
0x18003534f  mov     qword ptr [rax], 0
0x180035356  mov     qword ptr [rax+8], 0
0x18003535e  test    rcx, rcx
0x180035361  jz      short loc_1800353AD
0x180035363  mov     ecx, 0B0h; Size
0x180035368  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003536d  mov     rbx, rax
0x180035370  mov     [rbp+57h+var_80], rax
0x180035374  xorps   xmm0, xmm0
0x180035377  movups  xmmword ptr [rax], xmm0
0x18003537a  mov     [rax+8], r15d
0x18003537e  mov     [rax+0Ch], r15d
0x180035382  lea     rax, ??_7?$_Ref_count_obj2@VResourceStoragePoolItem@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::ResourceStoragePoolItem>::`vftable'
0x180035389  mov     [rbx], rax
0x18003538c  lea     rdi, [rbx+10h]
0x180035390  lea     rdx, [rbp+57h+var_70]
0x180035394  mov     rcx, rdi
0x180035397  call    ??$_Construct_in_place@VResourceStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResource@ClusApi@@@std@@@std@@YAXAEAVResourceStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResource@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::ResourceStoragePoolItem,std::shared_ptr<ClusApi::IResource> const &>(ClusApi::ResourceStoragePoolItem &,std::shared_ptr<ClusApi::IResource> const &)
0x18003539c  nop
0x18003539d  mov     [rbp+57h+var_60], rdi
0x1800353a1  mov     [rbp+57h+var_60+8], rbx
0x1800353a5  xor     ebx, ebx
0x1800353a7  mov     rdx, [rbp+57h+var_70+8]
0x1800353ab  jmp     short loc_1800353B6
0x1800353ad  mov     ebx, 80070057h
0x1800353b2  mov     rdi, [rbp+57h+var_60]
0x1800353b6  test    rdx, rdx
0x1800353b9  jz      short loc_1800353C4
0x1800353bb  mov     rcx, rdx; this
0x1800353be  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800353c3  nop
0x1800353c4  mov     rcx, [rbp+57h+var_48]; this
0x1800353c8  test    rcx, rcx
0x1800353cb  jz      short loc_1800353D2
0x1800353cd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800353d2  test    ebx, ebx
0x1800353d4  js      loc_180035497
0x1800353da  xorps   xmm0, xmm0
0x1800353dd  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x1800353e2  test    rdi, rdi
0x1800353e5  jz      loc_180035480
0x1800353eb  mov     ecx, 20h ; ' '; Size
0x1800353f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800353f5  mov     rdi, rax
0x1800353f8  mov     [rbp+57h+var_80], rax
0x1800353fc  xorps   xmm0, xmm0
0x1800353ff  movups  xmmword ptr [rax], xmm0
0x180035402  mov     [rax+8], r15d
0x180035406  mov     [rax+0Ch], r15d
0x18003540a  lea     rax, ??_7?$_Ref_count_obj2@VStorageParser@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::StorageParser>::`vftable'
0x180035411  mov     [rdi], rax
0x180035414  lea     rcx, [rdi+10h]
0x180035418  lea     rdx, [rbp+57h+var_60]
0x18003541c  call    ??$_Construct_in_place@VSharedVolumeParser@ClusApi@@AEBV?$shared_ptr@UISharedVolumeStorageItem@ClusApi@@@std@@@std@@YAXAEAVSharedVolumeParser@ClusApi@@AEBV?$shared_ptr@UISharedVolumeStorageItem@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::SharedVolumeParser,std::shared_ptr<ClusApi::ISharedVolumeStorageItem> const &>(ClusApi::SharedVolumeParser &,std::shared_ptr<ClusApi::ISharedVolumeStorageItem> const &)
0x180035421  mov     [rbp+57h+var_70], rcx
0x180035425  mov     [rbp+57h+var_70+8], rdi
0x180035429  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x18003542e  lea     rdx, [rbp+57h+var_80]
0x180035432  call    ?Parse@StorageParser@ClusApi@@QEAAJPEAV?$shared_ptr@UIStorage@ClusApi@@@std@@@Z; ClusApi::StorageParser::Parse(std::shared_ptr<ClusApi::IStorage> *)
0x180035437  mov     ebx, eax
0x180035439  test    eax, eax
0x18003543b  js      short loc_180035470
0x18003543d  mov     rax, [rbp+57h+var_80]
0x180035441  test    rax, rax
0x180035444  jz      short loc_180035470
0x180035446  mov     rcx, [rbp+57h+var_80+8]
0x18003544a  test    rcx, rcx
0x18003544d  jz      short loc_180035458
0x18003544f  lock add [rcx+8], r15d
0x180035454  mov     rcx, [rbp+57h+var_80+8]
0x180035458  mov     [rsi], rax
0x18003545b  mov     rax, [rsi+8]
0x18003545f  mov     [rsi+8], rcx
0x180035463  test    rax, rax
0x180035466  jz      short loc_180035474
0x180035468  mov     rcx, rax; this
0x18003546b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035470  mov     rcx, [rbp+57h+var_80+8]; this
0x180035474  test    rcx, rcx
0x180035477  jz      short loc_180035489
0x180035479  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003547e  jmp     short loc_180035489
0x180035480  mov     ebx, 80070057h
0x180035485  mov     rdi, [rbp+57h+var_70+8]
0x180035489  test    rdi, rdi
0x18003548c  jz      short loc_180035497
0x18003548e  mov     rcx, rdi; this
0x180035491  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035496  nop
0x180035497  mov     rcx, [rbp+57h+var_60+8]; this
0x18003549b  test    rcx, rcx
0x18003549e  jz      short loc_1800354AC
0x1800354a0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800354a5  jmp     short loc_1800354AC
0x1800354a7  mov     ebx, 80070032h
0x1800354ac  lea     rcx, [rbp+57h+var_40]
0x1800354b0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800354b5  mov     eax, ebx
0x1800354b7  mov     rcx, [rbp+57h+var_20]
0x1800354bb  xor     rcx, rsp; StackCookie
0x1800354be  call    __security_check_cookie
0x1800354c3  lea     r11, [rsp+0B0h+var_10]
0x1800354cb  mov     rbx, [r11+30h]
0x1800354cf  mov     rsi, [r11+38h]
0x1800354d3  mov     rsp, r11
0x1800354d6  pop     r15
0x1800354d8  pop     rdi
0x1800354d9  pop     rbp
0x1800354da  retn
```
