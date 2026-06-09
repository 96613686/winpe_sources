# META_SCRIPT_MAP_TABLE::Initialize(INativeConfigurationElement *,IHttpServer *,int,LANG_STRING *,char const *,ushort,STRU *,IHttpTraceContext *)

- ea: `0x180018e28`
- end: `0x18001923f`
- name: `?Initialize@META_SCRIPT_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@PEAVIHttpServer@@HPEAVLANG_STRING@@PEBDGPEAVSTRU@@PEAVIHttpTraceContext@@@Z`
- size: `1047`
- prototype: `__int64 __fastcall(META_SCRIPT_MAP_TABLE *__hidden this, struct INativeConfigurationElement *, struct IHttpServer *, int, struct LANG_STRING *, const char *, unsigned __int16, struct STRU *, struct IHttpTraceContext *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180018d28`

## callees

- `0x1800011d4`
- `0x180018a84`
- `0x180018e28`
- `0x180023010`

## import_xrefs

- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x1800190f1`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x1800190f1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800190da`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800190e4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800190fe`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001910b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180019118`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800190da`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800190e4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800190fe`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001910b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180019118`

## string_xrefs

- `0x18001903f`: `requireAccess`
- `0x18001906c`: `allowPathInfo`

## pseudocode

```c
__int64 __fastcall META_SCRIPT_MAP_TABLE::Initialize(
        META_SCRIPT_MAP_TABLE *this,
        struct INativeConfigurationElement *a2,
        struct IHttpServer *a3,
        int a4,
        struct LANG_STRING *a5,
        const char *a6,
        unsigned int a7,
        struct STRU *a8,
        struct IHttpTraceContext *a9)
{
  __int64 v9; // rax
  __int64 (__fastcall *v11)(struct INativeConfigurationElement *, struct STRU **); // rax
  int v12; // ebx
  unsigned int v13; // r14d
  char *v14; // rsi
  __int64 v15; // rax
  char *v16; // rdi
  bool v17; // zf
  char *v18; // rax
  char **v19; // rcx
  const char *v20; // rcx
  struct STRU *v21; // rcx
  LPCWSTR lpSrc; // [rsp+60h] [rbp-29h] BYREF
  unsigned __int16 *v24; // [rsp+68h] [rbp-21h] BYREF
  unsigned __int16 *v25; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int16 *v26; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int16 *v27; // [rsp+80h] [rbp-9h] BYREF
  int v28; // [rsp+D8h] [rbp+4Fh] BYREF
  struct IHttpServer *v29; // [rsp+E0h] [rbp+57h] BYREF
  int v30; // [rsp+E8h] [rbp+5Fh] BYREF

