# enumerate_archive__lambda_29e3a5b996ca071a98342c6046de9681_

- ea: `0x180054c60`
- end: `0x180054f70`
- name: `enumerate_archive__lambda_29e3a5b996ca071a98342c6046de9681___`
- size: `784`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e554`

## callees

- `0x180035418`
- `0x18003547c`
- `0x1800354bc`
- `0x1800354e0`
- `0x1800354fc`
- `0x180036f50`
- `0x1800390f1`
- `0x180054c60`
- `0x1800553e8`
- `0x180055f7c`
- `0x180055f9c`
- `0x180055fd4`
- `0x18005634c`

## import_xrefs

- `archiveint!archive_read_has_encrypted_entries` at `0x180054d37`
- `archiveint!archive_read_has_encrypted_entries` at `0x180054d37`
- `archiveint!archive_error_string` at `0x180054d48`
- `archiveint!archive_error_string` at `0x180054df2`
- `archiveint!archive_error_string` at `0x180054e41`
- `archiveint!archive_error_string` at `0x180054f0e`
- `archiveint!archive_error_string` at `0x180054d48`
- `archiveint!archive_error_string` at `0x180054df2`
- `archiveint!archive_error_string` at `0x180054e41`
- `archiveint!archive_error_string` at `0x180054f0e`
- `archiveint!archive_errno` at `0x180054cc7`
- `archiveint!archive_errno` at `0x180054d16`
- `archiveint!archive_errno` at `0x180054dd5`
- `archiveint!archive_errno` at `0x180054cc7`
- `archiveint!archive_errno` at `0x180054d16`
- `archiveint!archive_errno` at `0x180054dd5`
- `archiveint!archive_read_next_header` at `0x180054cf2`
- `archiveint!archive_read_next_header` at `0x180054cf2`
- `archiveint!archive_read_open_filename_w` at `0x180054cba`
- `archiveint!archive_read_open_filename_w` at `0x180054cba`
- `archiveint!archive_read_new` at `0x180054c87`
- `archiveint!archive_read_new` at `0x180054c87`

## string_xrefs

- `0x180054e22`: `shell\ext\zip\archive\precomp.h`
- `0x180054e71`: `shell\ext\zip\archive\precomp.h`
- `0x180054e95`: `shell\ext\zip\archive\precomp.h`
- `0x180054eb9`: `shell\ext\zip\archive\precomp.h`
- `0x180054ecb`: `shell\ext\zip\archive\precomp.h`
- `0x180054eef`: `shell\ext\zip\archive\precomp.h`
- `0x180054f3e`: `shell\ext\zip\archive\precomp.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall enumerate_archive__lambda_29e3a5b996ca071a98342c6046de9681_(unsigned __int16 *a1, __int64 a2)
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
        v9 = lambda_29e3a5b996ca071a98342c6046de9681_::operator()(a2, v6, v38);
      while ( v9 == 2 );
    }
  }
  while ( v9 != 1 );
  return wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(&v37);
}

