# LaunchGenericReporting(void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180021b88`
- end: `0x180021fb9`
- name: `?LaunchGenericReporting@@YAJPEAX00000000000PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `1073`
- prototype: `__int64 __fastcall(HANDLE hTargetProcessHandle, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18001924c`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180003cf8`
- `0x180003d6c`
- `0x180006134`
- `0x180007cf8`
- `0x180011ef8`
- `0x18001fb94`
- `0x180021b88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021d08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021eed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021d08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021eed`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180021d59`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180021d59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021f1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ccd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ccd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f8e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180021d33`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180021f14`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180021d33`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180021f14`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LaunchGenericReporting(
        HANDLE hTargetProcessHandle,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        void **a13)
{
  void *v14; // rcx
  int v15; // esi
  int v16; // edi
  HANDLE *v17; // r12
  HANDLE *v18; // rbx
  HANDLE v19; // rax
  DWORD ProcessId; // eax
  signed int ElevatedProcessAsUser; // ebx
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  signed int v24; // eax
  HANDLE *v25; // rbx
  HANDLE v26; // rdi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  HANDLE hSourceHandle; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+88h] [rbp-78h] BYREF
  __int64 v32; // [rsp+90h] [rbp-70h] BYREF
  __int64 v33; // [rsp+98h] [rbp-68h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v37; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v38; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v39; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v40; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v41; // [rsp+D8h] [rbp-28h] BYREF
  void **v42; // [rsp+E0h] [rbp-20h]
  _QWORD v43[12]; // [rsp+F0h] [rbp-10h]
  _QWORD v44[12]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v45[12]; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t v46[264]; // [rsp+210h] [rbp+110h] BYREF

  v42 = a13;
  v31 = a2;
  v32 = a3;
  v33 = a4;
  v34 = a5;
  v35 = a6;
  v36 = a7;
  v37 = a8;
  v38 = a9;
  v39 = a10;
  v40 = a11;
  v41 = a12;
  hSourceHandle = 0;
  v43[0] = &v31;
  v43[1] = &v32;
  v43[2] = &v33;
  v43[3] = &v34;
  v43[4] = &v35;
  v43[5] = &v36;
  v43[6] = &v37;
  v43[7] = &v38;
  v43[8] = &v39;
  v43[9] = &v40;
  v43[10] = &v41;
  memset_0(v44, 0, 0x58u);
  `eh vector constructor iterator'(
    v45,
    8u,
    0xBu,
    tlx::unique_any<tlx::file_handle_traits>::unique_any<tlx::file_handle_traits>,
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>);
  v14 = *a13;
  *a13 = 0;
  if ( (unsigned __int64)v14 + 1 > 1 )
    CloseHandle(v14);
  v15 = 0;
  v46[0] = 0;
  v16 = 0;
  while ( 1 )
  {
    v17 = (HANDLE *)v43[v16];
    if ( (__int64)*v17 > 0 )
      break;
LABEL_7:
    if ( (unsigned int)++v16 >= 0xB )
    {
      ProcessId = GetProcessId(hTargetProcessHandle);
      ElevatedProcessAsUser = StringCchPrintfW(
                                v46,
                                0x104u,
                                L"-outproc 1 %u %Id %Id %Id %Id %Id %Id %Id %Id %Id %Id %Id",
                                ProcessId,
                                v44[0],
                                v44[1],
                                v44[2],
                                v44[3],
                                v44[4],
                                v44[5],
                                v44[6],
                                v44[7],
                                v44[8],
                                v44[9],
                                v44[10]);
      if ( ElevatedProcessAsUser >= 0 )
      {
        ElevatedProcessAsUser = CreateElevatedProcessAsUser(
                                  (_DWORD)hTargetProcessHandle,
                                  (unsigned int)v46,
                                  (unsigned int)v45,
                                  v15,
                                  0,
                                  (__int64)&hSourceHandle,
                                  170);
        if ( ElevatedProcessAsUser >= 0 )
        {
          v25 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(v42);
          v26 = hSourceHandle;
          hSourceHandle = 0;
          CurrentProcess = GetCurrentProcess();
          if ( DuplicateHandle(CurrentProcess, v26, hTargetProcessHandle, v25, 0x120001u, 0, 1u) )
          {
            ElevatedProcessAsUser = 0;
          }
          else
          {
            LastError = GetLastError();
            ElevatedProcessAsUser = LastError;
            if ( LastError > 0 )
              ElevatedProcessAsUser = (unsigned __int16)LastError | 0x80070000;
            if ( ElevatedProcessAsUser >= 0 )
              ElevatedProcessAsUser = -2147467259;
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v23 = 120;
              goto LABEL_19;
            }
          }
        }
        else
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v23 = 119;
            goto LABEL_19;
          }
        }
      }
      else
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v23 = 118;
LABEL_19:
          WPP_SF_d(v22[2], v23, &WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, (unsigned int)ElevatedProcessAsUser);
          goto LABEL_33;
        }
      }
      goto LABEL_33;
    }
  }
  v18 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&v45[v15]);
  v19 = GetCurrentProcess();
  if ( DuplicateHandle(hTargetProcessHandle, *v17, v19, v18, 0, 1, 2u) )
  {
    v44[v16] = v45[v15++];
    goto LABEL_7;
  }
  v24 = GetLastError();
  ElevatedProcessAsUser = v24;
  if ( v24 > 0 )
    ElevatedProcessAsUser = (unsigned __int16)v24 | 0x80070000;
  if ( ElevatedProcessAsUser >= 0 )
    ElevatedProcessAsUser = -2147467259;
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v23 = 117;
    goto LABEL_19;
  }
