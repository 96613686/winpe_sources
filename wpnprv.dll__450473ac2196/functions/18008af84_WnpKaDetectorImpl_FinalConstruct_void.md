# WnpKaDetectorImpl::FinalConstruct(void)

- ea: `0x18008af84`
- end: `0x18008b49b`
- name: `?FinalConstruct@WnpKaDetectorImpl@@IEAAJXZ`
- size: `1303`
- prototype: `__int64 __fastcall(char *pv)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18008aa60`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x1800670fc`
- `0x180086bd8`
- `0x18008af84`
- `0x18008df50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008b02d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008b0ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008b141`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008b02d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008b0ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008b141`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18008b01d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18008b01d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b071`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b0cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b0f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b17f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b2d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b35c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b3b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b071`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b0cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b0f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b17f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b2d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b35c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b3b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b405`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008b2bf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008b2bf`

## pseudocode

```c
__int64 __fastcall WnpKaDetectorImpl::FinalConstruct(char *pv)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v4; // sf
  signed int v5; // eax
  HANDLE v6; // rax
  signed int v7; // eax
  bool v8; // sf
  signed int v9; // eax
  HANDLE v10; // rax
  signed int v11; // eax
  bool v12; // sf
  signed int v13; // eax
  int Instance; // eax
  unsigned int v15; // ebx
  PVOID *v16; // rcx
  __int64 v17; // rdx
  int AuthManager; // eax
  PTP_WORK v19; // rax
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  struct _TP_CALLBACK_ENVIRON_V3 pcbe; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
  }
  *(_QWORD *)&pcbe.Version = 3;
  pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  *(_QWORD *)&pcbe.Size = 72;
  memset(&pcbe.Pool, 0, 52);
  InitializeCriticalSection((LPCRITICAL_SECTION)(pv + 352));
  EventW = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)pv + 50) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v4 = LastError < 0;
    if ( LastError > 0 )
      v4 = 1;
    if ( v4
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = GetLastError();
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
        (unsigned int)v5);
    }
  }
  if ( (unsigned __int64)(*((_QWORD *)pv + 50) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v23 = GetLastError();
    v15 = v23;
    if ( v23 > 0 )
      v15 = (unsigned __int16)v23 | 0x80070000;
    if ( (v15 & 0x80000000) == 0 )
      v15 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
      (const char *)v15,
      pcbe.Version);
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v17 = 16;
        goto LABEL_87;
      }
      goto LABEL_89;
    }
  }
  else
  {
    v6 = CreateEventW(0, 1, 1, 0);
    *((_QWORD *)pv + 41) = v6;
    if ( !v6 )
    {
      v7 = GetLastError();
      v8 = v7 < 0;
      if ( v7 > 0 )
        v8 = 1;
      if ( v8
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = GetLastError();
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
          (unsigned int)v9);
      }
    }
    if ( (unsigned __int64)(*((_QWORD *)pv + 41) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v22 = GetLastError();
      v15 = v22;
      if ( v22 > 0 )
        v15 = (unsigned __int16)v22 | 0x80070000;
      if ( (v15 & 0x80000000) == 0 )
        v15 = -2147467259;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
        (const char *)v15,
        pcbe.Version);
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v17 = 18;
          goto LABEL_87;
        }
        goto LABEL_89;
      }
    }
    else
    {
      v10 = CreateEventW(0, 1, 1, 0);
      *((_QWORD *)pv + 51) = v10;
      if ( !v10 )
      {
        v11 = GetLastError();
        v12 = v11 < 0;
        if ( v11 > 0 )
          v12 = 1;
        if ( v12
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = GetLastError();
          if ( v13 > 0 )
            v13 = (unsigned __int16)v13 | 0x80070000;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
            (unsigned int)v13);
        }
      }
      if ( (unsigned __int64)(*((_QWORD *)pv + 51) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        v21 = GetLastError();
        v15 = v21;
        if ( v21 > 0 )
          v15 = (unsigned __int16)v21 | 0x80070000;
        if ( (v15 & 0x80000000) == 0 )
          v15 = -2147467259;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x103,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
          (const char *)v15,
          pcbe.Version);
        v16 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v17 = 20;
            goto LABEL_87;
          }
          goto LABEL_89;
        }
      }
      else
      {
        Instance = WNPMessageGenerator::CreateInstance((struct WNPMessageGenerator **)pv + 15);
        v15 = Instance;
        if ( Instance >= 0 )
        {
          AuthManager = CreateAuthManager(2, pv + 112);
          v15 = AuthManager;
          if ( AuthManager >= 0 )
          {
            v19 = CreateThreadpoolWork(WnpKaDetectorImpl::BackgroundProcessing, pv, &pcbe);
            *((_QWORD *)pv + 49) = v19;
            if ( v19 )
              goto LABEL_65;
            v20 = GetLastError();
            v15 = v20;
            if ( v20 > 0 )
              v15 = (unsigned __int16)v20 | 0x80070000;
            if ( (v15 & 0x80000000) == 0 )
            {
LABEL_65:
              WnpKaDetectorImpl::ReadRegistryOverrides((WnpKaDetectorImpl *)pv);
LABEL_88:
              v16 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_89;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, v15);
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x112,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
              (const char *)v15,
              pcbe.Version);
            v16 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                v17 = 26;
                goto LABEL_87;
              }
              goto LABEL_89;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                23,
                &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
                (unsigned int)AuthManager);
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x10B,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
              (const char *)v15,
              pcbe.Version);
            v16 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                v17 = 24;
                goto LABEL_87;
              }
LABEL_89:
              if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 8) != 0 && *((_BYTE *)v16 + 25) >= 6u )
                WPP_SF_d(v16[2], 27, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, v15);
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
              (unsigned int)Instance);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x107,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
            (const char *)v15,
            pcbe.Version);
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              v17 = 22;
LABEL_87:
              WPP_SF_d(v16[2], v17, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, v15);
              goto LABEL_88;
            }
            goto LABEL_89;
          }
        }
      }
    }
  }
  return v15;
}

```

