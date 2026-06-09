# PromptAbsoluteLinkOverride

- ea: `0x180068128`
- end: `0x1800683c2`
- name: `PromptAbsoluteLinkOverride`
- size: `666`
- prototype: `__int64 __fastcall(__int64, struct archive_entry *, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18006408c`
- `0x18006442c`

## callees

- `0x1800208a8`
- `0x180020cbc`
- `0x18002abd0`
- `0x18002ec00`
- `0x18002ed2c`
- `0x180030a3c`
- `0x180031e94`
- `0x180036f50`
- `0x180037958`
- `0x180057fbc`
- `0x180058688`
- `0x18005faf4`
- `0x180062780`
- `0x180068128`
- `0x180071010`

## import_xrefs

- `archiveint!archive_entry_pathname_w` at `0x180068160`
- `archiveint!archive_entry_pathname_w` at `0x180068160`
- `archiveint!archive_entry_symlink_w` at `0x1800682ba`
- `archiveint!archive_entry_symlink_w` at `0x1800682ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PromptAbsoluteLinkOverride(__int64 a1, struct archive_entry *a2, __int64 a3, int a4, __int64 a5)
{
  __int64 v9; // rax
  const WCHAR *v10; // rax
  const struct _GUID *v11; // rdx
  int v12; // eax
  unsigned int v13; // ebx
  __int128 v15; // xmm0
  int v16; // eax
  int v17; // [rsp+20h] [rbp-128h]
  __int64 v18; // [rsp+30h] [rbp-118h] BYREF
  _BYTE v19[32]; // [rsp+38h] [rbp-110h] BYREF
  _BYTE v20[40]; // [rsp+58h] [rbp-F0h] BYREF
  _DWORD v21[2]; // [rsp+80h] [rbp-C8h] BYREF
  int v22; // [rsp+88h] [rbp-C0h]
  __int128 v23; // [rsp+8Ch] [rbp-BCh]
  int v24; // [rsp+A4h] [rbp-A4h]
  void *v25; // [rsp+A8h] [rbp-A0h]
  int v26; // [rsp+B8h] [rbp-90h]
  __int64 v27; // [rsp+C0h] [rbp-88h]
  __int64 v28; // [rsp+D0h] [rbp-78h]
  void *v29; // [rsp+E0h] [rbp-68h] BYREF
  int v30; // [rsp+E8h] [rbp-60h] BYREF
  __int64 v31; // [rsp+F0h] [rbp-58h] BYREF
  _BYTE v32[32]; // [rsp+F8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v18 = archive_entry_pathname_w(a2);
  std::filesystem::path::path(v19, &v18);
  v9 = std::filesystem::operator/(v20, a1, v19);
  std::filesystem::path::lexically_normal(v9, v32);
  std::wstring::_Tidy_deallocate(v20);
  std::wstring::_Tidy_deallocate(v19);
  v29 = 0;
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
  v12 = ShellItemFromFileSystemPath(v10, v11, &v29, 0);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DB,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
      (const char *)(unsigned int)v12,
      v17);
    if ( v29 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v29);
LABEL_4:
    std::wstring::_Tidy_deallocate(v32);
    return v13;
  }
  memset_0(v21, 0, 0x60u);
  v28 = a3;
  v21[1] = 2;
  v21[0] = a4;
  v22 = ((unsigned __int8)ArchiveEntryToWindowsAttributes(a2) >> 4) & 1;
  v24 = 0;
  v25 = v29;
  v26 = -2147024215;
  if ( v22 )
    v15 = STCONFIRM_ABSOLUTE_LINK_STORAGE;
  else
    v15 = STCONFIRM_ABSOLUTE_LINK_STREAM;
  v23 = v15;
  v27 = archive_entry_symlink_w(a2);
  v30 = 0;
  wil::CoCreateInstance<ITransferConfirmation,wil::err_exception_policy>(&v31);
  v16 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64, int *))(*(_QWORD *)v31 + 24LL))(v31, v21, a5, &v30);
  v13 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3EA,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
      (const char *)(unsigned int)v16,
      v17);
    wil::com_ptr_t<ITransferConfirmation,wil::err_exception_policy>::~com_ptr_t<ITransferConfirmation,wil::err_exception_policy>(&v31);
    if ( v29 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v29);
    goto LABEL_4;
  }
  wil::com_ptr_t<ITransferConfirmation,wil::err_exception_policy>::~com_ptr_t<ITransferConfirmation,wil::err_exception_policy>(&v31);
  if ( v29 )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v29);
  std::wstring::_Tidy_deallocate(v32);
  return 0;
}

```

