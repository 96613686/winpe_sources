# CRemoteTerminal::IsUserAllowedToLogon(IUserName *)

- ea: `0x1800526a0`
- end: `0x18005288c`
- name: `?IsUserAllowedToLogon@CRemoteTerminal@@UEAAJPEAUIUserName@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(CRemoteTerminal *__hidden this, struct IUserName *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180052a00`

## callees

- `0x18000a210`
- `0x18000ef50`
- `0x180011f80`
- `0x180014814`
- `0x1800148d0`
- `0x1800321f0`
- `0x18003d79c`
- `0x18003e644`
- `0x18004fe3c`
- `0x1800526a0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800527a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800527a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052825`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052825`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052835`

## string_xrefs

- `0x1800527c5`: `DuplicateTokenInPid failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRemoteTerminal::IsUserAllowedToLogon(CRemoteTerminal *this, struct IUserName *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // eax
  __int64 (__fastcall *v7)(struct IUserName *, _QWORD, __int64 *); // rbx
  DWORD CurrentProcessId; // eax
  int v9; // eax
  int v10; // eax
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v13; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[16]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Parameter[40]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v17[160]; // [rsp+80h] [rbp-80h] BYREF

  v13 = 0;
  pv = 0;
  v14 = 0;
  CTSRemoteTerminalTrace::CTSRemoteTerminalTrace(
    (CTSRemoteTerminalTrace *)v17,
    "CRemoteTerminal::IsUserAllowedToLogon",
    this);
  CTerminalOpsMonitor::CTerminalOpsMonitor(Parameter, *((_DWORD *)this + 420), "CRemoteTerminal::IsUserAllowedToLogon");
  CAutoSharedLock::CAutoSharedLock((CAutoSharedLock *)v15, (CRemoteTerminal *)((char *)this + 5112));
  if ( *((_QWORD *)this + 200) )
  {
    v5 = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, &v13);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)a2 + 48LL))(a2, &pv);
      v4 = v6;
      if ( v6 >= 0 )
      {
        v7 = *(__int64 (__fastcall **)(struct IUserName *, _QWORD, __int64 *))(*(_QWORD *)a2 + 80LL);
        CurrentProcessId = GetCurrentProcessId();
        v9 = v7(a2, CurrentProcessId, &v14);
        v4 = v9;
        if ( v9 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, LPVOID, LPVOID))(**((_QWORD **)this + 200) + 496LL))(
                  *((_QWORD *)this + 200),
                  *((unsigned int *)this + 420),
                  v14,
                  pv,
                  v13);
          v4 = v10;
          if ( v10 < 0 )
            _DbgPrintMessage(1, "IsUserAllowedToLogon return 0x%x", v10);
        }
        else
        {
          _DbgPrintMessage(
            8,
            "DuplicateTokenInPid failed: 0x%x in %s",
            (unsigned int)v9,
            "CRemoteTerminal::IsUserAllowedToLogon");
        }
      }
      else
      {
        _DbgPrintMessage(
          8,
          "GetDomainStr failed: 0x%x in %s",
          (unsigned int)v6,
          "CRemoteTerminal::IsUserAllowedToLogon");
      }
    }
    else
    {
      _DbgPrintMessage(8, "GetUserStr failed: 0x%x in %s", (unsigned int)v5, "CRemoteTerminal::IsUserAllowedToLogon");
    }
  }
  else
  {
    v4 = -2147022646;
    _DbgPrintMessage(
      8,
      "(IConnection *)NULL == this->ptrConnection failed: 0x%x in %s",
      2147944650LL,
      "CRemoteTerminal::IsUserAllowedToLogon");
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v13 )
    CoTaskMemFree(v13);
  CAutoLock::Unlock((CAutoLock *)v15);
  CTerminalOpsMonitor::~CTerminalOpsMonitor((CTerminalOpsMonitor *)Parameter);
  CTSRemoteTerminalTrace::~CTSRemoteTerminalTrace((CTSRemoteTerminalTrace *)v17);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&v14);
  return v4;
}

```

## disassembly