## disassembly

```asm
0x18008af84  push    rbp
0x18008af86  push    rbx
0x18008af87  push    rdi
0x18008af88  push    r12
0x18008af8a  push    r14
0x18008af8c  push    r15
0x18008af8e  mov     rbp, rsp
0x18008af91  sub     rsp, 78h
0x18008af95  mov     rdi, rcx
0x18008af98  mov     rcx, cs:WPP_GLOBAL_Control
0x18008af9f  lea     r15, WPP_GLOBAL_Control
0x18008afa6  lea     r14, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008afad  cmp     rcx, r15
0x18008afb0  jz      short loc_18008AFCF
0x18008afb2  test    byte ptr [rcx+1Ch], 8
0x18008afb6  jz      short loc_18008AFCF
0x18008afb8  cmp     byte ptr [rcx+19h], 6
0x18008afbc  jb      short loc_18008AFCF
0x18008afbe  mov     rcx, [rcx+10h]
0x18008afc2  mov     edx, 0Eh
0x18008afc7  mov     r8, r14
0x18008afca  call    WPP_SF_
0x18008afcf  xorps   xmm0, xmm0
0x18008afd2  mov     qword ptr [rbp+pcbe.Version], 3
0x18008afda  mov     ebx, 1
0x18008afdf  movdqa  xmmword ptr [rbp+pcbe.RaceDll], xmm0
0x18008afe4  lea     rcx, [rdi+160h]; lpCriticalSection
0x18008afeb  mov     [rbp+pcbe.CallbackPriority], ebx
0x18008afee  mov     qword ptr [rbp+pcbe.Size], 48h ; 'H'
0x18008aff6  mov     [rbp+pcbe.Pool], 0
0x18008affe  mov     [rbp+pcbe.CleanupGroup], 0
0x18008b006  mov     [rbp+pcbe.CleanupGroupCancelCallback], 0
0x18008b00e  mov     [rbp+pcbe.FinalizationCallback], 0
0x18008b016  mov     dword ptr [rbp+pcbe.u], 0
0x18008b01d  call    cs:__imp_InitializeCriticalSection
0x18008b023  xor     r9d, r9d; lpName
0x18008b026  mov     r8d, ebx; bInitialState
0x18008b029  mov     edx, ebx; bManualReset
0x18008b02b  xor     ecx, ecx; lpEventAttributes
0x18008b02d  call    cs:__imp_CreateEventW
0x18008b033  mov     [rdi+190h], rax
0x18008b03a  mov     r12d, 80070000h
0x18008b040  test    rax, rax
0x18008b043  jnz     short loc_18008B09C
0x18008b045  call    cs:__imp_GetLastError
0x18008b04b  test    eax, eax
0x18008b04d  jle     short loc_18008B057
0x18008b04f  movzx   eax, ax
0x18008b052  or      eax, r12d
0x18008b055  test    eax, eax
0x18008b057  jns     short loc_18008B09C
0x18008b059  mov     rax, cs:WPP_GLOBAL_Control
0x18008b060  cmp     rax, r15
0x18008b063  jz      short loc_18008B09C
0x18008b065  test    byte ptr [rax+1Ch], 8
0x18008b069  jz      short loc_18008B09C
0x18008b06b  cmp     byte ptr [rax+19h], 2
0x18008b06f  jb      short loc_18008B09C
0x18008b071  call    cs:__imp_GetLastError
0x18008b077  test    eax, eax
0x18008b079  jle     short loc_18008B081
0x18008b07b  movzx   eax, ax
0x18008b07e  or      eax, r12d
0x18008b081  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b088  mov     edx, 0Fh
0x18008b08d  mov     r9d, eax
0x18008b090  mov     r8, r14
0x18008b093  mov     rcx, [rcx+10h]
0x18008b097  call    WPP_SF_d
0x18008b09c  mov     rax, [rdi+190h]
0x18008b0a3  sub     rax, rbx
0x18008b0a6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008b0aa  ja      loc_18008B405
0x18008b0b0  xor     r9d, r9d; lpName
0x18008b0b3  mov     r8d, ebx; bInitialState
0x18008b0b6  mov     edx, ebx; bManualReset
0x18008b0b8  xor     ecx, ecx; lpEventAttributes
0x18008b0ba  call    cs:__imp_CreateEventW
0x18008b0c0  mov     [rdi+148h], rax
0x18008b0c7  test    rax, rax
0x18008b0ca  jnz     short loc_18008B123
0x18008b0cc  call    cs:__imp_GetLastError
0x18008b0d2  test    eax, eax
0x18008b0d4  jle     short loc_18008B0DE
0x18008b0d6  movzx   eax, ax
0x18008b0d9  or      eax, r12d
0x18008b0dc  test    eax, eax
0x18008b0de  jns     short loc_18008B123
0x18008b0e0  mov     rax, cs:WPP_GLOBAL_Control
0x18008b0e7  cmp     rax, r15
0x18008b0ea  jz      short loc_18008B123
0x18008b0ec  test    byte ptr [rax+1Ch], 8
0x18008b0f0  jz      short loc_18008B123
0x18008b0f2  cmp     byte ptr [rax+19h], 2
0x18008b0f6  jb      short loc_18008B123
0x18008b0f8  call    cs:__imp_GetLastError
0x18008b0fe  test    eax, eax
0x18008b100  jle     short loc_18008B108
0x18008b102  movzx   eax, ax
0x18008b105  or      eax, r12d
0x18008b108  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b10f  mov     edx, 11h
0x18008b114  mov     r9d, eax
0x18008b117  mov     r8, r14
0x18008b11a  mov     rcx, [rcx+10h]
0x18008b11e  call    WPP_SF_d
0x18008b123  mov     rax, [rdi+148h]
0x18008b12a  sub     rax, rbx
0x18008b12d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008b131  ja      loc_18008B3B4
0x18008b137  xor     r9d, r9d; lpName
0x18008b13a  mov     r8d, ebx; bInitialState
0x18008b13d  mov     edx, ebx; bManualReset
0x18008b13f  xor     ecx, ecx; lpEventAttributes
0x18008b141  call    cs:__imp_CreateEventW
0x18008b147  mov     [rdi+198h], rax
0x18008b14e  test    rax, rax
0x18008b151  jnz     short loc_18008B1AA
0x18008b153  call    cs:__imp_GetLastError
0x18008b159  test    eax, eax
0x18008b15b  jle     short loc_18008B165
0x18008b15d  movzx   eax, ax
0x18008b160  or      eax, r12d
0x18008b163  test    eax, eax
0x18008b165  jns     short loc_18008B1AA
0x18008b167  mov     rax, cs:WPP_GLOBAL_Control
0x18008b16e  cmp     rax, r15
0x18008b171  jz      short loc_18008B1AA
0x18008b173  test    byte ptr [rax+1Ch], 8
0x18008b177  jz      short loc_18008B1AA
0x18008b179  cmp     byte ptr [rax+19h], 2
0x18008b17d  jb      short loc_18008B1AA
0x18008b17f  call    cs:__imp_GetLastError
0x18008b185  test    eax, eax
0x18008b187  jle     short loc_18008B18F
0x18008b189  movzx   eax, ax
0x18008b18c  or      eax, r12d
0x18008b18f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b196  mov     edx, 13h
0x18008b19b  mov     r9d, eax
0x18008b19e  mov     r8, r14
0x18008b1a1  mov     rcx, [rcx+10h]
0x18008b1a5  call    WPP_SF_d
0x18008b1aa  mov     rax, [rdi+198h]
0x18008b1b1  sub     rax, rbx
0x18008b1b4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008b1b8  ja      loc_18008B35C
0x18008b1be  lea     rcx, [rdi+78h]; struct WNPMessageGenerator **
0x18008b1c2  call    ?CreateInstance@WNPMessageGenerator@@SAJPEAPEAV1@@Z; WNPMessageGenerator::CreateInstance(WNPMessageGenerator * *)
0x18008b1c7  mov     ebx, eax
0x18008b1c9  test    eax, eax
0x18008b1cb  jns     short loc_18008B235
0x18008b1cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b1d4  cmp     rcx, r15
0x18008b1d7  jz      short loc_18008B1F9
0x18008b1d9  test    byte ptr [rcx+1Ch], 8
0x18008b1dd  jz      short loc_18008B1F9
0x18008b1df  cmp     byte ptr [rcx+19h], 2
0x18008b1e3  jb      short loc_18008B1F9
0x18008b1e5  mov     rcx, [rcx+10h]
0x18008b1e9  mov     edx, 15h
0x18008b1ee  mov     r9d, eax
0x18008b1f1  mov     r8, r14
0x18008b1f4  call    WPP_SF_d
0x18008b1f9  mov     rcx, [rbp+30h]; this
0x18008b1fd  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008b204  mov     r9d, ebx; char *
0x18008b207  mov     edx, 107h; void *
0x18008b20c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008b211  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b218  cmp     rcx, r15
0x18008b21b  jz      loc_18008B48B
0x18008b221  test    byte ptr [rcx+1Ch], 80h
0x18008b225  jz      loc_18008B466
0x18008b22b  mov     edx, 16h
0x18008b230  jmp     loc_18008B450
0x18008b235  lea     rdx, [rdi+70h]
0x18008b239  mov     ecx, 2
0x18008b23e  call    ?CreateAuthManager@@YAJW4_WPN_QOS_CONNECTION_TYPE@@PEAPEAVIAuthManager@@@Z; CreateAuthManager(_WPN_QOS_CONNECTION_TYPE,IAuthManager * *)
0x18008b243  mov     ebx, eax
0x18008b245  test    eax, eax
0x18008b247  jns     short loc_18008B2B1
0x18008b249  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b250  cmp     rcx, r15
0x18008b253  jz      short loc_18008B275
0x18008b255  test    byte ptr [rcx+1Ch], 8
0x18008b259  jz      short loc_18008B275
0x18008b25b  cmp     byte ptr [rcx+19h], 2
0x18008b25f  jb      short loc_18008B275
0x18008b261  mov     rcx, [rcx+10h]
0x18008b265  mov     edx, 17h
0x18008b26a  mov     r9d, eax
0x18008b26d  mov     r8, r14
0x18008b270  call    WPP_SF_d
0x18008b275  mov     rcx, [rbp+30h]; this
0x18008b279  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008b280  mov     r9d, ebx; char *
0x18008b283  mov     edx, 10Bh; void *
0x18008b288  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008b28d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b294  cmp     rcx, r15
0x18008b297  jz      loc_18008B48B
0x18008b29d  test    byte ptr [rcx+1Ch], 80h
0x18008b2a1  jz      loc_18008B466
0x18008b2a7  mov     edx, 18h
0x18008b2ac  jmp     loc_18008B450
0x18008b2b1  lea     r8, [rbp+pcbe]; pcbe
0x18008b2b5  mov     rdx, rdi; pv
0x18008b2b8  lea     rcx, ?BackgroundProcessing@WnpKaDetectorImpl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18008b2bf  call    cs:__imp_CreateThreadpoolWork
0x18008b2c5  mov     [rdi+188h], rax
0x18008b2cc  test    rax, rax
0x18008b2cf  jnz     short loc_18008B34F
0x18008b2d1  call    cs:__imp_GetLastError
0x18008b2d7  mov     ebx, eax
0x18008b2d9  test    eax, eax
0x18008b2db  jle     short loc_18008B2E3
0x18008b2dd  movzx   ebx, ax
0x18008b2e0  or      ebx, r12d
0x18008b2e3  test    ebx, ebx
0x18008b2e5  jns     short loc_18008B34F
0x18008b2e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b2ee  cmp     rcx, r15
0x18008b2f1  jz      short loc_18008B313
0x18008b2f3  test    byte ptr [rcx+1Ch], 8
0x18008b2f7  jz      short loc_18008B313
0x18008b2f9  cmp     byte ptr [rcx+19h], 2
0x18008b2fd  jb      short loc_18008B313
0x18008b2ff  mov     rcx, [rcx+10h]
0x18008b303  mov     edx, 19h
0x18008b308  mov     r9d, ebx
0x18008b30b  mov     r8, r14
0x18008b30e  call    WPP_SF_d
0x18008b313  mov     rcx, [rbp+30h]; this
0x18008b317  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008b31e  mov     r9d, ebx; char *
0x18008b321  mov     edx, 112h; void *
0x18008b326  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008b32b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b332  cmp     rcx, r15
0x18008b335  jz      loc_18008B48B
0x18008b33b  test    byte ptr [rcx+1Ch], 80h
0x18008b33f  jz      loc_18008B466
0x18008b345  mov     edx, 1Ah
0x18008b34a  jmp     loc_18008B450
0x18008b34f  mov     rcx, rdi; this
0x18008b352  call    ?ReadRegistryOverrides@WnpKaDetectorImpl@@AEAAXXZ; WnpKaDetectorImpl::ReadRegistryOverrides(void)
0x18008b357  jmp     loc_18008B45F
0x18008b35c  call    cs:__imp_GetLastError
0x18008b362  mov     ebx, eax
0x18008b364  test    eax, eax
0x18008b366  jle     short loc_18008B36E
0x18008b368  movzx   ebx, ax
0x18008b36b  or      ebx, r12d
0x18008b36e  mov     rcx, [rbp+30h]; this
0x18008b372  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008b379  test    ebx, ebx
0x18008b37b  mov     eax, 80004005h
0x18008b380  mov     edx, 103h; void *
0x18008b385  cmovns  ebx, eax
0x18008b388  mov     r9d, ebx; char *
0x18008b38b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008b390  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b397  cmp     rcx, r15
0x18008b39a  jz      loc_18008B48B
0x18008b3a0  test    byte ptr [rcx+1Ch], 80h
0x18008b3a4  jz      loc_18008B466
0x18008b3aa  mov     edx, 14h
0x18008b3af  jmp     loc_18008B450
0x18008b3b4  call    cs:__imp_GetLastError
0x18008b3ba  mov     ebx, eax
0x18008b3bc  test    eax, eax
0x18008b3be  jle     short loc_18008B3C6
0x18008b3c0  movzx   ebx, ax
0x18008b3c3  or      ebx, r12d
0x18008b3c6  mov     rcx, [rbp+30h]; this
0x18008b3ca  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008b3d1  test    ebx, ebx
0x18008b3d3  mov     eax, 80004005h
0x18008b3d8  mov     edx, 0F9h; void *
0x18008b3dd  cmovns  ebx, eax
0x18008b3e0  mov     r9d, ebx; char *
0x18008b3e3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008b3e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b3ef  cmp     rcx, r15
0x18008b3f2  jz      loc_18008B48B
0x18008b3f8  test    byte ptr [rcx+1Ch], 80h
0x18008b3fc  jz      short loc_18008B466
0x18008b3fe  mov     edx, 12h
0x18008b403  jmp     short loc_18008B450
0x18008b405  call    cs:__imp_GetLastError
0x18008b40b  mov     ebx, eax
0x18008b40d  test    eax, eax
0x18008b40f  jle     short loc_18008B417
0x18008b411  movzx   ebx, ax
0x18008b414  or      ebx, r12d
0x18008b417  mov     rcx, [rbp+30h]; this
0x18008b41b  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008b422  test    ebx, ebx
0x18008b424  mov     eax, 80004005h
  ... truncated ...
```
