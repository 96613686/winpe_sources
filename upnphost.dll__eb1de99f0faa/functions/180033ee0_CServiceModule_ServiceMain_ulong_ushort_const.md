# CServiceModule::ServiceMain(ulong,ushort * * const)

- ea: `0x180033ee0`
- end: `0x180034020`
- name: `?ServiceMain@CServiceModule@@QEAAXKQEAPEAG@Z`
- size: `320`
- prototype: `void __fastcall(CServiceModule *__hidden this, unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18003ba60`

## callees

- `0x18001347c`
- `0x180030c3c`
- `0x180033b14`
- `0x180033ee0`
- `0x180038ce4`
- `0x180039094`
- `0x180039298`
- `0x18003ecb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f92`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180033f57`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180033f57`
- `api-ms-win-core-processthreads-l1-1-2!SetProtectedPolicy` at `0x180033f88`
- `api-ms-win-core-processthreads-l1-1-2!SetProtectedPolicy` at `0x180033f88`

## pseudocode

```c
void __fastcall CServiceModule::ServiceMain(CServiceModule *this, __int64 a2, unsigned __int16 **const a3)
{
  CServiceModule *v3; // rcx
  signed int Win32Error; // eax
  bool v5; // zf
  STRSAFE_PCNZWCH v6; // rcx
  __int64 v7; // rdx

  xmmword_180071C28 = 0;
  LODWORD(xmmword_180071C28) = 32;
  *(__int128 *)((char *)&xmmword_180071C28 + 12) = 0;
  DWORD2(xmmword_180071C28) = 0;
  qword_180071A18 = 0;
  WPP_MAIN_CB = 0;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_GLOBAL_Control = (STRSAFE_PCNZWCH)&WPP_MAIN_CB;
  qword_180071A20 = 1;
  WppInitUm(this, a2, a3);
  EnableMitigations();
  qword_180071C20 = (__int64)RegisterServiceCtrlHandlerExW(
                               L"upnphost",
                               (LPHANDLER_FUNCTION_EX)CServiceModule::_DwHandler,
                               0);
  if ( !qword_180071C20 )
  {
    if ( !(unsigned int)HrFromLastWin32Error()
      || WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[14] & 1) == 0 )
    {
      goto LABEL_15;
    }
    Win32Error = HrFromLastWin32Error();
    v6 = WPP_GLOBAL_Control;
    v7 = 31;
    goto LABEL_14;
  }
  CServiceModule::SetServiceStatus((CServiceModule *)&_Module, 2u);
  if ( (unsigned int)SetProtectedPolicy(qword_180064C18, 1) )
    goto LABEL_9;
  Win32Error = GetLastError();
  v5 = Win32Error == 0;
  if ( Win32Error > 0 )
  {
    Win32Error = (unsigned __int16)Win32Error | 0x80070000;
    v5 = Win32Error == 0;
  }
  if ( v5 )
  {
LABEL_9:
    CServiceModule::Run(v3);
    return;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v7 = 30;
LABEL_14:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, (unsigned int)Win32Error);
  }
LABEL_15:
  WppCleanupUm();
}

```

## disassembly

```asm
0x180033ee0  sub     rsp, 28h
0x180033ee4  xorps   xmm0, xmm0
0x180033ee7  xor     eax, eax
0x180033ee9  movups  cs:xmmword_180071C28, xmm0
0x180033ef0  mov     dword ptr cs:xmmword_180071C28, 20h ; ' '
0x180033efa  movups  cs:xmmword_180071C28+0Ch, xmm0
0x180033f01  mov     dword ptr cs:xmmword_180071C28+8, eax
0x180033f07  mov     cs:qword_180071A18, rax
0x180033f0e  mov     cs:WPP_MAIN_CB, rax
0x180033f15  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x180033f1c  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180033f23  lea     rax, WPP_MAIN_CB
0x180033f2a  mov     cs:WPP_GLOBAL_Control, rax
0x180033f31  mov     cs:qword_180071A20, 1
0x180033f3c  call    WppInitUm
0x180033f41  call    ?EnableMitigations@@YAXXZ; EnableMitigations(void)
0x180033f46  xor     r8d, r8d; lpContext
0x180033f49  lea     rdx, ?_DwHandler@CServiceModule@@CAKKKPEAX0@Z; lpHandlerProc
0x180033f50  lea     rcx, ServiceName; "upnphost"
0x180033f57  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180033f5d  mov     cs:qword_180071C20, rax
0x180033f64  test    rax, rax
0x180033f67  jz      short loc_180033FD1
0x180033f69  mov     edx, 2; unsigned int
0x180033f6e  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x180033f75  call    ?SetServiceStatus@CServiceModule@@QEAAXK@Z; CServiceModule::SetServiceStatus(ulong)
0x180033f7a  xor     r8d, r8d
0x180033f7d  lea     rcx, qword_180064C18
0x180033f84  lea     edx, [r8+1]
0x180033f88  call    cs:__imp_SetProtectedPolicy
0x180033f8e  test    eax, eax
0x180033f90  jnz     short loc_180033FC8
0x180033f92  call    cs:__imp_GetLastError
0x180033f98  test    eax, eax
0x180033f9a  jle     short loc_180033FA6
0x180033f9c  movzx   eax, ax
0x180033f9f  or      eax, 80070000h
0x180033fa4  test    eax, eax
0x180033fa6  jz      short loc_180033FC8
0x180033fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180033faf  lea     rdx, WPP_GLOBAL_Control
0x180033fb6  cmp     rcx, rdx
0x180033fb9  jz      short loc_180034017
0x180033fbb  test    byte ptr [rcx+1Ch], 1
0x180033fbf  jz      short loc_180034017
0x180033fc1  mov     edx, 1Eh
0x180033fc6  jmp     short loc_180034004
0x180033fc8  add     rsp, 28h
0x180033fcc  jmp     ?Run@CServiceModule@@QEAAXXZ; CServiceModule::Run(void)
0x180033fd1  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180033fd6  test    eax, eax
0x180033fd8  jz      short loc_180034017
0x180033fda  mov     rax, cs:WPP_GLOBAL_Control
0x180033fe1  lea     rdx, WPP_GLOBAL_Control
0x180033fe8  cmp     rax, rdx
0x180033feb  jz      short loc_180034017
0x180033fed  test    byte ptr [rax+1Ch], 1
0x180033ff1  jz      short loc_180034017
0x180033ff3  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180033ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x180033fff  mov     edx, 1Fh
0x180034004  mov     rcx, [rcx+10h]
0x180034008  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x18003400f  mov     r9d, eax
0x180034012  call    WPP_SF_d
0x180034017  add     rsp, 28h
0x18003401b  jmp     WppCleanupUm
```
