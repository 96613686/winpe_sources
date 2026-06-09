# KspOpenStorageProviderInternal(unsigned __int64 *,ushort const *,ulong)

- ea: `0x180024e98`
- end: `0x1800253b7`
- name: `?KspOpenStorageProviderInternal@@YAJPEA_KPEBGK@Z`
- size: `1311`
- prototype: `int(unsigned __int64 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002af40`

## callees

- `0x180009e82`
- `0x18000a3c8`
- `0x18000a408`
- `0x18000abfc`
- `0x18000d2a8`
- `0x180011fd8`
- `0x180012b24`
- `0x180013734`
- `0x180013aac`
- `0x180024e98`
- `0x18002b140`
- `0x1800375d4`
- `0x18003aea8`
- `0x18003af5c`
- `0x18003afc0`
- `0x18003b9e0`
- `0x18003c20e`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x18002527e`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002527e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KspOpenStorageProviderInternal(unsigned __int64 *a1, const unsigned __int16 *a2, int a3)
{
  char v3; // si
  PVOID v6; // rcx
  int Settings; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rcx
  _QWORD *v13; // rcx
  int v14; // edx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  char *v19; // rax
  char *v20; // rdi
  __int64 v21; // rcx
  __int64 v22; // rcx
  void **v24; // [rsp+30h] [rbp-30h] BYREF
  __int64 v25; // [rsp+38h] [rbp-28h]
  _DWORD v26[4]; // [rsp+40h] [rbp-20h] BYREF
  void *(__stdcall *v27)(size_t); // [rsp+50h] [rbp-10h]
  __int64 (__fastcall *v28)(_QWORD); // [rsp+58h] [rbp-8h]

  v3 = a3;
  v26[3] = 0;
  v24 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v25 = 0;
  if ( !a1 || !a2 )
  {
    WppTraceIndent(a1, 2);
    v10 = 2148073511LL;
    Settings = -2146893785;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 260;
      goto LABEL_71;
    }
    goto LABEL_72;
  }
  if ( (a3 & 0xFFFFFFBF) != 0 )
  {
    WppTraceIndent(a1, 2);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        261,
        (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        (_DWORD)WPP_pszIndent,
        v3);
    }
    WppTraceIndent(v6, 2);
    Settings = -2146893815;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 262;
      v10 = 2148073481LL;
LABEL_71:
      WPP_SF_d(v8[2], v9, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, v10);
      goto LABEL_72;
    }
    goto LABEL_72;
  }
  if ( !wcscmp_0(a2, L"Microsoft Smart Card Key Storage Provider")
    || !wcscmp_0(a2, L"Microsoft Base Smart Card Crypto Provider") )
  {
    Settings = KspEnterCriticalSection(&g_KspState);
    if ( Settings )
    {
      WppTraceIndent(v12, 2);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 264;
LABEL_64:
        WPP_SF_sd(
          v13[2],
          v14,
          (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
          (_DWORD)WPP_pszIndent,
          Settings);
      }
    }
    else
    {
      Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v24, &g_KspState);
      v26[0] = 50000;
      v26[1] = 10000;
      v26[2] = 5;
      v27 = MIDL_user_allocate;
      v28 = CspFreeH;
      if ( qword_18004C240 || (Settings = ScCacheInitializeCache(&qword_18004C240, v26)) == 0 )
      {
        if ( qword_18004C278 || (Settings = ScCacheInitializeCache(&qword_18004C278, v26)) == 0 )
        {
          if ( dword_18004C290 || (Settings = RegConfigGetSettings(&dword_18004C290)) == 0 )
          {
            Settings = TransactionManagerInitialize((unsigned int)dword_18004C29C);
            if ( Settings )
            {
              WppTraceIndent(v18, 2);
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v14 = 268;
                goto LABEL_64;
              }
            }
            else
            {
              v19 = (char *)MIDL_user_allocate(0x98u);
              v20 = v19;
              if ( !v19 )
              {
                Settings = -2146893810;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_s(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    269,
                    &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
                    WPP_pszIndent);
                }
                goto LABEL_72;
              }
              memset_0(v19 + 8, 0, 0x90u);
              *(_QWORD *)v20 = &g_KspState;
              ++dword_18004C280;
              CspInitializeCriticalSection(v20 + 16);
              *((_DWORD *)v20 + 14) = 1;
              if ( phProvider
                || (Settings = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0)) == 0 )
              {
                if ( v25 )
                {
                  v25 = 0;
                  KspLeaveCriticalSection(&g_KspState);
                }
                *((_DWORD *)v20 + 15) = v3 & 0x40;
                Settings = HtAddHandle(v20, 3, a1);
                if ( !Settings )
                  goto LABEL_65;
                WppTraceIndent(v22, 2);
                v13 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_65;
                }
                v14 = 271;
                goto LABEL_64;
              }
              WppTraceIndent(v21, 2);
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v14 = 270;
                goto LABEL_64;
              }
            }
          }
          else
          {
            WppTraceIndent(v17, 2);
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = 267;
              goto LABEL_64;
            }
          }
        }
        else
        {
          WppTraceIndent(v16, 2);
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = 266;
            goto LABEL_64;
          }
        }
      }
      else
      {
        WppTraceIndent(v15, 2);
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = 265;
          goto LABEL_64;
        }
      }
    }
LABEL_65:
    if ( Settings > 0 )
      Settings = (unsigned __int16)Settings | 0x80070000;
    goto LABEL_72;
  }
  WppTraceIndent(v11, 2);
  v10 = 2148073511LL;
  Settings = -2146893785;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 263;
    goto LABEL_71;
  }
LABEL_72:
  v24 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v24);
  return (unsigned int)Settings;
}

```

