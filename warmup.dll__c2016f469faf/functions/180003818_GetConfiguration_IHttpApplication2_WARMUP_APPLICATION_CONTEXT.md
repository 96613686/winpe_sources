# GetConfiguration(IHttpApplication2 *,WARMUP_APPLICATION_CONTEXT *)

- ea: `0x180003818`
- end: `0x180003c6c`
- name: `?GetConfiguration@@YAJPEAVIHttpApplication2@@PEAVWARMUP_APPLICATION_CONTEXT@@@Z`
- size: `1108`
- prototype: `__int64 __fastcall(struct IHttpApplication2 *, struct WARMUP_APPLICATION_CONTEXT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180003398`

## callees

- `0x180001008`
- `0x180001048`
- `0x180002924`
- `0x1800029a8`
- `0x1800029f0`
- `0x180002bd8`
- `0x180003818`
- `0x180004480`
- `0x180004fe0`
- `0x180006010`

## import_xrefs

- `msvcrt!wcstoul` at `0x1800038b9`
- `msvcrt!wcstoul` at `0x1800038b9`
- `msvcrt!wcsstr` at `0x18000389a`
- `msvcrt!wcsstr` at `0x1800038cf`
- `msvcrt!wcsstr` at `0x18000389a`
- `msvcrt!wcsstr` at `0x1800038cf`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003988`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003b17`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003988`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003b17`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000396b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003af1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000396b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003af1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c03`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c0d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c17`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c21`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c33`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c3d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c03`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c0d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c17`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c21`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c33`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c3d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003867`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003871`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003a58`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003a62`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003a6c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003a79`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003867`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003871`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003a58`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003a62`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003a6c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003a79`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003953`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003a9a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003ada`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003b4c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003953`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003a9a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003ada`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003b4c`

## pseudocode

```c
__int64 __fastcall GetConfiguration(struct IHttpApplication2 *a1, struct WARMUP_APPLICATION_CONTEXT *a2)
{
  char *v4; // rsi
  __int64 v5; // rax
  const wchar_t *v6; // rdi
  wchar_t *v7; // rax
  int AdminElement; // ebx
  unsigned int v9; // r15d
  wchar_t *v10; // rax
  const unsigned __int16 *v11; // r13
  const unsigned __int16 *v12; // rbx
  struct IAppHostAdminManager *v13; // rax
  unsigned int v14; // r14d
  char *v15; // rax
  char *v16; // rdi
  unsigned int v18; // [rsp+30h] [rbp-89h] BYREF
  struct IAppHostElement *v19; // [rsp+38h] [rbp-81h] BYREF
  struct IAppHostElement *v20; // [rsp+40h] [rbp-79h] BYREF
  int v21; // [rsp+48h] [rbp-71h] BYREF
  struct IAppHostElementCollection *v22; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-61h]
  _BYTE v24[32]; // [rsp+60h] [rbp-59h] BYREF
  wchar_t *Destination; // [rsp+80h] [rbp-39h]
  int v26; // [rsp+90h] [rbp-29h]
  _BYTE v27[32]; // [rsp+98h] [rbp-21h] BYREF
  const unsigned __int16 *v28; // [rsp+B8h] [rbp-1h]
  int v29; // [rsp+C8h] [rbp+Fh]

  v20 = 0;
  v19 = 0;
  v22 = 0;
  v4 = 0;
  STRU::STRU((STRU *)v27);
  STRU::STRU((STRU *)v24);
  v5 = *(_QWORD *)a1;
  v21 = 0;
  v18 = 0;
  v6 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IHttpApplication2 *))(v5 + 8))(a1);
  v7 = wcsstr(v6, L"/LM/W3SVC/");
  if ( !v7 )
  {
    AdminElement = -2147418113;
    goto LABEL_30;
  }
  v9 = wcstoul(v7 + 10, 0, 10);
  v23 = v9;
  v10 = wcsstr(v6, L"/ROOT");
  v11 = v10 + 5;
  if ( !v10 )
    v11 = 0;
  v12 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpApplication2 *))(*(_QWORD *)a1 + 16LL))(a1);
  v13 = (struct IAppHostAdminManager *)(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pServer + 56LL))(g_pServer);
  AdminElement = GetAdminElement(v13, v12, L"system.webServer/applicationInitialization", &v20);
  if ( AdminElement < 0 )
    goto LABEL_30;
  AdminElement = GetConfigString(v20, L"remapManagedRequestsTo", (struct STRU *)v27);
  if ( AdminElement < 0 )
    goto LABEL_30;
  if ( v29 )
  {
    AdminElement = STRU::Copy((STRU *)v24, L"/");
    if ( AdminElement < 0 )
      goto LABEL_30;
    STRU::Append((STRU *)v24, v28);
    AdminElement = NormalizeUrlWPreserveQueryString(Destination);
    if ( AdminElement < 0 )
      goto LABEL_30;
    STRU::SyncWithBuffer((STRU *)v24);
  }
  AdminElement = GetConfigBool(v20, L"doAppInitAfterRestart", &v21);
  if ( AdminElement >= 0 )
  {
    AdminElement = (*(__int64 (__fastcall **)(struct WARMUP_APPLICATION_CONTEXT *, const unsigned __int16 *, unsigned __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
                     a2,
                     v11,
                     (unsigned __int64)Destination & -(__int64)(v26 != 0),
                     (unsigned int)v21);
    if ( AdminElement >= 0 )
    {
      AdminElement = ((__int64 (__fastcall *)(struct IAppHostElement *, struct IAppHostElementCollection **))v20->lpVtbl->get_Collection)(
                       v20,
                       &v22);
      if ( AdminElement >= 0 )
      {
        AdminElement = ((__int64 (__fastcall *)(struct IAppHostElementCollection *, unsigned int *))v22->lpVtbl->get_Count)(
                         v22,
                         &v18);
        if ( AdminElement >= 0 )
        {
          v14 = 0;
          if ( v18 )
          {
            while ( 1 )
            {
              AdminElement = GetCollectionElement(v22, v14, &v19);
              if ( AdminElement < 0 )
                break;
              v15 = (char *)operator new(0xF8u);
              v16 = v15;
              if ( !v15 )
              {
                AdminElement = -2147024882;
                break;
              }
              STRU::STRU((STRU *)(v15 + 8));
              STRU::STRU((STRU *)(v16 + 64));
              STRU::STRU((STRU *)(v16 + 120));
              STRU::STRU((STRU *)(v16 + 176));
              *(_DWORD *)v16 = v9;
              *((_QWORD *)v16 + 30) = v16 + 232;
              *((_QWORD *)v16 + 29) = v16 + 232;
              AdminElement = STRU::Copy((STRU *)(v16 + 8), v11);
              v4 = v16;
              if ( AdminElement < 0 )
                goto LABEL_30;
              AdminElement = GetConfigString(v19, L"initializationPage", (struct STRU *)v27);
              if ( AdminElement < 0 )
                goto LABEL_30;
              AdminElement = STRU::Copy((STRU *)(v16 + 64), L"/");
              if ( AdminElement < 0 )
                goto LABEL_30;
              AdminElement = STRU::Append((STRU *)(v16 + 64), v28);
              if ( AdminElement < 0 )
                goto LABEL_30;
              AdminElement = NormalizeUrlWPreserveQueryString(*((wchar_t **)v16 + 12));
              if ( AdminElement < 0 )
                goto LABEL_30;
              STRU::SyncWithBuffer((STRU *)(v16 + 64));
              AdminElement = GetConfigString(v19, L"hostName", (struct STRU *)(v16 + 120));
              if ( AdminElement < 0 )
                goto LABEL_30;
              if ( !*((_DWORD *)v16 + 42) )
              {
                AdminElement = STRU::Copy((STRU *)(v16 + 120), L"localhost");
                if ( AdminElement < 0 )
                  goto LABEL_30;
              }
              (*(void (__fastcall **)(struct WARMUP_APPLICATION_CONTEXT *, char *))(*(_QWORD *)a2 + 16LL))(a2, v16);
              v4 = 0;
              ((void (__fastcall *)(struct IAppHostElement *))v19->lpVtbl->Release)(v19);
              v9 = v23;
              ++v14;
              v19 = 0;
              if ( v14 >= v18 )
                goto LABEL_32;
            }
            v4 = 0;
          }
        }
      }
    }
  }
LABEL_30:
  if ( v19 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v19->lpVtbl->Release)(v19);
    v19 = 0;
  }
LABEL_32:
  if ( v22 )
  {
    ((void (__fastcall *)(struct IAppHostElementCollection *))v22->lpVtbl->Release)(v22);
    v22 = 0;
  }
  if ( v20 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v20->lpVtbl->Release)(v20);
    v20 = 0;
  }
  if ( v4 )
  {
    STRU::~STRU((STRU *)(v4 + 176));
    STRU::~STRU((STRU *)(v4 + 120));
    STRU::~STRU((STRU *)(v4 + 64));
    STRU::~STRU((STRU *)(v4 + 8));
    operator delete(v4);
  }
  STRU::~STRU((STRU *)v24);
  STRU::~STRU((STRU *)v27);
  return (unsigned int)AdminElement;
}

