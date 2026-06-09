# CWerService::CheckIfSystemConnectingToPort(_WERSVC_MSG *)

- ea: `0x180014934`
- end: `0x180014c4b`
- name: `?CheckIfSystemConnectingToPort@CWerService@@AEAAJPEAU_WERSVC_MSG@@@Z`
- size: `791`
- prototype: `__int64 __fastcall(CWerService *__hidden this, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180014378`

## callees

- `0x180006a80`
- `0x180007cf8`
- `0x180011ef8`
- `0x180013df4`
- `0x180014934`
- `0x18001caf4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800149fa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800149fa`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014ae9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014ae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014af3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014af3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bb6`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180014b52`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180014b52`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180014b3a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180014b3a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014b95`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014bae`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014b95`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014bae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ba5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ba5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c34`

## string_xrefs

- `0x180014b44`: `WerSvc\WerSvcSystemPermissionsEvent`

## pseudocode

```c
__int64 __fastcall CWerService::CheckIfSystemConnectingToPort(CWerService *this, struct _WERSVC_MSG *a2)
{
  signed int v4; // ebx
  int v5; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  void **v9; // rax
  signed int LastError; // eax
  int v11; // eax
  void **v12; // rax
  signed int v13; // eax
  HANDLE v14; // rax
  DWORD v15; // eax
  signed int v16; // eax
  HANDLE hToken; // [rsp+80h] [rbp+40h] BYREF
  HANDLE ProcessHandle; // [rsp+88h] [rbp+48h] BYREF
  HANDLE ThreadHandle; // [rsp+90h] [rbp+50h] BYREF

  if ( *((_QWORD *)this + 51) == -1 || *((_QWORD *)this + 51) == 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  ThreadHandle = 0;
  ProcessHandle = 0;
  hToken = 0;
  if ( *((__int16 *)a2 + 2) < 0 )
  {
    v4 = 0;
    goto LABEL_49;
  }
  v5 = CWerService::_OpenSenderProcessThread((__int64)this, (__int64)a2, 0, 0, 64, &ThreadHandle, 0);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 29;
      v8 = (unsigned int)v5;
LABEL_48:
      WPP_SF_d(v6[2], v7, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v8);
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  v9 = tlx::replace<tlx::file_handle_traits>(&hToken);
  if ( !OpenThreadToken(ThreadHandle, 0xAu, 1, v9) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
      v4 = -2147467259;
      goto LABEL_14;
    }
    if ( v4 != -2147023888 )
    {
LABEL_14:
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_49;
      v7 = 33;
      goto LABEL_47;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
    v11 = CWerService::_OpenSenderProcessThread((__int64)this, (__int64)a2, 1024, &ProcessHandle, 0, 0, 0);
    v4 = v11;
    if ( v11 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 31;
        v8 = (unsigned int)v11;
        goto LABEL_48;
      }
      goto LABEL_49;
    }
    v12 = tlx::replace<tlx::file_handle_traits>(&hToken);
    if ( !OpenProcessToken(ProcessHandle, 0xAu, v12) )
    {
      v13 = GetLastError();
      v4 = v13;
      if ( v13 > 0 )
        v4 = (unsigned __int16)v13 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147467259;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_49;
      v7 = 32;
LABEL_47:
      v8 = (unsigned int)v4;
      goto LABEL_48;
    }
  }
  if ( ImpersonateLoggedOnUser(hToken) )
  {
    v14 = OpenEventW(0x80000000, 0, L"WerSvc\\WerSvcSystemPermissionsEvent");
    if ( (unsigned __int64)v14 + 1 > 1 )
    {
      CloseHandle(v14);
      v4 = 0;
      RevertToSelf();
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v15);
      }
      RevertToSelf();
      v4 = -2147024891;
    }
    goto LABEL_49;
  }
  v16 = GetLastError();
  v4 = v16;
  if ( v16 > 0 )
    v4 = (unsigned __int16)v16 | 0x80070000;
  if ( v4 >= 0 )
    v4 = -2147467259;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 35;
    goto LABEL_47;
  }
