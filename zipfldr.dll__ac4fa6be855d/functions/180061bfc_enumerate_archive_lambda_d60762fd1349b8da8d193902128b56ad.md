# enumerate_archive__lambda_d60762fd1349b8da8d193902128b56ad_

- ea: `0x180061bfc`
- end: `0x180061f0c`
- name: `enumerate_archive__lambda_d60762fd1349b8da8d193902128b56ad___`
- size: `784`
- prototype: `__int64 __fastcall(unsigned __int16 *, int **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180065780`

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
- `0x180061bfc`
- `0x18006442c`

## import_xrefs

- `archiveint!archive_read_has_encrypted_entries` at `0x180061cd3`
- `archiveint!archive_read_has_encrypted_entries` at `0x180061cd3`
- `archiveint!archive_error_string` at `0x180061ce4`
- `archiveint!archive_error_string` at `0x180061d8e`
- `archiveint!archive_error_string` at `0x180061ddd`
- `archiveint!archive_error_string` at `0x180061eaa`
- `archiveint!archive_error_string` at `0x180061ce4`
- `archiveint!archive_error_string` at `0x180061d8e`
- `archiveint!archive_error_string` at `0x180061ddd`
- `archiveint!archive_error_string` at `0x180061eaa`
- `archiveint!archive_errno` at `0x180061c63`
- `archiveint!archive_errno` at `0x180061cb2`
- `archiveint!archive_errno` at `0x180061d71`
- `archiveint!archive_errno` at `0x180061c63`
- `archiveint!archive_errno` at `0x180061cb2`
- `archiveint!archive_errno` at `0x180061d71`
- `archiveint!archive_read_next_header` at `0x180061c8e`
- `archiveint!archive_read_next_header` at `0x180061c8e`
- `archiveint!archive_read_open_filename_w` at `0x180061c56`
- `archiveint!archive_read_open_filename_w` at `0x180061c56`
- `archiveint!archive_read_new` at `0x180061c23`
- `archiveint!archive_read_new` at `0x180061c23`

## string_xrefs

- `0x180061dbe`: `shell\ext\zip\archive\precomp.h`
- `0x180061e0d`: `shell\ext\zip\archive\precomp.h`
- `0x180061e31`: `shell\ext\zip\archive\precomp.h`
- `0x180061e55`: `shell\ext\zip\archive\precomp.h`
- `0x180061e67`: `shell\ext\zip\archive\precomp.h`
- `0x180061e8b`: `shell\ext\zip\archive\precomp.h`
- `0x180061eda`: `shell\ext\zip\archive\precomp.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall enumerate_archive__lambda_d60762fd1349b8da8d193902128b56ad_(unsigned __int16 *a1, int **a2)
{
  struct archive *v4; // rax
  const char *v5; // r9
  __int64 v6; // rbx
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
  v6 = (__int64)v4;
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
        v9 = lambda_d60762fd1349b8da8d193902128b56ad_::operator()(a2, v6, v38);
      while ( v9 == 2 );
    }
  }
  while ( v9 != 1 );
  return wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(&v37);
}

```

## disassembly

