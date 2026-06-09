# HTTP_LOG_SITE_TABLE::Initialize(IAppHostAdminManager *)

- ea: `0x180008230`
- end: `0x180008556`
- name: `?Initialize@HTTP_LOG_SITE_TABLE@@QEAAJPEAUIAppHostAdminManager@@@Z`
- size: `806`
- prototype: `__int64 __fastcall(HTTP_LOG_SITE_TABLE *__hidden this, struct IAppHostAdminManager *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000bfc0`

## callees

- `0x180006f4c`
- `0x1800070a0`
- `0x180007338`
- `0x180007de4`
- `0x180008230`
- `0x18000855c`
- `0x18000e9a0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800083fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800083fb`
- `OLEAUT32!__imp_VariantInit` at `0x18000828d`
- `OLEAUT32!__imp_VariantInit` at `0x18000828d`
- `OLEAUT32!__imp_VariantClear` at `0x1800084d2`
- `OLEAUT32!__imp_VariantClear` at `0x1800084d2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800083eb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800083eb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800083a4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800083a4`
- `iisutil!PuDbgPrintError` at `0x1800082fb`
- `iisutil!PuDbgPrintError` at `0x1800082fb`

## string_xrefs

- `0x1800082f0`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsitetable.cpp`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_SITE_TABLE::Initialize(HTTP_LOG_SITE_TABLE *this, struct IAppHostAdminManager *a2)
{
  const wchar_t *v4; // rsi
  const unsigned __int16 *v5; // r8
  int Section; // ebx
  __int64 v7; // r8
  const unsigned __int16 *v8; // r8
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int LastError; // eax
  __int64 v11; // rax
  int v13; // [rsp+20h] [rbp-89h]
  unsigned int v14; // [rsp+40h] [rbp-69h] BYREF
  struct IAppHostElement *v15; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v16; // [rsp+50h] [rbp-59h] BYREF
  __int64 *v17; // [rsp+58h] [rbp-51h] BYREF
  struct IAppHostElement *v18; // [rsp+60h] [rbp-49h] BYREF
  struct IAppHostElement *v19; // [rsp+68h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-39h] BYREF
  VARIANTARG v21; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int16 v22[8]; // [rsp+B0h] [rbp+7h] BYREF
  __int16 v23; // [rsp+C0h] [rbp+17h]

  v18 = 0;
  v17 = 0;
  v15 = 0;
  v19 = 0;
  v14 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v16 = 0;
  *(_OWORD *)v22 = 0;
  v23 = 0;
  VariantInit(&pvarg);
  *((_QWORD *)this + 134) = a2;
  v4 = L"system.applicationHost/log";
  pvarg.vt = 19;
  Section = Config_GetSection(a2, L"system.applicationHost/log", v5, &v19);
  if ( Section < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_20;
    v7 = 185;
    goto LABEL_4;
  }
  Section = HTTP_LOG_FILE_CONFIG::CreateCentralLogConfigContext(v19, (struct HTTP_LOG_FILE_CONFIG **)this + 136);
  if ( Section >= 0 )
  {
    v4 = L"system.applicationHost/sites";
    Section = Config_GetSection(
                *((struct IAppHostAdminManager **)this + 134),
                L"system.applicationHost/sites",
                v8,
                &v18);
    if ( Section >= 0 )
    {
      Section = ((__int64 (__fastcall *)(struct IAppHostElement *, __int64 **))v18->lpVtbl->get_Collection)(v18, &v17);
      if ( Section >= 0 )
      {
        Section = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v17 + 24))(v17, &v14);
        if ( Section >= 0 )
        {
          ThreadpoolTimer = CreateThreadpoolTimer(
                              (PTP_TIMER_CALLBACK)HTTP_LOG_SITE_TABLE::FlushAllWritersTimerCallback,
                              this,
                              0);
          *((_QWORD *)this + 138) = ThreadpoolTimer;
          if ( ThreadpoolTimer )
          {
            *((_QWORD *)this + 139) = -300000000;
            SetThreadpoolTimer(ThreadpoolTimer, (PFILETIME)this + 139, 0, 0);
            AcquireSRWLockExclusive((PSRWLOCK)this + 137);
            for ( pvarg.lVal = 0; pvarg.lVal < v14; ++pvarg.lVal )
            {
              v11 = *v17;
              v21 = pvarg;
              Section = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, struct IAppHostElement **))(v11 + 32))(
                          v17,
                          &v21,
                          &v15);
              if ( Section < 0 )
                break;
              Section = Config_GetDWORDProperty(v15, L"id", &v16);
              if ( Section < 0 )
                break;
              _snwprintf_s<9>(v22, 9, L"%08x", v16);
              Section = HTTP_LOG_SITE_TABLE::InsertNoLock(
                          this,
                          v22,
                          v15,
                          *(_DWORD *)(*((_QWORD *)this + 136) + 12LL),
                          v13);
              if ( Section < 0 )
                break;
              ((void (__fastcall *)(struct IAppHostElement *))v15->lpVtbl->Release)(v15);
              v15 = 0;
              v23 = 0;
              *(_OWORD *)v22 = 0;
            }
            ReleaseSRWLockExclusive((PSRWLOCK)this + 137);
          }
          else
          {
            LastError = GetLastError();
            Section = LastError;
            if ( LastError > 0 )
              Section = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v7 = 207;
LABEL_4:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsitetable.cpp",
        v7,
        "HTTP_LOG_SITE_TABLE::Initialize",
        Section,
        " Failed to get section %S\n",
        v4);
    }
  }
LABEL_20:
  VariantClear(&pvarg);
  if ( v15 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v15->lpVtbl->Release)(v15);
    v15 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
    v17 = 0;
  }
  if ( v18 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v18->lpVtbl->Release)(v18);
    v18 = 0;
  }
  if ( v19 )
    ((void (__fastcall *)(struct IAppHostElement *))v19->lpVtbl->Release)(v19);
  return (unsigned int)Section;
}

```

