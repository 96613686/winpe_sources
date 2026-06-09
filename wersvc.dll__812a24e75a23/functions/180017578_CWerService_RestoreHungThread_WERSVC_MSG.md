# CWerService::RestoreHungThread(_WERSVC_MSG *)

- ea: `0x180017578`
- end: `0x180017e61`
- name: `?RestoreHungThread@CWerService@@AEAAJPEAU_WERSVC_MSG@@@Z`
- size: `2281`
- prototype: `__int64 __fastcall(CWerService *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014fa4`

## callees

- `0x1800029f4`
- `0x180006a80`
- `0x180007cf8`
- `0x180011ef8`
- `0x180013ef8`
- `0x180017578`
- `0x18001caf4`
- `0x18001e298`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017675`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017767`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017675`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017767`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001772a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017739`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001772a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017739`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017632`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017654`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017632`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017654`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x1800179f2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x1800179f2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800178e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800178e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e23`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180017936`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180017936`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800179a4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017dc5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800179a4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017dc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800176f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017706`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001771b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800179bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800179d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800176f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017706`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001771b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800179bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800179d4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001798a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001798a`

## string_xrefs

- `0x18001762b`: `Iphlpapi.dll`
- `0x18001764d`: `nsi.dll`

## pseudocode

```c
__int64 __fastcall CWerService::RestoreHungThread(CWerService *this, unsigned __int64 a2)
{
  struct _WERSVC_MSG *v2; // rdi
  _DWORD *v4; // rsi
  HMODULE Library; // r14
  HMODULE v6; // r15
  char *v7; // r12
  unsigned int v8; // ebx
  unsigned int v9; // r15d
  DWORD v10; // r13d
  FARPROC ProcAddress; // r14
  signed int LastError; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  signed int v16; // eax
  USHORT v17; // cx
  SCOPE_ID v18; // r8d
  __int64 v19; // rax
  const IN6_ADDR *v20; // rax
  USHORT v21; // cx
  SCOPE_ID v22; // r8d
  __int64 v23; // rax
  const IN6_ADDR *v24; // rax
  void **v25; // rax
  signed int v26; // eax
  signed int v27; // eax
  HANDLE v28; // rcx
  HANDLE v29; // rcx
  signed int v30; // eax
  int v31; // eax
  _QWORD *v32; // rax
  int v33; // eax
  __int64 v34; // r9
  __int64 v35; // rcx
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  int v38; // eax
  signed int v39; // eax
  signed int v40; // eax
  _QWORD *v41; // rcx
  __int64 v42; // rdx
  signed int v43; // eax
  HANDLE hObject; // [rsp+50h] [rbp-59h] BYREF
  HANDLE ProcessHandle; // [rsp+58h] [rbp-51h] BYREF
  _BYTE a[32]; // [rsp+60h] [rbp-49h] BYREF
  _DWORD v47[6]; // [rsp+80h] [rbp-29h] BYREF
  struct _FILETIME ExitTime; // [rsp+98h] [rbp-11h] BYREF
  struct _FILETIME CreationTime; // [rsp+A0h] [rbp-9h] BYREF
  char *v50; // [rsp+A8h] [rbp-1h]
  _DWORD *v51; // [rsp+B0h] [rbp+7h]
  void *v52; // [rsp+B8h] [rbp+Fh] BYREF
  FARPROC v53; // [rsp+C0h] [rbp+17h]
  HMODULE v54; // [rsp+C8h] [rbp+1Fh]
  unsigned int v55; // [rsp+118h] [rbp+6Fh] BYREF
  HMODULE hModule; // [rsp+120h] [rbp+77h]
  HMODULE v57; // [rsp+128h] [rbp+7Fh]

  v2 = (struct _WERSVC_MSG *)a2;
  v4 = 0;
  Library = 0;
  v6 = 0;
  hModule = 0;
  ProcessHandle = 0;
  hObject = 0;
  v7 = 0;
  v50 = 0;
  CreationTime = 0;
  ExitTime = 0;
  memset(a, 0, sizeof(a));
  memset(v47, 0, sizeof(v47));
  v51 = 0;
  v55 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    goto LABEL_18;
  }
  memset(a, 0, sizeof(a));
  memset(v47, 0, sizeof(v47));
  v9 = *(unsigned __int16 *)(a2 + 60);
  if ( ((_WORD)v9 == 2 || (_WORD)v9 == 23) && (_WORD)v9 == *(_WORD *)(a2 + 88) )
  {
    v10 = *(_DWORD *)(a2 + 48);
    Library = LoadLibraryExW(L"Iphlpapi.dll", 0, 0);
    v57 = Library;
    if ( Library )
    {
      hModule = LoadLibraryExW(L"nsi.dll", 0, 0);
      v54 = hModule;
      if ( hModule )
      {
        ProcAddress = GetProcAddress(Library, "GetExtendedTcpTable");
        if ( !ProcAddress )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_16;
          v14 = 148;
          goto LABEL_15;
        }
        v53 = GetProcAddress(hModule, "NsiSetAllParameters");
        if ( !v53 )
        {
          v16 = GetLastError();
          v8 = v16;
          if ( v16 > 0 )
            v8 = (unsigned __int16)v16 | 0x80070000;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_16;
          v14 = 149;
          goto LABEL_15;
        }
        v17 = *((_WORD *)v2 + 31);
        if ( *((_WORD *)v2 + 30) == 23 )
          v18.0 = (struct $::$38AB66A4EA7C49F20D686D738A108FEA::$013671E5920392F7B68C675C97F9F7D8)*((_DWORD *)v2 + 21);
        else
          v18.0 = 0;
        v19 = 68;
        if ( *((_WORD *)v2 + 30) != 23 )
          v19 = 64;
        v20 = (const IN6_ADDR *)((char *)v2 + v19);
        if ( (_WORD)v9 == 23 )
        {
          IN6ADDR_SETSOCKADDR((PSOCKADDR_IN6)a, v20, v18, v17);
        }
        else
        {
          *(_WORD *)a = 2;
          *(_WORD *)&a[2] = v17;
          *(_DWORD *)&a[4] = *(_DWORD *)v20->u.Byte;
          *(_QWORD *)&a[8] = 0;
        }
        v21 = *((_WORD *)v2 + 45);
        if ( *((_WORD *)v2 + 44) == 23 )
          v22.0 = (struct $::$38AB66A4EA7C49F20D686D738A108FEA::$013671E5920392F7B68C675C97F9F7D8)*((_DWORD *)v2 + 28);
        else
          v22.0 = 0;
        v23 = 96;
        if ( *((_WORD *)v2 + 44) != 23 )
          v23 = 92;
        v24 = (const IN6_ADDR *)((char *)v2 + v23);
        if ( (_WORD)v9 == 23 )
        {
          IN6ADDR_SETSOCKADDR((PSOCKADDR_IN6)&a[28], v24, v22, v21);
        }
        else
        {
          *(_WORD *)&a[28] = 2;
          *(_WORD *)&a[30] = v21;
          v47[0] = *(_DWORD *)v24->u.Byte;
          *(_QWORD *)&v47[1] = 0;
        }
        v8 = CWerService::_OpenSenderProcessThread((__int64)this, (__int64)v2, 1024, &ProcessHandle, 0, 0, 1);
        if ( (v8 & 0x80000000) != 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_16;
          v14 = 150;
          goto LABEL_15;
        }
        v25 = tlx::replace<tlx::file_handle_traits>(&hObject);
        if ( !OpenProcessToken(ProcessHandle, 0xAu, v25) )
        {
          v26 = GetLastError();
          v8 = v26;
          if ( v26 > 0 )
            v8 = (unsigned __int16)v26 | 0x80070000;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_16;
          v14 = 151;
          goto LABEL_15;
        }
        if ( !ImpersonateLoggedOnUser(hObject) )
        {
          v27 = GetLastError();
          v8 = v27;
          if ( v27 > 0 )
            v8 = (unsigned __int16)v27 | 0x80070000;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_16;
          v14 = 152;
          goto LABEL_15;
        }
        v7 = (char *)OpenProcess(0x1FFFFFu, 0, v10);
        v50 = v7;
        if ( v7 == (char *)-1LL || v7 + 1 == (char *)1 )
        {
          v39 = GetLastError();
          v8 = v39;
          if ( v39 > 0 )
            v8 = (unsigned __int16)v39 | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v8);
          RevertToSelf();
          goto LABEL_16;
        }
        RevertToSelf();
        v28 = hObject;
        hObject = 0;
        if ( (unsigned __int64)v28 + 1 > 1 )
          CloseHandle(v28);
        v29 = ProcessHandle;
        ProcessHandle = 0;
        if ( (unsigned __int64)v29 + 1 > 1 )
          CloseHandle(v29);
        if ( !GetProcessTimes(v7, &CreationTime, &ExitTime, &ExitTime, &ExitTime) )
        {
          v30 = GetLastError();
          v8 = v30;
          if ( v30 > 0 )
            v8 = (unsigned __int16)v30 | 0x80070000;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_16;
          v14 = 154;
          goto LABEL_15;
        }
        if ( CreationTime.dwLowDateTime == *((_DWORD *)v2 + 13) && CreationTime.dwHighDateTime == *((_DWORD *)v2 + 14) )
        {
          v31 = ((__int64 (__fastcall *)(_QWORD, unsigned int *, _QWORD, _QWORD, int, _DWORD))ProcAddress)(
                  0,
                  &v55,
                  0,
                  v9,
                  4,
                  0);
          v8 = v31;
          if ( v31 != 122 )
          {
            if ( v31 > 0 )
              v8 = (unsigned __int16)v31 | 0x80070000;
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_16;
            v14 = 156;
            goto LABEL_15;
          }
          v55 += 560;
          v32 = utl::make_unique<unsigned char [0],0>(&v52, v55);
          v4 = (_DWORD *)*v32;
          *v32 = 0;
          v51 = v4;
          if ( v52 )
            operator delete(v52, (const struct std::nothrow_t *)a2);
          if ( v4 )
          {
            v33 = ((__int64 (__fastcall *)(_DWORD *, unsigned int *, _QWORD, _QWORD, int, _DWORD))ProcAddress)(
                    v4,
                    &v55,
                    0,
                    v9,
                    4,
                    0);
            v8 = v33;
            if ( v33 )
            {
              if ( v33 > 0 )
                v8 = (unsigned __int16)v33 | 0x80070000;
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_16;
              v14 = 158;
LABEL_15:
              WPP_SF_d(v13[2], v14, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v8);
LABEL_16:
              Library = v57;
              goto LABEL_17;
            }
            if ( (_WORD)v9 == 2 )
            {
              v34 = 0;
              if ( *v4 )
              {
                while ( 1 )
                {
                  a2 = *(unsigned __int16 *)&a[2];
                  if ( *(_QWORD *)&v4[6 * v34 + 2] == __PAIR64__(*(unsigned __int16 *)&a[2], *(unsigned int *)&a[4])
                    && v4[6 * v34 + 6] == v10
                    && v4[6 * v34 + 4] == v47[0] )
                  {
                    a2 = *(unsigned __int16 *)&a[30];
                    if ( v4[6 * v34 + 5] == *(unsigned __int16 *)&a[30] )
                      break;
                  }
                  v34 = (unsigned int)(v34 + 1);
                  if ( (unsigned int)v34 >= *v4 )
                    goto LABEL_114;
                }
LABEL_119:
                v38 = ((__int64 (__fastcall *)(__int64, __int64, __int64 *))v53)(1, 2, NPI_MS_TCP_MODULEID);
                v8 = v38 | 0x10000000;
                if ( v38 >= 0 )
                  goto LABEL_16;
                v13 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_16;
                v14 = 160;
                goto LABEL_15;
              }
            }
            else
            {
              a2 = 0;
              if ( *v4 )
              {
                while ( 1 )
                {
                  v35 = 14LL * (unsigned int)a2;
                  if ( *(_QWORD *)&v4[v35 + 5] == __PAIR64__(*(unsigned __int16 *)&a[2], *(unsigned int *)&a[24])
                    && v4[v35 + 14] == v10
                    && v4[v35 + 12] == *(unsigned __int16 *)&a[30]
                    && v4[v35 + 11] == v47[5]
                    && *(_OWORD *)&v4[v35 + 1] == *(_OWORD *)&a[8]
                    && *(_OWORD *)&v4[v35 + 7] == *(_OWORD *)&v47[1] )
                  {
                    break;
                  }
                  a2 = (unsigned int)(a2 + 1);
                  if ( (unsigned int)a2 >= *v4 )
                  {
                    v7 = v50;
                    goto LABEL_114;
                  }
                }
                v7 = v50;
                goto LABEL_119;
              }
            }
LABEL_114:
            v8 = -2147023728;
            v36 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_16;
            v37 = 159;
          }
          else
          {
            v8 = -2147024882;
            v36 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_16;
            v37 = 157;
          }
        }
        else
        {
          v8 = -2147024809;
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_16;
          v37 = 155;
        }
        WPP_SF_(v36[2], v37, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
        goto LABEL_16;
      }
      v40 = GetLastError();
      v8 = v40;
      if ( v40 > 0 )
        v8 = (unsigned __int16)v40 | 0x80070000;
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_17;
      v42 = 147;
    }
    else
    {
      v43 = GetLastError();
      v8 = v43;
      if ( v43 > 0 )
        v8 = (unsigned __int16)v43 | 0x80070000;
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_17;
      v42 = 146;
    }
    WPP_SF_d(v41[2], v42, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v8);
    goto LABEL_17;
  }
  v8 = -2147024809;
LABEL_17:
  v6 = hModule;
LABEL_18:
  if ( v4 )
    operator delete(v4, (const struct std::nothrow_t *)a2);
  if ( (unsigned __int64)(v7 + 1) > 1 )
    CloseHandle(v7);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( (unsigned __int64)ProcessHandle + 1 > 1 )
    CloseHandle(ProcessHandle);
  if ( v6 )
    FreeLibrary(v6);
  if ( Library )
    FreeLibrary(Library);
  return v8;
}

```

