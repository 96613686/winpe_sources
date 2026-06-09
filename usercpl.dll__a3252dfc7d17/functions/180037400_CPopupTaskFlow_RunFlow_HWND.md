# CPopupTaskFlow::RunFlow(HWND__ *)

- ea: `0x180037400`
- end: `0x180037a45`
- name: `?RunFlow@CPopupTaskFlow@@UEAAJPEAUHWND__@@@Z`
- size: `1605`
- prototype: `__int64 __fastcall(CPopupTaskFlow *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002ae4`
- `0x18000d9a4`
- `0x1800361dc`
- `0x18003664c`
- `0x180037400`
- `0x180037a4c`
- `0x180038014`
- `0x1800381bc`
- `0x18003892c`
- `0x180038b64`
- `0x1800390e0`
- `0x180039868`
- `0x180039bc8`
- `0x18003a4e0`
- `0x180063b30`
- `0x18007728a`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800374fa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800374fa`
- `ntdll!WinSqmIncrementDWORD` at `0x1800377a7`
- `ntdll!WinSqmIncrementDWORD` at `0x18003794d`
- `ntdll!WinSqmIncrementDWORD` at `0x1800377a7`
- `ntdll!WinSqmIncrementDWORD` at `0x18003794d`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x1800379c7`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x1800379c7`
- `USER32!GetWindowBand` at `0x18003754e`
- `USER32!GetWindowBand` at `0x18003754e`
- `Windows.UI.Immersive!__imp_RegisterImmersiveBehaviors` at `0x18003743e`
- `Windows.UI.Immersive!__imp_RegisterImmersiveBehaviors` at `0x18003743e`
- `Windows.UI.Immersive!__imp_UnregisterImmersiveBehaviors` at `0x180037a13`
- `Windows.UI.Immersive!__imp_UnregisterImmersiveBehaviors` at `0x180037a13`

## string_xrefs

- `0x1800375a6`: `PopupTaskFlowInstance`

## pseudocode

```c
__int64 __fastcall CPopupTaskFlow::RunFlow(CPopupTaskFlow *this, HWND a2)
{
  int TaskFlowElement; // ebx
  int *v5; // r15
  struct CTaskFlowPageInfo *v6; // rbx
  int valid; // eax
  __int64 v8; // rax
  _QWORD *v9; // rsi
  int v10; // eax
  bool v11; // bl
  __int64 v12; // rcx
  CBaseEventHandler *v13; // rax
  CBaseEventHandler *v14; // r14
  struct CTaskFlowPageInfo *v15; // r12
  _DWORD *v16; // rax
  int v17; // ecx
  HWND v18; // rcx
  unsigned int v19; // r9d
  signed int LastError; // eax
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rcx
  LPVOID v27; // rcx
  int i; // r14d
  __int64 v29; // rax
  int v30; // ecx
  _QWORD *v31; // rsi
  DirectUI::Element *v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned int ppv; // [rsp+20h] [rbp-E0h]
  unsigned int v37; // [rsp+28h] [rbp-D8h]
  int v38; // [rsp+30h] [rbp-D0h] BYREF
  int v39; // [rsp+38h] [rbp-C8h] BYREF
  struct CTaskFlowPageInfo *v40; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v41; // [rsp+48h] [rbp-B8h] BYREF
  void **v42; // [rsp+50h] [rbp-B0h] BYREF
  int v43; // [rsp+58h] [rbp-A8h] BYREF
  char v44; // [rsp+5Ch] [rbp-A4h]
  int v45; // [rsp+80h] [rbp-80h] BYREF
  const char *v46; // [rsp+88h] [rbp-78h]
  __int64 v47; // [rsp+90h] [rbp-70h]
  char v48; // [rsp+98h] [rbp-68h]
  int v49; // [rsp+A0h] [rbp-60h]
  _BYTE v50[152]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v51; // [rsp+140h] [rbp+40h]
  int v52; // [rsp+150h] [rbp+50h]
  __int64 v53; // [rsp+158h] [rbp+58h]
  int *v54; // [rsp+160h] [rbp+60h]
  __int64 v55; // [rsp+168h] [rbp+68h]
  __int64 v56; // [rsp+170h] [rbp+70h]
  void ***v57; // [rsp+178h] [rbp+78h]
  __int64 v58; // [rsp+180h] [rbp+80h]
  int v59; // [rsp+188h] [rbp+88h]
  int *v60; // [rsp+190h] [rbp+90h]
  char v61; // [rsp+198h] [rbp+98h]
  _BYTE v62[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  int *v63; // [rsp+1B0h] [rbp+B0h]
  __int64 v64; // [rsp+1B8h] [rbp+B8h]
  struct CTaskFlowPageInfo **v65; // [rsp+1C0h] [rbp+C0h]
  __int64 v66; // [rsp+1C8h] [rbp+C8h]

  v38 = 0;
  TaskFlowElement = RegisterImmersiveBehaviors();
  if ( TaskFlowElement >= 0 )
  {
    TaskFlowElement = CPopupTaskFlow::_CreateDUIPages(this, &v38);
    if ( TaskFlowElement < 0 || v38 <= 0 )
    {
LABEL_64:
      UnregisterImmersiveBehaviors();
      return (unsigned int)TaskFlowElement;
    }
    v38 = 0;
    v5 = (int *)((char *)this + 36);
    *((_DWORD *)this + 9) = 0;
    v6 = **(struct CTaskFlowPageInfo ***)(*((_QWORD *)this + 11) + 8LL);
    v40 = v6;
    do
    {
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)v6 + 2) + 32LL))(*((_QWORD *)v6 + 2), 0, &v38) >= 0
        && v38 )
      {
        break;
      }
      valid = CPopupTaskFlow::_IncrementToNextValidPageFlowIndex(this, (int *)this + 9, &v40);
      v6 = v40;
    }
    while ( valid >= 0 );
    v8 = *((_QWORD *)v6 + 4);
    if ( v8 )
      *(_BYTE *)(v8 + 1616) = 0;
    v41 = 0;
    TaskFlowElement = CoCreateInstance(
                        &CLSID_PopupWindowFactory,
                        0,
                        1u,
                        &GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1,
                        &v41);
    if ( TaskFlowElement < 0 )
      goto LABEL_50;
    if ( a2 )
    {
      v39 = 0;
      v11 = 1;
      if ( (unsigned int)GetWindowBand(a2, &v39) )
        v11 = v39 == 1;
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v41 + 24LL))(v41, v11 ? 16392 : 20480);
      v9 = (_QWORD *)((char *)this + 72);
      v10 = (*(__int64 (__fastcall **)(LPVOID, HWND, char *))(*(_QWORD *)v41 + 72LL))(v41, a2, (char *)this + 72);
    }
    else
    {
      (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v41 + 24LL))(v41, 20480);
      v9 = (_QWORD *)((char *)this + 72);
      v10 = (*(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)v41 + 80LL))(v41, (char *)this + 72);
    }
    TaskFlowElement = v10;
    if ( v10 < 0 )
    {
LABEL_50:
      v27 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
      }
      for ( i = 0; ; ++i )
      {
        v29 = *((_QWORD *)this + 11);
        v30 = v29 ? *(_DWORD *)v29 : 0;
        if ( i >= v30 )
          break;
        v31 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)(v29 + 8) + 8LL * i) + 32LL);
        v32 = (DirectUI::Element *)v31[3];
        if ( v32 )
          DirectUI::Element::RemoveListener(
            v32,
            (struct DirectUI::IElementListener *)((unsigned __int64)(v31 + 2)
                                                & ((unsigned __int128)-(__int128)(unsigned __int64)v31 >> 64)));
        v33 = v31[200];
        v31[200] = 0;
        if ( v33 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        v34 = v31[201];
        v31[201] = 0;
        if ( v34 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      }
      goto LABEL_64;
    }
    v43 = 0;
    v46 = "PopupTaskFlowInstance";
    v51 = 0;
    v44 = 0;
    v48 = 0;
    v45 = 0;
    v47 = 0;
    v49 = 0;
    memset_0(v50, 0, sizeof(v50));
    v12 = *v9;
    v52 = 1;
    v53 = 0;
    v55 = 0;
    v54 = &v43;
    v57 = &v42;
    v60 = &v45;
    v56 = 0;
    v58 = 0;
    v59 = 0;
    v61 = 0;
    v42 = &TaskFlowTelemetry::PopupTaskFlowInstance::`vftable';
    (*(void (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)v12 + 32LL))(v12, L" ");
    TaskFlowElement = CPopupTaskFlow::_CreateTaskFlowElement(this);
    if ( TaskFlowElement >= 0 )
    {
      v13 = (CBaseEventHandler *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v13;
      if ( v13 )
      {
        CBaseEventHandler::CBaseEventHandler(v13);
        *(_QWORD *)v14 = &CDismissCommandHandler::`vftable';
        TaskFlowElement = CBaseEventHandler::Initialize(
                            v14,
                            (struct ITaskFlowFrame *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)));
        if ( TaskFlowElement >= 0 )
        {
          TaskFlowElement = (*(__int64 (__fastcall **)(_QWORD, CBaseEventHandler *))(*(_QWORD *)*v9 + 168LL))(*v9, v14);
          if ( TaskFlowElement >= 0 )
          {
            TaskFlowElement = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v9 + 352LL))(
                                *v9,
                                *((_QWORD *)this + 8));
            if ( TaskFlowElement >= 0 )
            {
              v15 = *(struct CTaskFlowPageInfo **)(*(_QWORD *)(*((_QWORD *)this + 11) + 8LL) + 8LL * *v5);
              TaskFlowElement = CPopupTaskFlow::_SetActivePage(this, v15);
              if ( TaskFlowElement >= 0 )
              {
                v16 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
                if ( v16 )
                {
                  v17 = *v5;
                  *(_QWORD *)v16 = v15;
                  v16[2] = v17;
                  v16[3] = 0;
                  DPA_InsertPtr(*((HDPA *)this + 7), 0x7FFFFFFF, v16);
                }
                TaskFlowElement = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 272LL))(*v9);
                if ( TaskFlowElement >= 0 )
                {
                  if ( *((_DWORD *)&off_18007AE30 + 22 * *((int *)this + 20) + 18) )
                  {
                    TaskFlowTelemetry::PopupTaskFlowInstance::StartActivity(&v42);
                    WinSqmIncrementDWORD(0, *((unsigned int *)&off_18007AE30 + 22 * *((int *)this + 20) + 18), 1);
                  }
                  CPopupTaskFlow::_PostSetActive(this);
                  v40 = (struct CTaskFlowPageInfo *)*((_QWORD *)this + 3);
                  if ( SHProcessMessagesUntilEventsEx(v18, (void **)&v40, v40 != 0, v19, ppv, v37) == -1 )
                  {
                    LastError = GetLastError();
                    TaskFlowElement = LastError;
                    if ( LastError > 0 )
                      TaskFlowElement = (unsigned __int16)LastError | 0x80070000;
                    if ( TaskFlowElement >= 0 )
                      TaskFlowElement = -2147467259;
                  }
                }
              }
            }
          }
        }
        (*(void (__fastcall **)(CBaseEventHandler *))(*(_QWORD *)v14 + 16LL))(v14);
      }
      else
      {
        TaskFlowElement = -2147024882;
      }
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 304LL))(*v9);
    v22 = *v9;
    *v9 = 0;
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( TaskFlowElement >= 0 )
    {
      TaskFlowElement = *((_DWORD *)this + 8);
      if ( TaskFlowElement >= 0 )
      {
        if ( (Microsoft_Windows_User_ControlPanelEnableBits & 0x10) != 0 )
        {
          v39 = *((_DWORD *)this + 20);
          LODWORD(v40) = -1;
          v63 = &v39;
          v65 = &v40;
          v64 = 4;
          v66 = 4;
          McGenEventWrite_EventWriteTransfer(v22, PerfTrack_UAM_TaskFlowPageChange_Stop, v21, 3, v62);
        }
        v23 = *((int *)this + 20);
        if ( !*((_DWORD *)&off_18007AE30 + 22 * v23 + 21) )
          goto LABEL_49;
        TaskFlowTelemetry::PopupTaskFlowInstance::Stop(&v42, v23, 0);
        v24 = *((unsigned int *)&off_18007AE30 + 22 * *((int *)this + 20) + 21);
        goto LABEL_48;
      }
      v25 = *((int *)this + 20);
      v26 = 88 * v25;
      if ( TaskFlowElement == -2147023673 )
      {
        if ( *(_DWORD *)((char *)&off_18007AE30 + v26 + 76) )
        {
          TaskFlowTelemetry::PopupTaskFlowInstance::Stop(&v42, v25, 1);
          v24 = *((unsigned int *)&off_18007AE30 + 22 * *((int *)this + 20) + 19);
LABEL_48:
          WinSqmIncrementDWORD(0, v24, 1);
        }
      }
      else if ( *(_DWORD *)((char *)&off_18007AE30 + v26 + 80) )
      {
        TaskFlowTelemetry::PopupTaskFlowInstance::Stop(&v42, v25, 2);
        v24 = *((unsigned int *)&off_18007AE30 + 22 * *((int *)this + 20) + 20);
        goto LABEL_48;
      }
    }
