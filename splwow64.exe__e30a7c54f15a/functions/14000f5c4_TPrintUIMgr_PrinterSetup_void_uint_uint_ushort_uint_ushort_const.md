# TPrintUIMgr::PrinterSetup(void *,uint,uint,ushort *,uint *,ushort const *)

- ea: `0x14000f5c4`
- end: `0x14000f779`
- name: `?PrinterSetup@TPrintUIMgr@@QEAAKPEAXIIPEAGPEAIPEBG@Z`
- size: `437`
- prototype: `unsigned int __fastcall(TPrintUIMgr *__hidden this, void *, unsigned int, unsigned int, unsigned __int16 *, unsigned int *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000e110`

## callees

- `0x140006894`
- `0x140007298`
- `0x140007d00`
- `0x1400085d8`
- `0x14000f3ec`
- `0x14000f400`
- `0x14000f5c4`
- `0x140012e84`
- `0x140012f28`
- `0x140016010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000f740`
- `KERNEL32!SetLastError` at `0x14000f740`
- `KERNEL32!GetLastError` at `0x14000f68f`
- `KERNEL32!GetLastError` at `0x14000f6e9`
- `KERNEL32!GetLastError` at `0x14000f68f`
- `KERNEL32!GetLastError` at `0x14000f6e9`
- `KERNEL32!GetProcAddress` at `0x14000f681`
- `KERNEL32!GetProcAddress` at `0x14000f681`
- `KERNEL32!FreeLibrary` at `0x14000f661`
- `KERNEL32!FreeLibrary` at `0x14000f661`
- `KERNEL32!LoadLibraryExW` at `0x14000f64e`
- `KERNEL32!LoadLibraryExW` at `0x14000f64e`
- `RPCRT4!RpcRevertToSelf` at `0x14000f761`
- `RPCRT4!RpcRevertToSelf` at `0x14000f761`
- `RPCRT4!RpcImpersonateClient` at `0x14000f5e2`
- `RPCRT4!RpcImpersonateClient` at `0x14000f5e2`

## string_xrefs

- `0x14000f647`: `printui.dll`

## pseudocode

```c
__int64 __fastcall TPrintUIMgr::PrinterSetup(
        TPrintUIMgr *this,
        void *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int *a6,
        const unsigned __int16 *a7)
{
  NSecurityLibrary *v11; // rcx
  DWORD LastError; // ebx
  const unsigned __int16 *v13; // rdx
  NSecurityLibrary *v14; // rcx
  FARPROC ProcAddress; // r14
  TLoad64BitDllsMgr **v16; // rdi
  HMODULE Library; // rsi
  HMODULE hLibModule[10]; // [rsp+48h] [rbp-50h] BYREF

  LastError = RpcImpersonateClient(0);
  if ( !LastError )
  {
    if ( !NSecurityLibrary::IsClientAppContainer(v11) || NSecurityLibrary::HasCapability(v14, v13) )
    {
      NCoreLibrary::TAutoHandleHMODULE::TAutoHandleHMODULE((NCoreLibrary::TAutoHandleHMODULE *)hLibModule);
      ProcAddress = 0;
      v16 = (TLoad64BitDllsMgr **)((char *)this + 48);
      hLibModule[1] = (HMODULE)v16;
      TLoad64BitDllsMgr::RefreshLifeSpan(*v16);
      Library = LoadLibraryExW(L"printui.dll", 0, 0x800u);
      if ( hLibModule[0] )
        FreeLibrary(hLibModule[0]);
      hLibModule[0] = Library;
      if ( !Library || (LastError = 0, (ProcAddress = GetProcAddress(Library, "bPrinterSetup")) == 0) )
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 668;
      }
      if ( !LastError )
      {
        TLoad64BitDllsMgr::IncUIRefCnt(*v16);
        ((void (__fastcall *)(void *, _QWORD, _QWORD, unsigned __int16 *, unsigned int *, const unsigned __int16 *))ProcAddress)(
          a2,
          a3,
          a4,
          a5,
          a6,
          a7);
        LastError = GetLastError();
        TLoad64BitDllsMgr::DecUIRefCnt(*v16);
      }
      NCoreLibrary::TAutoHandleHMODULE::~TAutoHandleHMODULE((NCoreLibrary::TAutoHandleHMODULE *)hLibModule);
    }
    else
    {
      SplWow64Telemetry::WriteDbgTraceError("TPrintUIMgr::PrinterSetup", L"called from AppContainer");
      LastError = 5;
    }
    RpcRevertToSelf();
  }
  return LastError;
}

```

## disassembly

