# ProgressUIThreadProc(void *)

- ea: `0x180020ce0`
- end: `0x18002147b`
- name: `?ProgressUIThreadProc@@YAKPEAX@Z`
- size: `1947`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180020ce0`
- `0x1800285c8`
- `0x18002dfa8`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18005422c`
- `0x1800543a8`
- `0x180054850`
- `0x18006e4e4`
- `0x180078010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180020d3c`
- `KERNEL32!InitializeCriticalSection` at `0x180020d3c`
- `KERNEL32!DeleteCriticalSection` at `0x180021447`
- `KERNEL32!DeleteCriticalSection` at `0x180021447`
- `KERNEL32!EnterCriticalSection` at `0x180020efd`
- `KERNEL32!EnterCriticalSection` at `0x180020f39`
- `KERNEL32!EnterCriticalSection` at `0x180021014`
- `KERNEL32!EnterCriticalSection` at `0x18002107a`
- `KERNEL32!EnterCriticalSection` at `0x180021162`
- `KERNEL32!EnterCriticalSection` at `0x18002122f`
- `KERNEL32!EnterCriticalSection` at `0x180021263`
- `KERNEL32!EnterCriticalSection` at `0x1800212a1`
- `KERNEL32!EnterCriticalSection` at `0x18002134a`
- `KERNEL32!EnterCriticalSection` at `0x1800213de`
- `KERNEL32!EnterCriticalSection` at `0x180020efd`
- `KERNEL32!EnterCriticalSection` at `0x180020f39`
- `KERNEL32!EnterCriticalSection` at `0x180021014`
- `KERNEL32!EnterCriticalSection` at `0x18002107a`
- `KERNEL32!EnterCriticalSection` at `0x180021162`
- `KERNEL32!EnterCriticalSection` at `0x18002122f`
- `KERNEL32!EnterCriticalSection` at `0x180021263`
- `KERNEL32!EnterCriticalSection` at `0x1800212a1`
- `KERNEL32!EnterCriticalSection` at `0x18002134a`
- `KERNEL32!EnterCriticalSection` at `0x1800213de`
- `KERNEL32!LeaveCriticalSection` at `0x180021152`
- `KERNEL32!LeaveCriticalSection` at `0x180021331`
- `KERNEL32!LeaveCriticalSection` at `0x1800213b9`
- `KERNEL32!LeaveCriticalSection` at `0x180021418`
- `KERNEL32!LeaveCriticalSection` at `0x180021152`
- `KERNEL32!LeaveCriticalSection` at `0x180021331`
- `KERNEL32!LeaveCriticalSection` at `0x1800213b9`
- `KERNEL32!LeaveCriticalSection` at `0x180021418`
- `KERNEL32!SetEvent` at `0x180020ea8`
- `KERNEL32!SetEvent` at `0x1800212c9`
- `KERNEL32!SetEvent` at `0x180020ea8`
- `KERNEL32!SetEvent` at `0x1800212c9`
- `KERNEL32!CreateTimerQueueTimer` at `0x180020db5`
- `KERNEL32!CreateTimerQueueTimer` at `0x180020db5`
- `KERNEL32!WaitForMultipleObjects` at `0x180020ebd`
- `KERNEL32!WaitForMultipleObjects` at `0x180020ebd`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180021433`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180021433`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18002113c`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18002113c`
- `USER32!LoadStringW` at `0x1800210df`
- `USER32!LoadStringW` at `0x1800210df`
- `ole32!CoUninitialize` at `0x18002141e`
- `ole32!CoUninitialize` at `0x18002141e`
- `ole32!CoCreateInstance` at `0x180021376`
- `ole32!CoCreateInstance` at `0x180021376`
- `ole32!CoInitializeEx` at `0x180020d49`
- `ole32!CoInitializeEx` at `0x180020d49`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ProgressUIThreadProc(char *lpThreadParameter)
{
  HRESULT v2; // eax
  struct IUnknown *v3; // rcx
  int Progress; // eax
  int v5; // r15d
  int v6; // r14d
  DWORD v7; // eax
  DWORD v8; // edi
  int v9; // eax
  char *v10; // r8
  int v11; // eax
  char *v12; // r8
  DWORD v13; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  int v16; // eax
  int v17; // eax
  IUnknown *punk; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE phNewTimer; // [rsp+50h] [rbp-B0h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v23[2]; // [rsp+80h] [rbp-80h] BYREF
  HANDLE Handles[10]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer; // [rsp+E0h] [rbp-20h] BYREF
  char v26[526]; // [rsp+E2h] [rbp-1Eh] BYREF

  punk = 0;
  phNewTimer = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  InitializeCriticalSection(&CriticalSection);
  v2 = CoInitializeEx(0, 4u);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        112,
        &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids,
        (unsigned int)v2);
    goto LABEL_80;
  }
  if ( !CreateTimerQueueTimer(
          &phNewTimer,
          0,
          (WAITORTIMERCALLBACK)_TimerCallback,
          *((PVOID *)lpThreadParameter + 11),
          0x3E8u,
          0x3E8u,
          0) )
    goto LABEL_79;
  if ( !phNewTimer )
  {
    v3 = (struct IUnknown *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, "hTimer");
  }
  Progress = _CreateProgress(v3, (struct IActionProgress **)&punk);
  if ( Progress < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        114,
        &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids,
        (unsigned int)Progress);
    goto LABEL_79;
  }
  v5 = 0;
  v6 = 0;
  Handles[0] = *((HANDLE *)lpThreadParameter + 4);
  Handles[1] = *((HANDLE *)lpThreadParameter + 3);
  Handles[2] = *((HANDLE *)lpThreadParameter + 5);
  Handles[3] = *((HANDLE *)lpThreadParameter + 6);
  Handles[4] = *((HANDLE *)lpThreadParameter + 9);
  Handles[5] = *((HANDLE *)lpThreadParameter + 10);
  Handles[6] = *((HANDLE *)lpThreadParameter + 11);
  Handles[7] = *((HANDLE *)lpThreadParameter + 12);
  Handles[8] = *((HANDLE *)lpThreadParameter + 7);
  Handles[9] = *((HANDLE *)lpThreadParameter + 8);
  *((_DWORD *)lpThreadParameter + 28) = 1;
  SetEvent(*((HANDLE *)lpThreadParameter + 2));
  while ( 1 )
  {
    while ( 1 )
    {
      v7 = WaitForMultipleObjects(0xAu, Handles, 0, 0xFFFFFFFF);
      v8 = v7;
      if ( v7 == 5 )
      {
        EnterCriticalSection(&CriticalSection);
        if ( punk )
        {
          ppv = 0;
          v11 = ((__int64 (__fastcall *)(IUnknown *, GUID *, LPVOID *))punk->lpVtbl->QueryInterface)(
                  punk,
                  &GUID_ebbc7c04_315e_11d2_b62f_006097df5bd4,
                  &ppv);
          v12 = lpThreadParameter + 172;
          if ( v11 < 0 )
          {
            ((void (__fastcall *)(IUnknown *, __int64, char *, __int64))punk->lpVtbl[1].Release)(punk, 2, v12, 1);
          }
          else
          {
            (*(void (__fastcall **)(LPVOID, __int64, char *, __int64, _QWORD))(*(_QWORD *)ppv + 80LL))(
              ppv,
              1,
              v12,
              1,
              0);
            (*(void (__fastcall **)(LPVOID, __int64, char *, __int64, _QWORD))(*(_QWORD *)ppv + 80LL))(
              ppv,
              2,
              lpThreadParameter + 692,
              1,
              0);
          }
          if ( ppv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        goto LABEL_36;
      }
      if ( v7 <= 5 )
        break;
      v13 = v7 - 6;
      if ( v13 && (v14 = v13 - 1) != 0 )
      {
        v15 = v14 - 1;
        if ( !v15 )
        {
          EnterCriticalSection(&CriticalSection);
          if ( punk && !v6 )
          {
            if ( v5 )
              _PauseTimer((struct IActionProgress *)punk);
            v6 = 1;
          }
          goto LABEL_36;
        }
        if ( v15 == 1 )
        {
          EnterCriticalSection(&CriticalSection);
          if ( punk && v6 )
          {
            if ( v5 )
              _ResumeTimer((struct IActionProgress *)punk);
            v6 = 0;
          }
          goto LABEL_36;
        }
      }
      else if ( *((_DWORD *)lpThreadParameter + 26) != 1 )
      {
        EnterCriticalSection(&CriticalSection);
        if ( v8 == 6 )
        {
          v16 = *((_DWORD *)lpThreadParameter + 32);
          if ( v16 )
          {
            v17 = v16 - 1;
            *((_DWORD *)lpThreadParameter + 32) = v17;
            if ( !v17 )
              SetEvent(*((HANDLE *)lpThreadParameter + 3));
            goto LABEL_36;
          }
          LODWORD(ppv) = 0;
          if ( !punk
            || ((int (__fastcall *)(IUnknown *, LPVOID *))punk->lpVtbl[2].QueryInterface)(punk, &ppv) < 0
            || !(_DWORD)ppv )
          {
            goto LABEL_36;
          }
        }
        *((_DWORD *)lpThreadParameter + 26) = 1;
        if ( punk )
        {
          *((_QWORD *)lpThreadParameter + 15) = 0;
          _EndAndReleaseProgress((struct IActionProgress **)&punk, 1);
          punk = 0;
        }
        LeaveCriticalSection(&CriticalSection);
        v23[0] = 0;
        ppv = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)(lpThreadParameter + 2776));
        if ( *((_DWORD *)lpThreadParameter + 704)
          && CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0
          && (*(int (__fastcall **)(LPVOID, _QWORD, GUID *, _QWORD *))(*(_QWORD *)ppv + 40LL))(
               ppv,
               *((unsigned int *)lpThreadParameter + 704),
               &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c,
               v23) >= 0 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 56LL))(v23[0]);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(lpThreadParameter + 2776));
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v23);
      }
    }
    if ( !v7 )
      break;
    switch ( v7 )
    {
      case 1u:
        EnterCriticalSection(&CriticalSection);
        if ( !punk )
          break;
        ppv = 0;
        if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, LPVOID *))punk->lpVtbl->QueryInterface)(
               punk,
               &GUID_49ff1172_eadc_446d_9285_156453a6431c,
               &ppv) >= 0 )
        {
          Buffer = 0;
          memset_0(v26, 0, 0x206u);
          LoadStringW(g_hInst, *((_DWORD *)lpThreadParameter + 34), &Buffer, 260);
          if ( (*(int (__fastcall **)(LPVOID, __int64, WCHAR *, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 1, &Buffer, 0) >= 0 )
          {
            ((void (__fastcall *)(IUnknown *, _QWORD, __int64))punk->lpVtbl[1].QueryInterface)(
              punk,
              *((unsigned int *)lpThreadParameter + 33),
              2);
            v5 = 1;
            if ( v6 )
              _PauseTimer((struct IActionProgress *)punk);
            IUnknown_GetWindow(punk, (HWND *)lpThreadParameter + 15);
          }
        }
        goto LABEL_35;
      case 2u:
        *((_DWORD *)lpThreadParameter + 27) = 1;
        EnterCriticalSection(&CriticalSection);
        if ( punk )
        {
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl[2].Release)(punk);
          ((void (__fastcall *)(IUnknown *, _QWORD, __int64))punk->lpVtbl[1].QueryInterface)(
            punk,
            *((unsigned int *)lpThreadParameter + 33),
            32);
          ((void (__fastcall *)(IUnknown *, __int64, char *))punk->lpVtbl[1].Release)(punk, 2, lpThreadParameter + 2252);
        }
        break;
      case 3u:
        *((_DWORD *)lpThreadParameter + 27) = 0;
        EnterCriticalSection(&CriticalSection);
        if ( !punk )
          break;
        ppv = 0;
        ((void (__fastcall *)(IUnknown *))punk->lpVtbl[2].Release)(punk);
        ((void (__fastcall *)(IUnknown *, _QWORD, __int64))punk->lpVtbl[1].QueryInterface)(
          punk,
          *((unsigned int *)lpThreadParameter + 33),
          2);
        v9 = ((__int64 (__fastcall *)(IUnknown *, GUID *, LPVOID *))punk->lpVtbl->QueryInterface)(
               punk,
               &GUID_ebbc7c04_315e_11d2_b62f_006097df5bd4,
               &ppv);
        v10 = lpThreadParameter + 172;
        if ( v9 < 0 )
        {
          ((void (__fastcall *)(IUnknown *, __int64, char *, __int64))punk->lpVtbl[1].Release)(punk, 2, v10, 1);
        }
        else
        {
          (*(void (__fastcall **)(LPVOID, __int64, char *, __int64, _QWORD))(*(_QWORD *)ppv + 80LL))(ppv, 1, v10, 1, 0);
          (*(void (__fastcall **)(LPVOID, __int64, char *, __int64, _QWORD))(*(_QWORD *)ppv + 80LL))(
            ppv,
            2,
            lpThreadParameter + 692,
            1,
            0);
        }
LABEL_35:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
        break;
      default:
        EnterCriticalSection(&CriticalSection);
        if ( punk )
          ((void (__fastcall *)(IUnknown *, _QWORD, _QWORD))punk->lpVtbl[1].AddRef)(
            punk,
            *((_QWORD *)lpThreadParameter + 19),
            *((_QWORD *)lpThreadParameter + 18));
        break;
    }
