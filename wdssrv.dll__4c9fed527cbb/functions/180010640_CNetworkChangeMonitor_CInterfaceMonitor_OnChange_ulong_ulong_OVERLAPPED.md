# CNetworkChangeMonitor<CInterfaceMonitor>::_OnChange(ulong,ulong,_OVERLAPPED *)

- ea: `0x180010640`
- end: `0x18001077f`
- name: `?_OnChange@?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@CAXKKPEAU_OVERLAPPED@@@Z`
- size: `319`
- prototype: `void __stdcall(DWORD dwErrorCode, DWORD dwNumberOfBytesTransfered, LPOVERLAPPED lpOverlapped)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003944`
- `0x180008158`
- `0x18001038c`
- `0x18001040c`
- `0x180010640`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800106c5`
- `KERNEL32!LeaveCriticalSection` at `0x180010732`
- `KERNEL32!LeaveCriticalSection` at `0x1800106c5`
- `KERNEL32!LeaveCriticalSection` at `0x180010732`
- `KERNEL32!EnterCriticalSection` at `0x180010656`
- `KERNEL32!EnterCriticalSection` at `0x180010656`
- `KERNEL32!SetEvent` at `0x18001070b`
- `KERNEL32!SetEvent` at `0x18001070b`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180010762`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180010762`
- `WdsServerCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x1800106e8`
- `WdsServerCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x1800106e8`
- `WdsServerCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18001071a`
- `WdsServerCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18001071a`

## pseudocode

```c
void __fastcall CNetworkChangeMonitor<CInterfaceMonitor>::_OnChange(
        DWORD dwErrorCode,
        DWORD dwNumberOfBytesTransfered,
        LPOVERLAPPED lpOverlapped)
{
  ULONG_PTR Internal; // rbx
  int v4; // edi
  unsigned int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // eax
  __int64 v8; // rdx
  int v9; // esi

  Internal = lpOverlapped[1].Internal;
  EnterCriticalSection((LPCRITICAL_SECTION)Internal);
  v4 = 1;
  if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(Internal + 48), 0) )
  {
    v5 = CNetworkChangeMonitor<CInterfaceMonitor>::PostChangeNotification((LPCRITICAL_SECTION)Internal);
    if ( !(unsigned int)ElValidateWin32(v5, v6, "base\\Eco\\WDS\\wdslib\\net\\NetChgMon.h", 375) )
    {
      if ( *(_DWORD *)(Internal + 64) )
      {
        v7 = CTimer<CNetworkChangeMonitor<CInterfaceMonitor>>::Change(Internal + 72);
        if ( (unsigned int)ElValidateWin32(v7, v8, "base\\Eco\\WDS\\wdslib\\net\\NetChgMon.h", 384) )
          goto LABEL_9;
        v9 = 0;
      }
      else
      {
        v9 = 1;
      }
      v4 = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)Internal);
      if ( v9 )
        CInterfaceMonitor::OnNetworkChange(*(LPCRITICAL_SECTION *)(Internal + 40));
    }
  }
LABEL_9:
  CMRSWLock::ReaderLock((CMRSWLock *)(Internal + 192));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(Internal + 176), 0xFFFFFFFF) == 1 )
    SetEvent(*(HANDLE *)(Internal + 184));
  CMRSWLock::ReaderRelease((CMRSWLock *)(Internal + 192));
  if ( v4 )
    LeaveCriticalSection((LPCRITICAL_SECTION)Internal);
}

