# TPrinterEventMgr::SpoolerPrinterEvent(ushort *,int,ulong,__int64,ulong *)

- ea: `0x14000ed78`
- end: `0x14000eee4`
- name: `?SpoolerPrinterEvent@TPrinterEventMgr@@QEAAHPEAGHK_JPEAK@Z`
- size: `364`
- prototype: `int(TPrinterEventMgr *__hidden this, unsigned __int16 *, int, unsigned int, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000e6a0`

## callees

- `0x140006894`
- `0x140007298`
- `0x1400085d8`
- `0x14000ed78`
- `0x14000f1e4`
- `0x140012f28`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000ee71`
- `KERNEL32!GetLastError` at `0x14000ee8c`
- `KERNEL32!GetLastError` at `0x14000eea9`
- `KERNEL32!GetLastError` at `0x14000ee71`
- `KERNEL32!GetLastError` at `0x14000ee8c`
- `KERNEL32!GetLastError` at `0x14000eea9`
- `KERNEL32!GetProcAddress` at `0x14000ee2e`
- `KERNEL32!GetProcAddress` at `0x14000ee2e`
- `KERNEL32!FreeLibrary` at `0x14000ee84`
- `KERNEL32!FreeLibrary` at `0x14000ee84`
- `WINSPOOL!OpenPrinterW` at `0x14000edff`
- `WINSPOOL!OpenPrinterW` at `0x14000edff`
- `WINSPOOL!ClosePrinter` at `0x14000eea1`
- `WINSPOOL!ClosePrinter` at `0x14000eea1`
- `RPCRT4!RpcRevertToSelf` at `0x14000eec1`
- `RPCRT4!RpcRevertToSelf` at `0x14000eec1`
- `RPCRT4!RpcImpersonateClient` at `0x14000eda3`
- `RPCRT4!RpcImpersonateClient` at `0x14000eda3`

## pseudocode

```c
__int64 __fastcall TPrinterEventMgr::SpoolerPrinterEvent(
        TPrinterEventMgr *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        unsigned int *a6)
{
  unsigned int v10; // edi
  NSecurityLibrary *v11; // rcx
  RPC_STATUS v12; // r10d
  TLoad64BitDllsMgr **v13; // rsi
  TPrinterDriver *v14; // rcx
  HMODULE PrinterDriver; // rax
  HMODULE v16; // rbx
  FARPROC ProcAddress; // rax
  HANDLE phPrinter[10]; // [rsp+38h] [rbp-50h] BYREF

  phPrinter[0] = 0;
  v10 = 0;
  v12 = RpcImpersonateClient(0);
  if ( v12 )
  {
    *a6 = v12;
  }
  else
  {
    if ( NSecurityLibrary::IsClientAppContainer(v11) )
    {
      SplWow64Telemetry::WriteDbgTraceError("TPrinterEventMgr::SpoolerPrinterEvent", L"called from AppContainer");
      *a6 = 5;
    }
    else
    {
      v13 = (TLoad64BitDllsMgr **)((char *)this + 56);
      phPrinter[2] = v13;
      TLoad64BitDllsMgr::IncUIRefCnt(*v13);
      if ( OpenPrinterW(a2, phPrinter, 0) )
      {
        PrinterDriver = (HMODULE)TPrinterDriver::LoadPrinterDriver(v14, phPrinter[0]);
        v16 = PrinterDriver;
        phPrinter[1] = PrinterDriver;
        if ( PrinterDriver )
        {
          ProcAddress = GetProcAddress(PrinterDriver, "DrvPrinterEvent");
          if ( ProcAddress )
            v10 = ((__int64 (__fastcall *)(unsigned __int16 *, _QWORD, _QWORD, __int64))ProcAddress)(a2, a3, a4, a5);
          else
            *a6 = GetLastError();
          FreeLibrary(v16);
        }
        else
        {
          *a6 = GetLastError();
        }
        ClosePrinter(phPrinter[0]);
      }
      else
      {
        *a6 = GetLastError();
      }
      TLoad64BitDllsMgr::DecUIRefCnt(*v13);
    }
    RpcRevertToSelf();
  }
  return v10;
}

