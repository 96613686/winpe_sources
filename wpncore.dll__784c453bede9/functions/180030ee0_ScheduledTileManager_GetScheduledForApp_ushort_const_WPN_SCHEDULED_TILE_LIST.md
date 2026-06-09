# ScheduledTileManager::GetScheduledForApp(ushort const *,_WPN_SCHEDULED_TILE_LIST * *)

- ea: `0x180030ee0`
- end: `0x18003145d`
- name: `?GetScheduledForApp@ScheduledTileManager@@UEAAJPEBGPEAPEAU_WPN_SCHEDULED_TILE_LIST@@@Z`
- size: `1405`
- prototype: `__int64 __fastcall(ScheduledTileManager *__hidden this, const unsigned __int16 *, struct _WPN_SCHEDULED_TILE_LIST **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002e210`
- `0x18002ee38`
- `0x18002fae0`
- `0x180030ee0`
- `0x180031464`
- `0x180032608`
- `0x1800af0a4`
- `0x1800ba574`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031033`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031055`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003142b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031444`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031033`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031055`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003142b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031444`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031041`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031063`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031420`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031439`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031452`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031041`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031063`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031420`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031439`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031452`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003108e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003113f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800313ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800313e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800313f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003108e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003113f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800313ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800313e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800313f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030f35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800310dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030f35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800310dd`

## string_xrefs

- `0x180031105`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18003114e`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x1800311a4`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180031203`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180031275`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x1800312cd`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180031305`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18003133b`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`

## pseudocode

```c
__int64 __fastcall ScheduledTileManager::GetScheduledForApp(
        ScheduledTileManager *this,
        const unsigned __int16 *a2,
        struct _WPN_SCHEDULED_TILE_LIST **a3)
{
  TimerBrokerHelper *v3; // rcx
  unsigned int v4; // r12d
  unsigned __int16 *v5; // r15
  char *v6; // r13
  int PersistenceIdListForApp; // eax
  unsigned int v8; // ebx
  struct _WPN_SCHEDULED_TILE_LIST *v9; // rax
  struct _WPN_SCHEDULED_TILE_LIST *v10; // r14
  __int64 v11; // rsi
  char *v12; // rdi
  int v13; // eax
  int v14; // eax
  char *v15; // rsi
  int v16; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v18; // rax
  struct _WPN_SCHEDULED_TILE_LIST **v19; // rax
  struct _GUID *v20; // rdi
  SIZE_T v22; // rsi
  char *v23; // rax
  unsigned int v24; // r12d
  int v25; // eax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  unsigned __int64 v28; // rsi
  void *v29; // rcx
  void *v30; // rcx
  void *v31; // rcx
  HANDLE v32; // rax
  HANDLE v33; // rax
  HANDLE v34; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-30h] BYREF
  struct _GUID *v36; // [rsp+28h] [rbp-28h] BYREF
  __int64 v37; // [rsp+30h] [rbp-20h]
  struct _GUID v38; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  unsigned int v40; // [rsp+90h] [rbp+40h] BYREF
  struct _WPN_SCHEDULED_TILE_LIST **v41; // [rsp+A0h] [rbp+50h]
  unsigned __int16 *v42; // [rsp+A8h] [rbp+58h] BYREF

  v41 = a3;
  v3 = (TimerBrokerHelper *)*((_QWORD *)this + 15);
  v4 = 0;
  v40 = 0;
  v5 = 0;
  v42 = 0;
  v6 = 0;
  v36 = 0;
  lpMem = 0;
  PersistenceIdListForApp = TimerBrokerHelper::GetPersistenceIdListForApp(v3, a2, &v40, &v36);
  v8 = PersistenceIdListForApp;
  if ( PersistenceIdListForApp >= 0 )
  {
    v9 = (struct _WPN_SCHEDULED_TILE_LIST *)CoTaskMemAlloc(0x10u);
    v10 = v9;
    if ( v9 )
    {
      v11 = v40;
      v12 = 0;
      *(_DWORD *)v9 = 0;
      *((_QWORD *)v9 + 1) = 0;
      if ( (_DWORD)v11 )
      {
        v22 = v11 << 6;
        v23 = (char *)CoTaskMemAlloc(v22);
        v12 = v23;
        if ( v23 )
        {
          memset_0(v23, 0, v22);
          goto LABEL_13;
        }
        v8 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x33B,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
          (const char *)0x8007000ELL,
          (int)lpMem);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            WPP_91456f608371345bae03279a5fee97df_Traceguids,
            2147942414LL);
      }
      else
      {
        while ( 1 )
        {
          if ( v4 >= (unsigned int)v11 )
          {
            v19 = v41;
            *(_DWORD *)v10 = v11;
            *((_QWORD *)v10 + 1) = v12;
            *v19 = v10;
            goto LABEL_16;
          }
          v37 = v4;
          v38 = v36[v4];
          v13 = ScheduledTileManager::UnpackPersistedEvent(
                  &v38,
                  0,
                  (struct ScheduledTileManager::_PERSISTED_TILE **)&lpMem,
                  0);
          v6 = (char *)lpMem;
          v8 = v13;
          if ( v13 < 0 )
            break;
          v14 = WpnUtf8ToUtf16((LPCCH)lpMem + 654, &v42);
          v8 = v14;
          if ( v14 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x34D,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
              (const char *)(unsigned int)v14,
              (int)lpMem);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_91456f608371345bae03279a5fee97df_Traceguids, v8);
            v5 = v42;
            goto LABEL_26;
          }
          v5 = v42;
          v15 = &v12[64 * v37];
          v16 = WpnCoTaskStrCpy(v42, (unsigned __int16 **)v15);
          v8 = v16;
          if ( v16 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x350,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
              (const char *)(unsigned int)v16,
              (int)lpMem);
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
              goto LABEL_42;
            v27 = 41;