LABEL_49:
  if ( (unsigned __int64)hToken + 1 > 1 )
    CloseHandle(hToken);
  if ( (unsigned __int64)ProcessHandle + 1 > 1 )
    CloseHandle(ProcessHandle);
  if ( (unsigned __int64)ThreadHandle + 1 > 1 )
    CloseHandle(ThreadHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014934  push    rbp
0x180014936  push    rbx
0x180014937  push    rsi
0x180014938  push    rdi
0x180014939  push    r12
0x18001493b  push    r14
0x18001493d  push    r15
0x18001493f  mov     rbp, rsp
0x180014942  sub     rsp, 40h
0x180014946  mov     r14, rdx
0x180014949  mov     r15, rcx
0x18001494c  mov     rax, [rcx+198h]
0x180014953  inc     rax
0x180014956  cmp     rax, 1
0x18001495a  ja      short loc_180014961
0x18001495c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180014961  xor     r12d, r12d
0x180014964  mov     [rbp+ThreadHandle], r12
0x180014968  mov     [rbp+ProcessHandle], r12
0x18001496c  mov     [rbp+hToken], r12
0x180014970  cmp     [r14+4], r12w
0x180014975  jge     short loc_18001497F
0x180014977  mov     ebx, r12d
0x18001497a  jmp     loc_180014BFC
0x18001497f  mov     [rsp+40h+var_10], r12d
0x180014984  lea     rax, [rbp+ThreadHandle]
0x180014988  mov     [rsp+40h+var_18], rax
0x18001498d  mov     [rsp+40h+var_20], 40h ; '@'
0x180014995  xor     r9d, r9d
0x180014998  xor     r8d, r8d
0x18001499b  mov     rdx, r14
0x18001499e  mov     rcx, r15
0x1800149a1  call    ?_OpenSenderProcessThread@CWerService@@AEAAJPEAU_WERSVC_MSG@@KPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K1K@Z; CWerService::_OpenSenderProcessThread(_WERSVC_MSG *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong)
0x1800149a6  mov     ebx, eax
0x1800149a8  test    eax, eax
0x1800149aa  jns     short loc_1800149E1
0x1800149ac  lea     rdi, WPP_GLOBAL_Control
0x1800149b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149ba  cmp     rcx, rdi
0x1800149bd  jz      loc_180014BFC
0x1800149c3  test    byte ptr [rcx+1Ch], 1
0x1800149c7  jz      loc_180014BFC
0x1800149cd  mov     edx, 1Dh
0x1800149d2  mov     r9d, eax
0x1800149d5  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x1800149dc  jmp     loc_180014BF2
0x1800149e1  lea     rcx, [rbp+hToken]
0x1800149e5  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800149ea  mov     r9, rax; TokenHandle
0x1800149ed  mov     edx, 0Ah; DesiredAccess
0x1800149f2  lea     r8d, [rdx-9]; OpenAsSelf
0x1800149f6  mov     rcx, [rbp+ThreadHandle]; ThreadHandle
0x1800149fa  call    cs:__imp_OpenThreadToken
0x180014a00  lea     rdi, WPP_GLOBAL_Control
0x180014a07  lea     rsi, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180014a0e  test    eax, eax
0x180014a10  jnz     loc_180014B36
0x180014a16  call    cs:__imp_GetLastError
0x180014a1c  mov     ebx, eax
0x180014a1e  test    eax, eax
0x180014a20  jle     short loc_180014A2B
0x180014a22  movzx   ebx, ax
0x180014a25  or      ebx, 80070000h
0x180014a2b  test    ebx, ebx
0x180014a2d  js      short loc_180014A58
0x180014a2f  mov     ebx, 80004005h
0x180014a34  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a3b  cmp     rcx, rdi
0x180014a3e  jz      loc_180014BFC
0x180014a44  test    byte ptr [rcx+1Ch], 1
0x180014a48  jz      loc_180014BFC
0x180014a4e  mov     edx, 21h ; '!'
0x180014a53  jmp     loc_180014BEC
0x180014a58  cmp     ebx, 800703F0h
0x180014a5e  jnz     short loc_180014A34
0x180014a60  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a67  cmp     rcx, rdi
0x180014a6a  jz      short loc_180014A83
0x180014a6c  test    byte ptr [rcx+1Ch], 2
0x180014a70  jz      short loc_180014A83
0x180014a72  mov     edx, 1Eh
0x180014a77  mov     r8, rsi
0x180014a7a  mov     rcx, [rcx+10h]
0x180014a7e  call    WPP_SF_
0x180014a83  mov     [rsp+40h+var_10], r12d
0x180014a88  mov     [rsp+40h+var_18], r12
0x180014a8d  mov     [rsp+40h+var_20], r12d
0x180014a92  lea     r9, [rbp+ProcessHandle]
0x180014a96  mov     r8d, 400h
0x180014a9c  mov     rdx, r14
0x180014a9f  mov     rcx, r15
0x180014aa2  call    ?_OpenSenderProcessThread@CWerService@@AEAAJPEAU_WERSVC_MSG@@KPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K1K@Z; CWerService::_OpenSenderProcessThread(_WERSVC_MSG *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong)
0x180014aa7  mov     ebx, eax
0x180014aa9  test    eax, eax
0x180014aab  jns     short loc_180014AD4
0x180014aad  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ab4  cmp     rcx, rdi
0x180014ab7  jz      loc_180014BFC
0x180014abd  test    byte ptr [rcx+1Ch], 1
0x180014ac1  jz      loc_180014BFC
0x180014ac7  mov     edx, 1Fh
0x180014acc  mov     r9d, eax
0x180014acf  jmp     loc_180014BEF
0x180014ad4  lea     rcx, [rbp+hToken]
0x180014ad8  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180014add  mov     r8, rax; TokenHandle
0x180014ae0  mov     edx, 0Ah; DesiredAccess
0x180014ae5  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x180014ae9  call    cs:__imp_OpenProcessToken
0x180014aef  test    eax, eax
0x180014af1  jnz     short loc_180014B36
0x180014af3  call    cs:__imp_GetLastError
0x180014af9  mov     ebx, eax
0x180014afb  test    eax, eax
0x180014afd  jle     short loc_180014B08
0x180014aff  movzx   ebx, ax
0x180014b02  or      ebx, 80070000h
0x180014b08  mov     eax, 80004005h
0x180014b0d  test    ebx, ebx
0x180014b0f  cmovns  ebx, eax
0x180014b12  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b19  cmp     rcx, rdi
0x180014b1c  jz      loc_180014BFC
0x180014b22  test    byte ptr [rcx+1Ch], 1
0x180014b26  jz      loc_180014BFC
0x180014b2c  mov     edx, 20h ; ' '
0x180014b31  jmp     loc_180014BEC
0x180014b36  mov     rcx, [rbp+hToken]; hToken
0x180014b3a  call    cs:__imp_ImpersonateLoggedOnUser
0x180014b40  test    eax, eax
0x180014b42  jz      short loc_180014BB6
0x180014b44  lea     r8, aWersvcWersvcsy; "WerSvc\\WerSvcSystemPermissionsEvent"
0x180014b4b  xor     edx, edx; bInheritHandle
0x180014b4d  mov     ecx, 80000000h; dwDesiredAccess
0x180014b52  call    cs:__imp_OpenEventW
0x180014b58  lea     rcx, [rax+1]
0x180014b5c  cmp     rcx, 1
0x180014b60  ja      short loc_180014BA2
0x180014b62  mov     rax, cs:WPP_GLOBAL_Control
0x180014b69  cmp     rax, rdi
0x180014b6c  jz      short loc_180014B95
0x180014b6e  test    byte ptr [rax+1Ch], 2
0x180014b72  jz      short loc_180014B95
0x180014b74  call    cs:__imp_GetLastError
0x180014b7a  mov     edx, 22h ; '"'
0x180014b7f  mov     r9d, eax
0x180014b82  mov     r8, rsi
0x180014b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b8c  mov     rcx, [rcx+10h]
0x180014b90  call    WPP_SF_d
0x180014b95  call    cs:__imp_RevertToSelf
0x180014b9b  mov     ebx, 80070005h
0x180014ba0  jmp     short loc_180014BFC
0x180014ba2  mov     rcx, rax; hObject
0x180014ba5  call    cs:__imp_CloseHandle
0x180014bab  mov     ebx, r12d
0x180014bae  call    cs:__imp_RevertToSelf
0x180014bb4  jmp     short loc_180014BFC
0x180014bb6  call    cs:__imp_GetLastError
0x180014bbc  mov     ebx, eax
0x180014bbe  test    eax, eax
0x180014bc0  jle     short loc_180014BCB
0x180014bc2  movzx   ebx, ax
0x180014bc5  or      ebx, 80070000h
0x180014bcb  mov     eax, 80004005h
0x180014bd0  test    ebx, ebx
0x180014bd2  cmovns  ebx, eax
0x180014bd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bdc  cmp     rcx, rdi
0x180014bdf  jz      short loc_180014BFC
0x180014be1  test    byte ptr [rcx+1Ch], 1
0x180014be5  jz      short loc_180014BFC
0x180014be7  mov     edx, 23h ; '#'
0x180014bec  mov     r9d, ebx
0x180014bef  mov     r8, rsi
0x180014bf2  mov     rcx, [rcx+10h]
0x180014bf6  call    WPP_SF_d
0x180014bfb  nop
0x180014bfc  mov     rcx, [rbp+hToken]; hObject
0x180014c00  lea     rax, [rcx+1]
0x180014c04  cmp     rax, 1
0x180014c08  jbe     short loc_180014C11
0x180014c0a  call    cs:__imp_CloseHandle
0x180014c10  nop
0x180014c11  mov     rcx, [rbp+ProcessHandle]; hObject
0x180014c15  lea     rax, [rcx+1]
0x180014c19  cmp     rax, 1
0x180014c1d  jbe     short loc_180014C26
0x180014c1f  call    cs:__imp_CloseHandle
0x180014c25  nop
0x180014c26  mov     rcx, [rbp+ThreadHandle]; hObject
0x180014c2a  lea     rax, [rcx+1]
0x180014c2e  cmp     rax, 1
0x180014c32  jbe     short loc_180014C3A
0x180014c34  call    cs:__imp_CloseHandle
0x180014c3a  mov     eax, ebx
0x180014c3c  add     rsp, 40h
0x180014c40  pop     r15
0x180014c42  pop     r14
0x180014c44  pop     r12
0x180014c46  pop     rdi
0x180014c47  pop     rsi
0x180014c48  pop     rbx
0x180014c49  pop     rbp
0x180014c4a  retn
```
