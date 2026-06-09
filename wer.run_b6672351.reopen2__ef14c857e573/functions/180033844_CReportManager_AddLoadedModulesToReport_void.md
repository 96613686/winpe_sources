# CReportManager::AddLoadedModulesToReport(void)

- ea: `0x180033844`
- end: `0x180033b92`
- name: `?AddLoadedModulesToReport@CReportManager@@AEAAJXZ`
- size: `846`
- prototype: `__int64 __fastcall(CReportManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x18007c77c`

## callees

- `0x180007fd8`
- `0x180008004`
- `0x18001c368`
- `0x180020680`
- `0x18002a0c4`
- `0x180033844`
- `0x180048b34`
- `0x18004b5f0`
- `0x18004c8d4`
- `0x180053300`
- `0x180053d3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800338ec`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180033971`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800338ec`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180033971`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003389f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003389f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b20`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180033921`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180033921`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180033a31`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180033a31`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x180033ab4`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x180033ab4`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x1800339c5`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x1800339c5`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18003398d`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18003398d`

## pseudocode

```c
__int64 __fastcall CReportManager::AddLoadedModulesToReport(CReportManager *this)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rcx
  __int64 v6; // rcx
  DWORD ProcessId; // eax
  HANDLE v8; // r14
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // edi
  wchar_t *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  HANDLE Toolhelp32Snapshot; // rax
  HANDLE v16; // rbx
  DWORD v17; // eax
  int v18; // eax
  DWORD v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  DWORD LastError; // eax
  DWORD TickCount; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE Process; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE hSnapshot[2]; // [rsp+30h] [rbp-D0h] BYREF
  MODULEENTRY32W me; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Filename[264]; // [rsp+480h] [rbp+380h] BYREF

  hSnapshot[0] = 0;
  Process = 0;
  memset_0(&me, 0, sizeof(me));
  Filename[0] = 0;
  TickCount = GetTickCount();
  v2 = *((_QWORD *)this + 1);
  v3 = *(_QWORD *)(v2 + 5848);
  v4 = *(_QWORD *)(v2 + 5856) - v3;
  *(_QWORD *)(v2 + 5856) = v3;
  utl::_RangeDestroyApc<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(
    v5,
    v3,
    v4 >> 5);
  v6 = *((_QWORD *)this + 1);
  if ( *(_QWORD *)(v6 + 6640) )
  {
    ProcessId = GetProcessId(*(HANDLE *)(v6 + 6640));
    v8 = *(HANDLE *)(*((_QWORD *)this + 1) + 6640LL);
  }
  else
  {
    v9 = *(_QWORD *)(v6 + 9112);
    if ( v9 )
    {
      v10 = PssQuerySnapshot(v9, 1, &Process);
      v11 = v10;
      if ( v10 )
      {
        if ( v10 > 0 )
          v11 = (unsigned __int16)v10 | 0x80070000;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v13 = 48;
          v14 = v11;
LABEL_35:
          WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, v14);
          goto LABEL_36;
        }
        goto LABEL_36;
      }
      ProcessId = GetProcessId(Process);
      v8 = Process;
    }
    else
    {
      v8 = 0;
      ProcessId = 0;
    }
  }
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(8u, ProcessId);
  tlx::unique_any<tlx::file_handle_traits>::reset(hSnapshot, Toolhelp32Snapshot);
  v16 = hSnapshot[0];
  if ( (unsigned __int64)hSnapshot[0] + 1 <= 1 )
  {
    LastError = GetLastError();
    v18 = ERROR_HR_FROM_WIN32(LastError);
    v11 = v18;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v13 = 49;
      goto LABEL_34;
    }
  }
  else
  {
    me.dwSize = 1080;
    if ( Module32FirstW(hSnapshot[0], &me) )
    {
      while ( 1 )
      {
        if ( !K32GetModuleFileNameExW(v8, me.hModule, Filename, 0x104u) )
        {
          v19 = GetLastError();
          v20 = ERROR_HR_FROM_WIN32(v19);
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, v20);
          StringCchCopyW(Filename, 0x104u, me.szExePath);
        }
        v18 = CReport::AddLoadedModule(*((CReport **)this + 1), Filename);
        v11 = v18;
        if ( v18 < 0 )
          break;
        if ( !Module32NextW(v16, &me) )
        {
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          {
            v21 = CTimer::Stop((CTimer *)&TickCount);
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, v21);
          }
          v11 = 0;
          goto LABEL_36;
        }
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 52;
        goto LABEL_34;
      }
    }
    else
    {
      v17 = GetLastError();
      v18 = ERROR_HR_FROM_WIN32(v17);
      v11 = v18;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 50;
LABEL_34:
        v14 = (unsigned int)v18;
        goto LABEL_35;
      }
    }
  }
LABEL_36:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(hSnapshot);
  return v11;
}

```

## disassembly

