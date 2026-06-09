# WEBHOST_PROTOCOL_MANAGER::InitializeInstance(IWorkerProcessFramework *)

- ea: `0x180002230`
- end: `0x18000242b`
- name: `?InitializeInstance@WEBHOST_PROTOCOL_MANAGER@@QEAAJPEAVIWorkerProcessFramework@@@Z`
- size: `507`
- prototype: `__int64 __fastcall(WEBHOST_PROTOCOL_MANAGER *__hidden this, struct IWorkerProcessFramework *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002130`

## callees

- `0x180001008`
- `0x180001bf8`
- `0x180002230`
- `0x180003d54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022ac`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800022a2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800022a2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000231b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002325`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000231b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002325`
- `iisutil!PuDbgPrint` at `0x180002399`
- `iisutil!PuDbgPrint` at `0x180002413`
- `iisutil!PuDbgPrint` at `0x180002399`
- `iisutil!PuDbgPrint` at `0x180002413`

## string_xrefs

- `0x180002380`: `WEBHOST_PROTOCOL_MANAGER::InitializeInstance`
- `0x180002400`: `WEBHOST_PROTOCOL_MANAGER::InitializeInstance`
- `0x180002392`: `servercommon\inetsrv\iis\iisrearc\core\webhost_pm\webhost_protocol_manager.cxx`
- `0x180002407`: `servercommon\inetsrv\iis\iisrearc\core\webhost_pm\webhost_protocol_manager.cxx`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::InitializeInstance(
        WEBHOST_PROTOCOL_MANAGER *this,
        struct IWorkerProcessFramework *a2)
{
  char *v4; // rbx
  signed int PMHFromISAPI; // ebx
  signed int LastError; // eax
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  __int64 v9; // r8
  const char *v10; // rax

  *((_QWORD *)this + 8) = a2;
  v4 = (char *)operator new(0x48u);
  if ( v4 )
  {
    *((_DWORD *)v4 + 3) = 1;
    *(_QWORD *)v4 = &PMH_PING_CALLBACK::`vftable';
    *((_QWORD *)v4 + 2) = 0;
    *((_DWORD *)v4 + 6) = 0;
    *((_DWORD *)v4 + 2) = 1129072720;
  }
  else
  {
    v4 = 0;
  }
  *((_QWORD *)this + 12) = v4;
  if ( !v4 )
    return (unsigned int)-2147024882;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v4 + 32), 0x3E8u) )
  {
    *((_DWORD *)v4 + 6) = 1;
  }
  else
  {
    LastError = GetLastError();
    PMHFromISAPI = LastError;
    if ( LastError > 0 )
      PMHFromISAPI = (unsigned __int16)LastError | 0x80070000;
    if ( PMHFromISAPI < 0 )
      return (unsigned int)PMHFromISAPI;
  }
  v7 = operator new(0xF0u);
  v8 = v7;
  if ( v7 )
  {
    v7[5] = 1;
    *(_QWORD *)v7 = &PMH_SUPPORT_FCNS::`vftable'{for `IProcessHostSupportFunctions'};
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 1) = &PMH_SUPPORT_FCNS::`vftable'{for `IApplicationPreloadUtil'};
    *((_QWORD *)v7 + 4) = 0;
    *((_QWORD *)v7 + 6) = 0;
    STRU::STRU((STRU *)(v7 + 16));
    STRU::STRU((STRU *)(v8 + 30));
    *((_QWORD *)v8 + 22) = 0;
    *((_QWORD *)v8 + 23) = 0;
    *((_QWORD *)v8 + 29) = 0;
    v8[4] = 1179863120;
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 13) = v8;
  if ( v8 )
  {
    PMHFromISAPI = PMH_SUPPORT_FCNS::InitializeInstance((PMH_SUPPORT_FCNS *)v8, a2, this);
    if ( PMHFromISAPI >= 0 )
    {
      PMHFromISAPI = WEBHOST_PROTOCOL_MANAGER::GetPMHFromISAPI(this);
      if ( PMHFromISAPI >= 0 || (g_dwDebugFlags & 3) == 0 )
        return (unsigned int)PMHFromISAPI;
      v9 = 514;
      v10 = "Error calling GetPMHFromISAPI().  Error = %x\n";
    }
    else
    {
      if ( (g_dwDebugFlags & 3) == 0 )
        return (unsigned int)PMHFromISAPI;
      v9 = 499;
      v10 = "Error initializing support functions.  Error = %x\n";
    }
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\webhost_pm\\webhost_protocol_manager.cxx",
      v9,
      "WEBHOST_PROTOCOL_MANAGER::InitializeInstance",
      v10);
    return (unsigned int)PMHFromISAPI;
  }
  PMHFromISAPI = -2147024882;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\webhost_pm\\webhost_protocol_manager.cxx",
      488,
      "WEBHOST_PROTOCOL_MANAGER::InitializeInstance",
      "Error allocating memory for the support functions.  \n");
  return (unsigned int)PMHFromISAPI;
}

