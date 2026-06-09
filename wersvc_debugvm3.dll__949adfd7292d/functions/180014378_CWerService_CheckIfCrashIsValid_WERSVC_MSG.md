# CWerService::CheckIfCrashIsValid(_WERSVC_MSG *)

- ea: `0x180014378`
- end: `0x18001492b`
- name: `?CheckIfCrashIsValid@CWerService@@AEAAJPEAU_WERSVC_MSG@@@Z`
- size: `1459`
- prototype: `__int64 __fastcall(CWerService *__hidden this, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180019d10`

## callees

- `0x1800029f4`
- `0x1800035e8`
- `0x180007cf8`
- `0x180011ef8`
- `0x180013df4`
- `0x180014378`
- `0x180014934`
- `0x180014ea4`
- `0x18001e5d0`
- `0x18002cb24`
- `0x18002fbb0`
- `0x18002fda8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014520`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014520`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001480f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001480f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014491`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800148e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800148f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014910`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014491`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800148e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800148f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014910`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001454b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001454b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800148d0`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800148d0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800145af`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800145af`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800144a8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800146a6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800144a8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800146a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWerService::CheckIfCrashIsValid(CWerService *this, struct _WERSVC_MSG *a2)
{
  char *v4; // r13
  char *v5; // rsi
  enum _PS_PROTECTED_SIGNER *v6; // r8
  signed int ProtectedProcessInfoByPid; // ebx
  DWORD v8; // r15d
  DWORD v9; // esi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // ebx
  signed int LastError; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  HANDLE *v19; // rbx
  HANDLE CurrentProcess; // rax
  signed int v21; // eax
  const void *v22; // rax
  signed int v23; // eax
  __int64 v24; // r8
  __int64 v25; // r9
  signed int v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  WCHAR *v29; // rcx
  LPCWCH v30; // r8
  __int16 v31; // [rsp+50h] [rbp-B0h]
  LPCWCH lpString2; // [rsp+60h] [rbp-A0h]
  _WORD *v33; // [rsp+68h] [rbp-98h]
  _WORD v34[8]; // [rsp+70h] [rbp-90h] BYREF
  LPCVOID lpBaseAddress; // [rsp+80h] [rbp-80h]
  char *v36; // [rsp+88h] [rbp-78h]
  _BYTE v37[4]; // [rsp+90h] [rbp-70h] BYREF
  int v38; // [rsp+94h] [rbp-6Ch]
  unsigned int v39; // [rsp+1D8h] [rbp+D8h] BYREF
  char *v40; // [rsp+1E0h] [rbp+E0h]
  HANDLE hObject; // [rsp+1E8h] [rbp+E8h] BYREF

  hObject = 0;
  v4 = 0;
  v36 = 0;
  v5 = 0;
  v40 = 0;
  lpBaseAddress = 0;
  memset_0(v37, 0, 0xF8u);
  if ( *((__int64 *)a2 + 7) <= 0 )
  {
    ProtectedProcessInfoByPid = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_id(*((_QWORD *)WPP_GLOBAL_Control + 2));
    goto LABEL_76;
  }
  v8 = *((_DWORD *)a2 + 2);
  v9 = *((_DWORD *)a2 + 13);
  if ( v8 != v9 )
    goto LABEL_17;
  v39 = 0;
  ProtectedProcessInfoByPid = UtilGetProtectedProcessInfoByPid(v9, (enum _PS_PROTECTED_TYPE *)&v39, v6);
  if ( ProtectedProcessInfoByPid < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
        (unsigned int)ProtectedProcessInfoByPid);
    goto LABEL_10;
  }
  v14 = v39;
  if ( v39 > 2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12, v13);
  if ( v14 <= 0 )
  {
LABEL_17:
    v4 = (char *)OpenProcess(0x450u, 0, v8);
    v36 = v4;
    if ( v4 == (char *)-1LL || v4 + 1 == (char *)1 )
    {
      LastError = GetLastError();
      ProtectedProcessInfoByPid = LastError;
      if ( LastError > 0 )
        ProtectedProcessInfoByPid = (unsigned __int16)LastError | 0x80070000;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_10;
      v18 = 21;
      goto LABEL_23;
    }
    v19 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&hObject);
    CurrentProcess = GetCurrentProcess();
    if ( !DuplicateHandle(v4, *((HANDLE *)a2 + 7), CurrentProcess, v19, 0, 0, 2u) )
    {
      v21 = GetLastError();
      ProtectedProcessInfoByPid = v21;
      if ( v21 > 0 )
        ProtectedProcessInfoByPid = (unsigned __int16)v21 | 0x80070000;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_10;
      v18 = 22;
      goto LABEL_23;
    }
    v22 = MapViewOfFile(hObject, 4u, 0, 0, 0);
    lpBaseAddress = v22;
    if ( !v22 )
    {
      v23 = GetLastError();
      ProtectedProcessInfoByPid = v23;
      if ( v23 > 0 )
        ProtectedProcessInfoByPid = (unsigned __int16)v23 | 0x80070000;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_10;
      v18 = 23;
LABEL_23:
      WPP_SF_d(v17[2], v18, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, (unsigned int)ProtectedProcessInfoByPid);
LABEL_10:
      v5 = v40;
LABEL_76:
      if ( lpBaseAddress )
        UnmapViewOfFile(lpBaseAddress);
      if ( (unsigned __int64)(v5 + 1) > 1 )
        CloseHandle(v5);
      if ( (unsigned __int64)(v4 + 1) > 1 )
        CloseHandle(v4);
      if ( (unsigned __int64)hObject + 1 > 1 )
        CloseHandle(hObject);
      return (unsigned int)ProtectedProcessInfoByPid;
    }
    ProtectedProcessInfoByPid = CopyCrashSharedData(
                                  (struct _CRASH_SHARED_DATA *)v37,
                                  (const struct _CRASH_SHARED_DATA *)v22);
    if ( ProtectedProcessInfoByPid < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_10;
      v18 = 24;
      goto LABEL_23;
    }
    if ( v38 != v9 )
    {
      ProtectedProcessInfoByPid = -2147024809;
      goto LABEL_10;
    }
    if ( v8 == v9 || !(unsigned int)CWerService::CheckIfSystemConnectingToPort(this, a2, v24, v25) )
    {
      v5 = v40;
    }
    else
    {
      v31 = 0;
      lpString2 = v34;
      v33 = v34;
      v34[0] = 0;
      v5 = (char *)OpenProcess(0x450u, 0, v9);
      if ( v5 == (char *)-1LL || v5 + 1 == (char *)1 )
      {
        v26 = GetLastError();
        ProtectedProcessInfoByPid = v26;
        if ( v26 > 0 )
          ProtectedProcessInfoByPid = (unsigned __int16)v26 | 0x80070000;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v28 = 25;
LABEL_50:
          WPP_SF_d(
            v27[2],
            v28,
            WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
            (unsigned int)ProtectedProcessInfoByPid);
          goto LABEL_51;
        }
        goto LABEL_51;
      }
      if ( !(unsigned int)PackageUtility::IsPackagedApplication(v4)
        || !(unsigned int)PackageUtility::IsPackagedApplication(v5) )
      {
        ProtectedProcessInfoByPid = -2147024809;
        goto LABEL_51;
      }
      ProtectedProcessInfoByPid = PackageUtility::GetProcessPackageFullName(v4);
      if ( ProtectedProcessInfoByPid < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v28 = 26;
          goto LABEL_50;
        }
