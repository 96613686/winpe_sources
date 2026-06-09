# WinSATInitiateAssessment

- ea: `0x180012af0`
- end: `0x180013120`
- name: `WinSATInitiateAssessment`
- size: `1584`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001e560`

## callees

- `0x180004040`
- `0x1800071d0`
- `0x180007220`
- `0x18000ac70`
- `0x18000e864`
- `0x1800112c8`
- `0x180012af0`
- `0x180013128`
- `0x1800151bb`
- `0x18001c9e8`
- `0x18001ca88`
- `0x18001cb1c`
- `0x18001cb70`
- `0x18001cbe0`
- `0x18001cc2c`
- `0x18001cf28`
- `0x18001cf78`
- `0x18001d340`
- `0x18001d3e8`
- `0x18001d438`
- `0x18001d490`
- `0x18001d63c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012da7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012da7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012dbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012dbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013029`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800130ea`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800130ea`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012f1c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012f1c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18001303a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18001303a`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180013094`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180013094`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180012f9b`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180012f9b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180012ec9`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180012ec9`
- `USER32!IsWindow` at `0x180012b9b`
- `USER32!IsWindow` at `0x180012b9b`
- `SHELL32!ShellExecuteExW` at `0x18001301f`
- `SHELL32!ShellExecuteExW` at `0x18001301f`

## string_xrefs

- `0x180012caf`: `signaloncompletion`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinSATInitiateAssessment(_WORD *a1, __int64 a2, __int64 *a3, __int64 a4, HWND *a5, HWND a6)
{
  __int64 result; // rax
  unsigned __int64 v9; // rax
  HWND *v10; // rsi
  char has_switch_word; // r14
  signed int TheCancelEvent; // edi
  _QWORD *v13; // rcx
  bool v14; // di
  int v15; // edi
  signed int LastError; // eax
  unsigned int v17; // ebx
  signed int v18; // ebx
  ULONG v19; // eax
  __int64 v20; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v21; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v23; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+50h] [rbp-C8h] BYREF
  PVOID OldValue; // [rsp+58h] [rbp-C0h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+60h] [rbp-B8h] BYREF
  _QWORD v27[3]; // [rsp+78h] [rbp-A0h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+90h] [rbp-88h] BYREF
  __int64 *v29; // [rsp+130h] [rbp+18h] BYREF

  v29 = a3;
  v27[1] = -2;
  if ( g_InitCount <= 0 )
    return 2147745793LL;
  if ( g_RunState == 1 )
    return 2147745849LL;
  if ( g_RunState == 2 )
    WinSATGetCompletionStatus();
  result = ProbeString(a1);
  if ( (int)result >= 0 )
  {
    try
    {
      v9 = mlib::m_traits<unsigned short>::CStrlen(a1, 0x10000);
    }
    catch ( mlib::CStringTooBig )
    {
      return 2147745802LL;
    }
    try
    {
      if ( v9 > 0x3800 )
        return 2147745802LL;
      v10 = a5;
      if ( *a5 && !IsWindow(*a5) )
        return 2147745804LL;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v29,
        a1);
      v24 = 0;
      has_switch_word = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                          &v29,
                          L"showconwin",
                          &v24);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v20,
        260);
      GetSystemDirectoryInMString(&v20);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::ensure_trailing_slash(&v20);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
        &v20,
        L"winsat.exe");
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v22,
        128);
      TheCancelEvent = CreateTheCancelEvent(&qword_18004DE78, (__int64)&v22);
      if ( TheCancelEvent < 0 )
      {
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v22);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v20);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v29);
        return (unsigned int)TheCancelEvent;
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v21,
        128);
      v13 = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::first_token(
              &v29,
              v27);
      v14 = 0;
      if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::eqi(v13) )
      {
        v24 = 0;
        if ( !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                                 &v29,
                                 L"signaloncompletion",
                                 &v24) )
          v14 = 1;
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v27);
      if ( v14 )
      {
        if ( (unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::UuidCreate(&v21) )
        {
          ResetGlobalState();
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v21);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v22);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v20);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v29);
          return 2147942408LL;
        }
        *(_QWORD *)&EventAttributes.nLength = 24;
        *(_QWORD *)&EventAttributes.bInheritHandle = 1;
        EventAttributes.lpSecurityDescriptor = 0;
        v15 = SetAdminRights(&EventAttributes);
        if ( v15 < 0 )
        {
          ResetGlobalState();
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v21);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v22);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v20);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v29);
          return (unsigned int)v15;
        }
        qword_18004DE90 = CreateEventW(&EventAttributes, 0, 0, *(LPCWSTR *)(v21 + 24));
        if ( !qword_18004DE90 )
        {
          ResetGlobalState();
          LastError = GetLastError();
          v17 = LastError;
          if ( LastError > 0 )
            v17 = (unsigned __int16)LastError | 0x80070000;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v21);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v22);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v20);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v29);
          return v17;
        }
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v23,
        1024);
      if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(&v29) )
      {
        ResetGlobalState();
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v23);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v21);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v22);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v20);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v29);
        return 2147745801LL;
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
        &v23,
        &v29);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spfa(
        &v23,
        L" -cancelevent %s",
        *(_QWORD *)(v22 + 24));
      if ( qword_18004DE90 )
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spfa(
          &v23,
          L" -moobegoevent %s",
          *(_QWORD *)(v21 + 24));
      Ptr = EncodePointer(CInitiateWinSAT::WinSATCompletionRoutine);
      qword_18004DE68 = a4;
      *(_OWORD *)&hWnd = *(_OWORD *)v10;
      *(_OWORD *)&wParam = *((_OWORD *)v10 + 1);
      xmmword_18004DEC8 = *((_OWORD *)v10 + 2);
      hThread = CreateThread(0, 0, WinSATWaitngThread, 0, 4u, 0);
      if ( !hThread )
      {
        v18 = GetLastError();
        ResetGlobalState();
        if ( v18 > 0 )
          v18 = (unsigned __int16)v18 | 0x80070000;
LABEL_36:
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v23);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v21);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v22);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v20);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v29);
        return (unsigned int)v18;
      }
      CreateStatusObjects();
      OldValue = 0;
      Wow64DisableWow64FsRedirection(&OldValue);
      memset_0(&pExecInfo.lpFile, 0, 0x58u);
      pExecInfo.cbSize = 112;
      v19 = 17472;
      if ( !has_switch_word )
        v19 = 50240;
      pExecInfo.fMask = v19;
      pExecInfo.hwnd = a6;
      pExecInfo.lpVerb = L"open";
      pExecInfo.lpFile = *(LPCWSTR *)(v20 + 24);
      pExecInfo.lpParameters = *(LPCWSTR *)(v23 + 24);
      if ( !ShellExecuteExW(&pExecInfo) )
      {
        v18 = GetLastError();
        TerminateThread(hThread, 0);
        ResetGlobalState();
        if ( v18 > 0 )
          v18 = (unsigned __int16)v18 | 0x80070000;
        goto LABEL_36;
      }
      Wow64RevertWow64FsRedirection(OldValue);
      g_WinSATProcessInfo = pExecInfo.hProcess;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v23);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v21);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v22);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v20);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v29);
      ResumeThread(hThread);
      _InterlockedExchange(&g_RunState, 1);
      result = 0;
    }
    catch ( ... )
    {
      if ( hThread )
        TerminateThread(hThread, 0);
      ResetGlobalState();
      return 2147942408LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012af0  mov     rax, rsp
0x180012af3  mov     [rax+18h], r8
0x180012af7  mov     [rax+10h], edx
0x180012afa  push    rdi
0x180012afb  push    r14
0x180012afd  push    r15
0x180012aff  sub     rsp, 100h
0x180012b06  mov     qword ptr [rax-98h], 0FFFFFFFFFFFFFFFEh
0x180012b11  mov     [rax+8], rbx
0x180012b15  mov     [rax+20h], rsi
0x180012b19  mov     r15, r9
0x180012b1c  mov     rdi, rcx
0x180012b1f  mov     dword ptr [rax+10h], 0
0x180012b26  cmp     cs:?g_InitCount@@3JA, 0; long g_InitCount
0x180012b2d  jg      short loc_180012B39
0x180012b2f  mov     eax, 80040001h
0x180012b34  jmp     loc_180013106
0x180012b39  mov     eax, cs:?g_RunState@@3JA; long g_RunState
0x180012b3f  mov     ebx, 1
0x180012b44  cmp     eax, ebx
0x180012b46  jnz     short loc_180012B52
0x180012b48  mov     eax, 80040039h
0x180012b4d  jmp     loc_180013106
0x180012b52  cmp     eax, 2
0x180012b55  jnz     short loc_180012B5C
0x180012b57  call    WinSATGetCompletionStatus
0x180012b5c  mov     rcx, rdi
0x180012b5f  call    ProbeString
0x180012b64  test    eax, eax
0x180012b66  js      loc_180013106
0x180012b6c  mov     edx, 10000h
0x180012b71  mov     rcx, rdi
0x180012b74  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x180012b79  cmp     rax, 3800h
0x180012b7f  jbe     short loc_180012B8B
0x180012b81  mov     eax, 8004000Ah
0x180012b86  jmp     loc_180013106
0x180012b8b  mov     rsi, [rsp+118h+arg_20]
0x180012b93  mov     rcx, [rsi]; hWnd
0x180012b96  test    rcx, rcx
0x180012b99  jz      short loc_180012BAF
0x180012b9b  call    cs:__imp_IsWindow
0x180012ba1  test    eax, eax
0x180012ba3  jnz     short loc_180012BAF
0x180012ba5  mov     eax, 8004000Ch
0x180012baa  jmp     loc_180013106
0x180012baf  mov     rdx, rdi
0x180012bb2  lea     rcx, [rsp+118h+arg_10]
0x180012bba  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x180012bbf  nop
0x180012bc0  mov     [rsp+118h+var_C8], 0
0x180012bc9  lea     r8, [rsp+118h+var_C8]
0x180012bce  lea     rdx, aShowconwin; "showconwin"
0x180012bd5  lea     rcx, [rsp+118h+arg_10]
0x180012bdd  call    ?has_switch_word@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NPEBGAEA_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::has_switch_word(ushort const *,unsigned __int64 &,bool)
0x180012be2  mov     r14b, al
0x180012be5  mov     edx, 104h
0x180012bea  lea     rcx, [rsp+118h+var_E8]
0x180012bef  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x180012bf4  nop
0x180012bf5  lea     rcx, [rsp+118h+var_E8]
0x180012bfa  call    ?GetSystemDirectoryInMString@@YAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; GetSystemDirectoryInMString(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180012bff  lea     rcx, [rsp+118h+var_E8]
0x180012c04  call    ?ensure_trailing_slash@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::ensure_trailing_slash(void)
0x180012c09  lea     rdx, aWinsatExe; "winsat.exe"
0x180012c10  lea     rcx, [rsp+118h+var_E8]
0x180012c15  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x180012c1a  mov     edx, 80h
0x180012c1f  lea     rcx, [rsp+118h+var_D8]
0x180012c24  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x180012c29  nop
0x180012c2a  lea     rdx, [rsp+118h+var_D8]
0x180012c2f  lea     rcx, qword_18004DE78
0x180012c36  call    ?CreateTheCancelEvent@@YAJAEAPEAXAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; CreateTheCancelEvent(void * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180012c3b  mov     edi, eax
0x180012c3d  test    eax, eax
0x180012c3f  jns     short loc_180012C6B
0x180012c41  lea     rcx, [rsp+118h+var_D8]
0x180012c46  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012c4b  nop
0x180012c4c  lea     rcx, [rsp+118h+var_E8]
0x180012c51  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012c56  nop
0x180012c57  lea     rcx, [rsp+118h+arg_10]
0x180012c5f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012c64  mov     eax, edi
0x180012c66  jmp     loc_180013106
0x180012c6b  mov     edx, 80h
0x180012c70  lea     rcx, [rsp+118h+var_E0]
0x180012c75  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x180012c7a  nop
0x180012c7b  lea     rdx, [rsp+118h+var_A0]
0x180012c80  lea     rcx, [rsp+118h+arg_10]
0x180012c88  call    ?first_token@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA?AV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::first_token(ushort const *)
0x180012c8d  nop
0x180012c8e  mov     [rsp+118h+arg_8], ebx
0x180012c95  mov     rcx, rax
0x180012c98  call    ?eqi@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NPEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::eqi(ushort const *)
0x180012c9d  test    al, al
0x180012c9f  jz      short loc_180012CCC
0x180012ca1  mov     [rsp+118h+var_C8], 0
0x180012caa  lea     r8, [rsp+118h+var_C8]
0x180012caf  lea     rdx, aSignaloncomple; "signaloncompletion"
0x180012cb6  lea     rcx, [rsp+118h+arg_10]
0x180012cbe  call    ?has_switch_word@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NPEBGAEA_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::has_switch_word(ushort const *,unsigned __int64 &,bool)
0x180012cc3  test    al, al
0x180012cc5  jnz     short loc_180012CCC
0x180012cc7  mov     dil, bl
0x180012cca  jmp     short loc_180012CCF
0x180012ccc  xor     dil, dil
0x180012ccf  lea     rcx, [rsp+118h+var_A0]
0x180012cd4  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012cd9  test    dil, dil
0x180012cdc  jz      loc_180012E08
0x180012ce2  lea     rcx, [rsp+118h+var_E0]
0x180012ce7  call    ?UuidCreate@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAJXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::UuidCreate(void)
0x180012cec  test    eax, eax
0x180012cee  jz      short loc_180012D2E
0x180012cf0  call    ResetGlobalState
0x180012cf5  nop
0x180012cf6  lea     rcx, [rsp+118h+var_E0]
0x180012cfb  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012d00  nop
0x180012d01  lea     rcx, [rsp+118h+var_D8]
0x180012d06  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012d0b  nop
0x180012d0c  lea     rcx, [rsp+118h+var_E8]
0x180012d11  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012d16  nop
0x180012d17  lea     rcx, [rsp+118h+arg_10]
0x180012d1f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012d24  mov     eax, 80070008h
0x180012d29  jmp     loc_180013106
0x180012d2e  mov     qword ptr [rsp+118h+EventAttributes.nLength], 18h
0x180012d37  mov     qword ptr [rsp+118h+EventAttributes.bInheritHandle], 1
0x180012d40  mov     [rsp+118h+EventAttributes.lpSecurityDescriptor], 0
0x180012d49  lea     rcx, [rsp+118h+EventAttributes]
0x180012d4e  call    SetAdminRights
0x180012d53  mov     edi, eax
0x180012d55  test    eax, eax
0x180012d57  jns     short loc_180012D94
0x180012d59  call    ResetGlobalState
0x180012d5e  nop
0x180012d5f  lea     rcx, [rsp+118h+var_E0]
0x180012d64  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012d69  nop
0x180012d6a  lea     rcx, [rsp+118h+var_D8]
0x180012d6f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012d74  nop
0x180012d75  lea     rcx, [rsp+118h+var_E8]
0x180012d7a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012d7f  nop
0x180012d80  lea     rcx, [rsp+118h+arg_10]
0x180012d88  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012d8d  mov     eax, edi
0x180012d8f  jmp     loc_180013106
0x180012d94  mov     r9, [rsp+118h+var_E0]
0x180012d99  mov     r9, [r9+18h]; lpName
0x180012d9d  xor     r8d, r8d; bInitialState
0x180012da0  xor     edx, edx; bManualReset
0x180012da2  lea     rcx, [rsp+118h+EventAttributes]; lpEventAttributes
0x180012da7  call    cs:__imp_CreateEventW
0x180012dad  mov     cs:qword_18004DE90, rax
0x180012db4  test    rax, rax
0x180012db7  jnz     short loc_180012E08
0x180012db9  call    ResetGlobalState
0x180012dbe  call    cs:__imp_GetLastError
0x180012dc4  mov     ebx, eax
0x180012dc6  test    eax, eax
0x180012dc8  jle     short loc_180012DD3
0x180012dca  movzx   ebx, ax
0x180012dcd  or      ebx, 80070000h
0x180012dd3  lea     rcx, [rsp+118h+var_E0]
0x180012dd8  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012ddd  nop
0x180012dde  lea     rcx, [rsp+118h+var_D8]
0x180012de3  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012de8  nop
0x180012de9  lea     rcx, [rsp+118h+var_E8]
0x180012dee  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012df3  nop
0x180012df4  lea     rcx, [rsp+118h+arg_10]
0x180012dfc  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012e01  mov     eax, ebx
0x180012e03  jmp     loc_180013106
0x180012e08  mov     edx, 400h
0x180012e0d  lea     rcx, [rsp+118h+var_D0]
0x180012e12  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x180012e17  nop
0x180012e18  lea     rcx, [rsp+118h+arg_10]
0x180012e20  call    ?is_blank@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_blank(void)
0x180012e25  test    al, al
0x180012e27  jz      short loc_180012E72
0x180012e29  call    ResetGlobalState
0x180012e2e  nop
0x180012e2f  lea     rcx, [rsp+118h+var_D0]
0x180012e34  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012e39  nop
0x180012e3a  lea     rcx, [rsp+118h+var_E0]
0x180012e3f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012e44  nop
0x180012e45  lea     rcx, [rsp+118h+var_D8]
0x180012e4a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012e4f  nop
0x180012e50  lea     rcx, [rsp+118h+var_E8]
0x180012e55  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012e5a  nop
0x180012e5b  lea     rcx, [rsp+118h+arg_10]
0x180012e63  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012e68  mov     eax, 80040009h
0x180012e6d  jmp     loc_180013106
0x180012e72  lea     rdx, [rsp+118h+arg_10]
0x180012e7a  lea     rcx, [rsp+118h+var_D0]
0x180012e7f  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@AEBV12@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x180012e84  mov     r8, [rsp+118h+var_D8]
0x180012e89  mov     r8, [r8+18h]
0x180012e8d  lea     rdx, aCanceleventS; " -cancelevent %s"
0x180012e94  lea     rcx, [rsp+118h+var_D0]
0x180012e99  call    ?spfa@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spfa(ushort const *,...)
0x180012e9e  cmp     cs:qword_18004DE90, 0
0x180012ea6  jz      short loc_180012EC2
0x180012ea8  mov     r8, [rsp+118h+var_E0]
0x180012ead  mov     r8, [r8+18h]
0x180012eb1  lea     rdx, aMoobegoeventS; " -moobegoevent %s"
0x180012eb8  lea     rcx, [rsp+118h+var_D0]
0x180012ebd  call    ?spfa@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spfa(ushort const *,...)
0x180012ec2  lea     rcx, ?WinSATCompletionRoutine@CInitiateWinSAT@@CAXPEAX0@Z; Ptr
0x180012ec9  call    cs:__imp_EncodePointer
0x180012ecf  mov     cs:Ptr, rax
0x180012ed6  mov     cs:qword_18004DE68, r15
0x180012edd  movaps  xmm0, xmmword ptr [rsi]
0x180012ee0  movups  cs:hWnd, xmm0
0x180012ee7  movaps  xmm1, xmmword ptr [rsi+10h]
0x180012eeb  movups  cs:wParam, xmm1
0x180012ef2  movaps  xmm0, xmmword ptr [rsi+20h]
0x180012ef6  movups  cs:xmmword_18004DEC8, xmm0
0x180012efd  mov     [rsp+118h+lpThreadId], 0; lpThreadId
0x180012f06  mov     [rsp+118h+dwCreationFlags], 4; dwCreationFlags
0x180012f0e  xor     r9d, r9d; lpParameter
0x180012f11  lea     r8, WinSATWaitngThread; lpStartAddress
0x180012f18  xor     edx, edx; dwStackSize
0x180012f1a  xor     ecx, ecx; lpThreadAttributes
0x180012f1c  call    cs:__imp_CreateThread
0x180012f22  mov     cs:hThread, rax
0x180012f29  test    rax, rax
0x180012f2c  jnz     short loc_180012F88
0x180012f2e  call    cs:__imp_GetLastError
0x180012f34  mov     ebx, eax
0x180012f36  call    ResetGlobalState
0x180012f3b  test    ebx, ebx
0x180012f3d  jle     short loc_180012F48
0x180012f3f  movzx   ebx, bx
0x180012f42  or      ebx, 80070000h
0x180012f48  lea     rcx, [rsp+118h+var_D0]
0x180012f4d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012f52  nop
0x180012f53  lea     rcx, [rsp+118h+var_E0]
0x180012f58  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012f5d  nop
0x180012f5e  lea     rcx, [rsp+118h+var_D8]
0x180012f63  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012f68  nop
0x180012f69  lea     rcx, [rsp+118h+var_E8]
0x180012f6e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012f73  nop
0x180012f74  lea     rcx, [rsp+118h+arg_10]
0x180012f7c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180012f81  mov     eax, ebx
0x180012f83  jmp     loc_180013106
0x180012f88  call    CreateStatusObjects
0x180012f8d  mov     [rsp+118h+OldValue], 0
0x180012f96  lea     rcx, [rsp+118h+OldValue]; OldValue
0x180012f9b  call    cs:__imp_Wow64DisableWow64FsRedirection
0x180012fa1  xor     edx, edx; Val
0x180012fa3  lea     r8d, [rdx+58h]; Size
0x180012fa7  lea     rcx, [rsp+118h+pExecInfo.lpFile]; void *
0x180012faf  call    memset_0
0x180012fb4  mov     [rsp+118h+pExecInfo.cbSize], 70h ; 'p'
0x180012fbf  mov     eax, 4440h
0x180012fc4  mov     ecx, 0C440h
0x180012fc9  test    r14b, r14b
0x180012fcc  cmovz   eax, ecx
0x180012fcf  mov     [rsp+118h+pExecInfo.fMask], eax
0x180012fd6  mov     rax, [rsp+118h+arg_28]
0x180012fde  mov     [rsp+118h+pExecInfo.hwnd], rax
0x180012fe6  lea     rax, aOpen; "open"
0x180012fed  mov     [rsp+118h+pExecInfo.lpVerb], rax
0x180012ff5  mov     rax, [rsp+118h+var_E8]
0x180012ffa  mov     rcx, [rax+18h]
0x180012ffe  mov     [rsp+118h+pExecInfo.lpFile], rcx
0x180013006  mov     rax, [rsp+118h+var_D0]
0x18001300b  mov     rcx, [rax+18h]
0x18001300f  mov     [rsp+118h+pExecInfo.lpParameters], rcx
0x180013017  lea     rcx, [rsp+118h+pExecInfo]; pExecInfo
0x18001301f  call    cs:__imp_ShellExecuteExW
0x180013025  test    eax, eax
0x180013027  jnz     short loc_18001308F
0x180013029  call    cs:__imp_GetLastError
0x18001302f  mov     ebx, eax
0x180013031  xor     edx, edx; dwExitCode
  ... truncated ...
```
