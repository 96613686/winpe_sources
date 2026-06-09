# ReportCrash(ulong,ulong,void *,void *,void * *,ulong,ulong,int,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180022d54`
- end: `0x180023200`
- name: `?ReportCrash@@YAJKKPEAX0PEAPEAXKKHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@2@Z`
- size: `1196`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001ad28`

## callees

- `0x180007cf8`
- `0x180011ef8`
- `0x180013df4`
- `0x180022d54`
- `0x180023208`
- `0x18002c9dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002316b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002317d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002316b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002317d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800231b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800231b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022db7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022dd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022fbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022fea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022fff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023013`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023027`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022db7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022dd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022fbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022fea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022fff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023013`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023027`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800231a7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800231a7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022dfc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022e29`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022e5e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002304e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022dfc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022e29`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022e5e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002304e`
- `ntdll!RtlSetThreadErrorMode` at `0x180022de3`
- `ntdll!RtlSetThreadErrorMode` at `0x180022fd5`
- `ntdll!RtlSetThreadErrorMode` at `0x180022de3`
- `ntdll!RtlSetThreadErrorMode` at `0x180022fd5`
- `faultrep!WerpInitiateCrashReporting` at `0x1800230dc`
- `faultrep!WerpInitiateCrashReporting` at `0x1800230dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ReportCrash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        int a8,
        void **a9,
        void **a10)
{
  DWORD v11; // esi
  char *v12; // r13
  void **v13; // r14
  void *v14; // rcx
  void **v15; // r15
  void *v16; // rcx
  HANDLE v17; // rdi
  HANDLE v18; // rbx
  signed int LastError; // eax
  signed int ProtectedProcessInfo; // ebx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  HANDLE v24; // rax
  void *v25; // rcx
  HANDLE v26; // rax
  void *v27; // rcx
  signed int v29; // eax
  __int64 v30; // rax
  HANDLE *v31; // r12
  HANDLE CurrentProcess; // rsi
  HANDLE v33; // rbx
  HANDLE v34; // rax
  signed int v35; // eax
  HANDLE hSourceHandle; // [rsp+50h] [rbp-28h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-20h] BYREF
  HANDLE v38; // [rsp+60h] [rbp-18h]
  __int64 v39; // [rsp+68h] [rbp-10h]
  DWORD dwProcessId; // [rsp+C0h] [rbp+48h]
  int v41; // [rsp+C8h] [rbp+50h] BYREF
  ULONG OldMode; // [rsp+D0h] [rbp+58h] BYREF
  __int64 v43; // [rsp+D8h] [rbp+60h]

  v43 = a4;
  dwProcessId = a1;
  v11 = a2;
  OldMode = 0;
  v12 = 0;
  v39 = 0;
  v38 = 0;
  hSourceHandle = 0;
  hObject = 0;
  if ( !(_DWORD)a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3, a4);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3, a4);
  v13 = a9;
  v14 = *a9;
  *a9 = 0;
  if ( (unsigned __int64)v14 + 1 > 1 )
    CloseHandle(v14);
  v15 = a10;
  v16 = *a10;
  *a10 = 0;
  if ( (unsigned __int64)v16 + 1 > 1 )
    CloseHandle(v16);
  LODWORD(a9) = RtlSetThreadErrorMode(0x50u, &OldMode);
  v17 = OpenProcess(0x1FFFFFu, 1, v11);
  v38 = v17;
  if ( (unsigned __int64)v17 + 1 <= 1 && GetLastError() == 5 )
  {
    v17 = OpenProcess(0x1001u, 1, v11);
    v38 = v17;
    v18 = v17;
  }
  else
  {
    v18 = v17;
  }
  if ( (unsigned __int64)v18 + 1 <= 1 && GetLastError() == 5 )
  {
    v17 = OpenProcess(0x1000u, 1, v11);
    v38 = v17;
    v18 = v17;
  }
  if ( (unsigned __int64)v18 + 1 <= 1 )
  {
    LastError = GetLastError();
    ProtectedProcessInfo = LastError;
    if ( LastError > 0 )
      ProtectedProcessInfo = (unsigned __int16)LastError | 0x80070000;
    if ( ProtectedProcessInfo >= 0 )
      ProtectedProcessInfo = -2147467259;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 78;
LABEL_24:
      v23 = (unsigned int)ProtectedProcessInfo;
LABEL_25:
      WPP_SF_d(v21[2], v22, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, v23);
      goto LABEL_37;
    }
    goto LABEL_37;
  }
  v41 = 0;
  ProtectedProcessInfo = UtilGetProtectedProcessInfo(
                           v17,
                           (enum _PS_PROTECTED_TYPE *)&v41,
                           (enum _PS_PROTECTED_SIGNER *)&a10);
  if ( ProtectedProcessInfo < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids,
        (unsigned int)ProtectedProcessInfo);
    goto LABEL_37;
  }
  if ( v41 )
  {
    ReportCrashProtected(v17, dwProcessId, v11, a3, v43, a5, a6, a7, a8, &hSourceHandle);
    goto LABEL_32;
  }
  v12 = (char *)OpenProcess(0x1FFFFFu, 1, dwProcessId);
  if ( v12 != (char *)-1LL && v12 + 1 != (char *)1 )
  {
    v30 = tlx::replace<tlx::file_handle_traits>(&hSourceHandle);
    ProtectedProcessInfo = WerpInitiateCrashReporting(v17, v12, a3, a5, a6, 0, 1, v30);
    if ( ProtectedProcessInfo < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v22 = 81;
        goto LABEL_24;
      }
      goto LABEL_37;
    }
    if ( hSourceHandle == (HANDLE)-1LL || (char *)hSourceHandle + 1 == HANDLE_FLAG_INHERIT )
    {
      ProtectedProcessInfo = -2147024890;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v22 = 82;
        v23 = 2147942406LL;
        goto LABEL_25;
      }
      goto LABEL_37;
    }
    v31 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&hObject);
    if ( a8 )
      CurrentProcess = GetCurrentProcess();
    else
      CurrentProcess = v12;
    v33 = hSourceHandle;
    v34 = GetCurrentProcess();
    if ( !DuplicateHandle(v34, v33, CurrentProcess, v31, 0x100000u, 0, 0) )
    {
      v35 = GetLastError();
      ProtectedProcessInfo = v35;
      if ( v35 > 0 )
        ProtectedProcessInfo = (unsigned __int16)v35 | 0x80070000;
      if ( ProtectedProcessInfo >= 0 )
        ProtectedProcessInfo = -2147467259;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v22 = 83;
        goto LABEL_24;
      }
      goto LABEL_37;
    }
