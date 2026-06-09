# TPrintUIMgr::PrintUIMethod(char const *,void *,ushort const *,int,__int64,TPrintUIMgr::EPrintUIOp)

- ea: `0x14000f42c`
- end: `0x14000f5bc`
- name: `?PrintUIMethod@TPrintUIMgr@@QEAAKPEBDPEAXPEBGH_JW4EPrintUIOp@1@@Z`
- size: `400`
- prototype: `unsigned int __high(const char *, void *, const unsigned __int16 *, int, __int64, enum TPrintUIMgr::EPrintUIOp)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000ddd0`
- `0x14000dfe0`
- `0x14000e290`
- `0x14000e3c0`

## callees

- `0x140006894`
- `0x140007298`
- `0x140007d00`
- `0x1400085d8`
- `0x14000f3ec`
- `0x14000f400`
- `0x14000f42c`
- `0x140012f28`
- `0x140016010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000f580`
- `KERNEL32!SetLastError` at `0x14000f580`
- `KERNEL32!GetLastError` at `0x14000f4ed`
- `KERNEL32!GetLastError` at `0x14000f4ed`
- `KERNEL32!GetProcAddress` at `0x14000f4df`
- `KERNEL32!GetProcAddress` at `0x14000f4df`
- `KERNEL32!FreeLibrary` at `0x14000f4c0`
- `KERNEL32!FreeLibrary` at `0x14000f4c0`
- `KERNEL32!LoadLibraryExW` at `0x14000f4ad`
- `KERNEL32!LoadLibraryExW` at `0x14000f4ad`
- `RPCRT4!RpcRevertToSelf` at `0x14000f5a4`
- `RPCRT4!RpcRevertToSelf` at `0x14000f5a4`
- `RPCRT4!RpcImpersonateClient` at `0x14000f44a`
- `RPCRT4!RpcImpersonateClient` at `0x14000f44a`

## string_xrefs

- `0x14000f4a6`: `printui.dll`

## pseudocode

```c
__int64 __fastcall TPrintUIMgr::PrintUIMethod(
        __int64 a1,
        const CHAR *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  NSecurityLibrary *v10; // rcx
  DWORD LastError; // ebx
  FARPROC ProcAddress; // r14
  TLoad64BitDllsMgr **v13; // rdi
  HMODULE Library; // rsi
  HMODULE hLibModule[9]; // [rsp+30h] [rbp-48h] BYREF

  LastError = RpcImpersonateClient(0);
  if ( !LastError )
  {
    if ( NSecurityLibrary::IsClientAppContainer(v10) )
    {
      SplWow64Telemetry::WriteDbgTraceError("TPrintUIMgr::PrintUIMethod", L"called from AppContainer");
      LastError = 5;
    }
    else
    {
      NCoreLibrary::TAutoHandleHMODULE::TAutoHandleHMODULE((NCoreLibrary::TAutoHandleHMODULE *)hLibModule);
      ProcAddress = 0;
      v13 = (TLoad64BitDllsMgr **)(a1 + 48);
      hLibModule[1] = (HMODULE)v13;
      TLoad64BitDllsMgr::RefreshLifeSpan(*v13);
      Library = LoadLibraryExW(L"printui.dll", 0, 0x800u);
      if ( hLibModule[0] )
        FreeLibrary(hLibModule[0]);
      hLibModule[0] = Library;
      if ( !Library || (LastError = 0, (ProcAddress = GetProcAddress(Library, a2)) == 0) )
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 668;
      }
      if ( !LastError )
      {
        TLoad64BitDllsMgr::IncUIRefCnt(*v13);
        ((void (__fastcall *)(__int64, __int64, _QWORD, __int64))ProcAddress)(a3, a4, a5, a6);
        TLoad64BitDllsMgr::DecUIRefCnt(*v13);
      }
      NCoreLibrary::TAutoHandleHMODULE::~TAutoHandleHMODULE((NCoreLibrary::TAutoHandleHMODULE *)hLibModule);
    }
    RpcRevertToSelf();
  }
  return LastError;
}

```

## disassembly