LABEL_33:
  `eh vector destructor iterator'(
    v45,
    8u,
    0xBu,
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>);
  if ( (unsigned __int64)hSourceHandle + 1 > 1 )
    CloseHandle(hSourceHandle);
  return (unsigned int)ElevatedProcessAsUser;
}

```

## disassembly

```asm
0x180021b88  push    rbp
0x180021b8a  push    rbx
0x180021b8b  push    rsi
0x180021b8c  push    rdi
0x180021b8d  push    r12
0x180021b8f  push    r13
0x180021b91  push    r14
0x180021b93  push    r15
0x180021b95  lea     rbp, [rsp-338h]
0x180021b9d  sub     rsp, 438h
0x180021ba4  mov     rax, cs:__security_cookie
0x180021bab  xor     rax, rsp
0x180021bae  mov     [rbp+370h+var_50], rax
0x180021bb5  mov     r15, rcx
0x180021bb8  mov     rbx, [rbp+370h+arg_60]
0x180021bbf  mov     [rbp+370h+var_390], rbx
0x180021bc3  mov     [rbp+370h+var_3E8], rdx
0x180021bc7  mov     [rbp+370h+var_3E0], r8
0x180021bcb  mov     [rbp+370h+var_3D8], r9
0x180021bcf  mov     rax, [rbp+370h+arg_20]
0x180021bd6  mov     [rbp+370h+var_3D0], rax
0x180021bda  mov     rax, [rbp+370h+arg_28]
0x180021be1  mov     [rbp+370h+var_3C8], rax
0x180021be5  mov     rax, [rbp+370h+arg_30]
0x180021bec  mov     [rbp+370h+var_3C0], rax
0x180021bf0  mov     rax, [rbp+370h+arg_38]
0x180021bf7  mov     [rbp+370h+var_3B8], rax
0x180021bfb  mov     rax, [rbp+370h+arg_40]
0x180021c02  mov     [rbp+370h+var_3B0], rax
0x180021c06  mov     rax, [rbp+370h+arg_48]
0x180021c0d  mov     [rbp+370h+var_3A8], rax
0x180021c11  mov     rax, [rbp+370h+arg_50]
0x180021c18  mov     [rbp+370h+var_3A0], rax
0x180021c1c  mov     rax, [rbp+370h+arg_58]
0x180021c23  mov     [rbp+370h+var_398], rax
0x180021c27  xor     r13d, r13d
0x180021c2a  mov     [rbp+370h+hSourceHandle], r13
0x180021c2e  lea     rax, [rbp+370h+var_3E8]
0x180021c32  mov     [rbp+370h+var_380], rax
0x180021c36  lea     rax, [rbp+370h+var_3E0]
0x180021c3a  mov     [rbp+370h+var_378], rax
0x180021c3e  lea     rax, [rbp+370h+var_3D8]
0x180021c42  mov     [rbp+370h+var_370], rax
0x180021c46  lea     rax, [rbp+370h+var_3D0]
0x180021c4a  mov     [rbp+370h+var_368], rax
0x180021c4e  lea     rax, [rbp+370h+var_3C8]
0x180021c52  mov     [rbp+370h+var_360], rax
0x180021c56  lea     rax, [rbp+370h+var_3C0]
0x180021c5a  mov     [rbp+370h+var_358], rax
0x180021c5e  lea     rax, [rbp+370h+var_3B8]
0x180021c62  mov     [rbp+370h+var_350], rax
0x180021c66  lea     rax, [rbp+370h+var_3B0]
0x180021c6a  mov     [rbp+370h+var_348], rax
0x180021c6e  lea     rax, [rbp+370h+var_3A8]
0x180021c72  mov     [rbp+370h+var_340], rax
0x180021c76  lea     rax, [rbp+370h+var_3A0]
0x180021c7a  mov     [rbp+370h+var_338], rax
0x180021c7e  lea     rax, [rbp+370h+var_398]
0x180021c82  mov     [rbp+370h+var_330], rax
0x180021c86  xor     edx, edx; Val
0x180021c88  lea     r8d, [r13+58h]; Size
0x180021c8c  lea     rcx, [rbp+370h+var_320]; void *
0x180021c90  call    memset_0
0x180021c95  lea     rax, ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180021c9c  mov     qword ptr [rsp+470h+dwDesiredAccess], rax; void (*)(void *)
0x180021ca1  lea     r9, ??0?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; void (*)(void *)
0x180021ca8  lea     edx, [r13+8]; unsigned __int64
0x180021cac  lea     r8d, [r13+0Bh]; unsigned __int64
0x180021cb0  lea     rcx, [rbp+370h+var_2C0]; void *
0x180021cb7  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180021cbc  nop
0x180021cbd  mov     rcx, [rbx]; hObject
0x180021cc0  mov     [rbx], r13
0x180021cc3  lea     rax, [rcx+1]
0x180021cc7  cmp     rax, 1
0x180021ccb  jbe     short loc_180021CD3
0x180021ccd  call    cs:__imp_CloseHandle
0x180021cd3  mov     esi, r13d
0x180021cd6  mov     [rbp+370h+var_260], r13w
0x180021cde  mov     edi, r13d
0x180021ce1  movsxd  r14, edi
0x180021ce4  mov     r12, [rbp+r14*8+370h+var_380]
0x180021ce9  cmp     [r12], r13
0x180021ced  jle     short loc_180021D4F
0x180021cef  mov     eax, esi
0x180021cf1  lea     r13, [rbp+370h+var_2C0]
0x180021cf8  lea     r13, [r13+rax*8+0]
0x180021cfd  mov     rcx, r13
0x180021d00  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180021d05  mov     rbx, rax
0x180021d08  call    cs:__imp_GetCurrentProcess
0x180021d0e  mov     [rsp+470h+dwOptions], 2; dwOptions
0x180021d16  mov     [rsp+470h+bInheritHandle], 1; bInheritHandle
0x180021d1e  mov     [rsp+470h+dwDesiredAccess], 0; dwDesiredAccess
0x180021d26  mov     r9, rbx; lpTargetHandle
0x180021d29  mov     r8, rax; hTargetProcessHandle
0x180021d2c  mov     rdx, [r12]; hSourceHandle
0x180021d30  mov     rcx, r15; hSourceProcessHandle
0x180021d33  call    cs:__imp_DuplicateHandle
0x180021d39  test    eax, eax
0x180021d3b  jz      loc_180021E1E
0x180021d41  mov     rax, [r13+0]
0x180021d45  mov     [rbp+r14*8+370h+var_320], rax
0x180021d4a  inc     esi
0x180021d4c  xor     r13d, r13d
0x180021d4f  inc     edi
0x180021d51  cmp     edi, 0Bh
0x180021d54  jb      short loc_180021CE1
0x180021d56  mov     rcx, r15; Process
0x180021d59  call    cs:__imp_GetProcessId
0x180021d5f  mov     r9d, eax
0x180021d62  mov     rcx, [rbp+370h+var_2D0]
0x180021d69  mov     [rsp+470h+var_400], rcx
0x180021d6e  mov     rcx, [rbp+370h+var_2D8]
0x180021d75  mov     [rsp+470h+var_408], rcx
0x180021d7a  mov     rcx, [rbp+370h+var_2E0]
0x180021d81  mov     [rsp+470h+var_410], rcx
0x180021d86  mov     rcx, [rbp+370h+var_2E8]
0x180021d8d  mov     [rsp+470h+var_418], rcx
0x180021d92  mov     rcx, [rbp+370h+var_2F0]
0x180021d99  mov     [rsp+470h+var_420], rcx
0x180021d9e  mov     rcx, [rbp+370h+var_2F8]
0x180021da2  mov     [rsp+470h+var_428], rcx
0x180021da7  mov     rcx, [rbp+370h+var_300]
0x180021dab  mov     [rsp+470h+var_430], rcx
0x180021db0  mov     rax, [rbp+370h+var_308]
0x180021db4  mov     [rsp+470h+var_438], rax
0x180021db9  mov     rax, [rbp+370h+var_310]
0x180021dbd  mov     qword ptr [rsp+470h+dwOptions], rax
0x180021dc2  mov     rax, [rbp+370h+var_318]
0x180021dc6  mov     qword ptr [rsp+470h+bInheritHandle], rax
0x180021dcb  mov     rax, [rbp+370h+var_320]
0x180021dcf  mov     qword ptr [rsp+470h+dwDesiredAccess], rax
0x180021dd4  lea     r8, aOutproc1UIdIdI; "-outproc 1 %u %Id %Id %Id %Id %Id %Id %"...
0x180021ddb  mov     edx, 104h; unsigned __int64
0x180021de0  lea     rcx, [rbp+370h+var_260]; wchar_t *
0x180021de7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180021dec  mov     ebx, eax
0x180021dee  test    eax, eax
0x180021df0  jns     loc_180021E7B
0x180021df6  lea     rax, WPP_GLOBAL_Control
0x180021dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e04  cmp     rcx, rax
0x180021e07  jz      loc_180021F63
0x180021e0d  test    byte ptr [rcx+1Ch], 1
0x180021e11  jz      loc_180021F63
0x180021e17  mov     edx, 76h ; 'v'
0x180021e1c  jmp     short loc_180021E63
0x180021e1e  call    cs:__imp_GetLastError
0x180021e24  mov     ebx, eax
0x180021e26  test    eax, eax
0x180021e28  jle     short loc_180021E33
0x180021e2a  movzx   ebx, ax
0x180021e2d  or      ebx, 80070000h
0x180021e33  mov     eax, 80004005h
0x180021e38  test    ebx, ebx
0x180021e3a  cmovns  ebx, eax
0x180021e3d  lea     rax, WPP_GLOBAL_Control
0x180021e44  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e4b  cmp     rcx, rax
0x180021e4e  jz      loc_180021F63
0x180021e54  test    byte ptr [rcx+1Ch], 1
0x180021e58  jz      loc_180021F63
0x180021e5e  mov     edx, 75h ; 'u'
0x180021e63  mov     r9d, ebx
0x180021e66  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x180021e6d  mov     rcx, [rcx+10h]
0x180021e71  call    WPP_SF_d
0x180021e76  jmp     loc_180021F63
0x180021e7b  mov     [rsp+470h+dwOptions], 0AAh
0x180021e83  lea     rcx, [rbp+370h+hSourceHandle]
0x180021e87  mov     qword ptr [rsp+470h+bInheritHandle], rcx
0x180021e8c  mov     word ptr [rsp+470h+dwDesiredAccess], r13w
0x180021e92  mov     r9d, esi
0x180021e95  lea     r8, [rbp+370h+var_2C0]
0x180021e9c  lea     rdx, [rbp+370h+var_260]
0x180021ea3  mov     rcx, r15
0x180021ea6  call    ?CreateElevatedProcessAsUser@@YAJPEAXPEA_WPEAPEAXKGPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K@Z; CreateElevatedProcessAsUser(void *,wchar_t *,void * *,ulong,ushort,tlx::unique_any<tlx::file_handle_traits> *,ulong)
0x180021eab  mov     ebx, eax
0x180021ead  test    eax, eax
0x180021eaf  jns     short loc_180021ED9
0x180021eb1  lea     rax, WPP_GLOBAL_Control
0x180021eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ebf  cmp     rcx, rax
0x180021ec2  jz      loc_180021F63
0x180021ec8  test    byte ptr [rcx+1Ch], 1
0x180021ecc  jz      loc_180021F63
0x180021ed2  mov     edx, 77h ; 'w'
0x180021ed7  jmp     short loc_180021E63
0x180021ed9  mov     rcx, [rbp+370h+var_390]
0x180021edd  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180021ee2  mov     rbx, rax
0x180021ee5  mov     rdi, [rbp+370h+hSourceHandle]
0x180021ee9  mov     [rbp+370h+hSourceHandle], r13
0x180021eed  call    cs:__imp_GetCurrentProcess
0x180021ef3  mov     [rsp+470h+dwOptions], 1; dwOptions
0x180021efb  mov     [rsp+470h+bInheritHandle], r13d; bInheritHandle
0x180021f00  mov     [rsp+470h+dwDesiredAccess], 120001h; dwDesiredAccess
0x180021f08  mov     r9, rbx; lpTargetHandle
0x180021f0b  mov     r8, r15; hTargetProcessHandle
0x180021f0e  mov     rdx, rdi; hSourceHandle
0x180021f11  mov     rcx, rax; hSourceProcessHandle
0x180021f14  call    cs:__imp_DuplicateHandle
0x180021f1a  test    eax, eax
0x180021f1c  jnz     short loc_180021F60
0x180021f1e  call    cs:__imp_GetLastError
0x180021f24  mov     ebx, eax
0x180021f26  test    eax, eax
0x180021f28  jle     short loc_180021F33
0x180021f2a  movzx   ebx, ax
0x180021f2d  or      ebx, 80070000h
0x180021f33  mov     eax, 80004005h
0x180021f38  test    ebx, ebx
0x180021f3a  cmovns  ebx, eax
0x180021f3d  lea     rax, WPP_GLOBAL_Control
0x180021f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f4b  cmp     rcx, rax
0x180021f4e  jz      short loc_180021F63
0x180021f50  test    byte ptr [rcx+1Ch], 1
0x180021f54  jz      short loc_180021F63
0x180021f56  mov     edx, 78h ; 'x'
0x180021f5b  jmp     loc_180021E63
0x180021f60  mov     ebx, r13d
0x180021f63  lea     r9, ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; void (*)(void *)
0x180021f6a  mov     edx, 8; unsigned __int64
0x180021f6f  lea     r8d, [rdx+3]; unsigned __int64
0x180021f73  lea     rcx, [rbp+370h+var_2C0]; void *
0x180021f7a  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180021f7f  nop
0x180021f80  mov     rcx, [rbp+370h+hSourceHandle]; hObject
0x180021f84  lea     rax, [rcx+1]
0x180021f88  cmp     rax, 1
0x180021f8c  jbe     short loc_180021F94
0x180021f8e  call    cs:__imp_CloseHandle
0x180021f94  mov     eax, ebx
0x180021f96  mov     rcx, [rbp+370h+var_50]
0x180021f9d  xor     rcx, rsp; StackCookie
0x180021fa0  call    __security_check_cookie
0x180021fa5  add     rsp, 438h
0x180021fac  pop     r15
0x180021fae  pop     r14
0x180021fb0  pop     r13
0x180021fb2  pop     r12
0x180021fb4  pop     rdi
0x180021fb5  pop     rsi
0x180021fb6  pop     rbx
0x180021fb7  pop     rbp
0x180021fb8  retn
```
