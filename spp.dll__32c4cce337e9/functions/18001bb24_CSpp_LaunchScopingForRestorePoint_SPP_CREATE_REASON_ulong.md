# CSpp::_LaunchScopingForRestorePoint(_SPP_CREATE_REASON,ulong)

- ea: `0x18001bb24`
- end: `0x18001be6b`
- name: `?_LaunchScopingForRestorePoint@CSpp@@AEAAJW4_SPP_CREATE_REASON@@K@Z`
- size: `839`
- prototype: `__int64 __fastcall(__int64, int, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013c7c`

## callees

- `0x18001b70c`
- `0x18001bb24`
- `0x180020710`
- `0x180020908`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x18002f358`
- `0x180034d70`
- `0x180034de0`
- `0x180034f54`
- `0x18003507c`
- `0x180035b00`
- `0x180035b9a`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001be13`
- `KERNEL32!CloseHandle` at `0x18001be26`
- `KERNEL32!CloseHandle` at `0x18001be13`
- `KERNEL32!CloseHandle` at `0x18001be26`
- `KERNEL32!CreateProcessW` at `0x18001bdd7`
- `KERNEL32!CreateProcessW` at `0x18001bdd7`

## string_xrefs

- `0x18001bcc3`: `%SystemRoot%\system32\srtasks.exe ExecuteScopeRestorePoint`

## pseudocode

```c
__int64 __fastcall CSpp::_LaunchScopingForRestorePoint(__int64 a1, int a2, unsigned int a3)
{
  CSpp *v5; // rcx
  __int16 v6; // ax
  __int16 v7; // ax
  int IsServerSku; // ecx
  unsigned int v9; // ebx
  int ScopedSnapshots; // [rsp+58h] [rbp-B0h] BYREF
  __int16 v12; // [rsp+5Ch] [rbp-ACh]
  __int16 v13; // [rsp+5Eh] [rbp-AAh]
  LPWSTR lpCommandLine[2]; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int16 *v15[2]; // [rsp+A0h] [rbp-68h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+B0h] [rbp-58h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v18; // [rsp+158h] [rbp+50h] BYREF

  v18 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&ScopedSnapshots,
    "CSpp::_LaunchScopingForRestorePoint",
    0x2CA7u,
    1u);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  lpCommandLine[1] = 0;
  v15[1] = 0;
  lpCommandLine[0] = (LPWSTR)&FileName;
  v15[0] = (unsigned __int16 *)&FileName;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  LOBYTE(v18) = 0;
  ScopedSnapshots = SxShouldCreateScopedSnapshots((unsigned __int8 *)&v18);
  v6 = 11455;
  if ( ScopedSnapshots < 0 )
    goto LABEL_5;
  v12 = 11455;
  if ( !(_BYTE)v18 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 196, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
    v7 = 11460;
    goto LABEL_35;
  }
  if ( ((a2 - 6) & 0xFFFFFFF6) == 0 && a2 != 14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
    v7 = 11471;
    goto LABEL_35;
  }
  IsServerSku = CSpp::_IsServerSku(v5);
  ScopedSnapshots = IsServerSku;
  v6 = 11474;
  if ( IsServerSku < 0 )
    goto LABEL_5;
  v12 = 11474;
  if ( !IsServerSku )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
    v7 = 11479;
    goto LABEL_35;
  }
  StartupInfo.cb = 104;
  ScopedSnapshots = CBsString::ExpandEnvironmentStringsW(
                      (CBsString *)lpCommandLine,
                      L"%SystemRoot%\\system32\\srtasks.exe ExecuteScopeRestorePoint");
  v6 = 11484;
  if ( ScopedSnapshots < 0 )
  {
LABEL_5:
    v13 = v6;
    goto LABEL_36;
  }
  v12 = 11484;
  if ( a3 )
  {
    ScopedSnapshots = CBsString::Format((CBsString *)v15, L"%lu", a3);
    v6 = 11488;
    if ( ScopedSnapshots < 0 )
      goto LABEL_5;
    v12 = 11488;
    ScopedSnapshots = CBsString::Append((CBsString *)lpCommandLine, L" ", L"/WaitForRestorePoint:");
    v6 = 11489;
    if ( ScopedSnapshots < 0 )
      goto LABEL_5;
    v12 = 11489;
    ScopedSnapshots = CBsString::Append((CBsString *)lpCommandLine, v15[0]);
    v6 = 11490;
    if ( ScopedSnapshots < 0 )
      goto LABEL_5;
    v12 = 11490;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      199,
      &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
      lpCommandLine[0]);
  if ( !CreateProcessW(0, lpCommandLine[0], 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    ScopedSnapshots = GetLastFailureAsHRESULT();
    v6 = 11503;
    goto LABEL_5;
  }
  v7 = 11503;
LABEL_35:
  v12 = v7;
  ScopedSnapshots = 0;
LABEL_36:
  if ( ProcessInformation.hProcess )
  {
    CloseHandle(ProcessInformation.hProcess);
    ProcessInformation.hProcess = (HANDLE)-1LL;
  }
  if ( ProcessInformation.hThread )
  {
    CloseHandle(ProcessInformation.hThread);
    ProcessInformation.hThread = (HANDLE)-1LL;
  }
  v9 = ScopedSnapshots;
  CBsString::_Release((CBsString *)v15);
  CBsString::_Release((CBsString *)lpCommandLine);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&ScopedSnapshots);
  return v9;
}

```

