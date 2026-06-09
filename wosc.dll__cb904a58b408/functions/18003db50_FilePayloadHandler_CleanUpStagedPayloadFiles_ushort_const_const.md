# FilePayloadHandler::CleanUpStagedPayloadFiles(ushort const * const)

- ea: `0x18003db50`
- end: `0x18003dd38`
- name: `?CleanUpStagedPayloadFiles@FilePayloadHandler@@UEAAXQEBG@Z`
- size: `488`
- prototype: `void __fastcall(FilePayloadHandler *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180003110`
- `0x18000843c`
- `0x180010278`
- `0x180014928`
- `0x180019e68`
- `0x180019f98`
- `0x180020a00`
- `0x180025a4c`
- `0x180025e88`
- `0x18003c690`
- `0x18003db50`
- `0x18003e790`
- `0x18003f0f8`
- `0x18004004c`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003dbd1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003dbd1`

## pseudocode

```c
void __fastcall FilePayloadHandler::CleanUpStagedPayloadFiles(FilePayloadHandler *this, const unsigned __int16 *a2)
{
  const WCHAR *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rdi
  unsigned int v6; // r12d
  unsigned int v7; // esi
  unsigned int v8; // r14d
  unsigned int v9; // r15d
  bool v10; // cf
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r10
  __int64 v15; // rax
  unsigned int v16; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v17; // [rsp+44h] [rbp-65h]
  unsigned int v18; // [rsp+48h] [rbp-61h]
  unsigned int v19; // [rsp+4Ch] [rbp-5Dh]
  __int128 v20; // [rsp+50h] [rbp-59h] BYREF
  __int64 v21; // [rsp+60h] [rbp-49h]
  _BYTE v22[16]; // [rsp+70h] [rbp-39h] BYREF
  __int64 v23; // [rsp+80h] [rbp-29h]
  _BYTE v24[32]; // [rsp+90h] [rbp-19h] BYREF
  _BYTE v25[32]; // [rsp+B0h] [rbp+7h] BYREF

  std::wstring::wstring(v24, a2);
  VersionUtils::OsVersion::OsVersion(&v16, v24);
  std::wstring::_Tidy_deallocate(v24);
  std::operator+<unsigned short>(v22, (char *)this + 8, L"\\Staged\\");
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PFVC_NoDirectoryCleanup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PFVC_NoDirectoryCleanup>::GetImpl'::`2'::impl)
    || (v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22), PathFileExistsW(v3)) )
  {
    std::operator+<unsigned short>(v25, v22, L"*");
    FilePayloadHandler::GetSubDirectories(&v20, v25);
    v5 = *((_QWORD *)&v20 + 1);
    v4 = v20;
    if ( (_QWORD)v20 != *((_QWORD *)&v20 + 1) )
    {
      v6 = v19;
      v7 = v18;
      v8 = v17;
      v9 = v16;
      do
      {
        VersionUtils::OsVersion::OsVersion(&v16, v4);
        v10 = v16 < v9;
        if ( v16 == v9 )
        {
          v10 = v17 < v8;
          if ( v17 == v8 )
          {
            v10 = v18 < v7;
            if ( v18 == v7 )
              v10 = v19 < v6;
          }
        }
        if ( v10 )
        {
          if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v23) < *(_QWORD *)(v4 + 16) )
            std::_Xlen_string();
          std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
          v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
          std::wstring::wstring(v24, v12, v13, v11, v13, v12, v14);
          v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
          wil::RemoveDirectoryRecursive(v15);
          std::wstring::_Tidy_deallocate(v24);
        }
        v4 += 32;
      }
      while ( v4 != v5 );
      v5 = *((_QWORD *)&v20 + 1);
      v4 = v20;
    }
    if ( v4 )
    {
      std::_Destroy_range<std::allocator<std::wstring>>(v4, v5);
      std::_Deallocate<16>(v20, (v21 - v20) & 0xFFFFFFFFFFFFFFE0uLL);
      v20 = 0;
      v21 = 0;
    }
    std::wstring::_Tidy_deallocate(v25);
  }
  std::wstring::_Tidy_deallocate(v22);
}

