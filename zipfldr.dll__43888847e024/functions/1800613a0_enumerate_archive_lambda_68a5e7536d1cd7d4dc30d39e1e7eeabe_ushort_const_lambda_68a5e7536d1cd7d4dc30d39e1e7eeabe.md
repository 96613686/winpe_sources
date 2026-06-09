# enumerate_archive<_lambda_68a5e7536d1cd7d4dc30d39e1e7eeabe_>(ushort const *,_lambda_68a5e7536d1cd7d4dc30d39e1e7eeabe_ &&)

- ea: `0x1800613a0`
- end: `0x1800616bf`
- name: `??$enumerate_archive@V_lambda_68a5e7536d1cd7d4dc30d39e1e7eeabe_@@@@YAXPEBG$$QEAV_lambda_68a5e7536d1cd7d4dc30d39e1e7eeabe_@@@Z`
- size: `799`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
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
- `0x1800613a0`

## import_xrefs

- `archiveint!archive_read_has_encrypted_entries` at `0x18006146b`
- `archiveint!archive_read_has_encrypted_entries` at `0x18006146b`
- `archiveint!archive_error_string` at `0x18006147c`
- `archiveint!archive_error_string` at `0x180061565`
- `archiveint!archive_error_string` at `0x1800615d8`
- `archiveint!archive_error_string` at `0x18006165d`
- `archiveint!archive_error_string` at `0x18006147c`
- `archiveint!archive_error_string` at `0x180061565`
- `archiveint!archive_error_string` at `0x1800615d8`
- `archiveint!archive_error_string` at `0x18006165d`
- `archiveint!archive_errno` at `0x180061402`
- `archiveint!archive_errno` at `0x18006144a`
- `archiveint!archive_errno` at `0x1800614fa`
- `archiveint!archive_errno` at `0x180061402`
- `archiveint!archive_errno` at `0x18006144a`
- `archiveint!archive_errno` at `0x1800614fa`
- `archiveint!archive_read_next_header` at `0x18006142a`
- `archiveint!archive_read_next_header` at `0x18006142a`
- `archiveint!archive_read_open_filename_w` at `0x1800613f5`
- `archiveint!archive_read_open_filename_w` at `0x1800613f5`
- `archiveint!archive_read_new` at `0x1800613c2`
- `archiveint!archive_read_new` at `0x1800613c2`
- `archiveint!archive_entry_size` at `0x1800614c7`
- `archiveint!archive_entry_size` at `0x1800614c7`
- `archiveint!archive_entry_filetype` at `0x1800614d7`
- `archiveint!archive_entry_filetype` at `0x1800614d7`

## string_xrefs

- `0x180061546`: `shell\ext\zip\archive\precomp.h`
- `0x180061595`: `shell\ext\zip\archive\precomp.h`
- `0x1800615b9`: `shell\ext\zip\archive\precomp.h`
- `0x180061608`: `shell\ext\zip\archive\precomp.h`
- `0x18006161a`: `shell\ext\zip\archive\precomp.h`
- `0x18006163e`: `shell\ext\zip\archive\precomp.h`
- `0x18006168d`: `shell\ext\zip\archive\precomp.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall enumerate_archive<_lambda_68a5e7536d1cd7d4dc30d39e1e7eeabe_>(unsigned __int16 *a1, _QWORD **a2)
{
  struct archive *v4; // rax
  const char *v5; // r9
  struct archive *v6; // rbx
  int v7; // ebx
  int v8; // esi
  int v9; // eax
  int v10; // edi
  int v11; // ebx
  unsigned int v12; // r8d
  const char *v13; // r9
  _BYTE *v14; // rax
  __int64 v15; // r8
  unsigned int v16; // r8d
  const char *v17; // r9
  __int64 v18; // rdi
  int v19; // ebx
  unsigned int v21; // eax
  __int64 v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // eax
  const char *v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // eax
  const char *v30; // rdx
  unsigned int v31; // eax
  __int64 v32; // rax
  unsigned int v33; // eax
  unsigned int v34; // eax
  const char *v35; // rdx
  unsigned int v36; // [rsp+20h] [rbp-48h]
  struct archive *v37; // [rsp+30h] [rbp-38h] BYREF
  __int64 v38; // [rsp+38h] [rbp-30h] BYREF
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
    v22 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(&v37);
    archive_error_string(v22);
    v23 = HRESULT_FROM_ERRNO(v7);
    v24 = wil::verify_hresult<long>(v23);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x199,
      (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
      (const char *)v24,
      (int)"archive error: %hs",
      v25,
      v37);
  }
  v38 = 0;
  v8 = 0;
  while ( 1 )
  {
    v9 = archive_read_next_header(v6, &v38);
    v10 = v9;
    if ( v9 == 1 )
      return wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(&v37);
    if ( v9 == -10 )
    {
      if ( (unsigned int)++v8 > 5 )
      {
        v11 = archive_errno(v6);
        if ( v11 )
        {
          v32 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(&v37);
          archive_error_string(v32);
          v33 = HRESULT_FROM_ERRNO(v11);
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
        v26 = wil::verify_hresult<long>(2147500037LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1A9,
          (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
          (const char *)v26,
          v36);
      }
    }
    else
    {
      if ( v9 )
      {
        if ( v9 == -30 )
        {
          if ( (int)archive_read_has_encrypted_entries(v6) > 0 )
            wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x1B5, v12, v13, v36);
          v14 = (_BYTE *)archive_error_string(v6);
          if ( !v14 )
            goto LABEL_22;
          v15 = -1;
          do
            ++v15;
          while ( v14[v15] );
          if ( v15 != 27 )
          {
LABEL_22:
            v19 = archive_errno(v6);
            if ( !v19 )
            {
              v21 = wil::verify_hresult<long>(2147500037LL);
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1D0,
                (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
                (const char *)v21,
                v36);
            }
            v27 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(&v37);
            archive_error_string(v27);
            v28 = HRESULT_FROM_ERRNO(v19);
            v29 = wil::verify_hresult<long>(v28);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x1D0,
              (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
              (const char *)v29,
              (int)"archive error: %hs",
              v30,
              v37);
          }
          if ( !memcmp_0(v14, KnownArchiveErrors::EncryptedRAR, 0x1Bu) )
            wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x1C1, v16, v17, v36);
        }
        if ( v10 != -20 )
          goto LABEL_22;
      }
      v8 = 0;
      v18 = v38;
      ++**a2;
      (*a2)[1] += archive_entry_size(v18);
      if ( (unsigned __int16)archive_entry_filetype(v18) == 0x4000 )
        ++*a2[1];
    }
  }
}

```

