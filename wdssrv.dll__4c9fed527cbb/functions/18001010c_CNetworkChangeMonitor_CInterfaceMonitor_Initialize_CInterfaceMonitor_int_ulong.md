# CNetworkChangeMonitor<CInterfaceMonitor>::Initialize(CInterfaceMonitor *,int,ulong)

- ea: `0x18001010c`
- end: `0x1800102bb`
- name: `?Initialize@?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@QEAAKPEAVCInterfaceMonitor@@HK@Z`
- size: `431`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013638`

## callees

- `0x180003944`
- `0x18001010c`
- `0x1800102c4`
- `0x18001040c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001015f`
- `KERNEL32!GetLastError` at `0x18001023d`
- `KERNEL32!GetLastError` at `0x18001015f`
- `KERNEL32!GetLastError` at `0x18001023d`
- `KERNEL32!LeaveCriticalSection` at `0x180010297`
- `KERNEL32!LeaveCriticalSection` at `0x180010297`
- `KERNEL32!EnterCriticalSection` at `0x180010129`
- `KERNEL32!EnterCriticalSection` at `0x180010129`
- `KERNEL32!CreateEventW` at `0x180010147`
- `KERNEL32!CreateEventW` at `0x180010147`
- `KERNEL32!BindIoCompletionCallback` at `0x18001022d`
- `KERNEL32!BindIoCompletionCallback` at `0x18001022d`
- `WS2_32!WSASocketW` at `0x1800101ea`
- `WS2_32!WSASocketW` at `0x1800101ea`
- `WS2_32!__imp_WSAGetLastError` at `0x180010200`
- `WS2_32!__imp_WSAGetLastError` at `0x180010200`
- `WdsServerCommonLib!?Initialize@CMRSWLock@@QEAAKK@Z` at `0x180010193`
- `WdsServerCommonLib!?Initialize@CMRSWLock@@QEAAKK@Z` at `0x180010193`

## pseudocode

```c
__int64 __fastcall CNetworkChangeMonitor<CInterfaceMonitor>::Initialize(
        LPCRITICAL_SECTION lpCriticalSection,
        struct _RTL_CRITICAL_SECTION_DEBUG *a2,
        int a3)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  void *v12; // rax
  DWORD Error; // eax
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rdx

  EnterCriticalSection(lpCriticalSection);
  LODWORD(lpCriticalSection[1].LockSemaphore) = 0;
  lpCriticalSection[1].DebugInfo = a2;
  EventW = CreateEventW(0, 0, 0, 0);
  lpCriticalSection[4].LockSemaphore = EventW;
  if ( EventW )
  {
    v10 = CMRSWLock::Initialize((CMRSWLock *)&lpCriticalSection[4].SpinCount, 0);
    ElValidateWin32(v10, v11, "onecore\\internal\\base\\inc\\private\\eco\\wds\\ChildCount.h", 217);
  }
  else
  {
    LastError = GetLastError();
    v10 = ElValidateWin32(LastError, v8, "onecore\\internal\\base\\inc\\private\\eco\\wds\\ChildCount.h", 213);
    if ( !v10 )
      v10 = 31;
  }
  if ( !(unsigned int)ElValidateWin32(v10, v9, "base\\Eco\\WDS\\wdslib\\net\\NetChgMon.h", 177) )
  {
    v12 = (void *)WSASocketW(a3, 0, 0, 0, 0, 1u);
    lpCriticalSection[1].OwningThread = v12;
    if ( v12 == (void *)-1LL )
    {
      Error = WSAGetLastError();
      v15 = 192;
LABEL_8:
      v10 = ElValidateWin32(Error, v14, "base\\Eco\\WDS\\wdslib\\net\\NetChgMon.h", v15);
      goto LABEL_13;
    }
    if ( !BindIoCompletionCallback(v12, CNetworkChangeMonitor<CInterfaceMonitor>::_OnChange, 0) )
    {
      Error = GetLastError();
      v15 = 201;
      goto LABEL_8;
    }
    lpCriticalSection[4].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)lpCriticalSection;
    v10 = CTimer<CNetworkChangeMonitor<CInterfaceMonitor>>::Initialize(&lpCriticalSection[1].SpinCount);
    if ( !(unsigned int)ElValidateWin32(v10, v16, "base\\Eco\\WDS\\wdslib\\net\\NetChgMon.h", 215) )
    {
      v10 = CNetworkChangeMonitor<CInterfaceMonitor>::PostChangeNotification(lpCriticalSection);
      ElValidateWin32(v10, v17, "base\\Eco\\WDS\\wdslib\\net\\NetChgMon.h", 222);
    }
  }
LABEL_13:
  LeaveCriticalSection(lpCriticalSection);
  return v10;
}

