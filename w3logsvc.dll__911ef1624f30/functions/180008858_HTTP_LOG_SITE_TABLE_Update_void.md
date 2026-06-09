# HTTP_LOG_SITE_TABLE::Update(void)

- ea: `0x180008858`
- end: `0x180008c81`
- name: `?Update@HTTP_LOG_SITE_TABLE@@AEAAJXZ`
- size: `1065`
- prototype: `__int64 __fastcall(HTTP_LOG_SITE_TABLE *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007ed0`

## callees

- `0x180001048`
- `0x180005bd4`
- `0x180006ca8`
- `0x180006f4c`
- `0x1800070a0`
- `0x180007338`
- `0x180007cf0`
- `0x180007de4`
- `0x180007e20`
- `0x18000855c`
- `0x1800086a4`
- `0x180008730`
- `0x180008858`
- `0x18000e9a0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800089c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800089c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c47`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800088ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800088ca`
- `OLEAUT32!__imp_VariantInit` at `0x1800088d4`
- `OLEAUT32!__imp_VariantInit` at `0x1800088d4`
- `OLEAUT32!__imp_VariantClear` at `0x1800089cf`
- `OLEAUT32!__imp_VariantClear` at `0x1800089cf`
- `iisutil!PuDbgPrintError` at `0x180008940`
- `iisutil!PuDbgPrintError` at `0x1800089b8`
- `iisutil!PuDbgPrintError` at `0x180008940`
- `iisutil!PuDbgPrintError` at `0x1800089b8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008a63`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008a6d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008a63`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008a6d`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180008a59`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180008a59`

## string_xrefs

- `0x18000892f`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsitetable.cpp`
- `0x1800089a7`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsitetable.cpp`
- `0x180008923`: `HTTP_LOG_SITE_TABLE::Update`
- `0x18000899b`: `HTTP_LOG_SITE_TABLE::Update`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_SITE_TABLE::Update(HTTP_LOG_SITE_TABLE *this)
{
  RTL_SRWLOCK *v1; // r15
  struct HTTP_LOG_SITE_ENTRY *v3; // rsi
  unsigned int *v4; // rdi
  struct IAppHostAdminManager *v5; // rcx
  const unsigned __int16 *v6; // r8
  int Section; // ebx
  const unsigned __int16 *v8; // r8
  HTTP_LOG_FILE_CONFIG *v10; // rcx
  LOG_WRITER *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  int v14; // r9d
  int inserted; // eax
  __int64 v16; // r8
  int v17; // [rsp+20h] [rbp-99h]
  struct IAppHostElement *v18; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v19; // [rsp+48h] [rbp-71h] BYREF
  unsigned int v20; // [rsp+4Ch] [rbp-6Dh] BYREF
  struct HTTP_LOG_SITE_ENTRY *v21; // [rsp+50h] [rbp-69h] BYREF
  __int64 *v22; // [rsp+58h] [rbp-61h] BYREF
  HTTP_LOG_FILE_CONFIG *v23; // [rsp+60h] [rbp-59h] BYREF
  struct IAppHostElement *v24; // [rsp+68h] [rbp-51h] BYREF
  struct IAppHostElement *v25; // [rsp+70h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-41h] BYREF
  VARIANTARG v27; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int16 v28[8]; // [rsp+B0h] [rbp-9h] BYREF
  __int16 v29; // [rsp+C0h] [rbp+7h]

  v1 = (RTL_SRWLOCK *)((char *)this + 1096);
  v24 = 0;
  v22 = 0;
  v18 = 0;
  v25 = 0;
  v19 = 0;
  v3 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v4 = 0;
  v20 = 0;
  *(_OWORD *)v28 = 0;
  v29 = 0;
  v21 = 0;
  v23 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 137);
  VariantInit(&pvarg);
  v5 = (struct IAppHostAdminManager *)*((_QWORD *)this + 134);
  pvarg.vt = 19;
  Section = Config_GetSection(v5, L"system.applicationHost/log", v6, &v25);
  if ( Section < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsitetable.cpp",
        445,
        "HTTP_LOG_SITE_TABLE::Update",
        Section,
        " Failed to get section %S\n",
        L"system.applicationHost/log");
    goto LABEL_9;
  }
  Section = HTTP_LOG_FILE_CONFIG::CreateCentralLogConfigContext(v25, &v23);
  if ( Section < 0 )
    goto LABEL_8;
  Section = Config_GetSection(*((struct IAppHostAdminManager **)this + 134), L"system.applicationHost/sites", v8, &v24);
  if ( Section < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsitetable.cpp",
        467,
        "HTTP_LOG_SITE_TABLE::Update",
        Section,
        " Failed to get section %S\n",
        L"system.applicationHost/sites");
    goto LABEL_8;
  }
  Section = ((__int64 (__fastcall *)(struct IAppHostElement *, __int64 **))v24->lpVtbl->get_Collection)(v24, &v22);
  if ( Section < 0
    || (Section = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v22 + 24))(v22, &v19), Section < 0) )
  {
LABEL_8:
    v4 = (unsigned int *)v23;
LABEL_9:
    ReleaseSRWLockExclusive(v1);
    goto LABEL_10;
  }
  v4 = (unsigned int *)*((_QWORD *)this + 136);
  v10 = v23;
  *((_QWORD *)this + 136) = v23;
  HTTP_LOG_FILE_CONFIG::CalculateChange(v10, (struct HTTP_LOG_FILE_CONFIG *)v4);
  v11 = (LOG_WRITER *)*((_QWORD *)this + 135);
  if ( v11 )
  {
    Section = LOG_WRITER::UpdateConfig(v11, *((const struct HTTP_LOG_FILE_CONFIG_CONTEXT **)this + 136));
    if ( Section < 0 )
      goto LABEL_9;
  }
  pvarg.lVal = 0;
  if ( v19 )
  {
    do
    {
      v12 = *v22;
      v27 = pvarg;
      Section = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, struct IAppHostElement **))(v12 + 32))(
                  v22,
                  &v27,
                  &v18);
      if ( Section < 0 )
        goto LABEL_9;
      Section = Config_GetDWORDProperty(v18, L"id", &v20);
      if ( Section < 0 )
        goto LABEL_9;
      _snwprintf_s<9>(v28, 9, L"%08x", v20);
      v13 = HTTP_LOG_SITE_TABLE::ContainsNoLock(this, v28, &v21);
      v14 = *(_DWORD *)(*((_QWORD *)this + 136) + 12LL);
      if ( v13 )
      {
        v3 = v21;
        Section = HTTP_LOG_SITE_ENTRY::Update(v21, v18, v14);
        if ( Section < 0 )
          goto LABEL_9;
        (*(void (__fastcall **)(struct HTTP_LOG_SITE_ENTRY *))(*(_QWORD *)v3 + 8LL))(v3);
        v3 = 0;
        v21 = 0;
      }
      else
      {
        inserted = HTTP_LOG_SITE_TABLE::InsertNoLock(this, v28, v18, v14, v17);
        v3 = v21;
        Section = inserted;
        if ( inserted < 0 )
          goto LABEL_9;
      }
      ((void (__fastcall *)(struct IAppHostElement *))v18->lpVtbl->Release)(v18);
      v18 = 0;
      v29 = 0;
      *(_OWORD *)v28 = 0;
    }
    while ( ++pvarg.lVal < v19 );
  }
  HTTP_LOG_SITE_TABLE::Iterate(
    this,
    (int (*)(struct HTTP_LOG_SITE_ENTRY *, struct HTTP_LOG_SITE_TABLE *))HTTP_LOG_SITE_TABLE::UpdateEntries,
    0);
  ReleaseSRWLockExclusive(v1);
  v16 = *((_QWORD *)this + 136);
  if ( (*(_DWORD *)(v16 + 228) & 0x2000) != 0 )
    Section = HTTP_LOG_SITE_TABLE::OnLogFileModeChange(this, v4[56], *(unsigned int *)(v16 + 224));
LABEL_10:
  VariantClear(&pvarg);
  if ( v18 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v18->lpVtbl->Release)(v18);
    v18 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
    v22 = 0;
  }
  if ( v24 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v24->lpVtbl->Release)(v24);
    v24 = 0;
  }
  if ( v3 )
    (*(void (__fastcall **)(struct HTTP_LOG_SITE_ENTRY *))(*(_QWORD *)v3 + 8LL))(v3);
  if ( v25 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v25->lpVtbl->Release)(v25);
    v25 = 0;
  }
  if ( v4 )
  {
    MULTISZ::~MULTISZ((MULTISZ *)(v4 + 40));
    STRU::~STRU((STRU *)(v4 + 26));
    STRU::~STRU((STRU *)(v4 + 12));
    operator delete(v4);
  }
  return (unsigned int)Section;
}

```

