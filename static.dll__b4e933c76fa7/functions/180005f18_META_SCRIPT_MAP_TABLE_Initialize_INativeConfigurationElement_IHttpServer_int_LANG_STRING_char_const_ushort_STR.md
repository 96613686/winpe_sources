# META_SCRIPT_MAP_TABLE::Initialize(INativeConfigurationElement *,IHttpServer *,int,LANG_STRING *,char const *,ushort,STRU *,IHttpTraceContext *)

- ea: `0x180005f18`
- end: `0x180006324`
- name: `?Initialize@META_SCRIPT_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@PEAVIHttpServer@@HPEAVLANG_STRING@@PEBDGPEAVSTRU@@PEAVIHttpTraceContext@@@Z`
- size: `1036`
- prototype: `__int64 __fastcall(META_SCRIPT_MAP_TABLE *__hidden this, struct INativeConfigurationElement *, struct IHttpServer *, int, struct LANG_STRING *, const char *, unsigned __int16, struct STRU *, struct IHttpTraceContext *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005e30`

## callees

- `0x180001358`
- `0x1800059bc`
- `0x180005f18`
- `0x180007010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x1800061ca`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800061d4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800061ee`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800061fb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006208`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800061ca`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800061d4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800061ee`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800061fb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006208`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x1800061e1`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x1800061e1`

## string_xrefs

- `0x18000612f`: `requireAccess`
- `0x18000615c`: `allowPathInfo`

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
  unsigned int i; // r14d
  __int64 v14; // rax
  char *v15; // rsi
  __int64 v16; // rax
  char *v17; // rdi
  bool v18; // zf
  char *v19; // rax
  char **v20; // rcx
  const char *v21; // rcx
  unsigned __int16 *v23; // [rsp+60h] [rbp-29h] BYREF
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
  v23 = 0;
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
      for ( i = 0; ; ++i )
      {
        v14 = *(_QWORD *)a8;
        if ( i >= a7 )
          break;
        v12 = (*(__int64 (__fastcall **)(struct STRU *, _QWORD, const char **))(v14 + 32))(a8, i, &a6);
        if ( v12 < 0 )
          goto LABEL_25;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a6 + 64LL))(
                a6,
                L"name",
                &v27,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_25;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a6 + 64LL))(
                a6,
                L"path",
                &v26,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_25;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a6 + 64LL))(
                a6,
                L"verb",
                &v25,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_25;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a6 + 64LL))(
                a6,
                L"modules",
                &v24,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_25;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a6 + 64LL))(
                a6,
                L"scriptProcessor",
                &v23,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_25;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, struct IHttpTraceContext **, _QWORD, _QWORD))(*(_QWORD *)a6 + 64LL))(
                a6,
                L"type",
                &a9,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_25;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, struct LANG_STRING **, _QWORD, _QWORD))(*(_QWORD *)a6 + 48LL))(
                a6,
                L"resourceType",
                &a5,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_25;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)a6 + 48LL))(
                a6,
                L"requireAccess",
                &v28,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_25;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, struct IHttpServer **, _QWORD, _QWORD))(*(_QWORD *)a6 + 72LL))(
                a6,
                L"allowPathInfo",
                &v29,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_25;
        v12 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)a6 + 48LL))(
                a6,
                L"responseBufferLimit",
                &v30,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_25;
        v15 = (char *)operator new(0x180u);
        if ( !v15 )
        {
          v12 = -2147024888;
          goto LABEL_25;
        }
        *(_QWORD *)v15 = &META_SCRIPT_MAP_ENTRY::`vftable';
        STRU::STRU((STRU *)(v15 + 24));
        STRU::STRU((STRU *)(v15 + 80));
        MULTISZA::MULTISZA((MULTISZA *)(v15 + 136));
        STRU::STRU((STRU *)(v15 + 192));
        STRU::STRU((STRU *)(v15 + 248));
        STRU::STRU((STRU *)(v15 + 304));
        *((_QWORD *)v15 + 46) = 0;
        *((_QWORD *)v15 + 2) = v15 + 8;
        *((_QWORD *)v15 + 1) = v15 + 8;
        v12 = META_SCRIPT_MAP_ENTRY::Create(
                (META_SCRIPT_MAP_ENTRY *)v15,
                v27,
                v26,
                v25,
                v24,
                v23,
                (const unsigned __int16 *)a9,
                (int)a5,
                v28,
                (int)v29,
                v30);
        v16 = *(_QWORD *)v15;
        if ( v12 < 0 )
        {
          (*(void (__fastcall **)(char *, __int64))(v16 + 88))(v15, 1);
          goto LABEL_25;
        }
        v17 = v15 + 8;
        v18 = (*(unsigned int (__fastcall **)(char *))(v16 + 64))(v15) == 0;
        v19 = (char *)this + 24;
        if ( v18 )
          v19 = (char *)this + 8;
        v20 = (char **)*((_QWORD *)v19 + 1);
        if ( *v20 != v19 )
          __fastfail(3u);
        *(_QWORD *)v17 = v19;
        *((_QWORD *)v15 + 2) = v20;
        *v20 = v17;
        v21 = a6;
        *((_QWORD *)v19 + 1) = v17;
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v21 + 16LL))(v21);
        a6 = 0;
      }
      goto LABEL_29;
    }
  }
