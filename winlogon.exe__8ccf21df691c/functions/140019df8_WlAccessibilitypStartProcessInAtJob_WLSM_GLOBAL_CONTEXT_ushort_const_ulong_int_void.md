# WlAccessibilitypStartProcessInAtJob(_WLSM_GLOBAL_CONTEXT *,ushort const *,ulong,int,void * *)

- ea: `0x140019df8`
- end: `0x14001a1f9`
- name: `?WlAccessibilitypStartProcessInAtJob@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@PEBGKHPEAPEAX@Z`
- size: `1025`
- prototype: `__int64 __fastcall(CSession **, const unsigned __int16 *, __int64, int)`
- caller_count: `12`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005840`
- `0x1400180f0`
- `0x140019c94`
- `0x14003c3e0`
- `0x140058c7c`
- `0x140058f1c`
- `0x140059000`
- `0x1400590a0`
- `0x140059190`
- `0x1400594a4`
- `0x140059684`
- `0x140059888`

## callees

- `0x1400057f4`
- `0x140006fc0`
- `0x140019df8`
- `0x14001a520`
- `0x140041c34`
- `0x140053720`
- `0x1400544e0`
- `0x14005b444`
- `0x14007b9dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019ee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019fc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a08c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a0e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019ee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019fc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a08c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a0e5`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14001a0da`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14001a0da`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140019fb4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140019fb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a166`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a195`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009dd04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009dd14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009dd24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a166`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a195`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009dd04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009dd14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009dd24`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x14001a082`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x14001a082`

## pseudocode