```asm
0x14000f42c  push    rbx
0x14000f42e  push    rsi
0x14000f42f  push    rdi
0x14000f430  push    r12
0x14000f432  push    r13
0x14000f434  push    r14
0x14000f436  push    r15
0x14000f438  sub     rsp, 40h
0x14000f43c  mov     r12, r9
0x14000f43f  mov     r13, r8
0x14000f442  mov     r15, rdx
0x14000f445  mov     rdi, rcx
0x14000f448  xor     ecx, ecx; BindingHandle
0x14000f44a  call    cs:__imp_RpcImpersonateClient
0x14000f450  mov     ebx, eax
0x14000f452  test    eax, eax
0x14000f454  jnz     loc_14000F5AA
0x14000f45a  call    ?IsClientAppContainer@NSecurityLibrary@@YA_NXZ; NSecurityLibrary::IsClientAppContainer(void)
0x14000f45f  test    al, al
0x14000f461  jz      short loc_14000F480
0x14000f463  lea     rdx, aCalledFromAppc; "called from AppContainer"
0x14000f46a  lea     rcx, aTprintuimgrPri_2; "TPrintUIMgr::PrintUIMethod"
0x14000f471  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000f476  mov     ebx, 5
0x14000f47b  jmp     loc_14000F5A4
0x14000f480  lea     rcx, [rsp+78h+hLibModule]; this
0x14000f485  call    ??0TAutoHandleHMODULE@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TAutoHandleHMODULE::TAutoHandleHMODULE(void)
0x14000f48a  xor     r14d, r14d
0x14000f48d  add     rdi, 30h ; '0'
0x14000f491  mov     [rsp+78h+var_40], rdi
0x14000f496  mov     rcx, [rdi]; this
0x14000f499  call    ?RefreshLifeSpan@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::RefreshLifeSpan(void)
0x14000f49e  xor     edx, edx; hFile
0x14000f4a0  mov     r8d, 800h; dwFlags
0x14000f4a6  lea     rcx, aPrintuiDll; "printui.dll"
0x14000f4ad  call    cs:__imp_LoadLibraryExW
0x14000f4b3  mov     rsi, rax
0x14000f4b6  mov     rcx, [rsp+78h+hLibModule]; hLibModule
0x14000f4bb  test    rcx, rcx
0x14000f4be  jz      short loc_14000F4C6
0x14000f4c0  call    cs:__imp_FreeLibrary
0x14000f4c6  mov     [rsp+78h+hLibModule], rsi
0x14000f4cb  test    rsi, rsi
0x14000f4ce  jz      short loc_14000F4ED
0x14000f4d0  xor     ebx, ebx
0x14000f4d2  mov     [rsp+78h+arg_30], ebx
0x14000f4d9  mov     rdx, r15; lpProcName
0x14000f4dc  mov     rcx, rsi; hModule
0x14000f4df  call    cs:__imp_GetProcAddress
0x14000f4e5  mov     r14, rax
0x14000f4e8  test    rax, rax
0x14000f4eb  jnz     short loc_14000F506
0x14000f4ed  call    cs:__imp_GetLastError
0x14000f4f3  mov     ebx, eax
0x14000f4f5  mov     eax, 29Ch
0x14000f4fa  test    ebx, ebx
0x14000f4fc  cmovz   ebx, eax
0x14000f4ff  mov     [rsp+78h+arg_30], ebx
0x14000f506  test    ebx, ebx
0x14000f508  jnz     loc_14000F59A
0x14000f50e  mov     rcx, [rdi]; this
0x14000f511  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x14000f516  nop
0x14000f517  mov     r9, [rsp+78h+arg_28]
0x14000f51f  mov     r8d, [rsp+78h+arg_20]
0x14000f527  mov     rdx, r12
0x14000f52a  mov     rcx, r13
0x14000f52d  mov     rax, r14
0x14000f530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f535  jmp     short loc_14000F592
0x14000f537  mov     ebx, eax
0x14000f539  add     eax, 3FFFFF74h
0x14000f53e  cmp     eax, 0Ah
0x14000f541  jbe     short loc_14000F563
0x14000f543  cmp     ebx, 3E6h
0x14000f549  jz      short loc_14000F563
0x14000f54b  cmp     ebx, 6C6h
0x14000f551  jz      short loc_14000F563
0x14000f553  cmp     ebx, 80000002h
0x14000f559  jz      short loc_14000F563
0x14000f55b  cmp     ebx, 0C0000005h
0x14000f561  jnz     short loc_14000F568
0x14000f563  mov     ebx, 57h ; 'W'
0x14000f568  mov     r8d, ebx
0x14000f56b  lea     rdx, aFailedToCallPr; "Failed to call Print UI.  Exception hr:"...
0x14000f572  lea     rcx, aTprintuimgrPri_2; "TPrintUIMgr::PrintUIMethod"
0x14000f579  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000f57e  mov     ecx, ebx; dwErrCode
0x14000f580  call    cs:__imp_SetLastError
0x14000f586  mov     ebx, [rsp+78h+arg_30]
0x14000f58d  mov     rdi, [rsp+78h+var_40]
0x14000f592  mov     rcx, [rdi]; this
0x14000f595  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x14000f59a  lea     rcx, [rsp+78h+hLibModule]; this
0x14000f59f  call    ??1TAutoHandleHMODULE@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TAutoHandleHMODULE::~TAutoHandleHMODULE(void)
0x14000f5a4  call    cs:__imp_RpcRevertToSelf
0x14000f5aa  mov     eax, ebx
0x14000f5ac  add     rsp, 40h
0x14000f5b0  pop     r15
0x14000f5b2  pop     r14
0x14000f5b4  pop     r13
0x14000f5b6  pop     r12
0x14000f5b8  pop     rdi
0x14000f5b9  pop     rsi
0x14000f5ba  pop     rbx
0x14000f5bb  retn
```