```

## disassembly

```asm
0x14000ed78  push    rbx
0x14000ed7a  push    rsi
0x14000ed7b  push    rdi
0x14000ed7c  push    r12
0x14000ed7e  push    r14
0x14000ed80  push    r15
0x14000ed82  sub     rsp, 58h
0x14000ed86  mov     r15d, r9d
0x14000ed89  mov     r12d, r8d
0x14000ed8c  mov     r14, rdx
0x14000ed8f  mov     rsi, rcx
0x14000ed92  mov     [rsp+88h+phPrinter], 0
0x14000ed9b  xor     edi, edi
0x14000ed9d  mov     [rsp+88h+var_58], edi
0x14000eda1  xor     ecx, ecx; BindingHandle
0x14000eda3  call    cs:__imp_RpcImpersonateClient
0x14000eda9  mov     r10d, eax
0x14000edac  test    eax, eax
0x14000edae  jnz     loc_14000EEC9
0x14000edb4  call    ?IsClientAppContainer@NSecurityLibrary@@YA_NXZ; NSecurityLibrary::IsClientAppContainer(void)
0x14000edb9  test    al, al
0x14000edbb  jz      short loc_14000EDE3
0x14000edbd  lea     rdx, aCalledFromAppc; "called from AppContainer"
0x14000edc4  lea     rcx, aTprintereventm_0; "TPrinterEventMgr::SpoolerPrinterEvent"
0x14000edcb  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000edd0  mov     rax, [rsp+88h+arg_28]
0x14000edd8  mov     dword ptr [rax], 5
0x14000edde  jmp     loc_14000EEC1
0x14000ede3  add     rsi, 38h ; '8'
0x14000ede7  mov     [rsp+88h+var_40], rsi
0x14000edec  mov     rcx, [rsi]; this
0x14000edef  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x14000edf4  xor     r8d, r8d; pDefault
0x14000edf7  lea     rdx, [rsp+88h+phPrinter]; phPrinter
0x14000edfc  mov     rcx, r14; pPrinterName
0x14000edff  call    cs:__imp_OpenPrinterW
0x14000ee05  test    eax, eax
0x14000ee07  jz      loc_14000EEA9
0x14000ee0d  mov     rdx, [rsp+88h+phPrinter]; void *
0x14000ee12  call    ?LoadPrinterDriver@TPrinterDriver@@IEAAPEAXPEAX@Z; TPrinterDriver::LoadPrinterDriver(void *)
0x14000ee17  mov     rbx, rax
0x14000ee1a  mov     [rsp+88h+var_48], rax
0x14000ee1f  test    rax, rax
0x14000ee22  jz      short loc_14000EE8C
0x14000ee24  lea     rdx, aDrvprintereven; "DrvPrinterEvent"
0x14000ee2b  mov     rcx, rax; hModule
0x14000ee2e  call    cs:__imp_GetProcAddress
0x14000ee34  test    rax, rax
0x14000ee37  jz      short loc_14000EE71
0x14000ee39  mov     r9, [rsp+88h+arg_20]
0x14000ee41  mov     r8d, r15d
0x14000ee44  mov     edx, r12d
0x14000ee47  mov     rcx, r14
0x14000ee4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ee4f  mov     edi, eax
0x14000ee51  mov     [rsp+88h+var_58], eax
0x14000ee55  jmp     short loc_14000EE81
0x14000ee57  mov     rcx, [rsp+88h+arg_28]
0x14000ee5f  mov     [rcx], eax
0x14000ee61  mov     rbx, [rsp+88h+var_48]
0x14000ee66  mov     edi, [rsp+88h+var_58]
0x14000ee6a  mov     rsi, [rsp+88h+var_40]
0x14000ee6f  jmp     short loc_14000EE81
0x14000ee71  call    cs:__imp_GetLastError
0x14000ee77  mov     rcx, [rsp+88h+arg_28]
0x14000ee7f  mov     [rcx], eax
0x14000ee81  mov     rcx, rbx; hLibModule
0x14000ee84  call    cs:__imp_FreeLibrary
0x14000ee8a  jmp     short loc_14000EE9C
0x14000ee8c  call    cs:__imp_GetLastError
0x14000ee92  mov     rcx, [rsp+88h+arg_28]
0x14000ee9a  mov     [rcx], eax
0x14000ee9c  mov     rcx, [rsp+88h+phPrinter]; hPrinter
0x14000eea1  call    cs:__imp_ClosePrinter
0x14000eea7  jmp     short loc_14000EEB9
0x14000eea9  call    cs:__imp_GetLastError
0x14000eeaf  mov     rdx, [rsp+88h+arg_28]
0x14000eeb7  mov     [rdx], eax
0x14000eeb9  mov     rcx, [rsi]; this
0x14000eebc  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x14000eec1  call    cs:__imp_RpcRevertToSelf
0x14000eec7  jmp     short loc_14000EED4
0x14000eec9  mov     rax, [rsp+88h+arg_28]
0x14000eed1  mov     [rax], r10d
0x14000eed4  mov     eax, edi
0x14000eed6  add     rsp, 58h
0x14000eeda  pop     r15
0x14000eedc  pop     r14
0x14000eede  pop     r12
0x14000eee0  pop     rdi
0x14000eee1  pop     rsi
0x14000eee2  pop     rbx
0x14000eee3  retn
```
