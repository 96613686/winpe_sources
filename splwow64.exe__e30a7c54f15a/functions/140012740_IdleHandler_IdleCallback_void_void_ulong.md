# IdleHandler::IdleCallback(void *,void *,ulong)

- ea: `0x140012740`
- end: `0x140012866`
- name: `?IdleCallback@IdleHandler@@SAXPEAX0K@Z`
- size: `294`
- prototype: `static void(void *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1400082e0`
- `0x1400086e0`
- `0x14000c2b4`
- `0x140012740`
- `0x14001286c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400127cc`
- `KERNEL32!GetCurrentThreadId` at `0x1400127cc`
- `KERNEL32!CloseHandle` at `0x14001282a`
- `KERNEL32!CloseHandle` at `0x14001282a`
- `KERNEL32!EnterCriticalSection` at `0x1400127c0`
- `KERNEL32!EnterCriticalSection` at `0x1400127c0`
- `KERNEL32!LeaveCriticalSection` at `0x140012850`
- `KERNEL32!LeaveCriticalSection` at `0x140012850`
- `KERNEL32!CreateThread` at `0x14001281c`
- `KERNEL32!CreateThread` at `0x14001281c`

## string_xrefs

- `0x1400127f1`: `TLoad64BitDllsMgr::StartMonitorSrvrLifeExpirationThread`

## pseudocode

```c
void __fastcall IdleHandler::IdleCallback(void *a1, void *a2, unsigned int a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  HANDLE Thread; // rax

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl) )
  {
    SplWow64Telemetry::WriteDbgTraceInfo(
      "IdleHandler::IdleCallback",
      L"RPC idle callback for group %p, IsGroupIdle=%u",
      a1,
      a3);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, a1, a3);
  }
  if ( dword_140021500 >= 0 )
  {
    EnterCriticalSection(&IdleHandler::m_idleLock);
    ++dword_1400214FC;
    dword_1400214F8 = GetCurrentThreadId();
    if ( a3 )
    {
      if ( (unsigned int)TLoad64BitDllsMgr::StillAlive((TLoad64BitDllsMgr *)a2, 0) )
      {
        SplWow64Telemetry::WriteDbgTraceInfo("TLoad64BitDllsMgr::StartMonitorSrvrLifeExpirationThread", L"Entered..");
        Thread = CreateThread(0, 0, TLoad64BitDllsMgr::MonitorSrvrLifeExpiration, a2, 0, 0);
        if ( Thread )
          CloseHandle(Thread);
      }
    }
    if ( !--dword_1400214FC )
      dword_1400214F8 = 0;
    LeaveCriticalSection(&IdleHandler::m_idleLock);
  }
}

```

## disassembly

```asm
0x140012740  mov     [rsp+arg_0], rbx
0x140012745  mov     [rsp+arg_8], rsi
0x14001274a  push    rdi
0x14001274b  sub     rsp, 30h
0x14001274f  mov     ebx, r8d
0x140012752  mov     rsi, rdx
0x140012755  mov     rdi, rcx
0x140012758  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x14001275f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x140012764  test    al, al
0x140012766  jz      short loc_140012783
0x140012768  mov     r9d, ebx
0x14001276b  lea     rdx, aRpcIdleCallbac; "RPC idle callback for group %p, IsGroup"...
0x140012772  mov     r8, rdi
0x140012775  lea     rcx, aIdlehandlerIdl; "IdleHandler::IdleCallback"
0x14001277c  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140012781  jmp     short loc_1400127AC
0x140012783  mov     rcx, cs:WPP_GLOBAL_Control
0x14001278a  lea     rax, WPP_GLOBAL_Control
0x140012791  cmp     rcx, rax
0x140012794  jz      short loc_1400127AC
0x140012796  test    byte ptr [rcx+1Ch], 2
0x14001279a  jz      short loc_1400127AC
0x14001279c  mov     rcx, [rcx+10h]
0x1400127a0  mov     r9, rdi
0x1400127a3  mov     [rsp+38h+dwCreationFlags], ebx
0x1400127a7  call    WPP_SF_qD
0x1400127ac  cmp     cs:dword_140021500, 0
0x1400127b3  jl      loc_140012856
0x1400127b9  lea     rcx, ?m_idleLock@IdleHandler@@0VTCriticalSection@NCoreLibrary@@A; lpCriticalSection
0x1400127c0  call    cs:__imp_EnterCriticalSection
0x1400127c6  inc     cs:dword_1400214FC
0x1400127cc  call    cs:__imp_GetCurrentThreadId
0x1400127d2  mov     cs:dword_1400214F8, eax
0x1400127d8  test    ebx, ebx
0x1400127da  jz      short loc_140012830
0x1400127dc  xor     edx, edx; unsigned __int64
0x1400127de  mov     rcx, rsi; this
0x1400127e1  call    ?StillAlive@TLoad64BitDllsMgr@@QEAAH_K@Z; TLoad64BitDllsMgr::StillAlive(unsigned __int64)
0x1400127e6  test    eax, eax
0x1400127e8  jz      short loc_140012830
0x1400127ea  lea     rdx, aEntered; "Entered.."
0x1400127f1  lea     rcx, aTload64bitdlls; "TLoad64BitDllsMgr::StartMonitorSrvrLife"...
0x1400127f8  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400127fd  mov     r9, rsi; lpParameter
0x140012800  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x140012809  lea     r8, ?MonitorSrvrLifeExpiration@TLoad64BitDllsMgr@@KAKPEAX@Z; lpStartAddress
0x140012810  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140012818  xor     edx, edx; dwStackSize
0x14001281a  xor     ecx, ecx; lpThreadAttributes
0x14001281c  call    cs:__imp_CreateThread
0x140012822  test    rax, rax
0x140012825  jz      short loc_140012830
0x140012827  mov     rcx, rax; hObject
0x14001282a  call    cs:__imp_CloseHandle
0x140012830  add     cs:dword_1400214FC, 0FFFFFFFFh
0x140012837  mov     eax, cs:dword_1400214FC
0x14001283d  jnz     short loc_140012849
0x14001283f  mov     cs:dword_1400214F8, 0
0x140012849  lea     rcx, ?m_idleLock@IdleHandler@@0VTCriticalSection@NCoreLibrary@@A; lpCriticalSection
0x140012850  call    cs:__imp_LeaveCriticalSection
0x140012856  mov     rbx, [rsp+38h+arg_0]
0x14001285b  mov     rsi, [rsp+38h+arg_8]
0x140012860  add     rsp, 30h
0x140012864  pop     rdi
0x140012865  retn
```
