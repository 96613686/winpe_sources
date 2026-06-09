# CHungApp::_LaunchElevatedHangReporting(SharedHangRepData *)

- ea: `0x18002accc`
- end: `0x18002b161`
- name: `?_LaunchElevatedHangReporting@CHungApp@@AEAAJPEAUSharedHangRepData@@@Z`
- size: `1173`
- prototype: `__int64 __fastcall(CHungApp *__hidden this, struct SharedHangRepData *Src)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b168`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180006134`
- `0x180011ef8`
- `0x180013df4`
- `0x1800264dc`
- `0x18002a244`
- `0x18002ab58`
- `0x18002accc`
- `0x180034550`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002b0b2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002b0b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002af87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002aff5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002af87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002aff5`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002b058`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002b058`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002af3f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002af3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b063`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aeda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aeea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b0c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b0d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b10c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b122`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aeda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aeea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b0c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b0d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b10c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b122`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002afa9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002b01b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002afa9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002b01b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002b0f6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002b132`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002b0f6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002b132`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CHungApp::_LaunchElevatedHangReporting(
        CHungApp *this,
        struct SharedHangRepData *Src,
        __int64 a3,
        __int64 a4)
{
  int v6; // eax
  UINT v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // r8d
  int appended; // eax
  signed int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  HANDLE v15; // rbx
  HANDLE CurrentProcess; // rax
  signed int v17; // eax
  HANDLE *v18; // rbx
  HANDLE v19; // rdi
  HANDLE v20; // rax
  signed int v21; // eax
  signed int LastError; // eax
  HANDLE hProcess; // rcx
  struct _PROCESS_INFORMATION hObject; // [rsp+50h] [rbp-B0h] BYREF
  LPCVOID lpBaseAddress; // [rsp+68h] [rbp-98h] BYREF
  HANDLE v27; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hSourceHandle; // [rsp+78h] [rbp-88h] BYREF
  LPHANDLE lpTargetHandle; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpCurrentDirectory; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpApplicationName; // [rsp+90h] [rbp-70h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v33; // [rsp+110h] [rbp+10h] BYREF
  __int128 v34; // [rsp+120h] [rbp+20h]
  __int128 v35; // [rsp+130h] [rbp+30h]
  __int128 v36; // [rsp+140h] [rbp+40h]
  __int128 v37; // [rsp+150h] [rbp+50h]
  __int128 v38; // [rsp+160h] [rbp+60h]
  void *v39; // [rsp+170h] [rbp+70h]
  _BYTE Srca[1912]; // [rsp+178h] [rbp+78h] BYREF
  wchar_t v41[48]; // [rsp+8F0h] [rbp+7F0h] BYREF
  WCHAR CommandLine[264]; // [rsp+950h] [rbp+850h] BYREF

  if ( !CHungApp::ms_exePath )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, Src, a3, a4);
  lpTargetHandle = 0;
  hSourceHandle = 0;
  v27 = 0;
  lpBaseAddress = 0;
  memset(&hObject, 0, sizeof(hObject));
  v6 = CHungApp::_CreateSharedMemory(
         (__int64)this,
         0,
         &hSourceHandle,
         (const void **)&lpTargetHandle,
         &v27,
         &lpBaseAddress,
         v41);
  v7 = v6;
  if ( v6 >= 0 )
  {
    memcpy_0(Srca, Src, sizeof(Srca));
    memcpy_0((void *)lpBaseAddress, Srca, 0x778u);
    v6 = StringCchPrintfW(CommandLine, 0x104u, L"werfault.exe /h /shared %s", v41);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_46;
      v9 = 32;
      goto LABEL_7;
    }
    appended = CHungApp::AppendClientIdsToCmdLine(this, CommandLine, v10);
    if ( appended < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids,
        (unsigned int)appended);
    memset_0(&v33, 0, 0x68u);
    *(_OWORD *)&StartupInfo.cb = v33;
    StartupInfo.lpTitle = (LPWSTR)*((_QWORD *)&v34 + 1);
    *(_OWORD *)&StartupInfo.dwX = v35;
    *(_OWORD *)&StartupInfo.dwXCountChars = v36;
    *(_OWORD *)&StartupInfo.wShowWindow = v37;
    *(_OWORD *)&StartupInfo.hStdInput = v38;
    StartupInfo.hStdError = v39;
    StartupInfo.cb = 104;
    StartupInfo.lpDesktop = 0;
    lpApplicationName = 0;
    lpCurrentDirectory = 0;
    CHungApp::_GetSystemAndExePathForProcess(this, &lpCurrentDirectory, &lpApplicationName);
    if ( hObject.hProcess )
      CloseHandle(hObject.hProcess);
    if ( hObject.hThread )
      CloseHandle(hObject.hThread);
    memset(&hObject, 0, sizeof(hObject));
    if ( CreateProcessW(lpApplicationName, CommandLine, 0, 0, 0, 4u, 0, lpCurrentDirectory, &StartupInfo, &hObject) )
    {
      v15 = hSourceHandle;
      CurrentProcess = GetCurrentProcess();
      if ( DuplicateHandle(CurrentProcess, v15, hObject.hProcess, 0, 4u, 0, 0) )
      {
        v18 = lpTargetHandle;
        v19 = v27;
        v20 = GetCurrentProcess();
        if ( DuplicateHandle(v20, v19, hObject.hProcess, v18, 2u, 0, 0) )
        {
          if ( ResumeThread(hObject.hThread) != -1 )
          {
            v7 = 0;
            goto LABEL_49;
          }
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v14 = 37;
            goto LABEL_44;
          }
        }
        else
        {
          v21 = GetLastError();
          v7 = v21;
          if ( v21 > 0 )
            v7 = (unsigned __int16)v21 | 0x80070000;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v14 = 36;
            goto LABEL_44;
          }
        }
      }
      else
      {
        v17 = GetLastError();
        v7 = v17;
        if ( v17 > 0 )
          v7 = (unsigned __int16)v17 | 0x80070000;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 35;
          goto LABEL_44;
        }
      }
    }
    else
    {
      v12 = GetLastError();
      v7 = v12;
      if ( v12 > 0 )
        v7 = (unsigned __int16)v12 | 0x80070000;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 34;
LABEL_44:
        WPP_SF_d(v13[2], v14, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids, v7);
      }
    }
    if ( (v7 & 0x80000000) == 0 )
      goto LABEL_49;
    goto LABEL_46;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_46;
  v9 = 31;
LABEL_7:
  WPP_SF_d(v8[2], v9, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids, (unsigned int)v6);
LABEL_46:
  hProcess = hObject.hProcess;
  if ( !hObject.hProcess )
    goto LABEL_50;
  TerminateProcess(hObject.hProcess, v7);
LABEL_49:
  hProcess = hObject.hProcess;
LABEL_50:
  if ( hProcess )
    CloseHandle(hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  memset(&hObject, 0, sizeof(hObject));
  if ( lpBaseAddress )
    UnmapViewOfFile(lpBaseAddress);
  if ( (unsigned __int64)v27 + 1 > 1 )
    CloseHandle(v27);
  if ( (unsigned __int64)hSourceHandle + 1 > 1 )
    CloseHandle(hSourceHandle);
  if ( lpTargetHandle )
    UnmapViewOfFile(lpTargetHandle);
  return v7;
}

```

