# CWerService::TryCaptureSnapshot(ulong,ulong,unsigned __int64,ushort)

- ea: `0x18001a6d8`
- end: `0x18001ad22`
- name: `?TryCaptureSnapshot@CWerService@@AEAAJKK_KG@Z`
- size: `1610`
- prototype: `int __fastcall(CWerService *this, DWORD, DWORD, void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180016ac0`
- `0x180019d10`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x1800035e8`
- `0x180006134`
- `0x180007cf8`
- `0x18000f6e8`
- `0x180011b3c`
- `0x180011ef8`
- `0x18001a6d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001a83c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001a83c`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001a9c1`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001aa02`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001a9c1`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001aa02`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18001aad9`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18001ac9a`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18001aad9`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18001ac9a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001abc6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001abc6`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001aaae`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001aaae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001a7b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001a7b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aabc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001abdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aabc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001abdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac3d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001ac28`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001ac28`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18001a7a3`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18001a7a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a781`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a94c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aa49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aa59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aa7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aafd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001abd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001acbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001acce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001acf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a781`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a94c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aa49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aa59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aa7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aafd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001abd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001acbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001acce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001acf0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001a866`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001a866`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a73e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a813`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a73e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a813`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall CWerService::TryCaptureSnapshot(CWerService *this, DWORD a2, DWORD a3, void *a4)
{
  bool v7; // si
  HANDLE v8; // rax
  void *v9; // rbx
  UINT SystemDirectoryW; // eax
  int result; // eax
  HANDLE v12; // r14
  HANDLE *v13; // rbx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v16; // ebx
  HANDLE v17; // rcx
  bool v18; // cc
  size_t v19; // rbx
  LPPROC_THREAD_ATTRIBUTE_LIST v20; // rsi
  struct _PROC_THREAD_ATTRIBUTE_LIST *v21; // rbx
  signed int v22; // eax
  unsigned int v23; // edi
  signed int v24; // eax
  DWORD v25; // edi
  BOOL v26; // edi
  signed int v27; // eax
  signed int v28; // edi
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  DWORD v31; // eax
  signed int v32; // eax
  unsigned __int16 Value[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v34; // [rsp+64h] [rbp-9Ch] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION hHandle; // [rsp+70h] [rbp-90h] BYREF
  ULONG_PTR Size; // [rsp+88h] [rbp-78h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-60h]
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v41; // [rsp+118h] [rbp+18h]
  WCHAR Buffer[264]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR ApplicationName[264]; // [rsp+330h] [rbp+230h] BYREF
  WCHAR CommandLine[264]; // [rsp+540h] [rbp+440h] BYREF

  memset_0(Buffer, 0, 0x208u);
  Value[0] = 0;
  v34 = 0;
  v7 = 0;
  v8 = OpenProcess(0x1000u, 0, a2);
  v9 = v8;
  if ( (unsigned __int64)v8 + 1 > 1 )
  {
    UtilGetProcessArchitecture(v8, Value, &v34);
    if ( Value[0] == 0x8664 )
      v7 = v34 == 0xAA64;
    CloseHandle(v9);
  }
  if ( !Value[0] || v7 )
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  else
    SystemDirectoryW = GetSystemWow64Directory2W(Buffer, 260);
  if ( !SystemDirectoryW )
    goto LABEL_10;
  result = StringCchPrintfW(ApplicationName, 0x104u, L"%ws\\%ws", Buffer, L"WerFault.exe");
  if ( result < 0 )
    return result;
  v12 = OpenProcess(0x1040u, 0, a3);
  if ( (unsigned __int64)v12 + 1 <= 1 )
  {
LABEL_10:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  hObject = 0;
  v13 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&hObject);
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(v12, a4, CurrentProcess, v13, 6u, 1, 0) )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( v16 >= 0 )
      v16 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        176,
        WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
        (unsigned int)v16);
    v17 = hObject;
    v18 = (unsigned __int64)hObject + 1 <= 1;
    goto LABEL_25;
  }
  v16 = StringCchPrintfW(
          CommandLine,
          0x104u,
          L"%ws %ws %ws %Iu %ws %u %ws %u",
          ApplicationName,
          L"-pss",
          L"-s",
          hObject,
          L"-p",
          a2,
          L"-ip",
          a3);
  if ( v16 < 0 )
  {
    v17 = hObject;
    v18 = (unsigned __int64)hObject + 1 <= 1;
LABEL_25:
    if ( !v18 )
      CloseHandle(v17);
LABEL_57:
    CloseHandle(v12);
    return v16;
  }
  memset_0(&StartupInfo, 0, 0x70u);
  StartupInfo.cb = 112;
  StartupInfo.wShowWindow = 0;
  v39 = -1;
  StartupInfo.lpDesktop = (LPWSTR)&dword_180039414;
  StartupInfo.dwFlags = 1;
  memset(&hHandle, 0, sizeof(hHandle));
  *(__m128i *)lpAttributeList = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( v7 )
  {
    Size = 0;
    InitializeProcThreadAttributeList(0, 1u, 0, &Size);
    v19 = Size;
    if ( Size )
    {
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(lpAttributeList, Size) )
      {
        if ( lpAttributeList[0] != (LPPROC_THREAD_ATTRIBUTE_LIST)-1LL )
          operator delete(lpAttributeList[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( hHandle.hProcess )
          CloseHandle(hHandle.hProcess);
        if ( hHandle.hThread )
          CloseHandle(hHandle.hThread);
        memset(&hHandle, 0, sizeof(hHandle));
        if ( (unsigned __int64)hObject + 1 > 1 )
          CloseHandle(hObject);
        v16 = -2147024882;
        goto LABEL_57;
      }
      memset_0(lpAttributeList[1], 0, v19);
    }
    v20 = lpAttributeList[0];
    v21 = lpAttributeList[0];
    if ( !InitializeProcThreadAttributeList(lpAttributeList[0], 1u, 0, &Size) )
    {
      v22 = GetLastError();
      v23 = v22;
      if ( v22 > 0 )
        v23 = (unsigned __int16)v22 | 0x80070000;
      goto LABEL_48;
    }
    if ( !UpdateProcThreadAttribute(v21, 0, 0x20019u, Value, 2u, 0, 0) )
    {
      v24 = GetLastError();
      v23 = v24;
      if ( v24 > 0 )
        v23 = (unsigned __int16)v24 | 0x80070000;
      if ( !v21 )
        goto LABEL_49;
      DeleteProcThreadAttributeList(v21);
LABEL_48:
      if ( v21 == (struct _PROC_THREAD_ATTRIBUTE_LIST *)-1LL )
      {
LABEL_50:
        if ( hHandle.hProcess )
          CloseHandle(hHandle.hProcess);
        if ( hHandle.hThread )
          CloseHandle(hHandle.hThread);
        memset(&hHandle, 0, sizeof(hHandle));
        if ( (unsigned __int64)hObject + 1 > 1 )
          CloseHandle(hObject);
        v16 = v23;
        goto LABEL_57;
      }
LABEL_49:
      operator delete(v20, (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_50;
    }
    v25 = 525312;
    v41 = v21;
  }
  else
  {
    v20 = lpAttributeList[0];
    v25 = 1024;
    v21 = 0;
  }
  if ( hHandle.hProcess )
    CloseHandle(hHandle.hProcess);
  if ( hHandle.hThread )
    CloseHandle(hHandle.hThread);
  memset(&hHandle, 0, sizeof(hHandle));
  v26 = CreateProcessW(ApplicationName, CommandLine, 0, 0, 1, v25, 0, 0, &StartupInfo, &hHandle);
  CloseHandle(v12);
  if ( !v26 )
  {
    v27 = GetLastError();
    v28 = v27;
    if ( v27 > 0 )
      v28 = (unsigned __int16)v27 | 0x80070000;
    if ( v28 >= 0 )
      v28 = -2147467259;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_84;
    v30 = 177;
    goto LABEL_82;
  }
  v31 = WaitForSingleObject(hHandle.hProcess, 0xFFFFFFFF);
  if ( !v31 )
  {
    v28 = 0;
    goto LABEL_84;
  }
  if ( v31 == -1 )
  {
    v32 = GetLastError();
    v28 = v32;
    if ( v32 > 0 )
      v28 = (unsigned __int16)v32 | 0x80070000;
    if ( v28 >= 0 )
      v28 = -2147467259;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_84;
    v30 = 178;
LABEL_82:
    WPP_SF_d(v29[2], v30, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, (unsigned int)v28);
    goto LABEL_84;
  }
  v28 = -2147418113;
LABEL_84:
  if ( v21 )
    DeleteProcThreadAttributeList(v21);
  if ( v20 != (LPPROC_THREAD_ATTRIBUTE_LIST)-1LL )
    operator delete(v20, (const struct std::nothrow_t *)&std::nothrow);
  if ( hHandle.hProcess )
    CloseHandle(hHandle.hProcess);
  if ( hHandle.hThread )
    CloseHandle(hHandle.hThread);
  memset(&hHandle, 0, sizeof(hHandle));
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return v28;
}

```

