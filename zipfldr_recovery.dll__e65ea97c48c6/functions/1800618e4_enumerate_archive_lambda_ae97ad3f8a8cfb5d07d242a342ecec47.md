# enumerate_archive__lambda_ae97ad3f8a8cfb5d07d242a342ecec47_

- ea: `0x1800618e4`
- end: `0x180061bf4`
- name: `enumerate_archive__lambda_ae97ad3f8a8cfb5d07d242a342ecec47___`
- size: `784`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800652fc`

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
- `0x1800618e4`
- `0x18006408c`

## import_xrefs

- `archiveint!archive_read_has_encrypted_entries` at `0x1800619bb`
- `archiveint!archive_read_has_encrypted_entries` at `0x1800619bb`
- `archiveint!archive_error_string` at `0x1800619cc`
- `archiveint!archive_error_string` at `0x180061a76`
- `archiveint!archive_error_string` at `0x180061ac5`
- `archiveint!archive_error_string` at `0x180061b92`
- `archiveint!archive_error_string` at `0x1800619cc`
- `archiveint!archive_error_string` at `0x180061a76`
- `archiveint!archive_error_string` at `0x180061ac5`
- `archiveint!archive_error_string` at `0x180061b92`
- `archiveint!archive_errno` at `0x18006194b`
- `archiveint!archive_errno` at `0x18006199a`
- `archiveint!archive_errno` at `0x180061a59`
- `archiveint!archive_errno` at `0x18006194b`
- `archiveint!archive_errno` at `0x18006199a`
- `archiveint!archive_errno` at `0x180061a59`
- `archiveint!archive_read_next_header` at `0x180061976`
- `archiveint!archive_read_next_header` at `0x180061976`
- `archiveint!archive_read_open_filename_w` at `0x18006193e`
- `archiveint!archive_read_open_filename_w` at `0x18006193e`
- `archiveint!archive_read_new` at `0x18006190b`
- `archiveint!archive_read_new` at `0x18006190b`

## string_xrefs

- `0x180061aa6`: `shell\ext\zip\archive\precomp.h`
- `0x180061af5`: `shell\ext\zip\archive\precomp.h`
- `0x180061b19`: `shell\ext\zip\archive\precomp.h`
- `0x180061b3d`: `shell\ext\zip\archive\precomp.h`
- `0x180061b4f`: `shell\ext\zip\archive\precomp.h`
- `0x180061b73`: `shell\ext\zip\archive\precomp.h`
- `0x180061bc2`: `shell\ext\zip\archive\precomp.h`

## pseudocode

```c
__int64 __fastcall enumerate_archive__lambda_ae97ad3f8a8cfb5d07d242a342ecec47_(unsigned __int16 *a1, __int64 a2)
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
        v9 = lambda_ae97ad3f8a8cfb5d07d242a342ecec47_::operator()(a2, v6, v38);
      while ( v9 == 2 );
    }
  }
  while ( v9 != 1 );
  return wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(&v37);
}