LABEL_32:
    v24 = hSourceHandle;
    hSourceHandle = 0;
    v25 = *v13;
    *v13 = v24;
    if ( (unsigned __int64)v25 + 1 > 1 )
      CloseHandle(v25);
    v26 = hObject;
    hObject = 0;
    v27 = *v15;
    *v15 = v26;
    if ( (unsigned __int64)v27 + 1 > 1 )
      CloseHandle(v27);
    ProtectedProcessInfo = 0;
    goto LABEL_37;
  }
  v29 = GetLastError();
  ProtectedProcessInfo = v29;
  if ( v29 > 0 )
    ProtectedProcessInfo = (unsigned __int16)v29 | 0x80070000;
  if ( ProtectedProcessInfo >= 0 )
    ProtectedProcessInfo = -2147467259;
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v22 = 80;
    goto LABEL_24;
  }
LABEL_37:
  if ( (int)a9 >= 0 )
    RtlSetThreadErrorMode(OldMode, 0);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( (unsigned __int64)hSourceHandle + 1 > 1 )
    CloseHandle(hSourceHandle);
  if ( (unsigned __int64)v17 + 1 > 1 )
    CloseHandle(v17);
  if ( (unsigned __int64)(v12 + 1) > 1 )
    CloseHandle(v12);
  return (unsigned int)ProtectedProcessInfo;
}