```

## disassembly

```asm
0x18003db50  mov     [rsp-8+arg_10], rbx
0x18003db55  mov     [rsp-8+arg_18], rsi
0x18003db5a  push    rbp
0x18003db5b  push    rdi
0x18003db5c  push    r12
0x18003db5e  push    r14
0x18003db60  push    r15
0x18003db62  lea     rbp, [rsp-37h]
0x18003db67  sub     rsp, 0E0h
0x18003db6e  mov     rax, cs:__security_cookie
0x18003db75  xor     rax, rsp
0x18003db78  mov     [rbp+57h+var_30], rax
0x18003db7c  mov     rbx, rcx
0x18003db7f  lea     rcx, [rbp+57h+var_70]
0x18003db83  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003db88  nop
0x18003db89  lea     rdx, [rbp+57h+var_70]
0x18003db8d  lea     rcx, [rbp+57h+var_C0]
0x18003db91  call    ??0OsVersion@VersionUtils@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; VersionUtils::OsVersion::OsVersion(std::wstring const &)
0x18003db96  nop
0x18003db97  lea     rcx, [rbp+57h+var_70]
0x18003db9b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003dba0  lea     rdx, [rbx+8]
0x18003dba4  lea     r8, aStaged; "\\Staged\\"
0x18003dbab  lea     rcx, [rbp+57h+var_90]
0x18003dbaf  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18003dbb4  nop
0x18003dbb5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PFVC_NoDirectoryCleanup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PFVC_NoDirectoryCleanup@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PFVC_NoDirectoryCleanup> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PFVC_NoDirectoryCleanup>::GetImpl(void)'::`2'::impl
0x18003dbbc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PFVC_NoDirectoryCleanup@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PFVC_NoDirectoryCleanup>::__private_IsEnabled(void)
0x18003dbc1  test    al, al
0x18003dbc3  jz      short loc_18003DBDF
0x18003dbc5  lea     rcx, [rbp+57h+var_90]
0x18003dbc9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003dbce  mov     rcx, rax; pszPath
0x18003dbd1  call    cs:__imp_PathFileExistsW
0x18003dbd7  test    eax, eax
0x18003dbd9  jz      loc_18003DD01
0x18003dbdf  lea     r8, pszMore; "*"
0x18003dbe6  lea     rdx, [rbp+57h+var_90]
0x18003dbea  lea     rcx, [rbp+57h+var_50]
0x18003dbee  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18003dbf3  nop
0x18003dbf4  lea     rdx, [rbp+57h+var_50]
0x18003dbf8  lea     rcx, [rbp+57h+var_B0]
0x18003dbfc  call    ?GetSubDirectories@FilePayloadHandler@@CA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; FilePayloadHandler::GetSubDirectories(std::wstring const &)
0x18003dc01  nop
0x18003dc02  mov     rbx, qword ptr [rbp+57h+var_B0]
0x18003dc06  mov     rdi, qword ptr [rbp+57h+var_B0+8]
0x18003dc0a  cmp     rbx, rdi
0x18003dc0d  jz      loc_18003DCC3
0x18003dc13  mov     r12d, [rbp+57h+var_B4]
0x18003dc17  mov     esi, [rbp+57h+var_B8]
0x18003dc1a  mov     r14d, [rbp+57h+var_BC]
0x18003dc1e  mov     r15d, [rbp+57h+var_C0]
0x18003dc22  mov     rdx, rbx
0x18003dc25  lea     rcx, [rbp+57h+var_C0]
0x18003dc29  call    ??0OsVersion@VersionUtils@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; VersionUtils::OsVersion::OsVersion(std::wstring const &)
0x18003dc2e  cmp     [rbp+57h+var_C0], r15d
0x18003dc32  jnz     short loc_18003DC43
0x18003dc34  cmp     [rbp+57h+var_BC], r14d
0x18003dc38  jnz     short loc_18003DC43
0x18003dc3a  cmp     [rbp+57h+var_B8], esi
0x18003dc3d  jnz     short loc_18003DC43
0x18003dc3f  cmp     [rbp+57h+var_B4], r12d
0x18003dc43  jnb     short loc_18003DCAE
0x18003dc45  mov     r8, [rbp+57h+var_80]
0x18003dc49  mov     r10, [rbx+10h]
0x18003dc4d  mov     rax, 7FFFFFFFFFFFFFFEh
0x18003dc57  sub     rax, r8
0x18003dc5a  cmp     rax, r10
0x18003dc5d  jb      loc_18003DD32
0x18003dc63  mov     rcx, rbx
0x18003dc66  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003dc6b  mov     rdx, rax
0x18003dc6e  lea     rcx, [rbp+57h+var_90]
0x18003dc72  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003dc77  mov     r9, rax
0x18003dc7a  mov     [rsp+100h+var_D0], r10
0x18003dc7f  mov     [rsp+100h+var_D8], rdx
0x18003dc84  mov     [rsp+100h+var_E0], r8
0x18003dc89  lea     rcx, [rbp+57h+var_70]
0x18003dc8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18003dc92  nop
0x18003dc93  lea     rcx, [rbp+57h+var_70]
0x18003dc97  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003dc9c  mov     rcx, rax
0x18003dc9f  call    ?RemoveDirectoryRecursive@wil@@YAXPEBGW4RemoveDirectoryOptions@1@@Z; wil::RemoveDirectoryRecursive(ushort const *,wil::RemoveDirectoryOptions)
0x18003dca4  nop
0x18003dca5  lea     rcx, [rbp+57h+var_70]
0x18003dca9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003dcae  add     rbx, 20h ; ' '
0x18003dcb2  cmp     rbx, rdi
0x18003dcb5  jnz     loc_18003DC22
0x18003dcbb  mov     rdi, qword ptr [rbp+57h+var_B0+8]
0x18003dcbf  mov     rbx, qword ptr [rbp+57h+var_B0]
0x18003dcc3  test    rbx, rbx
0x18003dcc6  jz      short loc_18003DCF7
0x18003dcc8  mov     rdx, rdi
0x18003dccb  mov     rcx, rbx
0x18003dcce  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18003dcd3  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18003dcd7  mov     rdx, [rbp+57h+var_A0]
0x18003dcdb  sub     rdx, rcx
0x18003dcde  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18003dce2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003dce7  xorps   xmm0, xmm0
0x18003dcea  movdqu  [rbp+57h+var_B0], xmm0
0x18003dcef  mov     [rbp+57h+var_A0], 0
0x18003dcf7  lea     rcx, [rbp+57h+var_50]
0x18003dcfb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003dd00  nop
0x18003dd01  lea     rcx, [rbp+57h+var_90]
0x18003dd05  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003dd0a  mov     rcx, [rbp+57h+var_30]
0x18003dd0e  xor     rcx, rsp; StackCookie
0x18003dd11  call    __security_check_cookie
0x18003dd16  lea     r11, [rsp+100h+var_20]
0x18003dd1e  mov     rbx, [r11+40h]
0x18003dd22  mov     rsi, [r11+48h]
0x18003dd26  mov     rsp, r11
0x18003dd29  pop     r15
0x18003dd2b  pop     r14
0x18003dd2d  pop     r12
0x18003dd2f  pop     rdi
0x18003dd30  pop     rbp
0x18003dd31  retn
0x18003dd32  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