```

## disassembly

```asm
0x18001010c  mov     [rsp+arg_0], rbx
0x180010111  mov     [rsp+arg_8], rbp
0x180010116  mov     [rsp+arg_10], rsi
0x18001011b  push    rdi
0x18001011c  sub     rsp, 40h
0x180010120  mov     esi, r8d
0x180010123  mov     rbx, rdx
0x180010126  mov     rdi, rcx
0x180010129  call    cs:__imp_EnterCriticalSection
0x180010130  nop     dword ptr [rax+rax+00h]
0x180010135  and     dword ptr [rdi+40h], 0
0x180010139  xor     r9d, r9d; lpName
0x18001013c  xor     r8d, r8d; bInitialState
0x18001013f  mov     [rdi+28h], rbx
0x180010143  xor     edx, edx; bManualReset
0x180010145  xor     ecx, ecx; lpEventAttributes
0x180010147  call    cs:__imp_CreateEventW
0x18001014e  nop     dword ptr [rax+rax+00h]
0x180010153  mov     [rdi+0B8h], rax
0x18001015a  test    rax, rax
0x18001015d  jnz     short loc_18001018A
0x18001015f  call    cs:__imp_GetLastError
0x180010166  nop     dword ptr [rax+rax+00h]
0x18001016b  mov     r9d, 0D5h
0x180010171  lea     r8, aOnecoreInterna_1; "onecore\\internal\\base\\inc\\private\\"...
0x180010178  mov     ecx, eax
0x18001017a  call    ElValidateWin32
0x18001017f  mov     ebx, eax
0x180010181  test    eax, eax
0x180010183  jnz     short loc_1800101B5
0x180010185  lea     ebx, [rax+1Fh]
0x180010188  jmp     short loc_1800101B5
0x18001018a  lea     rcx, [rdi+0C0h]
0x180010191  xor     edx, edx
0x180010193  call    cs:__imp_?Initialize@CMRSWLock@@QEAAKK@Z; CMRSWLock::Initialize(ulong)
0x18001019a  nop     dword ptr [rax+rax+00h]
0x18001019f  mov     r9d, 0D9h
0x1800101a5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\base\\inc\\private\\"...
0x1800101ac  mov     ecx, eax
0x1800101ae  mov     ebx, eax
0x1800101b0  call    ElValidateWin32
0x1800101b5  lea     rbp, aBaseEcoWdsWdsl_0; "base\\Eco\\WDS\\wdslib\\net\\NetChgMon."...
0x1800101bc  mov     r9d, 0B1h
0x1800101c2  mov     r8, rbp
0x1800101c5  mov     ecx, ebx
0x1800101c7  call    ElValidateWin32
0x1800101cc  test    eax, eax
0x1800101ce  jnz     loc_180010294
0x1800101d4  mov     [rsp+48h+dwFlags], 1; dwFlags
0x1800101dc  xor     r9d, r9d; lpProtocolInfo
0x1800101df  and     [rsp+48h+var_28], eax
0x1800101e3  xor     r8d, r8d; protocol
0x1800101e6  xor     edx, edx; type
0x1800101e8  mov     ecx, esi; af
0x1800101ea  call    cs:__imp_WSASocketW
0x1800101f1  nop     dword ptr [rax+rax+00h]
0x1800101f6  mov     [rdi+38h], rax
0x1800101fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800101fe  jnz     short loc_180010220
0x180010200  call    cs:__imp_WSAGetLastError
0x180010207  nop     dword ptr [rax+rax+00h]
0x18001020c  mov     r9d, 0C0h
0x180010212  mov     ecx, eax
0x180010214  mov     r8, rbp
0x180010217  call    ElValidateWin32
0x18001021c  mov     ebx, eax
0x18001021e  jmp     short loc_180010294
0x180010220  xor     r8d, r8d; Flags
0x180010223  lea     rdx, ?_OnChange@?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@CAXKKPEAU_OVERLAPPED@@@Z; Function
0x18001022a  mov     rcx, rax; FileHandle
0x18001022d  call    cs:__imp_BindIoCompletionCallback
0x180010234  nop     dword ptr [rax+rax+00h]
0x180010239  test    eax, eax
0x18001023b  jnz     short loc_180010251
0x18001023d  call    cs:__imp_GetLastError
0x180010244  nop     dword ptr [rax+rax+00h]
0x180010249  mov     r9d, 0C9h
0x18001024f  jmp     short loc_180010212
0x180010251  lea     rcx, [rdi+48h]; Parameter
0x180010255  mov     [rdi+0A0h], rdi
0x18001025c  mov     rdx, rdi
0x18001025f  call    ?Initialize@?$CTimer@V?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@@@QEAAKPEAV?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@PEAXKK1K@Z; CTimer<CNetworkChangeMonitor<CInterfaceMonitor>>::Initialize(CNetworkChangeMonitor<CInterfaceMonitor> *,void *,ulong,ulong,void *,ulong)
0x180010264  mov     r9d, 0D7h
0x18001026a  mov     r8, rbp
0x18001026d  mov     ecx, eax
0x18001026f  mov     ebx, eax
0x180010271  call    ElValidateWin32
0x180010276  test    eax, eax
0x180010278  jnz     short loc_180010294
0x18001027a  mov     rcx, rdi; lpCriticalSection
0x18001027d  call    ?PostChangeNotification@?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@AEAAKXZ; CNetworkChangeMonitor<CInterfaceMonitor>::PostChangeNotification(void)
0x180010282  mov     r9d, 0DEh
0x180010288  mov     r8, rbp
0x18001028b  mov     ecx, eax
0x18001028d  mov     ebx, eax
0x18001028f  call    ElValidateWin32
0x180010294  mov     rcx, rdi; lpCriticalSection
0x180010297  call    cs:__imp_LeaveCriticalSection
0x18001029e  nop     dword ptr [rax+rax+00h]
0x1800102a3  mov     rbp, [rsp+48h+arg_8]
0x1800102a8  mov     eax, ebx
0x1800102aa  mov     rbx, [rsp+48h+arg_0]
0x1800102af  mov     rsi, [rsp+48h+arg_10]
0x1800102b4  add     rsp, 40h
0x1800102b8  pop     rdi
0x1800102b9  retn
```
