# CMonitorEvents::CreateProcess_(ushort *,CMonitorEvents *,ResyncPerfTask *)

- ea: `0x180004ccc`
- end: `0x180004f3c`
- name: `?CreateProcess_@CMonitorEvents@@SAHPEAGPEAV1@PEAVResyncPerfTask@@@Z`
- size: `624`
- prototype: `__int64 __fastcall(LPWSTR lpCommandLine, struct CMonitorEvents *, struct ResyncPerfTask *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180004390`
- `0x180004900`

## callees

- `0x180004ccc`
- `0x18000b648`
- `0x180012c34`
- `0x18001323c`
- `0x180016b6c`
- `0x18001d377`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004eae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004eae`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180004e1c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180004e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ee8`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180004e5a`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180004e5a`
- `wbemcomn!?Enter@CStaticCritSec@@QEAAXXZ` at `0x180004d81`
- `wbemcomn!?Enter@CStaticCritSec@@QEAAXXZ` at `0x180004f09`
- `wbemcomn!?Enter@CStaticCritSec@@QEAAXXZ` at `0x180004d81`
- `wbemcomn!?Enter@CStaticCritSec@@QEAAXXZ` at `0x180004f09`
- `wbemcomn!?Leave@CStaticCritSec@@QEAAXXZ` at `0x180004d92`
- `wbemcomn!?Leave@CStaticCritSec@@QEAAXXZ` at `0x180004f1a`
- `wbemcomn!?Leave@CStaticCritSec@@QEAAXXZ` at `0x180004d92`
- `wbemcomn!?Leave@CStaticCritSec@@QEAAXXZ` at `0x180004f1a`
- `wbemcomn!GetWMIADAPCmdLine` at `0x180004d1d`
- `wbemcomn!GetWMIADAPCmdLine` at `0x180004d1d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180004d45`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180004eca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180004d45`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180004eca`
- `wbemcomn!GetMemLogObject` at `0x180004d39`
- `wbemcomn!GetMemLogObject` at `0x180004ebe`
- `wbemcomn!GetMemLogObject` at `0x180004d39`
- `wbemcomn!GetMemLogObject` at `0x180004ebe`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180004f24`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180004f24`

## pseudocode

```c
__int64 __fastcall CMonitorEvents::CreateProcess_(
        LPWSTR lpCommandLine,
        struct CMonitorEvents *a2,
        struct ResyncPerfTask *a3)
{
  WCHAR *WMIADAPCmdLine; // rbp
  CMemoryLog *v7; // rax
  unsigned int v9; // r15d
  HANDLE hProcess; // rcx
  __int64 v11; // rax
  DWORD LastError; // eax
  CMemoryLog *MemLogObject; // rax
  char v14; // al
  int v15; // edx
  int v16; // r8d
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-C8h] BYREF
  WCHAR *v18; // [rsp+68h] [rbp-B0h]
  __int64 v19; // [rsp+70h] [rbp-A8h]
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-98h] BYREF

  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 128;
  WMIADAPCmdLine = GetWMIADAPCmdLine(64);
  v18 = WMIADAPCmdLine;
  v19 = 0;
  if ( WMIADAPCmdLine )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids, lpCommandLine);
    }
    v9 = CreateProcessW(WMIADAPCmdLine, lpCommandLine, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation);
    if ( v9 )
    {
      CloseHandle(ProcessInformation.hThread);
      hProcess = ProcessInformation.hProcess;
      *((_QWORD *)a3 + 5) = ProcessInformation.hProcess;
      v11 = RegisterWaitForSingleObjectEx(hProcess, CMonitorEvents::EventCallBack, a3, *((unsigned int *)a2 + 141), 12);
      *((_QWORD *)a3 + 6) = v11;
      if ( v11 )
      {
LABEL_23:
        CWin32DefaultArena::WbemMemFree(WMIADAPCmdLine);
        return v9;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids, LastError);
      }
      CloseHandle(*((HANDLE *)a3 + 5));
      *((_QWORD *)a3 + 5) = 0;
    }
    else
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -1);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = GetLastError();
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, (_DWORD)WMIADAPCmdLine, v14);
      }
    }
    CStaticCritSec::Enter((struct CMonitorEvents *)((char *)a2 + 24));
    *((_DWORD *)a3 + 1) = 1;
    CStaticCritSec::Leave((struct CMonitorEvents *)((char *)a2 + 24));
    goto LABEL_23;
  }
  v7 = GetMemLogObject();
  CMemoryLog::Write(v7, -1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids);
  }
  CStaticCritSec::Enter((struct CMonitorEvents *)((char *)a2 + 24));
  *((_DWORD *)a3 + 1) = 1;
  CStaticCritSec::Leave((struct CMonitorEvents *)((char *)a2 + 24));
  return 0;
}

```