```c
__int64 __fastcall WlAccessibilitypStartProcessInAtJob(CSession **a1, const unsigned __int16 *a2, __int64 a3, int a4)
{
  void *AccessibilityJobObject; // rsi
  int v8; // edx
  unsigned int v9; // edi
  CUser *v10; // rcx
  DWORD LastError; // eax
  __int64 v12; // rdx
  DWORD v13; // eax
  int v14; // edx
  int v15; // r8d
  const char *v16; // r9
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-2C8h] BYREF
  void *v19; // [rsp+78h] [rbp-2B0h]
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-2A8h] BYREF
  WCHAR CommandLine[264]; // [rsp+F0h] [rbp-238h] BYREF

  AccessibilityJobObject = 0;
  v19 = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(CommandLine, 0, 0x208u);
  if ( !(unsigned int)StringCchCopyW(CommandLine, 0x104u, a2) )
  {
    AccessibilityJobObject = CSession::GetAccessibilityJobObject(a1[2], v8);
    v19 = AccessibilityJobObject;
    if ( !AccessibilityJobObject )
    {
      LastError = GetLastError();
      v9 = LastError;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_41;
      }
      v12 = 36;
      goto LABEL_12;
    }
    StartupInfo.cb = 104;
    StartupInfo.dwFlags = 129;
    StartupInfo.wShowWindow = 1;
    if ( a4 )
    {
      StartupInfo.lpDesktop = L"Winsta0\\Winlogon";
      if ( !CreateProcessAsUserW(
              *((HANDLE *)*a1 + 10),
              0,
              CommandLine,
              0,
              0,
              0,
              4u,
              0,
              0,
              &StartupInfo,
              &ProcessInformation) )
      {
        LastError = GetLastError();
        v9 = LastError;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_41;
        }
        v12 = 37;
        goto LABEL_12;
      }
    }
    else
    {
      StartupInfo.lpDesktop = 0;
      LastError = CUser::CreateProcessW(a1[4], 0, CommandLine, 4u, &StartupInfo, &ProcessInformation, 0);
      v9 = LastError;
      if ( LastError )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_41;
        }
        v12 = 38;
        goto LABEL_12;
      }
    }
    if ( !AssignProcessToJobObject(AccessibilityJobObject, ProcessInformation.hProcess) )
    {
      v13 = GetLastError();
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v13);
      }
    }
    if ( ResumeThread(ProcessInformation.hThread) != -1 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v16 = "System";
        if ( !a4 )
          v16 = "User  ";
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, (_DWORD)v16, (__int64)a2);
        v10 = WPP_GLOBAL_Control;
      }
      v9 = 0;
      goto LABEL_41;
    }
    LastError = GetLastError();
    v9 = LastError;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_41;
    }
    v12 = 40;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v10 + 2), v12, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, LastError);
    goto LABEL_6;
  }
  v9 = 87;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids);
LABEL_6:
    v10 = WPP_GLOBAL_Control;
  }
LABEL_41:
  if ( ProcessInformation.hProcess )
  {
    CloseHandle(ProcessInformation.hProcess);
    v10 = WPP_GLOBAL_Control;
  }
  if ( ProcessInformation.hThread )
  {
    CloseHandle(ProcessInformation.hThread);
    v10 = WPP_GLOBAL_Control;
  }
  if ( AccessibilityJobObject )
  {
    CloseHandle(AccessibilityJobObject);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x40000) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)v10 + 2), 42, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x140019df8  mov     [rsp+arg_10], rbx
0x140019dfd  mov     [rsp+arg_18], rsi
0x140019e02  push    rdi
0x140019e03  push    r14
0x140019e05  push    r15
0x140019e07  sub     rsp, 310h
0x140019e0e  mov     rax, cs:__security_cookie
0x140019e15  xor     rax, rsp
0x140019e18  mov     [rsp+328h+var_28], rax
0x140019e20  mov     r14d, r9d
0x140019e23  mov     r15, rdx
0x140019e26  mov     rbx, rcx
0x140019e29  xor     esi, esi
0x140019e2b  mov     [rsp+328h+var_2B0], rsi
0x140019e30  lea     edi, [rsi+68h]
0x140019e33  mov     r8d, edi; Size
0x140019e36  xor     edx, edx; Val
0x140019e38  lea     rcx, [rsp+328h+StartupInfo]; void *
0x140019e40  call    memset_0
0x140019e45  xorps   xmm0, xmm0
0x140019e48  xor     eax, eax
0x140019e4a  movups  xmmword ptr [rsp+328h+ProcessInformation.hProcess], xmm0
0x140019e4f  mov     qword ptr [rsp+328h+ProcessInformation.dwProcessId], rax
0x140019e54  xor     edx, edx; Val
0x140019e56  mov     r8d, 208h; Size
0x140019e5c  lea     rcx, [rsp+328h+CommandLine]; void *
0x140019e64  call    memset_0
0x140019e69  nop
0x140019e6a  mov     r8, r15; unsigned __int16 *
0x140019e6d  mov     edx, 104h; unsigned __int64
0x140019e72  lea     rcx, [rsp+328h+CommandLine]; unsigned __int16 *
0x140019e7a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140019e7f  test    eax, eax
0x140019e81  jz      short loc_140019ED3
0x140019e83  lea     edi, [rsi+57h]
0x140019e86  lea     rbx, WPP_GLOBAL_Control
0x140019e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140019e94  cmp     rcx, rbx
0x140019e97  jz      loc_14001A159
0x140019e9d  test    dword ptr [rcx+1Ch], 40000h
0x140019ea4  jz      loc_14001A159
0x140019eaa  cmp     byte ptr [rcx+19h], 2
0x140019eae  jb      loc_14001A159
0x140019eb4  lea     edx, [rsi+23h]
0x140019eb7  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x140019ebe  mov     rcx, [rcx+10h]
0x140019ec2  call    WPP_SF_
0x140019ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x140019ece  jmp     loc_14001A159
0x140019ed3  mov     rcx, [rbx+10h]; this
0x140019ed7  call    ?GetAccessibilityJobObject@CSession@@QEAAPEAXH@Z; CSession::GetAccessibilityJobObject(int)
0x140019edc  mov     rsi, rax
0x140019edf  mov     [rsp+328h+var_2B0], rax
0x140019ee4  test    rax, rax
0x140019ee7  jnz     short loc_140019F37
0x140019ee9  call    cs:__imp_GetLastError
0x140019eef  mov     edi, eax
0x140019ef1  lea     rbx, WPP_GLOBAL_Control
0x140019ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x140019eff  cmp     rcx, rbx
0x140019f02  jz      loc_14001A159
0x140019f08  test    dword ptr [rcx+1Ch], 40000h
0x140019f0f  jz      loc_14001A159
0x140019f15  cmp     byte ptr [rcx+19h], 2
0x140019f19  jb      loc_14001A159
0x140019f1f  lea     edx, [rsi+24h]
0x140019f22  mov     r9d, eax
0x140019f25  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x140019f2c  mov     rcx, [rcx+10h]
0x140019f30  call    WPP_SF_d
0x140019f35  jmp     short loc_140019EC7
0x140019f37  mov     [rsp+328h+StartupInfo.cb], edi
0x140019f3e  mov     [rsp+328h+StartupInfo.dwFlags], 81h
0x140019f49  mov     eax, 1
0x140019f4e  mov     [rsp+328h+StartupInfo.wShowWindow], ax
0x140019f56  lea     r8, [rsp+328h+CommandLine]; lpCommandLine
0x140019f5e  xor     edx, edx; lpApplicationName
0x140019f60  test    r14d, r14d
0x140019f63  jz      loc_14001A002
0x140019f69  lea     rax, aWinsta0Winlogo; "Winsta0\\Winlogon"
0x140019f70  mov     [rsp+328h+StartupInfo.lpDesktop], rax
0x140019f78  mov     rcx, [rbx]
0x140019f7b  lea     rax, [rsp+328h+ProcessInformation]
0x140019f80  mov     [rsp+328h+lpProcessInformation], rax; lpProcessInformation
0x140019f85  lea     rax, [rsp+328h+StartupInfo]
0x140019f8d  mov     [rsp+328h+lpStartupInfo], rax; lpStartupInfo
0x140019f92  mov     [rsp+328h+lpCurrentDirectory], rdx; lpCurrentDirectory
0x140019f97  mov     [rsp+328h+lpEnvironment], rdx; lpEnvironment
0x140019f9c  mov     [rsp+328h+dwCreationFlags], 4; dwCreationFlags
0x140019fa4  mov     [rsp+328h+bInheritHandles], edx; bInheritHandles
0x140019fa8  mov     [rsp+328h+lpThreadAttributes], rdx; lpThreadAttributes
0x140019fad  xor     r9d, r9d; lpProcessAttributes
0x140019fb0  mov     rcx, [rcx+50h]; hToken
0x140019fb4  call    cs:__imp_CreateProcessAsUserW
0x140019fba  test    eax, eax
0x140019fbc  jnz     loc_14001A07A
0x140019fc2  call    cs:__imp_GetLastError
0x140019fc8  mov     edi, eax
0x140019fca  lea     rbx, WPP_GLOBAL_Control
0x140019fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x140019fd8  cmp     rcx, rbx
0x140019fdb  jz      loc_14001A159
0x140019fe1  test    dword ptr [rcx+1Ch], 40000h
0x140019fe8  jz      loc_14001A159
0x140019fee  cmp     byte ptr [rcx+19h], 2
0x140019ff2  jb      loc_14001A159
0x140019ff8  mov     edx, 25h ; '%'
0x140019ffd  jmp     loc_140019F22
0x14001a002  mov     [rsp+328h+StartupInfo.lpDesktop], 0
0x14001a00e  mov     [rsp+328h+dwCreationFlags], 0; int
0x14001a016  lea     rax, [rsp+328h+ProcessInformation]
0x14001a01b  mov     qword ptr [rsp+328h+bInheritHandles], rax; LPPROCESS_INFORMATION
0x14001a020  lea     rax, [rsp+328h+StartupInfo]
0x14001a028  mov     [rsp+328h+lpThreadAttributes], rax; LPSTARTUPINFOW
0x14001a02d  mov     r9d, 4; unsigned int
0x14001a033  mov     rcx, [rbx+20h]; this
0x14001a037  call    ?CreateProcessW@CUser@@QEAAKPEBGPEAGKPEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@H@Z; CUser::CreateProcessW(ushort const *,ushort *,ulong,_STARTUPINFOW *,_PROCESS_INFORMATION *,int)
0x14001a03c  mov     edi, eax
0x14001a03e  test    eax, eax
0x14001a040  jz      short loc_14001A07A
0x14001a042  lea     rbx, WPP_GLOBAL_Control
0x14001a049  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a050  cmp     rcx, rbx
0x14001a053  jz      loc_14001A159
0x14001a059  test    dword ptr [rcx+1Ch], 40000h
0x14001a060  jz      loc_14001A159
0x14001a066  cmp     byte ptr [rcx+19h], 2
0x14001a06a  jb      loc_14001A159
0x14001a070  mov     edx, 26h ; '&'
0x14001a075  jmp     loc_140019F22
0x14001a07a  mov     rdx, [rsp+328h+ProcessInformation.hProcess]; hProcess
0x14001a07f  mov     rcx, rsi; hJob
0x14001a082  call    cs:__imp_AssignProcessToJobObject
0x14001a088  test    eax, eax
0x14001a08a  jnz     short loc_14001A0CE
0x14001a08c  call    cs:__imp_GetLastError
0x14001a092  lea     rbx, WPP_GLOBAL_Control
0x14001a099  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a0a0  cmp     rcx, rbx
0x14001a0a3  jz      short loc_14001A0D5
0x14001a0a5  test    dword ptr [rcx+1Ch], 40000h
0x14001a0ac  jz      short loc_14001A0D5
0x14001a0ae  cmp     byte ptr [rcx+19h], 2
0x14001a0b2  jb      short loc_14001A0D5
0x14001a0b4  mov     edx, 27h ; '''
0x14001a0b9  mov     r9d, eax
0x14001a0bc  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x14001a0c3  mov     rcx, [rcx+10h]
0x14001a0c7  call    WPP_SF_d
0x14001a0cc  jmp     short loc_14001A0D5
0x14001a0ce  lea     rbx, WPP_GLOBAL_Control
0x14001a0d5  mov     rcx, [rsp+328h+ProcessInformation.hThread]; hThread
0x14001a0da  call    cs:__imp_ResumeThread
0x14001a0e0  cmp     eax, 0FFFFFFFFh
0x14001a0e3  jnz     short loc_14001A112
0x14001a0e5  call    cs:__imp_GetLastError
0x14001a0eb  mov     edi, eax
0x14001a0ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a0f4  cmp     rcx, rbx
0x14001a0f7  jz      short loc_14001A159
0x14001a0f9  test    dword ptr [rcx+1Ch], 40000h
0x14001a100  jz      short loc_14001A159
0x14001a102  cmp     byte ptr [rcx+19h], 2
0x14001a106  jb      short loc_14001A159
0x14001a108  mov     edx, 28h ; '('
0x14001a10d  jmp     loc_140019F22
0x14001a112  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a119  cmp     rcx, rbx
0x14001a11c  jz      short loc_14001A157
0x14001a11e  test    dword ptr [rcx+1Ch], 40000h
0x14001a125  jz      short loc_14001A157
0x14001a127  cmp     byte ptr [rcx+19h], 4
0x14001a12b  jb      short loc_14001A157
0x14001a12d  lea     rax, aUser; "User  "
0x14001a134  lea     r9, aSystem; "System"
0x14001a13b  test    r14d, r14d
0x14001a13e  cmovz   r9, rax
0x14001a142  mov     [rsp+328h+lpThreadAttributes], r15
0x14001a147  mov     rcx, [rcx+10h]
0x14001a14b  call    WPP_SF_sS
0x14001a150  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a157  xor     edi, edi
0x14001a159  mov     rax, [rsp+328h+ProcessInformation.hProcess]
0x14001a15e  test    rax, rax
0x14001a161  jz      short loc_14001A173
0x14001a163  mov     rcx, rax; hObject
0x14001a166  call    cs:__imp_CloseHandle
0x14001a16c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a173  mov     rax, [rsp+328h+ProcessInformation.hThread]
0x14001a178  test    rax, rax
0x14001a17b  jz      short loc_14001A18D
0x14001a17d  mov     rcx, rax; hObject
0x14001a180  call    cs:__imp_CloseHandle
0x14001a186  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a18d  test    rsi, rsi
0x14001a190  jz      short loc_14001A1A2
0x14001a192  mov     rcx, rsi; hObject
0x14001a195  call    cs:__imp_CloseHandle
0x14001a19b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a1a2  cmp     rcx, rbx
0x14001a1a5  jz      short loc_14001A1CE
0x14001a1a7  test    dword ptr [rcx+1Ch], 40000h
0x14001a1ae  jz      short loc_14001A1CE
0x14001a1b0  cmp     byte ptr [rcx+19h], 4
0x14001a1b4  jb      short loc_14001A1CE
0x14001a1b6  mov     edx, 2Ah ; '*'
0x14001a1bb  mov     r9d, edi
0x14001a1be  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x14001a1c5  mov     rcx, [rcx+10h]
0x14001a1c9  call    WPP_SF_d
0x14001a1ce  mov     eax, edi
0x14001a1d0  mov     rcx, [rsp+328h+var_28]
0x14001a1d8  xor     rcx, rsp; StackCookie
0x14001a1db  call    __security_check_cookie
0x14001a1e0  lea     r11, [rsp+328h+var_18]
0x14001a1e8  mov     rbx, [r11+30h]
0x14001a1ec  mov     rsi, [r11+38h]
0x14001a1f0  mov     rsp, r11
0x14001a1f3  pop     r15
0x14001a1f5  pop     r14
0x14001a1f7  pop     rdi
0x14001a1f8  retn
0x14009dcf2  push    rbp
0x14009dcf4  sub     rsp, 60h
0x14009dcf8  mov     rbp, rdx
0x14009dcfb  mov     rcx, [rbp+60h]; hObject
0x14009dcff  test    rcx, rcx
0x14009dd02  jz      short loc_14009DD0B
0x14009dd04  call    cs:__imp_CloseHandle
0x14009dd0a  nop
0x14009dd0b  mov     rcx, [rbp+68h]; hObject
0x14009dd0f  test    rcx, rcx
0x14009dd12  jz      short loc_14009DD1B
0x14009dd14  call    cs:__imp_CloseHandle
0x14009dd1a  nop
0x14009dd1b  mov     rcx, [rbp+78h]; hObject
0x14009dd1f  test    rcx, rcx
0x14009dd22  jz      short loc_14009DD2B
0x14009dd24  call    cs:__imp_CloseHandle
0x14009dd2a  nop
0x14009dd2b  add     rsp, 60h
0x14009dd2f  pop     rbp
0x14009dd30  retn
```
