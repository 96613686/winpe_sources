# CProtocolExMgr::CProtocolExMgr(ISessionManager *,long *)

- ea: `0x18008abac`
- end: `0x18008ae4d`
- name: `??0CProtocolExMgr@@QEAA@PEAUISessionManager@@PEAJ@Z`
- size: `673`
- prototype: `CProtocolExMgr *__fastcall(CProtocolExMgr *__hidden this, struct ISessionManager *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180048510`

## callees

- `0x180009940`
- `0x1800139c0`
- `0x180027434`
- `0x180029754`
- `0x18003ed38`
- `0x180046f00`
- `0x18008abac`
- `0x1800ce010`

## import_xrefs

- `ntdll!RtlInitializeGenericTable` at `0x18008ac44`
- `ntdll!RtlInitializeGenericTable` at `0x18008ac44`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008ad63`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008ad63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ade8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ade8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008add0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008add0`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18008ad44`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18008ad44`

## string_xrefs

- `0x18008abce`: `CProtocolExMgr`
- `0x18008ae11`: `CProtocolExMgr::CProtocolExMgr`
- `0x18008ac92`: `ProtocolMgrListLock.Initialize failed: 0x%x in %s`
- `0x18008ae0a`: `CreateThread( staticNotificationWorker ) failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
CProtocolExMgr *__fastcall CProtocolExMgr::CProtocolExMgr(CProtocolExMgr *this, struct ISessionManager *a2, int *a3)
{
  int v6; // eax
  signed int v7; // ebx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int GlobalDispatcher; // eax
  int v12; // eax
  HANDLE v13; // rax
  signed int LastError; // eax
  DWORD ThreadId; // [rsp+80h] [rbp+18h] BYREF
  struct ITSEventDispatcher *v17; // [rsp+88h] [rbp+20h] BYREF

  CDefTSNotifySink::CDefTSNotifySink(this, "CProtocolExMgr");
  *(_QWORD *)this = &CProtocolExMgr::`vftable';
  SmartPtr<IRemoteTerminal>::SmartPtr<IRemoteTerminal>((char *)this + 1592, a2);
  *((_QWORD *)this + 200) = 0;
  *((_QWORD *)this + 201) = 0;
  *((_QWORD *)this + 202) = 0;
  *((_DWORD *)this + 430) = 0;
  RtlInitializeGenericTable(
    (PRTL_GENERIC_TABLE)this + 24,
    CListTree<IProtocolManager>::staticCompareEntry,
    CListTree<IProtocolManager>::staticAllocateEntry,
    CListTree<IListenerItem>::staticFreeEntry,
    (char *)this + 1728);
  *((_BYTE *)this + 1800) = 1;
  *((_DWORD *)this + 480) = 0;
  *((_QWORD *)this + 241) = 0;
  *((_QWORD *)this + 242) = 0;
  *((_QWORD *)this + 243) = 0;
  v17 = 0;
  v6 = CResource::Initialize((CProtocolExMgr *)((char *)this + 1624));
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = CResource::Initialize((CProtocolExMgr *)((char *)this + 1824));
    v7 = v8;
    if ( v8 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 199) + 24LL))(
             *((_QWORD *)this + 199),
             (char *)this + 1600);
      v7 = v9;
      if ( v9 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 200) + 32LL))(
                *((_QWORD *)this + 200),
                (char *)this + 1608);
        v7 = v10;
        if ( v10 >= 0 )
        {
          GlobalDispatcher = CHelper::GetGlobalDispatcher(&v17);
          v7 = GlobalDispatcher;
          if ( GlobalDispatcher >= 0 )
          {
            *((_QWORD *)this + 227) = (char *)this + 1808;
            *((_QWORD *)this + 226) = (char *)this + 1808;
            *((_QWORD *)this + 241) = CreateSemaphoreW(0, 0, 100, 0);
            *((_QWORD *)this + 242) = CreateEventW(0, 1, 0, 0);
            v12 = (*(__int64 (__fastcall **)(struct ITSEventDispatcher *, CProtocolExMgr *, char *))(*(_QWORD *)v17 + 48LL))(
                    v17,
                    this,
                    (char *)this + 1616);
            v7 = v12;
            if ( v12 >= 0 )
            {
              ThreadId = 0;
              v13 = CreateThread(0, 0, CProtocolExMgr::staticNotificationWorker, this, 0, &ThreadId);
              *((_QWORD *)this + 243) = v13;
              if ( !v13 )
              {
                LastError = GetLastError();
                v7 = LastError;
                if ( LastError > 0 )
                  v7 = (unsigned __int16)LastError | 0x80070000;
                if ( v7 < 0 )
                  _DbgPrintMessage(
                    8,
                    "CreateThread( staticNotificationWorker ) failed: 0x%x in %s",
                    (unsigned int)v7,
                    "CProtocolExMgr::CProtocolExMgr");
              }
            }
            else
            {
              _DbgPrintMessage(8, "Advise failed: 0x%x in %s", (unsigned int)v12, "CProtocolExMgr::CProtocolExMgr");
            }
          }
          else
          {
            _DbgPrintMessage(
              8,
              "GetGlobalDispatcher failed: 0x%x in %s",
              (unsigned int)GlobalDispatcher,
              "CProtocolExMgr::CProtocolExMgr");
          }
        }
        else
        {
          _DbgPrintMessage(
            8,
            "GetInstanceOfEnum failed: 0x%x in %s",
            (unsigned int)v10,
            "CProtocolExMgr::CProtocolExMgr");
        }
      }
      else
      {
        _DbgPrintMessage(8, "GetSessionList failed: 0x%x in %s", (unsigned int)v9, "CProtocolExMgr::CProtocolExMgr");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "NotificationWorkItemsLock.Initialize failed: 0x%x in %s",
        (unsigned int)v8,
        "CProtocolExMgr::CProtocolExMgr");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "ProtocolMgrListLock.Initialize failed: 0x%x in %s",
      (unsigned int)v6,
      "CProtocolExMgr::CProtocolExMgr");
  }
  *a3 = v7;
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v17);
  return this;
}