LABEL_25:
  if ( a6 )
  {
    (*(void (__fastcall **)(const char *))(*(_QWORD *)a6 + 16LL))(a6);
    a6 = 0;
  }
  if ( a8 )
  {
    v14 = *(_QWORD *)a8;
LABEL_29:
    (*(void (**)(void))(v14 + 16))();
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180005f18  mov     [rsp-8+arg_18], r9d
0x180005f1d  mov     [rsp-8+arg_10], r8
0x180005f22  push    rbp
0x180005f23  push    rbx
0x180005f24  push    rsi
0x180005f25  push    rdi
0x180005f26  push    r12
0x180005f28  push    r14
0x180005f2a  push    r15
0x180005f2c  lea     rbp, [rsp-7]
0x180005f31  sub     rsp, 90h
0x180005f38  mov     rax, [rdx]
0x180005f3b  xor     r12d, r12d
0x180005f3e  mov     r8, rdx
0x180005f41  mov     [rbp+37h+arg_38], r12
0x180005f45  mov     r15, rcx
0x180005f48  mov     [rbp+37h+arg_28], r12
0x180005f4c  lea     rdx, [rbp+37h+arg_38]
0x180005f50  mov     [rbp+37h+var_40], r12
0x180005f54  mov     rax, [rax+28h]
0x180005f58  mov     rcx, r8
0x180005f5b  mov     [rbp+37h+var_48], r12
0x180005f5f  mov     [rbp+37h+var_50], r12
0x180005f63  mov     [rbp+37h+var_58], r12
0x180005f67  mov     [rbp+37h+var_60], r12
0x180005f6b  mov     [rbp+37h+arg_40], r12
0x180005f72  mov     dword ptr [rbp+37h+arg_20], r12d
0x180005f76  mov     [rbp+37h+arg_8], r12d
0x180005f7a  mov     dword ptr [rbp+37h+arg_10], r12d
0x180005f7e  mov     [rbp+37h+arg_18], r12d
0x180005f82  mov     [rbp+37h+arg_30], r12d
0x180005f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f8b  mov     ebx, eax
0x180005f8d  test    eax, eax
0x180005f8f  js      loc_1800062E2
0x180005f95  mov     rcx, [rbp+37h+arg_38]
0x180005f99  lea     rdx, [rbp+37h+arg_30]
0x180005f9d  mov     rax, [rcx]
0x180005fa0  mov     rax, [rax+18h]
0x180005fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fa9  mov     ebx, eax
0x180005fab  test    eax, eax
0x180005fad  js      loc_1800062E2
0x180005fb3  mov     r14d, r12d
0x180005fb6  mov     rcx, [rbp+37h+arg_38]
0x180005fba  mov     rax, [rcx]
0x180005fbd  cmp     r14d, [rbp+37h+arg_30]
0x180005fc1  jnb     loc_180006307
0x180005fc7  mov     rax, [rax+20h]
0x180005fcb  lea     r8, [rbp+37h+arg_28]
0x180005fcf  mov     edx, r14d
0x180005fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fd7  mov     ebx, eax
0x180005fd9  test    eax, eax
0x180005fdb  js      loc_1800062E2
0x180005fe1  mov     rcx, [rbp+37h+arg_28]
0x180005fe5  lea     r8, [rbp+37h+var_40]
0x180005fe9  xor     r9d, r9d
0x180005fec  mov     [rsp+0C0h+var_A0], r12
0x180005ff1  lea     rdx, aName; "name"
0x180005ff8  mov     rax, [rcx]
0x180005ffb  mov     rax, [rax+40h]
0x180005fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006004  mov     ebx, eax
0x180006006  test    eax, eax
0x180006008  js      loc_1800062E2
0x18000600e  mov     rcx, [rbp+37h+arg_28]
0x180006012  lea     r8, [rbp+37h+var_48]
0x180006016  xor     r9d, r9d
0x180006019  mov     [rsp+0C0h+var_A0], r12
0x18000601e  lea     rdx, aPath; "path"
0x180006025  mov     rax, [rcx]
0x180006028  mov     rax, [rax+40h]
0x18000602c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006031  mov     ebx, eax
0x180006033  test    eax, eax
0x180006035  js      loc_1800062E2
0x18000603b  mov     rcx, [rbp+37h+arg_28]
0x18000603f  lea     r8, [rbp+37h+var_50]
0x180006043  xor     r9d, r9d
0x180006046  mov     [rsp+0C0h+var_A0], r12
0x18000604b  lea     rdx, aVerb; "verb"
0x180006052  mov     rax, [rcx]
0x180006055  mov     rax, [rax+40h]
0x180006059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000605e  mov     ebx, eax
0x180006060  test    eax, eax
0x180006062  js      loc_1800062E2
0x180006068  mov     rcx, [rbp+37h+arg_28]
0x18000606c  lea     r8, [rbp+37h+var_58]
0x180006070  xor     r9d, r9d
0x180006073  mov     [rsp+0C0h+var_A0], r12
0x180006078  lea     rdx, aModules; "modules"
0x18000607f  mov     rax, [rcx]
0x180006082  mov     rax, [rax+40h]
0x180006086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000608b  mov     ebx, eax
0x18000608d  test    eax, eax
0x18000608f  js      loc_1800062E2
0x180006095  mov     rcx, [rbp+37h+arg_28]
0x180006099  lea     r8, [rbp+37h+var_60]
0x18000609d  xor     r9d, r9d
0x1800060a0  mov     [rsp+0C0h+var_A0], r12
0x1800060a5  lea     rdx, aScriptprocesso; "scriptProcessor"
0x1800060ac  mov     rax, [rcx]
0x1800060af  mov     rax, [rax+40h]
0x1800060b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060b8  mov     ebx, eax
0x1800060ba  test    eax, eax
0x1800060bc  js      loc_1800062E2
0x1800060c2  mov     rcx, [rbp+37h+arg_28]
0x1800060c6  lea     r8, [rbp+37h+arg_40]
0x1800060cd  xor     r9d, r9d
0x1800060d0  mov     [rsp+0C0h+var_A0], r12
0x1800060d5  lea     rdx, aType; "type"
0x1800060dc  mov     rax, [rcx]
0x1800060df  mov     rax, [rax+40h]
0x1800060e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060e8  mov     ebx, eax
0x1800060ea  test    eax, eax
0x1800060ec  js      loc_1800062E2
0x1800060f2  mov     rcx, [rbp+37h+arg_28]
0x1800060f6  lea     r8, [rbp+37h+arg_20]
0x1800060fa  xor     r9d, r9d
0x1800060fd  mov     [rsp+0C0h+var_A0], r12
0x180006102  lea     rdx, aResourcetype; "resourceType"
0x180006109  mov     rax, [rcx]
0x18000610c  mov     rax, [rax+30h]
0x180006110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006115  mov     ebx, eax
0x180006117  test    eax, eax
0x180006119  js      loc_1800062E2
0x18000611f  mov     rcx, [rbp+37h+arg_28]
0x180006123  lea     r8, [rbp+37h+arg_8]
0x180006127  xor     r9d, r9d
0x18000612a  mov     [rsp+0C0h+var_A0], r12
0x18000612f  lea     rdx, aRequireaccess; "requireAccess"
0x180006136  mov     rax, [rcx]
0x180006139  mov     rax, [rax+30h]
0x18000613d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006142  mov     ebx, eax
0x180006144  test    eax, eax
0x180006146  js      loc_1800062E2
0x18000614c  mov     rcx, [rbp+37h+arg_28]
0x180006150  lea     r8, [rbp+37h+arg_10]
0x180006154  xor     r9d, r9d
0x180006157  mov     [rsp+0C0h+var_A0], r12
0x18000615c  lea     rdx, aAllowpathinfo; "allowPathInfo"
0x180006163  mov     rax, [rcx]
0x180006166  mov     rax, [rax+48h]
0x18000616a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000616f  mov     ebx, eax
0x180006171  test    eax, eax
0x180006173  js      loc_1800062E2
0x180006179  mov     rcx, [rbp+37h+arg_28]
0x18000617d  lea     r8, [rbp+37h+arg_18]
0x180006181  xor     r9d, r9d
0x180006184  mov     [rsp+0C0h+var_A0], r12
0x180006189  lea     rdx, aResponsebuffer; "responseBufferLimit"
0x180006190  mov     rax, [rcx]
0x180006193  mov     rax, [rax+30h]
0x180006197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000619c  mov     ebx, eax
0x18000619e  test    eax, eax
0x1800061a0  js      loc_1800062E2
0x1800061a6  mov     ecx, 180h; Size
0x1800061ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800061b0  mov     rsi, rax
0x1800061b3  test    rax, rax
0x1800061b6  jz      loc_1800062DD
0x1800061bc  lea     rax, ??_7META_SCRIPT_MAP_ENTRY@@6B@; const META_SCRIPT_MAP_ENTRY::`vftable'
0x1800061c3  lea     rcx, [rsi+18h]
0x1800061c7  mov     [rsi], rax
0x1800061ca  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800061d0  lea     rcx, [rsi+50h]
0x1800061d4  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800061da  lea     rcx, [rsi+88h]
0x1800061e1  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x1800061e7  lea     rcx, [rsi+0C0h]
0x1800061ee  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800061f4  lea     rcx, [rsi+0F8h]
0x1800061fb  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006201  lea     rcx, [rsi+130h]
0x180006208  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000620e  mov     [rsi+170h], r12
0x180006215  lea     rax, [rsi+8]
0x180006219  mov     [rsi+10h], rax
0x18000621d  mov     rcx, rsi; this
0x180006220  mov     [rax], rax
0x180006223  mov     eax, [rbp+37h+arg_18]
0x180006226  mov     r9, [rbp+37h+var_50]; unsigned __int16 *
0x18000622a  mov     r8, [rbp+37h+var_48]; unsigned __int16 *
0x18000622e  mov     rdx, [rbp+37h+var_40]; unsigned __int16 *
0x180006232  mov     [rsp+0C0h+var_70], eax; int
0x180006236  mov     eax, dword ptr [rbp+37h+arg_10]
0x180006239  mov     [rsp+0C0h+var_78], eax; int
0x18000623d  mov     eax, [rbp+37h+arg_8]
0x180006240  mov     [rsp+0C0h+var_80], eax; int
0x180006244  mov     eax, dword ptr [rbp+37h+arg_20]
0x180006247  mov     [rsp+0C0h+var_88], eax; int
0x18000624b  mov     rax, [rbp+37h+arg_40]
0x180006252  mov     [rsp+0C0h+var_90], rax; unsigned __int16 *
0x180006257  mov     rax, [rbp+37h+var_60]
0x18000625b  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x180006260  mov     rax, [rbp+37h+var_58]
0x180006264  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x180006269  call    ?Create@META_SCRIPT_MAP_ENTRY@@QEAAJPEBG00000JJHJ@Z; META_SCRIPT_MAP_ENTRY::Create(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,long,long,int,long)
0x18000626e  mov     ebx, eax
0x180006270  mov     rcx, rsi
0x180006273  mov     rax, [rsi]
0x180006276  test    ebx, ebx
0x180006278  js      short loc_1800062CD
0x18000627a  mov     rax, [rax+40h]
0x18000627e  lea     rdi, [rsi+8]
0x180006282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006287  test    eax, eax
0x180006289  lea     rax, [r15+18h]
0x18000628d  jnz     short loc_180006293
0x18000628f  lea     rax, [r15+8]
0x180006293  mov     rcx, [rax+8]
0x180006297  cmp     [rcx], rax
0x18000629a  jnz     short loc_1800062C6
0x18000629c  mov     [rdi], rax
0x18000629f  mov     [rdi+8], rcx
0x1800062a3  mov     [rcx], rdi
0x1800062a6  mov     rcx, [rbp+37h+arg_28]
0x1800062aa  mov     [rax+8], rdi
0x1800062ae  mov     rax, [rcx]
0x1800062b1  mov     rax, [rax+10h]
0x1800062b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062ba  inc     r14d
0x1800062bd  mov     [rbp+37h+arg_28], r12
0x1800062c1  jmp     loc_180005FB6
0x1800062c6  mov     ecx, 3
0x1800062cb  int     29h; Win8: RtlFailFast(ecx)
0x1800062cd  mov     rax, [rax+58h]
0x1800062d1  mov     edx, 1
0x1800062d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062db  jmp     short loc_1800062E2
0x1800062dd  mov     ebx, 80070008h
0x1800062e2  mov     rcx, [rbp+37h+arg_28]
0x1800062e6  test    rcx, rcx
0x1800062e9  jz      short loc_1800062FB
0x1800062eb  mov     rax, [rcx]
0x1800062ee  mov     rax, [rax+10h]
0x1800062f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062f7  mov     [rbp+37h+arg_28], r12
0x1800062fb  mov     rcx, [rbp+37h+arg_38]
0x1800062ff  test    rcx, rcx
0x180006302  jz      short loc_180006310
0x180006304  mov     rax, [rcx]
0x180006307  mov     rax, [rax+10h]
0x18000630b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006310  mov     eax, ebx
0x180006312  add     rsp, 90h
0x180006319  pop     r15
0x18000631b  pop     r14
0x18000631d  pop     r12
0x18000631f  pop     rdi
0x180006320  pop     rsi
0x180006321  pop     rbx
0x180006322  pop     rbp
0x180006323  retn
```