```

## disassembly

```asm
0x180003818  mov     [rsp-8+arg_10], rbx
0x18000381d  push    rbp
0x18000381e  push    rsi
0x18000381f  push    rdi
0x180003820  push    r12
0x180003822  push    r13
0x180003824  push    r14
0x180003826  push    r15
0x180003828  lea     rbp, [rsp-27h]
0x18000382d  sub     rsp, 0E0h
0x180003834  mov     rax, cs:__security_cookie
0x18000383b  xor     rax, rsp
0x18000383e  mov     [rbp+57h+var_40], rax
0x180003842  mov     rbx, rcx
0x180003845  mov     [rbp+57h+var_D0], 0
0x18000384d  lea     rcx, [rbp+57h+var_78]
0x180003851  mov     [rsp+110h+var_D8], 0
0x18000385a  mov     r12, rdx
0x18000385d  mov     [rbp+57h+var_C0], 0
0x180003865  xor     esi, esi
0x180003867  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000386d  lea     rcx, [rbp+57h+var_B0]
0x180003871  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003877  mov     rax, [rbx]
0x18000387a  mov     rcx, rbx
0x18000387d  mov     [rbp+57h+var_C8], esi
0x180003880  mov     [rsp+110h+var_E0], esi
0x180003884  mov     rax, [rax+8]
0x180003888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000388d  lea     rdx, aLmW3svc; "/LM/W3SVC/"
0x180003894  mov     rcx, rax; Str
0x180003897  mov     rdi, rax
0x18000389a  call    cs:__imp_wcsstr
0x1800038a0  test    rax, rax
0x1800038a3  jnz     short loc_1800038AF
0x1800038a5  mov     ebx, 8000FFFFh
0x1800038aa  jmp     loc_180003B9E
0x1800038af  xor     edx, edx; EndPtr
0x1800038b1  lea     rcx, [rax+14h]; String
0x1800038b5  lea     r8d, [rdx+0Ah]; Radix
0x1800038b9  call    cs:__imp_wcstoul
0x1800038bf  lea     rdx, aRoot; "/ROOT"
0x1800038c6  mov     rcx, rdi; Str
0x1800038c9  mov     r15d, eax
0x1800038cc  mov     [rbp+57h+var_B8], eax
0x1800038cf  call    cs:__imp_wcsstr
0x1800038d5  mov     rdx, [rbx]
0x1800038d8  mov     rcx, rbx
0x1800038db  test    rax, rax
0x1800038de  lea     r13, [rax+0Ah]
0x1800038e2  cmovz   r13, rax
0x1800038e6  mov     rax, [rdx+10h]
0x1800038ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038ef  mov     rcx, cs:?g_pServer@@3PEAVIHttpServer@@EA; IHttpServer * g_pServer
0x1800038f6  mov     rbx, rax
0x1800038f9  mov     rdx, [rcx]
0x1800038fc  mov     rax, [rdx+38h]
0x180003900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003905  lea     r9, [rbp+57h+var_D0]; struct IAppHostElement **
0x180003909  mov     rdx, rbx; unsigned __int16 *
0x18000390c  lea     r8, aSystemWebserve; "system.webServer/applicationInitializat"...
0x180003913  mov     rcx, rax; struct IAppHostAdminManager *
0x180003916  call    ?GetAdminElement@@YAJPEAUIAppHostAdminManager@@PEBG1PEAPEAUIAppHostElement@@@Z; GetAdminElement(IAppHostAdminManager *,ushort const *,ushort const *,IAppHostElement * *)
0x18000391b  mov     ebx, eax
0x18000391d  test    eax, eax
0x18000391f  js      loc_180003B9E
0x180003925  mov     rcx, [rbp+57h+var_D0]; struct IAppHostElement *
0x180003929  lea     r8, [rbp+57h+var_78]; struct STRU *
0x18000392d  lea     rdx, aRemapmanagedre; "remapManagedRequestsTo"
0x180003934  call    ?GetConfigString@@YAJPEAUIAppHostElement@@PEBGPEAVSTRU@@@Z; GetConfigString(IAppHostElement *,ushort const *,STRU *)
0x180003939  mov     ebx, eax
0x18000393b  test    eax, eax
0x18000393d  js      loc_180003B9E
0x180003943  cmp     [rbp+57h+var_48], esi
0x180003946  jz      short loc_18000398E
0x180003948  lea     rdx, asc_180007870; "/"
0x18000394f  lea     rcx, [rbp+57h+var_B0]
0x180003953  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003959  mov     ebx, eax
0x18000395b  test    eax, eax
0x18000395d  js      loc_180003B9E
0x180003963  mov     rdx, [rbp+57h+var_58]
0x180003967  lea     rcx, [rbp+57h+var_B0]
0x18000396b  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180003971  mov     rcx, [rbp+57h+Destination]; Destination
0x180003975  call    ?NormalizeUrlWPreserveQueryString@@YAJPEAG@Z; NormalizeUrlWPreserveQueryString(ushort *)
0x18000397a  mov     ebx, eax
0x18000397c  test    eax, eax
0x18000397e  js      loc_180003B9E
0x180003984  lea     rcx, [rbp+57h+var_B0]
0x180003988  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000398e  mov     rcx, [rbp+57h+var_D0]; struct IAppHostElement *
0x180003992  lea     r8, [rbp+57h+var_C8]; int *
0x180003996  lea     rdx, aDoappinitafter; "doAppInitAfterRestart"
0x18000399d  call    ?GetConfigBool@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; GetConfigBool(IAppHostElement *,ushort const *,int *)
0x1800039a2  mov     ebx, eax
0x1800039a4  test    eax, eax
0x1800039a6  js      loc_180003B9E
0x1800039ac  mov     ecx, [rbp+57h+var_80]
0x1800039af  mov     rdx, r13
0x1800039b2  mov     rax, [r12]
0x1800039b6  neg     ecx
0x1800039b8  mov     r9d, [rbp+57h+var_C8]
0x1800039bc  mov     rcx, r12
0x1800039bf  sbb     r8, r8
0x1800039c2  and     r8, [rbp+57h+Destination]
0x1800039c6  mov     rax, [rax+8]
0x1800039ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039cf  mov     ebx, eax
0x1800039d1  test    eax, eax
0x1800039d3  js      loc_180003B9E
0x1800039d9  mov     rcx, [rbp+57h+var_D0]
0x1800039dd  lea     rdx, [rbp+57h+var_C0]
0x1800039e1  mov     rax, [rcx]
0x1800039e4  mov     rax, [rax+20h]
0x1800039e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ed  mov     ebx, eax
0x1800039ef  test    eax, eax
0x1800039f1  js      loc_180003B9E
0x1800039f7  mov     rcx, [rbp+57h+var_C0]
0x1800039fb  lea     rdx, [rsp+110h+var_E0]
0x180003a00  mov     rax, [rcx]
0x180003a03  mov     rax, [rax+18h]
0x180003a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a0c  mov     ebx, eax
0x180003a0e  test    eax, eax
0x180003a10  js      loc_180003B9E
0x180003a16  xor     r14d, r14d
0x180003a19  cmp     [rsp+110h+var_E0], esi
0x180003a1d  jbe     loc_180003B9E
0x180003a23  mov     rcx, [rbp+57h+var_C0]; struct IAppHostElementCollection *
0x180003a27  lea     r8, [rsp+110h+var_D8]; struct IAppHostElement **
0x180003a2c  mov     edx, r14d; unsigned int
0x180003a2f  call    ?GetCollectionElement@@YAJPEAUIAppHostElementCollection@@KPEAPEAUIAppHostElement@@@Z; GetCollectionElement(IAppHostElementCollection *,ulong,IAppHostElement * *)
0x180003a34  mov     ebx, eax
0x180003a36  test    eax, eax
0x180003a38  js      loc_180003B9C
0x180003a3e  mov     ecx, 0F8h; Size
0x180003a43  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a48  mov     rdi, rax
0x180003a4b  test    rax, rax
0x180003a4e  jz      loc_180003B97
0x180003a54  lea     rcx, [rax+8]
0x180003a58  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003a5e  lea     rcx, [rdi+40h]
0x180003a62  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003a68  lea     rcx, [rdi+78h]
0x180003a6c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003a72  lea     rcx, [rdi+0B0h]
0x180003a79  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003a7f  lea     rcx, [rdi+0E8h]
0x180003a86  mov     [rdi], r15d
0x180003a89  mov     [rdi+0F0h], rcx
0x180003a90  mov     rdx, r13
0x180003a93  mov     [rcx], rcx
0x180003a96  lea     rcx, [rdi+8]
0x180003a9a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003aa0  mov     ebx, eax
0x180003aa2  mov     rsi, rdi
0x180003aa5  test    eax, eax
0x180003aa7  js      loc_180003B9E
0x180003aad  mov     rcx, [rsp+110h+var_D8]; struct IAppHostElement *
0x180003ab2  lea     r8, [rbp+57h+var_78]; struct STRU *
0x180003ab6  lea     rdx, aInitialization; "initializationPage"
0x180003abd  call    ?GetConfigString@@YAJPEAUIAppHostElement@@PEBGPEAVSTRU@@@Z; GetConfigString(IAppHostElement *,ushort const *,STRU *)
0x180003ac2  mov     ebx, eax
0x180003ac4  test    eax, eax
0x180003ac6  js      loc_180003B9E
0x180003acc  lea     r15, [rdi+40h]
0x180003ad0  mov     rcx, r15
0x180003ad3  lea     rdx, asc_180007870; "/"
0x180003ada  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003ae0  mov     ebx, eax
0x180003ae2  test    eax, eax
0x180003ae4  js      loc_180003B9E
0x180003aea  mov     rdx, [rbp+57h+var_58]
0x180003aee  mov     rcx, r15
0x180003af1  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180003af7  mov     ebx, eax
0x180003af9  test    eax, eax
0x180003afb  js      loc_180003B9E
0x180003b01  mov     rcx, [rdi+60h]; Destination
0x180003b05  call    ?NormalizeUrlWPreserveQueryString@@YAJPEAG@Z; NormalizeUrlWPreserveQueryString(ushort *)
0x180003b0a  mov     ebx, eax
0x180003b0c  test    eax, eax
0x180003b0e  js      loc_180003B9E
0x180003b14  mov     rcx, r15
0x180003b17  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180003b1d  mov     rcx, [rsp+110h+var_D8]; struct IAppHostElement *
0x180003b22  lea     r8, [rdi+78h]; struct STRU *
0x180003b26  lea     rdx, aHostname; "hostName"
0x180003b2d  call    ?GetConfigString@@YAJPEAUIAppHostElement@@PEBGPEAVSTRU@@@Z; GetConfigString(IAppHostElement *,ushort const *,STRU *)
0x180003b32  mov     ebx, eax
0x180003b34  test    eax, eax
0x180003b36  js      short loc_180003B9E
0x180003b38  cmp     dword ptr [rdi+0A8h], 0
0x180003b3f  jnz     short loc_180003B58
0x180003b41  lea     rdx, aLocalhost; "localhost"
0x180003b48  lea     rcx, [rdi+78h]
0x180003b4c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003b52  mov     ebx, eax
0x180003b54  test    eax, eax
0x180003b56  js      short loc_180003B9E
0x180003b58  mov     rax, [r12]
0x180003b5c  mov     rdx, rdi
0x180003b5f  mov     rcx, r12
0x180003b62  mov     rax, [rax+10h]
0x180003b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b6b  mov     rcx, [rsp+110h+var_D8]
0x180003b70  xor     esi, esi
0x180003b72  mov     rax, [rcx]
0x180003b75  mov     rax, [rax+10h]
0x180003b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b7e  mov     r15d, [rbp+57h+var_B8]
0x180003b82  inc     r14d
0x180003b85  mov     [rsp+110h+var_D8], rsi
0x180003b8a  cmp     r14d, [rsp+110h+var_E0]
0x180003b8f  jb      loc_180003A23
0x180003b95  jmp     short loc_180003BBD
0x180003b97  mov     ebx, 8007000Eh
0x180003b9c  xor     esi, esi
0x180003b9e  mov     rcx, [rsp+110h+var_D8]
0x180003ba3  test    rcx, rcx
0x180003ba6  jz      short loc_180003BBD
0x180003ba8  mov     rax, [rcx]
0x180003bab  mov     rax, [rax+10h]
0x180003baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bb4  mov     [rsp+110h+var_D8], 0
0x180003bbd  mov     rcx, [rbp+57h+var_C0]
0x180003bc1  test    rcx, rcx
0x180003bc4  jz      short loc_180003BDA
0x180003bc6  mov     rax, [rcx]
0x180003bc9  mov     rax, [rax+10h]
0x180003bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bd2  mov     [rbp+57h+var_C0], 0
0x180003bda  mov     rcx, [rbp+57h+var_D0]
0x180003bde  test    rcx, rcx
0x180003be1  jz      short loc_180003BF7
0x180003be3  mov     rax, [rcx]
0x180003be6  mov     rax, [rax+10h]
0x180003bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bef  mov     [rbp+57h+var_D0], 0
0x180003bf7  test    rsi, rsi
0x180003bfa  jz      short loc_180003C2F
0x180003bfc  lea     rcx, [rsi+0B0h]
0x180003c03  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003c09  lea     rcx, [rsi+78h]
0x180003c0d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003c13  lea     rcx, [rsi+40h]
0x180003c17  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003c1d  lea     rcx, [rsi+8]
0x180003c21  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003c27  mov     rcx, rsi; Block
0x180003c2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003c2f  lea     rcx, [rbp+57h+var_B0]
0x180003c33  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003c39  lea     rcx, [rbp+57h+var_78]
0x180003c3d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003c43  mov     eax, ebx
0x180003c45  mov     rcx, [rbp+57h+var_40]
0x180003c49  xor     rcx, rsp; StackCookie
0x180003c4c  call    __security_check_cookie
0x180003c51  mov     rbx, [rsp+110h+arg_10]
0x180003c59  add     rsp, 0E0h
0x180003c60  pop     r15
0x180003c62  pop     r14
0x180003c64  pop     r13
0x180003c66  pop     r12
0x180003c68  pop     rdi
0x180003c69  pop     rsi
0x180003c6a  pop     rbp
0x180003c6b  retn
```
