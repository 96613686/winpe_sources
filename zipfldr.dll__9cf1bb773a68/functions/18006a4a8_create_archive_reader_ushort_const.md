# create_archive_reader(ushort const *)

- ea: `0x18006a4a8`
- end: `0x18006a5a7`
- name: `?create_archive_reader@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006a340`

## callees

- `0x18003547c`
- `0x1800354bc`
- `0x1800354e0`
- `0x1800354fc`
- `0x180055f7c`
- `0x180055f9c`
- `0x18005634c`
- `0x18006a4a8`

## import_xrefs

- `archiveint!archive_error_string` at `0x18006a553`
- `archiveint!archive_error_string` at `0x18006a553`
- `archiveint!archive_errno` at `0x18006a508`
- `archiveint!archive_errno` at `0x18006a508`
- `archiveint!archive_read_open_filename_w` at `0x18006a4fb`
- `archiveint!archive_read_open_filename_w` at `0x18006a4fb`
- `archiveint!archive_read_new` at `0x18006a4c5`
- `archiveint!archive_read_new` at `0x18006a4c5`

## string_xrefs

- `0x18006a536`: `shell\ext\zip\archive\precomp.h`
- `0x18006a583`: `shell\ext\zip\archive\precomp.h`
- `0x18006a595`: `shell\ext\zip\archive\precomp.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct archive **__fastcall create_archive_reader(struct archive **a1, const unsigned __int16 *a2)
{
  struct archive *v4; // rax
  const char *v5; // r9
  int v6; // edi
  unsigned int v8; // eax
  __int64 v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // eax
  const char *v12; // rdx
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = (struct archive *)archive_read_new();
  *a1 = v4;
  if ( !v4 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x13A,
      (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
      v5);
  prepare_archive_reader(v4, a2);
  if ( (unsigned int)archive_read_open_filename_w(*a1, a2, 10240) )
  {
    v6 = archive_errno(*a1);
    if ( !v6 )
    {
      v8 = wil::verify_hresult<long>(2147500037LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13E,
        (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
        (const char *)v8,
        v13);
    }
    v9 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(a1);
    archive_error_string(v9);
    v10 = HRESULT_FROM_ERRNO(v6);
    v11 = wil::verify_hresult<long>(v10);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x13E,
      (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
      (const char *)v11,
      (int)"archive error: %hs",
      v12,
      1);
  }
  return a1;
}

```

## disassembly

```asm
0x18006a4a8  mov     [rsp+arg_8], rbx
0x18006a4ad  mov     [rsp+arg_0], rcx
0x18006a4b2  push    rdi
0x18006a4b3  sub     rsp, 40h
0x18006a4b7  mov     rdi, rdx
0x18006a4ba  mov     rbx, rcx
0x18006a4bd  mov     [rsp+48h+var_18], 0
0x18006a4c5  call    cs:__imp_archive_read_new
0x18006a4cb  mov     [rbx], rax
0x18006a4ce  mov     [rsp+48h+var_18], 1
0x18006a4d6  mov     rcx, [rsp+48h]; this
0x18006a4db  test    rax, rax
0x18006a4de  jz      loc_18006A595
0x18006a4e4  mov     rdx, rdi; unsigned __int16 *
0x18006a4e7  mov     rcx, rax; struct archive *
0x18006a4ea  call    ?prepare_archive_reader@@YAXPEAUarchive@@PEBG@Z; prepare_archive_reader(archive *,ushort const *)
0x18006a4ef  mov     r8d, 2800h
0x18006a4f5  mov     rdx, rdi
0x18006a4f8  mov     rcx, [rbx]
0x18006a4fb  call    cs:__imp_archive_read_open_filename_w
0x18006a501  test    eax, eax
0x18006a503  jz      short loc_18006A516
0x18006a505  mov     rcx, [rbx]
0x18006a508  call    cs:__imp_archive_errno
0x18006a50e  mov     edi, eax
0x18006a510  test    eax, eax
0x18006a512  jnz     short loc_18006A548
0x18006a514  jmp     short loc_18006A524
0x18006a516  mov     rax, rbx
0x18006a519  mov     rbx, [rsp+48h+arg_8]
0x18006a51e  add     rsp, 40h
0x18006a522  pop     rdi
0x18006a523  retn
0x18006a524  mov     ecx, 80004005h
0x18006a529  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18006a52e  mov     r9d, eax; char *
0x18006a531  mov     rcx, [rsp+48h]; this
0x18006a536  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x18006a53d  mov     edx, 13Eh; void *
0x18006a542  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a548  mov     rcx, rbx
0x18006a54b  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUarchive@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>>::get(void)
0x18006a550  mov     rcx, rax
0x18006a553  call    cs:__imp_archive_error_string
0x18006a559  mov     rdx, rax
0x18006a55c  mov     ecx, edi; int
0x18006a55e  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x18006a563  mov     ecx, eax
0x18006a565  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18006a56a  mov     r9d, eax; char *
0x18006a56d  mov     rcx, [rsp+48h]; this
0x18006a572  mov     [rsp+48h+var_20], rdx; char *
0x18006a577  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x18006a57e  mov     qword ptr [rsp+48h+var_28], rax; int
0x18006a583  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x18006a58a  mov     edx, 13Eh; void *
0x18006a58f  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006a595  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x18006a59c  mov     edx, 13Ah; void *
0x18006a5a1  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