## disassembly

```asm
0x180068128  push    rbx
0x18006812a  push    rsi
0x18006812b  push    rdi
0x18006812c  push    r14
0x18006812e  push    r15
0x180068130  sub     rsp, 120h
0x180068137  mov     rax, cs:__security_cookie
0x18006813e  xor     rax, rsp
0x180068141  mov     [rsp+148h+var_30], rax
0x180068149  mov     r14d, r9d
0x18006814c  mov     rsi, r8
0x18006814f  mov     rdi, rdx
0x180068152  mov     rbx, rcx
0x180068155  mov     r15, [rsp+148h+arg_20]
0x18006815d  mov     rcx, rdx
0x180068160  call    cs:__imp_archive_entry_pathname_w
0x180068166  mov     [rsp+148h+var_118], rax
0x18006816b  lea     rdx, [rsp+148h+var_118]
0x180068170  lea     rcx, [rsp+148h+var_110]
0x180068175  call    ??$?0PEBG$0A@@path@filesystem@std@@QEAA@AEBQEBGW4format@012@@Z; std::filesystem::path::path(ushort const * const &,std::filesystem::path::format)
0x18006817a  nop
0x18006817b  lea     r8, [rsp+148h+var_110]
0x180068180  mov     rdx, rbx
0x180068183  lea     rcx, [rsp+148h+var_F0]
0x180068188  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18006818d  nop
0x18006818e  lea     rdx, [rsp+148h+var_50]
0x180068196  mov     rcx, rax
0x180068199  call    ?lexically_normal@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::lexically_normal(void)
0x18006819e  nop
0x18006819f  lea     rcx, [rsp+148h+var_F0]
0x1800681a4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800681a9  nop
0x1800681aa  lea     rcx, [rsp+148h+var_110]
0x1800681af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800681b4  mov     [rsp+148h+var_68], 0
0x1800681c0  lea     rcx, [rsp+148h+var_50]
0x1800681c8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800681cd  mov     rcx, rax; pszPath
0x1800681d0  xor     r9d, r9d; struct IBindCtx *
0x1800681d3  lea     r8, [rsp+148h+var_68]; void **
0x1800681db  call    ?ShellItemFromFileSystemPath@@YAJPEBGAEBU_GUID@@PEAPEAXPEAUIBindCtx@@@Z; ShellItemFromFileSystemPath(ushort const *,_GUID const &,void * *,IBindCtx *)
0x1800681e0  mov     ebx, eax
0x1800681e2  test    eax, eax
0x1800681e4  jns     short loc_180068230
0x1800681e6  mov     rcx, [rsp+148h]; this
0x1800681ee  mov     r9d, eax; char *
0x1800681f1  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x1800681f8  mov     edx, 3DBh; void *
0x1800681fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068202  nop
0x180068203  cmp     [rsp+148h+var_68], 0
0x18006820c  jz      short loc_18006821C
0x18006820e  lea     rcx, [rsp+148h+var_68]
0x180068216  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18006821b  nop
0x18006821c  lea     rcx, [rsp+148h+var_50]
0x180068224  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180068229  mov     eax, ebx
0x18006822b  jmp     loc_1800683A2
0x180068230  xor     edx, edx; Val
0x180068232  lea     r8d, [rdx+60h]; Size
0x180068236  lea     rcx, [rsp+148h+var_C8]; void *
0x18006823e  call    memset_0
0x180068243  mov     [rsp+148h+var_78], rsi
0x18006824b  mov     [rsp+148h+var_C4], 2
0x180068256  mov     [rsp+148h+var_C8], r14d
0x18006825e  mov     rcx, rdi; struct archive_entry *
0x180068261  call    ?ArchiveEntryToWindowsAttributes@@YAKPEAUarchive_entry@@@Z; ArchiveEntryToWindowsAttributes(archive_entry *)
0x180068266  movzx   ecx, al
0x180068269  shr     ecx, 4
0x18006826c  and     ecx, 1
0x18006826f  mov     [rsp+148h+var_C0], ecx
0x180068276  mov     [rsp+148h+var_A4], 0
0x180068281  mov     rax, [rsp+148h+var_68]
0x180068289  mov     [rsp+148h+var_A0], rax
0x180068291  mov     [rsp+148h+var_90], 800702A9h
0x18006829c  jz      short loc_1800682A7
0x18006829e  movups  xmm0, cs:STCONFIRM_ABSOLUTE_LINK_STORAGE
0x1800682a5  jmp     short loc_1800682AE
0x1800682a7  movups  xmm0, cs:STCONFIRM_ABSOLUTE_LINK_STREAM
0x1800682ae  movdqu  [rsp+148h+var_BC], xmm0
0x1800682b7  mov     rcx, rdi
0x1800682ba  call    cs:__imp_archive_entry_symlink_w
0x1800682c0  mov     [rsp+148h+var_88], rax
0x1800682c8  mov     [rsp+148h+var_60], 0
0x1800682d3  lea     rcx, [rsp+148h+var_58]
0x1800682db  call    ??$CoCreateInstance@UITransferConfirmation@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UITransferConfirmation@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<ITransferConfirmation,wil::err_exception_policy>(_GUID const &,ulong)
0x1800682e0  nop
0x1800682e1  mov     rcx, [rsp+148h+var_58]
0x1800682e9  mov     rax, [rcx]
0x1800682ec  lea     r9, [rsp+148h+var_60]
0x1800682f4  mov     r8, r15
0x1800682f7  lea     rdx, [rsp+148h+var_C8]
0x1800682ff  mov     rax, [rax+18h]
0x180068303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068308  mov     ebx, eax
0x18006830a  test    eax, eax
0x18006830c  jns     short loc_180068363
0x18006830e  mov     rcx, [rsp+148h]; this
0x180068316  mov     r9d, eax; char *
0x180068319  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x180068320  mov     edx, 3EAh; void *
0x180068325  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006832a  nop
0x18006832b  lea     rcx, [rsp+148h+var_58]
0x180068333  call    ??1?$com_ptr_t@UITransferConfirmation@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITransferConfirmation,wil::err_exception_policy>::~com_ptr_t<ITransferConfirmation,wil::err_exception_policy>(void)
0x180068338  nop
0x180068339  cmp     [rsp+148h+var_68], 0
0x180068342  jz      short loc_180068352
0x180068344  lea     rcx, [rsp+148h+var_68]
0x18006834c  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180068351  nop
0x180068352  lea     rcx, [rsp+148h+var_50]
0x18006835a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006835f  mov     eax, ebx
0x180068361  jmp     short loc_1800683A2
0x180068363  lea     rcx, [rsp+148h+var_58]
0x18006836b  call    ??1?$com_ptr_t@UITransferConfirmation@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITransferConfirmation,wil::err_exception_policy>::~com_ptr_t<ITransferConfirmation,wil::err_exception_policy>(void)
0x180068370  nop
0x180068371  cmp     [rsp+148h+var_68], 0
0x18006837a  jz      short loc_18006838A
0x18006837c  lea     rcx, [rsp+148h+var_68]
0x180068384  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180068389  nop
0x18006838a  lea     rcx, [rsp+148h+var_50]
0x180068392  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180068397  xor     eax, eax
0x180068399  jmp     short loc_1800683A2
0x18006839b  mov     eax, [rsp+148h+var_60]
0x1800683a2  mov     rcx, [rsp+148h+var_30]
0x1800683aa  xor     rcx, rsp; StackCookie
0x1800683ad  call    __security_check_cookie
0x1800683b2  add     rsp, 120h
0x1800683b9  pop     r15
0x1800683bb  pop     r14
0x1800683bd  pop     rdi
0x1800683be  pop     rsi
0x1800683bf  pop     rbx
0x1800683c0  retn
```
