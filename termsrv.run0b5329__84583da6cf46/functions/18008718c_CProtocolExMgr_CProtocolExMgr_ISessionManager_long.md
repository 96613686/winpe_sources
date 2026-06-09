# CProtocolExMgr::CProtocolExMgr(ISessionManager *,long *)

- ea: `0x18008718c`
- end: `0x18008740e`
- name: `??0CProtocolExMgr@@QEAA@PEAUISessionManager@@PEAJ@Z`
- size: `642`
- prototype: `CProtocolExMgr *__fastcall(CProtocolExMgr *__hidden this, struct ISessionManager *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180046100`

## callees

- `0x18000a210`
- `0x180013150`
- `0x180025fc4`
- `0x18002817c`
- `0x18003cae8`
- `0x180044b50`
- `0x18008718c`
- `0x1800c8010`

## import_xrefs

- `ntdll!RtlInitializeGenericTable` at `0x180087224`
- `ntdll!RtlInitializeGenericTable` at `0x180087224`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180087337`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180087337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800873b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800873b0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008739e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008739e`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18008731e`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18008731e`

## string_xrefs

- `0x1800871ae`: `CProtocolExMgr`
- `0x1800873d3`: `CProtocolExMgr::CProtocolExMgr`
- `0x18008726c`: `ProtocolMgrListLock.Initialize failed: 0x%x in %s`
- `0x1800873cc`: `CreateThread( staticNotificationWorker ) failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18008718c  mov     [rsp+arg_8], rbx
0x180087191  mov     [rsp+arg_0], rcx
0x180087196  push    rbp
0x180087197  push    rsi
0x180087198  push    rdi
0x180087199  push    r12
0x18008719b  push    r13
0x18008719d  push    r14
0x18008719f  push    r15
0x1800871a1  sub     rsp, 30h
0x1800871a5  mov     r12, r8
0x1800871a8  mov     rbx, rdx
0x1800871ab  mov     rdi, rcx
0x1800871ae  lea     rdx, aCprotocolexmgr_9; "CProtocolExMgr"
0x1800871b5  call    ??0CDefTSNotifySink@@QEAA@PEBD@Z; CDefTSNotifySink::CDefTSNotifySink(char const *)
0x1800871ba  nop
0x1800871bb  lea     rax, ??_7CProtocolExMgr@@6B@; const CProtocolExMgr::`vftable'
0x1800871c2  mov     [rdi], rax
0x1800871c5  lea     r14, [rdi+638h]
0x1800871cc  mov     rdx, rbx
0x1800871cf  mov     rcx, r14
0x1800871d2  call    ??0?$SmartPtr@VIRemoteTerminal@@@@QEAA@PEAVIRemoteTerminal@@@Z; SmartPtr<IRemoteTerminal>::SmartPtr<IRemoteTerminal>(IRemoteTerminal *)
0x1800871d7  nop
0x1800871d8  lea     rsi, [rdi+640h]
0x1800871df  xor     eax, eax
0x1800871e1  mov     [rsi], rax
0x1800871e4  lea     r15, [rdi+648h]
0x1800871eb  mov     [r15], rax
0x1800871ee  lea     r13, [rdi+650h]
0x1800871f5  mov     [r13+0], rax
0x1800871f9  lea     rbx, [rdi+658h]
0x180087200  mov     [rbx+60h], eax
0x180087203  lea     rcx, [rdi+6C0h]; Table
0x18008720a  mov     [rsp+68h+TableContext], rcx; TableContext
0x18008720f  lea     r9, ?staticFreeEntry@?$CListTree@VIListenerItem@@@@KAXPEAU_RTL_GENERIC_TABLE@@PEAX@Z; FreeRoutine
0x180087216  lea     r8, ?staticAllocateEntry@?$CListTree@VIProtocolManager@@@@KAPEAXPEAU_RTL_GENERIC_TABLE@@K@Z; AllocateRoutine
0x18008721d  lea     rdx, ?staticCompareEntry@?$CListTree@VIProtocolManager@@@@KA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_GENERIC_TABLE@@PEAX1@Z; CompareRoutine
0x180087224  call    cs:__imp_RtlInitializeGenericTable
0x18008722a  nop
0x18008722b  mov     byte ptr [rdi+708h], 1
0x180087232  lea     rbp, [rdi+720h]
0x180087239  xor     eax, eax
0x18008723b  mov     [rbp+60h], eax
0x18008723e  mov     [rdi+788h], rax
0x180087245  mov     [rdi+790h], rax
0x18008724c  mov     [rdi+798h], rax
0x180087253  mov     [rsp+68h+arg_18], rax
0x18008725b  mov     rcx, rbx; this
0x18008725e  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x180087263  mov     ebx, eax
0x180087265  test    eax, eax
0x180087267  jns     short loc_180087278
0x180087269  mov     r8d, eax
0x18008726c  lea     rdx, aProtocolmgrlis; "ProtocolMgrListLock.Initialize failed: "...
0x180087273  jmp     loc_1800873D3
0x180087278  mov     rcx, rbp; this
0x18008727b  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x180087280  mov     ebx, eax
0x180087282  test    eax, eax
0x180087284  jns     short loc_180087295
0x180087286  mov     r8d, eax
0x180087289  lea     rdx, aNotificationwo; "NotificationWorkItemsLock.Initialize fa"...
0x180087290  jmp     loc_1800873D3
0x180087295  mov     rcx, [r14]
0x180087298  mov     rax, [rcx]
0x18008729b  mov     rdx, rsi
0x18008729e  mov     rax, [rax+18h]
0x1800872a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800872a7  mov     ebx, eax
0x1800872a9  test    eax, eax
0x1800872ab  jns     short loc_1800872BC
0x1800872ad  mov     r8d, eax
0x1800872b0  lea     rdx, aGetsessionlist_0; "GetSessionList failed: 0x%x in %s"
0x1800872b7  jmp     loc_1800873D3
0x1800872bc  mov     rcx, [rsi]
0x1800872bf  mov     rax, [rcx]
0x1800872c2  mov     rdx, r15
0x1800872c5  mov     rax, [rax+20h]
0x1800872c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800872ce  mov     ebx, eax
0x1800872d0  test    eax, eax
0x1800872d2  jns     short loc_1800872E3
0x1800872d4  mov     r8d, eax
0x1800872d7  lea     rdx, aGetinstanceofe_2; "GetInstanceOfEnum failed: 0x%x in %s"
0x1800872de  jmp     loc_1800873D3
0x1800872e3  lea     rcx, [rsp+68h+arg_18]; struct ITSEventDispatcher **
0x1800872eb  call    ?GetGlobalDispatcher@CHelper@@SAJPEAPEAUITSEventDispatcher@@@Z; CHelper::GetGlobalDispatcher(ITSEventDispatcher * *)
0x1800872f0  mov     ebx, eax
0x1800872f2  test    eax, eax
0x1800872f4  jns     short loc_180087305
0x1800872f6  mov     r8d, eax
0x1800872f9  lea     rdx, aGetglobaldispa; "GetGlobalDispatcher failed: 0x%x in %s"
0x180087300  jmp     loc_1800873D3
0x180087305  lea     rax, [rdi+710h]
0x18008730c  mov     [rax+8], rax
0x180087310  mov     [rax], rax
0x180087313  xor     r9d, r9d; lpName
0x180087316  xor     edx, edx; lInitialCount
0x180087318  xor     ecx, ecx; lpSemaphoreAttributes
0x18008731a  lea     r8d, [r9+64h]; lMaximumCount
0x18008731e  call    cs:__imp_CreateSemaphoreW
0x180087324  mov     [rdi+788h], rax
0x18008732b  xor     r9d, r9d; lpName
0x18008732e  xor     r8d, r8d; bInitialState
0x180087331  lea     edx, [r9+1]; bManualReset
0x180087335  xor     ecx, ecx; lpEventAttributes
0x180087337  call    cs:__imp_CreateEventW
0x18008733d  mov     [rdi+790h], rax
0x180087344  mov     rcx, [rsp+68h+arg_18]
0x18008734c  mov     rax, [rcx]
0x18008734f  mov     r8, r13
0x180087352  mov     rdx, rdi
0x180087355  mov     rax, [rax+30h]
0x180087359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008735e  mov     ebx, eax
0x180087360  test    eax, eax
0x180087362  jns     short loc_180087370
0x180087364  mov     r8d, eax
0x180087367  lea     rdx, aAdviseFailed0x; "Advise failed: 0x%x in %s"
0x18008736e  jmp     short loc_1800873D3
0x180087370  mov     [rsp+68h+ThreadId], 0
0x18008737b  lea     rax, [rsp+68h+ThreadId]
0x180087383  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x180087388  mov     dword ptr [rsp+68h+TableContext], 0; dwCreationFlags
0x180087390  mov     r9, rdi; lpParameter
0x180087393  lea     r8, ?staticNotificationWorker@CProtocolExMgr@@CAKPEAX@Z; lpStartAddress
0x18008739a  xor     edx, edx; dwStackSize
0x18008739c  xor     ecx, ecx; lpThreadAttributes
0x18008739e  call    cs:__imp_CreateThread
0x1800873a4  mov     [rdi+798h], rax
0x1800873ab  test    rax, rax
0x1800873ae  jnz     short loc_1800873E4
0x1800873b0  call    cs:__imp_GetLastError
0x1800873b6  mov     ebx, eax
0x1800873b8  test    eax, eax
0x1800873ba  jle     short loc_1800873C5
0x1800873bc  movzx   ebx, ax
0x1800873bf  or      ebx, 80070000h
0x1800873c5  test    ebx, ebx
0x1800873c7  jns     short loc_1800873E4
0x1800873c9  mov     r8d, ebx
0x1800873cc  lea     rdx, aCreatethreadSt; "CreateThread( staticNotificationWorker "...
0x1800873d3  lea     r9, aCprotocolexmgr_4; "CProtocolExMgr::CProtocolExMgr"
0x1800873da  mov     ecx, 8; int
0x1800873df  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800873e4  mov     [r12], ebx
0x1800873e8  lea     rcx, [rsp+68h+arg_18]; void *
0x1800873f0  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800873f5  nop
0x1800873f6  mov     rax, rdi
0x1800873f9  mov     rbx, [rsp+68h+arg_8]
0x1800873fe  add     rsp, 30h
0x180087402  pop     r15
0x180087404  pop     r14
0x180087406  pop     r13
0x180087408  pop     r12
0x18008740a  pop     rdi
0x18008740b  pop     rsi
0x18008740c  pop     rbp
0x18008740d  retn
```
