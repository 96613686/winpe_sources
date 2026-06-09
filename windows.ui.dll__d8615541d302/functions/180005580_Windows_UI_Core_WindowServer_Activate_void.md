# Windows::UI::Core::WindowServer::Activate(void)

- ea: `0x180005580`
- end: `0x180005791`
- name: `?Activate@WindowServer@Core@UI@Windows@@UEAAJXZ`
- size: `529`
- prototype: `__int64 __fastcall(Windows::UI::Core::WindowServer *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180005580`
- `0x180005798`
- `0x180006c30`
- `0x1800ca010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800055f4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005638`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800055f4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005638`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800055a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800055a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005663`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005663`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x1800056d6`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x1800056d6`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x180005627`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x180005627`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005753`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005753`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x180005786`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x180005786`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1800056cb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1800056cb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18000570e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18000570e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x1800056f9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x1800056f9`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::WindowServer::Activate(Windows::UI::Core::WindowServer *this)
{
  char v2; // bp
  DWORD CurrentProcessId; // eax
  Windows::UI::Core::WindowServer *v4; // rcx
  int ProcessAppContainerSid; // eax
  Windows::UI::Core::WindowServer *v6; // rcx
  struct _TOKEN_APPCONTAINER_INFORMATION *v7; // rsi
  int v8; // edi
  struct _TOKEN_APPCONTAINER_INFORMATION *v10; // r14
  char *SubSystemData; // rcx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  UINT v15; // eax
  Windows::UI::Core::CDispatcher *v16; // rcx
  struct _TOKEN_APPCONTAINER_INFORMATION *v17; // [rsp+40h] [rbp+8h] BYREF
  struct _TOKEN_APPCONTAINER_INFORMATION *v18; // [rsp+48h] [rbp+10h] BYREF

  v17 = 0;
  v18 = 0;
  v2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  ProcessAppContainerSid = Windows::UI::Core::WindowServer::GetProcessAppContainerSid(v4, CurrentProcessId, &v17);
  v7 = v17;
  v8 = ProcessAppContainerSid;
  if ( ProcessAppContainerSid >= 0 )
  {
    v8 = Windows::UI::Core::WindowServer::GetProcessAppContainerSid(v6, *((_DWORD *)this + 536), &v18);
    if ( v8 >= 0 )
    {
      v10 = v18;
      if ( v7->TokenAppContainer && v18->TokenAppContainer && (unsigned __int8)RtlIsParentOfChildAppContainer() )
      {
        v8 = 0;
        v2 = 1;
      }
      operator delete[](v10);
    }
  }
  if ( v7 )
    operator delete[](v7);
  if ( v8 >= 0 )
  {
    if ( !v2 && *((_DWORD *)this + 537) != 3 )
    {
      v16 = (Windows::UI::Core::CDispatcher *)*((_QWORD *)this + 46);
      if ( !v16 || !Windows::UI::Core::CDispatcher::CheckAccess(v16) || *((_DWORD *)this + 537) == 2 )
      {
        v8 = -2147417842;
        RoOriginateError(2147549454LL, 0);
        goto LABEL_5;
      }
    }
    v12 = *((_QWORD *)this + 383);
    if ( v12 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 344LL))(v12);
    }
    else
    {
      v14 = *((_QWORD *)this + 382);
      if ( !v14 )
      {
LABEL_23:
        ShowWindow(*((HWND *)this + 433), 4);
        if ( (unsigned int)QuirkIsEnabled(1114115) )
          SetForegroundWindow(*((HWND *)this + 433));
        if ( *((_QWORD *)this + 267) )
        {
          v15 = RegisterWindowMessageW(L"CoreWindowFirstActivated");
          PostMessageW(*((HWND *)this + 267), v15, 0, 0);
          *((_QWORD *)this + 267) = 0;
        }
        goto LABEL_5;
      }
      v13 = (*(__int64 (__fastcall **)(__int64, Windows::UI::Core::WindowServer *))(*(_QWORD *)v14 + 176LL))(v14, this);
    }
    v8 = v13;
    if ( v13 < 0 )
      goto LABEL_5;
    goto LABEL_23;
  }