```

## disassembly

```asm
0x180002230  mov     [rsp+arg_0], rbx
0x180002235  mov     [rsp+arg_8], rsi
0x18000223a  push    rdi
0x18000223b  sub     rsp, 30h
0x18000223f  mov     rdi, rcx
0x180002242  mov     [rcx+40h], rdx
0x180002246  mov     ecx, 48h ; 'H'; Size
0x18000224b  mov     rsi, rdx
0x18000224e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002253  mov     rbx, rax
0x180002256  test    rax, rax
0x180002259  jz      short loc_180002284
0x18000225b  lea     rax, ??_7PMH_PING_CALLBACK@@6B@; const PMH_PING_CALLBACK::`vftable'
0x180002262  mov     dword ptr [rbx+0Ch], 1
0x180002269  mov     [rbx], rax
0x18000226c  mov     qword ptr [rbx+10h], 0
0x180002274  mov     dword ptr [rbx+18h], 0
0x18000227b  mov     dword ptr [rbx+8], 434C4850h
0x180002282  jmp     short loc_180002286
0x180002284  xor     ebx, ebx
0x180002286  mov     [rdi+60h], rbx
0x18000228a  test    rbx, rbx
0x18000228d  jnz     short loc_180002299
0x18000228f  mov     ebx, 8007000Eh
0x180002294  jmp     loc_180002419
0x180002299  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000229d  mov     edx, 3E8h; dwSpinCount
0x1800022a2  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800022a8  test    eax, eax
0x1800022aa  jnz     short loc_1800022CA
0x1800022ac  call    cs:__imp_GetLastError
0x1800022b2  mov     ebx, eax
0x1800022b4  test    eax, eax
0x1800022b6  jle     short loc_1800022C1
0x1800022b8  movzx   ebx, ax
0x1800022bb  or      ebx, 80070000h
0x1800022c1  test    ebx, ebx
0x1800022c3  jns     short loc_1800022D1
0x1800022c5  jmp     loc_180002419
0x1800022ca  mov     dword ptr [rbx+18h], 1
0x1800022d1  mov     ecx, 0F0h; Size
0x1800022d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800022db  mov     rbx, rax
0x1800022de  test    rax, rax
0x1800022e1  jz      short loc_180002355
0x1800022e3  lea     rax, ??_7PMH_SUPPORT_FCNS@@6BIProcessHostSupportFunctions@@@; const PMH_SUPPORT_FCNS::`vftable'{for `IProcessHostSupportFunctions'}
0x1800022ea  mov     dword ptr [rbx+14h], 1
0x1800022f1  mov     [rbx], rax
0x1800022f4  lea     rcx, [rbx+40h]
0x1800022f8  lea     rax, ??_7PMH_SUPPORT_FCNS@@6BIApplicationPreloadUtil@@@; const PMH_SUPPORT_FCNS::`vftable'{for `IApplicationPreloadUtil'}
0x1800022ff  mov     qword ptr [rbx+18h], 0
0x180002307  mov     [rbx+8], rax
0x18000230b  mov     qword ptr [rbx+20h], 0
0x180002313  mov     qword ptr [rbx+30h], 0
0x18000231b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002321  lea     rcx, [rbx+78h]
0x180002325  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000232b  mov     qword ptr [rbx+0B0h], 0
0x180002336  mov     qword ptr [rbx+0B8h], 0
0x180002341  mov     qword ptr [rbx+0E8h], 0
0x18000234c  mov     dword ptr [rbx+10h], 46534850h
0x180002353  jmp     short loc_180002357
0x180002355  xor     ebx, ebx
0x180002357  mov     [rdi+68h], rbx
0x18000235b  test    rbx, rbx
0x18000235e  jnz     short loc_1800023A1
0x180002360  test    cs:g_dwDebugFlags, 3
0x180002367  mov     ebx, 8007000Eh
0x18000236c  jz      loc_180002419
0x180002372  mov     rcx, cs:g_pDebug
0x180002379  lea     rax, aErrorAllocatin; "Error allocating memory for the support"...
0x180002380  lea     r9, aWebhostProtoco; "WEBHOST_PROTOCOL_MANAGER::InitializeIns"...
0x180002387  mov     [rsp+38h+var_18], rax
0x18000238c  mov     r8d, 1E8h
0x180002392  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180002399  call    cs:__imp_PuDbgPrint
0x18000239f  jmp     short loc_180002419
0x1800023a1  mov     r8, rdi; struct IProtocolManager *
0x1800023a4  mov     rdx, rsi; struct IWorkerProcessFramework *
0x1800023a7  mov     rcx, rbx; this
0x1800023aa  call    ?InitializeInstance@PMH_SUPPORT_FCNS@@QEAAJPEAVIWorkerProcessFramework@@PEAVIProtocolManager@@@Z; PMH_SUPPORT_FCNS::InitializeInstance(IWorkerProcessFramework *,IProtocolManager *)
0x1800023af  mov     ebx, eax
0x1800023b1  test    eax, eax
0x1800023b3  jns     short loc_1800023D1
0x1800023b5  test    cs:g_dwDebugFlags, 3
0x1800023bc  jz      short loc_180002419
0x1800023be  mov     [rsp+38h+var_10], eax
0x1800023c2  mov     r8d, 1F3h
0x1800023c8  lea     rax, aErrorInitializ; "Error initializing support functions.  "...
0x1800023cf  jmp     short loc_1800023F9
0x1800023d1  mov     rcx, rdi; this
0x1800023d4  call    ?GetPMHFromISAPI@WEBHOST_PROTOCOL_MANAGER@@AEAAJXZ; WEBHOST_PROTOCOL_MANAGER::GetPMHFromISAPI(void)
0x1800023d9  mov     ebx, eax
0x1800023db  test    eax, eax
0x1800023dd  jns     short loc_180002419
0x1800023df  test    cs:g_dwDebugFlags, 3
0x1800023e6  jz      short loc_180002419
0x1800023e8  mov     [rsp+38h+var_10], eax
0x1800023ec  mov     r8d, 202h
0x1800023f2  lea     rax, aErrorCallingGe; "Error calling GetPMHFromISAPI().  Error"...
0x1800023f9  mov     rcx, cs:g_pDebug
0x180002400  lea     r9, aWebhostProtoco; "WEBHOST_PROTOCOL_MANAGER::InitializeIns"...
0x180002407  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000240e  mov     [rsp+38h+var_18], rax
0x180002413  call    cs:__imp_PuDbgPrint
0x180002419  mov     rsi, [rsp+38h+arg_8]
0x18000241e  mov     eax, ebx
0x180002420  mov     rbx, [rsp+38h+arg_0]
0x180002425  add     rsp, 30h
0x180002429  pop     rdi
0x18000242a  retn
```
