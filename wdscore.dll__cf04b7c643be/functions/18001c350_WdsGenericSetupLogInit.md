# WdsGenericSetupLogInit

- ea: `0x18001c350`
- end: `0x18001c750`
- name: `WdsGenericSetupLogInit`
- size: `1024`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x18001a8dc`
- `0x18001aa9c`
- `0x18001c350`
- `0x18001ca90`
- `0x180020210`
- `0x1800207f0`
- `0x180022bcc`
- `0x180022bf8`
- `0x180022e40`
- `0x180022e64`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18001c6a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18001c6a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c6cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c6cd`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18001c6f7`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18001c6f7`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18001c70f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18001c70f`

## pseudocode

```c
__int64 __fastcall WdsGenericSetupLogInit(__int64 a1, unsigned int a2)
{
  int v3; // eax
  unsigned __int16 *v4; // r13
  const wchar_t *v5; // rdi
  const WCHAR *v6; // rcx
  HANDLE MutexWrapperW; // rbx
  int v9; // r14d
  unsigned int v10; // esi
  struct ILogManager *v11; // rdi
  unsigned int v12; // edx
  __int64 v13; // [rsp+60h] [rbp-D8h] BYREF
  int v14; // [rsp+68h] [rbp-D0h]
  __int64 v15; // [rsp+6Ch] [rbp-CCh]
  int v16; // [rsp+74h] [rbp-C4h]
  _QWORD v17[6]; // [rsp+78h] [rbp-C0h] BYREF
  _QWORD v18[7]; // [rsp+A8h] [rbp-90h] BYREF
  const wchar_t *v19; // [rsp+E0h] [rbp-58h] BYREF
  __m128i si128; // [rsp+E8h] [rbp-50h]
  BOOL v22; // [rsp+148h] [rbp+10h]

  if ( !a1 || !(unsigned int)InitDefaultACL((a2 >> 20) & 1) )
    return 0;
  v3 = IsUserAdminOrLocalService();
  v4 = L"SetupLog";
  v5 = L"Global\\SetupLog";
  if ( !v3 )
    v5 = L"SetupLog";
  v6 = L"Global\\WdsSetupLogInit";
  if ( !v3 )
    v6 = L"WdsSetupLogInit";
  MutexWrapperW = CreateMutexWrapperW(v6);
  if ( MutexWrapperW )
  {
    v4 = (unsigned __int16 *)v5;
  }
  else
  {
    if ( GetLastError() == 5 )
      MutexWrapperW = CreateMutexWrapperW(L"WdsSetupLogInit");
    else
      v4 = (unsigned __int16 *)v5;
    if ( !MutexWrapperW )
      return 0;
  }
  v9 = a2 & 0x10000000;
  v10 = 0;
  if ( (a2 & 0x10000000) == 0 )
    ++g_RefCnt;
  v11 = g_pLogManager;
  v22 = g_pLogManager != 0;
  if ( !g_pLogManager )
  {
    WdsLogRegStockProviders();
    v11 = (struct ILogManager *)WdsLogCreate(v4, (struct tagLOG_FIELD_INFO *)qword_180030AA0, 0x11u);
    if ( !v11 )
    {
      if ( !v9 )
        --g_RefCnt;
      ReleaseMutexWrapper(MutexWrapperW);
      CloseHandleWrapper(MutexWrapperW);
      return 0;
    }
  }
  v19 = L"Sev";
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v17[0] = L"DT";
  v17[1] = L"Sev";
  v17[2] = L"Msg";
  v17[3] = L"Err";
  v17[4] = L"Uid";
  v17[5] = 0;
  v13 = a1;
  v14 = 2 * (a2 & 1);
  v15 = 0;
  v16 = 0;
  if ( (unsigned int)InitializeTLSVariables() )
  {
    v12 = g_dwPrevFlags;
    if ( (g_dwPrevFlags & 0x1000) == 0 && (a2 & 0x1000) != 0 )
    {
      if ( !(**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *, _QWORD *, __int64 *, __int64 *, _QWORD))v11)(
              v11,
              &qword_180030A88,
              &v19,
              &qword_180032D28,
              v17,
              &qword_180032D48,
              &v13,
              0) )
        goto LABEL_33;
      v12 = g_dwPrevFlags | 0x1000;
      g_dwPrevFlags |= 0x1000u;
    }
    v18[0] = L"Sev";
    v18[1] = L"Msg";
    v18[2] = L"Con";
    v18[3] = L"LN";
    v18[4] = L"Fil";
    v18[5] = L"Fun";
    v18[6] = L"Err";
    if ( (v12 & 0x8000) != 0 || (a2 & 0x8000) == 0 )
    {
LABEL_28:
      if ( (v12 & 0x1000000) == 0 && (a2 & 0x1000000) != 0 )
      {
        g_OldUnhandledExceptionFilter = SetUnhandledExceptionFilter(WdsUnhandledExceptionFilter);
        g_dwPrevFlags |= 0x1000000u;
      }
      if ( !v22 )
      {
        g_ProcessID = GetCurrentProcessId();
        g_pLogManager = v11;
        GetModuleFileNameA(0, g_ProcessExeA, 0x104u);
        GetModuleFileNameW(0, g_ProcessExeW, 0x104u);
      }
      v10 = 1;
      goto LABEL_33;
    }
    if ( (**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, _QWORD *, __int64 *, _QWORD *, _QWORD, _QWORD, _QWORD))v11)(
           v11,
           &qword_180030A78,
           v18,
           &qword_180030A58,
           v18,
           0,
           0,
           0) )
    {
      v12 = g_dwPrevFlags | 0x8000;
      g_dwPrevFlags |= 0x8000u;
      goto LABEL_28;
    }
  }
