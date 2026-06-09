# _lambda_94ba8ce0435b1f69c01c8b0462c8682c_::operator()

- ea: `0x18005bb2c`
- end: `0x18005bd3f`
- name: `_lambda_94ba8ce0435b1f69c01c8b0462c8682c_::operator()`
- size: `531`
- prototype: `char __fastcall(__int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18005a858`

## callees

- `0x18002abd0`
- `0x1800350cc`
- `0x180036f50`
- `0x180037958`
- `0x18003edd4`
- `0x18005a38c`
- `0x18005bb2c`
- `0x18005c004`
- `0x18005dca8`
- `0x18005df84`
- `0x18005f7e4`
- `0x18005f83c`
- `0x180071010`

## import_xrefs

- `archiveint!archive_entry_hardlink_w` at `0x18005bcb1`
- `archiveint!archive_entry_hardlink_w` at `0x18005bcb1`
- `archiveint!archive_entry_size` at `0x18005bc90`
- `archiveint!archive_entry_size` at `0x18005bc90`

## string_xrefs

- `0x18005bd0b`: `shell\ext\zip\archive\archivecreate.cpp`

## pseudocode

```c
char __fastcall lambda_94ba8ce0435b1f69c01c8b0462c8682c_::operator()(__int64 *a1, unsigned int *a2)
{
  __int64 v4; // rbx
  _QWORD *v5; // r14
  __int64 v6; // rbx
  bool v7; // bl
  __int64 v8; // r8
  __int64 v9; // rcx
  char result; // al
  int v11; // eax
  unsigned int v12; // r14d
  char v13; // bl
  __int64 v14; // rbx
  char v15; // r15
  __int64 v16; // r14
  int v17; // eax
  int v18; // [rsp+20h] [rbp-89h] BYREF
  int v19; // [rsp+28h] [rbp-81h] BYREF
  _BYTE v20[16]; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v21[32]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v22[48]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v23; // [rsp+90h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  if ( (*a2 & 0x80000000) == 0 )
  {
    v11 = CreateArchiveImpl::AddPathToArchive((CreateArchiveImpl *)a1[2], (const struct enum_path_data *)a2);
    v19 = v11;
    v12 = v11;
    if ( v11 >= 0 )
      return 0;
    if ( v11 == -2147023673 )
    {
      v13 = 1;
      *(_BYTE *)(a1[2] + 120) = 1;
      return v13;
    }
    v14 = a1[1];
    v15 = 0;
    LOBYTE(v18) = 0;
    if ( *(_QWORD *)std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::find(
                      v14,
                      v20,
                      &v19) == *(_QWORD *)(v14 + 8) )
    {
      v13 = CreateArchiveImpl::ShowErrorPrompt(a1[2], a2, v12, &v18);
      if ( v13 )
        return v13;
      v15 = v18;
    }
    else
    {
      v13 = 0;
    }
    v16 = archive_entry_size(*(_QWORD *)(a1[2] + 72));
    if ( !v16 && *((_WORD *)a2 + 2) == 0x8000 && !archive_entry_hardlink_w(*(_QWORD *)(a1[2] + 72)) )
    {
      memset_0(v22, 0, 0x68u);
      if ( (int)GetFileInfo(*((LPCWSTR *)a2 + 1), (struct _FILE_STAT_BASIC_INFORMATION *)v22) >= 0 )
        v16 = v23;
    }
    *(_QWORD *)(a1[2] + 96) -= v16;
    v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1[2] + 88) + 72LL))(
            *(_QWORD *)(a1[2] + 88),
            *(_QWORD *)(a1[2] + 104),
            *(_QWORD *)(a1[2] + 96));
    if ( v17 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x140,
        (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
        (const char *)(unsigned int)v17,
        v18);
    if ( v15 )
      std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::emplace<long const &>(
        a1[1],
        v20,
        &v19);
    return v13;
  }
  v4 = *a1;
  std::wstring::wstring(v21, *((_QWORD *)a2 + 1));
  v5 = a1 + 1;
  v7 = 0;
  if ( *(_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                    v4,
                    &v19,
                    v21) == *(_QWORD *)(*a1 + 8) )
  {
    v6 = *v5;
    if ( *(_QWORD *)std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::find(
                      *v5,
                      v20,
                      a2) == *(_QWORD *)(v6 + 8) )
      v7 = 1;
  }
  std::wstring::_Tidy_deallocate(v21);
  if ( v7 )
  {
    v8 = *a2;
    v9 = a1[2];
    LOBYTE(v18) = 0;
    result = CreateArchiveImpl::ShowErrorPrompt(v9, a2, v8, &v18);
    if ( result )
      return result;
    if ( (_BYTE)v18 )
      std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::emplace<long const &>(
        *v5,
        v20,
        a2);
  }
  return 0;
}

```