## disassembly

```asm
0x180008230  push    rbp
0x180008232  push    rbx
0x180008233  push    rsi
0x180008234  push    rdi
0x180008235  push    r14
0x180008237  push    r15
0x180008239  lea     rbp, [rsp-2Fh]
0x18000823e  sub     rsp, 0D8h
0x180008245  mov     rax, cs:__security_cookie
0x18000824c  xor     rax, rsp
0x18000824f  mov     [rbp+57h+var_38], rax
0x180008253  xor     r15d, r15d
0x180008256  xorps   xmm0, xmm0
0x180008259  xor     eax, eax
0x18000825b  mov     [rbp+57h+var_A0], r15
0x18000825f  mov     rdi, rcx
0x180008262  mov     [rbp+57h+var_A8], r15
0x180008266  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000826a  mov     [rbp+57h+var_B8], r15
0x18000826e  mov     [rbp+57h+var_98], r15
0x180008272  mov     rbx, rdx
0x180008275  mov     [rbp+57h+var_C0], r15d
0x180008279  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18000827d  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180008281  mov     [rbp+57h+var_B0], r15d
0x180008285  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180008289  mov     [rbp+57h+var_40], ax
0x18000828d  call    cs:__imp_VariantInit
0x180008293  lea     eax, [r15+13h]
0x180008297  mov     [rdi+430h], rbx
0x18000829e  lea     rsi, aSystemApplicat; "system.applicationHost/log"
0x1800082a5  mov     word ptr [rbp+57h+pvarg], ax
0x1800082a9  mov     rdx, rsi; unsigned __int16 *
0x1800082ac  lea     r9, [rbp+57h+var_98]; struct IAppHostElement **
0x1800082b0  mov     rcx, rbx; struct IAppHostAdminManager *
0x1800082b3  call    ?Config_GetSection@@YAJPEAUIAppHostAdminManager@@PEBG1PEAPEAUIAppHostElement@@@Z; Config_GetSection(IAppHostAdminManager *,ushort const *,ushort const *,IAppHostElement * *)
0x1800082b8  mov     ebx, eax
0x1800082ba  test    eax, eax
0x1800082bc  jns     short loc_180008306
0x1800082be  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800082c5  jz      loc_1800084CE
0x1800082cb  mov     r8d, 0B9h
0x1800082d1  mov     rcx, cs:g_pDebug
0x1800082d8  lea     rax, aFailedToGetSec; " Failed to get section %S\n"
0x1800082df  mov     [rsp+100h+var_D0], rsi
0x1800082e4  lea     r9, aHttpLogSiteTab_0; "HTTP_LOG_SITE_TABLE::Initialize"
0x1800082eb  mov     [rsp+100h+var_D8], rax
0x1800082f0  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800082f7  mov     [rsp+100h+var_E0], ebx
0x1800082fb  call    cs:__imp_PuDbgPrintError
0x180008301  jmp     loc_1800084CE
0x180008306  mov     rcx, [rbp+57h+var_98]; struct IAppHostElement *
0x18000830a  lea     r14, [rdi+440h]
0x180008311  mov     rdx, r14; struct HTTP_LOG_FILE_CONFIG **
0x180008314  call    ?CreateCentralLogConfigContext@HTTP_LOG_FILE_CONFIG@@SAJPEAUIAppHostElement@@PEAPEAV1@@Z; HTTP_LOG_FILE_CONFIG::CreateCentralLogConfigContext(IAppHostElement *,HTTP_LOG_FILE_CONFIG * *)
0x180008319  mov     ebx, eax
0x18000831b  test    eax, eax
0x18000831d  js      loc_1800084CE
0x180008323  mov     rcx, [rdi+430h]; struct IAppHostAdminManager *
0x18000832a  lea     rsi, aSystemApplicat_0; "system.applicationHost/sites"
0x180008331  mov     rdx, rsi; unsigned __int16 *
0x180008334  lea     r9, [rbp+57h+var_A0]; struct IAppHostElement **
0x180008338  call    ?Config_GetSection@@YAJPEAUIAppHostAdminManager@@PEBG1PEAPEAUIAppHostElement@@@Z; Config_GetSection(IAppHostAdminManager *,ushort const *,ushort const *,IAppHostElement * *)
0x18000833d  mov     ebx, eax
0x18000833f  test    eax, eax
0x180008341  jns     short loc_18000835B
0x180008343  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000834a  jz      loc_1800084CE
0x180008350  mov     r8d, 0CFh
0x180008356  jmp     loc_1800082D1
0x18000835b  mov     rcx, [rbp+57h+var_A0]
0x18000835f  lea     rdx, [rbp+57h+var_A8]
0x180008363  mov     rax, [rcx]
0x180008366  mov     rax, [rax+20h]
0x18000836a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000836f  mov     ebx, eax
0x180008371  test    eax, eax
0x180008373  js      loc_1800084CE
0x180008379  mov     rcx, [rbp+57h+var_A8]
0x18000837d  lea     rdx, [rbp+57h+var_C0]
0x180008381  mov     rax, [rcx]
0x180008384  mov     rax, [rax+18h]
0x180008388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000838d  mov     ebx, eax
0x18000838f  test    eax, eax
0x180008391  js      loc_1800084CE
0x180008397  xor     r8d, r8d; pcbe
0x18000839a  lea     rcx, ?FlushAllWritersTimerCallback@HTTP_LOG_SITE_TABLE@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800083a1  mov     rdx, rdi; pv
0x1800083a4  call    cs:__imp_CreateThreadpoolTimer
0x1800083aa  mov     [rdi+450h], rax
0x1800083b1  test    rax, rax
0x1800083b4  jnz     short loc_1800083D4
0x1800083b6  call    cs:__imp_GetLastError
0x1800083bc  mov     ebx, eax
0x1800083be  test    eax, eax
0x1800083c0  jle     loc_1800084CE
0x1800083c6  movzx   ebx, ax
0x1800083c9  or      ebx, 80070000h
0x1800083cf  jmp     loc_1800084CE
0x1800083d4  lea     rdx, [rdi+458h]; pftDueTime
0x1800083db  xor     r9d, r9d; msWindowLength
0x1800083de  xor     r8d, r8d; msPeriod
0x1800083e1  mov     qword ptr [rdx], 0FFFFFFFFEE1E5D00h
0x1800083e8  mov     rcx, rax; pti
0x1800083eb  call    cs:__imp_SetThreadpoolTimer
0x1800083f1  lea     rsi, [rdi+448h]
0x1800083f8  mov     rcx, rsi; SRWLock
0x1800083fb  call    cs:__imp_AcquireSRWLockExclusive
0x180008401  mov     dword ptr [rbp+57h+pvarg+8], r15d
0x180008405  cmp     [rbp+57h+var_C0], r15d
0x180008409  jbe     loc_1800084C5
0x18000840f  mov     rcx, [rbp+57h+var_A8]
0x180008413  lea     r8, [rbp+57h+var_B8]
0x180008417  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18000841b  lea     rdx, [rbp+57h+var_70]
0x18000841f  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180008424  mov     rax, [rcx]
0x180008427  movaps  [rbp+57h+var_70], xmm0
0x18000842b  movsd   [rbp+57h+var_60], xmm1
0x180008430  mov     rax, [rax+20h]
0x180008434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008439  mov     ebx, eax
0x18000843b  test    eax, eax
0x18000843d  js      loc_1800084C5
0x180008443  mov     rcx, [rbp+57h+var_B8]; struct IAppHostElement *
0x180008447  lea     r8, [rbp+57h+var_B0]; unsigned int *
0x18000844b  lea     rdx, aId; "id"
0x180008452  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x180008457  mov     ebx, eax
0x180008459  test    eax, eax
0x18000845b  js      short loc_1800084C5
0x18000845d  mov     r9d, [rbp+57h+var_B0]
0x180008461  lea     r8, a08x; "%08x"
0x180008468  mov     edx, 9
0x18000846d  lea     rcx, [rbp+57h+var_50]
0x180008471  call    ??$_snwprintf_s@$08@@YAHAEAY08G_KPEBGZZ; _snwprintf_s<9>(ushort (&)[9],unsigned __int64,ushort const *,...)
0x180008476  mov     r9, [r14]
0x180008479  lea     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x18000847d  mov     r8, [rbp+57h+var_B8]; struct IAppHostElement *
0x180008481  mov     rcx, rdi; this
0x180008484  mov     r9d, [r9+0Ch]; int
0x180008488  call    ?InsertNoLock@HTTP_LOG_SITE_TABLE@@AEAAJPEBGPEAUIAppHostElement@@HH@Z; HTTP_LOG_SITE_TABLE::InsertNoLock(ushort const *,IAppHostElement *,int,int)
0x18000848d  mov     ebx, eax
0x18000848f  test    eax, eax
0x180008491  js      short loc_1800084C5
0x180008493  mov     rcx, [rbp+57h+var_B8]
0x180008497  mov     rax, [rcx]
0x18000849a  mov     rax, [rax+10h]
0x18000849e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084a3  xor     eax, eax
0x1800084a5  mov     [rbp+57h+var_B8], r15
0x1800084a9  mov     [rbp+57h+var_40], ax
0x1800084ad  xorps   xmm0, xmm0
0x1800084b0  mov     eax, dword ptr [rbp+57h+pvarg+8]
0x1800084b3  inc     eax
0x1800084b5  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1800084b9  mov     dword ptr [rbp+57h+pvarg+8], eax
0x1800084bc  cmp     eax, [rbp+57h+var_C0]
0x1800084bf  jb      loc_18000840F
0x1800084c5  mov     rcx, rsi; SRWLock
0x1800084c8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800084ce  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800084d2  call    cs:__imp_VariantClear
0x1800084d8  mov     rcx, [rbp+57h+var_B8]
0x1800084dc  test    rcx, rcx
0x1800084df  jz      short loc_1800084F1
0x1800084e1  mov     rax, [rcx]
0x1800084e4  mov     rax, [rax+10h]
0x1800084e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084ed  mov     [rbp+57h+var_B8], r15
0x1800084f1  mov     rcx, [rbp+57h+var_A8]
0x1800084f5  test    rcx, rcx
0x1800084f8  jz      short loc_18000850A
0x1800084fa  mov     rax, [rcx]
0x1800084fd  mov     rax, [rax+10h]
0x180008501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008506  mov     [rbp+57h+var_A8], r15
0x18000850a  mov     rcx, [rbp+57h+var_A0]
0x18000850e  test    rcx, rcx
0x180008511  jz      short loc_180008523
0x180008513  mov     rax, [rcx]
0x180008516  mov     rax, [rax+10h]
0x18000851a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000851f  mov     [rbp+57h+var_A0], r15
0x180008523  mov     rcx, [rbp+57h+var_98]
0x180008527  test    rcx, rcx
0x18000852a  jz      short loc_180008538
0x18000852c  mov     rax, [rcx]
0x18000852f  mov     rax, [rax+10h]
0x180008533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008538  mov     eax, ebx
0x18000853a  mov     rcx, [rbp+57h+var_38]
0x18000853e  xor     rcx, rsp; StackCookie
0x180008541  call    __security_check_cookie
0x180008546  add     rsp, 0D8h
0x18000854d  pop     r15
0x18000854f  pop     r14
0x180008551  pop     rdi
0x180008552  pop     rsi
0x180008553  pop     rbx
0x180008554  pop     rbp
0x180008555  retn
```
