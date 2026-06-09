# CWerService::_OpenSenderProcessThread(_WERSVC_MSG *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong)

- ea: `0x18001caf4`
- end: `0x18001d069`
- name: `?_OpenSenderProcessThread@CWerService@@AEAAJPEAU_WERSVC_MSG@@KPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K1K@Z`
- size: `1397`
- prototype: `__int64 __fastcall(__int64, __int64, int, void **, int, void **, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180014934`
- `0x180014c54`
- `0x18001672c`
- `0x180017578`

## callees

- `0x180007cf8`
- `0x180011ef8`
- `0x180011f38`
- `0x180013df4`
- `0x18001caf4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001ce12`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001ce12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce80`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ce76`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ce76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cffd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d018`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d031`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d046`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cffd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d018`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d031`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d046`
- `ntdll!NtQueryInformationProcess` at `0x18001cf25`
- `ntdll!NtQueryInformationProcess` at `0x18001cf25`
- `ntdll!NtAlpcOpenSenderProcess` at `0x18001cc1d`
- `ntdll!NtAlpcOpenSenderProcess` at `0x18001cda0`
- `ntdll!NtAlpcOpenSenderProcess` at `0x18001cc1d`
- `ntdll!NtAlpcOpenSenderProcess` at `0x18001cda0`
- `ntdll!NtAlpcOpenSenderThread` at `0x18001ccb7`
- `ntdll!NtAlpcOpenSenderThread` at `0x18001ccb7`

## pseudocode