## disassembly

```asm
0x18005bb2c  mov     [rsp-8+arg_10], rbx
0x18005bb31  push    rbp
0x18005bb32  push    rsi
0x18005bb33  push    rdi
0x18005bb34  push    r14
0x18005bb36  push    r15
0x18005bb38  lea     rbp, [rsp-37h]
0x18005bb3d  sub     rsp, 0E0h
0x18005bb44  mov     rax, cs:__security_cookie
0x18005bb4b  xor     rax, rsp
0x18005bb4e  mov     [rbp+57h+var_30], rax
0x18005bb52  cmp     dword ptr [rdx], 0
0x18005bb55  mov     rsi, rdx
0x18005bb58  mov     rdi, rcx
0x18005bb5b  jge     loc_18005BC17
0x18005bb61  mov     rbx, [rcx]
0x18005bb64  lea     rcx, [rbp+57h+var_C0]
0x18005bb68  mov     rdx, [rdx+8]
0x18005bb6c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bb71  lea     r8, [rbp+57h+var_C0]
0x18005bb75  mov     rcx, rbx
0x18005bb78  lea     rdx, [rsp+100h+var_D8]
0x18005bb7d  call    ?find@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x18005bb82  mov     rcx, [rdi]
0x18005bb85  lea     r14, [rdi+8]
0x18005bb89  mov     rdx, [rcx+8]
0x18005bb8d  cmp     [rax], rdx
0x18005bb90  jnz     short loc_18005BBAD
0x18005bb92  mov     rbx, [r14]
0x18005bb95  lea     rdx, [rbp+57h+var_D0]
0x18005bb99  mov     rcx, rbx
0x18005bb9c  mov     r8, rsi
0x18005bb9f  call    ?find@?$_Hash@V?$_Uset_traits@JV?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@J@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@J@std@@@std@@@2@AEBJ@Z; std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::find(long const &)
0x18005bba4  mov     rcx, [rbx+8]
0x18005bba8  cmp     [rax], rcx
0x18005bbab  jz      short loc_18005BBB1
0x18005bbad  xor     bl, bl
0x18005bbaf  jmp     short loc_18005BBB3
0x18005bbb1  mov     bl, 1
0x18005bbb3  lea     rcx, [rbp+57h+var_C0]
0x18005bbb7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bbbc  test    bl, bl
0x18005bbbe  jz      short loc_18005BBF2
0x18005bbc0  mov     r8d, [rsi]
0x18005bbc3  lea     r9, [rsp+100h+var_E0]
0x18005bbc8  mov     rcx, [rdi+10h]
0x18005bbcc  mov     rdx, rsi
0x18005bbcf  mov     byte ptr [rsp+100h+var_E0], 0
0x18005bbd4  call    ?ShowErrorPrompt@CreateArchiveImpl@@AEAA?AW4enumerate_result@@AEBUenum_path_data@@JAEA_N@Z; CreateArchiveImpl::ShowErrorPrompt(enum_path_data const &,long,bool &)
0x18005bbd9  test    al, al
0x18005bbdb  jnz     short loc_18005BBF4
0x18005bbdd  cmp     byte ptr [rsp+100h+var_E0], al
0x18005bbe1  jz      short loc_18005BBF2
0x18005bbe3  mov     rcx, [r14]
0x18005bbe6  lea     rdx, [rbp+57h+var_D0]
0x18005bbea  mov     r8, rsi
0x18005bbed  call    ??$emplace@AEBJ@?$_Hash@V?$_Uset_traits@JV?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@J@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@J@std@@@std@@@std@@_N@1@AEBJ@Z; std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::emplace<long const &>(long const &)
0x18005bbf2  xor     al, al
0x18005bbf4  mov     rcx, [rbp+57h+var_30]
0x18005bbf8  xor     rcx, rsp; StackCookie
0x18005bbfb  call    __security_check_cookie
0x18005bc00  mov     rbx, [rsp+100h+arg_10]
0x18005bc08  add     rsp, 0E0h
0x18005bc0f  pop     r15
0x18005bc11  pop     r14
0x18005bc13  pop     rdi
0x18005bc14  pop     rsi
0x18005bc15  pop     rbp
0x18005bc16  retn
0x18005bc17  mov     rcx, [rcx+10h]; this
0x18005bc1b  call    ?AddPathToArchive@CreateArchiveImpl@@AEAAJAEBUenum_path_data@@@Z; CreateArchiveImpl::AddPathToArchive(enum_path_data const &)
0x18005bc20  mov     [rsp+100h+var_D8], eax
0x18005bc24  mov     r14d, eax
0x18005bc27  test    eax, eax
0x18005bc29  jns     short loc_18005BBF2
0x18005bc2b  cmp     eax, 800704C7h
0x18005bc30  jnz     short loc_18005BC3F
0x18005bc32  mov     rcx, [rdi+10h]
0x18005bc36  mov     bl, 1
0x18005bc38  mov     [rcx+78h], bl
0x18005bc3b  mov     al, bl
0x18005bc3d  jmp     short loc_18005BBF4
0x18005bc3f  mov     rbx, [rdi+8]
0x18005bc43  lea     r8, [rsp+100h+var_D8]
0x18005bc48  xor     r15b, r15b
0x18005bc4b  lea     rdx, [rbp+57h+var_D0]
0x18005bc4f  mov     rcx, rbx
0x18005bc52  mov     byte ptr [rsp+100h+var_E0], r15b; int
0x18005bc57  call    ?find@?$_Hash@V?$_Uset_traits@JV?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@J@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@J@std@@@std@@@2@AEBJ@Z; std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::find(long const &)
0x18005bc5c  mov     rcx, [rbx+8]
0x18005bc60  cmp     [rax], rcx
0x18005bc63  jz      short loc_18005BC69
0x18005bc65  xor     bl, bl
0x18005bc67  jmp     short loc_18005BC88
0x18005bc69  mov     rcx, [rdi+10h]
0x18005bc6d  lea     r9, [rsp+100h+var_E0]
0x18005bc72  mov     r8d, r14d
0x18005bc75  mov     rdx, rsi
0x18005bc78  call    ?ShowErrorPrompt@CreateArchiveImpl@@AEAA?AW4enumerate_result@@AEBUenum_path_data@@JAEA_N@Z; CreateArchiveImpl::ShowErrorPrompt(enum_path_data const &,long,bool &)
0x18005bc7d  mov     bl, al
0x18005bc7f  test    al, al
0x18005bc81  jnz     short loc_18005BC3B
0x18005bc83  mov     r15b, byte ptr [rsp+100h+var_E0]
0x18005bc88  mov     rcx, [rdi+10h]
0x18005bc8c  mov     rcx, [rcx+48h]
0x18005bc90  call    cs:__imp_archive_entry_size
0x18005bc96  mov     r14, rax
0x18005bc99  test    rax, rax
0x18005bc9c  jnz     short loc_18005BCDF
0x18005bc9e  mov     eax, 8000h
0x18005bca3  cmp     [rsi+4], ax
0x18005bca7  jnz     short loc_18005BCDF
0x18005bca9  mov     rcx, [rdi+10h]
0x18005bcad  mov     rcx, [rcx+48h]
0x18005bcb1  call    cs:__imp_archive_entry_hardlink_w
0x18005bcb7  test    rax, rax
0x18005bcba  jnz     short loc_18005BCDF
0x18005bcbc  xor     edx, edx; Val
0x18005bcbe  lea     r8d, [r14+68h]; Size
0x18005bcc2  lea     rcx, [rbp+57h+var_A0]; void *
0x18005bcc6  call    memset_0
0x18005bccb  mov     rcx, [rsi+8]; lpFileName
0x18005bccf  lea     rdx, [rbp+57h+var_A0]; struct _FILE_STAT_BASIC_INFORMATION *
0x18005bcd3  call    ?GetFileInfo@@YAJPEBGPEAU_FILE_STAT_BASIC_INFORMATION@@@Z; GetFileInfo(ushort const *,_FILE_STAT_BASIC_INFORMATION *)
0x18005bcd8  test    eax, eax
0x18005bcda  cmovns  r14, [rbp+57h+var_70]
0x18005bcdf  mov     rax, [rdi+10h]
0x18005bce3  sub     [rax+60h], r14
0x18005bce7  mov     rdx, [rdi+10h]
0x18005bceb  mov     rcx, [rdx+58h]
0x18005bcef  mov     r8, [rdx+60h]
0x18005bcf3  mov     rdx, [rdx+68h]
0x18005bcf7  mov     rax, [rcx]
0x18005bcfa  mov     rax, [rax+48h]
0x18005bcfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd03  test    eax, eax
0x18005bd05  jns     short loc_18005BD1F
0x18005bd07  mov     rcx, [rbp+5Fh]; this
0x18005bd0b  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005bd12  mov     r9d, eax; char *
0x18005bd15  mov     edx, 140h; void *
0x18005bd1a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005bd1f  test    r15b, r15b
0x18005bd22  jz      loc_18005BC3B
0x18005bd28  mov     rcx, [rdi+8]
0x18005bd2c  lea     r8, [rsp+100h+var_D8]
0x18005bd31  lea     rdx, [rbp+57h+var_D0]
0x18005bd35  call    ??$emplace@AEBJ@?$_Hash@V?$_Uset_traits@JV?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@J@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@J@std@@@std@@@std@@_N@1@AEBJ@Z; std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::emplace<long const &>(long const &)
0x18005bd3a  jmp     loc_18005BC3B
```
