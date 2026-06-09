# WdsAddUsmtLogStack

- ea: `0x18001bd30`
- end: `0x18001c32f`
- name: `WdsAddUsmtLogStack`
- size: `1535`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x180009e30`
- `0x18001a8dc`
- `0x18001aa9c`
- `0x18001bd30`
- `0x18001ca90`
- `0x180020210`
- `0x1800207f0`
- `0x180022bcc`
- `0x180022bf8`
- `0x180022e40`
- `0x180022e64`
- `0x1800274de`
- `0x180027510`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c2a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c2a8`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18001c2d0`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18001c2d0`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18001c2eb`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18001c2eb`

## pseudocode

```c
__int64 __fastcall WdsAddUsmtLogStack(const unsigned __int16 *a1, char a2, unsigned int a3)
{
  int v4; // eax
  unsigned __int16 *v5; // r12
  const wchar_t *v6; // rbx
  const WCHAR *v7; // rcx
  HANDLE MutexWrapperW; // rdi
  int v10; // esi
  unsigned int v11; // r15d
  struct ILogManager *v12; // rbx
  const wchar_t **v13; // rcx
  BOOL v15; // [rsp+58h] [rbp-360h]
  unsigned __int16 *v17; // [rsp+68h] [rbp-350h]
  unsigned __int16 *v18; // [rsp+78h] [rbp-340h] BYREF
  int v19; // [rsp+80h] [rbp-338h]
  __int64 v20; // [rsp+84h] [rbp-334h]
  int v21; // [rsp+8Ch] [rbp-32Ch]
  _QWORD v22[6]; // [rsp+90h] [rbp-328h] BYREF
  _QWORD v23[7]; // [rsp+C0h] [rbp-2F8h] BYREF
  const wchar_t *v24; // [rsp+F8h] [rbp-2C0h] BYREF
  __m128i v25; // [rsp+100h] [rbp-2B8h]
  const wchar_t *v26; // [rsp+110h] [rbp-2A8h] BYREF
  __m128i v27; // [rsp+118h] [rbp-2A0h]
  const wchar_t *v28; // [rsp+128h] [rbp-290h] BYREF
  __m128i si128; // [rsp+130h] [rbp-288h]
  const wchar_t *v30; // [rsp+140h] [rbp-278h] BYREF
  __m128i v31; // [rsp+148h] [rbp-270h]
  const wchar_t *v32; // [rsp+158h] [rbp-260h] BYREF
  __m128i v33; // [rsp+160h] [rbp-258h]
  unsigned __int16 v34[264]; // [rsp+170h] [rbp-248h] BYREF

  memset_0(v34, 0, 0x208u);
  if ( !(unsigned int)InitDefaultACL((a3 >> 20) & 1) )
    return 0;
  v4 = IsUserAdminOrLocalService();
  v5 = L"SetupLog";
  v6 = L"Global\\SetupLog";
  if ( !v4 )
    v6 = L"SetupLog";
  v7 = L"Global\\WdsSetupLogInit";
  if ( !v4 )
    v7 = L"WdsSetupLogInit";
  MutexWrapperW = CreateMutexWrapperW(v7);
  if ( MutexWrapperW )
  {
    v5 = (unsigned __int16 *)v6;
  }
  else
  {
    if ( GetLastError() == 5 )
      MutexWrapperW = CreateMutexWrapperW(L"WdsSetupLogInit");
    else
      v5 = (unsigned __int16 *)v6;
    if ( !MutexWrapperW )
      return 0;
  }
  v10 = a3 & 0x10000000;
  v11 = 0;
  if ( (a3 & 0x10000000) == 0 )
    ++g_RefCnt;
  v12 = g_pLogManager;
  v15 = g_pLogManager != 0;
  if ( !g_pLogManager )
  {
    WdsLogRegStockProviders();
    v12 = (struct ILogManager *)WdsLogCreate(v5, (struct tagLOG_FIELD_INFO *)qword_180030AA0, 0x11u);
    if ( !v12 )
    {
      if ( !v10 )
        --g_RefCnt;
      ReleaseMutexWrapper(MutexWrapperW);
      CloseHandleWrapper(MutexWrapperW);
      return 0;
    }
  }
  v28 = L"Sev";
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v26 = L"Sev";
  v27 = _mm_load_si128((const __m128i *)&_xmm);
  v24 = L"Sev";
  v25 = _mm_load_si128((const __m128i *)&_xmm);
  v32 = L"Sev";
  v33 = _mm_load_si128((const __m128i *)&_xmm);
  v30 = L"Sev";
  v31 = _mm_load_si128((const __m128i *)&_xmm);
  if ( a1 )
  {
    if ( StringCchCopyW(v34, 0x104u, a1) >= 0 )
    {
      v18 = v34;
      v19 = 2 * (a3 & 1);
      v20 = 0;
      v21 = 0;
      v23[0] = L"Sev";
      v23[1] = L"Msg";
      v23[2] = L"Con";
      v23[3] = L"LN";
      v23[4] = L"Fil";
      v23[5] = L"Fun";
      v23[6] = L"Err";
      if ( (unsigned int)InitializeTLSVariables() )
      {
        if ( (a3 & 0x20000000) != 0 && (g_dwPrevFlags & 0x20000000) == 0 )
        {
          v22[0] = L"DT";
          v22[1] = L"Sev";
          v22[2] = L"Msg";
          v22[3] = L"Err";
          v22[4] = L"Uid";
          v22[5] = 0;
          v13 = &v26;
          if ( (a2 & 1) != 0 )
            v13 = &v28;
          v17 = (unsigned __int16 *)v13;
          if ( !(**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *, _QWORD *, __int64 *, unsigned __int16 **, _QWORD))v12)(
                  v12,
                  &qword_180030A88,
                  v13,
                  &qword_180032D28,
                  v22,
                  &qword_180032D48,
                  &v18,
                  0)
            || !(**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *, _QWORD *, __int64 *, unsigned __int16 **, _QWORD))v12)(
                  v12,
                  &qword_180030A88,
                  &v30,
                  &qword_180032D28,
                  v22,
                  &qword_180032D48,
                  &v18,
                  0)
            || (a2 & 8) != 0
            && (!(**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, unsigned __int16 *, __int64 *, _QWORD *, _QWORD, _QWORD, _QWORD))v12)(
                   v12,
                   &qword_180030A88,
                   v17,
                   &qword_180030A58,
                   v23,
                   0,
                   0,
                   0)
             || (a2 & 1) != 0
             && !(**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *, _QWORD *, _QWORD, _QWORD, _QWORD))v12)(
                   v12,
                   &qword_180030A88,
                   &v32,
                   &qword_180030A58,
                   v23,
                   0,
                   0,
                   0))
            || (a2 & 4) != 0
            && (!(**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *, _QWORD *, __int64 *, unsigned __int16 **, _QWORD))v12)(
                   v12,
                   &qword_180030A88,
                   &v24,
                   &qword_180032D28,
                   v22,
                   &qword_180032D48,
                   &v18,
                   0)
             || (a2 & 8) != 0
             && !(**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *, _QWORD *, _QWORD, _QWORD, _QWORD))v12)(
                   v12,
                   &qword_180030A88,
                   &v24,
                   &qword_180030A58,
                   v23,
                   0,
                   0,
                   0)) )
          {
            goto LABEL_41;
          }
          g_dwPrevFlags |= 0x20000000u;
        }
        if ( !v15 )
        {
          g_ProcessID = GetCurrentProcessId();
          g_pLogManager = v12;
          GetModuleFileNameA(0, g_ProcessExeA, 0x104u);
          GetModuleFileNameW(0, g_ProcessExeW, 0x104u);
        }
        v11 = 1;
      }
    }
  }
LABEL_41:
  if ( !v11 )
  {
    g_pLogManager = v12;
    if ( !v10 )
      WdsSetupLogDestroy();
  }
  ReleaseMutexWrapper(MutexWrapperW);
  CloseHandleWrapper(MutexWrapperW);
  return v11;
}

```