## disassembly

```asm
0x18001a6d8  mov     [rsp-8+arg_0], rbx
0x18001a6dd  push    rbp
0x18001a6de  push    rsi
0x18001a6df  push    rdi
0x18001a6e0  push    r12
0x18001a6e2  push    r13
0x18001a6e4  push    r14
0x18001a6e6  push    r15
0x18001a6e8  lea     rbp, [rsp-660h]
0x18001a6f0  sub     rsp, 760h
0x18001a6f7  mov     rax, cs:__security_cookie
0x18001a6fe  xor     rax, rsp
0x18001a701  mov     [rbp+690h+var_40], rax
0x18001a708  mov     r15d, r8d
0x18001a70b  lea     rcx, [rbp+690h+Buffer]; void *
0x18001a70f  mov     r12d, edx
0x18001a712  mov     r8d, 208h; Size
0x18001a718  xor     edx, edx; Val
0x18001a71a  mov     r13, r9
0x18001a71d  call    memset_0
0x18001a722  xor     r14d, r14d
0x18001a725  mov     r8d, r12d; dwProcessId
0x18001a728  xor     edx, edx; bInheritHandle
0x18001a72a  mov     [rsp+790h+Value], r14w
0x18001a730  mov     ecx, 1000h; dwDesiredAccess
0x18001a735  mov     [rsp+790h+var_72C], r14w
0x18001a73b  mov     sil, r14b
0x18001a73e  call    cs:__imp_OpenProcess
0x18001a744  mov     rbx, rax
0x18001a747  lea     rcx, [rax+1]
0x18001a74b  cmp     rcx, 1
0x18001a74f  jbe     short loc_18001A787
0x18001a751  lea     r8, [rsp+790h+var_72C]; unsigned __int16 *
0x18001a756  mov     rcx, rax; void *
0x18001a759  lea     rdx, [rsp+790h+Value]; unsigned __int16 *
0x18001a75e  call    ?UtilGetProcessArchitecture@@YAJPEAXPEAG1@Z; UtilGetProcessArchitecture(void *,ushort *,ushort *)
0x18001a763  mov     eax, 8664h
0x18001a768  cmp     [rsp+790h+Value], ax
0x18001a76d  jnz     short loc_18001A77E
0x18001a76f  mov     eax, 0AA64h
0x18001a774  cmp     [rsp+790h+var_72C], ax
0x18001a779  jnz     short loc_18001A77E
0x18001a77b  mov     sil, 1
0x18001a77e  mov     rcx, rbx; hObject
0x18001a781  call    cs:__imp_CloseHandle
0x18001a787  movzx   r8d, [rsp+790h+Value]
0x18001a78d  test    r8w, r8w
0x18001a791  jz      short loc_18001A7AB
0x18001a793  test    sil, sil
0x18001a796  jnz     short loc_18001A7AB
0x18001a798  mov     edi, 104h
0x18001a79d  lea     rcx, [rbp+690h+Buffer]
0x18001a7a1  mov     edx, edi
0x18001a7a3  call    cs:__imp_GetSystemWow64Directory2W
0x18001a7a9  jmp     short loc_18001A7BC
0x18001a7ab  mov     edi, 104h
0x18001a7b0  lea     rcx, [rbp+690h+Buffer]; lpBuffer
0x18001a7b4  mov     edx, edi; uSize
0x18001a7b6  call    cs:__imp_GetSystemDirectoryW
0x18001a7bc  test    eax, eax
0x18001a7be  jnz     short loc_18001A7DB
0x18001a7c0  call    cs:__imp_GetLastError
0x18001a7c6  test    eax, eax
0x18001a7c8  jle     loc_18001ACF8
0x18001a7ce  movzx   eax, ax
0x18001a7d1  or      eax, 80070000h
0x18001a7d6  jmp     loc_18001ACF8
0x18001a7db  lea     rax, aWerfaultExe_0; "WerFault.exe"
0x18001a7e2  mov     rdx, rdi; unsigned __int64
0x18001a7e5  lea     r9, [rbp+690h+Buffer]
0x18001a7e9  mov     qword ptr [rsp+790h+dwDesiredAccess], rax
0x18001a7ee  lea     r8, aWsWs; "%ws\\%ws"
0x18001a7f5  lea     rcx, [rbp+690h+ApplicationName]; wchar_t *
0x18001a7fc  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001a801  test    eax, eax
0x18001a803  js      loc_18001ACF8
0x18001a809  mov     r8d, r15d; dwProcessId
0x18001a80c  xor     edx, edx; bInheritHandle
0x18001a80e  mov     ecx, 1040h; dwDesiredAccess
0x18001a813  call    cs:__imp_OpenProcess
0x18001a819  mov     r14, rax
0x18001a81c  lea     rcx, [rax+1]
0x18001a820  cmp     rcx, 1
0x18001a824  jbe     short loc_18001A7C0
0x18001a826  lea     rcx, [rsp+790h+hObject]
0x18001a82b  mov     [rsp+790h+hObject], 0
0x18001a834  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18001a839  mov     rbx, rax
0x18001a83c  call    cs:__imp_GetCurrentProcess
0x18001a842  mov     [rsp+790h+dwOptions], 0; dwOptions
0x18001a84a  mov     r9, rbx; lpTargetHandle
0x18001a84d  mov     r8, rax; hTargetProcessHandle
0x18001a850  mov     [rsp+790h+bInheritHandle], 1; bInheritHandle
0x18001a858  mov     rdx, r13; hSourceHandle
0x18001a85b  mov     [rsp+790h+dwDesiredAccess], 6; dwDesiredAccess
0x18001a863  mov     rcx, r14; hSourceProcessHandle
0x18001a866  call    cs:__imp_DuplicateHandle
0x18001a86c  xor     r13d, r13d
0x18001a86f  test    eax, eax
0x18001a871  jnz     short loc_18001A8D2
0x18001a873  call    cs:__imp_GetLastError
0x18001a879  mov     ebx, eax
0x18001a87b  test    eax, eax
0x18001a87d  jle     short loc_18001A888
0x18001a87f  movzx   ebx, ax
0x18001a882  or      ebx, 80070000h
0x18001a888  test    ebx, ebx
0x18001a88a  mov     eax, 80004005h
0x18001a88f  cmovns  ebx, eax
0x18001a892  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a899  lea     rax, WPP_GLOBAL_Control
0x18001a8a0  cmp     rcx, rax
0x18001a8a3  jz      short loc_18001A8C3
0x18001a8a5  test    byte ptr [rcx+1Ch], 1
0x18001a8a9  jz      short loc_18001A8C3
0x18001a8ab  mov     rcx, [rcx+10h]
0x18001a8af  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001a8b6  mov     edx, 0B0h
0x18001a8bb  mov     r9d, ebx
0x18001a8be  call    WPP_SF_d
0x18001a8c3  mov     rcx, [rsp+790h+hObject]
0x18001a8c8  lea     rax, [rcx+1]
0x18001a8cc  cmp     rax, 1
0x18001a8d0  jmp     short loc_18001A946
0x18001a8d2  mov     [rsp+790h+var_740], r15d
0x18001a8d7  lea     rax, aIp; "-ip"
0x18001a8de  mov     [rsp+790h+lpProcessInformation], rax
0x18001a8e3  lea     r9, [rbp+690h+ApplicationName]
0x18001a8ea  mov     dword ptr [rsp+790h+lpStartupInfo], r12d
0x18001a8ef  lea     rax, aP; "-p"
0x18001a8f6  mov     [rsp+790h+lpCurrentDirectory], rax
0x18001a8fb  lea     r8, aWsWsWsIuWsUWsU; "%ws %ws %ws %Iu %ws %u %ws %u"
0x18001a902  mov     rax, [rsp+790h+hObject]
0x18001a907  lea     rcx, [rbp+690h+CommandLine]; wchar_t *
0x18001a90e  mov     qword ptr [rsp+790h+dwOptions], rax
0x18001a913  mov     rdx, rdi; unsigned __int64
0x18001a916  lea     rax, aS; "-s"
0x18001a91d  mov     qword ptr [rsp+790h+bInheritHandle], rax
0x18001a922  lea     rax, aPss; "-pss"
0x18001a929  mov     qword ptr [rsp+790h+dwDesiredAccess], rax
0x18001a92e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001a933  mov     ebx, eax
0x18001a935  test    eax, eax
0x18001a937  jns     short loc_18001A957
0x18001a939  mov     rcx, [rsp+790h+hObject]; hObject
0x18001a93e  lea     rdx, [rcx+1]
0x18001a942  cmp     rdx, 1
0x18001a946  jbe     loc_18001AB37
0x18001a94c  call    cs:__imp_CloseHandle
0x18001a952  jmp     loc_18001AB37
0x18001a957  mov     ebx, 70h ; 'p'
0x18001a95c  lea     rcx, [rbp+690h+StartupInfo]; void *
0x18001a960  mov     r8d, ebx; Size
0x18001a963  xor     edx, edx; Val
0x18001a965  call    memset_0
0x18001a96a  xor     eax, eax
0x18001a96c  mov     [rbp+690h+StartupInfo.cb], ebx
0x18001a96f  xorps   xmm0, xmm0
0x18001a972  mov     [rbp+690h+var_710], rax
0x18001a976  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001a97a  mov     [rbp+690h+StartupInfo.wShowWindow], r13w
0x18001a97f  mov     [rbp+690h+var_6F0], r12
0x18001a983  lea     rax, dword_180039414
0x18001a98a  mov     [rbp+690h+StartupInfo.lpDesktop], rax
0x18001a98e  lea     r15d, [rbx-6Fh]
0x18001a992  mov     [rbp+690h+StartupInfo.dwFlags], r15d
0x18001a996  movups  xmmword ptr [rsp+790h+hHandle], xmm0
0x18001a99b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18001a9a3  movdqu  xmmword ptr [rbp+690h+lpAttributeList], xmm0
0x18001a9a8  test    sil, sil
0x18001a9ab  jz      loc_18001AB52
0x18001a9b1  lea     r9, [rbp+690h+Size]; lpSize
0x18001a9b5  mov     [rbp+690h+Size], r13
0x18001a9b9  xor     r8d, r8d; dwFlags
0x18001a9bc  mov     edx, r15d; dwAttributeCount
0x18001a9bf  xor     ecx, ecx; lpAttributeList
0x18001a9c1  call    cs:__imp_InitializeProcThreadAttributeList
0x18001a9c7  mov     rbx, [rbp+690h+Size]
0x18001a9cb  test    rbx, rbx
0x18001a9ce  jz      short loc_18001A9EE
0x18001a9d0  mov     rdx, rbx
0x18001a9d3  lea     rcx, [rbp+690h+lpAttributeList]
0x18001a9d7  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x18001a9dc  test    al, al
0x18001a9de  jz      short loc_18001AA2A
0x18001a9e0  mov     rcx, [rbp+690h+lpAttributeList+8]; void *
0x18001a9e4  mov     r8, rbx; Size
0x18001a9e7  xor     edx, edx; Val
0x18001a9e9  call    memset_0
0x18001a9ee  mov     rsi, [rbp+690h+lpAttributeList]
0x18001a9f2  lea     r9, [rbp+690h+Size]; lpSize
0x18001a9f6  mov     rcx, rsi; lpAttributeList
0x18001a9f9  xor     r8d, r8d; dwFlags
0x18001a9fc  mov     edx, r15d; dwAttributeCount
0x18001a9ff  mov     rbx, rsi
0x18001aa02  call    cs:__imp_InitializeProcThreadAttributeList
0x18001aa08  test    eax, eax
0x18001aa0a  jnz     short loc_18001AA8B
0x18001aa0c  call    cs:__imp_GetLastError
0x18001aa12  mov     edi, eax
0x18001aa14  test    eax, eax
0x18001aa16  jle     loc_18001AADF
0x18001aa1c  movzx   edi, ax
0x18001aa1f  or      edi, 80070000h
0x18001aa25  jmp     loc_18001AADF
0x18001aa2a  mov     rcx, [rbp+690h+lpAttributeList]; void *
0x18001aa2e  cmp     rcx, r12
0x18001aa31  jz      short loc_18001AA3F
0x18001aa33  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001aa3a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001aa3f  mov     rcx, [rsp+790h+hHandle]; hObject
0x18001aa44  test    rcx, rcx
0x18001aa47  jz      short loc_18001AA4F
0x18001aa49  call    cs:__imp_CloseHandle
0x18001aa4f  mov     rcx, [rsp+790h+hHandle+8]; hObject
0x18001aa54  test    rcx, rcx
0x18001aa57  jz      short loc_18001AA5F
0x18001aa59  call    cs:__imp_CloseHandle
0x18001aa5f  mov     rcx, [rsp+790h+hObject]; hObject
0x18001aa64  xor     eax, eax
0x18001aa66  mov     [rbp+690h+var_710], rax
0x18001aa6a  xorps   xmm0, xmm0
0x18001aa6d  movups  xmmword ptr [rsp+790h+hHandle], xmm0
0x18001aa72  lea     rax, [rcx+1]
0x18001aa76  cmp     rax, r15
0x18001aa79  jbe     short loc_18001AA81
0x18001aa7b  call    cs:__imp_CloseHandle
0x18001aa81  mov     ebx, 8007000Eh
0x18001aa86  jmp     loc_18001AB37
0x18001aa8b  mov     qword ptr [rsp+790h+dwOptions], r13; lpReturnSize
0x18001aa90  lea     r9, [rsp+790h+Value]; lpValue
0x18001aa95  mov     qword ptr [rsp+790h+bInheritHandle], r13; lpPreviousValue
0x18001aa9a  xor     edx, edx; dwFlags
0x18001aa9c  mov     r8d, 20019h; Attribute
0x18001aaa2  mov     qword ptr [rsp+790h+dwDesiredAccess], 2; cbSize
0x18001aaab  mov     rcx, rbx; lpAttributeList
0x18001aaae  call    cs:__imp_UpdateProcThreadAttribute
0x18001aab4  test    eax, eax
0x18001aab6  jnz     loc_18001AB47
0x18001aabc  call    cs:__imp_GetLastError
0x18001aac2  mov     edi, eax
0x18001aac4  test    eax, eax
0x18001aac6  jle     short loc_18001AAD1
0x18001aac8  movzx   edi, ax
0x18001aacb  or      edi, 80070000h
0x18001aad1  test    rbx, rbx
0x18001aad4  jz      short loc_18001AAE4
0x18001aad6  mov     rcx, rbx; lpAttributeList
0x18001aad9  call    cs:__imp_DeleteProcThreadAttributeList
0x18001aadf  cmp     rbx, r12
0x18001aae2  jz      short loc_18001AAF3
0x18001aae4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001aaeb  mov     rcx, rsi; void *
0x18001aaee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001aaf3  mov     rcx, [rsp+790h+hHandle]; hObject
0x18001aaf8  test    rcx, rcx
0x18001aafb  jz      short loc_18001AB03
0x18001aafd  call    cs:__imp_CloseHandle
0x18001ab03  mov     rcx, [rsp+790h+hHandle+8]; hObject
0x18001ab08  test    rcx, rcx
0x18001ab0b  jz      short loc_18001AB13
0x18001ab0d  call    cs:__imp_CloseHandle
0x18001ab13  mov     rcx, [rsp+790h+hObject]; hObject
0x18001ab18  xor     eax, eax
0x18001ab1a  mov     [rbp+690h+var_710], rax
0x18001ab1e  xorps   xmm0, xmm0
0x18001ab21  movups  xmmword ptr [rsp+790h+hHandle], xmm0
0x18001ab26  lea     rax, [rcx+1]
0x18001ab2a  cmp     rax, r15
0x18001ab2d  jbe     short loc_18001AB35
0x18001ab2f  call    cs:__imp_CloseHandle
0x18001ab35  mov     ebx, edi
0x18001ab37  mov     rcx, r14; hObject
0x18001ab3a  call    cs:__imp_CloseHandle
0x18001ab40  mov     eax, ebx
0x18001ab42  jmp     loc_18001ACF8
0x18001ab47  mov     edi, 80400h
0x18001ab4c  mov     [rbp+690h+var_678], rbx
0x18001ab50  jmp     short loc_18001AB5E
0x18001ab52  mov     rsi, [rbp+690h+lpAttributeList]
0x18001ab56  mov     edi, 400h
0x18001ab5b  mov     rbx, r13
0x18001ab5e  mov     rcx, [rsp+790h+hHandle]; hObject
0x18001ab63  test    rcx, rcx
0x18001ab66  jz      short loc_18001AB6E
0x18001ab68  call    cs:__imp_CloseHandle
0x18001ab6e  mov     rcx, [rsp+790h+hHandle+8]; hObject
0x18001ab73  test    rcx, rcx
0x18001ab76  jz      short loc_18001AB7E
0x18001ab78  call    cs:__imp_CloseHandle
0x18001ab7e  xor     eax, eax
0x18001ab80  lea     rdx, [rbp+690h+CommandLine]; lpCommandLine
0x18001ab87  mov     [rbp+690h+var_710], rax
0x18001ab8b  lea     rcx, [rbp+690h+ApplicationName]; lpApplicationName
0x18001ab92  lea     rax, [rsp+790h+hHandle]
0x18001ab97  xorps   xmm0, xmm0
0x18001ab9a  mov     [rsp+790h+lpProcessInformation], rax; lpProcessInformation
0x18001ab9f  xor     r9d, r9d; lpThreadAttributes
0x18001aba2  lea     rax, [rbp+690h+StartupInfo]
0x18001aba6  xor     r8d, r8d; lpProcessAttributes
  ... truncated ...
```