## disassembly

```asm
0x180017578  mov     [rsp-8+arg_0], rbx
0x18001757d  push    rbp
0x18001757e  push    rsi
0x18001757f  push    rdi
0x180017580  push    r12
0x180017582  push    r13
0x180017584  push    r14
0x180017586  push    r15
0x180017588  lea     rbp, [rsp-27h]
0x18001758d  sub     rsp, 0D0h
0x180017594  mov     rdi, rdx
0x180017597  mov     rbx, rcx
0x18001759a  xor     esi, esi
0x18001759c  mov     r14d, esi
0x18001759f  mov     r15d, esi
0x1800175a2  mov     [rbp+57h+hModule], rsi
0x1800175a6  mov     [rbp+57h+ProcessHandle], rsi
0x1800175aa  mov     [rbp+57h+hObject], rsi
0x1800175ae  mov     r12d, esi
0x1800175b1  mov     [rbp+57h+var_58], rsi
0x1800175b5  mov     qword ptr [rbp+57h+CreationTime.dwLowDateTime], rsi
0x1800175b9  mov     qword ptr [rbp+57h+ExitTime.dwLowDateTime], rsi
0x1800175bd  xorps   xmm0, xmm0
0x1800175c0  xor     eax, eax
0x1800175c2  movups  xmmword ptr [rbp+57h+a.sin6_family], xmm0
0x1800175c6  movups  xmmword ptr [rbp+57h+a.sin6_addr.u+8], xmm0
0x1800175ca  movups  xmmword ptr [rbp+57h+var_84.sin6_flowinfo], xmm0
0x1800175ce  mov     qword ptr [rbp+57h+var_84.sin6_addr.u+0Ch], rax
0x1800175d2  mov     [rbp+57h+var_50], rsi
0x1800175d6  mov     [rbp+57h+arg_8], eax
0x1800175d9  test    rdx, rdx
0x1800175dc  jnz     short loc_1800175E8
0x1800175de  mov     ebx, 80070057h
0x1800175e3  jmp     loc_1800176D5
0x1800175e8  xor     eax, eax
0x1800175ea  movups  xmmword ptr [rbp+57h+a.sin6_family], xmm0
0x1800175ee  movups  xmmword ptr [rbp+57h+a.sin6_addr.u+8], xmm0
0x1800175f2  movups  xmmword ptr [rbp+57h+var_84.sin6_flowinfo], xmm0
0x1800175f6  mov     qword ptr [rbp+57h+var_84.sin6_addr.u+0Ch], rax
0x1800175fa  movzx   r15d, word ptr [rdx+3Ch]
0x1800175ff  lea     ecx, [rax+2]
0x180017602  lea     eax, [rcx+15h]
0x180017605  cmp     cx, r15w
0x180017609  jz      short loc_180017611
0x18001760b  cmp     ax, r15w
0x18001760f  jnz     short loc_180017618
0x180017611  cmp     r15w, [rdx+58h]
0x180017616  jz      short loc_180017622
0x180017618  mov     ebx, 80070057h
0x18001761d  jmp     loc_1800176D1
0x180017622  mov     r13d, [rdx+30h]
0x180017626  xor     r8d, r8d; dwFlags
0x180017629  xor     edx, edx; hFile
0x18001762b  lea     rcx, LibFileName; "Iphlpapi.dll"
0x180017632  call    cs:__imp_LoadLibraryExW
0x180017638  mov     r14, rax
0x18001763b  mov     [rbp+57h+arg_18], rax
0x18001763f  test    rax, rax
0x180017642  jz      loc_180017E23
0x180017648  xor     r8d, r8d; dwFlags
0x18001764b  xor     edx, edx; hFile
0x18001764d  lea     rcx, aNsiDll; "nsi.dll"
0x180017654  call    cs:__imp_LoadLibraryExW
0x18001765a  mov     [rbp+57h+hModule], rax
0x18001765e  mov     [rbp+57h+var_38], rax
0x180017662  test    rax, rax
0x180017665  jz      loc_180017DD0
0x18001766b  lea     rdx, aGetextendedtcp; "GetExtendedTcpTable"
0x180017672  mov     rcx, r14; hModule
0x180017675  call    cs:__imp_GetProcAddress
0x18001767b  mov     r14, rax
0x18001767e  test    rax, rax
0x180017681  jnz     loc_18001775C
0x180017687  call    cs:__imp_GetLastError
0x18001768d  mov     ebx, eax
0x18001768f  test    eax, eax
0x180017691  jle     short loc_18001769C
0x180017693  movzx   ebx, ax
0x180017696  or      ebx, 80070000h
0x18001769c  lea     rax, WPP_GLOBAL_Control
0x1800176a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800176aa  cmp     rcx, rax
0x1800176ad  jz      short loc_1800176CD
0x1800176af  test    byte ptr [rcx+1Ch], 1
0x1800176b3  jz      short loc_1800176CD
0x1800176b5  mov     edx, 94h
0x1800176ba  mov     r9d, ebx
0x1800176bd  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x1800176c4  mov     rcx, [rcx+10h]
0x1800176c8  call    WPP_SF_d
0x1800176cd  mov     r14, [rbp+57h+arg_18]
0x1800176d1  mov     r15, [rbp+57h+hModule]
0x1800176d5  test    rsi, rsi
0x1800176d8  jz      short loc_1800176E3
0x1800176da  mov     rcx, rsi; void *
0x1800176dd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800176e2  nop
0x1800176e3  lea     rax, [r12+1]
0x1800176e8  cmp     rax, 1
0x1800176ec  jbe     short loc_1800176F8
0x1800176ee  mov     rcx, r12; hObject
0x1800176f1  call    cs:__imp_CloseHandle
0x1800176f7  nop
0x1800176f8  mov     rcx, [rbp+57h+hObject]; hObject
0x1800176fc  lea     rax, [rcx+1]
0x180017700  cmp     rax, 1
0x180017704  jbe     short loc_18001770D
0x180017706  call    cs:__imp_CloseHandle
0x18001770c  nop
0x18001770d  mov     rcx, [rbp+57h+ProcessHandle]; hObject
0x180017711  lea     rax, [rcx+1]
0x180017715  cmp     rax, 1
0x180017719  jbe     short loc_180017722
0x18001771b  call    cs:__imp_CloseHandle
0x180017721  nop
0x180017722  test    r15, r15
0x180017725  jz      short loc_180017731
0x180017727  mov     rcx, r15; hLibModule
0x18001772a  call    cs:__imp_FreeLibrary
0x180017730  nop
0x180017731  test    r14, r14
0x180017734  jz      short loc_18001773F
0x180017736  mov     rcx, r14; hLibModule
0x180017739  call    cs:__imp_FreeLibrary
0x18001773f  mov     eax, ebx
0x180017741  mov     rbx, [rsp+100h+arg_0]
0x180017749  add     rsp, 0D0h
0x180017750  pop     r15
0x180017752  pop     r14
0x180017754  pop     r13
0x180017756  pop     r12
0x180017758  pop     rdi
0x180017759  pop     rsi
0x18001775a  pop     rbp
0x18001775b  retn
0x18001775c  lea     rdx, aNsisetallparam; "NsiSetAllParameters"
0x180017763  mov     rcx, [rbp+57h+hModule]; hModule
0x180017767  call    cs:__imp_GetProcAddress
0x18001776d  mov     [rbp+57h+var_40], rax
0x180017771  test    rax, rax
0x180017774  jnz     short loc_1800177B6
0x180017776  call    cs:__imp_GetLastError
0x18001777c  mov     ebx, eax
0x18001777e  test    eax, eax
0x180017780  jle     short loc_18001778B
0x180017782  movzx   ebx, ax
0x180017785  or      ebx, 80070000h
0x18001778b  lea     rax, WPP_GLOBAL_Control
0x180017792  mov     rcx, cs:WPP_GLOBAL_Control
0x180017799  cmp     rcx, rax
0x18001779c  jz      loc_1800176CD
0x1800177a2  test    byte ptr [rcx+1Ch], 1
0x1800177a6  jz      loc_1800176CD
0x1800177ac  mov     edx, 95h
0x1800177b1  jmp     loc_1800176BA
0x1800177b6  movzx   ecx, word ptr [rdi+3Eh]
0x1800177ba  mov     r9d, 17h
0x1800177c0  cmp     [rdi+3Ch], r9w
0x1800177c5  jnz     short loc_1800177CD
0x1800177c7  mov     r8d, [rdi+54h]
0x1800177cb  jmp     short loc_1800177D0
0x1800177cd  xor     r8d, r8d; scope
0x1800177d0  mov     eax, 44h ; 'D'
0x1800177d5  lea     edx, [rax-4]
0x1800177d8  cmp     [rdi+3Ch], r9w
0x1800177dd  cmovnz  eax, edx
0x1800177e0  add     rax, rdi
0x1800177e3  cmp     r15w, r9w
0x1800177e7  jnz     short loc_180017805
0x1800177e9  movzx   r9d, cx; port
0x1800177ed  mov     rdx, rax; addr
0x1800177f0  lea     rcx, [rbp+57h+a]; a
0x1800177f4  call    IN6ADDR_SETSOCKADDR
0x1800177f9  mov     r9d, 17h
0x1800177ff  lea     r10d, [r9-15h]
0x180017803  jmp     short loc_18001781F
0x180017805  mov     r10d, 2
0x18001780b  mov     [rbp+57h+a.sin6_family], r10w
0x180017810  mov     [rbp+57h+a.sin6_port], cx
0x180017814  mov     eax, [rax]
0x180017816  mov     [rbp+57h+a.sin6_flowinfo], eax
0x180017819  xor     eax, eax
0x18001781b  mov     qword ptr [rbp+57h+a.sin6_addr.u], rax
0x18001781f  movzx   ecx, word ptr [rdi+5Ah]
0x180017823  cmp     [rdi+58h], r9w
0x180017828  jnz     short loc_180017830
0x18001782a  mov     r8d, [rdi+70h]
0x18001782e  jmp     short loc_180017833
0x180017830  xor     r8d, r8d; scope
0x180017833  mov     eax, 60h ; '`'
0x180017838  lea     edx, [rax-4]
0x18001783b  cmp     [rdi+58h], r9w
0x180017840  cmovnz  eax, edx
0x180017843  add     rax, rdi
0x180017846  cmp     r15w, r9w
0x18001784a  jnz     short loc_18001785E
0x18001784c  movzx   r9d, cx; port
0x180017850  mov     rdx, rax; addr
0x180017853  lea     rcx, [rbp+57h+var_84]; a
0x180017857  call    IN6ADDR_SETSOCKADDR
0x18001785c  jmp     short loc_180017872
0x18001785e  mov     [rbp+57h+var_84.sin6_family], r10w
0x180017863  mov     [rbp+57h+var_84.sin6_port], cx
0x180017867  mov     eax, [rax]
0x180017869  mov     [rbp+57h+var_84.sin6_flowinfo], eax
0x18001786c  xor     eax, eax
0x18001786e  mov     qword ptr [rbp+57h+var_84.sin6_addr.u], rax
0x180017872  mov     dword ptr [rsp+100h+var_D0], 1
0x18001787a  mov     [rsp+100h+var_D8], 0
0x180017883  mov     dword ptr [rsp+100h+lpUserTime], 0
0x18001788b  lea     r9, [rbp+57h+ProcessHandle]
0x18001788f  mov     r8d, 400h
0x180017895  mov     rdx, rdi
0x180017898  mov     rcx, rbx
0x18001789b  call    ?_OpenSenderProcessThread@CWerService@@AEAAJPEAU_WERSVC_MSG@@KPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K1K@Z; CWerService::_OpenSenderProcessThread(_WERSVC_MSG *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong)
0x1800178a0  mov     ebx, eax
0x1800178a2  test    eax, eax
0x1800178a4  jns     short loc_1800178D1
0x1800178a6  lea     rax, WPP_GLOBAL_Control
0x1800178ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178b4  cmp     rcx, rax
0x1800178b7  jz      loc_1800176CD
0x1800178bd  test    byte ptr [rcx+1Ch], 1
0x1800178c1  jz      loc_1800176CD
0x1800178c7  mov     edx, 96h
0x1800178cc  jmp     loc_1800176BA
0x1800178d1  lea     rcx, [rbp+57h+hObject]
0x1800178d5  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800178da  mov     r8, rax; TokenHandle
0x1800178dd  mov     edx, 0Ah; DesiredAccess
0x1800178e2  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1800178e6  call    cs:__imp_OpenProcessToken
0x1800178ec  xor     ebx, ebx
0x1800178ee  test    eax, eax
0x1800178f0  jnz     short loc_180017932
0x1800178f2  call    cs:__imp_GetLastError
0x1800178f8  mov     ebx, eax
0x1800178fa  test    eax, eax
0x1800178fc  jle     short loc_180017907
0x1800178fe  movzx   ebx, ax
0x180017901  or      ebx, 80070000h
0x180017907  lea     rax, WPP_GLOBAL_Control
0x18001790e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017915  cmp     rcx, rax
0x180017918  jz      loc_1800176CD
0x18001791e  test    byte ptr [rcx+1Ch], 1
0x180017922  jz      loc_1800176CD
0x180017928  mov     edx, 97h
0x18001792d  jmp     loc_1800176BA
0x180017932  mov     rcx, [rbp+57h+hObject]; hToken
0x180017936  call    cs:__imp_ImpersonateLoggedOnUser
0x18001793c  test    eax, eax
0x18001793e  jnz     short loc_180017980
0x180017940  call    cs:__imp_GetLastError
0x180017946  mov     ebx, eax
0x180017948  test    eax, eax
0x18001794a  jle     short loc_180017955
0x18001794c  movzx   ebx, ax
0x18001794f  or      ebx, 80070000h
0x180017955  lea     rax, WPP_GLOBAL_Control
0x18001795c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017963  cmp     rcx, rax
0x180017966  jz      loc_1800176CD
0x18001796c  test    byte ptr [rcx+1Ch], 1
0x180017970  jz      loc_1800176CD
0x180017976  mov     edx, 98h
0x18001797b  jmp     loc_1800176BA
0x180017980  mov     r8d, r13d; dwProcessId
0x180017983  xor     edx, edx; bInheritHandle
0x180017985  mov     ecx, 1FFFFFh; dwDesiredAccess
0x18001798a  call    cs:__imp_OpenProcess
0x180017990  mov     r12, rax
0x180017993  mov     [rbp+57h+var_58], rax
0x180017997  inc     rax
0x18001799a  cmp     rax, 1
0x18001799e  jbe     loc_180017D7F
0x1800179a4  call    cs:__imp_RevertToSelf
0x1800179aa  mov     rcx, [rbp+57h+hObject]; hObject
0x1800179ae  mov     [rbp+57h+hObject], rbx
0x1800179b2  lea     rax, [rcx+1]
0x1800179b6  cmp     rax, 1
0x1800179ba  jbe     short loc_1800179C2
0x1800179bc  call    cs:__imp_CloseHandle
0x1800179c2  mov     rcx, [rbp+57h+ProcessHandle]; hObject
0x1800179c6  mov     [rbp+57h+ProcessHandle], rbx
0x1800179ca  lea     rax, [rcx+1]
0x1800179ce  cmp     rax, 1
0x1800179d2  jbe     short loc_1800179DA
0x1800179d4  call    cs:__imp_CloseHandle
0x1800179da  lea     rax, [rbp+57h+ExitTime]
0x1800179de  mov     [rsp+100h+lpUserTime], rax; lpUserTime
0x1800179e3  lea     r9, [rbp+57h+ExitTime]; lpKernelTime
0x1800179e7  lea     r8, [rbp+57h+ExitTime]; lpExitTime
0x1800179eb  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x1800179ef  mov     rcx, r12; hProcess
0x1800179f2  call    cs:__imp_GetProcessTimes
0x1800179f8  test    eax, eax
0x1800179fa  jnz     short loc_180017A3C
0x1800179fc  call    cs:__imp_GetLastError
0x180017a02  mov     ebx, eax
  ... truncated ...
```
