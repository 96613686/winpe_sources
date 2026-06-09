# CRemoteTerminal::IsUserAllowedToLogon(IUserName *)

- ea: `0x180054de0`
- end: `0x180054fdf`
- name: `?IsUserAllowedToLogon@CRemoteTerminal@@UEAAJPEAUIUserName@@@Z`
- size: `511`
- prototype: `__int64 __fastcall(CRemoteTerminal *__hidden this, struct IUserName *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180055150`

## callees

- `0x180009940`
- `0x18000f0d0`
- `0x180012750`
- `0x180015020`
- `0x180015238`
- `0x180033f60`
- `0x18003f9a8`
- `0x180040878`
- `0x1800524e8`
- `0x180054de0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180054ee4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180054ee4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054f6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054f81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054f6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054f81`

## string_xrefs

- `0x180054f0b`: `DuplicateTokenInPid failed: 0x%x in %s`

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
0x180054de0  mov     [rsp-8+arg_10], rbx
0x180054de5  mov     [rsp-8+arg_18], rsi
0x180054dea  push    rbp
0x180054deb  push    rdi
0x180054dec  push    r15
0x180054dee  lea     rbp, [rsp-30h]
0x180054df3  sub     rsp, 130h
0x180054dfa  mov     rax, cs:__security_cookie
0x180054e01  xor     rax, rsp
0x180054e04  mov     [rbp+40h+var_20], rax
0x180054e08  mov     rdi, rdx
0x180054e0b  mov     rsi, rcx
0x180054e0e  mov     [rsp+140h+var_108], 0
0x180054e17  mov     [rsp+140h+pv], 0
0x180054e20  mov     [rsp+140h+var_100], 0
0x180054e29  mov     r8, rcx; struct CRemoteTerminal *
0x180054e2c  lea     r15, aCremotetermina_22; "CRemoteTerminal::IsUserAllowedToLogon"
0x180054e33  mov     rdx, r15; char *
0x180054e36  lea     rcx, [rbp+40h+var_C0]; this
0x180054e3a  call    ??0CTSRemoteTerminalTrace@@QEAA@PEBDPEAVCRemoteTerminal@@@Z; CTSRemoteTerminalTrace::CTSRemoteTerminalTrace(char const *,CRemoteTerminal *)
0x180054e3f  nop
0x180054e40  mov     r8, r15; char *
0x180054e43  mov     edx, [rsi+690h]; int
0x180054e49  lea     rcx, [rsp+140h+Parameter]; Parameter
0x180054e4e  call    ??0CTerminalOpsMonitor@@QEAA@JPEBD@Z; CTerminalOpsMonitor::CTerminalOpsMonitor(long,char const *)
0x180054e53  nop
0x180054e54  lea     rdx, [rsi+13F8h]; struct CResource *
0x180054e5b  lea     rcx, [rsp+140h+var_F8]; this
0x180054e60  call    ??0CAutoSharedLock@@QEAA@AEAVCResource@@@Z; CAutoSharedLock::CAutoSharedLock(CResource &)
0x180054e65  nop
0x180054e66  cmp     qword ptr [rsi+640h], 0
0x180054e6e  jnz     short loc_180054E91
0x180054e70  mov     ebx, 800708CAh
0x180054e75  mov     r8d, ebx
0x180054e78  lea     rdx, aIconnectionNul; "(IConnection *)NULL == this->ptrConnect"...
0x180054e7f  mov     r9, r15
0x180054e82  mov     ecx, 8; int
0x180054e87  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180054e8c  jmp     loc_180054F61
0x180054e91  mov     rax, [rdi]
0x180054e94  lea     rdx, [rsp+140h+var_108]
0x180054e99  mov     rcx, rdi
0x180054e9c  mov     rax, [rax+28h]
0x180054ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ea5  mov     ebx, eax
0x180054ea7  test    eax, eax
0x180054ea9  jns     short loc_180054EB7
0x180054eab  mov     r8d, eax
0x180054eae  lea     rdx, aGetuserstrFail; "GetUserStr failed: 0x%x in %s"
0x180054eb5  jmp     short loc_180054E7F
0x180054eb7  mov     rax, [rdi]
0x180054eba  lea     rdx, [rsp+140h+pv]
0x180054ebf  mov     rcx, rdi
0x180054ec2  mov     rax, [rax+30h]
0x180054ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ecb  mov     ebx, eax
0x180054ecd  test    eax, eax
0x180054ecf  jns     short loc_180054EDD
0x180054ed1  mov     r8d, eax
0x180054ed4  lea     rdx, aGetdomainstrFa; "GetDomainStr failed: 0x%x in %s"
0x180054edb  jmp     short loc_180054E7F
0x180054edd  mov     rax, [rdi]
0x180054ee0  mov     rbx, [rax+50h]
0x180054ee4  call    cs:__imp_GetCurrentProcessId
0x180054eeb  nop     dword ptr [rax+rax+00h]
0x180054ef0  lea     r8, [rsp+140h+var_100]
0x180054ef5  mov     edx, eax
0x180054ef7  mov     rcx, rdi
0x180054efa  mov     rax, rbx
0x180054efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f02  mov     ebx, eax
0x180054f04  test    eax, eax
0x180054f06  jns     short loc_180054F17
0x180054f08  mov     r8d, eax
0x180054f0b  lea     rdx, aDuplicatetoken; "DuplicateTokenInPid failed: 0x%x in %s"
0x180054f12  jmp     loc_180054E7F
0x180054f17  mov     rcx, [rsi+640h]
0x180054f1e  mov     rdx, [rsp+140h+var_108]
0x180054f23  mov     rax, [rcx]
0x180054f26  mov     [rsp+140h+var_120], rdx
0x180054f2b  mov     r9, [rsp+140h+pv]
0x180054f30  mov     r8, [rsp+140h+var_100]
0x180054f35  mov     edx, [rsi+690h]
0x180054f3b  mov     rax, [rax+1F0h]
0x180054f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f47  mov     ebx, eax
0x180054f49  test    eax, eax
0x180054f4b  jns     short loc_180054F61
0x180054f4d  mov     r8d, eax
0x180054f50  lea     rdx, aIsuserallowedt; "IsUserAllowedToLogon return 0x%x"
0x180054f57  mov     ecx, 1; int
0x180054f5c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180054f61  mov     rcx, [rsp+140h+pv]; pv
0x180054f66  test    rcx, rcx
0x180054f69  jz      short loc_180054F77
0x180054f6b  call    cs:__imp_CoTaskMemFree
0x180054f72  nop     dword ptr [rax+rax+00h]
0x180054f77  mov     rcx, [rsp+140h+var_108]; pv
0x180054f7c  test    rcx, rcx
0x180054f7f  jz      short loc_180054F8E
0x180054f81  call    cs:__imp_CoTaskMemFree
0x180054f88  nop     dword ptr [rax+rax+00h]
0x180054f8d  nop
0x180054f8e  lea     rcx, [rsp+140h+var_F8]; this
0x180054f93  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180054f98  nop
0x180054f99  lea     rcx, [rsp+140h+Parameter]; this
0x180054f9e  call    ??1CTerminalOpsMonitor@@UEAA@XZ; CTerminalOpsMonitor::~CTerminalOpsMonitor(void)
0x180054fa3  nop
0x180054fa4  lea     rcx, [rbp+40h+var_C0]; this
0x180054fa8  call    ??1CTSRemoteTerminalTrace@@UEAA@XZ; CTSRemoteTerminalTrace::~CTSRemoteTerminalTrace(void)
0x180054fad  nop
0x180054fae  lea     rcx, [rsp+140h+var_100]; this
0x180054fb3  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x180054fb8  mov     eax, ebx
0x180054fba  mov     rcx, [rbp+40h+var_20]
0x180054fbe  xor     rcx, rsp; StackCookie
0x180054fc1  call    __security_check_cookie
0x180054fc6  lea     r11, [rsp+140h+var_10]
0x180054fce  mov     rbx, [r11+30h]
0x180054fd2  mov     rsi, [r11+38h]
0x180054fd6  mov     rsp, r11
0x180054fd9  pop     r15
0x180054fdb  pop     rdi
0x180054fdc  pop     rbp
0x180054fdd  retn
```
