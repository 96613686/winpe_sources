# enumerate_archive__lambda_70f2a6337c3fbeddb77c614144e09a12_

- ea: `0x1800616c8`
- end: `0x1800618db`
- name: `enumerate_archive__lambda_70f2a6337c3fbeddb77c614144e09a12___`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800656dc`

## callees

- `0x18003547c`
- `0x1800354e0`
- `0x180036f50`
- `0x1800390f1`
- `0x180055f7c`
- `0x180055f9c`
- `0x180055fd4`
- `0x1800616c8`
- `0x180063e64`

## import_xrefs

- `archiveint!archive_read_has_encrypted_entries` at `0x180061793`
- `archiveint!archive_read_has_encrypted_entries` at `0x180061793`
- `archiveint!archive_error_string` at `0x1800617a4`
- `archiveint!archive_error_string` at `0x1800617ec`
- `archiveint!archive_error_string` at `0x180061879`
- `archiveint!archive_error_string` at `0x1800617a4`
- `archiveint!archive_error_string` at `0x1800617ec`
- `archiveint!archive_error_string` at `0x180061879`
- `archiveint!archive_errno` at `0x180061722`
- `archiveint!archive_errno` at `0x1800617dd`
- `archiveint!archive_errno` at `0x180061722`
- `archiveint!archive_errno` at `0x1800617dd`
- `archiveint!archive_read_next_header` at `0x180061708`
- `archiveint!archive_read_next_header` at `0x180061708`

## string_xrefs

- `0x18006181c`: `shell\ext\zip\archive\precomp.h`
- `0x180061840`: `shell\ext\zip\archive\precomp.h`
- `0x180061864`: `shell\ext\zip\archive\precomp.h`
- `0x1800618a9`: `shell\ext\zip\archive\precomp.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall enumerate_archive__lambda_70f2a6337c3fbeddb77c614144e09a12_(__int64 *a1, __int64 a2)
{
  __int64 v4; // rbx
  int v5; // edi
  char v6; // bp
  __int64 result; // rax
  int v8; // edi
  unsigned int v9; // r8d
  const char *v10; // r9
  _BYTE *v11; // rax
  __int64 v12; // r8
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // edi
  unsigned int v16; // eax
  unsigned int v17; // eax
  const char *v18; // rdx
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  const char *v23; // rdx
  unsigned int v24; // [rsp+20h] [rbp-48h]
  __int64 v25; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = *a1;
  v25 = 0;
  v5 = 0;
  v6 = 0;
  do
  {
    result = archive_read_next_header(v4, &v25);
    if ( (_DWORD)result == 1 )
      break;
    if ( (_DWORD)result == -10 )
    {
      if ( (unsigned int)++v5 > 5 )
      {
        v8 = archive_errno(v4);
        if ( v8 )
        {
          archive_error_string(v4);
          v21 = HRESULT_FROM_ERRNO(v8);
          v22 = wil::verify_hresult<long>(v21);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x162,
            (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
            (const char *)v22,
            (int)"archive error: %hs",
            v23);
        }
        v19 = wil::verify_hresult<long>(2147500037LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x162,
          (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
          (const char *)v19,
          v24);
      }
    }
    else
    {
      if ( (_DWORD)result )
      {
        if ( (_DWORD)result == -30 )
        {
          if ( (int)archive_read_has_encrypted_entries(v4) > 0 )
            wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x16E, v9, v10, v24);
          v11 = (_BYTE *)archive_error_string(v4);
          if ( v11 )
          {
            v12 = -1;
            do
              ++v12;
            while ( v11[v12] );
            if ( v12 == 27 && !memcmp_0(v11, KnownArchiveErrors::EncryptedRAR, 0x1Bu) )
              wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x17A, v13, v14, v24);
          }
        }
        v15 = archive_errno(v4);
        if ( v15 )
        {
          archive_error_string(v4);
          v16 = HRESULT_FROM_ERRNO(v15);
          v17 = wil::verify_hresult<long>(v16);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x17F,
            (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
            (const char *)v17,
            (int)"archive error: %hs",
            v18);
        }
        v20 = wil::verify_hresult<long>(2147500037LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x17F,
          (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
          (const char *)v20,
          v24);
      }
      v5 = 0;
      do
      {
        result = lambda_70f2a6337c3fbeddb77c614144e09a12_::operator()(a2, v25);
        v6 = result;
      }
      while ( (_BYTE)result == 2 );
      ++*((_DWORD *)a1 + 2);
    }
  }
  while ( v6 != 1 );
  return result;
}