LABEL_33:
  if ( !v10 )
  {
    g_pLogManager = v11;
    if ( !v9 )
      WdsSetupLogDestroy();
  }
  ReleaseMutexWrapper(MutexWrapperW);
  CloseHandleWrapper(MutexWrapperW);
  return v10;
}

```

## disassembly

```asm
0x18001c350  mov     [rsp+arg_0], rcx
0x18001c355  push    rbx
0x18001c356  push    rsi
0x18001c357  push    rdi
0x18001c358  push    r12
0x18001c35a  push    r13
0x18001c35c  push    r14
0x18001c35e  push    r15
0x18001c360  sub     rsp, 100h
0x18001c367  mov     r15d, edx
0x18001c36a  mov     rax, rcx
0x18001c36d  mov     ecx, edx
0x18001c36f  shr     ecx, 14h
0x18001c372  and     ecx, 1
0x18001c375  test    rax, rax
0x18001c378  jz      short loc_18001C3F1
0x18001c37a  call    InitDefaultACL
0x18001c37f  test    eax, eax
0x18001c381  jz      short loc_18001C3F1
0x18001c383  call    ?IsUserAdminOrLocalService@@YAHXZ; IsUserAdminOrLocalService(void)
0x18001c388  lea     r13, aSetuplog; "SetupLog"
0x18001c38f  lea     rdi, aGlobalSetuplog; "Global\\SetupLog"
0x18001c396  test    eax, eax
0x18001c398  cmovz   rdi, r13
0x18001c39c  lea     rsi, aWdssetuplogini_0; "WdsSetupLogInit"
0x18001c3a3  lea     rcx, aGlobalWdssetup; "Global\\WdsSetupLogInit"
0x18001c3aa  cmovz   rcx, rsi; lpName
0x18001c3ae  call    CreateMutexWrapperW
0x18001c3b3  mov     rbx, rax
0x18001c3b6  mov     [rsp+138h+arg_18], rax
0x18001c3be  test    rax, rax
0x18001c3c1  jnz     short loc_18001C407
0x18001c3c3  call    cs:__imp_GetLastError
0x18001c3ca  nop     dword ptr [rax+rax+00h]
0x18001c3cf  cmp     eax, 5
0x18001c3d2  jnz     short loc_18001C3E9
0x18001c3d4  mov     rcx, rsi; lpName
0x18001c3d7  call    CreateMutexWrapperW
0x18001c3dc  mov     rbx, rax
0x18001c3df  mov     [rsp+138h+arg_18], rax
0x18001c3e7  jmp     short loc_18001C3EC
0x18001c3e9  mov     r13, rdi
0x18001c3ec  test    rbx, rbx
0x18001c3ef  jnz     short loc_18001C40A
0x18001c3f1  xor     eax, eax
0x18001c3f3  add     rsp, 100h
0x18001c3fa  pop     r15
0x18001c3fc  pop     r14
0x18001c3fe  pop     r13
0x18001c400  pop     r12
0x18001c402  pop     rdi
0x18001c403  pop     rsi
0x18001c404  pop     rbx
0x18001c405  retn
0x18001c407  mov     r13, rdi
0x18001c40a  mov     r14d, r15d
0x18001c40d  and     r14d, 10000000h
0x18001c414  mov     [rsp+138h+arg_10], r14d
0x18001c41c  xor     esi, esi
0x18001c41e  mov     [rsp+138h+var_E8], esi
0x18001c422  mov     r12d, r15d
0x18001c425  and     r12d, 1
0x18001c429  add     r12d, r12d
0x18001c42c  test    r14d, r14d
0x18001c42f  jnz     short loc_18001C437
0x18001c431  inc     cs:?g_RefCnt@@3KA; ulong g_RefCnt
0x18001c437  xor     eax, eax
0x18001c439  mov     rdi, cs:?g_pLogManager@@3PEAVILogManager@@EA; ILogManager * g_pLogManager
0x18001c440  test    rdi, rdi
0x18001c443  setnz   al
0x18001c446  mov     [rsp+138h+arg_8], eax
0x18001c44d  test    eax, eax
0x18001c44f  jz      short loc_18001C45B
0x18001c451  mov     [rsp+138h+var_E0], rdi
0x18001c456  xor     r13d, r13d
0x18001c459  jmp     short loc_18001C4A5
0x18001c45b  call    WdsLogRegStockProviders
0x18001c460  mov     r8d, 11h; unsigned int
0x18001c466  lea     rdx, qword_180030AA0; struct tagLOG_FIELD_INFO *
0x18001c46d  mov     rcx, r13; unsigned __int16 *
0x18001c470  call    WdsLogCreate
0x18001c475  mov     rdi, rax
0x18001c478  mov     [rsp+138h+var_E0], rax
0x18001c47d  xor     r13d, r13d
0x18001c480  test    rax, rax
0x18001c483  jnz     short loc_18001C4A5
0x18001c485  test    r14d, r14d
0x18001c488  jnz     short loc_18001C490
0x18001c48a  dec     cs:?g_RefCnt@@3KA; ulong g_RefCnt
0x18001c490  mov     rcx, rbx
0x18001c493  call    ReleaseMutexWrapper
0x18001c498  mov     rcx, rbx
0x18001c49b  call    CloseHandleWrapper
0x18001c4a0  jmp     loc_18001C3F1
0x18001c4a5  lea     rcx, aSev; "Sev"
0x18001c4ac  mov     [rsp+138h+var_58], rcx
0x18001c4b4  movdqa  xmm0, cs:__xmm@00000000000000000000000104000000
0x18001c4bc  movdqu  [rsp+138h+var_50], xmm0
0x18001c4c5  lea     rax, aDt; "DT"
0x18001c4cc  mov     [rsp+138h+var_C0], rax
0x18001c4d1  mov     [rsp+138h+var_B8], rcx
0x18001c4d9  lea     rax, aMsg; "Msg"
0x18001c4e0  mov     [rsp+138h+var_B0], rax
0x18001c4e8  lea     rax, aErr; "Err"
0x18001c4ef  mov     [rsp+138h+var_A8], rax
0x18001c4f7  lea     rax, aUid; "Uid"
0x18001c4fe  mov     [rsp+138h+var_A0], rax
0x18001c506  mov     [rsp+138h+var_98], 0
0x18001c512  mov     rax, [rsp+138h+arg_0]
0x18001c51a  mov     [rsp+138h+var_D8], rax
0x18001c51f  mov     [rsp+138h+var_D0], r12d
0x18001c524  mov     [rsp+138h+var_CC], 0
0x18001c52d  xor     eax, eax
0x18001c52f  mov     [rsp+138h+var_C4], eax
0x18001c533  call    ?InitializeTLSVariables@@YAHXZ; InitializeTLSVariables(void)
0x18001c538  test    eax, eax
0x18001c53a  jz      loc_18001C724
0x18001c540  mov     edx, cs:?g_dwPrevFlags@@3KA; ulong g_dwPrevFlags
0x18001c546  bt      edx, 0Ch
0x18001c54a  setnb   cl
0x18001c54d  bt      r15d, 0Ch
0x18001c552  setb    al
0x18001c555  test    al, cl
0x18001c557  jz      short loc_18001C5BA
0x18001c559  mov     rax, [rdi]
0x18001c55c  mov     [rsp+138h+var_100], r13
0x18001c561  lea     rcx, [rsp+138h+var_D8]
0x18001c566  mov     [rsp+138h+var_108], rcx
0x18001c56b  lea     rcx, qword_180032D48
0x18001c572  mov     [rsp+138h+var_110], rcx
0x18001c577  lea     rcx, [rsp+138h+var_C0]
0x18001c57c  mov     [rsp+138h+var_118], rcx
0x18001c581  lea     r9, qword_180032D28
0x18001c588  lea     r8, [rsp+138h+var_58]
0x18001c590  lea     rdx, qword_180030A88
0x18001c597  mov     rcx, rdi
0x18001c59a  mov     rax, [rax]
0x18001c59d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5a2  test    eax, eax
0x18001c5a4  jz      loc_18001C724
0x18001c5aa  mov     edx, cs:?g_dwPrevFlags@@3KA; ulong g_dwPrevFlags
0x18001c5b0  bts     edx, 0Ch
0x18001c5b4  mov     cs:?g_dwPrevFlags@@3KA, edx; ulong g_dwPrevFlags
0x18001c5ba  lea     rax, aSev; "Sev"
0x18001c5c1  mov     [rsp+138h+var_90], rax
0x18001c5c9  lea     rax, aMsg; "Msg"
0x18001c5d0  mov     [rsp+138h+var_88], rax
0x18001c5d8  lea     rax, aCon; "Con"
0x18001c5df  mov     [rsp+138h+var_80], rax
0x18001c5e7  lea     rax, aLn; "LN"
0x18001c5ee  mov     [rsp+138h+var_78], rax
0x18001c5f6  lea     rax, aFil; "Fil"
0x18001c5fd  mov     [rsp+138h+var_70], rax
0x18001c605  lea     rax, aFun; "Fun"
0x18001c60c  mov     [rsp+138h+var_68], rax
0x18001c614  lea     rax, aErr; "Err"
0x18001c61b  mov     [rsp+138h+var_60], rax
0x18001c623  bt      edx, 0Fh
0x18001c627  setnb   cl
0x18001c62a  bt      r15d, 0Fh
0x18001c62f  setb    al
0x18001c632  test    al, cl
0x18001c634  jz      short loc_18001C68E
0x18001c636  mov     rax, [rdi]
0x18001c639  mov     [rsp+138h+var_100], r13
0x18001c63e  mov     [rsp+138h+var_108], r13
0x18001c643  mov     [rsp+138h+var_110], r13
0x18001c648  lea     rcx, [rsp+138h+var_90]
0x18001c650  mov     [rsp+138h+var_118], rcx
0x18001c655  lea     r9, qword_180030A58
0x18001c65c  lea     r8, [rsp+138h+var_90]
0x18001c664  lea     rdx, qword_180030A78
0x18001c66b  mov     rcx, rdi
0x18001c66e  mov     rax, [rax]
0x18001c671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c676  test    eax, eax
0x18001c678  jz      loc_18001C724
0x18001c67e  mov     edx, cs:?g_dwPrevFlags@@3KA; ulong g_dwPrevFlags
0x18001c684  bts     edx, 0Fh
0x18001c688  mov     cs:?g_dwPrevFlags@@3KA, edx; ulong g_dwPrevFlags
0x18001c68e  bt      edx, 18h
0x18001c692  setnb   cl
0x18001c695  bt      r15d, 18h
0x18001c69a  setb    al
0x18001c69d  test    al, cl
0x18001c69f  jz      short loc_18001C6C3
0x18001c6a1  lea     rcx, ?WdsUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; lpTopLevelExceptionFilter
0x18001c6a8  call    cs:__imp_SetUnhandledExceptionFilter
0x18001c6af  nop     dword ptr [rax+rax+00h]
0x18001c6b4  mov     cs:?g_OldUnhandledExceptionFilter@@3P6AJPEAU_EXCEPTION_POINTERS@@@ZEA, rax; long (*g_OldUnhandledExceptionFilter)(_EXCEPTION_POINTERS *)
0x18001c6bb  bts     cs:?g_dwPrevFlags@@3KA, 18h; ulong g_dwPrevFlags
0x18001c6c3  cmp     [rsp+138h+arg_8], r13d
0x18001c6cb  jnz     short loc_18001C71B
0x18001c6cd  call    cs:__imp_GetCurrentProcessId
0x18001c6d4  nop     dword ptr [rax+rax+00h]
0x18001c6d9  mov     cs:?g_ProcessID@@3KA, eax; ulong g_ProcessID
0x18001c6df  mov     cs:?g_pLogManager@@3PEAVILogManager@@EA, rdi; ILogManager * g_pLogManager
0x18001c6e6  mov     esi, 104h
0x18001c6eb  mov     r8d, esi; nSize
0x18001c6ee  lea     rdx, ?g_ProcessExeA@@3PADA; "<unknown>"
0x18001c6f5  xor     ecx, ecx; hModule
0x18001c6f7  call    cs:__imp_GetModuleFileNameA
0x18001c6fe  nop     dword ptr [rax+rax+00h]
0x18001c703  mov     r8d, esi; nSize
0x18001c706  lea     rdx, ?g_ProcessExeW@@3PAGA; "<unknown>"
0x18001c70d  xor     ecx, ecx; hModule
0x18001c70f  call    cs:__imp_GetModuleFileNameW
0x18001c716  nop     dword ptr [rax+rax+00h]
0x18001c71b  mov     esi, 1
0x18001c720  mov     [rsp+138h+var_E8], esi
0x18001c724  test    esi, esi
0x18001c726  jnz     short loc_18001C739
0x18001c728  mov     cs:?g_pLogManager@@3PEAVILogManager@@EA, rdi; ILogManager * g_pLogManager
0x18001c72f  test    r14d, r14d
0x18001c732  jnz     short loc_18001C739
0x18001c734  call    WdsSetupLogDestroy
0x18001c739  mov     rcx, rbx
0x18001c73c  call    ReleaseMutexWrapper
0x18001c741  mov     rcx, rbx
0x18001c744  call    CloseHandleWrapper
0x18001c749  mov     eax, esi
0x18001c74b  jmp     loc_18001C3F3
0x18002909d  push    rbp
0x18002909f  sub     rsp, 50h
0x1800290a3  mov     rbp, rdx
0x1800290a6  cmp     dword ptr [rbp+50h], 0
0x1800290aa  jnz     short loc_1800290C6
0x1800290ac  mov     rax, [rbp+58h]
0x1800290b0  mov     cs:?g_pLogManager@@3PEAVILogManager@@EA, rax; ILogManager * g_pLogManager
0x1800290b7  cmp     dword ptr [rbp+150h], 0
0x1800290be  jnz     short loc_1800290C6
0x1800290c0  call    WdsSetupLogDestroy
0x1800290c5  nop
0x1800290c6  mov     rcx, [rbp+158h]
0x1800290cd  call    ReleaseMutexWrapper
0x1800290d2  mov     rcx, [rbp+158h]
0x1800290d9  add     rsp, 50h
0x1800290dd  pop     rbp
0x1800290de  jmp     CloseHandleWrapper
```