## disassembly

```asm
0x180008858  push    rbp
0x18000885a  push    rbx
0x18000885b  push    rsi
0x18000885c  push    rdi
0x18000885d  push    r12
0x18000885f  push    r13
0x180008861  push    r14
0x180008863  push    r15
0x180008865  lea     rbp, [rsp-1Fh]
0x18000886a  sub     rsp, 0D8h
0x180008871  mov     rax, cs:__security_cookie
0x180008878  xor     rax, rsp
0x18000887b  mov     [rbp+57h+var_48], rax
0x18000887f  xor     r12d, r12d
0x180008882  lea     r15, [rcx+448h]
0x180008889  xorps   xmm0, xmm0
0x18000888c  mov     [rbp+57h+var_A8], r12
0x180008890  xor     eax, eax
0x180008892  mov     [rbp+57h+var_B8], r12
0x180008896  mov     r14, rcx
0x180008899  mov     [rbp+57h+var_D0], r12
0x18000889d  mov     rcx, r15; SRWLock
0x1800088a0  mov     [rbp+57h+var_A0], r12
0x1800088a4  mov     [rbp+57h+var_C8], r12d
0x1800088a8  mov     esi, r12d
0x1800088ab  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800088af  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800088b3  mov     edi, r12d
0x1800088b6  mov     [rbp+57h+var_C4], r12d
0x1800088ba  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800088be  mov     [rbp+57h+var_50], ax
0x1800088c2  mov     [rbp+57h+var_C0], r12
0x1800088c6  mov     [rbp+57h+var_B0], r12
0x1800088ca  call    cs:__imp_AcquireSRWLockExclusive
0x1800088d0  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800088d4  call    cs:__imp_VariantInit
0x1800088da  mov     rcx, [r14+430h]; struct IAppHostAdminManager *
0x1800088e1  lea     eax, [r12+13h]
0x1800088e6  lea     r13, aSystemApplicat; "system.applicationHost/log"
0x1800088ed  mov     word ptr [rbp+57h+pvarg], ax
0x1800088f1  mov     rdx, r13; unsigned __int16 *
0x1800088f4  lea     r9, [rbp+57h+var_A0]; struct IAppHostElement **
0x1800088f8  call    ?Config_GetSection@@YAJPEAUIAppHostAdminManager@@PEBG1PEAPEAUIAppHostElement@@@Z; Config_GetSection(IAppHostAdminManager *,ushort const *,ushort const *,IAppHostElement * *)
0x1800088fd  mov     ebx, eax
0x1800088ff  test    eax, eax
0x180008901  jns     short loc_180008948
0x180008903  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000890a  jz      loc_1800089C2
0x180008910  mov     rcx, cs:g_pDebug
0x180008917  lea     rax, aFailedToGetSec; " Failed to get section %S\n"
0x18000891e  mov     [rsp+110h+var_E0], r13
0x180008923  lea     r9, aHttpLogSiteTab; "HTTP_LOG_SITE_TABLE::Update"
0x18000892a  mov     [rsp+110h+var_E8], rax
0x18000892f  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180008936  mov     r8d, 1BDh
0x18000893c  mov     [rsp+110h+var_F0], ebx
0x180008940  call    cs:__imp_PuDbgPrintError
0x180008946  jmp     short loc_1800089C2
0x180008948  mov     rcx, [rbp+57h+var_A0]; struct IAppHostElement *
0x18000894c  lea     rdx, [rbp+57h+var_B0]; struct HTTP_LOG_FILE_CONFIG **
0x180008950  call    ?CreateCentralLogConfigContext@HTTP_LOG_FILE_CONFIG@@SAJPEAUIAppHostElement@@PEAPEAV1@@Z; HTTP_LOG_FILE_CONFIG::CreateCentralLogConfigContext(IAppHostElement *,HTTP_LOG_FILE_CONFIG * *)
0x180008955  mov     ebx, eax
0x180008957  test    eax, eax
0x180008959  js      short loc_1800089BE
0x18000895b  mov     rcx, [r14+430h]; struct IAppHostAdminManager *
0x180008962  lea     rdi, aSystemApplicat_0; "system.applicationHost/sites"
0x180008969  mov     rdx, rdi; unsigned __int16 *
0x18000896c  lea     r9, [rbp+57h+var_A8]; struct IAppHostElement **
0x180008970  call    ?Config_GetSection@@YAJPEAUIAppHostAdminManager@@PEBG1PEAPEAUIAppHostElement@@@Z; Config_GetSection(IAppHostAdminManager *,ushort const *,ushort const *,IAppHostElement * *)
0x180008975  mov     ebx, eax
0x180008977  test    eax, eax
0x180008979  jns     loc_180008A9D
0x18000897f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008986  jz      short loc_1800089BE
0x180008988  mov     rcx, cs:g_pDebug
0x18000898f  lea     rax, aFailedToGetSec; " Failed to get section %S\n"
0x180008996  mov     [rsp+110h+var_E0], rdi
0x18000899b  lea     r9, aHttpLogSiteTab; "HTTP_LOG_SITE_TABLE::Update"
0x1800089a2  mov     [rsp+110h+var_E8], rax
0x1800089a7  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800089ae  mov     r8d, 1D3h
0x1800089b4  mov     [rsp+110h+var_F0], ebx
0x1800089b8  call    cs:__imp_PuDbgPrintError
0x1800089be  mov     rdi, [rbp+57h+var_B0]
0x1800089c2  mov     rcx, r15; SRWLock
0x1800089c5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800089cb  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800089cf  call    cs:__imp_VariantClear
0x1800089d5  mov     rcx, [rbp+57h+var_D0]
0x1800089d9  test    rcx, rcx
0x1800089dc  jz      short loc_1800089EE
0x1800089de  mov     rax, [rcx]
0x1800089e1  mov     rax, [rax+10h]
0x1800089e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089ea  mov     [rbp+57h+var_D0], r12
0x1800089ee  mov     rcx, [rbp+57h+var_B8]
0x1800089f2  test    rcx, rcx
0x1800089f5  jz      short loc_180008A07
0x1800089f7  mov     rax, [rcx]
0x1800089fa  mov     rax, [rax+10h]
0x1800089fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a03  mov     [rbp+57h+var_B8], r12
0x180008a07  mov     rcx, [rbp+57h+var_A8]
0x180008a0b  test    rcx, rcx
0x180008a0e  jz      short loc_180008A20
0x180008a10  mov     rax, [rcx]
0x180008a13  mov     rax, [rax+10h]
0x180008a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a1c  mov     [rbp+57h+var_A8], r12
0x180008a20  test    rsi, rsi
0x180008a23  jz      short loc_180008A34
0x180008a25  mov     rax, [rsi]
0x180008a28  mov     rcx, rsi
0x180008a2b  mov     rax, [rax+8]
0x180008a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a34  mov     rcx, [rbp+57h+var_A0]
0x180008a38  test    rcx, rcx
0x180008a3b  jz      short loc_180008A4D
0x180008a3d  mov     rax, [rcx]
0x180008a40  mov     rax, [rax+10h]
0x180008a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a49  mov     [rbp+57h+var_A0], r12
0x180008a4d  test    rdi, rdi
0x180008a50  jz      short loc_180008A7B
0x180008a52  lea     rcx, [rdi+0A0h]
0x180008a59  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180008a5f  lea     rcx, [rdi+68h]
0x180008a63  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008a69  lea     rcx, [rdi+30h]
0x180008a6d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008a73  mov     rcx, rdi; Block
0x180008a76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008a7b  mov     eax, ebx
0x180008a7d  mov     rcx, [rbp+57h+var_48]
0x180008a81  xor     rcx, rsp; StackCookie
0x180008a84  call    __security_check_cookie
0x180008a89  add     rsp, 0D8h
0x180008a90  pop     r15
0x180008a92  pop     r14
0x180008a94  pop     r13
0x180008a96  pop     r12
0x180008a98  pop     rdi
0x180008a99  pop     rsi
0x180008a9a  pop     rbx
0x180008a9b  pop     rbp
0x180008a9c  retn
0x180008a9d  mov     rcx, [rbp+57h+var_A8]
0x180008aa1  lea     rdx, [rbp+57h+var_B8]
0x180008aa5  mov     rax, [rcx]
0x180008aa8  mov     rax, [rax+20h]
0x180008aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ab1  mov     ebx, eax
0x180008ab3  test    eax, eax
0x180008ab5  js      loc_1800089BE
0x180008abb  mov     rcx, [rbp+57h+var_B8]
0x180008abf  lea     rdx, [rbp+57h+var_C8]
0x180008ac3  mov     rax, [rcx]
0x180008ac6  mov     rax, [rax+18h]
0x180008aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008acf  mov     ebx, eax
0x180008ad1  test    eax, eax
0x180008ad3  js      loc_1800089BE
0x180008ad9  mov     rdi, [r14+440h]
0x180008ae0  mov     rcx, [rbp+57h+var_B0]; this
0x180008ae4  mov     rdx, rdi; struct HTTP_LOG_FILE_CONFIG *
0x180008ae7  mov     [r14+440h], rcx
0x180008aee  call    ?CalculateChange@HTTP_LOG_FILE_CONFIG@@QEAAXPEAV1@@Z; HTTP_LOG_FILE_CONFIG::CalculateChange(HTTP_LOG_FILE_CONFIG *)
0x180008af3  mov     rcx, [r14+438h]; this
0x180008afa  test    rcx, rcx
0x180008afd  jz      short loc_180008B15
0x180008aff  mov     rdx, [r14+440h]; struct HTTP_LOG_FILE_CONFIG_CONTEXT *
0x180008b06  call    ?UpdateConfig@LOG_WRITER@@QEAAJPEBVHTTP_LOG_FILE_CONFIG_CONTEXT@@@Z; LOG_WRITER::UpdateConfig(HTTP_LOG_FILE_CONFIG_CONTEXT const *)
0x180008b0b  mov     ebx, eax
0x180008b0d  test    eax, eax
0x180008b0f  js      loc_1800089C2
0x180008b15  mov     dword ptr [rbp+57h+pvarg+8], r12d
0x180008b19  cmp     [rbp+57h+var_C8], r12d
0x180008b1d  jbe     loc_180008C32
0x180008b23  mov     rcx, [rbp+57h+var_B8]
0x180008b27  lea     r8, [rbp+57h+var_D0]
0x180008b2b  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180008b2f  lea     rdx, [rbp+57h+var_80]
0x180008b33  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180008b38  mov     rax, [rcx]
0x180008b3b  movaps  [rbp+57h+var_80], xmm0
0x180008b3f  movsd   [rbp+57h+var_70], xmm1
0x180008b44  mov     rax, [rax+20h]
0x180008b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b4d  mov     ebx, eax
0x180008b4f  test    eax, eax
0x180008b51  js      loc_1800089C2
0x180008b57  mov     rcx, [rbp+57h+var_D0]; struct IAppHostElement *
0x180008b5b  lea     r8, [rbp+57h+var_C4]; unsigned int *
0x180008b5f  lea     rdx, aId; "id"
0x180008b66  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x180008b6b  mov     ebx, eax
0x180008b6d  test    eax, eax
0x180008b6f  js      loc_1800089C2
0x180008b75  mov     r9d, [rbp+57h+var_C4]
0x180008b79  lea     r8, a08x; "%08x"
0x180008b80  mov     edx, 9
0x180008b85  lea     rcx, [rbp+57h+var_60]
0x180008b89  call    ??$_snwprintf_s@$08@@YAHAEAY08G_KPEBGZZ; _snwprintf_s<9>(ushort (&)[9],unsigned __int64,ushort const *,...)
0x180008b8e  lea     r8, [rbp+57h+var_C0]; struct HTTP_LOG_SITE_ENTRY **
0x180008b92  mov     rcx, r14; this
0x180008b95  lea     rdx, [rbp+57h+var_60]; unsigned __int16 *
0x180008b99  call    ?ContainsNoLock@HTTP_LOG_SITE_TABLE@@AEAAHPEBGPEAPEAVHTTP_LOG_SITE_ENTRY@@@Z; HTTP_LOG_SITE_TABLE::ContainsNoLock(ushort const *,HTTP_LOG_SITE_ENTRY * *)
0x180008b9e  mov     rcx, [r14+440h]
0x180008ba5  mov     r9d, [rcx+0Ch]; int
0x180008ba9  test    eax, eax
0x180008bab  jz      short loc_180008BE2
0x180008bad  mov     rsi, [rbp+57h+var_C0]
0x180008bb1  mov     r8d, r9d; int
0x180008bb4  mov     rdx, [rbp+57h+var_D0]; struct IAppHostElement *
0x180008bb8  mov     rcx, rsi; this
0x180008bbb  call    ?Update@HTTP_LOG_SITE_ENTRY@@QEAAJPEAUIAppHostElement@@H@Z; HTTP_LOG_SITE_ENTRY::Update(IAppHostElement *,int)
0x180008bc0  mov     ebx, eax
0x180008bc2  test    eax, eax
0x180008bc4  js      loc_1800089C2
0x180008bca  mov     rax, [rsi]
0x180008bcd  mov     rcx, rsi
0x180008bd0  mov     rax, [rax+8]
0x180008bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bd9  mov     rsi, r12
0x180008bdc  mov     [rbp+57h+var_C0], r12
0x180008be0  jmp     short loc_180008C00
0x180008be2  mov     r8, [rbp+57h+var_D0]; struct IAppHostElement *
0x180008be6  lea     rdx, [rbp+57h+var_60]; unsigned __int16 *
0x180008bea  mov     rcx, r14; this
0x180008bed  call    ?InsertNoLock@HTTP_LOG_SITE_TABLE@@AEAAJPEBGPEAUIAppHostElement@@HH@Z; HTTP_LOG_SITE_TABLE::InsertNoLock(ushort const *,IAppHostElement *,int,int)
0x180008bf2  mov     rsi, [rbp+57h+var_C0]
0x180008bf6  mov     ebx, eax
0x180008bf8  test    eax, eax
0x180008bfa  js      loc_1800089C2
0x180008c00  mov     rcx, [rbp+57h+var_D0]
0x180008c04  mov     rax, [rcx]
0x180008c07  mov     rax, [rax+10h]
0x180008c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c10  xor     eax, eax
0x180008c12  mov     [rbp+57h+var_D0], r12
0x180008c16  mov     [rbp+57h+var_50], ax
0x180008c1a  xorps   xmm0, xmm0
0x180008c1d  mov     eax, dword ptr [rbp+57h+pvarg+8]
0x180008c20  inc     eax
0x180008c22  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180008c26  mov     dword ptr [rbp+57h+pvarg+8], eax
0x180008c29  cmp     eax, [rbp+57h+var_C8]
0x180008c2c  jb      loc_180008B23
0x180008c32  xor     r8d, r8d; int
0x180008c35  lea     rdx, ?UpdateEntries@HTTP_LOG_SITE_TABLE@@CAJPEAVHTTP_LOG_SITE_ENTRY@@PEAV1@@Z; int (*)(struct HTTP_LOG_SITE_ENTRY *, struct HTTP_LOG_SITE_TABLE *)
0x180008c3c  mov     rcx, r14; this
0x180008c3f  call    ?Iterate@HTTP_LOG_SITE_TABLE@@AEAAJP6AJPEAVHTTP_LOG_SITE_ENTRY@@PEAV1@@ZH@Z; HTTP_LOG_SITE_TABLE::Iterate(long (*)(HTTP_LOG_SITE_ENTRY *,HTTP_LOG_SITE_TABLE *),int)
0x180008c44  mov     rcx, r15; SRWLock
0x180008c47  call    cs:__imp_ReleaseSRWLockExclusive
0x180008c4d  mov     r8, [r14+440h]
0x180008c54  test    dword ptr [r8+0E4h], 2000h
0x180008c5f  jz      loc_1800089CB
0x180008c65  mov     r8d, [r8+0E0h]
0x180008c6c  mov     rcx, r14
0x180008c6f  mov     edx, [rdi+0E0h]
0x180008c75  call    ?OnLogFileModeChange@HTTP_LOG_SITE_TABLE@@AEAAJW4HTTP_LOG_FILE_MODE@@0@Z; HTTP_LOG_SITE_TABLE::OnLogFileModeChange(HTTP_LOG_FILE_MODE,HTTP_LOG_FILE_MODE)
0x180008c7a  mov     ebx, eax
0x180008c7c  jmp     loc_1800089CB
```
