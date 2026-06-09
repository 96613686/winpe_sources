# WdcSysmonNode::CreateMonitor(WdcConsoleManager *,ISystemMonitor2 * *)

- ea: `0x18005177c`
- end: `0x18005199a`
- name: `?CreateMonitor@WdcSysmonNode@@AEAAJPEAVWdcConsoleManager@@PEAPEAUISystemMonitor2@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(WdcSysmonNode *__hidden this, struct WdcConsoleManager *, struct ISystemMonitor2 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180051d30`

## callees

- `0x18000b854`
- `0x180049e20`
- `0x18005177c`
- `0x180051f68`
- `0x180086010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180051912`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180051912`
- `SHELL32!CommandLineToArgvW` at `0x1800518b4`
- `SHELL32!CommandLineToArgvW` at `0x1800518b4`
- `KERNEL32!GetLastError` at `0x1800518c2`
- `KERNEL32!GetLastError` at `0x1800518c2`
- `KERNEL32!GetCommandLineW` at `0x1800518a7`
- `KERNEL32!GetCommandLineW` at `0x1800518a7`
- `ole32!CoCreateInstance` at `0x1800517d2`
- `ole32!CoCreateInstance` at `0x1800517d2`

## string_xrefs

- `0x1800517ec`: `WdcSysmonNode::CreateMonitor`

## pseudocode

```c
__int64 __fastcall WdcSysmonNode::CreateMonitor(
        WdcSysmonNode *this,
        struct WdcConsoleManager *a2,
        struct ISystemMonitor2 **a3)
{
  HRESULT Instance; // eax
  signed int File; // ebx
  __int64 v8; // rcx
  const WCHAR *CommandLineW; // rax
  LPWSTR *v10; // rax
  LPWSTR *v11; // r14
  signed int LastError; // eax
  int v13; // esi
  LPVOID *ppv; // [rsp+20h] [rbp-20h]
  struct ISystemMonitor2 *v16; // [rsp+30h] [rbp-10h] BYREF
  struct IUnknown *v17; // [rsp+38h] [rbp-8h] BYREF
  int pNumArgs; // [rsp+88h] [rbp+48h] BYREF

  pNumArgs = 0;
  v17 = 0;
  v16 = 0;
  Instance = CoCreateInstance(&CLSID_SystemMonitor, 0, 0x15u, &IID_ISystemMonitor2, (LPVOID *)&v16);
  File = Instance;
  if ( Instance < 0 )
    goto LABEL_2;
  Instance = ((__int64 (__fastcall *)(struct ISystemMonitor2 *, GUID *, struct ISystemMonitor2 **))v16->lpVtbl->QueryInterface)(
               v16,
               &IID_ISystemMonitor2,
               a3);
  File = Instance;
  if ( Instance < 0 )
    goto LABEL_2;
  Instance = ((__int64 (__fastcall *)(struct ISystemMonitor2 *, GUID *, struct IUnknown **))v16->lpVtbl->QueryInterface)(
               v16,
               &IID_IUnknown,
               &v17);
  File = Instance;
  if ( Instance < 0 )
    goto LABEL_2;
  Instance = WdcConsoleManager::SetControl(a2, (__int64)this, v17);
  File = Instance;
  if ( Instance < 0 )
    goto LABEL_2;
  if ( !*((_DWORD *)this + 108) )
    goto LABEL_26;
  if ( *((_QWORD *)this + 55) )
  {
    (*(void (__fastcall **)(WdcSysmonNode *, struct WdcConsoleManager *))(*(_QWORD *)this + 336LL))(this, a2);
    v8 = *((_QWORD *)this + 55);
    File = 0;
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *((_QWORD *)this + 55) = 0;
    }
  }
  CommandLineW = GetCommandLineW();
  v10 = CommandLineToArgvW(CommandLineW, &pNumArgs);
  v11 = v10;
  if ( !v10 || v10 == (LPWSTR *)-1LL )
  {
    LastError = GetLastError();
    File = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        File = (unsigned __int16)LastError | 0x80070000;
      if ( File >= 0 )
        goto LABEL_19;
    }
    else
    {
      File = -2147467259;
    }
    Instance = File;
LABEL_2:
    LODWORD(ppv) = Instance;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\sysmonnode.cpp",
      "WdcSysmonNode::CreateMonitor",
      0,
      L"FAILURE: 0x%08x",
      ppv);
    goto LABEL_26;
  }