  v30 = a4;
  v29 = a3;
  v9 = *(_QWORD *)a2;
  a8 = 0;
  a6 = 0;
  v27 = 0;
  v11 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, struct STRU **))(v9 + 40);
  v26 = 0;
  v25 = 0;
  v24 = 0;
  lpSrc = 0;
  a9 = 0;
  LODWORD(a5) = 0;
  v28 = 0;
  LODWORD(v29) = 0;
  v30 = 0;
  a7 = 0;
  v12 = v11(a2, &a8);
  if ( v12 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(struct STRU *, unsigned int *))(*(_QWORD *)a8 + 24LL))(a8, &a7);
    if ( v12 >= 0 )
    {
      v13 = 0;
      if ( !a7 )
      {
LABEL_21:
        v21 = a8;
LABEL_27:
        (*(void (__fastcall **)(struct STRU *))(*(_QWORD *)v21 + 16LL))(v21);
        return (unsigned int)v12;
      }
      while ( 1 )
      {
        v12 = (*(__int64 (__fastcall **)(struct STRU *, _QWORD, const char **))(*(_QWORD *)a8 + 32LL))(a8, v13, &a6);
        if ( v12 < 0 )
          break;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a6 + 64LL))(
                a6,
                L"name",
                &v27,
                0,
                0);
        if ( v12 < 0 )
          break;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a6 + 64LL))(
                a6,
                L"path",
                &v26,
                0,
                0);
        if ( v12 < 0 )
          break;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a6 + 64LL))(
                a6,
                L"verb",
                &v25,
                0,
                0);
        if ( v12 < 0 )
          break;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a6 + 64LL))(
                a6,
                L"modules",
                &v24,
                0,
                0);
        if ( v12 < 0 )
          break;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)a6 + 64LL))(
                a6,
                L"scriptProcessor",
                &lpSrc,
                0,
                0);
        if ( v12 < 0 )
          break;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, struct IHttpTraceContext **, _QWORD, _QWORD))(*(_QWORD *)a6 + 64LL))(
                a6,
                L"type",
                &a9,
                0,
                0);
        if ( v12 < 0 )
          break;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, struct LANG_STRING **, _QWORD, _QWORD))(*(_QWORD *)a6 + 48LL))(
                a6,
                L"resourceType",
                &a5,
                0,
                0);
        if ( v12 < 0 )
          break;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)a6 + 48LL))(
                a6,
                L"requireAccess",
                &v28,
                0,
                0);
        if ( v12 < 0 )
          break;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, struct IHttpServer **, _QWORD, _QWORD))(*(_QWORD *)a6 + 72LL))(
                a6,
                L"allowPathInfo",
                &v29,
                0,
                0);
        if ( v12 < 0 )
          break;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)a6 + 48LL))(
                a6,
                L"responseBufferLimit",
                &v30,
                0,
                0);
        if ( v12 < 0 )
          break;
        v14 = (char *)operator new(0x180u);
        if ( !v14 )
        {
          v12 = -2147024888;
          break;
        }
        *(_QWORD *)v14 = &META_SCRIPT_MAP_ENTRY::`vftable';
        STRU::STRU((STRU *)(v14 + 24));
        STRU::STRU((STRU *)(v14 + 80));
        MULTISZA::MULTISZA((MULTISZA *)(v14 + 136));
        STRU::STRU((STRU *)(v14 + 192));
        STRU::STRU((STRU *)(v14 + 248));
        STRU::STRU((STRU *)(v14 + 304));
        *((_QWORD *)v14 + 46) = 0;
        *((_QWORD *)v14 + 2) = v14 + 8;
        *((_QWORD *)v14 + 1) = v14 + 8;
        v12 = META_SCRIPT_MAP_ENTRY::Create(
                (META_SCRIPT_MAP_ENTRY *)v14,
                v27,
                v26,
                v25,
                v24,
                lpSrc,
                (const unsigned __int16 *)a9,
                (int)a5,
                v28,
                (int)v29,
                v30);
        v15 = *(_QWORD *)v14;
        if ( v12 < 0 )
        {
          (*(void (__fastcall **)(char *, __int64))(v15 + 88))(v14, 1);
          break;
        }
        v16 = v14 + 8;
        v17 = (*(unsigned int (__fastcall **)(char *))(v15 + 64))(v14) == 0;
        v18 = (char *)this + 24;
        if ( v17 )
          v18 = (char *)this + 8;
        v19 = (char **)*((_QWORD *)v18 + 1);
        if ( *v19 != v18 )
          __fastfail(3u);
        *(_QWORD *)v16 = v18;
        *((_QWORD *)v14 + 2) = v19;
        *v19 = v16;
        v20 = a6;
        *((_QWORD *)v18 + 1) = v16;
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v20 + 16LL))(v20);
        ++v13;
        a6 = 0;
        if ( v13 >= a7 )
          goto LABEL_21;
      }
    }
  }
  if ( a6 )
  {
    (*(void (__fastcall **)(const char *))(*(_QWORD *)a6 + 16LL))(a6);
    a6 = 0;
  }
  v21 = a8;
  if ( a8 )
    goto LABEL_27;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180018e28  mov     [rsp-8+arg_18], r9d
0x180018e2d  mov     [rsp-8+arg_10], r8
0x180018e32  push    rbp
0x180018e33  push    rbx
0x180018e34  push    rsi
0x180018e35  push    rdi
0x180018e36  push    r12
0x180018e38  push    r14
0x180018e3a  push    r15
0x180018e3c  lea     rbp, [rsp-7]
0x180018e41  sub     rsp, 90h
0x180018e48  mov     rax, [rdx]
0x180018e4b  xor     r12d, r12d
0x180018e4e  mov     r8, rdx
0x180018e51  mov     [rbp+37h+arg_38], r12
0x180018e55  mov     r15, rcx
0x180018e58  mov     [rbp+37h+arg_28], r12
0x180018e5c  lea     rdx, [rbp+37h+arg_38]
0x180018e60  mov     [rbp+37h+var_40], r12
0x180018e64  mov     rax, [rax+28h]
0x180018e68  mov     rcx, r8
0x180018e6b  mov     [rbp+37h+var_48], r12
0x180018e6f  mov     [rbp+37h+var_50], r12
0x180018e73  mov     [rbp+37h+var_58], r12
0x180018e77  mov     [rbp+37h+var_60], r12
0x180018e7b  mov     [rbp+37h+arg_40], r12
0x180018e82  mov     dword ptr [rbp+37h+arg_20], r12d
0x180018e86  mov     [rbp+37h+arg_8], r12d
0x180018e8a  mov     dword ptr [rbp+37h+arg_10], r12d
0x180018e8e  mov     [rbp+37h+arg_18], r12d
0x180018e92  mov     [rbp+37h+arg_30], r12d
0x180018e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e9b  mov     ebx, eax
0x180018e9d  test    eax, eax
0x180018e9f  js      loc_1800191F6
0x180018ea5  mov     rcx, [rbp+37h+arg_38]
0x180018ea9  lea     rdx, [rbp+37h+arg_30]
0x180018ead  mov     rax, [rcx]
0x180018eb0  mov     rax, [rax+18h]
0x180018eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018eb9  mov     ebx, eax
0x180018ebb  test    eax, eax
0x180018ebd  js      loc_1800191F6
0x180018ec3  mov     r14d, r12d
0x180018ec6  cmp     [rbp+37h+arg_30], r12d
0x180018eca  jbe     loc_1800191DB
0x180018ed0  mov     rcx, [rbp+37h+arg_38]
0x180018ed4  lea     r8, [rbp+37h+arg_28]
0x180018ed8  mov     edx, r14d
0x180018edb  mov     rax, [rcx]
0x180018ede  mov     rax, [rax+20h]
0x180018ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ee7  mov     ebx, eax
0x180018ee9  test    eax, eax
0x180018eeb  js      loc_1800191F6
0x180018ef1  mov     rcx, [rbp+37h+arg_28]
0x180018ef5  lea     r8, [rbp+37h+var_40]
0x180018ef9  xor     r9d, r9d
0x180018efc  mov     [rsp+0C0h+var_A0], r12
0x180018f01  lea     rdx, aName; "name"
0x180018f08  mov     rax, [rcx]
0x180018f0b  mov     rax, [rax+40h]
0x180018f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f14  mov     ebx, eax
0x180018f16  test    eax, eax
0x180018f18  js      loc_1800191F6
0x180018f1e  mov     rcx, [rbp+37h+arg_28]
0x180018f22  lea     r8, [rbp+37h+var_48]
0x180018f26  xor     r9d, r9d
0x180018f29  mov     [rsp+0C0h+var_A0], r12
0x180018f2e  lea     rdx, aPath; "path"
0x180018f35  mov     rax, [rcx]
0x180018f38  mov     rax, [rax+40h]
0x180018f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f41  mov     ebx, eax
0x180018f43  test    eax, eax
0x180018f45  js      loc_1800191F6
0x180018f4b  mov     rcx, [rbp+37h+arg_28]
0x180018f4f  lea     r8, [rbp+37h+var_50]
0x180018f53  xor     r9d, r9d
0x180018f56  mov     [rsp+0C0h+var_A0], r12
0x180018f5b  lea     rdx, aVerb; "verb"
0x180018f62  mov     rax, [rcx]
0x180018f65  mov     rax, [rax+40h]
0x180018f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f6e  mov     ebx, eax
0x180018f70  test    eax, eax
0x180018f72  js      loc_1800191F6
0x180018f78  mov     rcx, [rbp+37h+arg_28]
0x180018f7c  lea     r8, [rbp+37h+var_58]
0x180018f80  xor     r9d, r9d
0x180018f83  mov     [rsp+0C0h+var_A0], r12
0x180018f88  lea     rdx, aModules; "modules"
0x180018f8f  mov     rax, [rcx]
0x180018f92  mov     rax, [rax+40h]
0x180018f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f9b  mov     ebx, eax
0x180018f9d  test    eax, eax
0x180018f9f  js      loc_1800191F6
0x180018fa5  mov     rcx, [rbp+37h+arg_28]
0x180018fa9  lea     r8, [rbp+37h+var_60]
0x180018fad  xor     r9d, r9d
0x180018fb0  mov     [rsp+0C0h+var_A0], r12
0x180018fb5  lea     rdx, aScriptprocesso; "scriptProcessor"
0x180018fbc  mov     rax, [rcx]
0x180018fbf  mov     rax, [rax+40h]
0x180018fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fc8  mov     ebx, eax
0x180018fca  test    eax, eax
0x180018fcc  js      loc_1800191F6
0x180018fd2  mov     rcx, [rbp+37h+arg_28]
0x180018fd6  lea     r8, [rbp+37h+arg_40]
0x180018fdd  xor     r9d, r9d
0x180018fe0  mov     [rsp+0C0h+var_A0], r12
0x180018fe5  lea     rdx, aType; "type"
0x180018fec  mov     rax, [rcx]
0x180018fef  mov     rax, [rax+40h]
0x180018ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ff8  mov     ebx, eax
0x180018ffa  test    eax, eax
0x180018ffc  js      loc_1800191F6
0x180019002  mov     rcx, [rbp+37h+arg_28]
0x180019006  lea     r8, [rbp+37h+arg_20]
0x18001900a  xor     r9d, r9d
0x18001900d  mov     [rsp+0C0h+var_A0], r12
0x180019012  lea     rdx, aResourcetype; "resourceType"
0x180019019  mov     rax, [rcx]
0x18001901c  mov     rax, [rax+30h]
0x180019020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019025  mov     ebx, eax
0x180019027  test    eax, eax
0x180019029  js      loc_1800191F6
0x18001902f  mov     rcx, [rbp+37h+arg_28]
0x180019033  lea     r8, [rbp+37h+arg_8]
0x180019037  xor     r9d, r9d
0x18001903a  mov     [rsp+0C0h+var_A0], r12
0x18001903f  lea     rdx, aRequireaccess; "requireAccess"
0x180019046  mov     rax, [rcx]
0x180019049  mov     rax, [rax+30h]
0x18001904d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019052  mov     ebx, eax
0x180019054  test    eax, eax
0x180019056  js      loc_1800191F6
0x18001905c  mov     rcx, [rbp+37h+arg_28]
0x180019060  lea     r8, [rbp+37h+arg_10]
0x180019064  xor     r9d, r9d
0x180019067  mov     [rsp+0C0h+var_A0], r12
0x18001906c  lea     rdx, aAllowpathinfo; "allowPathInfo"
0x180019073  mov     rax, [rcx]
0x180019076  mov     rax, [rax+48h]
0x18001907a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001907f  mov     ebx, eax
0x180019081  test    eax, eax
0x180019083  js      loc_1800191F6
0x180019089  mov     rcx, [rbp+37h+arg_28]
0x18001908d  lea     r8, [rbp+37h+arg_18]
0x180019091  xor     r9d, r9d
0x180019094  mov     [rsp+0C0h+var_A0], r12
0x180019099  lea     rdx, aResponsebuffer; "responseBufferLimit"
0x1800190a0  mov     rax, [rcx]
0x1800190a3  mov     rax, [rax+30h]
0x1800190a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190ac  mov     ebx, eax
0x1800190ae  test    eax, eax
0x1800190b0  js      loc_1800191F6
0x1800190b6  mov     ecx, 180h; Size
0x1800190bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800190c0  mov     rsi, rax
0x1800190c3  test    rax, rax
0x1800190c6  jz      loc_180019238
0x1800190cc  lea     rax, ??_7META_SCRIPT_MAP_ENTRY@@6B@; const META_SCRIPT_MAP_ENTRY::`vftable'
0x1800190d3  lea     rcx, [rsi+18h]
0x1800190d7  mov     [rsi], rax
0x1800190da  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800190e0  lea     rcx, [rsi+50h]
0x1800190e4  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800190ea  lea     rcx, [rsi+88h]
0x1800190f1  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x1800190f7  lea     rcx, [rsi+0C0h]
0x1800190fe  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180019104  lea     rcx, [rsi+0F8h]
0x18001910b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180019111  lea     rcx, [rsi+130h]
0x180019118  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001911e  mov     [rsi+170h], r12
0x180019125  lea     rax, [rsi+8]
0x180019129  mov     [rsi+10h], rax
0x18001912d  mov     rcx, rsi; this
0x180019130  mov     [rax], rax
0x180019133  mov     eax, [rbp+37h+arg_18]
0x180019136  mov     r9, [rbp+37h+var_50]; unsigned __int16 *
0x18001913a  mov     r8, [rbp+37h+var_48]; unsigned __int16 *
0x18001913e  mov     rdx, [rbp+37h+var_40]; unsigned __int16 *
0x180019142  mov     [rsp+0C0h+var_70], eax; int
0x180019146  mov     eax, dword ptr [rbp+37h+arg_10]
0x180019149  mov     [rsp+0C0h+var_78], eax; int
0x18001914d  mov     eax, [rbp+37h+arg_8]
0x180019150  mov     [rsp+0C0h+var_80], eax; int
0x180019154  mov     eax, dword ptr [rbp+37h+arg_20]
0x180019157  mov     [rsp+0C0h+var_88], eax; int
0x18001915b  mov     rax, [rbp+37h+arg_40]
0x180019162  mov     [rsp+0C0h+var_90], rax; unsigned __int16 *
0x180019167  mov     rax, [rbp+37h+var_60]
0x18001916b  mov     [rsp+0C0h+lpSrc], rax; lpSrc
0x180019170  mov     rax, [rbp+37h+var_58]
0x180019174  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x180019179  call    ?Create@META_SCRIPT_MAP_ENTRY@@QEAAJPEBG00000JJHJ@Z; META_SCRIPT_MAP_ENTRY::Create(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,long,long,int,long)
0x18001917e  mov     ebx, eax
0x180019180  mov     rcx, rsi
0x180019183  mov     rax, [rsi]
0x180019186  test    ebx, ebx
0x180019188  js      short loc_1800191E8
0x18001918a  mov     rax, [rax+40h]
0x18001918e  lea     rdi, [rsi+8]
0x180019192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019197  test    eax, eax
0x180019199  lea     rax, [r15+18h]
0x18001919d  jnz     short loc_1800191A3
0x18001919f  lea     rax, [r15+8]
0x1800191a3  mov     rcx, [rax+8]
0x1800191a7  cmp     [rcx], rax
0x1800191aa  jnz     short loc_1800191E1
0x1800191ac  mov     [rdi], rax
0x1800191af  mov     [rdi+8], rcx
0x1800191b3  mov     [rcx], rdi
0x1800191b6  mov     rcx, [rbp+37h+arg_28]
0x1800191ba  mov     [rax+8], rdi
0x1800191be  mov     rax, [rcx]
0x1800191c1  mov     rax, [rax+10h]
0x1800191c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191ca  inc     r14d
0x1800191cd  mov     [rbp+37h+arg_28], r12
0x1800191d1  cmp     r14d, [rbp+37h+arg_30]
0x1800191d5  jb      loc_180018ED0
0x1800191db  mov     rcx, [rbp+37h+arg_38]
0x1800191df  jmp     short loc_180019218
0x1800191e1  mov     ecx, 3
0x1800191e6  int     29h; Win8: RtlFailFast(ecx)
0x1800191e8  mov     rax, [rax+58h]
0x1800191ec  mov     edx, 1
0x1800191f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191f6  mov     rcx, [rbp+37h+arg_28]
0x1800191fa  test    rcx, rcx
0x1800191fd  jz      short loc_18001920F
0x1800191ff  mov     rax, [rcx]
0x180019202  mov     rax, [rax+10h]
0x180019206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001920b  mov     [rbp+37h+arg_28], r12
0x18001920f  mov     rcx, [rbp+37h+arg_38]
0x180019213  test    rcx, rcx
0x180019216  jz      short loc_180019224
0x180019218  mov     rax, [rcx]
0x18001921b  mov     rax, [rax+10h]
0x18001921f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019224  mov     eax, ebx
0x180019226  add     rsp, 90h
0x18001922d  pop     r15
0x18001922f  pop     r14
0x180019231  pop     r12
0x180019233  pop     rdi
0x180019234  pop     rsi
0x180019235  pop     rbx
0x180019236  pop     rbp
0x180019237  retn
0x180019238  mov     ebx, 80070008h
0x18001923d  jmp     short loc_1800191F6
```