## disassembly

```asm
0x18002accc  mov     [rsp-8+arg_8], rbx
0x18002acd1  mov     [rsp-8+arg_10], rsi
0x18002acd6  push    rbp
0x18002acd7  push    rdi
0x18002acd8  push    r15
0x18002acda  lea     rbp, [rsp-0A70h]
0x18002ace2  sub     rsp, 0B70h
0x18002ace9  mov     rax, cs:__security_cookie
0x18002acf0  xor     rax, rsp
0x18002acf3  mov     [rbp+0A80h+var_20], rax
0x18002acfa  mov     rsi, rdx
0x18002acfd  mov     rdi, rcx
0x18002ad00  xor     r15d, r15d
0x18002ad03  cmp     cs:?ms_exePath@CHungApp@@0PA_WA, r15w; wchar_t near * CHungApp::ms_exePath
0x18002ad0b  jnz     short loc_18002AD12
0x18002ad0d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002ad12  mov     [rbp+0A80h+lpTargetHandle], r15
0x18002ad16  mov     [rsp+0B80h+hSourceHandle], r15
0x18002ad1b  mov     [rsp+0B80h+var_B10], r15
0x18002ad20  mov     [rsp+0B80h+lpBaseAddress], r15
0x18002ad25  xorps   xmm0, xmm0
0x18002ad28  xor     eax, eax
0x18002ad2a  movups  xmmword ptr [rsp+0B80h+hObject], xmm0
0x18002ad2f  mov     [rsp+0B80h+var_B20], rax
0x18002ad34  lea     rax, [rbp+0A80h+var_290]
0x18002ad3b  mov     [rsp+0B80h+lpEnvironment], rax
0x18002ad40  lea     rax, [rsp+0B80h+lpBaseAddress]
0x18002ad45  mov     qword ptr [rsp+0B80h+dwCreationFlags], rax
0x18002ad4a  lea     rax, [rsp+0B80h+var_B10]
0x18002ad4f  mov     qword ptr [rsp+0B80h+bInheritHandles], rax
0x18002ad54  lea     r9, [rbp+0A80h+lpTargetHandle]
0x18002ad58  lea     r8, [rsp+0B80h+hSourceHandle]
0x18002ad5d  xor     edx, edx
0x18002ad5f  mov     rcx, rdi
0x18002ad62  call    ?_CreateSharedMemory@CHungApp@@AEAAJPEAXPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAV?$unique_ptr@PEAXU?$generic_delete@PEAXU?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@1PEAV?$unique_ptr@USharedHangRepData@@U?$generic_delete@USharedHangRepData@@U?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@5@PEA_W@Z
0x18002ad67  mov     ebx, eax
0x18002ad69  test    eax, eax
0x18002ad6b  jns     short loc_18002ADAB
0x18002ad6d  lea     rsi, WPP_GLOBAL_Control
0x18002ad74  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad7b  cmp     rcx, rsi
0x18002ad7e  jz      loc_18002B0A6
0x18002ad84  test    byte ptr [rcx+1Ch], 1
0x18002ad88  jz      loc_18002B0A6
0x18002ad8e  mov     edx, 1Fh
0x18002ad93  mov     r9d, eax
0x18002ad96  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x18002ad9d  mov     rcx, [rcx+10h]
0x18002ada1  call    WPP_SF_d
0x18002ada6  jmp     loc_18002B0A6
0x18002adab  lea     rcx, [rbp+0A80h+Src]; void *
0x18002adaf  mov     rdx, rsi; Src
0x18002adb2  mov     ebx, 778h
0x18002adb7  mov     r8d, ebx; Size
0x18002adba  call    memcpy_0
0x18002adbf  mov     rcx, [rsp+0B80h+lpBaseAddress]; void *
0x18002adc4  lea     rdx, [rbp+0A80h+Src]; Src
0x18002adc8  mov     r8d, ebx; Size
0x18002adcb  call    memcpy_0
0x18002add0  lea     r9, [rbp+0A80h+var_290]
0x18002add7  lea     r8, aWerfaultExeHSh; "werfault.exe /h /shared %s"
0x18002adde  mov     edx, 104h; unsigned __int64
0x18002ade3  lea     rcx, [rbp+0A80h+CommandLine]; wchar_t *
0x18002adea  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002adef  mov     ebx, eax
0x18002adf1  test    eax, eax
0x18002adf3  jns     short loc_18002AE20
0x18002adf5  lea     rsi, WPP_GLOBAL_Control
0x18002adfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae03  cmp     rcx, rsi
0x18002ae06  jz      loc_18002B0A6
0x18002ae0c  test    byte ptr [rcx+1Ch], 1
0x18002ae10  jz      loc_18002B0A6
0x18002ae16  mov     edx, 20h ; ' '
0x18002ae1b  jmp     loc_18002AD93
0x18002ae20  lea     rdx, [rbp+0A80h+CommandLine]; wchar_t *
0x18002ae27  mov     rcx, rdi; this
0x18002ae2a  call    ?AppendClientIdsToCmdLine@CHungApp@@AEAAJPEA_WK@Z; CHungApp::AppendClientIdsToCmdLine(wchar_t *,ulong)
0x18002ae2f  lea     rsi, WPP_GLOBAL_Control
0x18002ae36  test    eax, eax
0x18002ae38  jns     short loc_18002AE64
0x18002ae3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae41  cmp     rcx, rsi
0x18002ae44  jz      short loc_18002AE64
0x18002ae46  test    byte ptr [rcx+1Ch], 2
0x18002ae4a  jz      short loc_18002AE64
0x18002ae4c  mov     edx, 21h ; '!'
0x18002ae51  mov     r9d, eax
0x18002ae54  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x18002ae5b  mov     rcx, [rcx+10h]
0x18002ae5f  call    WPP_SF_d
0x18002ae64  mov     ebx, 68h ; 'h'
0x18002ae69  mov     r8d, ebx; Size
0x18002ae6c  xor     edx, edx; Val
0x18002ae6e  lea     rcx, [rbp+0A80h+var_A70]; void *
0x18002ae72  call    memset_0
0x18002ae77  movups  xmm0, [rbp+0A80h+var_A70]
0x18002ae7b  movaps  xmmword ptr [rbp+0A80h+StartupInfo.cb], xmm0
0x18002ae7f  movups  xmm1, [rbp+0A80h+var_A60]
0x18002ae83  movaps  xmmword ptr [rbp+0A80h+StartupInfo.lpDesktop], xmm1
0x18002ae87  movups  xmm0, [rbp+0A80h+var_A50]
0x18002ae8b  movaps  xmmword ptr [rbp+0A80h+StartupInfo.dwX], xmm0
0x18002ae8f  movups  xmm1, [rbp+0A80h+var_A40]
0x18002ae93  movaps  xmmword ptr [rbp+0A80h+StartupInfo.dwXCountChars], xmm1
0x18002ae97  movups  xmm0, [rbp+0A80h+var_A30]
0x18002ae9b  movaps  xmmword ptr [rbp+0A80h+StartupInfo.wShowWindow], xmm0
0x18002ae9f  movups  xmm1, [rbp+0A80h+var_A20]
0x18002aea3  movaps  xmmword ptr [rbp+0A80h+StartupInfo.hStdInput], xmm1
0x18002aea7  movsd   xmm0, [rbp+0A80h+var_A10]
0x18002aeac  movsd   [rbp+0A80h+StartupInfo.hStdError], xmm0
0x18002aeb1  mov     [rbp+0A80h+StartupInfo.cb], ebx
0x18002aeb4  mov     [rbp+0A80h+StartupInfo.lpDesktop], r15
0x18002aeb8  mov     [rbp+0A80h+lpApplicationName], r15
0x18002aebc  mov     [rbp+0A80h+var_AF8], r15
0x18002aec0  lea     r8, [rbp+0A80h+lpApplicationName]; wchar_t **
0x18002aec4  lea     rdx, [rbp+0A80h+var_AF8]; wchar_t **
0x18002aec8  mov     rcx, rdi; this
0x18002aecb  call    ?_GetSystemAndExePathForProcess@CHungApp@@AEAAXPEAPEB_W0@Z; CHungApp::_GetSystemAndExePathForProcess(wchar_t const * *,wchar_t const * *)
0x18002aed0  mov     rcx, [rsp+0B80h+hObject]; hObject
0x18002aed5  test    rcx, rcx
0x18002aed8  jz      short loc_18002AEE0
0x18002aeda  call    cs:__imp_CloseHandle
0x18002aee0  mov     rcx, [rsp+0B80h+hObject+8]; hObject
0x18002aee5  test    rcx, rcx
0x18002aee8  jz      short loc_18002AEF0
0x18002aeea  call    cs:__imp_CloseHandle
0x18002aef0  xorps   xmm0, xmm0
0x18002aef3  xor     eax, eax
0x18002aef5  movups  xmmword ptr [rsp+0B80h+hObject], xmm0
0x18002aefa  mov     [rsp+0B80h+var_B20], rax
0x18002aeff  lea     rax, [rsp+0B80h+hObject]
0x18002af04  mov     [rsp+0B80h+lpProcessInformation], rax; lpProcessInformation
0x18002af09  lea     rax, [rbp+0A80h+StartupInfo]
0x18002af0d  mov     [rsp+0B80h+lpStartupInfo], rax; lpStartupInfo
0x18002af12  mov     rax, [rbp+0A80h+var_AF8]
0x18002af16  mov     [rsp+0B80h+lpCurrentDirectory], rax; lpCurrentDirectory
0x18002af1b  mov     [rsp+0B80h+lpEnvironment], r15; lpEnvironment
0x18002af20  mov     edi, 4
0x18002af25  mov     [rsp+0B80h+dwCreationFlags], edi; dwCreationFlags
0x18002af29  mov     [rsp+0B80h+bInheritHandles], r15d; bInheritHandles
0x18002af2e  xor     r9d, r9d; lpThreadAttributes
0x18002af31  xor     r8d, r8d; lpProcessAttributes
0x18002af34  lea     rdx, [rbp+0A80h+CommandLine]; lpCommandLine
0x18002af3b  mov     rcx, [rbp+0A80h+lpApplicationName]; lpApplicationName
0x18002af3f  call    cs:__imp_CreateProcessW
0x18002af45  test    eax, eax
0x18002af47  jnz     short loc_18002AF82
0x18002af49  call    cs:__imp_GetLastError
0x18002af4f  mov     ebx, eax
0x18002af51  test    eax, eax
0x18002af53  jle     short loc_18002AF5E
0x18002af55  movzx   ebx, ax
0x18002af58  or      ebx, 80070000h
0x18002af5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af65  cmp     rcx, rsi
0x18002af68  jz      loc_18002B0A2
0x18002af6e  test    byte ptr [rcx+1Ch], 1
0x18002af72  jz      loc_18002B0A2
0x18002af78  mov     edx, 22h ; '"'
0x18002af7d  jmp     loc_18002B08F
0x18002af82  mov     rbx, [rsp+0B80h+hSourceHandle]
0x18002af87  call    cs:__imp_GetCurrentProcess
0x18002af8d  mov     dword ptr [rsp+0B80h+lpEnvironment], r15d; dwOptions
0x18002af92  mov     [rsp+0B80h+dwCreationFlags], r15d; bInheritHandle
0x18002af97  mov     [rsp+0B80h+bInheritHandles], edi; dwDesiredAccess
0x18002af9b  xor     r9d, r9d; lpTargetHandle
0x18002af9e  mov     r8, [rsp+0B80h+hObject]; hTargetProcessHandle
0x18002afa3  mov     rdx, rbx; hSourceHandle
0x18002afa6  mov     rcx, rax; hSourceProcessHandle
0x18002afa9  call    cs:__imp_DuplicateHandle
0x18002afaf  test    eax, eax
0x18002afb1  jnz     short loc_18002AFEC
0x18002afb3  call    cs:__imp_GetLastError
0x18002afb9  mov     ebx, eax
0x18002afbb  test    eax, eax
0x18002afbd  jle     short loc_18002AFC8
0x18002afbf  movzx   ebx, ax
0x18002afc2  or      ebx, 80070000h
0x18002afc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afcf  cmp     rcx, rsi
0x18002afd2  jz      loc_18002B0A2
0x18002afd8  test    byte ptr [rcx+1Ch], 1
0x18002afdc  jz      loc_18002B0A2
0x18002afe2  mov     edx, 23h ; '#'
0x18002afe7  jmp     loc_18002B08F
0x18002afec  mov     rbx, [rbp+0A80h+lpTargetHandle]
0x18002aff0  mov     rdi, [rsp+0B80h+var_B10]
0x18002aff5  call    cs:__imp_GetCurrentProcess
0x18002affb  mov     dword ptr [rsp+0B80h+lpEnvironment], r15d; dwOptions
0x18002b000  mov     [rsp+0B80h+dwCreationFlags], r15d; bInheritHandle
0x18002b005  mov     [rsp+0B80h+bInheritHandles], 2; dwDesiredAccess
0x18002b00d  mov     r9, rbx; lpTargetHandle
0x18002b010  mov     r8, [rsp+0B80h+hObject]; hTargetProcessHandle
0x18002b015  mov     rdx, rdi; hSourceHandle
0x18002b018  mov     rcx, rax; hSourceProcessHandle
0x18002b01b  call    cs:__imp_DuplicateHandle
0x18002b021  test    eax, eax
0x18002b023  jnz     short loc_18002B053
0x18002b025  call    cs:__imp_GetLastError
0x18002b02b  mov     ebx, eax
0x18002b02d  test    eax, eax
0x18002b02f  jle     short loc_18002B03A
0x18002b031  movzx   ebx, ax
0x18002b034  or      ebx, 80070000h
0x18002b03a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b041  cmp     rcx, rsi
0x18002b044  jz      short loc_18002B0A2
0x18002b046  test    byte ptr [rcx+1Ch], 1
0x18002b04a  jz      short loc_18002B0A2
0x18002b04c  mov     edx, 24h ; '$'
0x18002b051  jmp     short loc_18002B08F
0x18002b053  mov     rcx, [rsp+0B80h+hObject+8]; hThread
0x18002b058  call    cs:__imp_ResumeThread
0x18002b05e  cmp     eax, 0FFFFFFFFh
0x18002b061  jnz     short loc_18002B0BA
0x18002b063  call    cs:__imp_GetLastError
0x18002b069  mov     ebx, eax
0x18002b06b  test    eax, eax
0x18002b06d  jle     short loc_18002B078
0x18002b06f  movzx   ebx, ax
0x18002b072  or      ebx, 80070000h
0x18002b078  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b07f  cmp     rcx, rsi
0x18002b082  jz      short loc_18002B0A2
0x18002b084  test    byte ptr [rcx+1Ch], 1
0x18002b088  jz      short loc_18002B0A2
0x18002b08a  mov     edx, 25h ; '%'
0x18002b08f  mov     r9d, ebx
0x18002b092  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x18002b099  mov     rcx, [rcx+10h]
0x18002b09d  call    WPP_SF_d
0x18002b0a2  test    ebx, ebx
0x18002b0a4  jns     short loc_18002B0BD
0x18002b0a6  mov     rcx, [rsp+0B80h+hObject]; hProcess
0x18002b0ab  test    rcx, rcx
0x18002b0ae  jz      short loc_18002B0C2
0x18002b0b0  mov     edx, ebx; uExitCode
0x18002b0b2  call    cs:__imp_TerminateProcess
0x18002b0b8  jmp     short loc_18002B0BD
0x18002b0ba  mov     ebx, r15d
0x18002b0bd  mov     rcx, [rsp+0B80h+hObject]; hObject
0x18002b0c2  test    rcx, rcx
0x18002b0c5  jz      short loc_18002B0CD
0x18002b0c7  call    cs:__imp_CloseHandle
0x18002b0cd  mov     rcx, [rsp+0B80h+hObject+8]; hObject
0x18002b0d2  test    rcx, rcx
0x18002b0d5  jz      short loc_18002B0DD
0x18002b0d7  call    cs:__imp_CloseHandle
0x18002b0dd  xorps   xmm0, xmm0
0x18002b0e0  xor     eax, eax
0x18002b0e2  movups  xmmword ptr [rsp+0B80h+hObject], xmm0
0x18002b0e7  mov     [rsp+0B80h+var_B20], rax
0x18002b0ec  mov     rcx, [rsp+0B80h+lpBaseAddress]; lpBaseAddress
0x18002b0f1  test    rcx, rcx
0x18002b0f4  jz      short loc_18002B0FD
0x18002b0f6  call    cs:__imp_UnmapViewOfFile
0x18002b0fc  nop
0x18002b0fd  mov     rcx, [rsp+0B80h+var_B10]; hObject
0x18002b102  lea     rax, [rcx+1]
0x18002b106  cmp     rax, 1
0x18002b10a  jbe     short loc_18002B113
0x18002b10c  call    cs:__imp_CloseHandle
0x18002b112  nop
0x18002b113  mov     rcx, [rsp+0B80h+hSourceHandle]; hObject
0x18002b118  lea     rax, [rcx+1]
0x18002b11c  cmp     rax, 1
0x18002b120  jbe     short loc_18002B129
0x18002b122  call    cs:__imp_CloseHandle
0x18002b128  nop
0x18002b129  mov     rcx, [rbp+0A80h+lpTargetHandle]; lpBaseAddress
0x18002b12d  test    rcx, rcx
0x18002b130  jz      short loc_18002B138
0x18002b132  call    cs:__imp_UnmapViewOfFile
0x18002b138  mov     eax, ebx
0x18002b13a  mov     rcx, [rbp+0A80h+var_20]
0x18002b141  xor     rcx, rsp; StackCookie
0x18002b144  call    __security_check_cookie
0x18002b149  lea     r11, [rsp+0B80h+var_10]
0x18002b151  mov     rbx, [r11+28h]
0x18002b155  mov     rsi, [r11+30h]
0x18002b159  mov     rsp, r11
0x18002b15c  pop     r15
0x18002b15e  pop     rdi
0x18002b15f  pop     rbp
0x18002b160  retn
```