LABEL_19:
  if ( pNumArgs > 1 )
  {
    v13 = 1;
    if ( pNumArgs - 1 > 1 )
    {
      while ( (unsigned int)_o__wcsicmp(v11[v13], L"/F") )
      {
        if ( ++v13 >= pNumArgs - 1 )
          goto LABEL_26;
      }
      File = WdcSysmonNode::LoadFile(this, a2, v16, v11[v13 + 1], 0);
      if ( File < 0 )
        File = 0;
    }
  }
LABEL_26:
  if ( v16 )
  {
    ((void (__fastcall *)(struct ISystemMonitor2 *))v16->lpVtbl->Release)(v16);
    v16 = 0;
  }
  if ( v17 )
    ((void (__fastcall *)(struct IUnknown *))v17->lpVtbl->Release)(v17);
  return (unsigned int)File;
}

```

## disassembly

```asm
0x18005177c  mov     [rsp-28h+arg_0], rbx
0x180051781  mov     [rsp-28h+arg_8], rsi
0x180051786  push    rbp
0x180051787  push    rdi
0x180051788  push    r12
0x18005178a  push    r14
0x18005178c  push    r15
0x18005178e  mov     rbp, rsp
0x180051791  sub     rsp, 40h
0x180051795  mov     r12, rdx
0x180051798  mov     [rbp+pNumArgs], 0
0x18005179f  xor     edx, edx; pUnkOuter
0x1800517a1  mov     [rbp+var_8], 0
0x1800517a9  mov     rsi, r8
0x1800517ac  mov     [rbp+var_10], 0
0x1800517b4  mov     rdi, rcx
0x1800517b7  lea     rax, [rbp+var_10]
0x1800517bb  lea     r9, IID_ISystemMonitor2; riid
0x1800517c2  mov     [rsp+40h+ppv], rax; ppv
0x1800517c7  lea     r8d, [rdx+15h]; dwClsContext
0x1800517cb  lea     rcx, CLSID_SystemMonitor; rclsid
0x1800517d2  call    cs:__imp_CoCreateInstance
0x1800517d8  mov     ebx, eax
0x1800517da  test    eax, eax
0x1800517dc  jns     short loc_180051804
0x1800517de  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800517e5  mov     dword ptr [rsp+40h+ppv], eax
0x1800517e9  xor     r8d, r8d; int
0x1800517ec  lea     rdx, aWdcsysmonnodeC_0; "WdcSysmonNode::CreateMonitor"
0x1800517f3  lea     rcx, aBaseDiagnosisP_9; "base\\diagnosis\\pdui\\perfmon\\mmc\\sy"...
0x1800517fa  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800517ff  jmp     loc_18005194F
0x180051804  mov     rcx, [rbp+var_10]
0x180051808  lea     rdx, IID_ISystemMonitor2
0x18005180f  mov     r8, rsi
0x180051812  mov     rax, [rcx]
0x180051815  mov     rax, [rax]
0x180051818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005181d  mov     ebx, eax
0x18005181f  test    eax, eax
0x180051821  js      short loc_1800517DE
0x180051823  mov     rcx, [rbp+var_10]
0x180051827  lea     r8, [rbp+var_8]
0x18005182b  lea     rdx, IID_IUnknown
0x180051832  mov     rax, [rcx]
0x180051835  mov     rax, [rax]
0x180051838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005183d  mov     ebx, eax
0x18005183f  test    eax, eax
0x180051841  js      short loc_1800517DE
0x180051843  mov     r8, [rbp+var_8]; struct IUnknown *
0x180051847  mov     rdx, rdi; __int64
0x18005184a  mov     rcx, r12; this
0x18005184d  call    ?SetControl@WdcConsoleManager@@QEAAJ_JPEAUIUnknown@@@Z; WdcConsoleManager::SetControl(__int64,IUnknown *)
0x180051852  mov     ebx, eax
0x180051854  test    eax, eax
0x180051856  js      short loc_1800517DE
0x180051858  cmp     dword ptr [rdi+1B0h], 0
0x18005185f  jz      loc_18005194F
0x180051865  mov     r8, [rdi+1B8h]
0x18005186c  test    r8, r8
0x18005186f  jz      short loc_1800518A7
0x180051871  mov     rax, [rdi]
0x180051874  mov     rdx, r12
0x180051877  mov     rcx, rdi
0x18005187a  mov     rax, [rax+150h]
0x180051881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051886  mov     rcx, [rdi+1B8h]
0x18005188d  xor     ebx, ebx
0x18005188f  test    rcx, rcx
0x180051892  jz      short loc_1800518A7
0x180051894  mov     rax, [rcx]
0x180051897  mov     rax, [rax+10h]
0x18005189b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800518a0  mov     [rdi+1B8h], rbx
0x1800518a7  call    cs:__imp_GetCommandLineW
0x1800518ad  mov     rcx, rax; lpCmdLine
0x1800518b0  lea     rdx, [rbp+pNumArgs]; pNumArgs
0x1800518b4  call    cs:__imp_CommandLineToArgvW
0x1800518ba  mov     r14, rax
0x1800518bd  test    rax, rax
0x1800518c0  jnz     short loc_1800518EB
0x1800518c2  call    cs:__imp_GetLastError
0x1800518c8  mov     ebx, eax
0x1800518ca  test    eax, eax
0x1800518cc  jz      short loc_1800518DF
0x1800518ce  jle     short loc_1800518D9
0x1800518d0  movzx   ebx, ax
0x1800518d3  or      ebx, 80070000h
0x1800518d9  test    ebx, ebx
0x1800518db  jns     short loc_1800518F1
0x1800518dd  jmp     short loc_1800518E4
0x1800518df  mov     ebx, 80004005h
0x1800518e4  mov     eax, ebx
0x1800518e6  jmp     loc_1800517DE
0x1800518eb  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800518ef  jz      short loc_1800518C2
0x1800518f1  mov     eax, [rbp+pNumArgs]
0x1800518f4  cmp     eax, 1
0x1800518f7  jle     short loc_18005194F
0x1800518f9  mov     esi, 1
0x1800518fe  dec     eax
0x180051900  cmp     eax, esi
0x180051902  jle     short loc_18005194F
0x180051904  movsxd  r15, esi
0x180051907  lea     rdx, asc_180092760; "/F"
0x18005190e  mov     rcx, [r14+r15*8]
0x180051912  call    cs:__imp__o__wcsicmp
0x180051918  test    eax, eax
0x18005191a  jz      short loc_180051929
0x18005191c  mov     eax, [rbp+pNumArgs]
0x18005191f  inc     esi
0x180051921  dec     eax
0x180051923  cmp     esi, eax
0x180051925  jl      short loc_180051904
0x180051927  jmp     short loc_18005194F
0x180051929  mov     r9, [r14+r15*8+8]; unsigned __int16 *
0x18005192e  mov     rdx, r12; struct WdcConsoleManager *
0x180051931  mov     r8, [rbp+var_10]; struct ISystemMonitor2 *
0x180051935  mov     rcx, rdi; this
0x180051938  mov     [rsp+40h+ppv], 0; struct IDataCollectorSet *
0x180051941  call    ?LoadFile@WdcSysmonNode@@QEAAJPEAVWdcConsoleManager@@PEAUISystemMonitor2@@PEBGPEAUIDataCollectorSet@@@Z; WdcSysmonNode::LoadFile(WdcConsoleManager *,ISystemMonitor2 *,ushort const *,IDataCollectorSet *)
0x180051946  mov     ebx, eax
0x180051948  xor     eax, eax
0x18005194a  test    ebx, ebx
0x18005194c  cmovs   ebx, eax
0x18005194f  mov     rcx, [rbp+var_10]
0x180051953  test    rcx, rcx
0x180051956  jz      short loc_18005196C
0x180051958  mov     rax, [rcx]
0x18005195b  mov     rax, [rax+10h]
0x18005195f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051964  mov     [rbp+var_10], 0
0x18005196c  mov     rcx, [rbp+var_8]
0x180051970  test    rcx, rcx
0x180051973  jz      short loc_180051981
0x180051975  mov     rax, [rcx]
0x180051978  mov     rax, [rax+10h]
0x18005197c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051981  mov     rsi, [rsp+40h+arg_8]
0x180051986  mov     eax, ebx
0x180051988  mov     rbx, [rsp+40h+arg_0]
0x18005198d  add     rsp, 40h
0x180051991  pop     r15
0x180051993  pop     r14
0x180051995  pop     r12
0x180051997  pop     rdi
0x180051998  pop     rbp
0x180051999  retn
```