## disassembly

```asm
0x1800613a0  mov     [rsp+arg_10], rbx
0x1800613a5  push    rsi
0x1800613a6  push    rdi
0x1800613a7  push    r14
0x1800613a9  sub     rsp, 50h
0x1800613ad  mov     rax, cs:__security_cookie
0x1800613b4  xor     rax, rsp
0x1800613b7  mov     [rsp+68h+var_28], rax
0x1800613bc  mov     r14, rdx
0x1800613bf  mov     rdi, rcx
0x1800613c2  call    cs:__imp_archive_read_new
0x1800613c8  mov     rbx, rax
0x1800613cb  mov     [rsp+68h+var_38], rax
0x1800613d0  mov     rcx, [rsp+68h]; this
0x1800613d5  test    rax, rax
0x1800613d8  jz      loc_18006161A
0x1800613de  mov     rdx, rdi; unsigned __int16 *
0x1800613e1  mov     rcx, rax; struct archive *
0x1800613e4  call    ?prepare_archive_reader@@YAXPEAUarchive@@PEBG@Z; prepare_archive_reader(archive *,ushort const *)
0x1800613e9  mov     r8d, 2800h
0x1800613ef  mov     rdx, rdi
0x1800613f2  mov     rcx, rbx
0x1800613f5  call    cs:__imp_archive_read_open_filename_w
0x1800613fb  test    eax, eax
0x1800613fd  jz      short loc_180061417
0x1800613ff  mov     rcx, rbx
0x180061402  call    cs:__imp_archive_errno
0x180061408  mov     ebx, eax
0x18006140a  test    eax, eax
0x18006140c  jnz     loc_180061558
0x180061412  jmp     loc_18006162C
0x180061417  mov     [rsp+68h+var_30], 0
0x180061420  xor     esi, esi
0x180061422  lea     rdx, [rsp+68h+var_30]
0x180061427  mov     rcx, rbx
0x18006142a  call    cs:__imp_archive_read_next_header
0x180061430  mov     edi, eax
0x180061432  cmp     eax, 1
0x180061435  jz      loc_18006150C
0x18006143b  cmp     eax, 0FFFFFFF6h
0x18006143e  jnz     short loc_18006145F
0x180061440  inc     esi
0x180061442  cmp     esi, 5
0x180061445  jbe     short loc_180061422
0x180061447  mov     rcx, rbx
0x18006144a  call    cs:__imp_archive_errno
0x180061450  mov     ebx, eax
0x180061452  test    eax, eax
0x180061454  jz      loc_1800615A7
0x18006145a  jmp     loc_180061650
0x18006145f  test    edi, edi
0x180061461  jz      short loc_1800614B7
0x180061463  cmp     edi, 0FFFFFFE2h
0x180061466  jnz     short loc_1800614B2
0x180061468  mov     rcx, rbx
0x18006146b  call    cs:__imp_archive_read_has_encrypted_entries
0x180061471  test    eax, eax
0x180061473  jg      loc_1800616AF
0x180061479  mov     rcx, rbx
0x18006147c  call    cs:__imp_archive_error_string
0x180061482  test    rax, rax
0x180061485  jz      short loc_1800614F7
0x180061487  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006148b  inc     r8; Size
0x18006148e  cmp     byte ptr [rax+r8], 0
0x180061493  jnz     short loc_18006148B
0x180061495  cmp     r8, 1Bh
0x180061499  jnz     short loc_1800614F7
0x18006149b  mov     rdx, cs:?EncryptedRAR@KnownArchiveErrors@@3V?$basic_string_view@DU?$char_traits@D@std@@@std@@B; Buf2
0x1800614a2  mov     rcx, rax; Buf1
0x1800614a5  call    memcmp_0
0x1800614aa  test    eax, eax
0x1800614ac  jz      loc_18006169F
0x1800614b2  cmp     edi, 0FFFFFFECh
0x1800614b5  jnz     short loc_1800614F7
0x1800614b7  xor     esi, esi
0x1800614b9  mov     rdi, [rsp+68h+var_30]
0x1800614be  mov     rax, [r14]
0x1800614c1  inc     qword ptr [rax]
0x1800614c4  mov     rcx, rdi
0x1800614c7  call    cs:__imp_archive_entry_size
0x1800614cd  mov     rdx, [r14]
0x1800614d0  add     [rdx+8], rax
0x1800614d4  mov     rcx, rdi
0x1800614d7  call    cs:__imp_archive_entry_filetype
0x1800614dd  mov     ecx, 4000h
0x1800614e2  cmp     ax, cx
0x1800614e5  jnz     loc_180061422
0x1800614eb  mov     rax, [r14+8]
0x1800614ef  inc     qword ptr [rax]
0x1800614f2  jmp     loc_180061422
0x1800614f7  mov     rcx, rbx
0x1800614fa  call    cs:__imp_archive_errno
0x180061500  mov     ebx, eax
0x180061502  test    eax, eax
0x180061504  jnz     loc_1800615CB
0x18006150a  jmp     short loc_180061534
0x18006150c  lea     rcx, [rsp+68h+var_38]
0x180061511  call    ??1?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(void)
0x180061516  mov     rcx, [rsp+68h+var_28]
0x18006151b  xor     rcx, rsp; StackCookie
0x18006151e  call    __security_check_cookie
0x180061523  mov     rbx, [rsp+68h+arg_10]
0x18006152b  add     rsp, 50h
0x18006152f  pop     r14
0x180061531  pop     rdi
0x180061532  pop     rsi
0x180061533  retn
0x180061534  mov     ecx, 80004005h
0x180061539  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18006153e  mov     r9d, eax; char *
0x180061541  mov     rcx, [rsp+68h]; this
0x180061546  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x18006154d  mov     edx, 1D0h; void *
0x180061552  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061558  lea     rcx, [rsp+68h+var_38]
0x18006155d  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x180061562  mov     rcx, rax
0x180061565  call    cs:__imp_archive_error_string
0x18006156b  mov     rdx, rax
0x18006156e  mov     ecx, ebx; int
0x180061570  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x180061575  mov     ecx, eax
0x180061577  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18006157c  mov     r9d, eax; char *
0x18006157f  mov     rcx, [rsp+68h]; this
0x180061584  mov     [rsp+68h+var_40], rdx; char *
0x180061589  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180061590  mov     qword ptr [rsp+68h+var_48], rax; int
0x180061595  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x18006159c  mov     edx, 199h; void *
0x1800615a1  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800615a7  mov     ecx, 80004005h
0x1800615ac  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800615b1  mov     r9d, eax; char *
0x1800615b4  mov     rcx, [rsp+68h]; this
0x1800615b9  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x1800615c0  mov     edx, 1A9h; void *
0x1800615c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800615cb  lea     rcx, [rsp+68h+var_38]
0x1800615d0  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x1800615d5  mov     rcx, rax
0x1800615d8  call    cs:__imp_archive_error_string
0x1800615de  mov     rdx, rax
0x1800615e1  mov     ecx, ebx; int
0x1800615e3  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x1800615e8  mov     ecx, eax
0x1800615ea  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800615ef  mov     r9d, eax; char *
0x1800615f2  mov     rcx, [rsp+68h]; this
0x1800615f7  mov     [rsp+68h+var_40], rdx; char *
0x1800615fc  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180061603  mov     qword ptr [rsp+68h+var_48], rax; int
0x180061608  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x18006160f  mov     edx, 1D0h; void *
0x180061614  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006161a  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061621  mov     edx, 195h; void *
0x180061626  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18006162c  mov     ecx, 80004005h
0x180061631  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061636  mov     r9d, eax; char *
0x180061639  mov     rcx, [rsp+68h]; this
0x18006163e  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061645  mov     edx, 199h; void *
0x18006164a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061650  lea     rcx, [rsp+68h+var_38]
0x180061655  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x18006165a  mov     rcx, rax
0x18006165d  call    cs:__imp_archive_error_string
0x180061663  mov     rdx, rax
0x180061666  mov     ecx, ebx; int
0x180061668  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x18006166d  mov     ecx, eax
0x18006166f  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061674  mov     r9d, eax; char *
0x180061677  mov     rcx, [rsp+68h]; this
0x18006167c  mov     [rsp+68h+var_40], rdx; char *
0x180061681  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180061688  mov     qword ptr [rsp+68h+var_48], rax; int
0x18006168d  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061694  mov     edx, 1A9h; void *
0x180061699  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006169f  mov     rcx, [rsp+68h]; this
0x1800616a4  mov     edx, 1C1h; void *
0x1800616a9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800616af  mov     rcx, [rsp+68h]; this
0x1800616b4  mov     edx, 1B5h; void *
0x1800616b9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