```

## disassembly

```asm
0x1800618e4  mov     [rsp+arg_10], rbx
0x1800618e9  mov     [rsp+arg_18], rbp
0x1800618ee  push    rsi
0x1800618ef  push    rdi
0x1800618f0  push    r14
0x1800618f2  sub     rsp, 50h
0x1800618f6  mov     rax, cs:__security_cookie
0x1800618fd  xor     rax, rsp
0x180061900  mov     [rsp+68h+var_28], rax
0x180061905  mov     r14, rdx
0x180061908  mov     rdi, rcx
0x18006190b  call    cs:__imp_archive_read_new
0x180061911  mov     rbx, rax
0x180061914  mov     [rsp+68h+var_38], rax
0x180061919  mov     rcx, [rsp+68h]; this
0x18006191e  test    rax, rax
0x180061921  jz      loc_180061B4F
0x180061927  mov     rdx, rdi; unsigned __int16 *
0x18006192a  mov     rcx, rax; struct archive *
0x18006192d  call    ?prepare_archive_reader@@YAXPEAUarchive@@PEBG@Z; prepare_archive_reader(archive *,ushort const *)
0x180061932  mov     r8d, 2800h
0x180061938  mov     rdx, rdi
0x18006193b  mov     rcx, rbx
0x18006193e  call    cs:__imp_archive_read_open_filename_w
0x180061944  test    eax, eax
0x180061946  jz      short loc_180061960
0x180061948  mov     rcx, rbx
0x18006194b  call    cs:__imp_archive_errno
0x180061951  mov     ebx, eax
0x180061953  test    eax, eax
0x180061955  jnz     loc_180061AB8
0x18006195b  jmp     loc_180061B61
0x180061960  mov     [rsp+68h+var_30], 0
0x180061969  xor     esi, esi
0x18006196b  xor     bpl, bpl
0x18006196e  lea     rdx, [rsp+68h+var_30]
0x180061973  mov     rcx, rbx
0x180061976  call    cs:__imp_archive_read_next_header
0x18006197c  mov     edi, eax
0x18006197e  cmp     eax, 1
0x180061981  jz      loc_180061A2A
0x180061987  cmp     eax, 0FFFFFFF6h
0x18006198a  jnz     short loc_1800619AF
0x18006198c  inc     esi
0x18006198e  cmp     esi, 5
0x180061991  jbe     loc_180061A20
0x180061997  mov     rcx, rbx
0x18006199a  call    cs:__imp_archive_errno
0x1800619a0  mov     ebx, eax
0x1800619a2  test    eax, eax
0x1800619a4  jz      loc_180061B07
0x1800619aa  jmp     loc_180061B85
0x1800619af  test    edi, edi
0x1800619b1  jz      short loc_180061A07
0x1800619b3  cmp     edi, 0FFFFFFE2h
0x1800619b6  jnz     short loc_180061A02
0x1800619b8  mov     rcx, rbx
0x1800619bb  call    cs:__imp_archive_read_has_encrypted_entries
0x1800619c1  test    eax, eax
0x1800619c3  jg      loc_180061BE4
0x1800619c9  mov     rcx, rbx
0x1800619cc  call    cs:__imp_archive_error_string
0x1800619d2  test    rax, rax
0x1800619d5  jz      short loc_180061A56
0x1800619d7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800619db  inc     r8; Size
0x1800619de  cmp     byte ptr [rax+r8], 0
0x1800619e3  jnz     short loc_1800619DB
0x1800619e5  cmp     r8, 1Bh
0x1800619e9  jnz     short loc_180061A56
0x1800619eb  mov     rdx, cs:?EncryptedRAR@KnownArchiveErrors@@3V?$basic_string_view@DU?$char_traits@D@std@@@std@@B; Buf2
0x1800619f2  mov     rcx, rax; Buf1
0x1800619f5  call    memcmp_0
0x1800619fa  test    eax, eax
0x1800619fc  jz      loc_180061BD4
0x180061a02  cmp     edi, 0FFFFFFECh
0x180061a05  jnz     short loc_180061A56
0x180061a07  xor     esi, esi
0x180061a09  mov     r8, [rsp+68h+var_30]
0x180061a0e  mov     rdx, rbx
0x180061a11  mov     rcx, r14
0x180061a14  call    _lambda_ae97ad3f8a8cfb5d07d242a342ecec47___operator__
0x180061a19  mov     bpl, al
0x180061a1c  cmp     al, 2
0x180061a1e  jz      short loc_180061A09
0x180061a20  cmp     bpl, 1
0x180061a24  jnz     loc_18006196E
0x180061a2a  lea     rcx, [rsp+68h+var_38]
0x180061a2f  call    ??1?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(void)
0x180061a34  mov     rcx, [rsp+68h+var_28]
0x180061a39  xor     rcx, rsp; StackCookie
0x180061a3c  call    __security_check_cookie
0x180061a41  lea     r11, [rsp+68h+var_18]
0x180061a46  mov     rbx, [r11+30h]
0x180061a4a  mov     rbp, [r11+38h]
0x180061a4e  mov     rsp, r11
0x180061a51  pop     r14
0x180061a53  pop     rdi
0x180061a54  pop     rsi
0x180061a55  retn
0x180061a56  mov     rcx, rbx
0x180061a59  call    cs:__imp_archive_errno
0x180061a5f  mov     ebx, eax
0x180061a61  test    eax, eax
0x180061a63  jz      loc_180061B2B
0x180061a69  lea     rcx, [rsp+68h+var_38]
0x180061a6e  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x180061a73  mov     rcx, rax
0x180061a76  call    cs:__imp_archive_error_string
0x180061a7c  mov     rdx, rax
0x180061a7f  mov     ecx, ebx; int
0x180061a81  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x180061a86  mov     ecx, eax
0x180061a88  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061a8d  mov     r9d, eax; char *
0x180061a90  mov     rcx, [rsp+68h]; this
0x180061a95  mov     [rsp+68h+var_40], rdx; char *
0x180061a9a  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180061aa1  mov     qword ptr [rsp+68h+var_48], rax; int
0x180061aa6  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061aad  mov     edx, 1D0h; void *
0x180061ab2  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180061ab8  lea     rcx, [rsp+68h+var_38]
0x180061abd  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x180061ac2  mov     rcx, rax
0x180061ac5  call    cs:__imp_archive_error_string
0x180061acb  mov     rdx, rax
0x180061ace  mov     ecx, ebx; int
0x180061ad0  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x180061ad5  mov     ecx, eax
0x180061ad7  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061adc  mov     r9d, eax; char *
0x180061adf  mov     rcx, [rsp+68h]; this
0x180061ae4  mov     [rsp+68h+var_40], rdx; char *
0x180061ae9  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180061af0  mov     qword ptr [rsp+68h+var_48], rax; int
0x180061af5  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061afc  mov     edx, 199h; void *
0x180061b01  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180061b07  mov     ecx, 80004005h
0x180061b0c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061b11  mov     r9d, eax; char *
0x180061b14  mov     rcx, [rsp+68h]; this
0x180061b19  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061b20  mov     edx, 1A9h; void *
0x180061b25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061b2b  mov     ecx, 80004005h
0x180061b30  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061b35  mov     r9d, eax; char *
0x180061b38  mov     rcx, [rsp+68h]; this
0x180061b3d  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061b44  mov     edx, 1D0h; void *
0x180061b49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061b4f  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061b56  mov     edx, 195h; void *
0x180061b5b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180061b61  mov     ecx, 80004005h
0x180061b66  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061b6b  mov     r9d, eax; char *
0x180061b6e  mov     rcx, [rsp+68h]; this
0x180061b73  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061b7a  mov     edx, 199h; void *
0x180061b7f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061b85  lea     rcx, [rsp+68h+var_38]
0x180061b8a  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x180061b8f  mov     rcx, rax
0x180061b92  call    cs:__imp_archive_error_string
0x180061b98  mov     rdx, rax
0x180061b9b  mov     ecx, ebx; int
0x180061b9d  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x180061ba2  mov     ecx, eax
0x180061ba4  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061ba9  mov     r9d, eax; char *
0x180061bac  mov     rcx, [rsp+68h]; this
0x180061bb1  mov     [rsp+68h+var_40], rdx; char *
0x180061bb6  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180061bbd  mov     qword ptr [rsp+68h+var_48], rax; int
0x180061bc2  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061bc9  mov     edx, 1A9h; void *
0x180061bce  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180061bd4  mov     rcx, [rsp+68h]; this
0x180061bd9  mov     edx, 1C1h; void *
0x180061bde  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180061be4  mov     rcx, [rsp+68h]; this
0x180061be9  mov     edx, 1B5h; void *
0x180061bee  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