LABEL_49:
    v42 = &TaskFlowTelemetry::PopupTaskFlowInstance::`vftable';
    wil::ActivityBase<TaskFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v42);
    wil::ActivityBase<TaskFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TaskFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)&v42);
    goto LABEL_50;
  }
  return (unsigned int)TaskFlowElement;
}

```

## disassembly

```asm
0x180037400  mov     [rsp-8+arg_10], rbx
0x180037405  push    rbp
0x180037406  push    rsi
0x180037407  push    rdi
0x180037408  push    r12
0x18003740a  push    r13
0x18003740c  push    r14
0x18003740e  push    r15
0x180037410  lea     rbp, [rsp-0E0h]
0x180037418  sub     rsp, 1E0h
0x18003741f  mov     rax, cs:__security_cookie
0x180037426  xor     rax, rsp
0x180037429  mov     [rbp+110h+var_40], rax
0x180037430  xor     r13d, r13d
0x180037433  mov     r14, rdx
0x180037436  mov     [rsp+210h+var_1E0], r13d
0x18003743b  mov     rdi, rcx
0x18003743e  call    cs:__imp_RegisterImmersiveBehaviors
0x180037444  mov     ebx, eax
0x180037446  test    eax, eax
0x180037448  js      loc_180037A19
0x18003744e  lea     rdx, [rsp+210h+var_1E0]; int *
0x180037453  mov     rcx, rdi; this
0x180037456  call    ?_CreateDUIPages@CPopupTaskFlow@@AEAAJPEAH@Z; CPopupTaskFlow::_CreateDUIPages(int *)
0x18003745b  mov     ebx, eax
0x18003745d  test    eax, eax
0x18003745f  js      loc_180037A13
0x180037465  cmp     [rsp+210h+var_1E0], r13d
0x18003746a  jle     loc_180037A13
0x180037470  mov     [rsp+210h+var_1E0], r13d
0x180037475  lea     r15, [rdi+24h]
0x180037479  mov     [r15], r13d
0x18003747c  mov     rax, [rdi+58h]
0x180037480  mov     rcx, [rax+8]
0x180037484  mov     rbx, [rcx]
0x180037487  mov     [rsp+210h+var_1D0], rbx
0x18003748c  mov     rcx, [rbx+10h]
0x180037490  lea     r8, [rsp+210h+var_1E0]
0x180037495  xor     edx, edx
0x180037497  mov     rax, [rcx]
0x18003749a  mov     rax, [rax+20h]
0x18003749e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374a3  test    eax, eax
0x1800374a5  js      short loc_1800374AE
0x1800374a7  cmp     [rsp+210h+var_1E0], r13d
0x1800374ac  jnz     short loc_1800374C7
0x1800374ae  lea     r8, [rsp+210h+var_1D0]; struct CTaskFlowPageInfo **
0x1800374b3  mov     rdx, r15; int *
0x1800374b6  mov     rcx, rdi; this
0x1800374b9  call    ?_IncrementToNextValidPageFlowIndex@CPopupTaskFlow@@AEAAJPEAHPEAPEAVCTaskFlowPageInfo@@@Z; CPopupTaskFlow::_IncrementToNextValidPageFlowIndex(int *,CTaskFlowPageInfo * *)
0x1800374be  mov     rbx, [rsp+210h+var_1D0]
0x1800374c3  test    eax, eax
0x1800374c5  jns     short loc_18003748C
0x1800374c7  mov     rax, [rbx+20h]
0x1800374cb  test    rax, rax
0x1800374ce  jz      short loc_1800374D7
0x1800374d0  mov     [rax+650h], r13b
0x1800374d7  xor     edx, edx; pUnkOuter
0x1800374d9  mov     [rsp+210h+var_1C8], r13
0x1800374de  lea     rax, [rsp+210h+var_1C8]
0x1800374e3  lea     r9, _GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1; riid
0x1800374ea  mov     [rsp+210h+ppv], rax; unsigned int
0x1800374ef  lea     rcx, CLSID_PopupWindowFactory; rclsid
0x1800374f6  lea     r8d, [rdx+1]; dwClsContext
0x1800374fa  call    cs:__imp_CoCreateInstance
0x180037500  mov     ebx, eax
0x180037502  test    eax, eax
0x180037504  js      loc_18003796C
0x18003750a  test    r14, r14
0x18003750d  jnz     short loc_18003753F
0x18003750f  mov     rcx, [rsp+210h+var_1C8]
0x180037514  mov     edx, 5000h
0x180037519  mov     rax, [rcx]
0x18003751c  mov     rax, [rax+18h]
0x180037520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037525  mov     rcx, [rsp+210h+var_1C8]
0x18003752a  lea     rsi, [rdi+48h]
0x18003752e  mov     rdx, rsi
0x180037531  mov     rax, [rcx]
0x180037534  mov     rax, [rax+50h]
0x180037538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003753d  jmp     short loc_18003759C
0x18003753f  lea     rdx, [rsp+210h+var_1D8]
0x180037544  mov     [rsp+210h+var_1D8], r13d
0x180037549  mov     rcx, r14
0x18003754c  mov     bl, 1
0x18003754e  call    cs:__imp_GetWindowBand
0x180037554  test    eax, eax
0x180037556  jz      short loc_180037560
0x180037558  cmp     [rsp+210h+var_1D8], 1
0x18003755d  setz    bl
0x180037560  mov     rcx, [rsp+210h+var_1C8]
0x180037565  neg     bl
0x180037567  sbb     edx, edx
0x180037569  and     edx, 0FFFFF008h
0x18003756f  mov     rax, [rcx]
0x180037572  add     edx, 5000h
0x180037578  mov     rax, [rax+18h]
0x18003757c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037581  mov     rcx, [rsp+210h+var_1C8]
0x180037586  lea     rsi, [rdi+48h]
0x18003758a  mov     r8, rsi
0x18003758d  mov     rdx, r14
0x180037590  mov     rax, [rcx]
0x180037593  mov     rax, [rax+48h]
0x180037597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003759c  mov     ebx, eax
0x18003759e  test    eax, eax
0x1800375a0  js      loc_18003796C
0x1800375a6  lea     rax, aPopuptaskflowi; "PopupTaskFlowInstance"
0x1800375ad  mov     [rsp+210h+var_1B8], r13d
0x1800375b2  xorps   xmm0, xmm0
0x1800375b5  mov     [rbp+110h+var_188], rax
0x1800375b9  xor     edx, edx; Val
0x1800375bb  movdqa  [rbp+110h+var_D0], xmm0
0x1800375c0  mov     r8d, 98h; Size
0x1800375c6  mov     [rsp+210h+var_1B4], r13b
0x1800375cb  lea     rcx, [rbp+110h+var_168]; void *
0x1800375cf  mov     [rbp+110h+var_178], r13b
0x1800375d3  mov     [rbp+110h+var_190], r13d
0x1800375d7  mov     [rbp+110h+var_180], r13
0x1800375db  mov     [rbp+110h+var_170], r13d
0x1800375df  call    memset_0
0x1800375e4  mov     rcx, [rsi]
0x1800375e7  lea     r14, ??_7PopupTaskFlowInstance@TaskFlowTelemetry@@6B@; const TaskFlowTelemetry::PopupTaskFlowInstance::`vftable'
0x1800375ee  xor     eax, eax
0x1800375f0  mov     [rbp+110h+var_C0], 1
0x1800375f7  mov     [rbp+110h+var_B8], rax
0x1800375fb  lea     rdx, pszTrimChars; " "
0x180037602  lea     rax, [rsp+210h+var_1B8]
0x180037607  mov     [rbp+110h+var_A8], r13
0x18003760b  mov     [rbp+110h+var_B0], rax
0x18003760f  lea     rax, [rsp+210h+var_1C0]
0x180037614  mov     [rbp+110h+var_98], rax
0x180037618  lea     rax, [rbp+110h+var_190]
0x18003761c  mov     [rbp+110h+var_80], rax
0x180037623  mov     [rbp+110h+var_A0], r13
0x180037627  mov     [rbp+110h+var_90], r13
0x18003762e  mov     [rbp+110h+var_88], r13d
0x180037635  mov     [rbp+110h+var_78], r13b
0x18003763c  mov     [rsp+210h+var_1C0], r14
0x180037641  mov     rax, [rcx]
0x180037644  mov     rax, [rax+20h]
0x180037648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003764d  mov     rcx, rdi; this
0x180037650  call    ?_CreateTaskFlowElement@CPopupTaskFlow@@AEAAJXZ; CPopupTaskFlow::_CreateTaskFlowElement(void)
0x180037655  lea     r12, off_18007AE30
0x18003765c  mov     ebx, eax
0x18003765e  test    eax, eax
0x180037660  js      loc_18003781C
0x180037666  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003766d  mov     ecx, 18h; unsigned __int64
0x180037672  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180037677  mov     r14, rax
0x18003767a  test    rax, rax
0x18003767d  jz      loc_180037810
0x180037683  mov     rcx, rax; this
0x180037686  call    ??0CBaseEventHandler@@QEAA@XZ; CBaseEventHandler::CBaseEventHandler(void)
0x18003768b  lea     rax, ??_7CDismissCommandHandler@@6B@; const CDismissCommandHandler::`vftable'
0x180037692  mov     rcx, rdi
0x180037695  neg     rcx
0x180037698  mov     [r14], rax
0x18003769b  mov     rax, cs:off_18007B350
0x1800376a2  lea     r8, [rdi+8]
0x1800376a6  sbb     rdx, rdx
0x1800376a9  mov     rcx, r14
0x1800376ac  and     rdx, r8
0x1800376af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376b4  mov     ebx, eax
0x1800376b6  test    eax, eax
0x1800376b8  js      loc_1800377FF
0x1800376be  mov     rcx, [rsi]
0x1800376c1  mov     rdx, r14
0x1800376c4  mov     rax, [rcx]
0x1800376c7  mov     rax, [rax+0A8h]
0x1800376ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376d3  mov     ebx, eax
0x1800376d5  test    eax, eax
0x1800376d7  js      loc_1800377FF
0x1800376dd  mov     rcx, [rsi]
0x1800376e0  mov     rdx, [rdi+40h]
0x1800376e4  mov     rax, [rcx]
0x1800376e7  mov     rax, [rax+160h]
0x1800376ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376f3  mov     ebx, eax
0x1800376f5  test    eax, eax
0x1800376f7  js      loc_1800377FF
0x1800376fd  mov     rax, [rdi+58h]
0x180037701  movsxd  r8, dword ptr [r15]
0x180037704  mov     rcx, [rax+8]
0x180037708  mov     r12, [rcx+r8*8]
0x18003770c  mov     rcx, rdi; this
0x18003770f  mov     rdx, r12; struct CTaskFlowPageInfo *
0x180037712  call    ?_SetActivePage@CPopupTaskFlow@@AEAAJPEAVCTaskFlowPageInfo@@@Z; CPopupTaskFlow::_SetActivePage(CTaskFlowPageInfo *)
0x180037717  mov     ebx, eax
0x180037719  test    eax, eax
0x18003771b  js      loc_1800377F8
0x180037721  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180037728  mov     ecx, 10h; unsigned __int64
0x18003772d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180037732  test    rax, rax
0x180037735  jz      short loc_180037756
0x180037737  mov     ecx, [r15]
0x18003773a  mov     r8, rax; p
0x18003773d  mov     [rax], r12
0x180037740  mov     edx, 7FFFFFFFh; i
0x180037745  mov     [rax+8], ecx
0x180037748  mov     [rax+0Ch], r13d
0x18003774c  mov     rcx, [rdi+38h]; hdpa
0x180037750  call    cs:__imp_DPA_InsertPtr
0x180037756  mov     rcx, [rsi]
0x180037759  mov     rax, [rcx]
0x18003775c  mov     rax, [rax+110h]
0x180037763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037768  lea     r12, off_18007AE30
0x18003776f  mov     ebx, eax
0x180037771  test    eax, eax
0x180037773  js      loc_1800377FF
0x180037779  movsxd  rdx, dword ptr [rdi+50h]
0x18003777d  imul    rcx, rdx, 58h ; 'X'
0x180037781  cmp     [rcx+r12+48h], r13d
0x180037786  jz      short loc_1800377AD
0x180037788  lea     rcx, [rsp+210h+var_1C0]
0x18003778d  call    ?StartActivity@PopupTaskFlowInstance@TaskFlowTelemetry@@QEAAXW4TASK_FLOW_ID@@@Z; TaskFlowTelemetry::PopupTaskFlowInstance::StartActivity(TASK_FLOW_ID)
0x180037792  movsxd  rax, dword ptr [rdi+50h]
0x180037796  mov     r8d, 1
0x18003779c  imul    rdx, rax, 58h ; 'X'
0x1800377a0  xor     ecx, ecx
0x1800377a2  mov     edx, [rdx+r12+48h]
0x1800377a7  call    cs:__imp_WinSqmIncrementDWORD
0x1800377ad  mov     rcx, rdi; this
0x1800377b0  call    ?_PostSetActive@CPopupTaskFlow@@AEAAXXZ; CPopupTaskFlow::_PostSetActive(void)
0x1800377b5  mov     rax, [rdi+18h]
0x1800377b9  lea     rdx, [rsp+210h+var_1D0]; void **
0x1800377be  test    rax, rax
0x1800377c1  mov     [rsp+210h+var_1D0], rax
0x1800377c6  mov     r8d, r13d
0x1800377c9  setnz   r8b; unsigned int
0x1800377cd  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x1800377d2  cmp     eax, 0FFFFFFFFh
0x1800377d5  jnz     short loc_1800377FF
0x1800377d7  call    cs:__imp_GetLastError
0x1800377dd  mov     ebx, eax
0x1800377df  test    eax, eax
0x1800377e1  jle     short loc_1800377EC
0x1800377e3  movzx   ebx, ax
0x1800377e6  or      ebx, 80070000h
0x1800377ec  test    ebx, ebx
0x1800377ee  mov     eax, 80004005h
0x1800377f3  cmovns  ebx, eax
0x1800377f6  jmp     short loc_1800377FF
0x1800377f8  lea     r12, off_18007AE30
0x1800377ff  mov     rax, [r14]
0x180037802  mov     rcx, r14
0x180037805  mov     rax, [rax+10h]
0x180037809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003780e  jmp     short loc_180037815
0x180037810  mov     ebx, 8007000Eh
0x180037815  lea     r14, ??_7PopupTaskFlowInstance@TaskFlowTelemetry@@6B@; const TaskFlowTelemetry::PopupTaskFlowInstance::`vftable'
0x18003781c  mov     rcx, [rsi]
0x18003781f  mov     rax, [rcx]
0x180037822  mov     rax, [rax+130h]
0x180037829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003782e  mov     rcx, [rsi]
0x180037831  mov     [rsi], r13
0x180037834  test    rcx, rcx
0x180037837  jz      short loc_180037845
0x180037839  mov     rax, [rcx]
0x18003783c  mov     rax, [rax+10h]
0x180037840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037845  test    ebx, ebx
0x180037847  js      loc_180037953
0x18003784d  mov     ebx, [rdi+20h]
0x180037850  test    ebx, ebx
0x180037852  js      loc_1800378EB
0x180037858  test    cs:Microsoft_Windows_User_ControlPanelEnableBits, 10h
0x18003785f  jz      short loc_1800378BC
0x180037861  mov     eax, [rdi+50h]
0x180037864  lea     rdx, PerfTrack_UAM_TaskFlowPageChange_Stop
0x18003786b  mov     [rsp+210h+var_1D8], eax
0x18003786f  mov     r9d, 3
0x180037875  lea     rax, [rsp+210h+var_1D8]
0x18003787a  mov     dword ptr [rsp+210h+var_1D0], 0FFFFFFFFh
0x180037882  mov     [rbp+110h+var_60], rax
0x180037889  lea     rax, [rsp+210h+var_1D0]
0x18003788e  mov     [rbp+110h+var_50], rax
0x180037895  lea     rax, [rbp+110h+var_70]
0x18003789c  mov     [rsp+210h+ppv], rax
0x1800378a1  mov     [rbp+110h+var_58], 4
0x1800378ac  mov     [rbp+110h+var_48], 4
0x1800378b7  call    McGenEventWrite_EventWriteTransfer
0x1800378bc  movsxd  rdx, dword ptr [rdi+50h]
0x1800378c0  imul    rcx, rdx, 58h ; 'X'
0x1800378c4  cmp     [rcx+r12+54h], r13d
0x1800378c9  jz      loc_180037953
0x1800378cf  xor     r8d, r8d
0x1800378d2  lea     rcx, [rsp+210h+var_1C0]
0x1800378d7  call    ?Stop@PopupTaskFlowInstance@TaskFlowTelemetry@@QEAAXW4TASK_FLOW_ID@@W4TelemetryTaskFlowResult@2@@Z; TaskFlowTelemetry::PopupTaskFlowInstance::Stop(TASK_FLOW_ID,TaskFlowTelemetry::TelemetryTaskFlowResult)
0x1800378dc  movsxd  rax, dword ptr [rdi+50h]
0x1800378e0  imul    rdx, rax, 58h ; 'X'
  ... truncated ...
```
