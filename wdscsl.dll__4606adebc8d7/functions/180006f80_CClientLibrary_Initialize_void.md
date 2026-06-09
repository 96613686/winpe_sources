# CClientLibrary::Initialize(void)

- ea: `0x180006f80`
- end: `0x180007264`
- name: `?Initialize@CClientLibrary@@QEAAKXZ`
- size: `740`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d070`

## callees

- `0x180004d4c`
- `0x180006f80`
- `0x18000bd5c`
- `0x18000d6d2`
- `0x18000d700`
- `0x18000e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006fc4`
- `KERNEL32!EnterCriticalSection` at `0x180007133`
- `KERNEL32!EnterCriticalSection` at `0x180006fc4`
- `KERNEL32!EnterCriticalSection` at `0x180007133`
- `KERNEL32!GetModuleHandleExW` at `0x18000708b`
- `KERNEL32!GetModuleHandleExW` at `0x18000708b`
- `KERNEL32!LeaveCriticalSection` at `0x180007182`
- `KERNEL32!LeaveCriticalSection` at `0x180007220`
- `KERNEL32!LeaveCriticalSection` at `0x180007182`
- `KERNEL32!LeaveCriticalSection` at `0x180007220`
- `KERNEL32!GetLastError` at `0x1800070bc`
- `KERNEL32!GetLastError` at `0x1800070bc`
- `KERNEL32!GetProcAddress` at `0x1800070ab`
- `KERNEL32!GetProcAddress` at `0x1800070e5`
- `KERNEL32!GetProcAddress` at `0x180007101`
- `KERNEL32!GetProcAddress` at `0x1800070ab`
- `KERNEL32!GetProcAddress` at `0x1800070e5`
- `KERNEL32!GetProcAddress` at `0x180007101`
- `KERNEL32!FreeLibrary` at `0x180007211`
- `KERNEL32!FreeLibrary` at `0x180007211`
- `WS2_32!__imp_WSAGetLastError` at `0x180007056`
- `WS2_32!__imp_WSAGetLastError` at `0x180007056`
- `WS2_32!__imp_WSAStartup` at `0x180007046`
- `WS2_32!__imp_WSAStartup` at `0x180007046`
- `WdsCommonLib!?Initialize@CTrace@@QEAAKPEBGH@Z` at `0x180007011`
- `WdsCommonLib!?Initialize@CTrace@@QEAAKPEBGH@Z` at `0x180007011`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180007165`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x1800071e3`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180007165`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x1800071e3`

## string_xrefs

- `0x180007082`: `wdssrv.dll`

## pseudocode

```c
__int64 __fastcall CClientLibrary::Initialize(LPCRITICAL_SECTION lpCriticalSection)
{
  __int64 v2; // rsi
  __int64 v3; // rdx
  DWORD Error; // eax
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rcx
  unsigned int (*ProcAddress)(void); // rax
  FARPROC v9; // rax
  HMODULE v10; // rcx
  FARPROC v11; // rax
  bool v12; // zf
  __int64 v13; // rdx
  __int64 v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // rdx
  HMODULE phModule; // [rsp+30h] [rbp-1C8h] BYREF
  WSAData WSAData; // [rsp+40h] [rbp-1B8h] BYREF

  LODWORD(v2) = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  phModule = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&lpCriticalSection[1], 0) > 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&lpCriticalSection[1]);
    goto LABEL_23;
  }
  g_ErrLibTraceFunction = WdsClientTrace;
  g_ErrLibTraceFunctionEx = WdsClientTraceEx;
  v2 = CTrace::Initialize((CTrace *)g_WdsCslTrace, L"WDSCSL", 0);
  if ( !(unsigned int)ElValidateWin32(v2, v3, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 161) )
  {
    if ( WSAStartup(2u, &WSAData) )
    {
      Error = WSAGetLastError();
      v6 = 169;
LABEL_6:
      v7 = Error;
LABEL_7:
      LODWORD(v2) = ElValidateWin32(v7, v5, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", v6);
      goto LABEL_19;
    }
    lpCriticalSection[1].LockCount = 0;
    if ( GetModuleHandleExW(0, L"wdssrv.dll", &phModule) )
    {
      ProcAddress = (unsigned int (*)(void))GetProcAddress(phModule, "WdsIsServerMode");
      if ( !ProcAddress )
      {
        Error = GetLastError();
        v6 = 193;
        goto LABEL_6;
      }
      if ( ProcAddress() )
      {
        v9 = GetProcAddress(phModule, "WdsPacketAllocate");
        v10 = phModule;
        lpCriticalSection[1].LockSemaphore = v9;
        v11 = GetProcAddress(v10, "WdsPacketFree");
        v12 = lpCriticalSection[1].LockSemaphore == 0;
        lpCriticalSection[1].SpinCount = (ULONG_PTR)v11;
        if ( v12 || !v11 )
        {
          v6 = 211;
          v7 = 127;
          goto LABEL_7;
        }
        lpCriticalSection[1].LockCount = 1;
      }
    }
    EnterCriticalSection(&stru_180015920);
    if ( dword_180015948 )
      WdsAssert("base\\eco\\wds\\wdscsl\\client\\controllib.cpp", 0x49u, "!m_uInitDone", 1, 0);
    dword_180015948 = 1;
    LeaveCriticalSection(&stru_180015920);
    LODWORD(v2) = ElValidateWin32(0, v13, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 222);
    if ( !(unsigned int)ElValidateWin32((unsigned int)v2, v14, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 223) )
    {
      HIDWORD(lpCriticalSection[1].DebugInfo) = 1;
      _InterlockedIncrement((volatile signed __int32 *)&lpCriticalSection[1]);
    }
  }
LABEL_19:
  if ( (_DWORD)v2 )
  {
    if ( LODWORD(lpCriticalSection[1].DebugInfo) )
      WdsAssert("base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 0xF1u, "m_uInitCount == 0", 1, 0);
    v15 = CClientLibrary::CleanupResources(lpCriticalSection);
    ElValidateWin32(v15, v16, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 242);
  }
LABEL_23:
  if ( phModule )
    FreeLibrary(phModule);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180006f80  mov     [rsp+arg_8], rbx
0x180006f85  mov     [rsp+arg_10], rsi
0x180006f8a  push    r14
0x180006f8c  sub     rsp, 1F0h
0x180006f93  mov     rax, cs:__security_cookie
0x180006f9a  xor     rax, rsp
0x180006f9d  mov     [rsp+1F8h+var_18], rax
0x180006fa5  mov     rbx, rcx
0x180006fa8  xor     edx, edx; Val
0x180006faa  lea     rcx, [rsp+1F8h+WSAData]; void *
0x180006faf  mov     r8d, 198h; Size
0x180006fb5  xor     esi, esi
0x180006fb7  call    memset_0
0x180006fbc  and     [rsp+1F8h+phModule], rsi
0x180006fc1  mov     rcx, rbx; lpCriticalSection
0x180006fc4  call    cs:__imp_EnterCriticalSection
0x180006fcb  nop     dword ptr [rax+rax+00h]
0x180006fd0  xor     eax, eax
0x180006fd2  lock xadd [rbx+28h], eax
0x180006fd7  test    eax, eax
0x180006fd9  jle     short loc_180006FE4
0x180006fdb  lock inc dword ptr [rbx+28h]
0x180006fdf  jmp     loc_180007207
0x180006fe4  lea     rax, ?WdsClientTrace@@YAXPEBGZZ; WdsClientTrace(ushort const *,...)
0x180006feb  mov     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, rax; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180006ff2  lea     rax, ?WdsClientTraceEx@@YAXKPEBGZZ; WdsClientTraceEx(ulong,ushort const *,...)
0x180006ff9  mov     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rax; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007000  xor     r8d, r8d
0x180007003  lea     rdx, aWdscsl; "WDSCSL"
0x18000700a  lea     rcx, ?g_WdsCslTrace@@3VCTrace@@A; CTrace g_WdsCslTrace
0x180007011  call    cs:__imp_?Initialize@CTrace@@QEAAKPEBGH@Z; CTrace::Initialize(ushort const *,int)
0x180007018  nop     dword ptr [rax+rax+00h]
0x18000701d  lea     r14, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180007024  mov     r9d, 0A1h
0x18000702a  mov     r8, r14
0x18000702d  mov     ecx, eax
0x18000702f  mov     esi, eax
0x180007031  call    ElValidateWin32
0x180007036  test    eax, eax
0x180007038  jnz     loc_1800071BF
0x18000703e  lea     ecx, [rax+2]; wVersionRequested
0x180007041  lea     rdx, [rsp+1F8h+WSAData]; lpWSAData
0x180007046  call    cs:__imp_WSAStartup
0x18000704d  nop     dword ptr [rax+rax+00h]
0x180007052  test    eax, eax
0x180007054  jz      short loc_180007079
0x180007056  call    cs:__imp_WSAGetLastError
0x18000705d  nop     dword ptr [rax+rax+00h]
0x180007062  mov     r9d, 0A9h
0x180007068  mov     ecx, eax
0x18000706a  mov     r8, r14
0x18000706d  call    ElValidateWin32
0x180007072  mov     esi, eax
0x180007074  jmp     loc_1800071BF
0x180007079  and     dword ptr [rbx+30h], 0
0x18000707d  lea     r8, [rsp+1F8h+phModule]; phModule
0x180007082  lea     rdx, aWdssrvDll; "wdssrv.dll"
0x180007089  xor     ecx, ecx; dwFlags
0x18000708b  call    cs:__imp_GetModuleHandleExW
0x180007092  nop     dword ptr [rax+rax+00h]
0x180007097  test    eax, eax
0x180007099  jz      loc_18000712C
0x18000709f  mov     rcx, [rsp+1F8h+phModule]; hModule
0x1800070a4  lea     rdx, ProcName; "WdsIsServerMode"
0x1800070ab  call    cs:__imp_GetProcAddress
0x1800070b2  nop     dword ptr [rax+rax+00h]
0x1800070b7  test    rax, rax
0x1800070ba  jnz     short loc_1800070D0
0x1800070bc  call    cs:__imp_GetLastError
0x1800070c3  nop     dword ptr [rax+rax+00h]
0x1800070c8  mov     r9d, 0C1h
0x1800070ce  jmp     short loc_180007068
0x1800070d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070d5  test    eax, eax
0x1800070d7  jz      short loc_18000712C
0x1800070d9  mov     rcx, [rsp+1F8h+phModule]; hModule
0x1800070de  lea     rdx, aWdspacketalloc; "WdsPacketAllocate"
0x1800070e5  call    cs:__imp_GetProcAddress
0x1800070ec  nop     dword ptr [rax+rax+00h]
0x1800070f1  mov     rcx, [rsp+1F8h+phModule]; hModule
0x1800070f6  lea     rdx, aWdspacketfree; "WdsPacketFree"
0x1800070fd  mov     [rbx+40h], rax
0x180007101  call    cs:__imp_GetProcAddress
0x180007108  nop     dword ptr [rax+rax+00h]
0x18000710d  cmp     qword ptr [rbx+40h], 0
0x180007112  mov     [rbx+48h], rax
0x180007116  jz      loc_180007255
0x18000711c  test    rax, rax
0x18000711f  jz      loc_180007255
0x180007125  mov     dword ptr [rbx+30h], 1
0x18000712c  lea     rcx, stru_180015920; lpCriticalSection
0x180007133  call    cs:__imp_EnterCriticalSection
0x18000713a  nop     dword ptr [rax+rax+00h]
0x18000713f  cmp     cs:dword_180015948, 0
0x180007146  jz      short loc_180007171
0x180007148  and     [rsp+1F8h+var_1D8], 0
0x18000714d  lea     r8, aMUinitdone_0; "!m_uInitDone"
0x180007154  mov     r9d, 1
0x18000715a  lea     rcx, aBaseEcoWdsWdsc; "base\\eco\\wds\\wdscsl\\client\\control"...
0x180007161  lea     edx, [r9+48h]
0x180007165  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000716c  nop     dword ptr [rax+rax+00h]
0x180007171  lea     rcx, stru_180015920; lpCriticalSection
0x180007178  mov     cs:dword_180015948, 1
0x180007182  call    cs:__imp_LeaveCriticalSection
0x180007189  nop     dword ptr [rax+rax+00h]
0x18000718e  mov     r9d, 0DEh
0x180007194  mov     r8, r14
0x180007197  xor     ecx, ecx
0x180007199  call    ElValidateWin32
0x18000719e  mov     r9d, 0DFh
0x1800071a4  mov     r8, r14
0x1800071a7  mov     ecx, eax
0x1800071a9  mov     esi, eax
0x1800071ab  call    ElValidateWin32
0x1800071b0  test    eax, eax
0x1800071b2  jnz     short loc_1800071BF
0x1800071b4  mov     dword ptr [rbx+2Ch], 1
0x1800071bb  lock inc dword ptr [rbx+28h]
0x1800071bf  test    esi, esi
0x1800071c1  jz      short loc_180007207
0x1800071c3  cmp     dword ptr [rbx+28h], 0
0x1800071c7  jz      short loc_1800071EF
0x1800071c9  and     [rsp+1F8h+var_1D8], 0
0x1800071ce  lea     r8, aMUinitcount0; "m_uInitCount == 0"
0x1800071d5  mov     r9d, 1
0x1800071db  mov     edx, 0F1h
0x1800071e0  mov     rcx, r14
0x1800071e3  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800071ea  nop     dword ptr [rax+rax+00h]
0x1800071ef  mov     rcx, rbx; lpCriticalSection
0x1800071f2  call    ?CleanupResources@CClientLibrary@@AEAAKXZ; CClientLibrary::CleanupResources(void)
0x1800071f7  mov     ecx, eax
0x1800071f9  mov     r9d, 0F2h
0x1800071ff  mov     r8, r14
0x180007202  call    ElValidateWin32
0x180007207  mov     rcx, [rsp+1F8h+phModule]; hLibModule
0x18000720c  test    rcx, rcx
0x18000720f  jz      short loc_18000721D
0x180007211  call    cs:__imp_FreeLibrary
0x180007218  nop     dword ptr [rax+rax+00h]
0x18000721d  mov     rcx, rbx; lpCriticalSection
0x180007220  call    cs:__imp_LeaveCriticalSection
0x180007227  nop     dword ptr [rax+rax+00h]
0x18000722c  mov     eax, esi
0x18000722e  mov     rcx, [rsp+1F8h+var_18]
0x180007236  xor     rcx, rsp; StackCookie
0x180007239  call    __security_check_cookie
0x18000723e  lea     r11, [rsp+1F8h+var_8]
0x180007246  mov     rbx, [r11+18h]
0x18000724a  mov     rsi, [r11+20h]
0x18000724e  mov     rsp, r11
0x180007251  pop     r14
0x180007253  retn
0x180007255  mov     r9d, 0D3h
0x18000725b  lea     ecx, [r9-54h]
0x18000725f  jmp     loc_18000706A
```