```asm
0x180061bfc  mov     [rsp+arg_10], rbx
0x180061c01  mov     [rsp+arg_18], rbp
0x180061c06  push    rsi
0x180061c07  push    rdi
0x180061c08  push    r14
0x180061c0a  sub     rsp, 50h
0x180061c0e  mov     rax, cs:__security_cookie
0x180061c15  xor     rax, rsp
0x180061c18  mov     [rsp+68h+var_28], rax
0x180061c1d  mov     r14, rdx
0x180061c20  mov     rdi, rcx
0x180061c23  call    cs:__imp_archive_read_new
0x180061c29  mov     rbx, rax
0x180061c2c  mov     [rsp+68h+var_38], rax
0x180061c31  mov     rcx, [rsp+68h]; this
0x180061c36  test    rax, rax
0x180061c39  jz      loc_180061E67
0x180061c3f  mov     rdx, rdi; unsigned __int16 *
0x180061c42  mov     rcx, rax; struct archive *
0x180061c45  call    ?prepare_archive_reader@@YAXPEAUarchive@@PEBG@Z; prepare_archive_reader(archive *,ushort const *)
0x180061c4a  mov     r8d, 2800h
0x180061c50  mov     rdx, rdi
0x180061c53  mov     rcx, rbx
0x180061c56  call    cs:__imp_archive_read_open_filename_w
0x180061c5c  test    eax, eax
0x180061c5e  jz      short loc_180061C78
0x180061c60  mov     rcx, rbx
0x180061c63  call    cs:__imp_archive_errno
0x180061c69  mov     ebx, eax
0x180061c6b  test    eax, eax
0x180061c6d  jnz     loc_180061DD0
0x180061c73  jmp     loc_180061E79
0x180061c78  mov     [rsp+68h+var_30], 0
0x180061c81  xor     esi, esi
0x180061c83  xor     bpl, bpl
0x180061c86  lea     rdx, [rsp+68h+var_30]
0x180061c8b  mov     rcx, rbx
0x180061c8e  call    cs:__imp_archive_read_next_header
0x180061c94  mov     edi, eax
0x180061c96  cmp     eax, 1
0x180061c99  jz      loc_180061D42
0x180061c9f  cmp     eax, 0FFFFFFF6h
0x180061ca2  jnz     short loc_180061CC7
0x180061ca4  inc     esi
0x180061ca6  cmp     esi, 5
0x180061ca9  jbe     loc_180061D38
0x180061caf  mov     rcx, rbx
0x180061cb2  call    cs:__imp_archive_errno
0x180061cb8  mov     ebx, eax
0x180061cba  test    eax, eax
0x180061cbc  jz      loc_180061E1F
0x180061cc2  jmp     loc_180061E9D
0x180061cc7  test    edi, edi
0x180061cc9  jz      short loc_180061D1F
0x180061ccb  cmp     edi, 0FFFFFFE2h
0x180061cce  jnz     short loc_180061D1A
0x180061cd0  mov     rcx, rbx
0x180061cd3  call    cs:__imp_archive_read_has_encrypted_entries
0x180061cd9  test    eax, eax
0x180061cdb  jg      loc_180061EFC
0x180061ce1  mov     rcx, rbx
0x180061ce4  call    cs:__imp_archive_error_string
0x180061cea  test    rax, rax
0x180061ced  jz      short loc_180061D6E
0x180061cef  or      r8, 0FFFFFFFFFFFFFFFFh
0x180061cf3  inc     r8; Size
0x180061cf6  cmp     byte ptr [rax+r8], 0
0x180061cfb  jnz     short loc_180061CF3
0x180061cfd  cmp     r8, 1Bh
0x180061d01  jnz     short loc_180061D6E
0x180061d03  mov     rdx, cs:?EncryptedRAR@KnownArchiveErrors@@3V?$basic_string_view@DU?$char_traits@D@std@@@std@@B; Buf2
0x180061d0a  mov     rcx, rax; Buf1
0x180061d0d  call    memcmp_0
0x180061d12  test    eax, eax
0x180061d14  jz      loc_180061EEC
0x180061d1a  cmp     edi, 0FFFFFFECh
0x180061d1d  jnz     short loc_180061D6E
0x180061d1f  xor     esi, esi
0x180061d21  mov     r8, [rsp+68h+var_30]
0x180061d26  mov     rdx, rbx
0x180061d29  mov     rcx, r14
0x180061d2c  call    _lambda_d60762fd1349b8da8d193902128b56ad___operator__
0x180061d31  mov     bpl, al
0x180061d34  cmp     al, 2
0x180061d36  jz      short loc_180061D21
0x180061d38  cmp     bpl, 1
0x180061d3c  jnz     loc_180061C86
0x180061d42  lea     rcx, [rsp+68h+var_38]
0x180061d47  call    ??1?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(void)
0x180061d4c  mov     rcx, [rsp+68h+var_28]
0x180061d51  xor     rcx, rsp; StackCookie
0x180061d54  call    __security_check_cookie
0x180061d59  lea     r11, [rsp+68h+var_18]
0x180061d5e  mov     rbx, [r11+30h]
0x180061d62  mov     rbp, [r11+38h]
0x180061d66  mov     rsp, r11
0x180061d69  pop     r14
0x180061d6b  pop     rdi
0x180061d6c  pop     rsi
0x180061d6d  retn
0x180061d6e  mov     rcx, rbx
0x180061d71  call    cs:__imp_archive_errno
0x180061d77  mov     ebx, eax
0x180061d79  test    eax, eax
0x180061d7b  jz      loc_180061E43
0x180061d81  lea     rcx, [rsp+68h+var_38]
0x180061d86  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x180061d8b  mov     rcx, rax
0x180061d8e  call    cs:__imp_archive_error_string
0x180061d94  mov     rdx, rax
0x180061d97  mov     ecx, ebx; int
0x180061d99  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x180061d9e  mov     ecx, eax
0x180061da0  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061da5  mov     r9d, eax; char *
0x180061da8  mov     rcx, [rsp+68h]; this
0x180061dad  mov     [rsp+68h+var_40], rdx; char *
0x180061db2  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180061db9  mov     qword ptr [rsp+68h+var_48], rax; int
0x180061dbe  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061dc5  mov     edx, 1D0h; void *
0x180061dca  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180061dd0  lea     rcx, [rsp+68h+var_38]
0x180061dd5  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x180061dda  mov     rcx, rax
0x180061ddd  call    cs:__imp_archive_error_string
0x180061de3  mov     rdx, rax
0x180061de6  mov     ecx, ebx; int
0x180061de8  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x180061ded  mov     ecx, eax
0x180061def  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061df4  mov     r9d, eax; char *
0x180061df7  mov     rcx, [rsp+68h]; this
0x180061dfc  mov     [rsp+68h+var_40], rdx; char *
0x180061e01  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180061e08  mov     qword ptr [rsp+68h+var_48], rax; int
0x180061e0d  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061e14  mov     edx, 199h; void *
0x180061e19  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180061e1f  mov     ecx, 80004005h
0x180061e24  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061e29  mov     r9d, eax; char *
0x180061e2c  mov     rcx, [rsp+68h]; this
0x180061e31  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061e38  mov     edx, 1A9h; void *
0x180061e3d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061e43  mov     ecx, 80004005h
0x180061e48  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061e4d  mov     r9d, eax; char *
0x180061e50  mov     rcx, [rsp+68h]; this
0x180061e55  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061e5c  mov     edx, 1D0h; void *
0x180061e61  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061e67  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061e6e  mov     edx, 195h; void *
0x180061e73  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180061e79  mov     ecx, 80004005h
0x180061e7e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061e83  mov     r9d, eax; char *
0x180061e86  mov     rcx, [rsp+68h]; this
0x180061e8b  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061e92  mov     edx, 199h; void *
0x180061e97  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061e9d  lea     rcx, [rsp+68h+var_38]
0x180061ea2  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x180061ea7  mov     rcx, rax
0x180061eaa  call    cs:__imp_archive_error_string
0x180061eb0  mov     rdx, rax
0x180061eb3  mov     ecx, ebx; int
0x180061eb5  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x180061eba  mov     ecx, eax
0x180061ebc  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061ec1  mov     r9d, eax; char *
0x180061ec4  mov     rcx, [rsp+68h]; this
0x180061ec9  mov     [rsp+68h+var_40], rdx; char *
0x180061ece  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180061ed5  mov     qword ptr [rsp+68h+var_48], rax; int
0x180061eda  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061ee1  mov     edx, 1A9h; void *
0x180061ee6  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180061eec  mov     rcx, [rsp+68h]; this
0x180061ef1  mov     edx, 1C1h; void *
0x180061ef6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180061efc  mov     rcx, [rsp+68h]; this
0x180061f01  mov     edx, 1B5h; void *
0x180061f06  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
