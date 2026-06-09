# ClusApi::Resource::GetStoragePool(std::shared_ptr<ClusApi::IStoragePool> *)

- ea: `0x1800325b0`
- end: `0x180032802`
- name: `?GetStoragePool@Resource@ClusApi@@UEAAJPEAV?$shared_ptr@UIStoragePool@ClusApi@@@std@@@Z`
- size: `594`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180002b50`
- `0x180002f70`
- `0x18000bc64`
- `0x18000cde0`
- `0x18000da34`
- `0x18000daf8`
- `0x180021300`
- `0x180021450`
- `0x1800325b0`
- `0x180034a10`
- `0x18004c8f8`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180032632`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180032632`

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
0x1800325b0  mov     [rsp-8+arg_10], rbx
0x1800325b5  mov     [rsp-8+arg_18], rsi
0x1800325ba  push    rbp
0x1800325bb  push    rdi
0x1800325bc  push    r15
0x1800325be  lea     rbp, [rsp-47h]
0x1800325c3  sub     rsp, 0A0h
0x1800325ca  mov     rax, cs:__security_cookie
0x1800325d1  xor     rax, rsp
0x1800325d4  mov     [rbp+57h+var_20], rax
0x1800325d8  mov     rsi, rdx
0x1800325db  mov     rdi, rcx
0x1800325de  lea     rcx, [rbp+57h+var_40]
0x1800325e2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800325e7  nop
0x1800325e8  mov     rax, [rdi]
0x1800325eb  lea     rdx, [rbp+57h+var_40]
0x1800325ef  mov     rcx, rdi
0x1800325f2  mov     rax, [rax+70h]
0x1800325f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325fb  mov     ebx, eax
0x1800325fd  test    eax, eax
0x1800325ff  js      loc_1800327D2
0x180032605  lea     rcx, [rbp+57h+var_40]
0x180032609  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003260e  mov     r8, rax; lpString1
0x180032611  or      r9d, 0FFFFFFFFh; cchCount1
0x180032615  mov     [rsp+0B0h+cchCount2], r9d; cchCount2
0x18003261a  lea     rax, String2; "Storage Pool"
0x180032621  mov     [rsp+0B0h+lpString2], rax; lpString2
0x180032626  lea     r15d, [r9+2]
0x18003262a  mov     edx, r15d; dwCmpFlags
0x18003262d  mov     ecx, 400h; Locale
0x180032632  call    cs:__imp_CompareStringW
0x180032639  nop     dword ptr [rax+rax+00h]
0x18003263e  cmp     eax, 2
0x180032641  jnz     loc_1800327CD
0x180032647  xorps   xmm0, xmm0
0x18003264a  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18003264f  lea     rcx, [rdi+28h]
0x180032653  lea     rdx, [rbp+57h+var_50]
0x180032657  call    ?shared_from_this@?$enable_shared_from_this@VNode@ClusApi@@@std@@QEAA?AV?$shared_ptr@VNode@ClusApi@@@2@XZ; std::enable_shared_from_this<ClusApi::Node>::shared_from_this(void)
0x18003265c  nop
0x18003265d  mov     rcx, [rax]
0x180032660  test    rcx, rcx
0x180032663  jz      short loc_180032669
0x180032665  add     rcx, 8
0x180032669  mov     [rbp+57h+var_70], rcx
0x18003266d  mov     rdx, [rax+8]
0x180032671  mov     [rbp+57h+var_70+8], rdx
0x180032675  mov     qword ptr [rax], 0
0x18003267c  mov     qword ptr [rax+8], 0
0x180032684  test    rcx, rcx
0x180032687  jz      short loc_1800326D3
0x180032689  mov     ecx, 0B0h; Size
0x18003268e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032693  mov     rbx, rax
0x180032696  mov     [rbp+57h+var_80], rax
0x18003269a  xorps   xmm0, xmm0
0x18003269d  movups  xmmword ptr [rax], xmm0
0x1800326a0  mov     [rax+8], r15d
0x1800326a4  mov     [rax+0Ch], r15d
0x1800326a8  lea     rax, ??_7?$_Ref_count_obj2@VResourceStoragePoolItem@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::ResourceStoragePoolItem>::`vftable'
0x1800326af  mov     [rbx], rax
0x1800326b2  lea     rdi, [rbx+10h]
0x1800326b6  lea     rdx, [rbp+57h+var_70]
0x1800326ba  mov     rcx, rdi
0x1800326bd  call    ??$_Construct_in_place@VResourceStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResource@ClusApi@@@std@@@std@@YAXAEAVResourceStoragePoolItem@ClusApi@@AEBV?$shared_ptr@UIResource@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::ResourceStoragePoolItem,std::shared_ptr<ClusApi::IResource> const &>(ClusApi::ResourceStoragePoolItem &,std::shared_ptr<ClusApi::IResource> const &)
0x1800326c2  nop
0x1800326c3  mov     [rbp+57h+var_60], rdi
0x1800326c7  mov     [rbp+57h+var_60+8], rbx
0x1800326cb  xor     ebx, ebx
0x1800326cd  mov     rdx, [rbp+57h+var_70+8]
0x1800326d1  jmp     short loc_1800326DC
0x1800326d3  mov     ebx, 80070057h
0x1800326d8  mov     rdi, [rbp+57h+var_60]
0x1800326dc  test    rdx, rdx
0x1800326df  jz      short loc_1800326EA
0x1800326e1  mov     rcx, rdx; this
0x1800326e4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800326e9  nop
0x1800326ea  mov     rcx, [rbp+57h+var_48]; this
0x1800326ee  test    rcx, rcx
0x1800326f1  jz      short loc_1800326F8
0x1800326f3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800326f8  test    ebx, ebx
0x1800326fa  js      loc_1800327BD
0x180032700  xorps   xmm0, xmm0
0x180032703  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180032708  test    rdi, rdi
0x18003270b  jz      loc_1800327A6
0x180032711  mov     ecx, 20h ; ' '; Size
0x180032716  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003271b  mov     rdi, rax
0x18003271e  mov     [rbp+57h+var_80], rax
0x180032722  xorps   xmm0, xmm0
0x180032725  movups  xmmword ptr [rax], xmm0
0x180032728  mov     [rax+8], r15d
0x18003272c  mov     [rax+0Ch], r15d
0x180032730  lea     rax, ??_7?$_Ref_count_obj2@VStorageParser@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::StorageParser>::`vftable'
0x180032737  mov     [rdi], rax
0x18003273a  lea     rcx, [rdi+10h]
0x18003273e  lea     rdx, [rbp+57h+var_60]
0x180032742  call    ??$_Construct_in_place@VSharedVolumeParser@ClusApi@@AEBV?$shared_ptr@UISharedVolumeStorageItem@ClusApi@@@std@@@std@@YAXAEAVSharedVolumeParser@ClusApi@@AEBV?$shared_ptr@UISharedVolumeStorageItem@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::SharedVolumeParser,std::shared_ptr<ClusApi::ISharedVolumeStorageItem> const &>(ClusApi::SharedVolumeParser &,std::shared_ptr<ClusApi::ISharedVolumeStorageItem> const &)
0x180032747  mov     [rbp+57h+var_70], rcx
0x18003274b  mov     [rbp+57h+var_70+8], rdi
0x18003274f  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x180032754  lea     rdx, [rbp+57h+var_80]
0x180032758  call    ?Parse@StorageParser@ClusApi@@QEAAJPEAV?$shared_ptr@UIStorage@ClusApi@@@std@@@Z; ClusApi::StorageParser::Parse(std::shared_ptr<ClusApi::IStorage> *)
0x18003275d  mov     ebx, eax
0x18003275f  test    eax, eax
0x180032761  js      short loc_180032796
0x180032763  mov     rax, [rbp+57h+var_80]
0x180032767  test    rax, rax
0x18003276a  jz      short loc_180032796
0x18003276c  mov     rcx, [rbp+57h+var_80+8]
0x180032770  test    rcx, rcx
0x180032773  jz      short loc_18003277E
0x180032775  lock add [rcx+8], r15d
0x18003277a  mov     rcx, [rbp+57h+var_80+8]
0x18003277e  mov     [rsi], rax
0x180032781  mov     rax, [rsi+8]
0x180032785  mov     [rsi+8], rcx
0x180032789  test    rax, rax
0x18003278c  jz      short loc_18003279A
0x18003278e  mov     rcx, rax; this
0x180032791  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032796  mov     rcx, [rbp+57h+var_80+8]; this
0x18003279a  test    rcx, rcx
0x18003279d  jz      short loc_1800327AF
0x18003279f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800327a4  jmp     short loc_1800327AF
0x1800327a6  mov     ebx, 80070057h
0x1800327ab  mov     rdi, [rbp+57h+var_70+8]
0x1800327af  test    rdi, rdi
0x1800327b2  jz      short loc_1800327BD
0x1800327b4  mov     rcx, rdi; this
0x1800327b7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800327bc  nop
0x1800327bd  mov     rcx, [rbp+57h+var_60+8]; this
0x1800327c1  test    rcx, rcx
0x1800327c4  jz      short loc_1800327D2
0x1800327c6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800327cb  jmp     short loc_1800327D2
0x1800327cd  mov     ebx, 80070032h
0x1800327d2  lea     rcx, [rbp+57h+var_40]
0x1800327d6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800327db  mov     eax, ebx
0x1800327dd  mov     rcx, [rbp+57h+var_20]
0x1800327e1  xor     rcx, rsp; StackCookie
0x1800327e4  call    __security_check_cookie
0x1800327e9  lea     r11, [rsp+0B0h+var_10]
0x1800327f1  mov     rbx, [r11+30h]
0x1800327f5  mov     rsi, [r11+38h]
0x1800327f9  mov     rsp, r11
0x1800327fc  pop     r15
0x1800327fe  pop     rdi
0x1800327ff  pop     rbp
0x180032800  retn
```