LABEL_51:
        v29 = (WCHAR *)lpString2;
        if ( lpString2 == v34 )
          goto LABEL_76;
LABEL_52:
        operator delete(v29, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_76;
      }
      ProtectedProcessInfoByPid = PackageUtility::GetProcessPackageFullName(v5);
      if ( ProtectedProcessInfoByPid < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v28 = 27;
          goto LABEL_50;
        }
        goto LABEL_51;
      }
      v30 = lpString2;
      if ( v33 - lpString2 )
      {
        ProtectedProcessInfoByPid = -2147024809;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
            2147942487LL);
          v30 = lpString2;
        }
        if ( v30 == v34 )
          goto LABEL_76;
        v29 = (WCHAR *)v30;
        goto LABEL_52;
      }
      if ( lpString2 != v34 )
        operator delete((void *)lpString2, (const struct std::nothrow_t *)&std::nothrow);
    }
    ProtectedProcessInfoByPid = 0;
    goto LABEL_76;
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x180014378  push    rbp
0x18001437a  push    rbx
0x18001437b  push    rsi
0x18001437c  push    r12
0x18001437e  push    r13
0x180014380  push    r14
0x180014382  push    r15
0x180014384  lea     rbp, [rsp-90h]
0x18001438c  sub     rsp, 190h
0x180014393  mov     r14, rdx
0x180014396  mov     r12, rcx
0x180014399  xor     ebx, ebx
0x18001439b  mov     [rbp+0C0h+hObject], rbx
0x1800143a2  mov     r13d, ebx
0x1800143a5  mov     [rbp+0C0h+var_138], rbx
0x1800143a9  mov     esi, ebx
0x1800143ab  mov     [rbp+0C0h+arg_10], rbx
0x1800143b2  mov     [rbp+0C0h+lpBaseAddress], rbx
0x1800143b6  xor     edx, edx; Val
0x1800143b8  mov     r8d, 0F8h; Size
0x1800143be  lea     rcx, [rbp+0C0h+var_130]; void *
0x1800143c2  call    memset_0
0x1800143c7  mov     r9, [r14+38h]
0x1800143cb  test    r9, r9
0x1800143ce  jg      short loc_180014404
0x1800143d0  mov     ebx, 80070057h
0x1800143d5  lea     rax, WPP_GLOBAL_Control
0x1800143dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143e3  cmp     rcx, rax
0x1800143e6  jz      loc_1800148C7
0x1800143ec  test    byte ptr [rcx+1Ch], 2
0x1800143f0  jz      loc_1800148C7
0x1800143f6  mov     rcx, [rcx+10h]
0x1800143fa  call    WPP_SF_id
0x1800143ff  jmp     loc_1800148C7
0x180014404  mov     r15d, [r14+8]
0x180014408  mov     esi, [r14+34h]
0x18001440c  cmp     r15d, esi
0x18001440f  jnz     loc_18001449E
0x180014415  mov     [rbp+0C0h+arg_8], ebx
0x18001441b  lea     rdx, [rbp+0C0h+arg_8]; enum _PS_PROTECTED_TYPE *
0x180014422  mov     ecx, esi; dwProcessId
0x180014424  call    ?UtilGetProtectedProcessInfoByPid@@YAJKPEAW4_PS_PROTECTED_TYPE@@PEAW4_PS_PROTECTED_SIGNER@@@Z; UtilGetProtectedProcessInfoByPid(ulong,_PS_PROTECTED_TYPE *,_PS_PROTECTED_SIGNER *)
0x180014429  mov     ebx, eax
0x18001442b  test    eax, eax
0x18001442d  jns     short loc_18001446C
0x18001442f  lea     rax, WPP_GLOBAL_Control
0x180014436  mov     rcx, cs:WPP_GLOBAL_Control
0x18001443d  cmp     rcx, rax
0x180014440  jz      short loc_180014460
0x180014442  test    byte ptr [rcx+1Ch], 1
0x180014446  jz      short loc_180014460
0x180014448  mov     edx, 14h
0x18001444d  mov     r9d, ebx
0x180014450  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180014457  mov     rcx, [rcx+10h]
0x18001445b  call    WPP_SF_d
0x180014460  mov     rsi, [rbp+0C0h+arg_10]
0x180014467  jmp     loc_1800148C7
0x18001446c  mov     ebx, [rbp+0C0h+arg_8]
0x180014472  cmp     ebx, 2
0x180014475  jbe     short loc_18001447C
0x180014477  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001447c  test    ebx, ebx
0x18001447e  jle     short loc_18001449E
0x180014480  mov     rcx, [rbp+0C0h+hObject]; hObject
0x180014487  lea     rax, [rcx+1]
0x18001448b  cmp     rax, 1
0x18001448f  jbe     short loc_180014497
0x180014491  call    cs:__imp_CloseHandle
0x180014497  xor     eax, eax
0x180014499  jmp     loc_180014918
0x18001449e  mov     r8d, r15d; dwProcessId
0x1800144a1  xor     edx, edx; bInheritHandle
0x1800144a3  mov     ecx, 450h; dwDesiredAccess
0x1800144a8  call    cs:__imp_OpenProcess
0x1800144ae  mov     r13, rax
0x1800144b1  mov     [rbp+0C0h+var_138], rax
0x1800144b5  inc     rax
0x1800144b8  cmp     rax, 1
0x1800144bc  ja      short loc_180014511
0x1800144be  call    cs:__imp_GetLastError
0x1800144c4  mov     ebx, eax
0x1800144c6  test    eax, eax
0x1800144c8  jle     short loc_1800144D3
0x1800144ca  movzx   ebx, ax
0x1800144cd  or      ebx, 80070000h
0x1800144d3  lea     rax, WPP_GLOBAL_Control
0x1800144da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144e1  cmp     rcx, rax
0x1800144e4  jz      loc_180014460
0x1800144ea  test    byte ptr [rcx+1Ch], 2
0x1800144ee  jz      loc_180014460
0x1800144f4  mov     edx, 15h
0x1800144f9  mov     r9d, ebx
0x1800144fc  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180014503  mov     rcx, [rcx+10h]
0x180014507  call    WPP_SF_d
0x18001450c  jmp     loc_180014460
0x180014511  lea     rcx, [rbp+0C0h+hObject]
0x180014518  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18001451d  mov     rbx, rax
0x180014520  call    cs:__imp_GetCurrentProcess
0x180014526  mov     [rsp+1C0h+dwOptions], 2; dwOptions
0x18001452e  mov     [rsp+1C0h+bInheritHandle], 0; bInheritHandle
0x180014536  mov     [rsp+1C0h+dwDesiredAccess], 0; dwDesiredAccess
0x18001453e  mov     r9, rbx; lpTargetHandle
0x180014541  mov     r8, rax; hTargetProcessHandle
0x180014544  mov     rdx, [r14+38h]; hSourceHandle
0x180014548  mov     rcx, r13; hSourceProcessHandle
0x18001454b  call    cs:__imp_DuplicateHandle
0x180014551  test    eax, eax
0x180014553  jnz     short loc_180014595
0x180014555  call    cs:__imp_GetLastError
0x18001455b  mov     ebx, eax
0x18001455d  test    eax, eax
0x18001455f  jle     short loc_18001456A
0x180014561  movzx   ebx, ax
0x180014564  or      ebx, 80070000h
0x18001456a  lea     rax, WPP_GLOBAL_Control
0x180014571  mov     rcx, cs:WPP_GLOBAL_Control
0x180014578  cmp     rcx, rax
0x18001457b  jz      loc_180014460
0x180014581  test    byte ptr [rcx+1Ch], 2
0x180014585  jz      loc_180014460
0x18001458b  mov     edx, 16h
0x180014590  jmp     loc_1800144F9
0x180014595  mov     qword ptr [rsp+1C0h+dwDesiredAccess], 0; dwNumberOfBytesToMap
0x18001459e  xor     r9d, r9d; dwFileOffsetLow
0x1800145a1  xor     r8d, r8d; dwFileOffsetHigh
0x1800145a4  lea     edx, [r9+4]; dwDesiredAccess
0x1800145a8  mov     rcx, [rbp+0C0h+hObject]; hFileMappingObject
0x1800145af  call    cs:__imp_MapViewOfFile
0x1800145b5  mov     [rbp+0C0h+lpBaseAddress], rax
0x1800145b9  test    rax, rax
0x1800145bc  jnz     short loc_1800145FE
0x1800145be  call    cs:__imp_GetLastError
0x1800145c4  mov     ebx, eax
0x1800145c6  test    eax, eax
0x1800145c8  jle     short loc_1800145D3
0x1800145ca  movzx   ebx, ax
0x1800145cd  or      ebx, 80070000h
0x1800145d3  lea     rax, WPP_GLOBAL_Control
0x1800145da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145e1  cmp     rcx, rax
0x1800145e4  jz      loc_180014460
0x1800145ea  test    byte ptr [rcx+1Ch], 2
0x1800145ee  jz      loc_180014460
0x1800145f4  mov     edx, 17h
0x1800145f9  jmp     loc_1800144F9
0x1800145fe  mov     rdx, rax; struct _CRASH_SHARED_DATA *
0x180014601  lea     rcx, [rbp+0C0h+var_130]; struct _CRASH_SHARED_DATA *
0x180014605  call    ?CopyCrashSharedData@@YAJPEAU_CRASH_SHARED_DATA@@PEBU1@@Z; CopyCrashSharedData(_CRASH_SHARED_DATA *,_CRASH_SHARED_DATA const *)
0x18001460a  mov     ebx, eax
0x18001460c  test    eax, eax
0x18001460e  jns     short loc_18001463B
0x180014610  lea     rax, WPP_GLOBAL_Control
0x180014617  mov     rcx, cs:WPP_GLOBAL_Control
0x18001461e  cmp     rcx, rax
0x180014621  jz      loc_180014460
0x180014627  test    byte ptr [rcx+1Ch], 1
0x18001462b  jz      loc_180014460
0x180014631  mov     edx, 18h
0x180014636  jmp     loc_1800144F9
0x18001463b  cmp     [rbp+0C0h+var_12C], esi
0x18001463e  jz      short loc_18001464A
0x180014640  mov     ebx, 80070057h
0x180014645  jmp     loc_180014460
0x18001464a  cmp     r15d, esi
0x18001464d  jz      loc_1800148BE
0x180014653  mov     rdx, r14; struct _WERSVC_MSG *
0x180014656  mov     rcx, r12; this
0x180014659  call    ?CheckIfSystemConnectingToPort@CWerService@@AEAAJPEAU_WERSVC_MSG@@@Z; CWerService::CheckIfSystemConnectingToPort(_WERSVC_MSG *)
0x18001465e  test    eax, eax
0x180014660  jz      loc_1800148BE
0x180014666  lea     rax, [rsp+1C0h+var_170]
0x18001466b  mov     [rsp+1C0h+lpString1], rax
0x180014670  lea     rax, [rsp+1C0h+var_170]
0x180014675  mov     [rsp+1C0h+var_178], rax
0x18001467a  xor     eax, eax
0x18001467c  mov     [rsp+1C0h+var_170], ax
0x180014681  lea     rax, [rsp+1C0h+var_150]
0x180014686  mov     [rsp+1C0h+lpString2], rax
0x18001468b  lea     rax, [rsp+1C0h+var_150]
0x180014690  mov     [rsp+1C0h+var_158], rax
0x180014695  xor     eax, eax
0x180014697  mov     [rsp+1C0h+var_150], ax
0x18001469c  mov     r8d, esi; dwProcessId
0x18001469f  xor     edx, edx; bInheritHandle
0x1800146a1  mov     ecx, 450h; dwDesiredAccess
0x1800146a6  call    cs:__imp_OpenProcess
0x1800146ac  mov     rsi, rax
0x1800146af  inc     rax
0x1800146b2  cmp     rax, 1
0x1800146b6  ja      loc_180014741
0x1800146bc  call    cs:__imp_GetLastError
0x1800146c2  mov     ebx, eax
0x1800146c4  test    eax, eax
0x1800146c6  jle     short loc_1800146D1
0x1800146c8  movzx   ebx, ax
0x1800146cb  or      ebx, 80070000h
0x1800146d1  lea     rax, WPP_GLOBAL_Control
0x1800146d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146df  cmp     rcx, rax
0x1800146e2  jz      short loc_180014702
0x1800146e4  test    byte ptr [rcx+1Ch], 2
0x1800146e8  jz      short loc_180014702
0x1800146ea  mov     edx, 19h
0x1800146ef  mov     r9d, ebx
0x1800146f2  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x1800146f9  mov     rcx, [rcx+10h]
0x1800146fd  call    WPP_SF_d
0x180014702  lea     rax, [rsp+1C0h+var_150]
0x180014707  mov     rcx, [rsp+1C0h+lpString2]; void *
0x18001470c  cmp     rcx, rax
0x18001470f  jz      short loc_18001471D
0x180014711  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014718  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001471d  mov     rcx, [rsp+1C0h+lpString1]; void *
0x180014722  lea     rax, [rsp+1C0h+var_170]
0x180014727  cmp     rcx, rax
0x18001472a  jz      loc_1800148C7
0x180014730  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014737  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001473c  jmp     loc_1800148C7
0x180014741  mov     rcx, r13; hProcess
0x180014744  call    ?IsPackagedApplication@PackageUtility@@SAHPEAX@Z; PackageUtility::IsPackagedApplication(void *)
0x180014749  test    eax, eax
0x18001474b  jz      loc_1800148B4
0x180014751  mov     rcx, rsi; hProcess
0x180014754  call    ?IsPackagedApplication@PackageUtility@@SAHPEAX@Z; PackageUtility::IsPackagedApplication(void *)
0x180014759  test    eax, eax
0x18001475b  jz      loc_1800148B4
0x180014761  lea     rdx, [rsp+1C0h+lpString1]
0x180014766  mov     rcx, r13; hProcess
0x180014769  call    ?GetProcessPackageFullName@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PackageUtility::GetProcessPackageFullName(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001476e  mov     ebx, eax
0x180014770  test    eax, eax
0x180014772  jns     short loc_18001479F
0x180014774  lea     rax, WPP_GLOBAL_Control
0x18001477b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014782  cmp     rcx, rax
0x180014785  jz      loc_180014702
0x18001478b  test    byte ptr [rcx+1Ch], 2
0x18001478f  jz      loc_180014702
0x180014795  mov     edx, 1Ah
0x18001479a  jmp     loc_1800146EF
0x18001479f  lea     rdx, [rsp+1C0h+lpString2]
0x1800147a4  mov     rcx, rsi; hProcess
0x1800147a7  call    ?GetProcessPackageFullName@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PackageUtility::GetProcessPackageFullName(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800147ac  mov     ebx, eax
0x1800147ae  test    eax, eax
0x1800147b0  jns     short loc_1800147DD
0x1800147b2  lea     rax, WPP_GLOBAL_Control
0x1800147b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147c0  cmp     rcx, rax
0x1800147c3  jz      loc_180014702
0x1800147c9  test    byte ptr [rcx+1Ch], 2
0x1800147cd  jz      loc_180014702
0x1800147d3  mov     edx, 1Bh
0x1800147d8  jmp     loc_1800146EF
0x1800147dd  mov     r9, [rsp+1C0h+var_158]
0x1800147e2  mov     r8, [rsp+1C0h+lpString2]; lpString2
0x1800147e7  sub     r9, r8
0x1800147ea  sar     r9, 1; cchCount2
0x1800147ed  mov     rdx, [rsp+1C0h+var_178]
0x1800147f2  mov     rcx, [rsp+1C0h+lpString1]; lpString1
0x1800147f7  sub     rdx, rcx
0x1800147fa  sar     rdx, 1; cchCount1
0x1800147fd  cmp     rdx, r9
0x180014800  jnz     short loc_18001485A
0x180014802  test    rdx, rdx
0x180014805  jz      short loc_180014824
0x180014807  mov     [rsp+1C0h+dwDesiredAccess], 1; bIgnoreCase
0x18001480f  call    cs:__imp_CompareStringOrdinal
0x180014815  mov     rcx, [rsp+1C0h+lpString1]
0x18001481a  mov     r8, [rsp+1C0h+lpString2]
0x18001481f  cmp     eax, 2
0x180014822  jnz     short loc_18001485A
0x180014824  lea     rax, [rsp+1C0h+var_150]
0x180014829  cmp     r8, rax
0x18001482c  jz      short loc_180014842
0x18001482e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014835  mov     rcx, r8; void *
0x180014838  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001483d  mov     rcx, [rsp+1C0h+lpString1]; void *
0x180014842  lea     rax, [rsp+1C0h+var_170]
0x180014847  cmp     rcx, rax
0x18001484a  jz      short loc_1800148C5
0x18001484c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014853  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014858  jmp     short loc_1800148C5
0x18001485a  mov     ebx, 80070057h
0x18001485f  lea     rax, WPP_GLOBAL_Control
0x180014866  mov     r10, cs:WPP_GLOBAL_Control
0x18001486d  cmp     r10, rax
0x180014870  jz      short loc_18001489E
0x180014872  test    byte ptr [r10+1Ch], 2
0x180014877  jz      short loc_18001489E
0x180014879  mov     edx, 1Ch
  ... truncated ...
```