```asm
0x14000f5c4  push    rbx
0x14000f5c6  push    rsi
0x14000f5c7  push    rdi
0x14000f5c8  push    r12
0x14000f5ca  push    r13
0x14000f5cc  push    r14
0x14000f5ce  push    r15
0x14000f5d0  sub     rsp, 60h
0x14000f5d4  mov     r15d, r9d
0x14000f5d7  mov     r12d, r8d
0x14000f5da  mov     r13, rdx
0x14000f5dd  mov     rdi, rcx
0x14000f5e0  xor     ecx, ecx; BindingHandle
0x14000f5e2  call    cs:__imp_RpcImpersonateClient
0x14000f5e8  mov     ebx, eax
0x14000f5ea  test    eax, eax
0x14000f5ec  jnz     loc_14000F767
0x14000f5f2  call    ?IsClientAppContainer@NSecurityLibrary@@YA_NXZ; NSecurityLibrary::IsClientAppContainer(void)
0x14000f5f7  test    al, al
0x14000f5f9  jz      short loc_14000F621
0x14000f5fb  call    ?HasCapability@NSecurityLibrary@@YA_NPEBG@Z; NSecurityLibrary::HasCapability(ushort const *)
0x14000f600  test    al, al
0x14000f602  jnz     short loc_14000F621
0x14000f604  lea     rdx, aCalledFromAppc; "called from AppContainer"
0x14000f60b  lea     rcx, aTprintuimgrPri_0; "TPrintUIMgr::PrinterSetup"
0x14000f612  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000f617  mov     ebx, 5
0x14000f61c  jmp     loc_14000F761
0x14000f621  lea     rcx, [rsp+98h+hLibModule]; this
0x14000f626  call    ??0TAutoHandleHMODULE@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TAutoHandleHMODULE::TAutoHandleHMODULE(void)
0x14000f62b  xor     r14d, r14d
0x14000f62e  add     rdi, 30h ; '0'
0x14000f632  mov     [rsp+98h+var_48], rdi
0x14000f637  mov     rcx, [rdi]; this
0x14000f63a  call    ?RefreshLifeSpan@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::RefreshLifeSpan(void)
0x14000f63f  xor     edx, edx; hFile
0x14000f641  mov     r8d, 800h; dwFlags
0x14000f647  lea     rcx, aPrintuiDll; "printui.dll"
0x14000f64e  call    cs:__imp_LoadLibraryExW
0x14000f654  mov     rsi, rax
0x14000f657  mov     rcx, [rsp+98h+hLibModule]; hLibModule
0x14000f65c  test    rcx, rcx
0x14000f65f  jz      short loc_14000F667
0x14000f661  call    cs:__imp_FreeLibrary
0x14000f667  mov     [rsp+98h+hLibModule], rsi
0x14000f66c  test    rsi, rsi
0x14000f66f  jz      short loc_14000F68F
0x14000f671  xor     ebx, ebx
0x14000f673  mov     [rsp+98h+var_58], ebx
0x14000f677  lea     rdx, aBprintersetup; "bPrinterSetup"
0x14000f67e  mov     rcx, rsi; hModule
0x14000f681  call    cs:__imp_GetProcAddress
0x14000f687  mov     r14, rax
0x14000f68a  test    rax, rax
0x14000f68d  jnz     short loc_14000F6A5
0x14000f68f  call    cs:__imp_GetLastError
0x14000f695  mov     ebx, eax
0x14000f697  mov     eax, 29Ch
0x14000f69c  test    ebx, ebx
0x14000f69e  cmovz   ebx, eax
0x14000f6a1  mov     [rsp+98h+var_58], ebx
0x14000f6a5  test    ebx, ebx
0x14000f6a7  jnz     loc_14000F757
0x14000f6ad  mov     rcx, [rdi]; this
0x14000f6b0  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x14000f6b5  nop
0x14000f6b6  mov     rax, [rsp+98h+arg_30]
0x14000f6be  mov     [rsp+98h+var_70], rax
0x14000f6c3  mov     rax, [rsp+98h+arg_28]
0x14000f6cb  mov     [rsp+98h+var_78], rax
0x14000f6d0  mov     r9, [rsp+98h+arg_20]
0x14000f6d8  mov     r8d, r15d
0x14000f6db  mov     edx, r12d
0x14000f6de  mov     rcx, r13
0x14000f6e1  mov     rax, r14
0x14000f6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f6e9  call    cs:__imp_GetLastError
0x14000f6ef  mov     ebx, eax
0x14000f6f1  mov     [rsp+98h+var_58], eax
0x14000f6f5  jmp     short loc_14000F74F
0x14000f6f7  mov     ebx, eax
0x14000f6f9  add     eax, 3FFFFF74h
0x14000f6fe  cmp     eax, 0Ah
0x14000f701  jbe     short loc_14000F723
0x14000f703  cmp     ebx, 3E6h
0x14000f709  jz      short loc_14000F723
0x14000f70b  cmp     ebx, 6C6h
0x14000f711  jz      short loc_14000F723
0x14000f713  cmp     ebx, 80000002h
0x14000f719  jz      short loc_14000F723
0x14000f71b  cmp     ebx, 0C0000005h
0x14000f721  jnz     short loc_14000F728
0x14000f723  mov     ebx, 57h ; 'W'
0x14000f728  mov     r8d, ebx
0x14000f72b  lea     rdx, aFailedToCallPr; "Failed to call Print UI.  Exception hr:"...
0x14000f732  lea     rcx, aTprintuimgrPri_0; "TPrintUIMgr::PrinterSetup"
0x14000f739  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000f73e  mov     ecx, ebx; dwErrCode
0x14000f740  call    cs:__imp_SetLastError
0x14000f746  mov     ebx, [rsp+98h+var_58]
0x14000f74a  mov     rdi, [rsp+98h+var_48]
0x14000f74f  mov     rcx, [rdi]; this
0x14000f752  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x14000f757  lea     rcx, [rsp+98h+hLibModule]; this
0x14000f75c  call    ??1TAutoHandleHMODULE@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TAutoHandleHMODULE::~TAutoHandleHMODULE(void)
0x14000f761  call    cs:__imp_RpcRevertToSelf
0x14000f767  mov     eax, ebx
0x14000f769  add     rsp, 60h
0x14000f76d  pop     r15
0x14000f76f  pop     r14
0x14000f771  pop     r13
0x14000f773  pop     r12
0x14000f775  pop     rdi
0x14000f776  pop     rsi
0x14000f777  pop     rbx
0x14000f778  retn
```