```

## disassembly

```asm
0x1800616c8  mov     [rsp+arg_10], rbx
0x1800616cd  mov     [rsp+arg_18], rbp
0x1800616d2  push    rsi
0x1800616d3  push    rdi
0x1800616d4  push    r14
0x1800616d6  sub     rsp, 50h
0x1800616da  mov     rax, cs:__security_cookie
0x1800616e1  xor     rax, rsp
0x1800616e4  mov     [rsp+68h+var_20], rax
0x1800616e9  mov     r14, rdx
0x1800616ec  mov     rsi, rcx
0x1800616ef  mov     rbx, [rcx]
0x1800616f2  mov     [rsp+68h+var_28], 0
0x1800616fb  xor     edi, edi
0x1800616fd  xor     bpl, bpl
0x180061700  lea     rdx, [rsp+68h+var_28]
0x180061705  mov     rcx, rbx
0x180061708  call    cs:__imp_archive_read_next_header
0x18006170e  cmp     eax, 1
0x180061711  jz      short loc_180061769
0x180061713  cmp     eax, 0FFFFFFF6h
0x180061716  jnz     short loc_180061737
0x180061718  inc     edi
0x18006171a  cmp     edi, 5
0x18006171d  jbe     short loc_180061763
0x18006171f  mov     rcx, rbx
0x180061722  call    cs:__imp_archive_errno
0x180061728  mov     edi, eax
0x18006172a  test    eax, eax
0x18006172c  jz      loc_18006182E
0x180061732  jmp     loc_180061876
0x180061737  test    eax, eax
0x180061739  jnz     short loc_18006178B
0x18006173b  xor     edi, edi
0x18006173d  mov     [rsp+68h+var_38], rsi
0x180061742  mov     [rsp+68h+var_30], 1
0x180061747  mov     rdx, [rsp+68h+var_28]
0x18006174c  mov     rcx, r14
0x18006174f  call    _lambda_70f2a6337c3fbeddb77c614144e09a12___operator__
0x180061754  mov     bpl, al
0x180061757  cmp     al, 2
0x180061759  jz      short loc_180061747
0x18006175b  mov     [rsp+68h+var_30], 0
0x180061760  inc     dword ptr [rsi+8]
0x180061763  cmp     bpl, 1
0x180061767  jnz     short loc_180061700
0x180061769  mov     rcx, [rsp+68h+var_20]
0x18006176e  xor     rcx, rsp; StackCookie
0x180061771  call    __security_check_cookie
0x180061776  lea     r11, [rsp+68h+var_18]
0x18006177b  mov     rbx, [r11+30h]
0x18006177f  mov     rbp, [r11+38h]
0x180061783  mov     rsp, r11
0x180061786  pop     r14
0x180061788  pop     rdi
0x180061789  pop     rsi
0x18006178a  retn
0x18006178b  cmp     eax, 0FFFFFFE2h
0x18006178e  jnz     short loc_1800617DA
0x180061790  mov     rcx, rbx
0x180061793  call    cs:__imp_archive_read_has_encrypted_entries
0x180061799  test    eax, eax
0x18006179b  jg      loc_1800618BB
0x1800617a1  mov     rcx, rbx
0x1800617a4  call    cs:__imp_archive_error_string
0x1800617aa  test    rax, rax
0x1800617ad  jz      short loc_1800617DA
0x1800617af  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800617b3  inc     r8; Size
0x1800617b6  cmp     byte ptr [rax+r8], 0
0x1800617bb  jnz     short loc_1800617B3
0x1800617bd  cmp     r8, 1Bh
0x1800617c1  jnz     short loc_1800617DA
0x1800617c3  mov     rdx, cs:?EncryptedRAR@KnownArchiveErrors@@3V?$basic_string_view@DU?$char_traits@D@std@@@std@@B; Buf2
0x1800617ca  mov     rcx, rax; Buf1
0x1800617cd  call    memcmp_0
0x1800617d2  test    eax, eax
0x1800617d4  jz      loc_1800618CB
0x1800617da  mov     rcx, rbx
0x1800617dd  call    cs:__imp_archive_errno
0x1800617e3  mov     edi, eax
0x1800617e5  test    eax, eax
0x1800617e7  jz      short loc_180061852
0x1800617e9  mov     rcx, rbx
0x1800617ec  call    cs:__imp_archive_error_string
0x1800617f2  mov     rdx, rax
0x1800617f5  mov     ecx, edi; int
0x1800617f7  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x1800617fc  mov     ecx, eax
0x1800617fe  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061803  mov     r9d, eax; char *
0x180061806  mov     rcx, [rsp+68h]; this
0x18006180b  mov     [rsp+68h+var_40], rdx; char *
0x180061810  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x180061817  mov     qword ptr [rsp+68h+var_48], rax; int
0x18006181c  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061823  mov     edx, 17Fh; void *
0x180061828  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006182e  mov     ecx, 80004005h
0x180061833  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061838  mov     r9d, eax; char *
0x18006183b  mov     rcx, [rsp+68h]; this
0x180061840  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x180061847  mov     edx, 162h; void *
0x18006184c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061852  mov     ecx, 80004005h
0x180061857  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18006185c  mov     r9d, eax; char *
0x18006185f  mov     rcx, [rsp+68h]; this
0x180061864  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x18006186b  mov     edx, 17Fh; void *
0x180061870  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061876  mov     rcx, rbx
0x180061879  call    cs:__imp_archive_error_string
0x18006187f  mov     rdx, rax
0x180061882  mov     ecx, edi; int
0x180061884  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x180061889  mov     ecx, eax
0x18006188b  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061890  mov     r9d, eax; char *
0x180061893  mov     rcx, [rsp+68h]; this
0x180061898  mov     [rsp+68h+var_40], rdx; char *
0x18006189d  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x1800618a4  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800618a9  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x1800618b0  mov     edx, 162h; void *
0x1800618b5  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800618bb  mov     rcx, [rsp+68h]; this
0x1800618c0  mov     edx, 16Eh; void *
0x1800618c5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800618cb  mov     rcx, [rsp+68h]; this
0x1800618d0  mov     edx, 17Ah; void *
0x1800618d5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
