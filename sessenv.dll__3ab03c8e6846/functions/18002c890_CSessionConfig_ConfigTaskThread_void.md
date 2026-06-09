# CSessionConfig::ConfigTaskThread(void)

- ea: `0x18002c890`
- end: `0x18002cd11`
- name: `?ConfigTaskThread@CSessionConfig@@AEAAJXZ`
- size: `1153`
- prototype: `__int64 __fastcall(CSessionConfig *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18002d920`

## callees

- `0x180003f30`
- `0x18001a280`
- `0x18001a2a4`
- `0x18001a8d0`
- `0x18001ad5c`
- `0x18002c868`
- `0x18002c890`
- `0x18002cff0`
- `0x18002d3cc`
- `0x18002d9ac`
- `0x18002db88`
- `0x18004350c`
- `0x1800436bc`
- `0x1800436f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002cab5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002cab5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002ca70`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002ca70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cabf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cabf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002cca6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002cca6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002cb3b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002cb3b`
- `OLEAUT32!__imp_VariantInit` at `0x18002c8ef`
- `OLEAUT32!__imp_VariantInit` at `0x18002c8ef`
- `OLEAUT32!__imp_VariantClear` at `0x18002cce6`
- `OLEAUT32!__imp_VariantClear` at `0x18002cce6`

## string_xrefs

- `0x18002c91c`: `CSessionConfig::ConfigTaskThread`
- `0x18002c912`: `new ESkipTaskExecution failed: 0x%x in %s`
- `0x18002c95a`: `new SetSkippedTasks failed: 0x%x in %s`
- `0x18002c981`: `new CSessionConfigTaskThread failed: 0x%x in %s`
- `0x18002ca41`: `new RunTasks failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CSessionConfig::ConfigTaskThread(HANDLE *this)
{
  struct CSessionConfigTaskThread **v2; // r14
  enum ESkipTaskExecution *v3; // r12
  unsigned __int64 *v4; // r9
  enum ESkipTaskExecution *v5; // r13
  signed int v6; // ebx
  const char *v7; // rdx
  int v8; // eax
  __int64 v9; // r8
  const struct SConfigTask *v10; // r8
  unsigned __int64 i; // rsi
  _QWORD *v12; // rax
  HANDLE v13; // rdx
  int v14; // eax
  signed int LastError; // eax
  __int64 v16; // rcx
  signed int v17; // eax
  CSessionConfig *v18; // rcx
  int v19; // eax
  unsigned int v20; // edx
  enum ESkipTaskExecution *v21; // rax
  unsigned __int64 *v22; // r9
  int v23; // eax
  void *v24; // rax
  unsigned __int64 j; // rsi
  _QWORD *v26; // rax
  _QWORD *v27; // r9
  HANDLE v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rcx
  HANDLE *v31; // rcx
  int v32; // eax
  unsigned __int64 k; // rdi
  CSessionConfigTaskThread *v34; // rcx
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-E0h] BYREF
  HMODULE phModule; // [rsp+28h] [rbp-D8h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[256]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
  v3 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset_0(Buffer, 0, sizeof(Buffer));
  VariantInit(&pvarg);
  v5 = (enum ESkipTaskExecution *)operator new(0xCu, (const struct std::nothrow_t *)std::nothrow);
  if ( !v5 )
  {
LABEL_2:
    v6 = -2147024882;
    v7 = "new ESkipTaskExecution failed: 0x%x in %s";
LABEL_3:
    _DbgPrintMessage(8, v7, (unsigned int)v6, "CSessionConfig::ConfigTaskThread");
    goto LABEL_57;
  }
  *(_QWORD *)v5 = 0;
  *((_DWORD *)v5 + 2) = 0;
  v8 = CSessionConfig::s_SetSkippedTasks((LPCWSTR *)&off_18005E4F0, 3u, v5, v4);
  v6 = v8;
  if ( v8 < 0 )
  {
    v9 = (unsigned int)v8;
LABEL_7:
    _DbgPrintMessage(8, "new SetSkippedTasks failed: 0x%x in %s", v9, "CSessionConfig::ConfigTaskThread");
LABEL_57:
    SetEvent(this[199]);
    goto LABEL_58;
  }
  v2 = (struct CSessionConfigTaskThread **)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v2 )
  {
LABEL_9:
    v6 = -2147024882;
LABEL_10:
    v7 = "new CSessionConfigTaskThread failed: 0x%x in %s";
    goto LABEL_3;
  }
  *(_OWORD *)v2 = 0;
  v2[2] = 0;
  if ( !this[199] )
  {
    v6 = -2147418113;
    goto LABEL_57;
  }
  for ( i = 0; i < 3; ++i )
  {
    if ( !*((_DWORD *)v5 + i) )
    {
      v12 = operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
      if ( v12 )
      {
        v13 = this[199];
        v10 = (const struct SConfigTask *)*(&off_18005E4F0 + 4 * i);
        *v12 = *(&off_18005E4F0 + 4 * i + 1);
        v12[5] = &pvarg;
        v12[1] = 0;
        v12[2] = v13;
        v12[3] = v10;
        *((_DWORD *)v12 + 8) = 0;
        *((_DWORD *)v12 + 12) = 0;
      }
      else
      {
        v12 = 0;
      }
      v2[i] = (struct CSessionConfigTaskThread *)v12;
      if ( !v12 )
        goto LABEL_9;
      if ( v6 < 0 )
        goto LABEL_10;
    }
  }
  v14 = CSessionConfig::RunTasks((CSessionConfig *)this, v2, v10);
  v6 = v14;
  if ( v14 < 0 )
  {
    _DbgPrintMessage(8, "new RunTasks failed: 0x%x in %s", (unsigned int)v14, "CSessionConfig::ConfigTaskThread");
    goto LABEL_57;
  }
  if ( *((_DWORD *)this + 403) )
  {
    phModule = 0;
    if ( !GetModuleHandleExW(6u, (LPCWSTR)CSessionConfig::s_ConfigTaskThread, &phModule) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 < 0 )
      {
        v7 = "GetModuleHandleEx failed: 0x%x in %s";
        goto LABEL_3;
      }
    }
    if ( !LoadStringW(phModule, 0x66u, Buffer, 256) )
    {
      v17 = GetLastError();
      v6 = v17;
      if ( v17 > 0 )
        v6 = (unsigned __int16)v17 | 0x80070000;
      if ( v6 < 0 )
      {
        v7 = "LoadString failed: 0x%x in %s";
        goto LABEL_3;
      }
    }
    Binding = 0;
    if ( !(unsigned int)WmsgpConnect(v16, &Binding) )
    {
      WmsgpPostNotifyMessage(Binding);
      WmsgpDisconnect(&Binding);
    }
    v19 = CSessionConfig::Reboot(v18, Buffer);
    v6 = v19;
    if ( v19 < 0 )
    {
      _DbgPrintMessage(8, "Reboot failed: 0x%x in %s", (unsigned int)v19, "CSessionConfig::ConfigTaskThread");
      goto LABEL_57;
    }
  }
  else
  {
    if ( !WaitForSingleObject(this[199], 1u) )
    {
      v6 = -2147467260;
      v7 = "Abort was signalled failed: 0x%x in %s";
      goto LABEL_3;
    }
    this[203] = HANDLE_FLAG_INHERIT;
    v21 = (enum ESkipTaskExecution *)operator new(4u, (const struct std::nothrow_t *)std::nothrow);
    v3 = v21;
    if ( !v21 )
      goto LABEL_2;
    *(_DWORD *)v21 = 0;
    v23 = CSessionConfig::s_SetSkippedTasks((LPCWSTR *)&off_18005E4D0, 1u, v21, v22);
    v6 = v23;
    if ( v23 < 0 )
    {
      v9 = (unsigned int)v23;
      goto LABEL_7;
    }
    v24 = operator new(8u, (const struct std::nothrow_t *)std::nothrow);
    this[202] = v24;
    if ( !v24 )
      goto LABEL_9;
    memset_0(v24, 0, 8LL * (_QWORD)this[203]);
    for ( j = 0; j < (unsigned __int64)this[203]; ++j )
    {
      if ( !*((_DWORD *)v3 + j) )
      {
        v26 = operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
        v27 = v26;
        if ( v26 )
        {
          v28 = this[199];
          v29 = (__int64)*(&off_18005E4D0 + 4 * j);
          v30 = (__int64)*(&off_18005E4D0 + 4 * j + 1);
          v26[5] = &pvarg;
          *v26 = v30;
          v26[1] = 0;
          v26[2] = v28;
          v26[3] = v29;
          *((_DWORD *)v26 + 8) = 0;
          *((_DWORD *)v26 + 12) = 0;
        }
        else
        {
          v27 = 0;
        }
        *((_QWORD *)this[202] + j) = v27;
        v31 = (HANDLE *)*((_QWORD *)this[202] + j);
        if ( !v31 )
          goto LABEL_9;
        if ( v6 < 0 )
          goto LABEL_10;
        v32 = CSessionConfigTaskThread::Start(v31);
        v6 = v32;
        if ( v32 < 0 )
        {
          _DbgPrintMessage(8, "Execute failed: 0x%x in %s", (unsigned int)v32, "CSessionConfig::ConfigTaskThread");
          goto LABEL_57;
        }
      }
    }
    if ( v6 < 0 )
      goto LABEL_57;
  }