```

## disassembly

```asm
0x180022d54  mov     [rsp-40h+arg_18], r9
0x180022d59  mov     [rsp-40h+dwProcessId], ecx
0x180022d5d  push    rbp
0x180022d5e  push    rbx
0x180022d5f  push    rsi
0x180022d60  push    rdi
0x180022d61  push    r12
0x180022d63  push    r13
0x180022d65  push    r14
0x180022d67  push    r15
0x180022d69  mov     rbp, rsp
0x180022d6c  sub     rsp, 78h
0x180022d70  mov     r12, r8
0x180022d73  mov     esi, edx
0x180022d75  xor     ebx, ebx
0x180022d77  mov     [rbp+OldMode], ebx
0x180022d7a  mov     r13d, ebx
0x180022d7d  mov     [rbp+var_10], rbx
0x180022d81  mov     [rbp+var_18], rbx
0x180022d85  mov     [rbp+hSourceHandle], rbx
0x180022d89  mov     [rbp+hObject], rbx
0x180022d8d  test    edx, edx
0x180022d8f  jnz     short loc_180022D96
0x180022d91  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180022d96  test    r12, r12
0x180022d99  jnz     short loc_180022DA0
0x180022d9b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180022da0  mov     r14, [rbp+arg_40]
0x180022da7  mov     rcx, [r14]; hObject
0x180022daa  mov     [r14], rbx
0x180022dad  lea     rax, [rcx+1]
0x180022db1  cmp     rax, 1
0x180022db5  jbe     short loc_180022DBD
0x180022db7  call    cs:__imp_CloseHandle
0x180022dbd  mov     r15, [rbp+arg_48]
0x180022dc4  mov     rcx, [r15]; hObject
0x180022dc7  mov     [r15], rbx
0x180022dca  lea     rax, [rcx+1]
0x180022dce  cmp     rax, 1
0x180022dd2  jbe     short loc_180022DDA
0x180022dd4  call    cs:__imp_CloseHandle
0x180022dda  lea     rdx, [rbp+OldMode]; OldMode
0x180022dde  mov     ecx, 50h ; 'P'; NewMode
0x180022de3  call    cs:__imp_RtlSetThreadErrorMode
0x180022de9  mov     dword ptr [rbp+arg_40], eax
0x180022def  mov     r8d, esi; dwProcessId
0x180022df2  mov     edx, 1; bInheritHandle
0x180022df7  mov     ecx, 1FFFFFh; dwDesiredAccess
0x180022dfc  call    cs:__imp_OpenProcess
0x180022e02  mov     rdi, rax
0x180022e05  mov     [rbp+var_18], rax
0x180022e09  lea     rcx, [rax+1]
0x180022e0d  cmp     rcx, 1
0x180022e11  ja      short loc_180022E3B
0x180022e13  call    cs:__imp_GetLastError
0x180022e19  cmp     eax, 5
0x180022e1c  jnz     short loc_180022E3B
0x180022e1e  mov     r8d, esi; dwProcessId
0x180022e21  lea     edx, [rax-4]; bInheritHandle
0x180022e24  mov     ecx, 1001h; dwDesiredAccess
0x180022e29  call    cs:__imp_OpenProcess
0x180022e2f  mov     rdi, rax
0x180022e32  mov     [rbp+var_18], rax
0x180022e36  mov     rbx, rax
0x180022e39  jmp     short loc_180022E3E
0x180022e3b  mov     rbx, rdi
0x180022e3e  lea     rax, [rbx+1]
0x180022e42  cmp     rax, 1
0x180022e46  ja      short loc_180022E6E
0x180022e48  call    cs:__imp_GetLastError
0x180022e4e  cmp     eax, 5
0x180022e51  jnz     short loc_180022E6E
0x180022e53  mov     r8d, esi; dwProcessId
0x180022e56  lea     edx, [rax-4]; bInheritHandle
0x180022e59  mov     ecx, 1000h; dwDesiredAccess
0x180022e5e  call    cs:__imp_OpenProcess
0x180022e64  mov     rdi, rax
0x180022e67  mov     [rbp+var_18], rax
0x180022e6b  mov     rbx, rax
0x180022e6e  lea     rax, [rbx+1]
0x180022e72  cmp     rax, 1
0x180022e76  ja      short loc_180022ED5
0x180022e78  call    cs:__imp_GetLastError
0x180022e7e  mov     ebx, eax
0x180022e80  test    eax, eax
0x180022e82  jle     short loc_180022E8D
0x180022e84  movzx   ebx, ax
0x180022e87  or      ebx, 80070000h
0x180022e8d  mov     eax, 80004005h
0x180022e92  test    ebx, ebx
0x180022e94  cmovns  ebx, eax
0x180022e97  lea     rax, WPP_GLOBAL_Control
0x180022e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ea5  cmp     rcx, rax
0x180022ea8  jz      loc_180022FC7
0x180022eae  test    byte ptr [rcx+1Ch], 1
0x180022eb2  jz      loc_180022FC7
0x180022eb8  mov     edx, 4Eh ; 'N'
0x180022ebd  mov     r9d, ebx
0x180022ec0  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x180022ec7  mov     rcx, [rcx+10h]
0x180022ecb  call    WPP_SF_d
0x180022ed0  jmp     loc_180022FC7
0x180022ed5  mov     [rbp+arg_8], 0
0x180022edc  lea     r8, [rbp+arg_48]; enum _PS_PROTECTED_SIGNER *
0x180022ee3  lea     rdx, [rbp+arg_8]; enum _PS_PROTECTED_TYPE *
0x180022ee7  mov     rcx, rdi; void *
0x180022eea  call    ?UtilGetProtectedProcessInfo@@YAJPEAXPEAW4_PS_PROTECTED_TYPE@@PEAW4_PS_PROTECTED_SIGNER@@@Z; UtilGetProtectedProcessInfo(void *,_PS_PROTECTED_TYPE *,_PS_PROTECTED_SIGNER *)
0x180022eef  mov     ebx, eax
0x180022ef1  test    eax, eax
0x180022ef3  jns     short loc_180022F33
0x180022ef5  lea     rax, WPP_GLOBAL_Control
0x180022efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f03  cmp     rcx, rax
0x180022f06  jz      loc_180022FC7
0x180022f0c  test    byte ptr [rcx+1Ch], 1
0x180022f10  jz      loc_180022FC7
0x180022f16  mov     edx, 4Fh ; 'O'
0x180022f1b  mov     r9d, ebx
0x180022f1e  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x180022f25  mov     rcx, [rcx+10h]
0x180022f29  call    WPP_SF_d
0x180022f2e  jmp     loc_180022FC7
0x180022f33  cmp     [rbp+arg_8], 0
0x180022f37  jz      loc_180023040
0x180022f3d  lea     rax, [rbp+hSourceHandle]
0x180022f41  mov     [rsp+78h+var_30], rax; __int64
0x180022f46  mov     eax, [rbp+arg_38]
0x180022f4c  mov     [rsp+78h+var_38], eax; int
0x180022f50  mov     eax, [rbp+arg_30]
0x180022f53  mov     [rsp+78h+var_40], eax; int
0x180022f57  mov     eax, [rbp+arg_28]
0x180022f5a  mov     [rsp+78h+dwOptions], eax; int
0x180022f5e  mov     rax, [rbp+arg_20]
0x180022f62  mov     qword ptr [rsp+78h+bInheritHandle], rax; __int64
0x180022f67  mov     rax, [rbp+arg_18]
0x180022f6b  mov     qword ptr [rsp+78h+dwDesiredAccess], rax; __int64
0x180022f70  mov     r9, r12
0x180022f73  mov     r8d, esi
0x180022f76  mov     edx, [rbp+dwProcessId]
0x180022f79  mov     rcx, rdi; Process
0x180022f7c  call    ?ReportCrashProtected@@YAJPEAXKK00PEAPEAXKKHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; ReportCrashProtected(void *,ulong,ulong,void *,void *,void * *,ulong,ulong,int,tlx::unique_any<tlx::file_handle_traits> *)
0x180022f81  mov     rax, [rbp+hSourceHandle]
0x180022f85  mov     [rbp+hSourceHandle], 0
0x180022f8d  mov     rcx, [r14]; hObject
0x180022f90  mov     [r14], rax
0x180022f93  lea     rax, [rcx+1]
0x180022f97  cmp     rax, 1
0x180022f9b  jbe     short loc_180022FA3
0x180022f9d  call    cs:__imp_CloseHandle
0x180022fa3  mov     rax, [rbp+hObject]
0x180022fa7  mov     [rbp+hObject], 0
0x180022faf  mov     rcx, [r15]; hObject
0x180022fb2  mov     [r15], rax
0x180022fb5  lea     rax, [rcx+1]
0x180022fb9  cmp     rax, 1
0x180022fbd  jbe     short loc_180022FC5
0x180022fbf  call    cs:__imp_CloseHandle
0x180022fc5  xor     ebx, ebx
0x180022fc7  cmp     dword ptr [rbp+arg_40], 0
0x180022fce  jl      short loc_180022FDC
0x180022fd0  xor     edx, edx; OldMode
0x180022fd2  mov     ecx, [rbp+OldMode]; NewMode
0x180022fd5  call    cs:__imp_RtlSetThreadErrorMode
0x180022fdb  nop
0x180022fdc  mov     rcx, [rbp+hObject]; hObject
0x180022fe0  lea     rax, [rcx+1]
0x180022fe4  cmp     rax, 1
0x180022fe8  jbe     short loc_180022FF1
0x180022fea  call    cs:__imp_CloseHandle
0x180022ff0  nop
0x180022ff1  mov     rcx, [rbp+hSourceHandle]; hObject
0x180022ff5  lea     rax, [rcx+1]
0x180022ff9  cmp     rax, 1
0x180022ffd  jbe     short loc_180023006
0x180022fff  call    cs:__imp_CloseHandle
0x180023005  nop
0x180023006  lea     rax, [rdi+1]
0x18002300a  cmp     rax, 1
0x18002300e  jbe     short loc_18002301A
0x180023010  mov     rcx, rdi; hObject
0x180023013  call    cs:__imp_CloseHandle
0x180023019  nop
0x18002301a  lea     rax, [r13+1]
0x18002301e  cmp     rax, 1
0x180023022  jbe     short loc_18002302D
0x180023024  mov     rcx, r13; hObject
0x180023027  call    cs:__imp_CloseHandle
0x18002302d  mov     eax, ebx
0x18002302f  add     rsp, 78h
0x180023033  pop     r15
0x180023035  pop     r14
0x180023037  pop     r13
0x180023039  pop     r12
0x18002303b  pop     rdi
0x18002303c  pop     rsi
0x18002303d  pop     rbx
0x18002303e  pop     rbp
0x18002303f  retn
0x180023040  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x180023044  mov     edx, 1; bInheritHandle
0x180023049  mov     ecx, 1FFFFFh; dwDesiredAccess
0x18002304e  call    cs:__imp_OpenProcess
0x180023054  mov     r13, rax
0x180023057  inc     rax
0x18002305a  cmp     rax, 1
0x18002305e  ja      short loc_1800230AA
0x180023060  call    cs:__imp_GetLastError
0x180023066  mov     ebx, eax
0x180023068  test    eax, eax
0x18002306a  jle     short loc_180023075
0x18002306c  movzx   ebx, ax
0x18002306f  or      ebx, 80070000h
0x180023075  mov     eax, 80004005h
0x18002307a  test    ebx, ebx
0x18002307c  cmovns  ebx, eax
0x18002307f  lea     rax, WPP_GLOBAL_Control
0x180023086  mov     rcx, cs:WPP_GLOBAL_Control
0x18002308d  cmp     rcx, rax
0x180023090  jz      loc_180022FC7
0x180023096  test    byte ptr [rcx+1Ch], 1
0x18002309a  jz      loc_180022FC7
0x1800230a0  mov     edx, 50h ; 'P'
0x1800230a5  jmp     loc_180022EBD
0x1800230aa  lea     rcx, [rbp+hSourceHandle]
0x1800230ae  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800230b3  mov     qword ptr [rsp+78h+var_40], rax
0x1800230b8  mov     [rsp+78h+dwOptions], 1
0x1800230c0  mov     [rsp+78h+bInheritHandle], 0
0x1800230c8  mov     eax, [rbp+arg_28]
0x1800230cb  mov     [rsp+78h+dwDesiredAccess], eax
0x1800230cf  mov     r9, [rbp+arg_20]
0x1800230d3  mov     r8, r12
0x1800230d6  mov     rdx, r13
0x1800230d9  mov     rcx, rdi
0x1800230dc  call    cs:__imp_WerpInitiateCrashReporting
0x1800230e2  mov     ebx, eax
0x1800230e4  test    eax, eax
0x1800230e6  jns     short loc_180023113
0x1800230e8  lea     rax, WPP_GLOBAL_Control
0x1800230ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800230f6  cmp     rcx, rax
0x1800230f9  jz      loc_180022FC7
0x1800230ff  test    byte ptr [rcx+1Ch], 1
0x180023103  jz      loc_180022FC7
0x180023109  mov     edx, 51h ; 'Q'
0x18002310e  jmp     loc_180022EBD
0x180023113  mov     rax, [rbp+hSourceHandle]
0x180023117  inc     rax
0x18002311a  cmp     rax, 1
0x18002311e  ja      short loc_180023156
0x180023120  mov     ebx, 80070006h
0x180023125  lea     rax, WPP_GLOBAL_Control
0x18002312c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023133  cmp     rcx, rax
0x180023136  jz      loc_180022FC7
0x18002313c  test    byte ptr [rcx+1Ch], 1
0x180023140  jz      loc_180022FC7
0x180023146  mov     edx, 52h ; 'R'
0x18002314b  mov     r9d, 80070006h
0x180023151  jmp     loc_180022EC0
0x180023156  lea     rcx, [rbp+hObject]
0x18002315a  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18002315f  mov     r12, rax
0x180023162  cmp     [rbp+arg_38], 0
0x180023169  jz      short loc_180023176
0x18002316b  call    cs:__imp_GetCurrentProcess
0x180023171  mov     rsi, rax
0x180023174  jmp     short loc_180023179
0x180023176  mov     rsi, r13
0x180023179  mov     rbx, [rbp+hSourceHandle]
0x18002317d  call    cs:__imp_GetCurrentProcess
0x180023183  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18002318b  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x180023193  mov     [rsp+78h+dwDesiredAccess], 100000h; dwDesiredAccess
0x18002319b  mov     r9, r12; lpTargetHandle
0x18002319e  mov     r8, rsi; hTargetProcessHandle
0x1800231a1  mov     rdx, rbx; hSourceHandle
0x1800231a4  mov     rcx, rax; hSourceProcessHandle
0x1800231a7  call    cs:__imp_DuplicateHandle
0x1800231ad  test    eax, eax
0x1800231af  jnz     loc_180022F81
0x1800231b5  call    cs:__imp_GetLastError
0x1800231bb  mov     ebx, eax
0x1800231bd  test    eax, eax
0x1800231bf  jle     short loc_1800231CA
0x1800231c1  movzx   ebx, ax
0x1800231c4  or      ebx, 80070000h
0x1800231ca  mov     eax, 80004005h
0x1800231cf  test    ebx, ebx
0x1800231d1  cmovns  ebx, eax
0x1800231d4  lea     rax, WPP_GLOBAL_Control
0x1800231db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231e2  cmp     rcx, rax
0x1800231e5  jz      loc_180022FC7
0x1800231eb  test    byte ptr [rcx+1Ch], 1
0x1800231ef  jz      loc_180022FC7
0x1800231f5  mov     edx, 53h ; 'S'
0x1800231fa  jmp     loc_180022EBD
```
