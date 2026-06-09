# TLPCMgr::TClientInfo::QueueRequest(TLPCMgr::TLPCRequest *)

- ea: `0x14001200c`
- end: `0x1400120ef`
- name: `?QueueRequest@TClientInfo@TLPCMgr@@QEAAJPEAVTLPCRequest@2@@Z`
- size: `227`
- prototype: `int(TLPCMgr::TClientInfo *__hidden this, struct TLPCMgr::TLPCRequest *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400120f8`

## callees

- `0x1400085d8`
- `0x14000faa4`
- `0x14001200c`
- `0x1400140b8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140012062`
- `KERNEL32!GetCurrentThreadId` at `0x140012062`
- `KERNEL32!SetEvent` at `0x1400120c4`
- `KERNEL32!SetEvent` at `0x1400120c4`
- `KERNEL32!EnterCriticalSection` at `0x140012059`
- `KERNEL32!EnterCriticalSection` at `0x140012059`
- `KERNEL32!LeaveCriticalSection` at `0x1400120b6`
- `KERNEL32!LeaveCriticalSection` at `0x1400120b6`

## pseudocode

```c
__int64 __fastcall TLPCMgr::TClientInfo::QueueRequest(TLPCMgr::TClientInfo *this, struct TLPCMgr::TLPCRequest *a2)
{
  __int64 v4; // rbp
  int v5; // ebx

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl'::`2'::impl) )
  {
    if ( *((_DWORD *)this + 16) != 1431130180 )
    {
      SplWow64Telemetry::WriteDbgTraceError(
        "TLPCMgr::TClientInfo::QueueRequest",
        L"ClientInfo object is corrupted (invalid signature)!");
      return 2147549183LL;
    }
    if ( !*((_QWORD *)this + 13) )
    {
      SplWow64Telemetry::WriteDbgTraceError("TLPCMgr::TClientInfo::QueueRequest", L"m_pDispatcher is NULL!");
      return 2147549183LL;
    }
  }
  v4 = *((_QWORD *)this + 13);
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 128));
  ++*(_DWORD *)(v4 + 172);
  *(_DWORD *)(v4 + 168) = GetCurrentThreadId();
  if ( a2 )
  {
    if ( *((_QWORD *)a2 + 2) && *((_QWORD *)a2 + 3) )
      v5 = 0;
    else
      v5 = -2147467259;
    if ( v5 >= 0 )
      v5 = NCoreLibrary::TLink::Link(*(NCoreLibrary::TLink **)(v4 + 216), a2);
  }
  else
  {
    v5 = -2147024809;
  }
  if ( (*(_DWORD *)(v4 + 172))-- == 1 )
    *(_DWORD *)(v4 + 168) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 128));
  if ( v5 >= 0 )
    SetEvent(*(HANDLE *)(v4 + 120));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001200c  push    rbx
0x14001200e  push    rbp
0x14001200f  push    rsi
0x140012010  push    rdi
0x140012011  sub     rsp, 28h
0x140012015  mov     rsi, rdx
0x140012018  mov     rbx, rcx
0x14001201b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl(void)'::`2'::impl
0x140012022  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(void)
0x140012027  test    al, al
0x140012029  jz      short loc_14001204B
0x14001202b  cmp     dword ptr [rbx+40h], 554D5044h
0x140012032  jz      short loc_140012040
0x140012034  lea     rdx, aClientinfoObje; "ClientInfo object is corrupted (invalid"...
0x14001203b  jmp     loc_1400120D5
0x140012040  cmp     qword ptr [rbx+68h], 0
0x140012045  jz      loc_1400120CE
0x14001204b  mov     rbp, [rbx+68h]
0x14001204f  lea     rdi, [rbp+80h]
0x140012056  mov     rcx, rdi; lpCriticalSection
0x140012059  call    cs:__imp_EnterCriticalSection
0x14001205f  inc     dword ptr [rdi+2Ch]
0x140012062  call    cs:__imp_GetCurrentThreadId
0x140012068  mov     [rdi+28h], eax
0x14001206b  test    rsi, rsi
0x14001206e  jz      short loc_14001209E
0x140012070  cmp     qword ptr [rsi+10h], 0
0x140012075  jz      short loc_140012082
0x140012077  cmp     qword ptr [rsi+18h], 0
0x14001207c  jz      short loc_140012082
0x14001207e  xor     ebx, ebx
0x140012080  jmp     short loc_140012087
0x140012082  mov     ebx, 80004005h
0x140012087  test    ebx, ebx
0x140012089  js      short loc_1400120A3
0x14001208b  mov     rcx, [rbp+0D8h]; this
0x140012092  mov     rdx, rsi; struct NCoreLibrary::TLink *
0x140012095  call    ?Link@TLink@NCoreLibrary@@QEAAJPEAV12@@Z; NCoreLibrary::TLink::Link(NCoreLibrary::TLink *)
0x14001209a  mov     ebx, eax
0x14001209c  jmp     short loc_1400120A3
0x14001209e  mov     ebx, 80070057h
0x1400120a3  add     dword ptr [rdi+2Ch], 0FFFFFFFFh
0x1400120a7  mov     eax, [rdi+2Ch]
0x1400120aa  jnz     short loc_1400120B3
0x1400120ac  mov     dword ptr [rdi+28h], 0
0x1400120b3  mov     rcx, rdi; lpCriticalSection
0x1400120b6  call    cs:__imp_LeaveCriticalSection
0x1400120bc  test    ebx, ebx
0x1400120be  js      short loc_1400120CA
0x1400120c0  mov     rcx, [rbp+78h]; hEvent
0x1400120c4  call    cs:__imp_SetEvent
0x1400120ca  mov     eax, ebx
0x1400120cc  jmp     short loc_1400120E6
0x1400120ce  lea     rdx, aMPdispatcherIs; "m_pDispatcher is NULL!"
0x1400120d5  lea     rcx, aTlpcmgrTclient; "TLPCMgr::TClientInfo::QueueRequest"
0x1400120dc  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400120e1  mov     eax, 8000FFFFh
0x1400120e6  add     rsp, 28h
0x1400120ea  pop     rdi
0x1400120eb  pop     rsi
0x1400120ec  pop     rbp
0x1400120ed  pop     rbx
0x1400120ee  retn
```