LABEL_41:
            WPP_SF_d(v26[2], v27, WPP_91456f608371345bae03279a5fee97df_Traceguids, v8);
            goto LABEL_42;
          }
          v8 = WpnCoTaskStrCpy((const unsigned __int16 *)v6 + 310, (unsigned __int16 **)v15 + 1);
          if ( (v8 & 0x80000000) != 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x353,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
              (const char *)v8,
              (int)lpMem);
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
              goto LABEL_42;
            v27 = 42;
            goto LABEL_41;
          }
          if ( *((_WORD *)v6 + 2887) )
          {
            v25 = WpnCoTaskStrCpy((const unsigned __int16 *)v6 + 2887, (unsigned __int16 **)v15 + 2);
            v8 = v25;
            if ( v25 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x357,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
                (const char *)(unsigned int)v25,
                (int)lpMem);
              v26 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                v27 = 43;
                goto LABEL_41;
              }
LABEL_42:
              LODWORD(v11) = v40;
              goto LABEL_26;
            }
          }
          *((_QWORD *)v15 + 3) = *((_QWORD *)v6 + 75);
          *((_QWORD *)v15 + 4) = *((_QWORD *)v6 + 76);
          *((_DWORD *)v15 + 10) = *((_DWORD *)v6 + 154);
          *(_OWORD *)(v15 + 44) = *(_OWORD *)(v6 + 4);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v6);
          lpMem = 0;
          v6 = 0;
          if ( v5 )
          {
            v18 = GetProcessHeap();
            HeapFree(v18, 0, v5);
            v5 = 0;
            v42 = 0;
          }
          ++v4;
LABEL_13:
          LODWORD(v11) = v40;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x34A,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
          (const char *)(unsigned int)v13,
          (int)lpMem);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_91456f608371345bae03279a5fee97df_Traceguids, v8);
LABEL_26:
        v24 = 0;
        if ( v12 )
        {
          if ( (_DWORD)v11 )
          {
            do
            {
              v28 = (unsigned __int64)v24 << 6;
              v29 = *(void **)&v12[v28];
              if ( v29 )
              {
                CoTaskMemFree(v29);
                *(_QWORD *)&v12[v28] = 0;
              }
              v30 = *(void **)&v12[v28 + 8];
              if ( v30 )
              {
                CoTaskMemFree(v30);
                *(_QWORD *)&v12[v28 + 8] = 0;
              }
              v31 = *(void **)&v12[v28 + 16];
              if ( v31 )
              {
                CoTaskMemFree(v31);
                *(_QWORD *)&v12[v28 + 16] = 0;
              }
              ++v24;
            }
            while ( v24 < v40 );
          }
          CoTaskMemFree(v12);
          if ( !v10 )
            goto LABEL_16;
        }
      }
      CoTaskMemFree(v10);
    }
    else
    {
      v8 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x32F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
        (const char *)0x8007000ELL,
        (int)lpMem);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_91456f608371345bae03279a5fee97df_Traceguids, 2147942414LL);
    }