```

## disassembly

```asm
0x180010640  mov     [rsp+arg_0], rbx
0x180010645  mov     [rsp+arg_8], rsi
0x18001064a  push    rdi
0x18001064b  sub     rsp, 30h
0x18001064f  mov     rbx, [r8+20h]
0x180010653  mov     rcx, rbx; lpCriticalSection
0x180010656  call    cs:__imp_EnterCriticalSection
0x18001065d  nop     dword ptr [rax+rax+00h]
0x180010662  xor     eax, eax
0x180010664  mov     edi, 1
0x180010669  lock xadd [rbx+30h], eax
0x18001066e  test    eax, eax
0x180010670  jnz     short loc_1800106DE
0x180010672  mov     rcx, rbx; lpCriticalSection
0x180010675  call    ?PostChangeNotification@?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@AEAAKXZ; CNetworkChangeMonitor<CInterfaceMonitor>::PostChangeNotification(void)
0x18001067a  mov     r9d, 177h
0x180010680  lea     r8, aBaseEcoWdsWdsl_0; "base\\Eco\\WDS\\wdslib\\net\\NetChgMon."...
0x180010687  mov     ecx, eax
0x180010689  call    ElValidateWin32
0x18001068e  test    eax, eax
0x180010690  jnz     short loc_1800106DE
0x180010692  mov     edx, [rbx+40h]
0x180010695  test    edx, edx
0x180010697  jz      short loc_1800106BE
0x180010699  lea     rcx, [rbx+48h]
0x18001069d  call    ?Change@?$CTimer@V?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@@@QEAAKKK@Z; CTimer<CNetworkChangeMonitor<CInterfaceMonitor>>::Change(ulong,ulong)
0x1800106a2  mov     r9d, 180h
0x1800106a8  lea     r8, aBaseEcoWdsWdsl_0; "base\\Eco\\WDS\\wdslib\\net\\NetChgMon."...
0x1800106af  mov     ecx, eax
0x1800106b1  call    ElValidateWin32
0x1800106b6  test    eax, eax
0x1800106b8  jnz     short loc_1800106DE
0x1800106ba  xor     esi, esi
0x1800106bc  jmp     short loc_1800106C0
0x1800106be  mov     esi, edi
0x1800106c0  mov     rcx, rbx; lpCriticalSection
0x1800106c3  xor     edi, edi
0x1800106c5  call    cs:__imp_LeaveCriticalSection
0x1800106cc  nop     dword ptr [rax+rax+00h]
0x1800106d1  test    esi, esi
0x1800106d3  jz      short loc_1800106DE
0x1800106d5  mov     rcx, [rbx+28h]; lpCriticalSection
0x1800106d9  call    ?OnNetworkChange@CInterfaceMonitor@@QEAAXXZ; CInterfaceMonitor::OnNetworkChange(void)
0x1800106de  lea     rsi, [rbx+0C0h]
0x1800106e5  mov     rcx, rsi
0x1800106e8  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x1800106ef  nop     dword ptr [rax+rax+00h]
0x1800106f4  or      eax, 0FFFFFFFFh
0x1800106f7  lock xadd [rbx+0B0h], eax
0x1800106ff  cmp     eax, 1
0x180010702  jnz     short loc_180010717
0x180010704  mov     rcx, [rbx+0B8h]; hEvent
0x18001070b  call    cs:__imp_SetEvent
0x180010712  nop     dword ptr [rax+rax+00h]
0x180010717  mov     rcx, rsi
0x18001071a  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180010721  nop     dword ptr [rax+rax+00h]
0x180010726  test    edi, edi
0x180010728  jz      short loc_18001076E
0x18001072a  add     edi, 0FFFFFFFFh
0x18001072d  jnz     short loc_180010740
0x18001072f  mov     rcx, rbx; lpCriticalSection
0x180010732  call    cs:__imp_LeaveCriticalSection
0x180010739  nop     dword ptr [rax+rax+00h]
0x18001073e  jmp     short loc_18001076E
0x180010740  test    edi, edi
0x180010742  jz      short loc_18001076E
0x180010744  and     [rsp+38h+var_18], 0
0x180010749  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x180010750  mov     r9d, 1
0x180010756  lea     rcx, aOnecoreInterna; "onecore\\internal\\base\\inc\\private\\"...
0x18001075d  mov     edx, 16Bh
0x180010762  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180010769  nop     dword ptr [rax+rax+00h]
0x18001076e  mov     rbx, [rsp+38h+arg_0]
0x180010773  mov     rsi, [rsp+38h+arg_8]
0x180010778  add     rsp, 30h
0x18001077c  pop     rdi
0x18001077d  retn
```