LABEL_36:
    LeaveCriticalSection(&CriticalSection);
  }
  EnterCriticalSection(&CriticalSection);
  if ( punk )
  {
    if ( v5 && v6 )
      _ResumeTimer((struct IActionProgress *)punk);
    *((_QWORD *)lpThreadParameter + 15) = 0;
    _EndAndReleaseProgress((struct IActionProgress **)&punk, v5);
    punk = 0;
  }
  LeaveCriticalSection(&CriticalSection);
LABEL_79:
  CoUninitialize();
LABEL_80:
  if ( phNewTimer )
  {
    DeleteTimerQueueTimer(0, phNewTimer, 0);
    phNewTimer = 0;
  }
  *((_DWORD *)lpThreadParameter + 28) = 0;
  DeleteCriticalSection(&CriticalSection);
  return 0;
}

```

## disassembly

```asm
0x180020ce0  mov     [rsp-8+arg_8], rbx
0x180020ce5  mov     [rsp-8+arg_10], rdi
0x180020cea  push    rbp
0x180020ceb  push    r12
0x180020ced  push    r13
0x180020cef  push    r14
0x180020cf1  push    r15
0x180020cf3  lea     rbp, [rsp-200h]
0x180020cfb  sub     rsp, 300h
0x180020d02  mov     rax, cs:__security_cookie
0x180020d09  xor     rax, rsp
0x180020d0c  mov     [rbp+220h+var_30], rax
0x180020d13  mov     rbx, rcx
0x180020d16  xor     r12d, r12d
0x180020d19  mov     [rsp+320h+punk], r12
0x180020d1e  mov     [rsp+320h+phNewTimer], r12
0x180020d23  xorps   xmm0, xmm0
0x180020d26  xor     eax, eax
0x180020d28  movups  xmmword ptr [rsp+320h+CriticalSection.DebugInfo], xmm0
0x180020d2d  movups  xmmword ptr [rsp+320h+CriticalSection.OwningThread], xmm0
0x180020d32  mov     [rsp+320h+CriticalSection.SpinCount], rax
0x180020d37  lea     rcx, [rsp+320h+CriticalSection]; lpCriticalSection
0x180020d3c  call    cs:__imp_InitializeCriticalSection
0x180020d42  lea     edx, [r12+4]; dwCoInit
0x180020d47  xor     ecx, ecx; pvReserved
0x180020d49  call    cs:__imp_CoInitializeEx
0x180020d4f  test    eax, eax
0x180020d51  jns     short loc_180020D91
0x180020d53  lea     rdi, WPP_GLOBAL_Control
0x180020d5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d61  cmp     rcx, rdi
0x180020d64  jz      loc_180021424
0x180020d6a  test    byte ptr [rcx+1Ch], 2
0x180020d6e  jz      loc_180021424
0x180020d74  lea     edx, [r12+70h]
0x180020d79  mov     r9d, eax
0x180020d7c  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180020d83  mov     rcx, [rcx+10h]
0x180020d87  call    WPP_SF_d
0x180020d8c  jmp     loc_180021424
0x180020d91  mov     [rsp+320h+Flags], r12d; Flags
0x180020d96  mov     eax, 3E8h
0x180020d9b  mov     [rsp+320h+Period], eax; Period
0x180020d9f  mov     [rsp+320h+DueTime], eax; DueTime
0x180020da3  mov     r9, [rbx+58h]; Parameter
0x180020da7  lea     r8, ?_TimerCallback@@YAXPEAXE@Z; Callback
0x180020dae  xor     edx, edx; TimerQueue
0x180020db0  lea     rcx, [rsp+320h+phNewTimer]; phNewTimer
0x180020db5  call    cs:__imp_CreateTimerQueueTimer
0x180020dbb  test    eax, eax
0x180020dbd  jz      loc_18002141E
0x180020dc3  lea     rdi, WPP_GLOBAL_Control
0x180020dca  cmp     [rsp+320h+phNewTimer], r12
0x180020dcf  jnz     short loc_180020DFF
0x180020dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180020dd8  cmp     rcx, rdi
0x180020ddb  jz      short loc_180020DFF
0x180020ddd  test    byte ptr [rcx+1Ch], 8
0x180020de1  jz      short loc_180020DFF
0x180020de3  mov     edx, 71h ; 'q'
0x180020de8  lea     r9, aHtimer; "hTimer"
0x180020def  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180020df6  mov     rcx, [rcx+10h]
0x180020dfa  call    WPP_SF_s
0x180020dff  lea     rdx, [rsp+320h+punk]; struct IActionProgress **
0x180020e04  call    ?_CreateProgress@@YAJPEAUIUnknown@@PEAPEAUIActionProgress@@@Z; _CreateProgress(IUnknown *,IActionProgress * *)
0x180020e09  test    eax, eax
0x180020e0b  jns     short loc_180020E44
0x180020e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e14  cmp     rcx, rdi
0x180020e17  jz      loc_18002141E
0x180020e1d  test    byte ptr [rcx+1Ch], 2
0x180020e21  jz      loc_18002141E
0x180020e27  mov     edx, 72h ; 'r'
0x180020e2c  mov     r9d, eax
0x180020e2f  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180020e36  mov     rcx, [rcx+10h]
0x180020e3a  call    WPP_SF_d
0x180020e3f  jmp     loc_18002141E
0x180020e44  mov     r15d, r12d
0x180020e47  mov     r14d, r12d
0x180020e4a  mov     rax, [rbx+20h]
0x180020e4e  mov     [rbp+220h+Handles], rax
0x180020e52  mov     rax, [rbx+18h]
0x180020e56  mov     [rbp+220h+var_288], rax
0x180020e5a  mov     rax, [rbx+28h]
0x180020e5e  mov     [rbp+220h+var_280], rax
0x180020e62  mov     rax, [rbx+30h]
0x180020e66  mov     [rbp+220h+var_278], rax
0x180020e6a  mov     rax, [rbx+48h]
0x180020e6e  mov     [rbp+220h+var_270], rax
0x180020e72  mov     rax, [rbx+50h]
0x180020e76  mov     [rbp+220h+var_268], rax
0x180020e7a  mov     rax, [rbx+58h]
0x180020e7e  mov     [rbp+220h+var_260], rax
0x180020e82  mov     rax, [rbx+60h]
0x180020e86  mov     [rbp+220h+var_258], rax
0x180020e8a  mov     rax, [rbx+38h]
0x180020e8e  mov     [rbp+220h+var_250], rax
0x180020e92  mov     rax, [rbx+40h]
0x180020e96  mov     [rbp+220h+var_248], rax
0x180020e9a  mov     r13d, 1
0x180020ea0  mov     [rbx+70h], r13d
0x180020ea4  mov     rcx, [rbx+10h]; hEvent
0x180020ea8  call    cs:__imp_SetEvent
0x180020eae  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180020eb2  xor     r8d, r8d; bWaitAll
0x180020eb5  lea     rdx, [rbp+220h+Handles]; lpHandles
0x180020eb9  lea     ecx, [r8+0Ah]; nCount
0x180020ebd  call    cs:__imp_WaitForMultipleObjects
0x180020ec3  mov     edi, eax
0x180020ec5  cmp     eax, 5
0x180020ec8  jz      loc_18002115D
0x180020ece  ja      loc_180021212
0x180020ed4  test    eax, eax
0x180020ed6  jz      loc_1800213D9
0x180020edc  sub     edi, 1
0x180020edf  jz      loc_180021075
0x180020ee5  sub     edi, 1
0x180020ee8  jz      loc_18002100B
0x180020eee  sub     edi, 1
0x180020ef1  jz      short loc_180020F30
0x180020ef3  cmp     edi, 1
0x180020ef6  jnz     short loc_180020EAE
0x180020ef8  lea     rcx, [rsp+320h+CriticalSection]; lpCriticalSection
0x180020efd  call    cs:__imp_EnterCriticalSection
0x180020f03  mov     rcx, [rsp+320h+punk]
0x180020f08  test    rcx, rcx
0x180020f0b  jz      loc_18002114D
0x180020f11  mov     rax, [rcx]
0x180020f14  mov     r8, [rbx+90h]
0x180020f1b  mov     rdx, [rbx+98h]
0x180020f22  mov     rax, [rax+20h]
0x180020f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f2b  jmp     loc_18002114D
0x180020f30  mov     [rbx+6Ch], r12d
0x180020f34  lea     rcx, [rsp+320h+CriticalSection]; lpCriticalSection
0x180020f39  call    cs:__imp_EnterCriticalSection
0x180020f3f  mov     rcx, [rsp+320h+punk]
0x180020f44  test    rcx, rcx
0x180020f47  jz      loc_18002114D
0x180020f4d  mov     [rsp+320h+ppv], r12
0x180020f52  mov     rax, [rcx]
0x180020f55  mov     rax, [rax+40h]
0x180020f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f5e  mov     rcx, [rsp+320h+punk]
0x180020f63  mov     rax, [rcx]
0x180020f66  mov     r8d, 2
0x180020f6c  mov     edx, [rbx+84h]
0x180020f72  mov     rax, [rax+18h]
0x180020f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f7b  mov     rcx, [rsp+320h+punk]
0x180020f80  mov     rax, [rcx]
0x180020f83  lea     r8, [rsp+320h+ppv]
0x180020f88  lea     rdx, _GUID_ebbc7c04_315e_11d2_b62f_006097df5bd4
0x180020f8f  mov     rax, [rax]
0x180020f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f97  lea     r8, [rbx+0ACh]
0x180020f9e  mov     r9d, r13d
0x180020fa1  test    eax, eax
0x180020fa3  js      short loc_180020FE5
0x180020fa5  mov     rcx, [rsp+320h+ppv]
0x180020faa  mov     rax, [rcx]
0x180020fad  mov     qword ptr [rsp+320h+DueTime], r12
0x180020fb2  mov     edx, r13d
0x180020fb5  mov     rax, [rax+50h]
0x180020fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fbe  mov     rcx, [rsp+320h+ppv]
0x180020fc3  mov     rax, [rcx]
0x180020fc6  lea     r8, [rbx+2B4h]
0x180020fcd  mov     qword ptr [rsp+320h+DueTime], r12
0x180020fd2  mov     r9d, r13d
0x180020fd5  mov     edx, 2
0x180020fda  mov     rax, [rax+50h]
0x180020fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fe3  jmp     short loc_180020FFC
0x180020fe5  mov     rcx, [rsp+320h+punk]
0x180020fea  mov     rax, [rcx]
0x180020fed  mov     edx, 2
0x180020ff2  mov     rax, [rax+28h]
0x180020ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ffb  nop
0x180020ffc  lea     rcx, [rsp+320h+ppv]
0x180021001  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021006  jmp     loc_18002114D
0x18002100b  mov     [rbx+6Ch], r13d
0x18002100f  lea     rcx, [rsp+320h+CriticalSection]; lpCriticalSection
0x180021014  call    cs:__imp_EnterCriticalSection
0x18002101a  mov     rcx, [rsp+320h+punk]
0x18002101f  test    rcx, rcx
0x180021022  jz      loc_18002114D
0x180021028  mov     rax, [rcx]
0x18002102b  mov     rax, [rax+40h]
0x18002102f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021034  mov     rcx, [rsp+320h+punk]
0x180021039  mov     rax, [rcx]
0x18002103c  mov     r8d, 20h ; ' '
0x180021042  mov     edx, [rbx+84h]
0x180021048  mov     rax, [rax+18h]
0x18002104c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021051  mov     rcx, [rsp+320h+punk]
0x180021056  mov     rax, [rcx]
0x180021059  lea     r8, [rbx+8CCh]
0x180021060  xor     r9d, r9d
0x180021063  lea     edx, [r9+2]
0x180021067  mov     rax, [rax+28h]
0x18002106b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021070  jmp     loc_18002114D
0x180021075  lea     rcx, [rsp+320h+CriticalSection]; lpCriticalSection
0x18002107a  call    cs:__imp_EnterCriticalSection
0x180021080  mov     rcx, [rsp+320h+punk]
0x180021085  test    rcx, rcx
0x180021088  jz      loc_18002114D
0x18002108e  mov     [rsp+320h+ppv], r12
0x180021093  mov     rax, [rcx]
0x180021096  lea     r8, [rsp+320h+ppv]
0x18002109b  lea     rdx, _GUID_49ff1172_eadc_446d_9285_156453a6431c
0x1800210a2  mov     rax, [rax]
0x1800210a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210aa  test    eax, eax
0x1800210ac  js      loc_180021143
0x1800210b2  mov     [rbp+220h+Buffer], r12w
0x1800210b7  xor     edx, edx; Val
0x1800210b9  mov     r8d, 206h; Size
0x1800210bf  lea     rcx, [rbp+220h+var_23E]; void *
0x1800210c3  call    memset_0
0x1800210c8  mov     r9d, 104h; cchBufferMax
0x1800210ce  lea     r8, [rbp+220h+Buffer]; lpBuffer
0x1800210d2  mov     edx, [rbx+88h]; uID
0x1800210d8  mov     rcx, cs:g_hInst; hInstance
0x1800210df  call    cs:__imp_LoadStringW
0x1800210e5  mov     rcx, [rsp+320h+ppv]
0x1800210ea  mov     rax, [rcx]
0x1800210ed  xor     r9d, r9d
0x1800210f0  lea     r8, [rbp+220h+Buffer]
0x1800210f4  mov     edx, r13d
0x1800210f7  mov     rax, [rax+18h]
0x1800210fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021100  test    eax, eax
0x180021102  js      short loc_180021143
0x180021104  mov     rcx, [rsp+320h+punk]
0x180021109  mov     rax, [rcx]
0x18002110c  mov     r8d, 2
0x180021112  mov     edx, [rbx+84h]
0x180021118  mov     rax, [rax+18h]
0x18002111c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021121  mov     r15d, r13d
0x180021124  test    r14d, r14d
0x180021127  jz      short loc_180021133
0x180021129  mov     rcx, [rsp+320h+punk]; struct IActionProgress *
0x18002112e  call    ?_PauseTimer@@YAJPEAUIActionProgress@@@Z; _PauseTimer(IActionProgress *)
0x180021133  lea     rdx, [rbx+78h]; phwnd
0x180021137  mov     rcx, [rsp+320h+punk]; punk
0x18002113c  call    cs:__imp_IUnknown_GetWindow
0x180021142  nop
0x180021143  lea     rcx, [rsp+320h+ppv]
0x180021148  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002114d  lea     rcx, [rsp+320h+CriticalSection]; lpCriticalSection
0x180021152  call    cs:__imp_LeaveCriticalSection
0x180021158  jmp     loc_180020EAE
0x18002115d  lea     rcx, [rsp+320h+CriticalSection]; lpCriticalSection
0x180021162  call    cs:__imp_EnterCriticalSection
0x180021168  mov     rcx, [rsp+320h+punk]
0x18002116d  test    rcx, rcx
0x180021170  jz      short loc_18002114D
0x180021172  mov     [rsp+320h+ppv], r12
0x180021177  lea     rdi, [rbx+0ACh]
0x18002117e  mov     rax, [rcx]
0x180021181  lea     r8, [rsp+320h+ppv]
0x180021186  lea     rdx, _GUID_ebbc7c04_315e_11d2_b62f_006097df5bd4
0x18002118d  mov     rax, [rax]
0x180021190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021195  mov     r9d, r13d
0x180021198  mov     r8, rdi
0x18002119b  test    eax, eax
0x18002119d  js      short loc_1800211DF
0x18002119f  mov     rcx, [rsp+320h+ppv]
0x1800211a4  mov     rax, [rcx]
0x1800211a7  mov     qword ptr [rsp+320h+DueTime], r12
0x1800211ac  mov     edx, r13d
0x1800211af  mov     rax, [rax+50h]
0x1800211b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211b8  mov     rcx, [rsp+320h+ppv]
0x1800211bd  mov     rax, [rcx]
0x1800211c0  lea     r8, [rbx+2B4h]
0x1800211c7  mov     qword ptr [rsp+320h+DueTime], r12
0x1800211cc  mov     r9d, r13d
0x1800211cf  mov     edx, 2
0x1800211d4  mov     rax, [rax+50h]
0x1800211d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211dd  jmp     short loc_1800211F6
0x1800211df  mov     rcx, [rsp+320h+punk]
0x1800211e4  mov     rax, [rcx]
0x1800211e7  mov     edx, 2
0x1800211ec  mov     rax, [rax+28h]
0x1800211f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211f5  nop
0x1800211f6  mov     rcx, [rsp+320h+ppv]
0x1800211fb  test    rcx, rcx
0x1800211fe  jz      short loc_18002120D
  ... truncated ...
```