## disassembly

```asm
0x18001bb24  mov     rax, rsp
0x18001bb27  mov     [rax+10h], rbx
0x18001bb2b  mov     [rax+18h], rdi
0x18001bb2f  mov     [rax+8], rcx
0x18001bb33  push    rbp
0x18001bb34  push    r14
0x18001bb36  push    r15
0x18001bb38  lea     rbp, [rax-48h]
0x18001bb3c  sub     rsp, 130h
0x18001bb43  mov     edi, r8d
0x18001bb46  mov     ebx, edx
0x18001bb48  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb4f  lea     r14, WPP_GLOBAL_Control
0x18001bb56  lea     r15, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001bb5d  cmp     rcx, r14
0x18001bb60  jz      short loc_18001BB7C
0x18001bb62  test    dword ptr [rcx+1Ch], 20000000h
0x18001bb69  jz      short loc_18001BB7C
0x18001bb6b  mov     rcx, [rcx+10h]
0x18001bb6f  mov     edx, 0C3h
0x18001bb74  mov     r8, r15
0x18001bb77  call    WPP_SF_
0x18001bb7c  mov     r9d, 1; unsigned __int16
0x18001bb82  lea     rdx, aCsppLaunchscop; "CSpp::_LaunchScopingForRestorePoint"
0x18001bb89  mov     r8d, 2CA7h; unsigned __int16
0x18001bb8f  lea     rcx, [rsp+140h+var_F0]; this
0x18001bb94  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001bb99  xor     edx, edx; Val
0x18001bb9b  lea     rcx, [rbp+40h+StartupInfo]; void *
0x18001bb9f  lea     r8d, [rdx+68h]; Size
0x18001bba3  call    memset_0
0x18001bba8  xor     eax, eax
0x18001bbaa  mov     [rbp+40h+var_B0], 0
0x18001bbb2  mov     qword ptr [rbp+40h+ProcessInformation.dwProcessId], rax
0x18001bbb6  lea     rcx, [rbp+40h+arg_0]; unsigned __int8 *
0x18001bbba  lea     rax, FileName
0x18001bbc1  mov     [rbp+40h+var_A0], 0
0x18001bbc9  xorps   xmm0, xmm0
0x18001bbcc  mov     [rbp+40h+lpCommandLine], rax
0x18001bbd0  mov     [rbp+40h+var_A8], rax
0x18001bbd4  movups  xmmword ptr [rbp+40h+ProcessInformation.hProcess], xmm0
0x18001bbd8  mov     byte ptr [rbp+40h+arg_0], 0
0x18001bbdc  call    ?SxShouldCreateScopedSnapshots@@YAJPEAE@Z; SxShouldCreateScopedSnapshots(uchar *)
0x18001bbe1  mov     [rsp+140h+var_F0], eax
0x18001bbe5  test    eax, eax
0x18001bbe7  mov     eax, 2CBFh
0x18001bbec  jns     short loc_18001BBF8
0x18001bbee  mov     [rsp+140h+var_EA], ax
0x18001bbf3  jmp     loc_18001BE06
0x18001bbf8  cmp     byte ptr [rbp+40h+arg_0], 0
0x18001bbfc  mov     [rsp+140h+var_EC], ax
0x18001bc01  jnz     short loc_18001BC33
0x18001bc03  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc0a  cmp     rcx, r14
0x18001bc0d  jz      short loc_18001BC29
0x18001bc0f  test    dword ptr [rcx+1Ch], 8000000h
0x18001bc16  jz      short loc_18001BC29
0x18001bc18  mov     rcx, [rcx+10h]
0x18001bc1c  mov     edx, 0C4h
0x18001bc21  mov     r8, r15
0x18001bc24  call    WPP_SF_
0x18001bc29  mov     eax, 2CC4h
0x18001bc2e  jmp     loc_18001BDF9
0x18001bc33  lea     eax, [rbx-6]
0x18001bc36  test    eax, 0FFFFFFF6h
0x18001bc3b  jnz     short loc_18001BC72
0x18001bc3d  cmp     ebx, 0Eh
0x18001bc40  jz      short loc_18001BC72
0x18001bc42  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc49  cmp     rcx, r14
0x18001bc4c  jz      short loc_18001BC68
0x18001bc4e  test    dword ptr [rcx+1Ch], 8000000h
0x18001bc55  jz      short loc_18001BC68
0x18001bc57  mov     rcx, [rcx+10h]
0x18001bc5b  mov     edx, 0C5h
0x18001bc60  mov     r8, r15
0x18001bc63  call    WPP_SF_
0x18001bc68  mov     eax, 2CCFh
0x18001bc6d  jmp     loc_18001BDF9
0x18001bc72  call    ?_IsServerSku@CSpp@@AEAAJXZ; CSpp::_IsServerSku(void)
0x18001bc77  mov     ecx, eax
0x18001bc79  mov     [rsp+140h+var_F0], eax
0x18001bc7d  test    eax, eax
0x18001bc7f  mov     eax, 2CD2h
0x18001bc84  js      loc_18001BBEE
0x18001bc8a  mov     [rsp+140h+var_EC], ax
0x18001bc8f  test    ecx, ecx
0x18001bc91  jnz     short loc_18001BCC3
0x18001bc93  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc9a  cmp     rcx, r14
0x18001bc9d  jz      short loc_18001BCB9
0x18001bc9f  test    dword ptr [rcx+1Ch], 8000000h
0x18001bca6  jz      short loc_18001BCB9
0x18001bca8  mov     rcx, [rcx+10h]
0x18001bcac  mov     edx, 0C6h
0x18001bcb1  mov     r8, r15
0x18001bcb4  call    WPP_SF_
0x18001bcb9  mov     eax, 2CD7h
0x18001bcbe  jmp     loc_18001BDF9
0x18001bcc3  lea     rdx, aSystemrootSyst; "%SystemRoot%\\system32\\srtasks.exe Exe"...
0x18001bcca  mov     [rbp+40h+StartupInfo.cb], 68h ; 'h'
0x18001bcd1  lea     rcx, [rbp+40h+lpCommandLine]; this
0x18001bcd5  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x18001bcda  mov     [rsp+140h+var_F0], eax
0x18001bcde  test    eax, eax
0x18001bce0  mov     eax, 2CDCh
0x18001bce5  js      loc_18001BBEE
0x18001bceb  mov     [rsp+140h+var_EC], ax
0x18001bcf0  test    edi, edi
0x18001bcf2  jz      short loc_18001BD6D
0x18001bcf4  mov     r8d, edi
0x18001bcf7  lea     rdx, aLu; "%lu"
0x18001bcfe  lea     rcx, [rbp+40h+var_A8]; this
0x18001bd02  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x18001bd07  mov     [rsp+140h+var_F0], eax
0x18001bd0b  test    eax, eax
0x18001bd0d  mov     eax, 2CE0h
0x18001bd12  js      loc_18001BBEE
0x18001bd18  lea     r8, aWaitforrestore; "/WaitForRestorePoint:"
0x18001bd1f  mov     [rsp+140h+var_EC], ax
0x18001bd24  lea     rdx, asc_18003A418; " "
0x18001bd2b  lea     rcx, [rbp+40h+lpCommandLine]; this
0x18001bd2f  call    ?Append@CBsString@@QEAAJPEBG0@Z; CBsString::Append(ushort const *,ushort const *)
0x18001bd34  mov     [rsp+140h+var_F0], eax
0x18001bd38  test    eax, eax
0x18001bd3a  mov     eax, 2CE1h
0x18001bd3f  js      loc_18001BBEE
0x18001bd45  mov     rdx, [rbp+40h+var_A8]; unsigned __int16 *
0x18001bd49  lea     rcx, [rbp+40h+lpCommandLine]; this
0x18001bd4d  mov     [rsp+140h+var_EC], ax
0x18001bd52  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18001bd57  mov     [rsp+140h+var_F0], eax
0x18001bd5b  test    eax, eax
0x18001bd5d  mov     eax, 2CE2h
0x18001bd62  js      loc_18001BBEE
0x18001bd68  mov     [rsp+140h+var_EC], ax
0x18001bd6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd74  cmp     rcx, r14
0x18001bd77  jz      short loc_18001BD97
0x18001bd79  test    dword ptr [rcx+1Ch], 8000000h
0x18001bd80  jz      short loc_18001BD97
0x18001bd82  mov     r9, [rbp+40h+lpCommandLine]
0x18001bd86  mov     edx, 0C7h
0x18001bd8b  mov     rcx, [rcx+10h]
0x18001bd8f  mov     r8, r15
0x18001bd92  call    WPP_SF_S
0x18001bd97  mov     rdx, [rbp+40h+lpCommandLine]; lpCommandLine
0x18001bd9b  lea     rax, [rbp+40h+ProcessInformation]
0x18001bd9f  mov     [rsp+140h+lpProcessInformation], rax; lpProcessInformation
0x18001bda4  xor     r9d, r9d; lpThreadAttributes
0x18001bda7  lea     rax, [rbp+40h+StartupInfo]
0x18001bdab  xor     r8d, r8d; lpProcessAttributes
0x18001bdae  mov     [rsp+140h+lpStartupInfo], rax; lpStartupInfo
0x18001bdb3  xor     ecx, ecx; lpApplicationName
0x18001bdb5  mov     [rsp+140h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18001bdbe  mov     [rsp+140h+lpEnvironment], 0; lpEnvironment
0x18001bdc7  mov     [rsp+140h+dwCreationFlags], 8000000h; dwCreationFlags
0x18001bdcf  mov     [rsp+140h+bInheritHandles], 0; bInheritHandles
0x18001bdd7  call    cs:__imp_CreateProcessW
0x18001bddd  test    eax, eax
0x18001bddf  jnz     short loc_18001BDF4
0x18001bde1  call    GetLastFailureAsHRESULT
0x18001bde6  mov     [rsp+140h+var_F0], eax
0x18001bdea  mov     eax, 2CEFh
0x18001bdef  jmp     loc_18001BBEE
0x18001bdf4  mov     eax, 2CEFh
0x18001bdf9  mov     [rsp+140h+var_EC], ax
0x18001bdfe  mov     [rsp+140h+var_F0], 0
0x18001be06  mov     rcx, [rbp+40h+ProcessInformation.hProcess]; hObject
0x18001be0a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001be0e  test    rcx, rcx
0x18001be11  jz      short loc_18001BE1D
0x18001be13  call    cs:__imp_CloseHandle
0x18001be19  mov     [rbp+40h+ProcessInformation.hProcess], rbx
0x18001be1d  mov     rcx, [rbp+40h+ProcessInformation.hThread]; hObject
0x18001be21  test    rcx, rcx
0x18001be24  jz      short loc_18001BE30
0x18001be26  call    cs:__imp_CloseHandle
0x18001be2c  mov     [rbp+40h+ProcessInformation.hThread], rbx
0x18001be30  mov     ebx, [rsp+140h+var_F0]
0x18001be34  lea     rcx, [rbp+40h+var_A8]; this
0x18001be38  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001be3d  lea     rcx, [rbp+40h+lpCommandLine]; this
0x18001be41  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001be46  lea     rcx, [rsp+140h+var_F0]; this
0x18001be4b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001be50  lea     r11, [rsp+140h+var_10]
0x18001be58  mov     eax, ebx
0x18001be5a  mov     rbx, [r11+28h]
0x18001be5e  mov     rdi, [r11+30h]
0x18001be62  mov     rsp, r11
0x18001be65  pop     r15
0x18001be67  pop     r14
0x18001be69  pop     rbp
0x18001be6a  retn
```