```asm
0x1800526a0  mov     [rsp-8+arg_10], rbx
0x1800526a5  mov     [rsp-8+arg_18], rsi
0x1800526aa  push    rbp
0x1800526ab  push    rdi
0x1800526ac  push    r15
0x1800526ae  lea     rbp, [rsp-30h]
0x1800526b3  sub     rsp, 130h
0x1800526ba  mov     rax, cs:__security_cookie
0x1800526c1  xor     rax, rsp
0x1800526c4  mov     [rbp+40h+var_20], rax
0x1800526c8  mov     rdi, rdx
0x1800526cb  mov     rsi, rcx
0x1800526ce  mov     [rsp+140h+var_108], 0
0x1800526d7  mov     [rsp+140h+pv], 0
0x1800526e0  mov     [rsp+140h+var_100], 0
0x1800526e9  mov     r8, rcx; struct CRemoteTerminal *
0x1800526ec  lea     r15, aCremotetermina_22; "CRemoteTerminal::IsUserAllowedToLogon"
0x1800526f3  mov     rdx, r15; char *
0x1800526f6  lea     rcx, [rbp+40h+var_C0]; this
0x1800526fa  call    ??0CTSRemoteTerminalTrace@@QEAA@PEBDPEAVCRemoteTerminal@@@Z; CTSRemoteTerminalTrace::CTSRemoteTerminalTrace(char const *,CRemoteTerminal *)
0x1800526ff  nop
0x180052700  mov     r8, r15; char *
0x180052703  mov     edx, [rsi+690h]; int
0x180052709  lea     rcx, [rsp+140h+Parameter]; Parameter
0x18005270e  call    ??0CTerminalOpsMonitor@@QEAA@JPEBD@Z; CTerminalOpsMonitor::CTerminalOpsMonitor(long,char const *)
0x180052713  nop
0x180052714  lea     rdx, [rsi+13F8h]; struct CResource *
0x18005271b  lea     rcx, [rsp+140h+var_F8]; this
0x180052720  call    ??0CAutoSharedLock@@QEAA@AEAVCResource@@@Z; CAutoSharedLock::CAutoSharedLock(CResource &)
0x180052725  nop
0x180052726  cmp     qword ptr [rsi+640h], 0
0x18005272e  jnz     short loc_180052751
0x180052730  mov     ebx, 800708CAh
0x180052735  mov     r8d, ebx
0x180052738  lea     rdx, aIconnectionNul; "(IConnection *)NULL == this->ptrConnect"...
0x18005273f  mov     r9, r15
0x180052742  mov     ecx, 8; int
0x180052747  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005274c  jmp     loc_18005281B
0x180052751  mov     rax, [rdi]
0x180052754  lea     rdx, [rsp+140h+var_108]
0x180052759  mov     rcx, rdi
0x18005275c  mov     rax, [rax+28h]
0x180052760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052765  mov     ebx, eax
0x180052767  test    eax, eax
0x180052769  jns     short loc_180052777
0x18005276b  mov     r8d, eax
0x18005276e  lea     rdx, aGetuserstrFail; "GetUserStr failed: 0x%x in %s"
0x180052775  jmp     short loc_18005273F
0x180052777  mov     rax, [rdi]
0x18005277a  lea     rdx, [rsp+140h+pv]
0x18005277f  mov     rcx, rdi
0x180052782  mov     rax, [rax+30h]
0x180052786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005278b  mov     ebx, eax
0x18005278d  test    eax, eax
0x18005278f  jns     short loc_18005279D
0x180052791  mov     r8d, eax
0x180052794  lea     rdx, aGetdomainstrFa; "GetDomainStr failed: 0x%x in %s"
0x18005279b  jmp     short loc_18005273F
0x18005279d  mov     rax, [rdi]
0x1800527a0  mov     rbx, [rax+50h]
0x1800527a4  call    cs:__imp_GetCurrentProcessId
0x1800527aa  lea     r8, [rsp+140h+var_100]
0x1800527af  mov     edx, eax
0x1800527b1  mov     rcx, rdi
0x1800527b4  mov     rax, rbx
0x1800527b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800527bc  mov     ebx, eax
0x1800527be  test    eax, eax
0x1800527c0  jns     short loc_1800527D1
0x1800527c2  mov     r8d, eax
0x1800527c5  lea     rdx, aDuplicatetoken; "DuplicateTokenInPid failed: 0x%x in %s"
0x1800527cc  jmp     loc_18005273F
0x1800527d1  mov     rcx, [rsi+640h]
0x1800527d8  mov     rdx, [rsp+140h+var_108]
0x1800527dd  mov     rax, [rcx]
0x1800527e0  mov     [rsp+140h+var_120], rdx
0x1800527e5  mov     r9, [rsp+140h+pv]
0x1800527ea  mov     r8, [rsp+140h+var_100]
0x1800527ef  mov     edx, [rsi+690h]
0x1800527f5  mov     rax, [rax+1F0h]
0x1800527fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052801  mov     ebx, eax
0x180052803  test    eax, eax
0x180052805  jns     short loc_18005281B
0x180052807  mov     r8d, eax
0x18005280a  lea     rdx, aIsuserallowedt; "IsUserAllowedToLogon return 0x%x"
0x180052811  mov     ecx, 1; int
0x180052816  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005281b  mov     rcx, [rsp+140h+pv]; pv
0x180052820  test    rcx, rcx
0x180052823  jz      short loc_18005282B
0x180052825  call    cs:__imp_CoTaskMemFree
0x18005282b  mov     rcx, [rsp+140h+var_108]; pv
0x180052830  test    rcx, rcx
0x180052833  jz      short loc_18005283C
0x180052835  call    cs:__imp_CoTaskMemFree
0x18005283b  nop
0x18005283c  lea     rcx, [rsp+140h+var_F8]; this
0x180052841  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180052846  nop
0x180052847  lea     rcx, [rsp+140h+Parameter]; this
0x18005284c  call    ??1CTerminalOpsMonitor@@UEAA@XZ; CTerminalOpsMonitor::~CTerminalOpsMonitor(void)
0x180052851  nop
0x180052852  lea     rcx, [rbp+40h+var_C0]; this
0x180052856  call    ??1CTSRemoteTerminalTrace@@UEAA@XZ; CTSRemoteTerminalTrace::~CTSRemoteTerminalTrace(void)
0x18005285b  nop
0x18005285c  lea     rcx, [rsp+140h+var_100]; this
0x180052861  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x180052866  mov     eax, ebx
0x180052868  mov     rcx, [rbp+40h+var_20]
0x18005286c  xor     rcx, rsp; StackCookie
0x18005286f  call    __security_check_cookie
0x180052874  lea     r11, [rsp+140h+var_10]
0x18005287c  mov     rbx, [r11+30h]
0x180052880  mov     rsi, [r11+38h]
0x180052884  mov     rsp, r11
0x180052887  pop     r15
0x180052889  pop     rdi
0x18005288a  pop     rbp
0x18005288b  retn
```