## disassembly

```asm
0x18001bd30  mov     [rsp+arg_8], rbx
0x18001bd35  mov     [rsp+arg_10], rsi
0x18001bd3a  push    rdi
0x18001bd3b  push    r12
0x18001bd3d  push    r13
0x18001bd3f  push    r14
0x18001bd41  push    r15
0x18001bd43  sub     rsp, 390h
0x18001bd4a  mov     rax, cs:__security_cookie
0x18001bd51  xor     rax, rsp
0x18001bd54  mov     [rsp+3B8h+var_38], rax
0x18001bd5c  mov     r13d, r8d
0x18001bd5f  mov     [rsp+3B8h+var_364], edx
0x18001bd63  mov     [rsp+3B8h+var_350], rcx
0x18001bd68  xor     edx, edx; Val
0x18001bd6a  mov     r8d, 208h; Size
0x18001bd70  lea     rcx, [rsp+3B8h+var_248]; void *
0x18001bd78  call    memset_0
0x18001bd7d  mov     ecx, r13d
0x18001bd80  shr     ecx, 14h
0x18001bd83  and     ecx, 1
0x18001bd86  call    InitDefaultACL
0x18001bd8b  test    eax, eax
0x18001bd8d  jz      short loc_18001BDF7
0x18001bd8f  call    ?IsUserAdminOrLocalService@@YAHXZ; IsUserAdminOrLocalService(void)
0x18001bd94  lea     r12, aSetuplog; "SetupLog"
0x18001bd9b  lea     rbx, aGlobalSetuplog; "Global\\SetupLog"
0x18001bda2  test    eax, eax
0x18001bda4  cmovz   rbx, r12
0x18001bda8  lea     rsi, aWdssetuplogini_0; "WdsSetupLogInit"
0x18001bdaf  lea     rcx, aGlobalWdssetup; "Global\\WdsSetupLogInit"
0x18001bdb6  cmovz   rcx, rsi; lpName
0x18001bdba  call    CreateMutexWrapperW
0x18001bdbf  mov     rdi, rax
0x18001bdc2  mov     [rsp+3B8h+var_358], rax
0x18001bdc7  test    rax, rax
0x18001bdca  jnz     short loc_18001BE27
0x18001bdcc  call    cs:__imp_GetLastError
0x18001bdd3  nop     dword ptr [rax+rax+00h]
0x18001bdd8  cmp     eax, 5
0x18001bddb  jnz     short loc_18001BDEF
0x18001bddd  mov     rcx, rsi; lpName
0x18001bde0  call    CreateMutexWrapperW
0x18001bde5  mov     rdi, rax
0x18001bde8  mov     [rsp+3B8h+var_358], rax
0x18001bded  jmp     short loc_18001BDF2
0x18001bdef  mov     r12, rbx
0x18001bdf2  test    rdi, rdi
0x18001bdf5  jnz     short loc_18001BE2A
0x18001bdf7  xor     eax, eax
0x18001bdf9  mov     rcx, [rsp+3B8h+var_38]
0x18001be01  xor     rcx, rsp; StackCookie
0x18001be04  call    __security_check_cookie
0x18001be09  lea     r11, [rsp+3B8h+var_28]
0x18001be11  mov     rbx, [r11+38h]
0x18001be15  mov     rsi, [r11+40h]
0x18001be19  mov     rsp, r11
0x18001be1c  pop     r15
0x18001be1e  pop     r14
0x18001be20  pop     r13
0x18001be22  pop     r12
0x18001be24  pop     rdi
0x18001be25  retn
0x18001be27  mov     r12, rbx
0x18001be2a  mov     esi, r13d
0x18001be2d  and     esi, 10000000h
0x18001be33  mov     [rsp+3B8h+var_35C], esi
0x18001be37  xor     r15d, r15d
0x18001be3a  mov     [rsp+3B8h+var_368], r15d
0x18001be3f  mov     r14d, r13d
0x18001be42  and     r14d, 1
0x18001be46  add     r14d, r14d
0x18001be49  test    esi, esi
0x18001be4b  jnz     short loc_18001BE53
0x18001be4d  inc     cs:?g_RefCnt@@3KA; ulong g_RefCnt
0x18001be53  xor     eax, eax
0x18001be55  mov     rbx, cs:?g_pLogManager@@3PEAVILogManager@@EA; ILogManager * g_pLogManager
0x18001be5c  test    rbx, rbx
0x18001be5f  setnz   al
0x18001be62  mov     [rsp+3B8h+var_360], eax
0x18001be66  test    eax, eax
0x18001be68  jz      short loc_18001BE71
0x18001be6a  mov     [rsp+3B8h+var_348], rbx
0x18001be6f  jmp     short loc_18001BEB7
0x18001be71  call    WdsLogRegStockProviders
0x18001be76  mov     r8d, 11h; unsigned int
0x18001be7c  lea     rdx, qword_180030AA0; struct tagLOG_FIELD_INFO *
0x18001be83  mov     rcx, r12; unsigned __int16 *
0x18001be86  call    WdsLogCreate
0x18001be8b  mov     rbx, rax
0x18001be8e  mov     [rsp+3B8h+var_348], rax
0x18001be93  test    rax, rax
0x18001be96  jnz     short loc_18001BEB7
0x18001be98  test    esi, esi
0x18001be9a  jnz     short loc_18001BEA2
0x18001be9c  dec     cs:?g_RefCnt@@3KA; ulong g_RefCnt
0x18001bea2  mov     rcx, rdi
0x18001bea5  call    ReleaseMutexWrapper
0x18001beaa  mov     rcx, rdi
0x18001bead  call    CloseHandleWrapper
0x18001beb2  jmp     loc_18001BDF7
0x18001beb7  lea     r12, aSev; "Sev"
0x18001bebe  mov     [rsp+3B8h+var_290], r12
0x18001bec6  movdqa  xmm0, cs:__xmm@00000000000000000000000104000000
0x18001bece  movdqu  [rsp+3B8h+var_288], xmm0
0x18001bed7  mov     [rsp+3B8h+var_2A8], r12
0x18001bedf  movdqa  xmm1, cs:__xmm@00000000000000000000000103000000
0x18001bee7  movdqu  [rsp+3B8h+var_2A0], xmm1
0x18001bef0  mov     [rsp+3B8h+var_2C0], r12
0x18001bef8  movdqa  xmm0, cs:__xmm@00000000000000010000000105000000
0x18001bf00  movdqu  [rsp+3B8h+var_2B8], xmm0
0x18001bf09  mov     [rsp+3B8h+var_260], r12
0x18001bf11  movdqa  xmm1, cs:__xmm@00000000000000010000000067000000
0x18001bf19  movdqu  [rsp+3B8h+var_258], xmm1
0x18001bf22  mov     [rsp+3B8h+var_278], r12
0x18001bf2a  movdqa  xmm0, cs:__xmm@00000000000000010000000109000000
0x18001bf32  movdqu  [rsp+3B8h+var_270], xmm0
0x18001bf3b  mov     rax, [rsp+3B8h+var_350]
0x18001bf40  test    rax, rax
0x18001bf43  jz      loc_18001C302
0x18001bf49  mov     r8, rax; unsigned __int16 *
0x18001bf4c  mov     edx, 104h; unsigned __int64
0x18001bf51  lea     rcx, [rsp+3B8h+var_248]; unsigned __int16 *
0x18001bf59  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001bf5e  test    eax, eax
0x18001bf60  js      loc_18001C302
0x18001bf66  lea     rax, [rsp+3B8h+var_248]
0x18001bf6e  mov     [rsp+3B8h+var_340], rax
0x18001bf73  mov     [rsp+3B8h+var_338], r14d
0x18001bf7b  mov     [rsp+3B8h+var_334], 0
0x18001bf87  xor     eax, eax
0x18001bf89  mov     [rsp+3B8h+var_32C], eax
0x18001bf90  mov     [rsp+3B8h+var_2F8], r12
0x18001bf98  lea     r14, aMsg; "Msg"
0x18001bf9f  mov     [rsp+3B8h+var_2F0], r14
0x18001bfa7  lea     rax, aCon; "Con"
0x18001bfae  mov     [rsp+3B8h+var_2E8], rax
0x18001bfb6  lea     rax, aLn; "LN"
0x18001bfbd  mov     [rsp+3B8h+var_2E0], rax
0x18001bfc5  lea     rax, aFil; "Fil"
0x18001bfcc  mov     [rsp+3B8h+var_2D8], rax
0x18001bfd4  lea     rax, aFun; "Fun"
0x18001bfdb  mov     [rsp+3B8h+var_2D0], rax
0x18001bfe3  lea     rax, aErr; "Err"
0x18001bfea  mov     [rsp+3B8h+var_2C8], rax
0x18001bff2  call    ?InitializeTLSVariables@@YAHXZ; InitializeTLSVariables(void)
0x18001bff7  test    eax, eax
0x18001bff9  jz      loc_18001C302
0x18001bfff  mov     eax, 20000000h
0x18001c004  test    eax, r13d
0x18001c007  jz      loc_18001C2A1
0x18001c00d  test    cs:?g_dwPrevFlags@@3KA, eax; ulong g_dwPrevFlags
0x18001c013  jnz     loc_18001C2A1
0x18001c019  lea     rax, aDt; "DT"
0x18001c020  mov     [rsp+3B8h+var_328], rax
0x18001c028  mov     [rsp+3B8h+var_320], r12
0x18001c030  mov     [rsp+3B8h+var_318], r14
0x18001c038  lea     rax, aErr; "Err"
0x18001c03f  mov     [rsp+3B8h+var_310], rax
0x18001c047  lea     rax, aUid; "Uid"
0x18001c04e  mov     [rsp+3B8h+var_308], rax
0x18001c056  mov     [rsp+3B8h+var_300], 0
0x18001c062  mov     r12d, [rsp+3B8h+var_364]
0x18001c067  mov     r13b, r12b
0x18001c06a  and     r13b, 1
0x18001c06e  lea     rcx, [rsp+3B8h+var_2A8]
0x18001c076  lea     rax, [rsp+3B8h+var_290]
0x18001c07e  cmovnz  rcx, rax
0x18001c082  mov     [rsp+3B8h+var_350], rcx
0x18001c087  mov     rax, [rbx]
0x18001c08a  mov     [rsp+3B8h+var_380], 0
0x18001c093  lea     rdx, [rsp+3B8h+var_340]
0x18001c098  mov     [rsp+3B8h+var_388], rdx
0x18001c09d  lea     r14, qword_180032D48
0x18001c0a4  mov     [rsp+3B8h+var_390], r14
0x18001c0a9  lea     rdx, [rsp+3B8h+var_328]
0x18001c0b1  mov     [rsp+3B8h+var_398], rdx
0x18001c0b6  lea     r9, qword_180032D28
0x18001c0bd  mov     r8, rcx
0x18001c0c0  lea     rdx, qword_180030A88
0x18001c0c7  mov     rcx, rbx
0x18001c0ca  mov     rax, [rax]
0x18001c0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0d2  test    eax, eax
0x18001c0d4  jz      loc_18001C302
0x18001c0da  mov     rax, [rbx]
0x18001c0dd  mov     [rsp+3B8h+var_380], 0
0x18001c0e6  lea     rcx, [rsp+3B8h+var_340]
0x18001c0eb  mov     [rsp+3B8h+var_388], rcx
0x18001c0f0  mov     [rsp+3B8h+var_390], r14
0x18001c0f5  lea     rcx, [rsp+3B8h+var_328]
0x18001c0fd  mov     [rsp+3B8h+var_398], rcx
0x18001c102  lea     r9, qword_180032D28
0x18001c109  lea     r8, [rsp+3B8h+var_278]
0x18001c111  lea     rdx, qword_180030A88
0x18001c118  mov     rcx, rbx
0x18001c11b  mov     rax, [rax]
0x18001c11e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c123  test    eax, eax
0x18001c125  jz      loc_18001C302
0x18001c12b  mov     r14d, r12d
0x18001c12e  and     r14d, 8
0x18001c132  jz      loc_18001C1E2
0x18001c138  mov     rax, [rbx]
0x18001c13b  mov     [rsp+3B8h+var_380], 0
0x18001c144  mov     [rsp+3B8h+var_388], 0
0x18001c14d  mov     [rsp+3B8h+var_390], 0
0x18001c156  lea     rcx, [rsp+3B8h+var_2F8]
0x18001c15e  mov     [rsp+3B8h+var_398], rcx
0x18001c163  lea     r9, qword_180030A58
0x18001c16a  mov     r8, [rsp+3B8h+var_350]
0x18001c16f  lea     rdx, qword_180030A88
0x18001c176  mov     rcx, rbx
0x18001c179  mov     rax, [rax]
0x18001c17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c181  test    eax, eax
0x18001c183  jz      loc_18001C302
0x18001c189  test    r13b, r13b
0x18001c18c  jz      short loc_18001C1E2
0x18001c18e  mov     rax, [rbx]
0x18001c191  mov     [rsp+3B8h+var_380], 0
0x18001c19a  mov     [rsp+3B8h+var_388], 0
0x18001c1a3  mov     [rsp+3B8h+var_390], 0
0x18001c1ac  lea     rcx, [rsp+3B8h+var_2F8]
0x18001c1b4  mov     [rsp+3B8h+var_398], rcx
0x18001c1b9  lea     r9, qword_180030A58
0x18001c1c0  lea     r8, [rsp+3B8h+var_260]
0x18001c1c8  lea     rdx, qword_180030A88
0x18001c1cf  mov     rcx, rbx
0x18001c1d2  mov     rax, [rax]
0x18001c1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1da  test    eax, eax
0x18001c1dc  jz      loc_18001C302
0x18001c1e2  test    r12b, 4
0x18001c1e6  jz      loc_18001C299
0x18001c1ec  mov     rax, [rbx]
0x18001c1ef  mov     [rsp+3B8h+var_380], 0
0x18001c1f8  lea     rcx, [rsp+3B8h+var_340]
0x18001c1fd  mov     [rsp+3B8h+var_388], rcx
0x18001c202  lea     rcx, qword_180032D48
0x18001c209  mov     [rsp+3B8h+var_390], rcx
0x18001c20e  lea     rcx, [rsp+3B8h+var_328]
0x18001c216  mov     [rsp+3B8h+var_398], rcx
0x18001c21b  lea     r9, qword_180032D28
0x18001c222  lea     r8, [rsp+3B8h+var_2C0]
0x18001c22a  lea     rdx, qword_180030A88
0x18001c231  mov     rcx, rbx
0x18001c234  mov     rax, [rax]
0x18001c237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c23c  test    eax, eax
0x18001c23e  jz      loc_18001C302
0x18001c244  test    r14d, r14d
0x18001c247  jz      short loc_18001C299
0x18001c249  mov     rax, [rbx]
0x18001c24c  mov     [rsp+3B8h+var_380], 0
0x18001c255  mov     [rsp+3B8h+var_388], 0
0x18001c25e  mov     [rsp+3B8h+var_390], 0
0x18001c267  lea     rcx, [rsp+3B8h+var_2F8]
0x18001c26f  mov     [rsp+3B8h+var_398], rcx
0x18001c274  lea     r9, qword_180030A58
0x18001c27b  lea     r8, [rsp+3B8h+var_2C0]
0x18001c283  lea     rdx, qword_180030A88
0x18001c28a  mov     rcx, rbx
0x18001c28d  mov     rax, [rax]
0x18001c290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c295  test    eax, eax
0x18001c297  jz      short loc_18001C302
0x18001c299  bts     cs:?g_dwPrevFlags@@3KA, 1Dh; ulong g_dwPrevFlags
0x18001c2a1  cmp     [rsp+3B8h+var_360], 0
0x18001c2a6  jnz     short loc_18001C2F7
0x18001c2a8  call    cs:__imp_GetCurrentProcessId
0x18001c2af  nop     dword ptr [rax+rax+00h]
0x18001c2b4  mov     cs:?g_ProcessID@@3KA, eax; ulong g_ProcessID
0x18001c2ba  mov     cs:?g_pLogManager@@3PEAVILogManager@@EA, rbx; ILogManager * g_pLogManager
0x18001c2c1  mov     r8d, 104h; nSize
0x18001c2c7  lea     rdx, ?g_ProcessExeA@@3PADA; "<unknown>"
0x18001c2ce  xor     ecx, ecx; hModule
0x18001c2d0  call    cs:__imp_GetModuleFileNameA
0x18001c2d7  nop     dword ptr [rax+rax+00h]
0x18001c2dc  mov     r8d, 104h; nSize
0x18001c2e2  lea     rdx, ?g_ProcessExeW@@3PAGA; "<unknown>"
0x18001c2e9  xor     ecx, ecx; hModule
0x18001c2eb  call    cs:__imp_GetModuleFileNameW
0x18001c2f2  nop     dword ptr [rax+rax+00h]
0x18001c2f7  mov     r15d, 1
0x18001c2fd  mov     [rsp+3B8h+var_368], r15d
0x18001c302  test    r15d, r15d
0x18001c305  jnz     short loc_18001C317
0x18001c307  mov     cs:?g_pLogManager@@3PEAVILogManager@@EA, rbx; ILogManager * g_pLogManager
0x18001c30e  test    esi, esi
0x18001c310  jnz     short loc_18001C317
0x18001c312  call    WdsSetupLogDestroy
0x18001c317  mov     rcx, rdi
0x18001c31a  call    ReleaseMutexWrapper
0x18001c31f  mov     rcx, rdi
0x18001c322  call    CloseHandleWrapper
0x18001c327  mov     eax, r15d
0x18001c32a  jmp     loc_18001BDF9
0x180029057  push    rbp
0x180029059  sub     rsp, 50h
  ... truncated ...
```