LABEL_16:
    if ( v6 )
    {
      v32 = GetProcessHeap();
      HeapFree(v32, 0, v6);
    }
    if ( v5 )
    {
      v33 = GetProcessHeap();
      HeapFree(v33, 0, v5);
    }
    goto LABEL_20;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x325,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
    (const char *)(unsigned int)PersistenceIdListForApp,
    (int)lpMem);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_91456f608371345bae03279a5fee97df_Traceguids, v8);
LABEL_20:
  v20 = v36;
  if ( v36 )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v20);
  }
  return v8;
}

```

## disassembly

```asm
0x180030ee0  mov     [rsp-38h+arg_8], rbx
0x180030ee5  mov     [rsp-38h+arg_10], r8
0x180030eea  push    rbp
0x180030eeb  push    rsi
0x180030eec  push    rdi
0x180030eed  push    r12
0x180030eef  push    r13
0x180030ef1  push    r14
0x180030ef3  push    r15
0x180030ef5  mov     rbp, rsp
0x180030ef8  sub     rsp, 50h
0x180030efc  mov     rcx, [rcx+78h]; this
0x180030f00  lea     r9, [rbp+var_28]; struct _GUID **
0x180030f04  xor     r12d, r12d
0x180030f07  lea     r8, [rbp+arg_0]; unsigned int *
0x180030f0b  mov     [rbp+arg_0], r12d
0x180030f0f  mov     r15d, r12d
0x180030f12  mov     [rbp+arg_18], r12
0x180030f16  mov     r13d, r12d
0x180030f19  mov     [rbp+var_28], r12
0x180030f1d  mov     [rbp+lpMem], r12
0x180030f21  call    ?GetPersistenceIdListForApp@TimerBrokerHelper@@QEAAJPEBGPEAIPEAPEAU_GUID@@@Z; TimerBrokerHelper::GetPersistenceIdListForApp(ushort const *,uint *,_GUID * *)
0x180030f26  mov     ebx, eax
0x180030f28  test    eax, eax
0x180030f2a  js      loc_18003114A
0x180030f30  lea     ecx, [r12+10h]; cb
0x180030f35  call    cs:__imp_CoTaskMemAlloc
0x180030f3b  mov     r14, rax
0x180030f3e  test    rax, rax
0x180030f41  jz      loc_1800311A0
0x180030f47  mov     esi, [rbp+arg_0]
0x180030f4a  mov     edi, r12d
0x180030f4d  mov     [rax], r12d
0x180030f50  mov     [rax+8], r12
0x180030f54  test    esi, esi
0x180030f56  jnz     loc_1800310D6
0x180030f5c  cmp     r12d, esi
0x180030f5f  jnb     loc_18003107B
0x180030f65  mov     rcx, [rbp+var_28]
0x180030f69  lea     r8, [rbp+lpMem]; struct ScheduledTileManager::_PERSISTED_TILE **
0x180030f6d  mov     eax, r12d
0x180030f70  xor     r9d, r9d; int *
0x180030f73  mov     [rbp+var_20], rax
0x180030f77  xor     edx, edx; void *
0x180030f79  add     rax, rax
0x180030f7c  movups  xmm0, xmmword ptr [rcx+rax*8]
0x180030f80  lea     rcx, [rbp+var_10]; struct _GUID
0x180030f84  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x180030f89  call    ?UnpackPersistedEvent@ScheduledTileManager@@CAJU_GUID@@PEAXPEAPEAU_PERSISTED_TILE@1@PEAH@Z; ScheduledTileManager::UnpackPersistedEvent(_GUID,void *,ScheduledTileManager::_PERSISTED_TILE * *,int *)
0x180030f8e  mov     r13, [rbp+lpMem]
0x180030f92  mov     ebx, eax
0x180030f94  test    eax, eax
0x180030f96  js      loc_180031101
0x180030f9c  lea     rcx, [r13+28Eh]; lpMultiByteStr
0x180030fa3  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x180030fa7  call    ?WpnUtf8ToUtf16@@YAJPEBDPEAPEAG@Z; WpnUtf8ToUtf16(char const *,ushort * *)
0x180030fac  mov     ebx, eax
0x180030fae  test    eax, eax
0x180030fb0  js      loc_180031337
0x180030fb6  mov     rsi, [rbp+var_20]
0x180030fba  mov     r15, [rbp+arg_18]
0x180030fbe  shl     rsi, 6
0x180030fc2  mov     rcx, r15; unsigned __int16 *
0x180030fc5  add     rsi, rdi
0x180030fc8  mov     rdx, rsi; unsigned __int16 **
0x180030fcb  call    ?WpnCoTaskStrCpy@@YAJPEBGPEAPEAG@Z; WpnCoTaskStrCpy(ushort const *,ushort * *)
0x180030fd0  mov     ebx, eax
0x180030fd2  test    eax, eax
0x180030fd4  js      loc_180031301
0x180030fda  lea     rdx, [rsi+8]; unsigned __int16 **
0x180030fde  lea     rcx, [r13+26Ch]; unsigned __int16 *
0x180030fe5  call    ?WpnCoTaskStrCpy@@YAJPEBGPEAPEAG@Z; WpnCoTaskStrCpy(ushort const *,ushort * *)
0x180030fea  mov     ebx, eax
0x180030fec  xor     eax, eax
0x180030fee  test    ebx, ebx
0x180030ff0  js      loc_1800312C9
0x180030ff6  lea     rcx, [r13+168Eh]; unsigned __int16 *
0x180030ffd  cmp     [rcx], ax
0x180031000  jnz     loc_18003125E
0x180031006  mov     rax, [r13+258h]
0x18003100d  mov     [rsi+18h], rax
0x180031011  movsd   xmm0, qword ptr [r13+260h]
0x18003101a  movsd   qword ptr [rsi+20h], xmm0
0x18003101f  mov     eax, [r13+268h]
0x180031026  mov     [rsi+28h], eax
0x180031029  movups  xmm0, xmmword ptr [r13+4]
0x18003102e  movdqu  xmmword ptr [rsi+2Ch], xmm0
0x180031033  call    cs:__imp_GetProcessHeap
0x180031039  mov     r8, r13; lpMem
0x18003103c  xor     edx, edx; dwFlags
0x18003103e  mov     rcx, rax; hHeap
0x180031041  call    cs:__imp_HeapFree
0x180031047  xor     esi, esi
0x180031049  mov     [rbp+lpMem], rsi
0x18003104d  mov     r13d, esi
0x180031050  test    r15, r15
0x180031053  jz      short loc_180031070
0x180031055  call    cs:__imp_GetProcessHeap
0x18003105b  mov     r8, r15; lpMem
0x18003105e  xor     edx, edx; dwFlags
0x180031060  mov     rcx, rax; hHeap
0x180031063  call    cs:__imp_HeapFree
0x180031069  mov     r15d, esi
0x18003106c  mov     [rbp+arg_18], rsi
0x180031070  inc     r12d
0x180031073  mov     esi, [rbp+arg_0]
0x180031076  jmp     loc_180030F5C
0x18003107b  mov     rax, [rbp+arg_10]
0x18003107f  mov     [r14], esi
0x180031082  mov     [r14+8], rdi
0x180031086  mov     [rax], r14
0x180031089  jmp     short loc_18003109D
0x18003108b  mov     rcx, rdi; pv
0x18003108e  call    cs:__imp_CoTaskMemFree
0x180031094  test    r14, r14
0x180031097  jnz     loc_18003113C
0x18003109d  test    r13, r13
0x1800310a0  jnz     loc_180031412
0x1800310a6  test    r15, r15
0x1800310a9  jnz     loc_18003142B
0x1800310af  mov     rdi, [rbp+var_28]
0x1800310b3  test    rdi, rdi
0x1800310b6  jnz     loc_180031444
0x1800310bc  mov     eax, ebx
0x1800310be  mov     rbx, [rsp+50h+arg_8]
0x1800310c6  add     rsp, 50h
0x1800310ca  pop     r15
0x1800310cc  pop     r14
0x1800310ce  pop     r13
0x1800310d0  pop     r12
0x1800310d2  pop     rdi
0x1800310d3  pop     rsi
0x1800310d4  pop     rbp
0x1800310d5  retn
0x1800310d6  shl     rsi, 6
0x1800310da  mov     rcx, rsi; cb
0x1800310dd  call    cs:__imp_CoTaskMemAlloc
0x1800310e3  mov     rdi, rax
0x1800310e6  test    rax, rax
0x1800310e9  jz      loc_1800311FF
0x1800310ef  mov     r8, rsi; Size
0x1800310f2  xor     edx, edx; Val
0x1800310f4  mov     rcx, rax; void *
0x1800310f7  call    memset_0
0x1800310fc  jmp     loc_180031073
0x180031101  mov     rcx, [rbp+38h]; this
0x180031105  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003110c  mov     r9d, ebx; char *
0x18003110f  mov     edx, 34Ah; void *
0x180031114  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031119  mov     rcx, cs:WPP_GLOBAL_Control
0x180031120  lea     rax, WPP_GLOBAL_Control
0x180031127  cmp     rcx, rax
0x18003112a  jnz     loc_180031389
0x180031130  xor     r12d, r12d
0x180031133  test    rdi, rdi
0x180031136  jnz     loc_1800313B0
0x18003113c  mov     rcx, r14; pv
0x18003113f  call    cs:__imp_CoTaskMemFree
0x180031145  jmp     loc_18003109D
0x18003114a  mov     rcx, [rbp+38h]; this
0x18003114e  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180031155  mov     r9d, ebx; char *
0x180031158  mov     edx, 325h; void *
0x18003115d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031162  mov     rcx, cs:WPP_GLOBAL_Control
0x180031169  lea     rax, WPP_GLOBAL_Control
0x180031170  cmp     rcx, rax
0x180031173  jz      loc_1800310AF
0x180031179  test    byte ptr [rcx+1Ch], 80h
0x18003117d  jz      loc_1800310AF
0x180031183  mov     rcx, [rcx+10h]
0x180031187  lea     r8, WPP_91456f608371345bae03279a5fee97df_Traceguids
0x18003118e  mov     edx, 24h ; '$'
0x180031193  mov     r9d, ebx
0x180031196  call    WPP_SF_d
0x18003119b  jmp     loc_1800310AF
0x1800311a0  mov     rcx, [rbp+38h]; this
0x1800311a4  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800311ab  mov     r9d, 8007000Eh; char *
0x1800311b1  mov     edx, 32Fh; void *
0x1800311b6  mov     ebx, r9d
0x1800311b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800311be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800311c5  lea     rax, WPP_GLOBAL_Control
0x1800311cc  cmp     rcx, rax
0x1800311cf  jz      loc_18003109D
0x1800311d5  test    byte ptr [rcx+1Ch], 80h
0x1800311d9  jz      loc_18003109D
0x1800311df  mov     rcx, [rcx+10h]
0x1800311e3  lea     r8, WPP_91456f608371345bae03279a5fee97df_Traceguids
0x1800311ea  mov     edx, 25h ; '%'
0x1800311ef  mov     r9d, 8007000Eh
0x1800311f5  call    WPP_SF_d
0x1800311fa  jmp     loc_18003109D
0x1800311ff  mov     rcx, [rbp+38h]; this
0x180031203  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003120a  mov     r9d, 8007000Eh; char *
0x180031210  mov     edx, 33Bh; void *
0x180031215  mov     ebx, r9d
0x180031218  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003121d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031224  lea     rax, WPP_GLOBAL_Control
0x18003122b  cmp     rcx, rax
0x18003122e  jz      loc_18003113C
0x180031234  test    byte ptr [rcx+1Ch], 80h
0x180031238  jz      loc_18003113C
0x18003123e  mov     rcx, [rcx+10h]
0x180031242  lea     r8, WPP_91456f608371345bae03279a5fee97df_Traceguids
0x180031249  mov     edx, 26h ; '&'
0x18003124e  mov     r9d, 8007000Eh
0x180031254  call    WPP_SF_d
0x180031259  jmp     loc_18003113C
0x18003125e  lea     rdx, [rsi+10h]; unsigned __int16 **
0x180031262  call    ?WpnCoTaskStrCpy@@YAJPEBGPEAPEAG@Z; WpnCoTaskStrCpy(ushort const *,ushort * *)
0x180031267  mov     ebx, eax
0x180031269  test    eax, eax
0x18003126b  jns     loc_180031006
0x180031271  mov     rcx, [rbp+38h]; this
0x180031275  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003127c  mov     r9d, eax; char *
0x18003127f  mov     edx, 357h; void *
0x180031284  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031289  mov     rcx, cs:WPP_GLOBAL_Control
0x180031290  lea     rax, WPP_GLOBAL_Control
0x180031297  cmp     rcx, rax
0x18003129a  jz      short loc_1800312C1
0x18003129c  test    byte ptr [rcx+1Ch], 80h
0x1800312a0  jz      short loc_1800312C1
0x1800312a2  mov     edx, 2Bh ; '+'
0x1800312a7  jmp     short loc_1800312AE
0x1800312a9  mov     edx, 29h ; ')'
0x1800312ae  mov     rcx, [rcx+10h]
0x1800312b2  lea     r8, WPP_91456f608371345bae03279a5fee97df_Traceguids
0x1800312b9  mov     r9d, ebx
0x1800312bc  call    WPP_SF_d
0x1800312c1  mov     esi, [rbp+arg_0]
0x1800312c4  jmp     loc_180031130
0x1800312c9  mov     rcx, [rbp+38h]; this
0x1800312cd  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800312d4  mov     r9d, ebx; char *
0x1800312d7  mov     edx, 353h; void *
0x1800312dc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800312e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800312e8  lea     rax, WPP_GLOBAL_Control
0x1800312ef  cmp     rcx, rax
0x1800312f2  jz      short loc_1800312C1
0x1800312f4  test    byte ptr [rcx+1Ch], 80h
0x1800312f8  jz      short loc_1800312C1
0x1800312fa  mov     edx, 2Ah ; '*'
0x1800312ff  jmp     short loc_1800312AE
0x180031301  mov     rcx, [rbp+38h]; this
0x180031305  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003130c  mov     r9d, ebx; char *
0x18003130f  mov     edx, 350h; void *
0x180031314  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031319  mov     rcx, cs:WPP_GLOBAL_Control
0x180031320  lea     rax, WPP_GLOBAL_Control
0x180031327  cmp     rcx, rax
0x18003132a  jz      short loc_1800312C1
0x18003132c  test    byte ptr [rcx+1Ch], 80h
0x180031330  jz      short loc_1800312C1
0x180031332  jmp     loc_1800312A9
0x180031337  mov     rcx, [rbp+38h]; this
0x18003133b  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180031342  mov     r9d, ebx; char *
0x180031345  mov     edx, 34Dh; void *
0x18003134a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003134f  mov     rcx, cs:WPP_GLOBAL_Control
0x180031356  lea     rax, WPP_GLOBAL_Control
0x18003135d  cmp     rcx, rax
0x180031360  jz      short loc_180031380
0x180031362  test    byte ptr [rcx+1Ch], 80h
0x180031366  jz      short loc_180031380
0x180031368  mov     rcx, [rcx+10h]
0x18003136c  lea     r8, WPP_91456f608371345bae03279a5fee97df_Traceguids
0x180031373  mov     edx, 28h ; '('
0x180031378  mov     r9d, ebx
0x18003137b  call    WPP_SF_d
0x180031380  mov     r15, [rbp+arg_18]
0x180031384  jmp     loc_180031130
0x180031389  test    byte ptr [rcx+1Ch], 80h
0x18003138d  jz      loc_180031130
0x180031393  mov     rcx, [rcx+10h]
0x180031397  lea     r8, WPP_91456f608371345bae03279a5fee97df_Traceguids
0x18003139e  mov     edx, 27h ; '''
0x1800313a3  mov     r9d, ebx
0x1800313a6  call    WPP_SF_d
0x1800313ab  jmp     loc_180031130
0x1800313b0  xor     eax, eax
0x1800313b2  test    esi, esi
0x1800313b4  jz      loc_18003108B
0x1800313ba  mov     esi, r12d
0x1800313bd  shl     rsi, 6
0x1800313c1  mov     rcx, [rsi+rdi]; pv
0x1800313c5  test    rcx, rcx
0x1800313c8  jz      short loc_1800313D6
0x1800313ca  call    cs:__imp_CoTaskMemFree
0x1800313d0  xor     eax, eax
0x1800313d2  mov     [rsi+rdi], rax
  ... truncated ...
```