## disassembly

```asm
0x180024e98  push    rbp
0x180024e9a  push    rbx
0x180024e9b  push    rsi
0x180024e9c  push    rdi
0x180024e9d  push    r12
0x180024e9f  push    r13
0x180024ea1  push    r14
0x180024ea3  mov     rbp, rsp
0x180024ea6  sub     rsp, 60h
0x180024eaa  mov     esi, r8d
0x180024ead  mov     rbx, rdx
0x180024eb0  mov     r14, rcx
0x180024eb3  mov     [rbp+var_14], 0
0x180024eba  lea     r13, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180024ec1  mov     [rbp+var_30], r13
0x180024ec5  mov     [rbp+var_28], 0
0x180024ecd  test    rcx, rcx
0x180024ed0  jz      loc_180025351
0x180024ed6  test    rdx, rdx
0x180024ed9  jz      loc_180025351
0x180024edf  test    r8d, 0FFFFFFBFh
0x180024ee6  jz      loc_180024F75
0x180024eec  mov     edx, 2
0x180024ef1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024ef6  lea     rdi, WPP_GLOBAL_Control
0x180024efd  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f04  cmp     rcx, rdi
0x180024f07  jz      short loc_180024F35
0x180024f09  test    byte ptr [rcx+1Ch], 1
0x180024f0d  jz      short loc_180024F35
0x180024f0f  cmp     byte ptr [rcx+19h], 2
0x180024f13  jb      short loc_180024F35
0x180024f15  mov     edx, 105h
0x180024f1a  mov     [rsp+60h+var_40], esi
0x180024f1e  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180024f25  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180024f2c  mov     rcx, [rcx+10h]
0x180024f30  call    WPP_SF_sd
0x180024f35  mov     edx, 2
0x180024f3a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024f3f  mov     ebx, 80090009h
0x180024f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f4b  cmp     rcx, rdi
0x180024f4e  jz      loc_180025399
0x180024f54  test    byte ptr [rcx+1Ch], 1
0x180024f58  jz      loc_180025399
0x180024f5e  cmp     byte ptr [rcx+19h], 2
0x180024f62  jb      loc_180025399
0x180024f68  mov     edx, 106h
0x180024f6d  mov     r9d, ebx
0x180024f70  jmp     loc_180025388
0x180024f75  lea     rdx, aMicrosoftSmart; "Microsoft Smart Card Key Storage Provid"...
0x180024f7c  mov     rcx, rbx; String1
0x180024f7f  call    wcscmp_0
0x180024f84  test    eax, eax
0x180024f86  jz      short loc_180024FE3
0x180024f88  lea     rdx, aMicrosoftBaseS; "Microsoft Base Smart Card Crypto Provid"...
0x180024f8f  mov     rcx, rbx; String1
0x180024f92  call    wcscmp_0
0x180024f97  test    eax, eax
0x180024f99  jz      short loc_180024FE3
0x180024f9b  mov     edx, 2
0x180024fa0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024fa5  mov     r9d, 80090027h
0x180024fab  mov     ebx, r9d
0x180024fae  lea     rdi, WPP_GLOBAL_Control
0x180024fb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180024fbc  cmp     rcx, rdi
0x180024fbf  jz      loc_180025399
0x180024fc5  test    byte ptr [rcx+1Ch], 1
0x180024fc9  jz      loc_180025399
0x180024fcf  cmp     byte ptr [rcx+19h], 2
0x180024fd3  jb      loc_180025399
0x180024fd9  mov     edx, 107h
0x180024fde  jmp     loc_180025388
0x180024fe3  lea     r12, g_KspState
0x180024fea  mov     rcx, r12
0x180024fed  call    KspEnterCriticalSection
0x180024ff2  mov     ebx, eax
0x180024ff4  test    eax, eax
0x180024ff6  jz      short loc_180025037
0x180024ff8  mov     edx, 2
0x180024ffd  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025002  lea     rdi, WPP_GLOBAL_Control
0x180025009  mov     rcx, cs:WPP_GLOBAL_Control
0x180025010  cmp     rcx, rdi
0x180025013  jz      loc_180025342
0x180025019  test    byte ptr [rcx+1Ch], 1
0x18002501d  jz      loc_180025342
0x180025023  cmp     byte ptr [rcx+19h], 2
0x180025027  jb      loc_180025342
0x18002502d  mov     edx, 108h
0x180025032  jmp     loc_180025327
0x180025037  mov     rdx, r12
0x18002503a  lea     rcx, [rbp+var_30]
0x18002503e  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180025043  mov     [rbp+var_20], 0C350h
0x18002504a  mov     [rbp+var_1C], 2710h
0x180025051  mov     [rbp+var_18], 5
0x180025058  lea     rax, MIDL_user_allocate
0x18002505f  mov     [rbp+var_10], rax
0x180025063  lea     rax, CspFreeH
0x18002506a  mov     [rbp+var_8], rax
0x18002506e  cmp     cs:qword_18004C240, 0
0x180025076  jnz     short loc_1800250CD
0x180025078  lea     rdx, [rbp+var_20]
0x18002507c  lea     rcx, qword_18004C240
0x180025083  call    ScCacheInitializeCache
0x180025088  mov     ebx, eax
0x18002508a  test    eax, eax
0x18002508c  jz      short loc_1800250CD
0x18002508e  mov     edx, 2
0x180025093  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025098  lea     rdi, WPP_GLOBAL_Control
0x18002509f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800250a6  cmp     rcx, rdi
0x1800250a9  jz      loc_180025342
0x1800250af  test    byte ptr [rcx+1Ch], 1
0x1800250b3  jz      loc_180025342
0x1800250b9  cmp     byte ptr [rcx+19h], 2
0x1800250bd  jb      loc_180025342
0x1800250c3  mov     edx, 109h
0x1800250c8  jmp     loc_180025327
0x1800250cd  cmp     cs:qword_18004C278, 0
0x1800250d5  jnz     short loc_18002512C
0x1800250d7  lea     rdx, [rbp+var_20]
0x1800250db  lea     rcx, qword_18004C278
0x1800250e2  call    ScCacheInitializeCache
0x1800250e7  mov     ebx, eax
0x1800250e9  test    eax, eax
0x1800250eb  jz      short loc_18002512C
0x1800250ed  mov     edx, 2
0x1800250f2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800250f7  lea     rdi, WPP_GLOBAL_Control
0x1800250fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180025105  cmp     rcx, rdi
0x180025108  jz      loc_180025342
0x18002510e  test    byte ptr [rcx+1Ch], 1
0x180025112  jz      loc_180025342
0x180025118  cmp     byte ptr [rcx+19h], 2
0x18002511c  jb      loc_180025342
0x180025122  mov     edx, 10Ah
0x180025127  jmp     loc_180025327
0x18002512c  cmp     cs:dword_18004C290, 0
0x180025133  jnz     short loc_180025186
0x180025135  lea     rcx, dword_18004C290
0x18002513c  call    RegConfigGetSettings
0x180025141  mov     ebx, eax
0x180025143  test    eax, eax
0x180025145  jz      short loc_180025186
0x180025147  mov     edx, 2
0x18002514c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025151  lea     rdi, WPP_GLOBAL_Control
0x180025158  mov     rcx, cs:WPP_GLOBAL_Control
0x18002515f  cmp     rcx, rdi
0x180025162  jz      loc_180025342
0x180025168  test    byte ptr [rcx+1Ch], 1
0x18002516c  jz      loc_180025342
0x180025172  cmp     byte ptr [rcx+19h], 2
0x180025176  jb      loc_180025342
0x18002517c  mov     edx, 10Bh
0x180025181  jmp     loc_180025327
0x180025186  mov     ecx, cs:dword_18004C29C
0x18002518c  call    TransactionManagerInitialize
0x180025191  mov     ebx, eax
0x180025193  test    eax, eax
0x180025195  jz      short loc_1800251D6
0x180025197  mov     edx, 2
0x18002519c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800251a1  lea     rdi, WPP_GLOBAL_Control
0x1800251a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251af  cmp     rcx, rdi
0x1800251b2  jz      loc_180025342
0x1800251b8  test    byte ptr [rcx+1Ch], 1
0x1800251bc  jz      loc_180025342
0x1800251c2  cmp     byte ptr [rcx+19h], 2
0x1800251c6  jb      loc_180025342
0x1800251cc  mov     edx, 10Ch
0x1800251d1  jmp     loc_180025327
0x1800251d6  mov     ecx, 98h; size
0x1800251db  call    MIDL_user_allocate
0x1800251e0  mov     rdi, rax
0x1800251e3  test    rax, rax
0x1800251e6  jnz     short loc_180025239
0x1800251e8  mov     ebx, 8009000Eh
0x1800251ed  lea     rdi, WPP_GLOBAL_Control
0x1800251f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251fb  cmp     rcx, rdi
0x1800251fe  jz      loc_180025399
0x180025204  test    byte ptr [rcx+1Ch], 1
0x180025208  jz      loc_180025399
0x18002520e  cmp     byte ptr [rcx+19h], 2
0x180025212  jb      loc_180025399
0x180025218  mov     edx, 10Dh
0x18002521d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025224  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18002522b  mov     rcx, [rcx+10h]
0x18002522f  call    WPP_SF_s
0x180025234  jmp     loc_180025399
0x180025239  lea     rcx, [rax+8]; void *
0x18002523d  xor     edx, edx; Val
0x18002523f  mov     r8d, 90h; Size
0x180025245  call    memset_0
0x18002524a  mov     [rdi], r12
0x18002524d  inc     cs:dword_18004C280
0x180025253  lea     rcx, [rdi+10h]
0x180025257  call    CspInitializeCriticalSection
0x18002525c  mov     dword ptr [rdi+38h], 1
0x180025263  cmp     cs:phProvider, 0
0x18002526b  jnz     short loc_1800252C6
0x18002526d  xor     r8d, r8d; dwFlags
0x180025270  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x180025277  lea     rcx, phProvider; phProvider
0x18002527e  call    cs:__imp_NCryptOpenStorageProvider
0x180025284  mov     ebx, eax
0x180025286  test    eax, eax
0x180025288  jz      short loc_1800252C6
0x18002528a  mov     edx, 2
0x18002528f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025294  lea     rdi, WPP_GLOBAL_Control
0x18002529b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800252a2  cmp     rcx, rdi
0x1800252a5  jz      loc_180025342
0x1800252ab  test    byte ptr [rcx+1Ch], 1
0x1800252af  jz      loc_180025342
0x1800252b5  cmp     byte ptr [rcx+19h], 2
0x1800252b9  jb      loc_180025342
0x1800252bf  mov     edx, 10Eh
0x1800252c4  jmp     short loc_180025327
0x1800252c6  cmp     [rbp+var_28], 0
0x1800252cb  jz      short loc_1800252DD
0x1800252cd  mov     [rbp+var_28], 0
0x1800252d5  mov     rcx, r12
0x1800252d8  call    KspLeaveCriticalSection
0x1800252dd  and     esi, 40h
0x1800252e0  mov     [rdi+3Ch], esi
0x1800252e3  mov     r8, r14
0x1800252e6  mov     edx, 3
0x1800252eb  mov     rcx, rdi
0x1800252ee  call    HtAddHandle
0x1800252f3  mov     ebx, eax
0x1800252f5  test    eax, eax
0x1800252f7  jz      short loc_180025342
0x1800252f9  mov     edx, 2
0x1800252fe  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025303  lea     rdi, WPP_GLOBAL_Control
0x18002530a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025311  cmp     rcx, rdi
0x180025314  jz      short loc_180025342
0x180025316  test    byte ptr [rcx+1Ch], 1
0x18002531a  jz      short loc_180025342
0x18002531c  cmp     byte ptr [rcx+19h], 2
0x180025320  jb      short loc_180025342
0x180025322  mov     edx, 10Fh
0x180025327  mov     [rsp+60h+var_40], ebx
0x18002532b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025332  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180025339  mov     rcx, [rcx+10h]
0x18002533d  call    WPP_SF_sd
0x180025342  test    ebx, ebx
0x180025344  jle     short loc_180025399
0x180025346  movzx   ebx, bx
0x180025349  or      ebx, 80070000h
0x18002534f  jmp     short loc_180025399
0x180025351  mov     edx, 2
0x180025356  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002535b  mov     r9d, 80090027h
0x180025361  mov     ebx, r9d
0x180025364  lea     rdi, WPP_GLOBAL_Control
0x18002536b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025372  cmp     rcx, rdi
0x180025375  jz      short loc_180025399
0x180025377  test    byte ptr [rcx+1Ch], 1
0x18002537b  jz      short loc_180025399
0x18002537d  cmp     byte ptr [rcx+19h], 2
0x180025381  jb      short loc_180025399
0x180025383  mov     edx, 104h
0x180025388  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18002538f  mov     rcx, [rcx+10h]
0x180025393  call    WPP_SF_d
0x180025398  nop
0x180025399  mov     [rbp+var_30], r13
0x18002539d  lea     rcx, [rbp+var_30]
0x1800253a1  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x1800253a6  mov     eax, ebx
0x1800253a8  add     rsp, 60h
0x1800253ac  pop     r14
0x1800253ae  pop     r13
0x1800253b0  pop     r12
0x1800253b2  pop     rdi
0x1800253b3  pop     rsi
0x1800253b4  pop     rbx
0x1800253b5  pop     rbp
0x1800253b6  retn
```