```asm
0x180033844  push    rbp
0x180033846  push    rbx
0x180033847  push    rsi
0x180033848  push    rdi
0x180033849  push    r14
0x18003384b  push    r15
0x18003384d  lea     rbp, [rsp-5A8h]
0x180033855  sub     rsp, 6A8h
0x18003385c  mov     rax, cs:__security_cookie
0x180033863  xor     rax, rsp
0x180033866  mov     [rbp+5D0h+var_40], rax
0x18003386d  mov     r15, rcx
0x180033870  mov     [rsp+6D0h+hSnapshot], 0
0x180033879  mov     esi, 438h
0x18003387e  mov     [rsp+6D0h+Process], 0
0x180033887  mov     r8d, esi; Size
0x18003388a  lea     rcx, [rsp+6D0h+me]; void *
0x18003388f  xor     edx, edx; Val
0x180033891  call    memset_0
0x180033896  xor     eax, eax
0x180033898  mov     [rbp+5D0h+Filename], ax
0x18003389f  call    cs:__imp_GetTickCount
0x1800338a6  nop     dword ptr [rax+rax+00h]
0x1800338ab  mov     [rsp+6D0h+var_6B0], eax
0x1800338af  mov     rax, [r15+8]
0x1800338b3  mov     rdx, [rax+16D8h]
0x1800338ba  mov     r8, [rax+16E0h]
0x1800338c1  sub     r8, rdx
0x1800338c4  mov     [rax+16E0h], rdx
0x1800338cb  sar     r8, 5
0x1800338cf  call    ??$_RangeDestroyApc@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@0@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64)
0x1800338d4  mov     rcx, [r15+8]
0x1800338d8  mov     ebx, 8
0x1800338dd  mov     rax, [rcx+19F0h]
0x1800338e4  test    rax, rax
0x1800338e7  jz      short loc_180033908
0x1800338e9  mov     rcx, rax; Process
0x1800338ec  call    cs:__imp_GetProcessId
0x1800338f3  nop     dword ptr [rax+rax+00h]
0x1800338f8  mov     rcx, [r15+8]
0x1800338fc  mov     r14, [rcx+19F0h]
0x180033903  jmp     loc_180033989
0x180033908  mov     rcx, [rcx+2398h]
0x18003390f  test    rcx, rcx
0x180033912  jz      short loc_180033984
0x180033914  mov     r9d, ebx
0x180033917  lea     r8, [rsp+6D0h+Process]
0x18003391c  mov     edx, 1
0x180033921  call    cs:__imp_PssQuerySnapshot
0x180033928  nop     dword ptr [rax+rax+00h]
0x18003392d  mov     edi, eax
0x18003392f  test    eax, eax
0x180033931  jz      short loc_18003396C
0x180033933  jle     short loc_18003393E
0x180033935  movzx   edi, ax
0x180033938  or      edi, 80070000h
0x18003393e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033945  lea     rsi, WPP_GLOBAL_Control
0x18003394c  cmp     rcx, rsi
0x18003394f  jz      loc_180033B66
0x180033955  test    byte ptr [rcx+1Ch], 1
0x180033959  jz      loc_180033B66
0x18003395f  mov     edx, 30h ; '0'
0x180033964  mov     r9d, edi
0x180033967  jmp     loc_180033B56
0x18003396c  mov     rcx, [rsp+6D0h+Process]; Process
0x180033971  call    cs:__imp_GetProcessId
0x180033978  nop     dword ptr [rax+rax+00h]
0x18003397d  mov     r14, [rsp+6D0h+Process]
0x180033982  jmp     short loc_180033989
0x180033984  xor     r14d, r14d
0x180033987  xor     eax, eax
0x180033989  mov     edx, eax; th32ProcessID
0x18003398b  mov     ecx, ebx; dwFlags
0x18003398d  call    cs:__imp_CreateToolhelp32Snapshot
0x180033994  nop     dword ptr [rax+rax+00h]
0x180033999  mov     rdx, rax
0x18003399c  lea     rcx, [rsp+6D0h+hSnapshot]
0x1800339a1  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800339a6  mov     rbx, [rsp+6D0h+hSnapshot]
0x1800339ab  lea     rax, [rbx+1]
0x1800339af  cmp     rax, 1
0x1800339b3  jbe     loc_180033B20
0x1800339b9  lea     rdx, [rsp+6D0h+me]; lpme
0x1800339be  mov     [rsp+6D0h+me.dwSize], esi
0x1800339c2  mov     rcx, rbx; hSnapshot
0x1800339c5  call    cs:__imp_Module32FirstW
0x1800339cc  nop     dword ptr [rax+rax+00h]
0x1800339d1  test    eax, eax
0x1800339d3  jnz     short loc_180033A15
0x1800339d5  call    cs:__imp_GetLastError
0x1800339dc  nop     dword ptr [rax+rax+00h]
0x1800339e1  mov     ecx, eax; unsigned int
0x1800339e3  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800339e8  mov     edi, eax
0x1800339ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800339f1  lea     rsi, WPP_GLOBAL_Control
0x1800339f8  cmp     rcx, rsi
0x1800339fb  jz      loc_180033B66
0x180033a01  test    byte ptr [rcx+1Ch], 1
0x180033a05  jz      loc_180033B66
0x180033a0b  mov     edx, 32h ; '2'
0x180033a10  jmp     loc_180033B53
0x180033a15  lea     rsi, WPP_GLOBAL_Control
0x180033a1c  mov     rdx, [rsp+6D0h+me.hModule]; hModule
0x180033a21  lea     r8, [rbp+5D0h+Filename]; lpFilename
0x180033a28  mov     r9d, 104h; nSize
0x180033a2e  mov     rcx, r14; hProcess
0x180033a31  call    cs:__imp_K32GetModuleFileNameExW
0x180033a38  nop     dword ptr [rax+rax+00h]
0x180033a3d  test    eax, eax
0x180033a3f  jnz     short loc_180033A96
0x180033a41  call    cs:__imp_GetLastError
0x180033a48  nop     dword ptr [rax+rax+00h]
0x180033a4d  mov     ecx, eax; unsigned int
0x180033a4f  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180033a54  mov     rcx, cs:WPP_GLOBAL_Control
0x180033a5b  cmp     rcx, rsi
0x180033a5e  jz      short loc_180033A7E
0x180033a60  test    byte ptr [rcx+1Ch], 1
0x180033a64  jz      short loc_180033A7E
0x180033a66  mov     rcx, [rcx+10h]
0x180033a6a  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x180033a71  mov     edx, 33h ; '3'
0x180033a76  mov     r9d, eax
0x180033a79  call    WPP_SF_d
0x180033a7e  lea     r8, [rbp+5D0h+me.szExePath]; wchar_t *
0x180033a85  mov     edx, 104h; unsigned __int64
0x180033a8a  lea     rcx, [rbp+5D0h+Filename]; wchar_t *
0x180033a91  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180033a96  mov     rcx, [r15+8]; this
0x180033a9a  lea     rdx, [rbp+5D0h+Filename]; wchar_t *
0x180033aa1  call    ?AddLoadedModule@CReport@@QEAAJPEB_W@Z; CReport::AddLoadedModule(wchar_t const *)
0x180033aa6  mov     edi, eax
0x180033aa8  test    eax, eax
0x180033aaa  js      short loc_180033B07
0x180033aac  lea     rdx, [rsp+6D0h+me]; lpme
0x180033ab1  mov     rcx, rbx; hSnapshot
0x180033ab4  call    cs:__imp_Module32NextW
0x180033abb  nop     dword ptr [rax+rax+00h]
0x180033ac0  test    eax, eax
0x180033ac2  jnz     loc_180033A1C
0x180033ac8  mov     rax, cs:WPP_GLOBAL_Control
0x180033acf  cmp     rax, rsi
0x180033ad2  jz      short loc_180033B03
0x180033ad4  test    byte ptr [rax+1Ch], 4
0x180033ad8  jz      short loc_180033B03
0x180033ada  lea     rcx, [rsp+6D0h+var_6B0]; this
0x180033adf  call    ?Stop@CTimer@@QEAAKXZ; CTimer::Stop(void)
0x180033ae4  mov     rcx, cs:WPP_GLOBAL_Control
0x180033aeb  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x180033af2  mov     edx, 35h ; '5'
0x180033af7  mov     r9d, eax
0x180033afa  mov     rcx, [rcx+10h]
0x180033afe  call    WPP_SF_d
0x180033b03  xor     edi, edi
0x180033b05  jmp     short loc_180033B66
0x180033b07  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b0e  cmp     rcx, rsi
0x180033b11  jz      short loc_180033B66
0x180033b13  test    byte ptr [rcx+1Ch], 1
0x180033b17  jz      short loc_180033B66
0x180033b19  mov     edx, 34h ; '4'
0x180033b1e  jmp     short loc_180033B53
0x180033b20  call    cs:__imp_GetLastError
0x180033b27  nop     dword ptr [rax+rax+00h]
0x180033b2c  mov     ecx, eax; unsigned int
0x180033b2e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180033b33  mov     edi, eax
0x180033b35  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b3c  lea     rsi, WPP_GLOBAL_Control
0x180033b43  cmp     rcx, rsi
0x180033b46  jz      short loc_180033B66
0x180033b48  test    byte ptr [rcx+1Ch], 1
0x180033b4c  jz      short loc_180033B66
0x180033b4e  mov     edx, 31h ; '1'
0x180033b53  mov     r9d, eax
0x180033b56  mov     rcx, [rcx+10h]
0x180033b5a  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x180033b61  call    WPP_SF_d
0x180033b66  lea     rcx, [rsp+6D0h+hSnapshot]
0x180033b6b  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180033b70  mov     eax, edi
0x180033b72  mov     rcx, [rbp+5D0h+var_40]
0x180033b79  xor     rcx, rsp; StackCookie
0x180033b7c  call    __security_check_cookie
0x180033b81  add     rsp, 6A8h
0x180033b88  pop     r15
0x180033b8a  pop     r14
0x180033b8c  pop     rdi
0x180033b8d  pop     rsi
0x180033b8e  pop     rbx
0x180033b8f  pop     rbp
0x180033b90  retn
```