LABEL_58:
  for ( k = 0; k < 3; ++k )
  {
    v34 = v2[k];
    if ( v34 )
    {
      CSessionConfigTaskThread::`scalar deleting destructor'(v34, v20);
      v2[k] = 0;
    }
  }
  operator delete(v2);
  operator delete(v5);
  operator delete(v3);
  VariantClear(&pvarg);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002c890  push    rbp
0x18002c892  push    rbx
0x18002c893  push    rsi
0x18002c894  push    rdi
0x18002c895  push    r12
0x18002c897  push    r13
0x18002c899  push    r14
0x18002c89b  push    r15
0x18002c89d  lea     rbp, [rsp-168h]
0x18002c8a5  sub     rsp, 268h
0x18002c8ac  mov     rax, cs:__security_cookie
0x18002c8b3  xor     rax, rsp
0x18002c8b6  mov     [rbp+1A0h+var_50], rax
0x18002c8bd  mov     rdi, rcx
0x18002c8c0  xor     r15d, r15d
0x18002c8c3  xorps   xmm0, xmm0
0x18002c8c6  lea     rcx, [rsp+2A0h+Buffer]; void *
0x18002c8cb  xor     eax, eax
0x18002c8cd  xor     edx, edx; Val
0x18002c8cf  mov     r8d, 200h; Size
0x18002c8d5  mov     qword ptr [rsp+2A0h+pvarg+10h], rax
0x18002c8da  mov     r14d, r15d
0x18002c8dd  mov     r12d, r15d
0x18002c8e0  movups  xmmword ptr [rsp+2A0h+pvarg], xmm0
0x18002c8e5  call    memset_0
0x18002c8ea  lea     rcx, [rsp+2A0h+pvarg]; pvarg
0x18002c8ef  call    cs:__imp_VariantInit
0x18002c8f5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002c8fc  lea     ecx, [r15+0Ch]; unsigned __int64
0x18002c900  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002c905  mov     r13, rax
0x18002c908  test    rax, rax
0x18002c90b  jnz     short loc_18002C932
0x18002c90d  mov     ebx, 8007000Eh
0x18002c912  lea     rdx, aNewEskiptaskex; "new ESkipTaskExecution failed: 0x%x in "...
0x18002c919  mov     r8d, ebx
0x18002c91c  lea     r9, aCsessionconfig_0; "CSessionConfig::ConfigTaskThread"
0x18002c923  mov     ecx, 8; int
0x18002c928  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c92d  jmp     loc_18002CC9F
0x18002c932  mov     rax, r15
0x18002c935  lea     rcx, off_18005E4F0; struct SConfigTask *
0x18002c93c  mov     [r13+0], rax
0x18002c940  mov     r8, r13; enum ESkipTaskExecution *
0x18002c943  mov     edx, 3; unsigned __int64
0x18002c948  mov     [r13+8], eax
0x18002c94c  call    ?s_SetSkippedTasks@CSessionConfig@@SAJPEBUSConfigTask@@_KPEAW4ESkipTaskExecution@@PEA_K@Z; CSessionConfig::s_SetSkippedTasks(SConfigTask const *,unsigned __int64,ESkipTaskExecution *,unsigned __int64 *)
0x18002c951  mov     ebx, eax
0x18002c953  test    eax, eax
0x18002c955  jns     short loc_18002C963
0x18002c957  mov     r8d, eax
0x18002c95a  lea     rdx, aNewSetskippedt; "new SetSkippedTasks failed: 0x%x in %s"
0x18002c961  jmp     short loc_18002C91C
0x18002c963  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002c96a  mov     ecx, 18h; unsigned __int64
0x18002c96f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002c974  mov     r14, rax
0x18002c977  test    rax, rax
0x18002c97a  jnz     short loc_18002C98A
0x18002c97c  mov     ebx, 8007000Eh
0x18002c981  lea     rdx, aNewCsessioncon_0; "new CSessionConfigTaskThread failed: 0x"...
0x18002c988  jmp     short loc_18002C919
0x18002c98a  xor     eax, eax
0x18002c98c  xorps   xmm0, xmm0
0x18002c98f  movups  xmmword ptr [r14], xmm0
0x18002c993  mov     [r14+10h], rax
0x18002c997  cmp     [rdi+638h], r15
0x18002c99e  jnz     short loc_18002C9AA
0x18002c9a0  mov     ebx, 8000FFFFh
0x18002c9a5  jmp     loc_18002CC9F
0x18002c9aa  mov     rsi, r15
0x18002c9ad  cmp     rsi, 3
0x18002c9b1  jnb     short loc_18002CA2D
0x18002c9b3  cmp     [r13+rsi*4+0], r15d
0x18002c9b8  jnz     short loc_18002CA28
0x18002c9ba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002c9c1  mov     ecx, 38h ; '8'; unsigned __int64
0x18002c9c6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002c9cb  test    rax, rax
0x18002c9ce  jz      short loc_18002CA10
0x18002c9d0  mov     rdx, [rdi+638h]
0x18002c9d7  lea     r9, off_18005E4F0
0x18002c9de  mov     rcx, rsi
0x18002c9e1  shl     rcx, 5
0x18002c9e5  mov     r8, [rcx+r9]
0x18002c9e9  mov     rcx, [rcx+r9+8]
0x18002c9ee  mov     [rax], rcx
0x18002c9f1  lea     rcx, [rsp+2A0h+pvarg]
0x18002c9f6  mov     [rax+28h], rcx
0x18002c9fa  mov     [rax+8], r15
0x18002c9fe  mov     [rax+10h], rdx
0x18002ca02  mov     [rax+18h], r8
0x18002ca06  mov     [rax+20h], r15d
0x18002ca0a  mov     [rax+30h], r15d
0x18002ca0e  jmp     short loc_18002CA13
0x18002ca10  mov     rax, r15
0x18002ca13  mov     [r14+rsi*8], rax
0x18002ca17  test    rax, rax
0x18002ca1a  jz      loc_18002C97C
0x18002ca20  test    ebx, ebx
0x18002ca22  js      loc_18002C981
0x18002ca28  inc     rsi
0x18002ca2b  jmp     short loc_18002C9AD
0x18002ca2d  mov     rdx, r14; struct CSessionConfigTaskThread **
0x18002ca30  mov     rcx, rdi; this
0x18002ca33  call    ?RunTasks@CSessionConfig@@AEAAJPEAPEAVCSessionConfigTaskThread@@PEBUSConfigTask@@_K@Z; CSessionConfig::RunTasks(CSessionConfigTaskThread * *,SConfigTask const *,unsigned __int64)
0x18002ca38  mov     ebx, eax
0x18002ca3a  test    eax, eax
0x18002ca3c  jns     short loc_18002CA4D
0x18002ca3e  mov     r8d, eax
0x18002ca41  lea     rdx, aNewRuntasksFai; "new RunTasks failed: 0x%x in %s"
0x18002ca48  jmp     loc_18002C91C
0x18002ca4d  cmp     [rdi+64Ch], r15d
0x18002ca54  jz      loc_18002CB2F
0x18002ca5a  lea     r8, [rsp+2A0h+phModule]; phModule
0x18002ca5f  mov     [rsp+2A0h+phModule], r15
0x18002ca64  lea     rdx, ?s_ConfigTaskThread@CSessionConfig@@CAKPEAX@Z; lpModuleName
0x18002ca6b  mov     ecx, 6; dwFlags
0x18002ca70  call    cs:__imp_GetModuleHandleExW
0x18002ca76  mov     esi, 80070000h
0x18002ca7b  test    eax, eax
0x18002ca7d  jnz     short loc_18002CAA0
0x18002ca7f  call    cs:__imp_GetLastError
0x18002ca85  mov     ebx, eax
0x18002ca87  test    eax, eax
0x18002ca89  jle     short loc_18002CA90
0x18002ca8b  movzx   ebx, ax
0x18002ca8e  or      ebx, esi
0x18002ca90  test    ebx, ebx
0x18002ca92  jns     short loc_18002CAA0
0x18002ca94  lea     rdx, aGetmodulehandl; "GetModuleHandleEx failed: 0x%x in %s"
0x18002ca9b  jmp     loc_18002C919
0x18002caa0  mov     rcx, [rsp+2A0h+phModule]; hInstance
0x18002caa5  lea     r8, [rsp+2A0h+Buffer]; lpBuffer
0x18002caaa  mov     r9d, 100h; cchBufferMax
0x18002cab0  mov     edx, 66h ; 'f'; uID
0x18002cab5  call    cs:__imp_LoadStringW
0x18002cabb  test    eax, eax
0x18002cabd  jnz     short loc_18002CAE0
0x18002cabf  call    cs:__imp_GetLastError
0x18002cac5  mov     ebx, eax
0x18002cac7  test    eax, eax
0x18002cac9  jle     short loc_18002CAD0
0x18002cacb  movzx   ebx, ax
0x18002cace  or      ebx, esi
0x18002cad0  test    ebx, ebx
0x18002cad2  jns     short loc_18002CAE0
0x18002cad4  lea     rdx, aLoadstringFail; "LoadString failed: 0x%x in %s"
0x18002cadb  jmp     loc_18002C919
0x18002cae0  lea     rdx, [rsp+2A0h+Binding]
0x18002cae5  mov     [rsp+2A0h+Binding], r15
0x18002caea  call    WmsgpConnect
0x18002caef  test    eax, eax
0x18002caf1  jnz     short loc_18002CB0C
0x18002caf3  mov     rcx, [rsp+2A0h+Binding]; SourceBinding
0x18002caf8  lea     r9, [rsp+2A0h+Buffer]
0x18002cafd  call    WmsgpPostNotifyMessage
0x18002cb02  lea     rcx, [rsp+2A0h+Binding]; Binding
0x18002cb07  call    WmsgpDisconnect
0x18002cb0c  lea     rdx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x18002cb11  call    ?Reboot@CSessionConfig@@AEAAJPEBGK@Z; CSessionConfig::Reboot(ushort const *,ulong)
0x18002cb16  mov     ebx, eax
0x18002cb18  test    eax, eax
0x18002cb1a  jns     loc_18002CCAC
0x18002cb20  mov     r8d, eax
0x18002cb23  lea     rdx, aRebootFailed0x; "Reboot failed: 0x%x in %s"
0x18002cb2a  jmp     loc_18002C91C
0x18002cb2f  mov     rcx, [rdi+638h]; hHandle
0x18002cb36  mov     edx, 1; dwMilliseconds
0x18002cb3b  call    cs:__imp_WaitForSingleObject
0x18002cb41  test    eax, eax
0x18002cb43  jnz     short loc_18002CB56
0x18002cb45  mov     ebx, 80004004h
0x18002cb4a  lea     rdx, aAbortWasSignal; "Abort was signalled failed: 0x%x in %s"
0x18002cb51  jmp     loc_18002C919
0x18002cb56  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002cb5d  mov     qword ptr [rdi+658h], 1
0x18002cb68  mov     ecx, 4; unsigned __int64
0x18002cb6d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002cb72  mov     r12, rax
0x18002cb75  test    rax, rax
0x18002cb78  jz      loc_18002C90D
0x18002cb7e  mov     r8, rax; enum ESkipTaskExecution *
0x18002cb81  mov     [rax], r15d
0x18002cb84  mov     edx, 1; unsigned __int64
0x18002cb89  lea     rcx, off_18005E4D0; struct SConfigTask *
0x18002cb90  call    ?s_SetSkippedTasks@CSessionConfig@@SAJPEBUSConfigTask@@_KPEAW4ESkipTaskExecution@@PEA_K@Z; CSessionConfig::s_SetSkippedTasks(SConfigTask const *,unsigned __int64,ESkipTaskExecution *,unsigned __int64 *)
0x18002cb95  mov     ebx, eax
0x18002cb97  test    eax, eax
0x18002cb99  jns     short loc_18002CBA3
0x18002cb9b  mov     r8d, eax
0x18002cb9e  jmp     loc_18002C95A
0x18002cba3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002cbaa  mov     ecx, 8; unsigned __int64
0x18002cbaf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002cbb4  mov     [rdi+650h], rax
0x18002cbbb  test    rax, rax
0x18002cbbe  jz      loc_18002C97C
0x18002cbc4  mov     r8, [rdi+658h]
0x18002cbcb  xor     edx, edx; Val
0x18002cbcd  shl     r8, 3; Size
0x18002cbd1  mov     rcx, rax; void *
0x18002cbd4  call    memset_0
0x18002cbd9  mov     rsi, r15
0x18002cbdc  cmp     rsi, [rdi+658h]
0x18002cbe3  jnb     loc_18002CC9B
0x18002cbe9  cmp     [r12+rsi*4], r15d
0x18002cbed  jnz     loc_18002CC84
0x18002cbf3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002cbfa  mov     ecx, 38h ; '8'; unsigned __int64
0x18002cbff  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002cc04  xor     r10d, r10d
0x18002cc07  mov     r9, rax
0x18002cc0a  test    rax, rax
0x18002cc0d  jz      short loc_18002CC4F
0x18002cc0f  mov     rdx, [rdi+638h]
0x18002cc16  lea     rax, off_18005E4D0
0x18002cc1d  mov     rcx, rsi
0x18002cc20  shl     rcx, 5
0x18002cc24  mov     r8, [rcx+rax]
0x18002cc28  mov     rcx, [rcx+rax+8]
0x18002cc2d  lea     rax, [rsp+2A0h+pvarg]
0x18002cc32  mov     [r9+28h], rax
0x18002cc36  mov     [r9], rcx
0x18002cc39  mov     [r9+8], r10
0x18002cc3d  mov     [r9+10h], rdx
0x18002cc41  mov     [r9+18h], r8
0x18002cc45  mov     [r9+20h], r10d
0x18002cc49  mov     [r9+30h], r10d
0x18002cc4d  jmp     short loc_18002CC52
0x18002cc4f  mov     r9, r10
0x18002cc52  mov     rax, [rdi+650h]
0x18002cc59  mov     [rax+rsi*8], r9
0x18002cc5d  mov     rax, [rdi+650h]
0x18002cc64  mov     rcx, [rax+rsi*8]; this
0x18002cc68  test    rcx, rcx
0x18002cc6b  jz      loc_18002C97C
0x18002cc71  test    ebx, ebx
0x18002cc73  js      loc_18002C981
0x18002cc79  call    ?Start@CSessionConfigTaskThread@@QEAAJXZ; CSessionConfigTaskThread::Start(void)
0x18002cc7e  mov     ebx, eax
0x18002cc80  test    eax, eax
0x18002cc82  js      short loc_18002CC8C
0x18002cc84  inc     rsi
0x18002cc87  jmp     loc_18002CBDC
0x18002cc8c  mov     r8d, eax
0x18002cc8f  lea     rdx, aExecuteFailed0; "Execute failed: 0x%x in %s"
0x18002cc96  jmp     loc_18002C91C
0x18002cc9b  test    ebx, ebx
0x18002cc9d  jns     short loc_18002CCAC
0x18002cc9f  mov     rcx, [rdi+638h]; hEvent
0x18002cca6  call    cs:__imp_SetEvent
0x18002ccac  xor     edi, edi
0x18002ccae  mov     rcx, [r14+rdi*8]; this
0x18002ccb2  test    rcx, rcx
0x18002ccb5  jz      short loc_18002CCC0
0x18002ccb7  call    ??_GCSessionConfigTaskThread@@QEAAPEAXI@Z; CSessionConfigTaskThread::`scalar deleting destructor'(uint)
0x18002ccbc  mov     [r14+rdi*8], r15
0x18002ccc0  inc     rdi
0x18002ccc3  cmp     rdi, 3
0x18002ccc7  jb      short loc_18002CCAE
0x18002ccc9  mov     rcx, r14; Block
0x18002cccc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ccd1  mov     rcx, r13; Block
0x18002ccd4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ccd9  mov     rcx, r12; Block
0x18002ccdc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cce1  lea     rcx, [rsp+2A0h+pvarg]; pvarg
0x18002cce6  call    cs:__imp_VariantClear
0x18002ccec  mov     eax, ebx
0x18002ccee  mov     rcx, [rbp+1A0h+var_50]
0x18002ccf5  xor     rcx, rsp; StackCookie
0x18002ccf8  call    __security_check_cookie
0x18002ccfd  add     rsp, 268h
0x18002cd04  pop     r15
0x18002cd06  pop     r14
0x18002cd08  pop     r13
0x18002cd0a  pop     r12
0x18002cd0c  pop     rdi
0x18002cd0d  pop     rsi
0x18002cd0e  pop     rbx
0x18002cd0f  pop     rbp
0x18002cd10  retn
```