```

## disassembly

```asm
0x180054c60  mov     [rsp+arg_10], rbx
0x180054c65  mov     [rsp+arg_18], rbp
0x180054c6a  push    rsi
0x180054c6b  push    rdi
0x180054c6c  push    r14
0x180054c6e  sub     rsp, 50h
0x180054c72  mov     rax, cs:__security_cookie
0x180054c79  xor     rax, rsp
0x180054c7c  mov     [rsp+68h+var_28], rax
0x180054c81  mov     r14, rdx
0x180054c84  mov     rdi, rcx
0x180054c87  call    cs:__imp_archive_read_new
0x180054c8d  mov     rbx, rax
0x180054c90  mov     [rsp+68h+var_38], rax
0x180054c95  mov     rcx, [rsp+68h]; this
0x180054c9a  test    rax, rax
0x180054c9d  jz      loc_180054ECB
0x180054ca3  mov     rdx, rdi; unsigned __int16 *
0x180054ca6  mov     rcx, rax; struct archive *
0x180054ca9  call    ?prepare_archive_reader@@YAXPEAUarchive@@PEBG@Z; prepare_archive_reader(archive *,ushort const *)
0x180054cae  mov     r8d, 2800h
0x180054cb4  mov     rdx, rdi
0x180054cb7  mov     rcx, rbx
0x180054cba  call    cs:__imp_archive_read_open_filename_w
0x180054cc0  test    eax, eax
0x180054cc2  jz      short loc_180054CDC
0x180054cc4  mov     rcx, rbx
0x180054cc7  call    cs:__imp_archive_errno
0x180054ccd  mov     ebx, eax
0x180054ccf  test    eax, eax
0x180054cd1  jnz     loc_180054E34
0x180054cd7  jmp     loc_180054EDD
0x180054cdc  mov     [rsp+68h+var_30], 0
0x180054ce5  xor     esi, esi
0x180054ce7  xor     bpl, bpl
0x180054cea  lea     rdx, [rsp+68h+var_30]
0x180054cef  mov     rcx, rbx
0x180054cf2  call    cs:__imp_archive_read_next_header
0x180054cf8  mov     edi, eax
0x180054cfa  cmp     eax, 1
0x180054cfd  jz      loc_180054DA6
0x180054d03  cmp     eax, 0FFFFFFF6h
0x180054d06  jnz     short loc_180054D2B
0x180054d08  inc     esi
0x180054d0a  cmp     esi, 5
0x180054d0d  jbe     loc_180054D9C
0x180054d13  mov     rcx, rbx
0x180054d16  call    cs:__imp_archive_errno
0x180054d1c  mov     ebx, eax
0x180054d1e  test    eax, eax
0x180054d20  jz      loc_180054E83
0x180054d26  jmp     loc_180054F01
0x180054d2b  test    edi, edi
0x180054d2d  jz      short loc_180054D83
0x180054d2f  cmp     edi, 0FFFFFFE2h
0x180054d32  jnz     short loc_180054D7E
0x180054d34  mov     rcx, rbx
0x180054d37  call    cs:__imp_archive_read_has_encrypted_entries
0x180054d3d  test    eax, eax
0x180054d3f  jg      loc_180054F60
0x180054d45  mov     rcx, rbx
0x180054d48  call    cs:__imp_archive_error_string
0x180054d4e  test    rax, rax
0x180054d51  jz      short loc_180054DD2
0x180054d53  or      r8, 0FFFFFFFFFFFFFFFFh
0x180054d57  inc     r8; Size
0x180054d5a  cmp     byte ptr [rax+r8], 0
0x180054d5f  jnz     short loc_180054D57
0x180054d61  cmp     r8, 1Bh
0x180054d65  jnz     short loc_180054DD2
0x180054d67  mov     rdx, cs:?EncryptedRAR@KnownArchiveErrors@@3V?$basic_string_view@DU?$char_traits@D@std@@@std@@B; Buf2
0x180054d6e  mov     rcx, rax; Buf1
0x180054d71  call    memcmp_0
0x180054d76  test    eax, eax
0x180054d78  jz      loc_180054F50
0x180054d7e  cmp     edi, 0FFFFFFECh
0x180054d81  jnz     short loc_180054DD2
0x180054d83  xor     esi, esi
0x180054d85  mov     r8, [rsp+68h+var_30]
0x180054d8a  mov     rdx, rbx
0x180054d8d  mov     rcx, r14
0x180054d90  call    _lambda_29e3a5b996ca071a98342c6046de9681___operator__
0x180054d95  mov     bpl, al
0x180054d98  cmp     al, 2
0x180054d9a  jz      short loc_180054D85
0x180054d9c  cmp     bpl, 1
0x180054da0  jnz     loc_180054CEA
0x180054da6  lea     rcx, [rsp+68h+var_38]
0x180054dab  call    ??1?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(void)
0x180054db0  mov     rcx, [rsp+68h+var_28]
0x180054db5  xor     rcx, rsp; StackCookie
0x180054db8  call    __security_check_cookie
0x180054dbd  lea     r11, [rsp+68h+var_18]
0x180054dc2  mov     rbx, [r11+30h]
0x180054dc6  mov     rbp, [r11+38h]
0x180054dca  mov     rsp, r11
0x180054dcd  pop     r14
0x180054dcf  pop     rdi
0x180054dd0  pop     rsi
0x180054dd1  retn
0x180054dd2  mov     rcx, rbx
0x180054dd5  call    cs:__imp_archive_errno
0x180054ddb  mov     ebx, eax
0x180054ddd  test    eax, eax
0x180054ddf  jz      loc_180054EA7
0x180054de5  lea     rcx, [rsp+68h+var_38]
0x180054dea  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x180054def  mov     rcx, rax
0x180054df2  call    cs:__imp_archive_error_string
0x180054df8  mov     rdx, rax
0x180054dfb  mov     ecx, ebx; int
0x180054dfd  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x180054e02  mov     ecx, eax
0x180054e04  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180054e09  mov     r9d, eax; char *
0x180054e0c  mov     rcx, [rsp+68h]; this
0x180054e11  mov     [rsp+68h+var_40], rdx; char *
0x180054e16  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180054e1d  mov     qword ptr [rsp+68h+var_48], rax; int
0x180054e22  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180054e29  mov     edx, 1D0h; void *
0x180054e2e  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180054e34  lea     rcx, [rsp+68h+var_38]
0x180054e39  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x180054e3e  mov     rcx, rax
0x180054e41  call    cs:__imp_archive_error_string
0x180054e47  mov     rdx, rax
0x180054e4a  mov     ecx, ebx; int
0x180054e4c  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x180054e51  mov     ecx, eax
0x180054e53  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180054e58  mov     r9d, eax; char *
0x180054e5b  mov     rcx, [rsp+68h]; this
0x180054e60  mov     [rsp+68h+var_40], rdx; char *
0x180054e65  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180054e6c  mov     qword ptr [rsp+68h+var_48], rax; int
0x180054e71  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180054e78  mov     edx, 199h; void *
0x180054e7d  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180054e83  mov     ecx, 80004005h
0x180054e88  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180054e8d  mov     r9d, eax; char *
0x180054e90  mov     rcx, [rsp+68h]; this
0x180054e95  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180054e9c  mov     edx, 1A9h; void *
0x180054ea1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054ea7  mov     ecx, 80004005h
0x180054eac  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180054eb1  mov     r9d, eax; char *
0x180054eb4  mov     rcx, [rsp+68h]; this
0x180054eb9  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180054ec0  mov     edx, 1D0h; void *
0x180054ec5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054ecb  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180054ed2  mov     edx, 195h; void *
0x180054ed7  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180054edd  mov     ecx, 80004005h
0x180054ee2  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180054ee7  mov     r9d, eax; char *
0x180054eea  mov     rcx, [rsp+68h]; this
0x180054eef  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180054ef6  mov     edx, 199h; void *
0x180054efb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054f01  lea     rcx, [rsp+68h+var_38]
0x180054f06  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x180054f0b  mov     rcx, rax
0x180054f0e  call    cs:__imp_archive_error_string
0x180054f14  mov     rdx, rax
0x180054f17  mov     ecx, ebx; int
0x180054f19  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x180054f1e  mov     ecx, eax
0x180054f20  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180054f25  mov     r9d, eax; char *
0x180054f28  mov     rcx, [rsp+68h]; this
0x180054f2d  mov     [rsp+68h+var_40], rdx; char *
0x180054f32  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180054f39  mov     qword ptr [rsp+68h+var_48], rax; int
0x180054f3e  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180054f45  mov     edx, 1A9h; void *
0x180054f4a  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180054f50  mov     rcx, [rsp+68h]; this
0x180054f55  mov     edx, 1C1h; void *
0x180054f5a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180054f60  mov     rcx, [rsp+68h]; this
0x180054f65  mov     edx, 1B5h; void *
0x180054f6a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
