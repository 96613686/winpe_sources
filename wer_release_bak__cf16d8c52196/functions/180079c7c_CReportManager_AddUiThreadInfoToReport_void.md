# CReportManager::AddUiThreadInfoToReport(void)

- ea: `0x180079c7c`
- end: `0x18007a1c1`
- name: `?AddUiThreadInfoToReport@CReportManager@@AEAAJXZ`
- size: `1349`
- prototype: `__int64 __fastcall(CReportManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180079198`

## callees

- `0x180004bb4`
- `0x180007e10`
- `0x18001fe24`
- `0x18002c220`
- `0x180050db0`
- `0x180070908`
- `0x180078694`
- `0x180078fd4`
- `0x180079c7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180079e7b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180079e7b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180079cc4`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180079d80`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180079cc4`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180079d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079dd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079fc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a04a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a0b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a0c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a14f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079dd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079fc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a04a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a0b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a0c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a14f`
- `ntdll!NtQueryInformationThread` at `0x180079eab`
- `ntdll!NtQueryInformationThread` at `0x180079eab`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180079f48`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180079fbf`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180079f48`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180079fbf`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180079d2e`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180079d2e`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180079d9a`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180079d9a`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x180079dce`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x180079dce`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x18007a0a7`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x18007a0a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
    v7 = *((_QWORD *)this + 1);
    Process = 0;
    v8 = PssQuerySnapshot(*(_QWORD *)(v7 + 9112), 1, &Process, 8);
    v9 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v9);
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
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v9);
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
      WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v9);
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
        WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
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
        WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
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
          WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
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
0x180079c7c  mov     [rsp-8+arg_8], rbx
0x180079c81  mov     [rsp-8+arg_10], rsi
0x180079c86  push    rbp
0x180079c87  push    rdi
0x180079c88  push    r12
0x180079c8a  push    r13
0x180079c8c  push    r15
0x180079c8e  lea     rbp, [rsp-37h]
0x180079c93  sub     rsp, 0B0h
0x180079c9a  mov     rax, cs:__security_cookie
0x180079ca1  xor     rax, rsp
0x180079ca4  mov     [rbp+57h+var_28], rax
0x180079ca8  mov     rax, [rcx+8]
0x180079cac  lea     rdi, WPP_GLOBAL_Control
0x180079cb3  mov     r13, rcx
0x180079cb6  xor     esi, esi
0x180079cb8  mov     rcx, [rax+19F0h]; Process
0x180079cbf  test    rcx, rcx
0x180079cc2  jz      short loc_180079CDD
0x180079cc4  call    cs:__imp_GetProcessId
0x180079cca  mov     rcx, [r13+8]
0x180079cce  mov     r15d, eax
0x180079cd1  mov     r12, [rcx+19F0h]
0x180079cd8  jmp     loc_180079D95
0x180079cdd  cmp     [rax+2398h], rsi
0x180079ce4  jz      loc_180079D8F
0x180079cea  mov     rcx, cs:WPP_GLOBAL_Control
0x180079cf1  cmp     rcx, rdi
0x180079cf4  jz      short loc_180079D11
0x180079cf6  test    byte ptr [rcx+1Ch], 2
0x180079cfa  jz      short loc_180079D11
0x180079cfc  mov     rcx, [rcx+10h]
0x180079d00  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180079d07  mov     edx, 36h ; '6'
0x180079d0c  call    WPP_SF_
0x180079d11  mov     rcx, [r13+8]
0x180079d15  lea     r8, [rbp+57h+Process]
0x180079d19  mov     r9d, 8
0x180079d1f  mov     [rbp+57h+Process], rsi
0x180079d23  mov     rcx, [rcx+2398h]
0x180079d2a  lea     edx, [r9-7]
0x180079d2e  call    cs:__imp_PssQuerySnapshot
0x180079d34  mov     ebx, eax
0x180079d36  test    eax, eax
0x180079d38  jz      short loc_180079D7C
0x180079d3a  jle     short loc_180079D45
0x180079d3c  movzx   ebx, ax
0x180079d3f  or      ebx, 80070000h
0x180079d45  mov     rcx, cs:WPP_GLOBAL_Control
0x180079d4c  cmp     rcx, rdi
0x180079d4f  jz      loc_18007A197
0x180079d55  test    byte ptr [rcx+1Ch], 1
0x180079d59  jz      loc_18007A197
0x180079d5f  mov     rcx, [rcx+10h]
0x180079d63  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180079d6a  mov     edx, 37h ; '7'
0x180079d6f  mov     r9d, ebx
0x180079d72  call    WPP_SF_d
0x180079d77  jmp     loc_18007A197
0x180079d7c  mov     rcx, [rbp+57h+Process]; Process
0x180079d80  call    cs:__imp_GetProcessId
0x180079d86  mov     r12, [rbp+57h+Process]
0x180079d8a  mov     r15d, eax
0x180079d8d  jmp     short loc_180079D95
0x180079d8f  mov     r15d, esi
0x180079d92  mov     r12, rsi
0x180079d95  xor     edx, edx; th32ProcessID
0x180079d97  lea     ecx, [rdx+4]; dwFlags
0x180079d9a  call    cs:__imp_CreateToolhelp32Snapshot
0x180079da0  mov     rbx, rax
0x180079da3  mov     [rbp+57h+var_88], rax
0x180079da7  inc     rax
0x180079daa  cmp     rax, 1
0x180079dae  jbe     loc_18007A14F
0x180079db4  xorps   xmm0, xmm0
0x180079db7  mov     qword ptr [rbp+57h+te.tpDeltaPri], rsi
0x180079dbb  lea     rdx, [rbp+57h+te]; lpte
0x180079dbf  mov     [rbp+57h+te.dwSize], 1Ch
0x180079dc6  mov     rcx, rbx; hSnapshot
0x180079dc9  movdqu  xmmword ptr [rbp+57h+te.cntUsage], xmm0
0x180079dce  call    cs:__imp_Thread32First
0x180079dd4  test    eax, eax
0x180079dd6  jnz     short loc_180079E11
0x180079dd8  call    cs:__imp_GetLastError
0x180079dde  mov     ebx, eax
0x180079de0  test    eax, eax
0x180079de2  jle     short loc_180079DED
0x180079de4  movzx   ebx, ax
0x180079de7  or      ebx, 80070000h
0x180079ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180079df4  cmp     rcx, rdi
0x180079df7  jz      loc_18007A18E
0x180079dfd  test    byte ptr [rcx+1Ch], 1
0x180079e01  jz      loc_18007A18E
0x180079e07  mov     edx, 39h ; '9'
0x180079e0c  jmp     loc_18007A17B
0x180079e11  lea     rcx, [rbp+57h+lpBuffer]
0x180079e15  call    ??$make_unique@U_TEB@@$$V$0A@@utl@@YA?AV?$unique_ptr@U_TEB@@U?$default_delete@U_TEB@@@utl@@@0@XZ; utl::make_unique<_TEB,,0>(void)
0x180079e1a  mov     rdi, [rbp+57h+lpBuffer]
0x180079e1e  test    rdi, rdi
0x180079e21  jz      loc_18007A10E
0x180079e27  cmp     [rbp+57h+te.th32OwnerProcessID], r15d
0x180079e2b  jnz     loc_18007A0A0
0x180079e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180079e38  lea     rax, WPP_GLOBAL_Control
0x180079e3f  cmp     rcx, rax
0x180079e42  jz      short loc_180079E63
0x180079e44  test    byte ptr [rcx+1Ch], 4
0x180079e48  jz      short loc_180079E63
0x180079e4a  mov     r9d, [rbp+57h+te.th32ThreadID]
0x180079e4e  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180079e55  mov     rcx, [rcx+10h]
0x180079e59  mov     edx, 3Bh ; ';'
0x180079e5e  call    WPP_SF_d
0x180079e63  mov     r8d, [rbp+57h+te.th32ThreadID]; dwThreadId
0x180079e67  xorps   xmm0, xmm0
0x180079e6a  xor     edx, edx; bInheritHandle
0x180079e6c  movups  [rbp+57h+ThreadInformation], xmm0
0x180079e70  movups  [rbp+57h+var_68], xmm0
0x180079e74  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180079e77  movups  [rbp+57h+var_58], xmm0
0x180079e7b  call    cs:__imp_OpenThread
0x180079e81  mov     [rbp+57h+var_A0], rax
0x180079e85  lea     rcx, [rax+1]
0x180079e89  cmp     rcx, 1
0x180079e8d  jbe     loc_18007A04A
0x180079e93  mov     r9d, 30h ; '0'; ThreadInformationLength
0x180079e99  mov     [rsp+0D0h+ReturnLength], 0; ReturnLength
0x180079ea2  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x180079ea6  xor     edx, edx; ThreadInformationClass
0x180079ea8  mov     rcx, rax; ThreadHandle
0x180079eab  call    cs:__imp_NtQueryInformationThread
0x180079eb1  test    eax, eax
0x180079eb3  jns     short loc_180079EE6
0x180079eb5  mov     esi, eax
0x180079eb7  bts     esi, 1Ch
0x180079ebb  mov     rcx, cs:WPP_GLOBAL_Control
0x180079ec2  lea     rax, WPP_GLOBAL_Control
0x180079ec9  cmp     rcx, rax
0x180079ecc  jz      loc_18007A097
0x180079ed2  test    byte ptr [rcx+1Ch], 2
0x180079ed6  jz      loc_18007A097
0x180079edc  mov     edx, 3Dh ; '='
0x180079ee1  jmp     loc_18007A07D
0x180079ee6  mov     rdx, qword ptr [rbp+57h+ThreadInformation+8]; lpBaseAddress
0x180079eea  test    rdx, rdx
0x180079eed  jnz     short loc_180079F33
0x180079eef  mov     esi, 80004005h
0x180079ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x180079efb  lea     rax, WPP_GLOBAL_Control
0x180079f02  cmp     rcx, rax
0x180079f05  jz      loc_18007A097
0x180079f0b  test    byte ptr [rcx+1Ch], 1
0x180079f0f  jz      loc_18007A097
0x180079f15  mov     r9d, [rbp+57h+te.th32ThreadID]
0x180079f19  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180079f20  mov     rcx, [rcx+10h]
0x180079f24  mov     edx, 3Eh ; '>'
0x180079f29  call    WPP_SF_d
0x180079f2e  jmp     loc_18007A097
0x180079f33  mov     r9d, 1870h; nSize
0x180079f39  mov     [rsp+0D0h+ReturnLength], 0; lpNumberOfBytesRead
0x180079f42  mov     r8, rdi; lpBuffer
0x180079f45  mov     rcx, r12; hProcess
0x180079f48  call    cs:__imp_ReadProcessMemory
0x180079f4e  xor     ecx, ecx
0x180079f50  test    eax, eax
0x180079f52  jnz     short loc_180079F94
0x180079f54  call    cs:__imp_GetLastError
0x180079f5a  mov     esi, eax
0x180079f5c  test    eax, eax
0x180079f5e  jle     short loc_180079F69
0x180079f60  movzx   esi, ax
0x180079f63  or      esi, 80070000h
0x180079f69  mov     rcx, cs:WPP_GLOBAL_Control
0x180079f70  lea     rax, WPP_GLOBAL_Control
0x180079f77  cmp     rcx, rax
0x180079f7a  jz      loc_18007A097
0x180079f80  test    byte ptr [rcx+1Ch], 2
0x180079f84  jz      loc_18007A097
0x180079f8a  mov     edx, 3Fh ; '?'
0x180079f8f  jmp     loc_18007A07D
0x180079f94  cmp     [rdi+78h], rcx
0x180079f98  jz      loc_18007A097
0x180079f9e  mov     rdx, qword ptr [rbp+57h+ThreadInformation+8]
0x180079fa2  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180079fa6  mov     [rbp+57h+Buffer], rcx
0x180079faa  add     rdx, 860h; lpBaseAddress
0x180079fb1  mov     [rsp+0D0h+ReturnLength], rcx; lpNumberOfBytesRead
0x180079fb6  mov     r9d, 8; nSize
0x180079fbc  mov     rcx, r12; hProcess
0x180079fbf  call    cs:__imp_ReadProcessMemory
0x180079fc5  test    eax, eax
0x180079fc7  jnz     short loc_18007A006
0x180079fc9  call    cs:__imp_GetLastError
0x180079fcf  mov     esi, eax
0x180079fd1  test    eax, eax
0x180079fd3  jle     short loc_180079FDE
0x180079fd5  movzx   esi, ax
0x180079fd8  or      esi, 80070000h
0x180079fde  mov     rcx, cs:WPP_GLOBAL_Control
0x180079fe5  lea     rax, WPP_GLOBAL_Control
0x180079fec  cmp     rcx, rax
0x180079fef  jz      loc_18007A097
0x180079ff5  test    byte ptr [rcx+1Ch], 2
0x180079ff9  jz      loc_18007A097
0x180079fff  mov     edx, 40h ; '@'
0x18007a004  jmp     short loc_18007A07D
0x18007a006  mov     r8, [rbp+57h+Buffer]; unsigned __int64
0x18007a00a  mov     r9d, 30h ; '0'; unsigned int
0x18007a010  mov     rcx, [r13+8]; this
0x18007a014  mov     edx, r15d; unsigned int
0x18007a017  mov     dword ptr [rsp+0D0h+ReturnLength], 0; unsigned int
0x18007a01f  call    ?AddMemBlock@CReport@@QEAAJK_KKK@Z; CReport::AddMemBlock(ulong,unsigned __int64,ulong,ulong)
0x18007a024  mov     esi, eax
0x18007a026  test    eax, eax
0x18007a028  jns     short loc_18007A097
0x18007a02a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a031  lea     rax, WPP_GLOBAL_Control
0x18007a038  cmp     rcx, rax
0x18007a03b  jz      short loc_18007A097
0x18007a03d  test    byte ptr [rcx+1Ch], 1
0x18007a041  jz      short loc_18007A097
0x18007a043  mov     edx, 41h ; 'A'
0x18007a048  jmp     short loc_18007A07D
0x18007a04a  call    cs:__imp_GetLastError
0x18007a050  mov     esi, eax
0x18007a052  test    eax, eax
0x18007a054  jle     short loc_18007A05F
0x18007a056  movzx   esi, ax
0x18007a059  or      esi, 80070000h
0x18007a05f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a066  lea     rax, WPP_GLOBAL_Control
0x18007a06d  cmp     rcx, rax
0x18007a070  jz      short loc_18007A097
0x18007a072  test    byte ptr [rcx+1Ch], 2
0x18007a076  jz      short loc_18007A097
0x18007a078  mov     edx, 3Ch ; '<'
0x18007a07d  mov     eax, [rbp+57h+te.th32ThreadID]
0x18007a080  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18007a087  mov     rcx, [rcx+10h]
0x18007a08b  mov     r9d, esi
0x18007a08e  mov     dword ptr [rsp+0D0h+ReturnLength], eax
0x18007a092  call    WPP_SF_Dd
0x18007a097  lea     rcx, [rbp+57h+var_A0]
0x18007a09b  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18007a0a0  lea     rdx, [rbp+57h+te]; lpte
0x18007a0a4  mov     rcx, rbx; hSnapshot
0x18007a0a7  call    cs:__imp_Thread32Next
0x18007a0ad  test    eax, eax
0x18007a0af  jnz     loc_180079E27
0x18007a0b5  call    cs:__imp_GetLastError
0x18007a0bb  cmp     eax, 12h
0x18007a0be  jz      short loc_18007A0F5
0x18007a0c0  call    cs:__imp_GetLastError
0x18007a0c6  mov     ebx, eax
0x18007a0c8  test    eax, eax
0x18007a0ca  jle     short loc_18007A0D5
0x18007a0cc  movzx   ebx, ax
0x18007a0cf  or      ebx, 80070000h
0x18007a0d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a0dc  lea     rax, WPP_GLOBAL_Control
0x18007a0e3  cmp     rcx, rax
0x18007a0e6  jz      short loc_18007A144
0x18007a0e8  test    byte ptr [rcx+1Ch], 1
0x18007a0ec  jz      short loc_18007A144
0x18007a0ee  mov     edx, 42h ; 'B'
0x18007a0f3  jmp     short loc_18007A131
0x18007a0f5  lea     rcx, [rbp+57h+lpBuffer]
0x18007a0f9  call    ??1?$unique_ptr@U_TEB@@U?$default_delete@U_TEB@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<_TEB,utl::default_delete<_TEB>>::~unique_ptr<_TEB,utl::default_delete<_TEB>>(void)
0x18007a0fe  lea     rcx, [rbp+57h+var_88]
0x18007a102  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18007a107  mov     eax, esi
0x18007a109  jmp     loc_18007A199
0x18007a10e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a115  lea     rax, WPP_GLOBAL_Control
0x18007a11c  mov     ebx, 8007000Eh
0x18007a121  cmp     rcx, rax
0x18007a124  jz      short loc_18007A144
0x18007a126  test    byte ptr [rcx+1Ch], 1
0x18007a12a  jz      short loc_18007A144
0x18007a12c  mov     edx, 3Ah ; ':'
0x18007a131  mov     rcx, [rcx+10h]
0x18007a135  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18007a13c  mov     r9d, ebx
0x18007a13f  call    WPP_SF_d
0x18007a144  lea     rcx, [rbp+57h+lpBuffer]
0x18007a148  call    ??1?$unique_ptr@U_TEB@@U?$default_delete@U_TEB@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<_TEB,utl::default_delete<_TEB>>::~unique_ptr<_TEB,utl::default_delete<_TEB>>(void)
0x18007a14d  jmp     short loc_18007A18E
0x18007a14f  call    cs:__imp_GetLastError
0x18007a155  mov     ebx, eax
0x18007a157  test    eax, eax
0x18007a159  jle     short loc_18007A164
0x18007a15b  movzx   ebx, ax
0x18007a15e  or      ebx, 80070000h
0x18007a164  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a16b  cmp     rcx, rdi
0x18007a16e  jz      short loc_18007A18E
0x18007a170  test    byte ptr [rcx+1Ch], 1
0x18007a174  jz      short loc_18007A18E
  ... truncated ...
```