## disassembly

```asm
0x180004ccc  push    rbx
0x180004cce  push    rbp
0x180004ccf  push    rsi
0x180004cd0  push    r14
0x180004cd2  push    r15
0x180004cd4  sub     rsp, 0F0h
0x180004cdb  mov     rsi, r8
0x180004cde  mov     r14, rdx
0x180004ce1  mov     r15, rcx
0x180004ce4  xorps   xmm0, xmm0
0x180004ce7  xor     eax, eax
0x180004ce9  movups  xmmword ptr [rsp+118h+ProcessInformation.hProcess], xmm0
0x180004cee  mov     qword ptr [rsp+118h+ProcessInformation.dwProcessId], rax
0x180004cf3  lea     ebx, [rax+68h]
0x180004cf6  mov     r8d, ebx; Size
0x180004cf9  xor     edx, edx; Val
0x180004cfb  lea     rcx, [rsp+118h+StartupInfo]; void *
0x180004d03  call    memset_0
0x180004d08  mov     [rsp+118h+StartupInfo.cb], ebx
0x180004d0f  mov     [rsp+118h+StartupInfo.dwFlags], 80h
0x180004d1a  lea     ecx, [rbx-28h]
0x180004d1d  call    cs:__imp_?GetWMIADAPCmdLine@@YAPEAGH@Z; GetWMIADAPCmdLine(int)
0x180004d23  mov     rbp, rax
0x180004d26  mov     [rsp+118h+var_B0], rax
0x180004d2b  mov     [rsp+118h+var_A8], 0
0x180004d34  test    rax, rax
0x180004d37  jnz     short loc_180004DA0
0x180004d39  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180004d3f  or      edx, 0FFFFFFFFh
0x180004d42  mov     rcx, rax
0x180004d45  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180004d4b  lea     rbx, WPP_GLOBAL_Control
0x180004d52  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d59  cmp     rcx, rbx
0x180004d5c  jz      short loc_180004D7D
0x180004d5e  test    byte ptr [rcx+1Ch], 1
0x180004d62  jz      short loc_180004D7D
0x180004d64  cmp     byte ptr [rcx+19h], 2
0x180004d68  jb      short loc_180004D7D
0x180004d6a  lea     edx, [rbp+10h]
0x180004d6d  lea     r8, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids
0x180004d74  mov     rcx, [rcx+10h]
0x180004d78  call    WPP_SF_
0x180004d7d  lea     rcx, [r14+18h]
0x180004d81  call    cs:__imp_?Enter@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Enter(void)
0x180004d87  mov     dword ptr [rsi+4], 1
0x180004d8e  lea     rcx, [r14+18h]
0x180004d92  call    cs:__imp_?Leave@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Leave(void)
0x180004d98  nop
0x180004d99  xor     eax, eax
0x180004d9b  jmp     loc_180004F2D
0x180004da0  lea     rbx, WPP_GLOBAL_Control
0x180004da7  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dae  cmp     rcx, rbx
0x180004db1  jz      short loc_180004DD7
0x180004db3  test    byte ptr [rcx+1Ch], 1
0x180004db7  jz      short loc_180004DD7
0x180004db9  cmp     byte ptr [rcx+19h], 5
0x180004dbd  jb      short loc_180004DD7
0x180004dbf  mov     edx, 11h
0x180004dc4  mov     r9, r15
0x180004dc7  lea     r8, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids
0x180004dce  mov     rcx, [rcx+10h]
0x180004dd2  call    WPP_SF_S
0x180004dd7  lea     rax, [rsp+118h+ProcessInformation]
0x180004ddc  mov     [rsp+118h+lpProcessInformation], rax; lpProcessInformation
0x180004de1  lea     rax, [rsp+118h+StartupInfo]
0x180004de9  mov     [rsp+118h+lpStartupInfo], rax; lpStartupInfo
0x180004dee  mov     [rsp+118h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180004df7  mov     [rsp+118h+lpEnvironment], 0; lpEnvironment
0x180004e00  mov     [rsp+118h+dwCreationFlags], 8000000h; dwCreationFlags
0x180004e08  mov     [rsp+118h+bInheritHandles], 0; bInheritHandles
0x180004e10  xor     r9d, r9d; lpThreadAttributes
0x180004e13  xor     r8d, r8d; lpProcessAttributes
0x180004e16  mov     rdx, r15; lpCommandLine
0x180004e19  mov     rcx, rbp; lpApplicationName
0x180004e1c  call    cs:__imp_CreateProcessW
0x180004e22  mov     r15d, eax
0x180004e25  test    eax, eax
0x180004e27  jz      loc_180004EBE
0x180004e2d  mov     rcx, [rsp+118h+ProcessInformation.hThread]; hObject
0x180004e32  call    cs:__imp_CloseHandle
0x180004e38  mov     rcx, [rsp+118h+ProcessInformation.hProcess]
0x180004e3d  mov     [rsi+28h], rcx
0x180004e41  mov     [rsp+118h+bInheritHandles], 0Ch
0x180004e49  mov     r9d, [r14+234h]
0x180004e50  mov     r8, rsi
0x180004e53  lea     rdx, ?EventCallBack@CMonitorEvents@@SAXPEAXE@Z; CMonitorEvents::EventCallBack(void *,uchar)
0x180004e5a  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180004e60  mov     [rsi+30h], rax
0x180004e64  test    rax, rax
0x180004e67  jnz     loc_180004F21
0x180004e6d  mov     rax, cs:WPP_GLOBAL_Control
0x180004e74  cmp     rax, rbx
0x180004e77  jz      short loc_180004EAA
0x180004e79  test    byte ptr [rax+1Ch], 1
0x180004e7d  jz      short loc_180004EAA
0x180004e7f  cmp     byte ptr [rax+19h], 5
0x180004e83  jb      short loc_180004EAA
0x180004e85  call    cs:__imp_GetLastError
0x180004e8b  mov     edx, 12h
0x180004e90  mov     r9d, eax
0x180004e93  lea     r8, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids
0x180004e9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ea1  mov     rcx, [rcx+10h]
0x180004ea5  call    WPP_SF_d
0x180004eaa  mov     rcx, [rsi+28h]; hObject
0x180004eae  call    cs:__imp_CloseHandle
0x180004eb4  mov     qword ptr [rsi+28h], 0
0x180004ebc  jmp     short loc_180004F05
0x180004ebe  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180004ec4  or      edx, 0FFFFFFFFh
0x180004ec7  mov     rcx, rax
0x180004eca  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180004ed0  mov     rax, cs:WPP_GLOBAL_Control
0x180004ed7  cmp     rax, rbx
0x180004eda  jz      short loc_180004F05
0x180004edc  test    byte ptr [rax+1Ch], 1
0x180004ee0  jz      short loc_180004F05
0x180004ee2  cmp     byte ptr [rax+19h], 2
0x180004ee6  jb      short loc_180004F05
0x180004ee8  call    cs:__imp_GetLastError
0x180004eee  mov     [rsp+118h+bInheritHandles], eax
0x180004ef2  mov     r9, rbp
0x180004ef5  mov     rcx, cs:WPP_GLOBAL_Control
0x180004efc  mov     rcx, [rcx+10h]
0x180004f00  call    WPP_SF_Sd
0x180004f05  lea     rcx, [r14+18h]
0x180004f09  call    cs:__imp_?Enter@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Enter(void)
0x180004f0f  mov     dword ptr [rsi+4], 1
0x180004f16  lea     rcx, [r14+18h]
0x180004f1a  call    cs:__imp_?Leave@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Leave(void)
0x180004f20  nop
0x180004f21  mov     rcx, rbp
0x180004f24  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180004f2a  mov     eax, r15d
0x180004f2d  add     rsp, 0F0h
0x180004f34  pop     r15
0x180004f36  pop     r14
0x180004f38  pop     rsi
0x180004f39  pop     rbp
0x180004f3a  pop     rbx
0x180004f3b  retn
```