```c
__int64 __fastcall CWerService::_OpenSenderProcessThread(
        __int64 a1,
        __int64 a2,
        int a3,
        void **a4,
        int a5,
        void **a6,
        int a7)
{
  __int64 v10; // rbx
  bool v11; // zf
  void **v12; // r14
  int v13; // edi
  bool v14; // zf
  void *v15; // rcx
  void *v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rax
  int v19; // ebx
  unsigned int v20; // ebx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rbx
  __int64 v24; // rax
  int v25; // ebx
  int v26; // r13d
  int v27; // edi
  __int64 v28; // rcx
  unsigned int v29; // r12d
  HANDLE v30; // rbx
  __int64 v31; // rbx
  __int64 v32; // rax
  int v33; // ebx
  void **v34; // rax
  signed int LastError; // eax
  signed int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r9
  HANDLE v39; // rcx
  NTSTATUS v40; // ebx
  HANDLE *v41; // r10
  void *v42; // rcx
  void *v43; // rcx
  __int64 TokenInformation; // [rsp+30h] [rbp-50h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-48h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-40h] BYREF
  __int128 v48; // [rsp+48h] [rbp-38h] BYREF
  __int128 v49; // [rsp+58h] [rbp-28h]
  __int128 v50; // [rsp+68h] [rbp-18h]
  unsigned __int8 ProcessInformation; // [rsp+D8h] [rbp+58h] BYREF

  v10 = a1;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  hObject = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  ProcessInformation = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  if ( a4 )
  {
    if ( (a3 & 0xFFE00000) == 0 )
      goto LABEL_9;
    v11 = a3 == 0x2000000;
  }
  else
  {
    v11 = a3 == 0;
  }
  if ( !v11 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
LABEL_9:
  v12 = a6;
  v13 = a5;
  if ( a6 )
  {
    if ( (a5 & 0xFFE00000) == 0 )
      goto LABEL_15;
    v14 = a5 == 0x2000000;
  }
  else
  {
    v14 = a5 == 0;
  }
  if ( !v14 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
LABEL_15:
  if ( a4 )
  {
    v15 = *a4;
    *a4 = 0;
    if ( (unsigned __int64)v15 + 1 > 1 )
      CloseHandle(v15);
  }
  if ( v12 )
  {
    v16 = *v12;
    *v12 = 0;
    if ( (unsigned __int64)v16 + 1 > 1 )
      CloseHandle(v16);
  }
  if ( a4 )
  {
    LODWORD(v48) = 48;
    *((_QWORD *)&v48 + 1) = 0;
    DWORD2(v49) = 0;
    *(_QWORD *)&v49 = 0;
    v50 = 0;
    v17 = *(_QWORD *)(v10 + 392);
    v18 = tlx::replace<tlx::file_handle_traits>(a4);
    v19 = NtAlpcOpenSenderProcess(v18, v17, a2, 0, a3, &v48, TokenInformation);
    if ( v19 < 0 )
    {
      v20 = v19 | 0x10000000;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v22 = 10;
LABEL_26:
        WPP_SF_d(v21[2], v22, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v20);
        goto LABEL_44;
      }
      goto LABEL_44;
    }
    v10 = a1;
  }
  if ( v12 )
  {
    LODWORD(v48) = 48;
    *((_QWORD *)&v48 + 1) = 0;
    DWORD2(v49) = 0;
    *(_QWORD *)&v49 = 0;
    v50 = 0;
    v23 = *(_QWORD *)(v10 + 392);
    v24 = tlx::replace<tlx::file_handle_traits>(v12);
    v25 = NtAlpcOpenSenderThread(v24, v23, a2, 0, v13, &v48);
    if ( v25 < 0 )
    {
      v20 = v25 | 0x10000000;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v22 = 11;
        goto LABEL_26;
      }
LABEL_44:
      if ( (v20 & 0x80000000) == 0 )
        goto LABEL_85;
      goto LABEL_78;
    }
  }
  if ( !a7 )
    goto LABEL_84;
  v26 = a7 & 1;
  v27 = a7 & 2;
  v28 = v27 != 0 ? 0x1000 : 0;
  v29 = (v26 << 10) & 0xFFFFEFFF;
  if ( ((v26 << 10) & 0x400) == 0 )
    v29 = v28 | (v26 << 10);
  if ( a4 && (v29 & a3) != 0 )
  {
    v30 = *a4;
    if ( !*a4 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v28);
  }
  else
  {
    LODWORD(v48) = 48;
    *((_QWORD *)&v48 + 1) = 0;
    DWORD2(v49) = 0;
    *(_QWORD *)&v49 = 0;
    v50 = 0;
    v31 = *(_QWORD *)(a1 + 392);
    v32 = tlx::replace<tlx::file_handle_traits>(&hObject);
    v33 = NtAlpcOpenSenderProcess(v32, v31, a2, 0, v29, &v48, TokenInformation);
    if ( v33 < 0 )
    {
      v20 = v33 | 0x10000000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v20);
      goto LABEL_44;
    }
    v30 = hObject;
  }
  if ( !v26 )
    goto LABEL_73;
  v34 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
  if ( !OpenProcessToken(v30, 8u, v34) )
  {
    LastError = GetLastError();
    v20 = LastError;
    if ( LastError > 0 )
      v20 = (unsigned __int16)LastError | 0x80070000;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 13;
      goto LABEL_26;
    }
    goto LABEL_44;
  }
  LODWORD(TokenInformation) = 0;
  if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, (PDWORD)&TokenInformation + 1) )
  {
    v36 = GetLastError();
    v20 = v36;
    if ( v36 > 0 )
      v20 = (unsigned __int16)v36 | 0x80070000;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 14;
      goto LABEL_26;
    }
    goto LABEL_44;
  }
  if ( !(_DWORD)TokenInformation )
  {
LABEL_73:
    if ( v27 )
    {
      ProcessInformation = 0;
      v40 = NtQueryInformationProcess(v30, ProcessAffinityUpdateMode|ProcessUserModeIOPL, &ProcessInformation, 1u, 0);
      if ( v40 < 0 )
      {
        v20 = v40 | 0x10000000;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v22 = 16;
          goto LABEL_26;
        }
        goto LABEL_44;
      }
      v41 = (HANDLE *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
          ProcessInformation & 7,
          ProcessInformation >> 4);
        v41 = (HANDLE *)WPP_GLOBAL_Control;
      }
      if ( (ProcessInformation & 7) == 0 || (ProcessInformation & 0xF0u) < 0x60 )
      {
        v20 = -805265408;
        if ( v41 == &WPP_GLOBAL_Control || (*((_BYTE *)v41 + 28) & 1) == 0 )
          goto LABEL_78;
        v37 = 18;
        v38 = 3489701888LL;
        v39 = v41[2];
        goto LABEL_77;
      }
    }
LABEL_84:
    v20 = 0;
    goto LABEL_85;
  }
  v20 = -2147020644;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_78;
  v37 = 15;
  v38 = 2147946652LL;
  v39 = (HANDLE)*((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_77:
  WPP_SF_d(v39, v37, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v38);
LABEL_78:
  if ( a4 )
  {
    v42 = *a4;
    *a4 = 0;
    if ( (unsigned __int64)v42 + 1 > 1 )
      CloseHandle(v42);
  }
  if ( v12 )
  {
    v43 = *v12;
    *v12 = 0;
    if ( (unsigned __int64)v43 + 1 > 1 )
      CloseHandle(v43);
  }
LABEL_85:
  if ( (unsigned __int64)TokenHandle + 1 > 1 )
    CloseHandle(TokenHandle);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return v20;
}

```