LABEL_5:
  if ( *((_BYTE *)this + 2157) )
  {
    SubSystemData = (char *)NtCurrentPeb()->SubSystemData;
    if ( SubSystemData )
    {
      if ( !*((_DWORD *)SubSystemData + 24) )
      {
        *((_DWORD *)SubSystemData + 24) = 1;
        GetSystemTimeAsFileTime((LPFILETIME)(SubSystemData + 100));
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005580  mov     rax, rsp
0x180005583  mov     [rax+18h], rbx
0x180005587  mov     [rax+20h], rbp
0x18000558b  push    rsi
0x18000558c  push    rdi
0x18000558d  push    r14
0x18000558f  sub     rsp, 20h
0x180005593  mov     rbx, rcx
0x180005596  mov     qword ptr [rax+8], 0
0x18000559e  mov     qword ptr [rax+10h], 0
0x1800055a6  xor     bpl, bpl
0x1800055a9  call    cs:__imp_GetCurrentProcessId
0x1800055af  mov     edx, eax; unsigned int
0x1800055b1  lea     r8, [rsp+38h+arg_0]; struct _TOKEN_APPCONTAINER_INFORMATION **
0x1800055b6  call    ?GetProcessAppContainerSid@WindowServer@Core@UI@Windows@@QEAAJKPEAPEAU_TOKEN_APPCONTAINER_INFORMATION@@@Z; Windows::UI::Core::WindowServer::GetProcessAppContainerSid(ulong,_TOKEN_APPCONTAINER_INFORMATION * *)
0x1800055bb  mov     rsi, [rsp+38h+arg_0]
0x1800055c0  mov     edi, eax
0x1800055c2  test    eax, eax
0x1800055c4  jns     short loc_1800055FC
0x1800055c6  test    rsi, rsi
0x1800055c9  jnz     short loc_1800055F1
0x1800055cb  test    edi, edi
0x1800055cd  jns     loc_180005724
0x1800055d3  cmp     byte ptr [rbx+86Dh], 0
0x1800055da  jnz     short loc_180005640
0x1800055dc  mov     rbx, [rsp+38h+arg_10]
0x1800055e1  mov     eax, edi
0x1800055e3  mov     rbp, [rsp+38h+arg_18]
0x1800055e8  add     rsp, 20h
0x1800055ec  pop     r14
0x1800055ee  pop     rdi
0x1800055ef  pop     rsi
0x1800055f0  retn
0x1800055f1  mov     rcx, rsi
0x1800055f4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800055fa  jmp     short loc_1800055CB
0x1800055fc  mov     edx, [rbx+860h]; unsigned int
0x180005602  lea     r8, [rsp+38h+arg_8]; struct _TOKEN_APPCONTAINER_INFORMATION **
0x180005607  call    ?GetProcessAppContainerSid@WindowServer@Core@UI@Windows@@QEAAJKPEAPEAU_TOKEN_APPCONTAINER_INFORMATION@@@Z; Windows::UI::Core::WindowServer::GetProcessAppContainerSid(ulong,_TOKEN_APPCONTAINER_INFORMATION * *)
0x18000560c  mov     edi, eax
0x18000560e  test    eax, eax
0x180005610  js      short loc_1800055C6
0x180005612  mov     rcx, [rsi]
0x180005615  mov     r14, [rsp+38h+arg_8]
0x18000561a  test    rcx, rcx
0x18000561d  jz      short loc_180005635
0x18000561f  mov     rdx, [r14]
0x180005622  test    rdx, rdx
0x180005625  jz      short loc_180005635
0x180005627  call    cs:__imp_RtlIsParentOfChildAppContainer
0x18000562d  test    al, al
0x18000562f  jnz     loc_18000575E
0x180005635  mov     rcx, r14
0x180005638  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000563e  jmp     short loc_1800055C6
0x180005640  mov     rax, gs:60h
0x180005649  mov     rcx, [rax+28h]
0x18000564d  test    rcx, rcx
0x180005650  jz      short loc_1800055DC
0x180005652  cmp     dword ptr [rcx+60h], 0
0x180005656  jnz     short loc_1800055DC
0x180005658  mov     dword ptr [rcx+60h], 1
0x18000565f  add     rcx, 64h ; 'd'; lpSystemTimeAsFileTime
0x180005663  call    cs:__imp_GetSystemTimeAsFileTime
0x180005669  jmp     loc_1800055DC
0x18000566e  call    ?CheckAccess@CDispatcher@Core@UI@Windows@@QEAAHXZ; Windows::UI::Core::CDispatcher::CheckAccess(void)
0x180005673  test    eax, eax
0x180005675  jz      loc_18000574A
0x18000567b  cmp     dword ptr [rbx+864h], 2
0x180005682  jz      loc_18000574A
0x180005688  mov     rcx, [rbx+0BF8h]
0x18000568f  test    rcx, rcx
0x180005692  jz      short loc_1800056AF
0x180005694  mov     rax, [rcx]
0x180005697  mov     rax, [rax+158h]
0x18000569e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056a3  mov     edi, eax
0x1800056a5  test    eax, eax
0x1800056a7  js      loc_1800055D3
0x1800056ad  jmp     short loc_1800056BF
0x1800056af  mov     rcx, [rbx+0BF0h]
0x1800056b6  test    rcx, rcx
0x1800056b9  jnz     loc_180005768
0x1800056bf  mov     rcx, [rbx+0D88h]; hWnd
0x1800056c6  mov     edx, 4; nCmdShow
0x1800056cb  call    cs:__imp_ShowWindow
0x1800056d1  mov     ecx, 110003h
0x1800056d6  call    cs:__imp_QuirkIsEnabled
0x1800056dc  test    eax, eax
0x1800056de  jnz     loc_18000577F
0x1800056e4  cmp     qword ptr [rbx+858h], 0
0x1800056ec  jz      loc_1800055D3
0x1800056f2  lea     rcx, String; "CoreWindowFirstActivated"
0x1800056f9  call    cs:__imp_RegisterWindowMessageW
0x1800056ff  mov     rcx, [rbx+858h]; hWnd
0x180005706  xor     r9d, r9d; lParam
0x180005709  mov     edx, eax; Msg
0x18000570b  xor     r8d, r8d; wParam
0x18000570e  call    cs:__imp_PostMessageW
0x180005714  mov     qword ptr [rbx+858h], 0
0x18000571f  jmp     loc_1800055D3
0x180005724  test    bpl, bpl
0x180005727  jnz     loc_180005688
0x18000572d  cmp     dword ptr [rbx+864h], 3
0x180005734  jz      loc_180005688
0x18000573a  mov     rcx, [rbx+170h]; this
0x180005741  test    rcx, rcx
0x180005744  jnz     loc_18000566E
0x18000574a  mov     edi, 8001010Eh
0x18000574f  xor     edx, edx
0x180005751  mov     ecx, edi
0x180005753  call    cs:__imp_RoOriginateError
0x180005759  jmp     loc_1800055D3
0x18000575e  xor     edi, edi
0x180005760  mov     bpl, 1
0x180005763  jmp     loc_180005635
0x180005768  mov     rax, [rcx]
0x18000576b  mov     rdx, rbx
0x18000576e  mov     rax, [rax+0B0h]
0x180005775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000577a  jmp     loc_1800056A3
0x18000577f  mov     rcx, [rbx+0D88h]; hWnd
0x180005786  call    cs:__imp_SetForegroundWindow
0x18000578c  jmp     loc_1800056E4
```