```

## disassembly

```asm
0x18008abac  mov     [rsp+arg_8], rbx
0x18008abb1  mov     [rsp+arg_0], rcx
0x18008abb6  push    rbp
0x18008abb7  push    rsi
0x18008abb8  push    rdi
0x18008abb9  push    r12
0x18008abbb  push    r13
0x18008abbd  push    r14
0x18008abbf  push    r15
0x18008abc1  sub     rsp, 30h
0x18008abc5  mov     r12, r8
0x18008abc8  mov     rbx, rdx
0x18008abcb  mov     rdi, rcx
0x18008abce  lea     rdx, aCprotocolexmgr_9; "CProtocolExMgr"
0x18008abd5  call    ??0CDefTSNotifySink@@QEAA@PEBD@Z; CDefTSNotifySink::CDefTSNotifySink(char const *)
0x18008abda  nop
0x18008abdb  lea     rax, ??_7CProtocolExMgr@@6B@; const CProtocolExMgr::`vftable'
0x18008abe2  mov     [rdi], rax
0x18008abe5  lea     r14, [rdi+638h]
0x18008abec  mov     rdx, rbx
0x18008abef  mov     rcx, r14
0x18008abf2  call    ??0?$SmartPtr@VIRemoteTerminal@@@@QEAA@PEAVIRemoteTerminal@@@Z; SmartPtr<IRemoteTerminal>::SmartPtr<IRemoteTerminal>(IRemoteTerminal *)
0x18008abf7  nop
0x18008abf8  lea     rsi, [rdi+640h]
0x18008abff  xor     eax, eax
0x18008ac01  mov     [rsi], rax
0x18008ac04  lea     r15, [rdi+648h]
0x18008ac0b  mov     [r15], rax
0x18008ac0e  lea     r13, [rdi+650h]
0x18008ac15  mov     [r13+0], rax
0x18008ac19  lea     rbx, [rdi+658h]
0x18008ac20  mov     [rbx+60h], eax
0x18008ac23  lea     rcx, [rdi+6C0h]; Table
0x18008ac2a  mov     [rsp+68h+TableContext], rcx; TableContext
0x18008ac2f  lea     r9, ?staticFreeEntry@?$CListTree@VIListenerItem@@@@KAXPEAU_RTL_GENERIC_TABLE@@PEAX@Z; FreeRoutine
0x18008ac36  lea     r8, ?staticAllocateEntry@?$CListTree@VIProtocolManager@@@@KAPEAXPEAU_RTL_GENERIC_TABLE@@K@Z; AllocateRoutine
0x18008ac3d  lea     rdx, ?staticCompareEntry@?$CListTree@VIProtocolManager@@@@KA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_GENERIC_TABLE@@PEAX1@Z; CompareRoutine
0x18008ac44  call    cs:__imp_RtlInitializeGenericTable
0x18008ac4b  nop     dword ptr [rax+rax+00h]
0x18008ac50  nop
0x18008ac51  mov     byte ptr [rdi+708h], 1
0x18008ac58  lea     rbp, [rdi+720h]
0x18008ac5f  xor     eax, eax
0x18008ac61  mov     [rbp+60h], eax
0x18008ac64  mov     [rdi+788h], rax
0x18008ac6b  mov     [rdi+790h], rax
0x18008ac72  mov     [rdi+798h], rax
0x18008ac79  mov     [rsp+68h+arg_18], rax
0x18008ac81  mov     rcx, rbx; this
0x18008ac84  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x18008ac89  mov     ebx, eax
0x18008ac8b  test    eax, eax
0x18008ac8d  jns     short loc_18008AC9E
0x18008ac8f  mov     r8d, eax
0x18008ac92  lea     rdx, aProtocolmgrlis; "ProtocolMgrListLock.Initialize failed: "...
0x18008ac99  jmp     loc_18008AE11
0x18008ac9e  mov     rcx, rbp; this
0x18008aca1  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x18008aca6  mov     ebx, eax
0x18008aca8  test    eax, eax
0x18008acaa  jns     short loc_18008ACBB
0x18008acac  mov     r8d, eax
0x18008acaf  lea     rdx, aNotificationwo; "NotificationWorkItemsLock.Initialize fa"...
0x18008acb6  jmp     loc_18008AE11
0x18008acbb  mov     rcx, [r14]
0x18008acbe  mov     rax, [rcx]
0x18008acc1  mov     rdx, rsi
0x18008acc4  mov     rax, [rax+18h]
0x18008acc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008accd  mov     ebx, eax
0x18008accf  test    eax, eax
0x18008acd1  jns     short loc_18008ACE2
0x18008acd3  mov     r8d, eax
0x18008acd6  lea     rdx, aGetsessionlist_0; "GetSessionList failed: 0x%x in %s"
0x18008acdd  jmp     loc_18008AE11
0x18008ace2  mov     rcx, [rsi]
0x18008ace5  mov     rax, [rcx]
0x18008ace8  mov     rdx, r15
0x18008aceb  mov     rax, [rax+20h]
0x18008acef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008acf4  mov     ebx, eax
0x18008acf6  test    eax, eax
0x18008acf8  jns     short loc_18008AD09
0x18008acfa  mov     r8d, eax
0x18008acfd  lea     rdx, aGetinstanceofe_2; "GetInstanceOfEnum failed: 0x%x in %s"
0x18008ad04  jmp     loc_18008AE11
0x18008ad09  lea     rcx, [rsp+68h+arg_18]; struct ITSEventDispatcher **
0x18008ad11  call    ?GetGlobalDispatcher@CHelper@@SAJPEAPEAUITSEventDispatcher@@@Z; CHelper::GetGlobalDispatcher(ITSEventDispatcher * *)
0x18008ad16  mov     ebx, eax
0x18008ad18  test    eax, eax
0x18008ad1a  jns     short loc_18008AD2B
0x18008ad1c  mov     r8d, eax
0x18008ad1f  lea     rdx, aGetglobaldispa; "GetGlobalDispatcher failed: 0x%x in %s"
0x18008ad26  jmp     loc_18008AE11
0x18008ad2b  lea     rax, [rdi+710h]
0x18008ad32  mov     [rax+8], rax
0x18008ad36  mov     [rax], rax
0x18008ad39  xor     r9d, r9d; lpName
0x18008ad3c  xor     edx, edx; lInitialCount
0x18008ad3e  xor     ecx, ecx; lpSemaphoreAttributes
0x18008ad40  lea     r8d, [r9+64h]; lMaximumCount
0x18008ad44  call    cs:__imp_CreateSemaphoreW
0x18008ad4b  nop     dword ptr [rax+rax+00h]
0x18008ad50  mov     [rdi+788h], rax
0x18008ad57  xor     r9d, r9d; lpName
0x18008ad5a  xor     r8d, r8d; bInitialState
0x18008ad5d  lea     edx, [r9+1]; bManualReset
0x18008ad61  xor     ecx, ecx; lpEventAttributes
0x18008ad63  call    cs:__imp_CreateEventW
0x18008ad6a  nop     dword ptr [rax+rax+00h]
0x18008ad6f  mov     [rdi+790h], rax
0x18008ad76  mov     rcx, [rsp+68h+arg_18]
0x18008ad7e  mov     rax, [rcx]
0x18008ad81  mov     r8, r13
0x18008ad84  mov     rdx, rdi
0x18008ad87  mov     rax, [rax+30h]
0x18008ad8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ad90  mov     ebx, eax
0x18008ad92  test    eax, eax
0x18008ad94  jns     short loc_18008ADA2
0x18008ad96  mov     r8d, eax
0x18008ad99  lea     rdx, aAdviseFailed0x; "Advise failed: 0x%x in %s"
0x18008ada0  jmp     short loc_18008AE11
0x18008ada2  mov     [rsp+68h+ThreadId], 0
0x18008adad  lea     rax, [rsp+68h+ThreadId]
0x18008adb5  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18008adba  mov     dword ptr [rsp+68h+TableContext], 0; dwCreationFlags
0x18008adc2  mov     r9, rdi; lpParameter
0x18008adc5  lea     r8, ?staticNotificationWorker@CProtocolExMgr@@CAKPEAX@Z; lpStartAddress
0x18008adcc  xor     edx, edx; dwStackSize
0x18008adce  xor     ecx, ecx; lpThreadAttributes
0x18008add0  call    cs:__imp_CreateThread
0x18008add7  nop     dword ptr [rax+rax+00h]
0x18008addc  mov     [rdi+798h], rax
0x18008ade3  test    rax, rax
0x18008ade6  jnz     short loc_18008AE22
0x18008ade8  call    cs:__imp_GetLastError
0x18008adef  nop     dword ptr [rax+rax+00h]
0x18008adf4  mov     ebx, eax
0x18008adf6  test    eax, eax
0x18008adf8  jle     short loc_18008AE03
0x18008adfa  movzx   ebx, ax
0x18008adfd  or      ebx, 80070000h
0x18008ae03  test    ebx, ebx
0x18008ae05  jns     short loc_18008AE22
0x18008ae07  mov     r8d, ebx
0x18008ae0a  lea     rdx, aCreatethreadSt; "CreateThread( staticNotificationWorker "...
0x18008ae11  lea     r9, aCprotocolexmgr_4; "CProtocolExMgr::CProtocolExMgr"
0x18008ae18  mov     ecx, 8; int
0x18008ae1d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008ae22  mov     [r12], ebx
0x18008ae26  lea     rcx, [rsp+68h+arg_18]; void *
0x18008ae2e  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18008ae33  nop
0x18008ae34  mov     rax, rdi
0x18008ae37  mov     rbx, [rsp+68h+arg_8]
0x18008ae3c  add     rsp, 30h
0x18008ae40  pop     r15
0x18008ae42  pop     r14
0x18008ae44  pop     r13
0x18008ae46  pop     r12
0x18008ae48  pop     rdi
0x18008ae49  pop     rsi
0x18008ae4a  pop     rbp
0x18008ae4b  retn
```
