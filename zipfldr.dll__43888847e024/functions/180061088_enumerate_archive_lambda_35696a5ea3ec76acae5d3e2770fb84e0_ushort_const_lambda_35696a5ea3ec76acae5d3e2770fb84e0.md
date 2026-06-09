# enumerate_archive<_lambda_35696a5ea3ec76acae5d3e2770fb84e0_>(ushort const *,_lambda_35696a5ea3ec76acae5d3e2770fb84e0_ &&)

- ea: `0x180061088`
- end: `0x180061398`
- name: `??$enumerate_archive@V_lambda_35696a5ea3ec76acae5d3e2770fb84e0_@@@@YAXPEBG$$QEAV_lambda_35696a5ea3ec76acae5d3e2770fb84e0_@@@Z`
- size: `784`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006644c`

## callees

- `0x180035418`
- `0x18003547c`
- `0x1800354bc`
- `0x1800354e0`
- `0x1800354fc`
- `0x180036f50`
- `0x1800390f1`
- `0x180055f7c`
- `0x180055f9c`
- `0x180055fd4`
- `0x18005634c`
- `0x180061088`
- `0x180062d2c`

## import_xrefs

- `archiveint!archive_read_has_encrypted_entries` at `0x18006115f`
- `archiveint!archive_read_has_encrypted_entries` at `0x18006115f`
- `archiveint!archive_error_string` at `0x180061170`
- `archiveint!archive_error_string` at `0x18006121a`
- `archiveint!archive_error_string` at `0x180061269`
- `archiveint!archive_error_string` at `0x180061336`
- `archiveint!archive_error_string` at `0x180061170`
- `archiveint!archive_error_string` at `0x18006121a`
- `archiveint!archive_error_string` at `0x180061269`
- `archiveint!archive_error_string` at `0x180061336`
- `archiveint!archive_errno` at `0x1800610ef`
- `archiveint!archive_errno` at `0x18006113e`
- `archiveint!archive_errno` at `0x1800611fd`
- `archiveint!archive_errno` at `0x1800610ef`
- `archiveint!archive_errno` at `0x18006113e`
- `archiveint!archive_errno` at `0x1800611fd`
- `archiveint!archive_read_next_header` at `0x18006111a`
- `archiveint!archive_read_next_header` at `0x18006111a`
- `archiveint!archive_read_open_filename_w` at `0x1800610e2`
- `archiveint!archive_read_open_filename_w` at `0x1800610e2`
- `archiveint!archive_read_new` at `0x1800610af`
- `archiveint!archive_read_new` at `0x1800610af`

## string_xrefs

- `0x18006124a`: `shell\ext\zip\archive\precomp.h`
- `0x180061299`: `shell\ext\zip\archive\precomp.h`
- `0x1800612bd`: `shell\ext\zip\archive\precomp.h`
- `0x1800612e1`: `shell\ext\zip\archive\precomp.h`
- `0x1800612f3`: `shell\ext\zip\archive\precomp.h`
- `0x180061317`: `shell\ext\zip\archive\precomp.h`
- `0x180061366`: `shell\ext\zip\archive\precomp.h`

## pseudocode

```c
__int64 __fastcall enumerate_archive<_lambda_35696a5ea3ec76acae5d3e2770fb84e0_>(unsigned __int16 *a1, char **a2)
{
  struct archive *v4; // rax
  const char *v5; // r9
  struct archive *v6; // rbx
  int v7; // ebx
  int v8; // esi
  char v9; // bp
  int v10; // eax
  int v11; // edi
  int v12; // ebx
  unsigned int v13; // r8d
  const char *v14; // r9
  _BYTE *v15; // rax
  __int64 v16; // r8
  unsigned int v17; // r8d
  const char *v18; // r9
  int v20; // ebx
  __int64 v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  const char *v24; // rdx
  __int64 v25; // rax
  unsigned int v26; // eax
  unsigned int v27; // eax
  const char *v28; // rdx
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  __int64 v32; // rax
  unsigned int v33; // eax
  unsigned int v34; // eax
  const char *v35; // rdx
  unsigned int v36; // [rsp+20h] [rbp-48h]
  struct archive *v37; // [rsp+30h] [rbp-38h] BYREF
  struct archive_entry *v38; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = (struct archive *)archive_read_new();
  v6 = v4;
  v37 = v4;
  if ( !v4 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x195,
      (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
      v5);
  prepare_archive_reader(v4, a1);
  if ( (unsigned int)archive_read_open_filename_w(v6, a1, 10240) )
  {
    v7 = archive_errno(v6);
    if ( !v7 )
    {
      v31 = wil::verify_hresult<long>(2147500037LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x199,
        (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
        (const char *)v31,
        v36);
    }
    v25 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(&v37);
    archive_error_string(v25);
    v26 = HRESULT_FROM_ERRNO(v7);
    v27 = wil::verify_hresult<long>(v26);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x199,
      (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
      (const char *)v27,
      (int)"archive error: %hs",
      v28,
      v37);
  }
  v38 = 0;
  v8 = 0;
  v9 = 0;
  do
  {
    v10 = archive_read_next_header(v6, &v38);
    v11 = v10;
    if ( v10 == 1 )
      break;
    if ( v10 == -10 )
    {
      if ( (unsigned int)++v8 > 5 )
      {
        v12 = archive_errno(v6);
        if ( v12 )
        {
          v32 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(&v37);
          archive_error_string(v32);
          v33 = HRESULT_FROM_ERRNO(v12);
          v34 = wil::verify_hresult<long>(v33);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x1A9,
            (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
            (const char *)v34,
            (int)"archive error: %hs",
            v35,
            v37);
        }
        v29 = wil::verify_hresult<long>(2147500037LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1A9,
          (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
          (const char *)v29,
          v36);
      }
    }
    else
    {
      if ( v10 )
      {
        if ( v10 == -30 )
        {
          if ( (int)archive_read_has_encrypted_entries(v6) > 0 )
            wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x1B5, v13, v14, v36);
          v15 = (_BYTE *)archive_error_string(v6);
          if ( !v15 )
            goto LABEL_24;
          v16 = -1;
          do
            ++v16;
          while ( v15[v16] );
          if ( v16 != 27 )
          {
LABEL_24:
            v20 = archive_errno(v6);
            if ( v20 )
            {
              v21 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(&v37);
              archive_error_string(v21);
              v22 = HRESULT_FROM_ERRNO(v20);
              v23 = wil::verify_hresult<long>(v22);
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x1D0,
                (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
                (const char *)v23,
                (int)"archive error: %hs",
                v24,
                v37);
            }
            v30 = wil::verify_hresult<long>(2147500037LL);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1D0,
              (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
              (const char *)v30,
              v36);
          }
          if ( !memcmp_0(v15, KnownArchiveErrors::EncryptedRAR, 0x1Bu) )
            wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x1C1, v17, v18, v36);
        }
        if ( v11 != -20 )
          goto LABEL_24;
      }
      v8 = 0;
      do
        v9 = _lambda_35696a5ea3ec76acae5d3e2770fb84e0_::operator()(a2, v6, v38);
      while ( v9 == 2 );
    }
  }
  while ( v9 != 1 );
  return wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(&v37);
}

```

## disassembly

```asm
0x180061088  mov     [rsp+arg_10], rbx
0x18006108d  mov     [rsp+arg_18], rbp
0x180061092  push    rsi
0x180061093  push    rdi
0x180061094  push    r14
0x180061096  sub     rsp, 50h
0x18006109a  mov     rax, cs:__security_cookie
0x1800610a1  xor     rax, rsp
0x1800610a4  mov     [rsp+68h+var_28], rax
0x1800610a9  mov     r14, rdx
0x1800610ac  mov     rdi, rcx
0x1800610af  call    cs:__imp_archive_read_new
0x1800610b5  mov     rbx, rax
0x1800610b8  mov     [rsp+68h+var_38], rax
0x1800610bd  mov     rcx, [rsp+68h]; this
0x1800610c2  test    rax, rax
0x1800610c5  jz      loc_1800612F3
0x1800610cb  mov     rdx, rdi; unsigned __int16 *
0x1800610ce  mov     rcx, rax; struct archive *
0x1800610d1  call    ?prepare_archive_reader@@YAXPEAUarchive@@PEBG@Z; prepare_archive_reader(archive *,ushort const *)
0x1800610d6  mov     r8d, 2800h
0x1800610dc  mov     rdx, rdi
0x1800610df  mov     rcx, rbx
0x1800610e2  call    cs:__imp_archive_read_open_filename_w
0x1800610e8  test    eax, eax
0x1800610ea  jz      short loc_180061104
0x1800610ec  mov     rcx, rbx
0x1800610ef  call    cs:__imp_archive_errno
0x1800610f5  mov     ebx, eax
0x1800610f7  test    eax, eax
0x1800610f9  jnz     loc_18006125C
0x1800610ff  jmp     loc_180061305
0x180061104  mov     [rsp+68h+var_30], 0
0x18006110d  xor     esi, esi
0x18006110f  xor     bpl, bpl
0x180061112  lea     rdx, [rsp+68h+var_30]
0x180061117  mov     rcx, rbx
0x18006111a  call    cs:__imp_archive_read_next_header
0x180061120  mov     edi, eax
0x180061122  cmp     eax, 1
0x180061125  jz      loc_1800611CE
0x18006112b  cmp     eax, 0FFFFFFF6h
0x18006112e  jnz     short loc_180061153
0x180061130  inc     esi
0x180061132  cmp     esi, 5
0x180061135  jbe     loc_1800611C4
0x18006113b  mov     rcx, rbx
0x18006113e  call    cs:__imp_archive_errno
0x180061144  mov     ebx, eax
0x180061146  test    eax, eax
0x180061148  jz      loc_1800612AB
0x18006114e  jmp     loc_180061329
0x180061153  test    edi, edi
0x180061155  jz      short loc_1800611AB
0x180061157  cmp     edi, 0FFFFFFE2h
0x18006115a  jnz     short loc_1800611A6
0x18006115c  mov     rcx, rbx
0x18006115f  call    cs:__imp_archive_read_has_encrypted_entries
0x180061165  test    eax, eax
0x180061167  jg      loc_180061388
0x18006116d  mov     rcx, rbx
0x180061170  call    cs:__imp_archive_error_string
0x180061176  test    rax, rax
0x180061179  jz      short loc_1800611FA
0x18006117b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006117f  inc     r8; Size
0x180061182  cmp     byte ptr [rax+r8], 0
0x180061187  jnz     short loc_18006117F
0x180061189  cmp     r8, 1Bh
0x18006118d  jnz     short loc_1800611FA
0x18006118f  mov     rdx, cs:?EncryptedRAR@KnownArchiveErrors@@3V?$basic_string_view@DU?$char_traits@D@std@@@std@@B; Buf2
0x180061196  mov     rcx, rax; Buf1
0x180061199  call    memcmp_0
0x18006119e  test    eax, eax
0x1800611a0  jz      loc_180061378
0x1800611a6  cmp     edi, 0FFFFFFECh
0x1800611a9  jnz     short loc_1800611FA
0x1800611ab  xor     esi, esi
0x1800611ad  mov     r8, [rsp+68h+var_30]
0x1800611b2  mov     rdx, rbx
0x1800611b5  mov     rcx, r14
0x1800611b8  call    ??R_lambda_35696a5ea3ec76acae5d3e2770fb84e0_@@QEBA@PEAUarchive@@PEAUarchive_entry@@@Z; _lambda_35696a5ea3ec76acae5d3e2770fb84e0_::operator()(archive *,archive_entry *)
0x1800611bd  mov     bpl, al
0x1800611c0  cmp     al, 2
0x1800611c2  jz      short loc_1800611AD
0x1800611c4  cmp     bpl, 1
0x1800611c8  jnz     loc_180061112
0x1800611ce  lea     rcx, [rsp+68h+var_38]
0x1800611d3  call    ??1?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(void)
0x1800611d8  mov     rcx, [rsp+68h+var_28]
0x1800611dd  xor     rcx, rsp; StackCookie
0x1800611e0  call    __security_check_cookie
0x1800611e5  lea     r11, [rsp+68h+var_18]
0x1800611ea  mov     rbx, [r11+30h]
0x1800611ee  mov     rbp, [r11+38h]
0x1800611f2  mov     rsp, r11
0x1800611f5  pop     r14
0x1800611f7  pop     rdi
0x1800611f8  pop     rsi
0x1800611f9  retn
0x1800611fa  mov     rcx, rbx
0x1800611fd  call    cs:__imp_archive_errno
0x180061203  mov     ebx, eax
0x180061205  test    eax, eax
0x180061207  jz      loc_1800612CF
0x18006120d  lea     rcx, [rsp+68h+var_38]
0x180061212  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x180061217  mov     rcx, rax
0x18006121a  call    cs:__imp_archive_error_string
0x180061220  mov     rdx, rax
0x180061223  mov     ecx, ebx; int
0x180061225  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x18006122a  mov     ecx, eax
0x18006122c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061231  mov     r9d, eax; char *
0x180061234  mov     rcx, [rsp+68h]; this
0x180061239  mov     [rsp+68h+var_40], rdx; char *
0x18006123e  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180061245  mov     qword ptr [rsp+68h+var_48], rax; int
0x18006124a  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061251  mov     edx, 1D0h; void *
0x180061256  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006125c  lea     rcx, [rsp+68h+var_38]
0x180061261  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x180061266  mov     rcx, rax
0x180061269  call    cs:__imp_archive_error_string
0x18006126f  mov     rdx, rax
0x180061272  mov     ecx, ebx; int
0x180061274  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x180061279  mov     ecx, eax
0x18006127b  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061280  mov     r9d, eax; char *
0x180061283  mov     rcx, [rsp+68h]; this
0x180061288  mov     [rsp+68h+var_40], rdx; char *
0x18006128d  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180061294  mov     qword ptr [rsp+68h+var_48], rax; int
0x180061299  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x1800612a0  mov     edx, 199h; void *
0x1800612a5  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800612ab  mov     ecx, 80004005h
0x1800612b0  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800612b5  mov     r9d, eax; char *
0x1800612b8  mov     rcx, [rsp+68h]; this
0x1800612bd  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x1800612c4  mov     edx, 1A9h; void *
0x1800612c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800612cf  mov     ecx, 80004005h
0x1800612d4  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800612d9  mov     r9d, eax; char *
0x1800612dc  mov     rcx, [rsp+68h]; this
0x1800612e1  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x1800612e8  mov     edx, 1D0h; void *
0x1800612ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800612f3  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x1800612fa  mov     edx, 195h; void *
0x1800612ff  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180061305  mov     ecx, 80004005h
0x18006130a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18006130f  mov     r9d, eax; char *
0x180061312  mov     rcx, [rsp+68h]; this
0x180061317  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x18006131e  mov     edx, 199h; void *
0x180061323  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061329  lea     rcx, [rsp+68h+var_38]
0x18006132e  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x180061333  mov     rcx, rax
0x180061336  call    cs:__imp_archive_error_string
0x18006133c  mov     rdx, rax
0x18006133f  mov     ecx, ebx; int
0x180061341  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x180061346  mov     ecx, eax
0x180061348  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18006134d  mov     r9d, eax; char *
0x180061350  mov     rcx, [rsp+68h]; this
0x180061355  mov     [rsp+68h+var_40], rdx; char *
0x18006135a  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180061361  mov     qword ptr [rsp+68h+var_48], rax; int
0x180061366  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x18006136d  mov     edx, 1A9h; void *
0x180061372  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180061378  mov     rcx, [rsp+68h]; this
0x18006137d  mov     edx, 1C1h; void *
0x180061382  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180061388  mov     rcx, [rsp+68h]; this
0x18006138d  mov     edx, 1B5h; void *
0x180061392  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