## disassembly

```asm
0x18001caf4  mov     [rsp-38h+arg_10], rbx
0x18001caf9  mov     [rsp-38h+arg_8], rdx
0x18001cafe  mov     [rsp-38h+arg_0], rcx
0x18001cb03  push    rbp
0x18001cb04  push    rsi
0x18001cb05  push    rdi
0x18001cb06  push    r12
0x18001cb08  push    r13
0x18001cb0a  push    r14
0x18001cb0c  push    r15
0x18001cb0e  mov     rbp, rsp
0x18001cb11  sub     rsp, 80h
0x18001cb18  mov     rsi, r9
0x18001cb1b  mov     r15d, r8d
0x18001cb1e  mov     r12, rdx
0x18001cb21  mov     rbx, rcx
0x18001cb24  xorps   xmm0, xmm0
0x18001cb27  movups  [rbp+var_38], xmm0
0x18001cb2b  movups  [rbp+var_28], xmm0
0x18001cb2f  movups  [rbp+var_18], xmm0
0x18001cb33  xor     r13d, r13d
0x18001cb36  mov     [rbp+hObject], r13
0x18001cb3a  mov     [rbp+TokenHandle], r13
0x18001cb3e  mov     [rbp+var_4C], r13d
0x18001cb42  mov     [rbp+TokenInformation], r13d
0x18001cb46  mov     [rbp+ProcessInformation], r13b
0x18001cb4a  test    rdx, rdx
0x18001cb4d  jnz     short loc_18001CB54
0x18001cb4f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001cb54  test    rsi, rsi
0x18001cb57  jz      short loc_18001CB6B
0x18001cb59  test    r15d, 0FFE00000h
0x18001cb60  jz      short loc_18001CB75
0x18001cb62  cmp     r15d, 2000000h
0x18001cb69  jmp     short loc_18001CB6E
0x18001cb6b  test    r15d, r15d
0x18001cb6e  jz      short loc_18001CB75
0x18001cb70  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001cb75  mov     r14, [rbp+arg_28]
0x18001cb79  mov     edi, [rbp+arg_20]
0x18001cb7c  test    r14, r14
0x18001cb7f  jz      short loc_18001CB91
0x18001cb81  test    edi, 0FFE00000h
0x18001cb87  jz      short loc_18001CB9A
0x18001cb89  cmp     edi, 2000000h
0x18001cb8f  jmp     short loc_18001CB93
0x18001cb91  test    edi, edi
0x18001cb93  jz      short loc_18001CB9A
0x18001cb95  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001cb9a  test    rsi, rsi
0x18001cb9d  jz      short loc_18001CBB5
0x18001cb9f  mov     rcx, [rsi]; hObject
0x18001cba2  mov     [rsi], r13
0x18001cba5  lea     rax, [rcx+1]
0x18001cba9  cmp     rax, 1
0x18001cbad  jbe     short loc_18001CBB5
0x18001cbaf  call    cs:__imp_CloseHandle
0x18001cbb5  test    r14, r14
0x18001cbb8  jz      short loc_18001CBD0
0x18001cbba  mov     rcx, [r14]; hObject
0x18001cbbd  mov     [r14], r13
0x18001cbc0  lea     rax, [rcx+1]
0x18001cbc4  cmp     rax, 1
0x18001cbc8  jbe     short loc_18001CBD0
0x18001cbca  call    cs:__imp_CloseHandle
0x18001cbd0  test    rsi, rsi
0x18001cbd3  jz      loc_18001CC6F
0x18001cbd9  mov     dword ptr [rbp+var_38], 30h ; '0'
0x18001cbe0  mov     qword ptr [rbp+var_38+8], r13
0x18001cbe4  mov     dword ptr [rbp+var_28+8], r13d
0x18001cbe8  mov     qword ptr [rbp+var_28], r13
0x18001cbec  xorps   xmm0, xmm0
0x18001cbef  movdqu  [rbp+var_18], xmm0
0x18001cbf4  mov     rbx, [rbx+188h]
0x18001cbfb  mov     rcx, rsi
0x18001cbfe  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18001cc03  lea     rcx, [rbp+var_38]
0x18001cc07  mov     [rsp+80h+var_58], rcx
0x18001cc0c  mov     dword ptr [rsp+80h+ReturnLength], r15d
0x18001cc11  xor     r9d, r9d
0x18001cc14  mov     r8, r12
0x18001cc17  mov     rdx, rbx
0x18001cc1a  mov     rcx, rax
0x18001cc1d  call    cs:__imp_NtAlpcOpenSenderProcess
0x18001cc23  mov     ebx, eax
0x18001cc25  test    eax, eax
0x18001cc27  jns     short loc_18001CC6B
0x18001cc29  bts     ebx, 1Ch
0x18001cc2d  lea     rdi, WPP_GLOBAL_Control
0x18001cc34  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc3b  cmp     rcx, rdi
0x18001cc3e  jz      loc_18001CDE4
0x18001cc44  test    byte ptr [rcx+1Ch], 1
0x18001cc48  jz      loc_18001CDE4
0x18001cc4e  mov     edx, 0Ah
0x18001cc53  mov     r9d, ebx
0x18001cc56  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001cc5d  mov     rcx, [rcx+10h]
0x18001cc61  call    WPP_SF_d
0x18001cc66  jmp     loc_18001CDE4
0x18001cc6b  mov     rbx, [rbp+arg_0]
0x18001cc6f  test    r14, r14
0x18001cc72  jz      short loc_18001CCF2
0x18001cc74  mov     dword ptr [rbp+var_38], 30h ; '0'
0x18001cc7b  mov     qword ptr [rbp+var_38+8], r13
0x18001cc7f  mov     dword ptr [rbp+var_28+8], r13d
0x18001cc83  mov     qword ptr [rbp+var_28], r13
0x18001cc87  xorps   xmm0, xmm0
0x18001cc8a  movdqu  [rbp+var_18], xmm0
0x18001cc8f  mov     rbx, [rbx+188h]
0x18001cc96  mov     rcx, r14
0x18001cc99  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18001cc9e  lea     rcx, [rbp+var_38]
0x18001cca2  mov     [rsp+80h+var_58], rcx
0x18001cca7  mov     dword ptr [rsp+80h+ReturnLength], edi
0x18001ccab  xor     r9d, r9d
0x18001ccae  mov     r8, r12
0x18001ccb1  mov     rdx, rbx
0x18001ccb4  mov     rcx, rax
0x18001ccb7  call    cs:__imp_NtAlpcOpenSenderThread
0x18001ccbd  mov     ebx, eax
0x18001ccbf  test    eax, eax
0x18001ccc1  jns     short loc_18001CCF2
0x18001ccc3  bts     ebx, 1Ch
0x18001ccc7  lea     rdi, WPP_GLOBAL_Control
0x18001ccce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccd5  cmp     rcx, rdi
0x18001ccd8  jz      loc_18001CDE4
0x18001ccde  test    byte ptr [rcx+1Ch], 1
0x18001cce2  jz      loc_18001CDE4
0x18001cce8  mov     edx, 0Bh
0x18001cced  jmp     loc_18001CC53
0x18001ccf2  mov     edi, [rbp+arg_30]
0x18001ccf5  test    edi, edi
0x18001ccf7  jz      loc_18001D020
0x18001ccfd  mov     r13d, edi
0x18001cd00  and     r13d, 1
0x18001cd04  and     edi, 2
0x18001cd07  mov     edx, r13d
0x18001cd0a  shl     edx, 0Ah
0x18001cd0d  mov     eax, edi
0x18001cd0f  neg     eax
0x18001cd11  sbb     ecx, ecx
0x18001cd13  and     ecx, 1000h
0x18001cd19  or      edx, ecx
0x18001cd1b  mov     r12d, edx
0x18001cd1e  btr     r12d, 0Ch
0x18001cd23  bt      edx, 0Ah
0x18001cd27  cmovnb  r12d, edx
0x18001cd2b  test    rsi, rsi
0x18001cd2e  jz      short loc_18001CD4B
0x18001cd30  test    r15d, r12d
0x18001cd33  jz      short loc_18001CD4B
0x18001cd35  mov     rbx, [rsi]
0x18001cd38  test    rbx, rbx
0x18001cd3b  jnz     loc_18001CDF5
0x18001cd41  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001cd46  jmp     loc_18001CDF5
0x18001cd4b  mov     dword ptr [rbp+var_38], 30h ; '0'
0x18001cd52  mov     qword ptr [rbp+var_38+8], 0
0x18001cd5a  mov     dword ptr [rbp+var_28+8], 0
0x18001cd61  mov     qword ptr [rbp+var_28], 0
0x18001cd69  xorps   xmm0, xmm0
0x18001cd6c  movdqu  [rbp+var_18], xmm0
0x18001cd71  mov     rbx, [rbp+arg_0]
0x18001cd75  mov     rbx, [rbx+188h]
0x18001cd7c  lea     rcx, [rbp+hObject]
0x18001cd80  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18001cd85  lea     rcx, [rbp+var_38]
0x18001cd89  mov     [rsp+80h+var_58], rcx
0x18001cd8e  mov     dword ptr [rsp+80h+ReturnLength], r12d
0x18001cd93  xor     r9d, r9d
0x18001cd96  mov     r8, [rbp+arg_8]
0x18001cd9a  mov     rdx, rbx
0x18001cd9d  mov     rcx, rax
0x18001cda0  call    cs:__imp_NtAlpcOpenSenderProcess
0x18001cda6  mov     ebx, eax
0x18001cda8  test    eax, eax
0x18001cdaa  jns     short loc_18001CDF1
0x18001cdac  bts     ebx, 1Ch
0x18001cdb0  lea     rdi, WPP_GLOBAL_Control
0x18001cdb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdbe  cmp     rcx, rdi
0x18001cdc1  jz      short loc_18001CDE1
0x18001cdc3  test    byte ptr [rcx+1Ch], 1
0x18001cdc7  jz      short loc_18001CDE1
0x18001cdc9  mov     edx, 0Ch
0x18001cdce  mov     r9d, ebx
0x18001cdd1  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001cdd8  mov     rcx, [rcx+10h]
0x18001cddc  call    WPP_SF_d
0x18001cde1  xor     r13d, r13d
0x18001cde4  test    ebx, ebx
0x18001cde6  jns     loc_18001D023
0x18001cdec  jmp     loc_18001CFE8
0x18001cdf1  mov     rbx, [rbp+hObject]
0x18001cdf5  test    r13d, r13d
0x18001cdf8  jz      loc_18001CF00
0x18001cdfe  lea     rcx, [rbp+TokenHandle]
0x18001ce02  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18001ce07  mov     r8, rax; TokenHandle
0x18001ce0a  mov     edx, 8; DesiredAccess
0x18001ce0f  mov     rcx, rbx; ProcessHandle
0x18001ce12  call    cs:__imp_OpenProcessToken
0x18001ce18  xor     r13d, r13d
0x18001ce1b  test    eax, eax
0x18001ce1d  jnz     short loc_18001CE57
0x18001ce1f  call    cs:__imp_GetLastError
0x18001ce25  mov     ebx, eax
0x18001ce27  test    eax, eax
0x18001ce29  jle     short loc_18001CE34
0x18001ce2b  movzx   ebx, ax
0x18001ce2e  or      ebx, 80070000h
0x18001ce34  lea     rdi, WPP_GLOBAL_Control
0x18001ce3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce42  cmp     rcx, rdi
0x18001ce45  jz      short loc_18001CDE4
0x18001ce47  test    byte ptr [rcx+1Ch], 1
0x18001ce4b  jz      short loc_18001CDE4
0x18001ce4d  mov     edx, 0Dh
0x18001ce52  jmp     loc_18001CC53
0x18001ce57  mov     [rbp+TokenInformation], r13d
0x18001ce5b  lea     rax, [rbp+var_4C]
0x18001ce5f  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x18001ce64  mov     r9d, 4; TokenInformationLength
0x18001ce6a  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18001ce6e  lea     edx, [r9+19h]; TokenInformationClass
0x18001ce72  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001ce76  call    cs:__imp_GetTokenInformation
0x18001ce7c  test    eax, eax
0x18001ce7e  jnz     short loc_18001CEC0
0x18001ce80  call    cs:__imp_GetLastError
0x18001ce86  mov     ebx, eax
0x18001ce88  test    eax, eax
0x18001ce8a  jle     short loc_18001CE95
0x18001ce8c  movzx   ebx, ax
0x18001ce8f  or      ebx, 80070000h
0x18001ce95  lea     rdi, WPP_GLOBAL_Control
0x18001ce9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cea3  cmp     rcx, rdi
0x18001cea6  jz      loc_18001CDE4
0x18001ceac  test    byte ptr [rcx+1Ch], 1
0x18001ceb0  jz      loc_18001CDE4
0x18001ceb6  mov     edx, 0Eh
0x18001cebb  jmp     loc_18001CC53
0x18001cec0  cmp     [rbp+TokenInformation], r13d
0x18001cec4  jz      short loc_18001CF03
0x18001cec6  mov     ebx, 8007109Ch
0x18001cecb  lea     rdi, WPP_GLOBAL_Control
0x18001ced2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ced9  cmp     rcx, rdi
0x18001cedc  jz      loc_18001CFE8
0x18001cee2  test    byte ptr [rcx+1Ch], 1
0x18001cee6  jz      loc_18001CFE8
0x18001ceec  mov     edx, 0Fh
0x18001cef1  mov     r9d, 8007109Ch
0x18001cef7  mov     rcx, [rcx+10h]
0x18001cefb  jmp     loc_18001CFDC
0x18001cf00  xor     r13d, r13d
0x18001cf03  test    edi, edi
0x18001cf05  jz      loc_18001D020
0x18001cf0b  mov     [rbp+ProcessInformation], r13b
0x18001cf0f  mov     [rsp+80h+ReturnLength], r13; ReturnLength
0x18001cf14  mov     r9d, 1; ProcessInformationLength
0x18001cf1a  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x18001cf1e  lea     edx, [r9+3Ch]; ProcessInformationClass
0x18001cf22  mov     rcx, rbx; ProcessHandle
0x18001cf25  call    cs:__imp_NtQueryInformationProcess
0x18001cf2b  mov     ebx, eax
0x18001cf2d  test    eax, eax
0x18001cf2f  jns     short loc_18001CF60
0x18001cf31  bts     ebx, 1Ch
0x18001cf35  lea     rdi, WPP_GLOBAL_Control
0x18001cf3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf43  cmp     rcx, rdi
0x18001cf46  jz      loc_18001CDE4
0x18001cf4c  test    byte ptr [rcx+1Ch], 1
0x18001cf50  jz      loc_18001CDE4
0x18001cf56  mov     edx, 10h
0x18001cf5b  jmp     loc_18001CC53
0x18001cf60  lea     rdi, WPP_GLOBAL_Control
0x18001cf67  mov     r10, cs:WPP_GLOBAL_Control
0x18001cf6e  cmp     r10, rdi
0x18001cf71  jz      short loc_18001CFA9
0x18001cf73  test    byte ptr [r10+1Ch], 8
0x18001cf78  jz      short loc_18001CFA9
0x18001cf7a  movzx   r9d, [rbp+ProcessInformation]
0x18001cf7f  mov     eax, r9d
0x18001cf82  shr     eax, 4
0x18001cf85  and     r9d, 7
0x18001cf89  mov     edx, 11h
0x18001cf8e  mov     dword ptr [rsp+80h+ReturnLength], eax
0x18001cf92  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001cf99  mov     rcx, [r10+10h]
0x18001cf9d  call    WPP_SF_Dd
0x18001cfa2  mov     r10, cs:WPP_GLOBAL_Control
0x18001cfa9  mov     al, [rbp+ProcessInformation]
0x18001cfac  mov     cl, al
0x18001cfae  and     cl, 7
0x18001cfb1  cmp     cl, 1
  ... truncated ...
```
