# CReportManager::AddUiThreadInfoToReport(void)

- ea: `0x18007d260`
- end: `0x18007d80c`
- name: `?AddUiThreadInfoToReport@CReportManager@@AEAAJXZ`
- size: `1452`
- prototype: `__int64 __fastcall(CReportManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18007c77c`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x180020680`
- `0x18002dc4c`
- `0x180053300`
- `0x180073c8c`
- `0x18007bc4c`
- `0x18007c5b4`
- `0x18007d260`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18007d483`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18007d483`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007d2a8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007d370`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007d2a8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007d370`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d3da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d56e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d5ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d6ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d6fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d3da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d56e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d5ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d6ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d6fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d793`
- `ntdll!NtQueryInformationThread` at `0x18007d4b9`
- `ntdll!NtQueryInformationThread` at `0x18007d4b9`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18007d55c`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18007d5df`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18007d55c`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18007d5df`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x18007d318`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x18007d318`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18007d390`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18007d390`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x18007d3ca`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x18007d3ca`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x18007d6d9`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x18007d6d9`

## pseudocode

```c
__int64 __fastcall CReportManager::AddUiThreadInfoToReport(CReportManager *this)
{
  __int64 v1; // rax
  int v3; // esi
  void *v4; // rcx
  DWORD ProcessId; // r15d
  HANDLE v6; // r12
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  DWORD v10; // eax
  char *Toolhelp32Snapshot; // rbx
  signed int v12; // eax
  wchar_t *v13; // rcx
  __int64 v14; // rdx
  _QWORD *v15; // rdi
  HANDLE v16; // rax
  NTSTATUS InformationThread; // eax
  wchar_t *v18; // rcx
  __int64 v19; // rdx
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  wchar_t *v24; // rcx
  __int64 v25; // rdx
  signed int LastError; // eax
  HANDLE v28; // [rsp+30h] [rbp-49h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-41h] BYREF
  HANDLE Process; // [rsp+40h] [rbp-39h] BYREF
  char *v31; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int64 Buffer; // [rsp+50h] [rbp-29h] BYREF
  _OWORD ThreadInformation[3]; // [rsp+58h] [rbp-21h] BYREF
  THREADENTRY32 te; // [rsp+88h] [rbp+Fh] BYREF

  v1 = *((_QWORD *)this + 1);
  v3 = 0;
  v4 = *(void **)(v1 + 6640);
  if ( v4 )
  {
    ProcessId = GetProcessId(v4);
    v6 = *(HANDLE *)(*((_QWORD *)this + 1) + 6640LL);
  }
  else if ( *(_QWORD *)(v1 + 9112) )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
    v7 = *((_QWORD *)this + 1);
    Process = 0;
    v8 = PssQuerySnapshot(*(_QWORD *)(v7 + 9112), 1, &Process);
    v9 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, v9);
      return v9;
    }
    v10 = GetProcessId(Process);
    v6 = Process;
    ProcessId = v10;
  }
  else
  {
    ProcessId = 0;
    v6 = 0;
  }
  Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(4u, 0);
  v31 = Toolhelp32Snapshot;
  if ( Toolhelp32Snapshot == (char *)-1LL || Toolhelp32Snapshot + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_79;
    v14 = 56;
    goto LABEL_78;
  }
  te.dwSize = 28;
  memset(&te.cntUsage, 0, 24);
  if ( !Thread32First(Toolhelp32Snapshot, &te) )
  {
    v12 = GetLastError();
    v9 = v12;
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_79;
    v14 = 57;
LABEL_78:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, v9);
LABEL_79:
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v31);
    return v9;
  }
  utl::make_unique<_TEB,,0>(&lpBuffer);
  v15 = lpBuffer;
  if ( !lpBuffer )
  {
    v24 = WPP_GLOBAL_Control;
    v9 = -2147024882;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v25 = 58;
LABEL_71:
      WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, v9);
    }
LABEL_72:
    utl::unique_ptr<_TEB,utl::default_delete<_TEB>>::~unique_ptr<_TEB,utl::default_delete<_TEB>>(&lpBuffer);
    goto LABEL_79;
  }
  do
  {
    if ( te.th32OwnerProcessID != ProcessId )
      continue;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
        te.th32ThreadID);
    memset(ThreadInformation, 0, sizeof(ThreadInformation));
    v16 = OpenThread(0x40u, 0, te.th32ThreadID);
    v28 = v16;
    if ( (unsigned __int64)v16 + 1 <= 1 )
    {
      v22 = GetLastError();
      v3 = v22;
      if ( v22 > 0 )
        v3 = (unsigned __int16)v22 | 0x80070000;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
        goto LABEL_59;
      v19 = 60;
LABEL_58:
      WPP_SF_Dd(
        *((_QWORD *)v18 + 2),
        v19,
        WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
        (unsigned int)v3,
        te.th32ThreadID);
      goto LABEL_59;
    }
    InformationThread = NtQueryInformationThread(v16, ThreadBasicInformation, ThreadInformation, 0x30u, 0);
    if ( InformationThread < 0 )
    {
      v3 = InformationThread | 0x10000000;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
        goto LABEL_59;
      v19 = 61;
      goto LABEL_58;
    }
    if ( !*((_QWORD *)&ThreadInformation[0] + 1) )
    {
      v3 = -2147467259;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
          te.th32ThreadID);
      goto LABEL_59;
    }
    if ( !ReadProcessMemory(v6, *((LPCVOID *)&ThreadInformation[0] + 1), v15, 0x1870u, 0) )
    {
      v20 = GetLastError();
      v3 = v20;
      if ( v20 > 0 )
        v3 = (unsigned __int16)v20 | 0x80070000;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
        goto LABEL_59;
      v19 = 63;
      goto LABEL_58;
    }
    if ( v15[15] )
    {
      Buffer = 0;
      if ( ReadProcessMemory(v6, (LPCVOID)(*((_QWORD *)&ThreadInformation[0] + 1) + 2144LL), &Buffer, 8u, 0) )
      {
        v3 = CReport::AddMemBlock(*((CReport **)this + 1), ProcessId, Buffer, 0x30u, 0);
        if ( v3 >= 0 )
          goto LABEL_59;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_59;
        v19 = 65;
      }
      else
      {
        v21 = GetLastError();
        v3 = v21;
        if ( v21 > 0 )
          v3 = (unsigned __int16)v21 | 0x80070000;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
          goto LABEL_59;
        v19 = 64;
      }
      goto LABEL_58;
    }
LABEL_59:
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v28);
  }
  while ( Thread32Next(Toolhelp32Snapshot, &te) );
  if ( GetLastError() != 18 )
  {
    v23 = GetLastError();
    v9 = v23;
    if ( v23 > 0 )
      v9 = (unsigned __int16)v23 | 0x80070000;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v25 = 66;
      goto LABEL_71;
    }
    goto LABEL_72;
  }
  utl::unique_ptr<_TEB,utl::default_delete<_TEB>>::~unique_ptr<_TEB,utl::default_delete<_TEB>>(&lpBuffer);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v31);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18007d260  mov     [rsp-8+arg_8], rbx
0x18007d265  mov     [rsp-8+arg_10], rsi
0x18007d26a  push    rbp
0x18007d26b  push    rdi
0x18007d26c  push    r12
0x18007d26e  push    r13
0x18007d270  push    r15
0x18007d272  lea     rbp, [rsp-37h]
0x18007d277  sub     rsp, 0B0h
0x18007d27e  mov     rax, cs:__security_cookie
0x18007d285  xor     rax, rsp
0x18007d288  mov     [rbp+57h+var_28], rax
0x18007d28c  mov     rax, [rcx+8]
0x18007d290  lea     rdi, WPP_GLOBAL_Control
0x18007d297  mov     r13, rcx
0x18007d29a  xor     esi, esi
0x18007d29c  mov     rcx, [rax+19F0h]; Process
0x18007d2a3  test    rcx, rcx
0x18007d2a6  jz      short loc_18007D2C7
0x18007d2a8  call    cs:__imp_GetProcessId
0x18007d2af  nop     dword ptr [rax+rax+00h]
0x18007d2b4  mov     rcx, [r13+8]
0x18007d2b8  mov     r15d, eax
0x18007d2bb  mov     r12, [rcx+19F0h]
0x18007d2c2  jmp     loc_18007D38B
0x18007d2c7  cmp     [rax+2398h], rsi
0x18007d2ce  jz      loc_18007D385
0x18007d2d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d2db  cmp     rcx, rdi
0x18007d2de  jz      short loc_18007D2FB
0x18007d2e0  test    byte ptr [rcx+1Ch], 2
0x18007d2e4  jz      short loc_18007D2FB
0x18007d2e6  mov     rcx, [rcx+10h]
0x18007d2ea  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18007d2f1  mov     edx, 36h ; '6'
0x18007d2f6  call    WPP_SF_
0x18007d2fb  mov     rcx, [r13+8]
0x18007d2ff  lea     r8, [rbp+57h+Process]
0x18007d303  mov     r9d, 8
0x18007d309  mov     [rbp+57h+Process], rsi
0x18007d30d  mov     rcx, [rcx+2398h]
0x18007d314  lea     edx, [r9-7]
0x18007d318  call    cs:__imp_PssQuerySnapshot
0x18007d31f  nop     dword ptr [rax+rax+00h]
0x18007d324  mov     ebx, eax
0x18007d326  test    eax, eax
0x18007d328  jz      short loc_18007D36C
0x18007d32a  jle     short loc_18007D335
0x18007d32c  movzx   ebx, ax
0x18007d32f  or      ebx, 80070000h
0x18007d335  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d33c  cmp     rcx, rdi
0x18007d33f  jz      loc_18007D7E1
0x18007d345  test    byte ptr [rcx+1Ch], 1
0x18007d349  jz      loc_18007D7E1
0x18007d34f  mov     rcx, [rcx+10h]
0x18007d353  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18007d35a  mov     edx, 37h ; '7'
0x18007d35f  mov     r9d, ebx
0x18007d362  call    WPP_SF_d
0x18007d367  jmp     loc_18007D7E1
0x18007d36c  mov     rcx, [rbp+57h+Process]; Process
0x18007d370  call    cs:__imp_GetProcessId
0x18007d377  nop     dword ptr [rax+rax+00h]
0x18007d37c  mov     r12, [rbp+57h+Process]
0x18007d380  mov     r15d, eax
0x18007d383  jmp     short loc_18007D38B
0x18007d385  mov     r15d, esi
0x18007d388  mov     r12, rsi
0x18007d38b  xor     edx, edx; th32ProcessID
0x18007d38d  lea     ecx, [rdx+4]; dwFlags
0x18007d390  call    cs:__imp_CreateToolhelp32Snapshot
0x18007d397  nop     dword ptr [rax+rax+00h]
0x18007d39c  mov     rbx, rax
0x18007d39f  mov     [rbp+57h+var_88], rax
0x18007d3a3  inc     rax
0x18007d3a6  cmp     rax, 1
0x18007d3aa  jbe     loc_18007D793
0x18007d3b0  xorps   xmm0, xmm0
0x18007d3b3  mov     qword ptr [rbp+57h+te.tpDeltaPri], rsi
0x18007d3b7  lea     rdx, [rbp+57h+te]; lpte
0x18007d3bb  mov     [rbp+57h+te.dwSize], 1Ch
0x18007d3c2  mov     rcx, rbx; hSnapshot
0x18007d3c5  movdqu  xmmword ptr [rbp+57h+te.cntUsage], xmm0
0x18007d3ca  call    cs:__imp_Thread32First
0x18007d3d1  nop     dword ptr [rax+rax+00h]
0x18007d3d6  test    eax, eax
0x18007d3d8  jnz     short loc_18007D419
0x18007d3da  call    cs:__imp_GetLastError
0x18007d3e1  nop     dword ptr [rax+rax+00h]
0x18007d3e6  mov     ebx, eax
0x18007d3e8  test    eax, eax
0x18007d3ea  jle     short loc_18007D3F5
0x18007d3ec  movzx   ebx, ax
0x18007d3ef  or      ebx, 80070000h
0x18007d3f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d3fc  cmp     rcx, rdi
0x18007d3ff  jz      loc_18007D7D8
0x18007d405  test    byte ptr [rcx+1Ch], 1
0x18007d409  jz      loc_18007D7D8
0x18007d40f  mov     edx, 39h ; '9'
0x18007d414  jmp     loc_18007D7C5
0x18007d419  lea     rcx, [rbp+57h+lpBuffer]
0x18007d41d  call    ??$make_unique@U_TEB@@$$V$0A@@utl@@YA?AV?$unique_ptr@U_TEB@@U?$default_delete@U_TEB@@@utl@@@0@XZ; utl::make_unique<_TEB,,0>(void)
0x18007d422  mov     rdi, [rbp+57h+lpBuffer]
0x18007d426  test    rdi, rdi
0x18007d429  jz      loc_18007D752
0x18007d42f  cmp     [rbp+57h+te.th32OwnerProcessID], r15d
0x18007d433  jnz     loc_18007D6D2
0x18007d439  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d440  lea     rax, WPP_GLOBAL_Control
0x18007d447  cmp     rcx, rax
0x18007d44a  jz      short loc_18007D46B
0x18007d44c  test    byte ptr [rcx+1Ch], 4
0x18007d450  jz      short loc_18007D46B
0x18007d452  mov     r9d, [rbp+57h+te.th32ThreadID]
0x18007d456  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18007d45d  mov     rcx, [rcx+10h]
0x18007d461  mov     edx, 3Bh ; ';'
0x18007d466  call    WPP_SF_d
0x18007d46b  mov     r8d, [rbp+57h+te.th32ThreadID]; dwThreadId
0x18007d46f  xorps   xmm0, xmm0
0x18007d472  xor     edx, edx; bInheritHandle
0x18007d474  movups  [rbp+57h+ThreadInformation], xmm0
0x18007d478  movups  [rbp+57h+var_68], xmm0
0x18007d47c  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18007d47f  movups  [rbp+57h+var_58], xmm0
0x18007d483  call    cs:__imp_OpenThread
0x18007d48a  nop     dword ptr [rax+rax+00h]
0x18007d48f  mov     [rbp+57h+var_A0], rax
0x18007d493  lea     rcx, [rax+1]
0x18007d497  cmp     rcx, 1
0x18007d49b  jbe     loc_18007D676
0x18007d4a1  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18007d4a7  mov     [rsp+0D0h+ReturnLength], 0; ReturnLength
0x18007d4b0  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18007d4b4  xor     edx, edx; ThreadInformationClass
0x18007d4b6  mov     rcx, rax; ThreadHandle
0x18007d4b9  call    cs:__imp_NtQueryInformationThread
0x18007d4c0  nop     dword ptr [rax+rax+00h]
0x18007d4c5  test    eax, eax
0x18007d4c7  jns     short loc_18007D4FA
0x18007d4c9  mov     esi, eax
0x18007d4cb  bts     esi, 1Ch
0x18007d4cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d4d6  lea     rax, WPP_GLOBAL_Control
0x18007d4dd  cmp     rcx, rax
0x18007d4e0  jz      loc_18007D6C9
0x18007d4e6  test    byte ptr [rcx+1Ch], 2
0x18007d4ea  jz      loc_18007D6C9
0x18007d4f0  mov     edx, 3Dh ; '='
0x18007d4f5  jmp     loc_18007D6AF
0x18007d4fa  mov     rdx, qword ptr [rbp+57h+ThreadInformation+8]; lpBaseAddress
0x18007d4fe  test    rdx, rdx
0x18007d501  jnz     short loc_18007D547
0x18007d503  mov     esi, 80004005h
0x18007d508  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d50f  lea     rax, WPP_GLOBAL_Control
0x18007d516  cmp     rcx, rax
0x18007d519  jz      loc_18007D6C9
0x18007d51f  test    byte ptr [rcx+1Ch], 1
0x18007d523  jz      loc_18007D6C9
0x18007d529  mov     r9d, [rbp+57h+te.th32ThreadID]
0x18007d52d  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18007d534  mov     rcx, [rcx+10h]
0x18007d538  mov     edx, 3Eh ; '>'
0x18007d53d  call    WPP_SF_d
0x18007d542  jmp     loc_18007D6C9
0x18007d547  mov     r9d, 1870h; nSize
0x18007d54d  mov     [rsp+0D0h+ReturnLength], 0; lpNumberOfBytesRead
0x18007d556  mov     r8, rdi; lpBuffer
0x18007d559  mov     rcx, r12; hProcess
0x18007d55c  call    cs:__imp_ReadProcessMemory
0x18007d563  nop     dword ptr [rax+rax+00h]
0x18007d568  xor     ecx, ecx
0x18007d56a  test    eax, eax
0x18007d56c  jnz     short loc_18007D5B4
0x18007d56e  call    cs:__imp_GetLastError
0x18007d575  nop     dword ptr [rax+rax+00h]
0x18007d57a  mov     esi, eax
0x18007d57c  test    eax, eax
0x18007d57e  jle     short loc_18007D589
0x18007d580  movzx   esi, ax
0x18007d583  or      esi, 80070000h
0x18007d589  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d590  lea     rax, WPP_GLOBAL_Control
0x18007d597  cmp     rcx, rax
0x18007d59a  jz      loc_18007D6C9
0x18007d5a0  test    byte ptr [rcx+1Ch], 2
0x18007d5a4  jz      loc_18007D6C9
0x18007d5aa  mov     edx, 3Fh ; '?'
0x18007d5af  jmp     loc_18007D6AF
0x18007d5b4  cmp     [rdi+78h], rcx
0x18007d5b8  jz      loc_18007D6C9
0x18007d5be  mov     rdx, qword ptr [rbp+57h+ThreadInformation+8]
0x18007d5c2  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18007d5c6  mov     [rbp+57h+Buffer], rcx
0x18007d5ca  add     rdx, 860h; lpBaseAddress
0x18007d5d1  mov     [rsp+0D0h+ReturnLength], rcx; lpNumberOfBytesRead
0x18007d5d6  mov     r9d, 8; nSize
0x18007d5dc  mov     rcx, r12; hProcess
0x18007d5df  call    cs:__imp_ReadProcessMemory
0x18007d5e6  nop     dword ptr [rax+rax+00h]
0x18007d5eb  test    eax, eax
0x18007d5ed  jnz     short loc_18007D632
0x18007d5ef  call    cs:__imp_GetLastError
0x18007d5f6  nop     dword ptr [rax+rax+00h]
0x18007d5fb  mov     esi, eax
0x18007d5fd  test    eax, eax
0x18007d5ff  jle     short loc_18007D60A
0x18007d601  movzx   esi, ax
0x18007d604  or      esi, 80070000h
0x18007d60a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d611  lea     rax, WPP_GLOBAL_Control
0x18007d618  cmp     rcx, rax
0x18007d61b  jz      loc_18007D6C9
0x18007d621  test    byte ptr [rcx+1Ch], 2
0x18007d625  jz      loc_18007D6C9
0x18007d62b  mov     edx, 40h ; '@'
0x18007d630  jmp     short loc_18007D6AF
0x18007d632  mov     r8, [rbp+57h+Buffer]; unsigned __int64
0x18007d636  mov     r9d, 30h ; '0'; unsigned int
0x18007d63c  mov     rcx, [r13+8]; this
0x18007d640  mov     edx, r15d; unsigned int
0x18007d643  mov     dword ptr [rsp+0D0h+ReturnLength], 0; unsigned int
0x18007d64b  call    ?AddMemBlock@CReport@@QEAAJK_KKK@Z; CReport::AddMemBlock(ulong,unsigned __int64,ulong,ulong)
0x18007d650  mov     esi, eax
0x18007d652  test    eax, eax
0x18007d654  jns     short loc_18007D6C9
0x18007d656  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d65d  lea     rax, WPP_GLOBAL_Control
0x18007d664  cmp     rcx, rax
0x18007d667  jz      short loc_18007D6C9
0x18007d669  test    byte ptr [rcx+1Ch], 1
0x18007d66d  jz      short loc_18007D6C9
0x18007d66f  mov     edx, 41h ; 'A'
0x18007d674  jmp     short loc_18007D6AF
0x18007d676  call    cs:__imp_GetLastError
0x18007d67d  nop     dword ptr [rax+rax+00h]
0x18007d682  mov     esi, eax
0x18007d684  test    eax, eax
0x18007d686  jle     short loc_18007D691
0x18007d688  movzx   esi, ax
0x18007d68b  or      esi, 80070000h
0x18007d691  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d698  lea     rax, WPP_GLOBAL_Control
0x18007d69f  cmp     rcx, rax
0x18007d6a2  jz      short loc_18007D6C9
0x18007d6a4  test    byte ptr [rcx+1Ch], 2
0x18007d6a8  jz      short loc_18007D6C9
0x18007d6aa  mov     edx, 3Ch ; '<'
0x18007d6af  mov     eax, [rbp+57h+te.th32ThreadID]
0x18007d6b2  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18007d6b9  mov     rcx, [rcx+10h]
0x18007d6bd  mov     r9d, esi
0x18007d6c0  mov     dword ptr [rsp+0D0h+ReturnLength], eax
0x18007d6c4  call    WPP_SF_Dd
0x18007d6c9  lea     rcx, [rbp+57h+var_A0]
0x18007d6cd  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18007d6d2  lea     rdx, [rbp+57h+te]; lpte
0x18007d6d6  mov     rcx, rbx; hSnapshot
0x18007d6d9  call    cs:__imp_Thread32Next
0x18007d6e0  nop     dword ptr [rax+rax+00h]
0x18007d6e5  test    eax, eax
0x18007d6e7  jnz     loc_18007D42F
0x18007d6ed  call    cs:__imp_GetLastError
0x18007d6f4  nop     dword ptr [rax+rax+00h]
0x18007d6f9  cmp     eax, 12h
0x18007d6fc  jz      short loc_18007D739
0x18007d6fe  call    cs:__imp_GetLastError
0x18007d705  nop     dword ptr [rax+rax+00h]
0x18007d70a  mov     ebx, eax
0x18007d70c  test    eax, eax
0x18007d70e  jle     short loc_18007D719
0x18007d710  movzx   ebx, ax
0x18007d713  or      ebx, 80070000h
0x18007d719  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d720  lea     rax, WPP_GLOBAL_Control
0x18007d727  cmp     rcx, rax
0x18007d72a  jz      short loc_18007D788
0x18007d72c  test    byte ptr [rcx+1Ch], 1
0x18007d730  jz      short loc_18007D788
0x18007d732  mov     edx, 42h ; 'B'
0x18007d737  jmp     short loc_18007D775
0x18007d739  lea     rcx, [rbp+57h+lpBuffer]
0x18007d73d  call    ??1?$unique_ptr@U_TEB@@U?$default_delete@U_TEB@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<_TEB,utl::default_delete<_TEB>>::~unique_ptr<_TEB,utl::default_delete<_TEB>>(void)
0x18007d742  lea     rcx, [rbp+57h+var_88]
0x18007d746  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18007d74b  mov     eax, esi
0x18007d74d  jmp     loc_18007D7E3
0x18007d752  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d759  lea     rax, WPP_GLOBAL_Control
0x18007d760  mov     ebx, 8007000Eh
0x18007d765  cmp     rcx, rax
0x18007d768  jz      short loc_18007D788
0x18007d76a  test    byte ptr [rcx+1Ch], 1
0x18007d76e  jz      short loc_18007D788
0x18007d770  mov     edx, 3Ah ; ':'
0x18007d775  mov     rcx, [rcx+10h]
0x18007d779  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
  ... truncated ...
```
