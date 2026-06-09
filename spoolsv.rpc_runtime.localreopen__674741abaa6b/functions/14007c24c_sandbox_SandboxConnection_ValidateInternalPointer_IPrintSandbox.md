# sandbox::SandboxConnection::ValidateInternalPointer(IPrintSandbox * *)

- ea: `0x14007c24c`
- end: `0x14007c634`
- name: `?ValidateInternalPointer@SandboxConnection@sandbox@@AEAAJPEAPEAUIPrintSandbox@@@Z`
- size: `1000`
- prototype: `__int64 __fastcall(sandbox::SandboxConnection *__hidden this, struct IPrintSandbox **)`
- caller_count: `9`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14007b880`
- `0x14007b910`
- `0x14007b9d0`
- `0x14007baf0`
- `0x14007bbf0`
- `0x14007bcf0`
- `0x14007bdb0`
- `0x14007c000`
- `0x14007c120`

## callees

- `0x140010c4c`
- `0x140016120`
- `0x140018d3c`
- `0x140063234`
- `0x14007a128`
- `0x14007a1d4`
- `0x14007c24c`
- `0x14007cf10`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14007c37e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14007c397`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14007c37e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14007c397`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007c2c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007c5fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007c2c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007c5fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14007c27f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14007c54f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14007c27f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14007c54f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14007c29a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14007c586`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14007c29a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14007c586`
- `KERNEL32!FreeLibrary` at `0x14007c433`
- `KERNEL32!FreeLibrary` at `0x14007c433`
- `KERNEL32!LoadLibraryExW` at `0x14007c341`
- `KERNEL32!LoadLibraryExW` at `0x14007c341`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14007c30c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14007c30c`

## string_xrefs

- `0x14007c5b9`: `A sandbox host is going to be recycled because of policies. m_dwObjectsCreated %u m_dwTimeBeforeRecycle %u`
- `0x14007c374`: `CreateBindCtx`
- `0x14007c334`: `ole32.dll`
- `0x14007c3e6`: `Session:%u!clsid:E7B3C0E0-FB47-49F6-A66B-8A7C2E4E7B9C`
- `0x14007c536`: `SetComSecurityBlanket failed: hr: 0x%x`

## pseudocode

```c
__int64 __fastcall sandbox::SandboxConnection::ValidateInternalPointer(
        sandbox::SandboxConnection *this,
        struct IPrintSandbox **a2)
{
  HRESULT Instance; // edi
  struct IPrintSandbox **v3; // r15
  struct _RTL_CRITICAL_SECTION *v5; // r13
  struct IPrintSandbox **v6; // r14
  int v7; // r8d
  NCoreLibrary *v8; // rcx
  HMODULE Library; // r15
  unsigned __int16 *v10; // rbx
  FARPROC ProcAddress; // rbx
  FARPROC v12; // rax
  NCoreLibrary *v13; // rcx
  __int64 (__fastcall *v14)(__int64, unsigned __int16 *, unsigned __int16 **, NCoreLibrary::TString **); // r12
  int v15; // eax
  int v16; // eax
  NCoreLibrary::TString *v17; // rcx
  int v18; // eax
  struct IUnknown *v19; // rdx
  int v20; // eax
  sandbox *v21; // rbx
  __int64 v23; // [rsp+30h] [rbp-28h] BYREF
  sandbox *v24; // [rsp+38h] [rbp-20h] BYREF
  LPVOID ppv[3]; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int16 *v26; // [rsp+A0h] [rbp+48h] BYREF
  struct IPrintSandbox **v27; // [rsp+A8h] [rbp+50h]
  __int64 v28; // [rsp+B0h] [rbp+58h] BYREF
  NCoreLibrary::TString *v29; // [rsp+B8h] [rbp+60h] BYREF

  v27 = a2;
  Instance = *((_DWORD *)this + 18);
  v3 = a2;
  if ( Instance < 0 )
  {
LABEL_50:
    SandboxTelemetry::WriteDbgTraceError(
      "sandbox::SandboxConnection::ValidateInternalPointer",
      L"Failed to get sandbox interface pointer. Error hr: 0x%x",
      (unsigned int)Instance);
    return (unsigned int)Instance;
  }
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( ++*((_DWORD *)this + 24) >= *((_DWORD *)this + 23)
    || GetTickCount() - *((_DWORD *)this + 25) >= *((_DWORD *)this + 22) )
  {
    Instance = -2147416390;
    SandboxTelemetry::WriteDbgTraceInfo(
      "sandbox::SandboxConnection::ValidateInternalPointer",
      L"A sandbox host is going to be recycled because of policies. m_dwObjectsCreated %u m_dwTimeBeforeRecycle %u",
      *((unsigned int *)this + 24),
      *((unsigned int *)this + 22));
    v6 = (struct IPrintSandbox **)((char *)this + 80);
    goto LABEL_46;
  }
  v6 = (struct IPrintSandbox **)((char *)this + 80);
  if ( !*((_QWORD *)this + 10) )
  {
    LeaveCriticalSection(v5);
    SandboxTelemetry::WriteDbgTraceInfo(
      "sandbox::SandboxConnection::ValidateInternalPointer",
      L"Sandbox interface pointer is NULL. Recreating sandbox object");
    v7 = *((_DWORD *)this + 26);
    ppv[0] = 0;
    if ( !v7 )
    {
      Instance = CoCreateInstance(&CLSID_CoPrintIsolationHost, 0, 4u, &IID_IPrintSandboxFactory, ppv);
LABEL_33:
      v24 = 0;
      if ( Instance >= 0 )
      {
        v18 = (*(__int64 (__fastcall **)(LPVOID, sandbox **))(*(_QWORD *)ppv[0] + 24LL))(ppv[0], &v24);
        Instance = v18;
        if ( v18 >= 0 )
        {
          v20 = sandbox::SetComSecurityBlanket(v24, v19);
          Instance = v20;
          if ( v20 < 0 )
            SandboxTelemetry::WriteDbgTraceError(
              "sandbox::SandboxConnection::ValidateInternalPointer",
              L"SetComSecurityBlanket failed: hr: 0x%x",
              (unsigned int)v20);
        }
        else
        {
          SandboxTelemetry::WriteDbgTraceError(
            "sandbox::SandboxConnection::ValidateInternalPointer",
            L"GetPrintSandboxInterface failed: hr: 0x%x",
            (unsigned int)v18);
        }
      }
      EnterCriticalSection(v5);
      if ( Instance >= 0 && !*v6 )
      {
        v21 = 0;
        if ( v24 )
        {
          v21 = v24;
          v24 = 0;
        }
        NCoreLibrary::TGenericSP<IPrintProcessorQuery,NCoreLibrary::TRefPtrCOM<IPrintProcessorQuery>,IPrintProcessorQuery *,0,IPrintProcessorQuery const *>::Reset((char *)this + 80);
        *v6 = v21;
        *((_DWORD *)this + 24) = 0;
        *((_DWORD *)this + 25) = GetTickCount();
      }
      NCoreLibrary::TGenericSP<IPrintProcessorQuery,NCoreLibrary::TRefPtrCOM<IPrintProcessorQuery>,IPrintProcessorQuery *,0,IPrintProcessorQuery const *>::Reset(&v24);
      if ( ppv[0] )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
      goto LABEL_46;
    }
    SandboxTelemetry::WriteDbgTraceInfo(
      "sandbox::SandboxConnection::ValidateInternalPointer",
      L"Connecting to CoPrintIsolationSessionHost in session %u");
    Library = LoadLibraryExW(L"ole32.dll", 0, 0x800u);
    if ( Library || (Instance = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v8), Instance >= 0) )
    {
      ProcAddress = GetProcAddress(Library, "CreateBindCtx");
      v12 = GetProcAddress(Library, "MkParseDisplayName");
      v14 = (__int64 (__fastcall *)(__int64, unsigned __int16 *, unsigned __int16 **, NCoreLibrary::TString **))v12;
      if ( !ProcAddress || !v12 )
        Instance = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v13);
      v23 = 0;
      if ( Instance >= 0 )
        Instance = ((__int64 (__fastcall *)(_QWORD, __int64 *))ProcAddress)(0, &v23);
      v10 = &NCoreLibrary::TString::gszNullState;
      v26 = &NCoreLibrary::TString::gszNullState;
      if ( Instance >= 0 )
      {
        v15 = NCoreLibrary::TString::Format(
                (NCoreLibrary::TString *)&v26,
                L"Session:%u!clsid:E7B3C0E0-FB47-49F6-A66B-8A7C2E4E7B9C",
                *((unsigned int *)this + 26));
        v10 = v26;
        Instance = v15;
      }
      v29 = 0;
      if ( Instance >= 0 )
      {
        LODWORD(v26) = 0;
        Instance = v14(v23, v10, &v26, &v29);
      }
      if ( Library )
        FreeLibrary(Library);
      v28 = 0;
      if ( Instance < 0 )
        goto LABEL_28;
      v16 = (*(__int64 (__fastcall **)(NCoreLibrary::TString *, __int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v29 + 64LL))(
              v29,
              v23,
              0,
              &GUID_00000001_0000_0000_c000_000000000046,
              &v28);
      Instance = v16;
      if ( v16 >= 0 )
        (*(void (__fastcall **)(__int64, _QWORD, GUID *, LPVOID *))(*(_QWORD *)v28 + 24LL))(
          v28,
          0,
          &GUID_f47e1b73_d682_4715_a684_305ebffaafe2,
          ppv);
      else
        SandboxTelemetry::WriteDbgTraceError(
          "sandbox::SandboxConnection::ValidateInternalPointer",
          L"BindToObject failed: hr: 0x%x",
          (unsigned int)v16);
      if ( !v28 )
        goto LABEL_28;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    else
    {
      v23 = 0;
      v10 = &NCoreLibrary::TString::gszNullState;
      v29 = 0;
    }
    v28 = 0;
LABEL_28:
    v17 = v29;
    if ( v29 )
    {
      (*(void (__fastcall **)(NCoreLibrary::TString *))(*(_QWORD *)v29 + 16LL))(v29);
      v29 = 0;
    }
    NCoreLibrary::TString::vFree(v17, v10);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v3 = v27;
    goto LABEL_33;
  }
LABEL_46:
  if ( v3 && Instance >= 0 )
  {
    *v3 = *v6;
    (*(void (__fastcall **)(struct IPrintSandbox *))(*(_QWORD *)*v6 + 8LL))(*v6);
  }
  LeaveCriticalSection(v5);
  if ( Instance < 0 )
    goto LABEL_50;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x14007c24c  mov     [rsp-40h+arg_8], rdx
0x14007c251  push    rbp
0x14007c252  push    rbx
0x14007c253  push    rsi
0x14007c254  push    rdi
0x14007c255  push    r12
0x14007c257  push    r13
0x14007c259  push    r14
0x14007c25b  push    r15
0x14007c25d  mov     rbp, rsp
0x14007c260  sub     rsp, 58h
0x14007c264  mov     edi, [rcx+48h]
0x14007c267  xor     r12d, r12d
0x14007c26a  mov     r15, rdx
0x14007c26d  mov     rsi, rcx
0x14007c270  test    edi, edi
0x14007c272  js      loc_14007C60A
0x14007c278  lea     r13, [rcx+20h]
0x14007c27c  mov     rcx, r13; lpCriticalSection
0x14007c27f  call    cs:__imp_EnterCriticalSection
0x14007c286  nop     dword ptr [rax+rax+00h]
0x14007c28b  inc     dword ptr [rsi+60h]
0x14007c28e  mov     eax, [rsi+60h]
0x14007c291  cmp     eax, [rsi+5Ch]
0x14007c294  jnb     loc_14007C5B5
0x14007c29a  call    cs:__imp_GetTickCount
0x14007c2a1  nop     dword ptr [rax+rax+00h]
0x14007c2a6  sub     eax, [rsi+64h]
0x14007c2a9  cmp     eax, [rsi+58h]
0x14007c2ac  jnb     loc_14007C5B5
0x14007c2b2  lea     r14, [rsi+50h]
0x14007c2b6  cmp     [r14], r12
0x14007c2b9  jnz     loc_14007C5D9
0x14007c2bf  mov     rcx, r13; lpCriticalSection
0x14007c2c2  call    cs:__imp_LeaveCriticalSection
0x14007c2c9  nop     dword ptr [rax+rax+00h]
0x14007c2ce  lea     rdx, aSandboxInterfa; "Sandbox interface pointer is NULL. Recr"...
0x14007c2d5  lea     rcx, aSandboxSandbox; "sandbox::SandboxConnection::ValidateInt"...
0x14007c2dc  call    ?WriteDbgTraceInfo@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14007c2e1  mov     r8d, [rsi+68h]
0x14007c2e5  mov     [rbp+var_18], r12
0x14007c2e9  test    r8d, r8d
0x14007c2ec  jnz     short loc_14007C31F
0x14007c2ee  lea     rax, [rbp+var_18]
0x14007c2f2  xor     edx, edx; pUnkOuter
0x14007c2f4  lea     r9, IID_IPrintSandboxFactory; riid
0x14007c2fb  mov     [rsp+58h+ppv], rax; ppv
0x14007c300  lea     r8d, [r12+4]; dwClsContext
0x14007c305  lea     rcx, CLSID_CoPrintIsolationHost; rclsid
0x14007c30c  call    cs:__imp_CoCreateInstance
0x14007c313  nop     dword ptr [rax+rax+00h]
0x14007c318  mov     edi, eax
0x14007c31a  jmp     loc_14007C4FC
0x14007c31f  lea     rdx, aConnectingToCo; "Connecting to CoPrintIsolationSessionHo"...
0x14007c326  lea     rcx, aSandboxSandbox; "sandbox::SandboxConnection::ValidateInt"...
0x14007c32d  call    ?WriteDbgTraceInfo@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14007c332  xor     edx, edx; hFile
0x14007c334  lea     rcx, aOle32Dll; "ole32.dll"
0x14007c33b  mov     r8d, 800h; dwFlags
0x14007c341  call    cs:__imp_LoadLibraryExW
0x14007c348  nop     dword ptr [rax+rax+00h]
0x14007c34d  mov     r15, rax
0x14007c350  test    rax, rax
0x14007c353  jnz     short loc_14007C374
0x14007c355  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14007c35a  mov     edi, eax
0x14007c35c  test    eax, eax
0x14007c35e  jns     short loc_14007C374
0x14007c360  mov     [rbp+var_28], r12
0x14007c364  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x14007c36b  mov     [rbp+arg_18], r12
0x14007c36f  jmp     loc_14007C4BE
0x14007c374  lea     rdx, aCreatebindctx; "CreateBindCtx"
0x14007c37b  mov     rcx, r15; hModule
0x14007c37e  call    cs:__imp_GetProcAddress
0x14007c385  nop     dword ptr [rax+rax+00h]
0x14007c38a  lea     rdx, aMkparsedisplay; "MkParseDisplayName"
0x14007c391  mov     rcx, r15; hModule
0x14007c394  mov     rbx, rax
0x14007c397  call    cs:__imp_GetProcAddress
0x14007c39e  nop     dword ptr [rax+rax+00h]
0x14007c3a3  mov     r12, rax
0x14007c3a6  test    rbx, rbx
0x14007c3a9  jz      short loc_14007C3B0
0x14007c3ab  test    rax, rax
0x14007c3ae  jnz     short loc_14007C3B7
0x14007c3b0  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14007c3b5  mov     edi, eax
0x14007c3b7  mov     [rbp+var_28], 0
0x14007c3bf  test    edi, edi
0x14007c3c1  js      short loc_14007C3D3
0x14007c3c3  lea     rdx, [rbp+var_28]
0x14007c3c7  xor     ecx, ecx
0x14007c3c9  mov     rax, rbx
0x14007c3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c3d1  mov     edi, eax
0x14007c3d3  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x14007c3da  mov     [rbp+arg_0], rbx
0x14007c3de  test    edi, edi
0x14007c3e0  js      short loc_14007C3FC
0x14007c3e2  mov     r8d, [rsi+68h]
0x14007c3e6  lea     rdx, aSessionUClsidE; "Session:%u!clsid:E7B3C0E0-FB47-49F6-A66"...
0x14007c3ed  lea     rcx, [rbp+arg_0]; this
0x14007c3f1  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x14007c3f6  mov     rbx, [rbp+arg_0]
0x14007c3fa  mov     edi, eax
0x14007c3fc  mov     [rbp+arg_18], 0
0x14007c404  test    edi, edi
0x14007c406  js      short loc_14007C428
0x14007c408  mov     rcx, [rbp+var_28]
0x14007c40c  lea     r9, [rbp+arg_18]
0x14007c410  lea     r8, [rbp+arg_0]
0x14007c414  mov     dword ptr [rbp+arg_0], 0
0x14007c41b  mov     rdx, rbx
0x14007c41e  mov     rax, r12
0x14007c421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c426  mov     edi, eax
0x14007c428  xor     r12d, r12d
0x14007c42b  test    r15, r15
0x14007c42e  jz      short loc_14007C43F
0x14007c430  mov     rcx, r15; hLibModule
0x14007c433  call    cs:__imp_FreeLibrary
0x14007c43a  nop     dword ptr [rax+rax+00h]
0x14007c43f  mov     [rbp+arg_10], r12
0x14007c443  test    edi, edi
0x14007c445  js      short loc_14007C4C2
0x14007c447  mov     rcx, [rbp+arg_18]
0x14007c44b  lea     rdx, [rbp+arg_10]
0x14007c44f  mov     [rsp+58h+ppv], rdx
0x14007c454  lea     r9, _GUID_00000001_0000_0000_c000_000000000046
0x14007c45b  mov     rdx, [rbp+var_28]
0x14007c45f  xor     r8d, r8d
0x14007c462  mov     rax, [rcx]
0x14007c465  mov     rax, [rax+40h]
0x14007c469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c46e  mov     edi, eax
0x14007c470  test    eax, eax
0x14007c472  jns     short loc_14007C48C
0x14007c474  mov     r8d, eax
0x14007c477  lea     rdx, aBindtoobjectFa; "BindToObject failed: hr: 0x%x"
0x14007c47e  lea     rcx, aSandboxSandbox; "sandbox::SandboxConnection::ValidateInt"...
0x14007c485  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14007c48a  jmp     short loc_14007C4A9
0x14007c48c  mov     rcx, [rbp+arg_10]
0x14007c490  lea     r9, [rbp+var_18]
0x14007c494  lea     r8, _GUID_f47e1b73_d682_4715_a684_305ebffaafe2
0x14007c49b  xor     edx, edx
0x14007c49d  mov     rax, [rcx]
0x14007c4a0  mov     rax, [rax+18h]
0x14007c4a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c4a9  mov     rcx, [rbp+arg_10]
0x14007c4ad  test    rcx, rcx
0x14007c4b0  jz      short loc_14007C4C2
0x14007c4b2  mov     rax, [rcx]
0x14007c4b5  mov     rax, [rax+10h]
0x14007c4b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c4be  mov     [rbp+arg_10], r12
0x14007c4c2  mov     rcx, [rbp+arg_18]
0x14007c4c6  test    rcx, rcx
0x14007c4c9  jz      short loc_14007C4DB
0x14007c4cb  mov     rax, [rcx]
0x14007c4ce  mov     rax, [rax+10h]
0x14007c4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c4d7  mov     [rbp+arg_18], r12
0x14007c4db  mov     rdx, rbx; void *
0x14007c4de  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x14007c4e3  mov     rcx, [rbp+var_28]
0x14007c4e7  test    rcx, rcx
0x14007c4ea  jz      short loc_14007C4F8
0x14007c4ec  mov     rax, [rcx]
0x14007c4ef  mov     rax, [rax+10h]
0x14007c4f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c4f8  mov     r15, [rbp+arg_8]
0x14007c4fc  mov     [rbp+var_20], r12
0x14007c500  test    edi, edi
0x14007c502  js      short loc_14007C54C
0x14007c504  mov     rcx, [rbp+var_18]
0x14007c508  lea     rdx, [rbp+var_20]
0x14007c50c  mov     rax, [rcx]
0x14007c50f  mov     rax, [rax+18h]
0x14007c513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c518  mov     edi, eax
0x14007c51a  test    eax, eax
0x14007c51c  jns     short loc_14007C527
0x14007c51e  lea     rdx, aGetprintsandbo; "GetPrintSandboxInterface failed: hr: 0x"...
0x14007c525  jmp     short loc_14007C53D
0x14007c527  mov     rcx, [rbp+var_20]; this
0x14007c52b  call    ?SetComSecurityBlanket@sandbox@@YAJPEAUIUnknown@@@Z; sandbox::SetComSecurityBlanket(IUnknown *)
0x14007c530  mov     edi, eax
0x14007c532  test    eax, eax
0x14007c534  jns     short loc_14007C54C
0x14007c536  lea     rdx, aSetcomsecurity; "SetComSecurityBlanket failed: hr: 0x%x"
0x14007c53d  mov     r8d, eax
0x14007c540  lea     rcx, aSandboxSandbox; "sandbox::SandboxConnection::ValidateInt"...
0x14007c547  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14007c54c  mov     rcx, r13; lpCriticalSection
0x14007c54f  call    cs:__imp_EnterCriticalSection
0x14007c556  nop     dword ptr [rax+rax+00h]
0x14007c55b  test    edi, edi
0x14007c55d  js      short loc_14007C595
0x14007c55f  cmp     [r14], r12
0x14007c562  jnz     short loc_14007C595
0x14007c564  mov     rax, [rbp+var_20]
0x14007c568  mov     rbx, r12
0x14007c56b  test    rax, rax
0x14007c56e  jz      short loc_14007C577
0x14007c570  mov     rbx, rax
0x14007c573  mov     [rbp+var_20], r12
0x14007c577  mov     rcx, r14
0x14007c57a  call    ?Reset@?$TGenericSP@UIPrintProcessorQuery@@V?$TRefPtrCOM@UIPrintProcessorQuery@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<IPrintProcessorQuery,NCoreLibrary::TRefPtrCOM<IPrintProcessorQuery>,IPrintProcessorQuery *,0,IPrintProcessorQuery const *>::Reset(void)
0x14007c57f  mov     [r14], rbx
0x14007c582  mov     [rsi+60h], r12d
0x14007c586  call    cs:__imp_GetTickCount
0x14007c58d  nop     dword ptr [rax+rax+00h]
0x14007c592  mov     [rsi+64h], eax
0x14007c595  lea     rcx, [rbp+var_20]
0x14007c599  call    ?Reset@?$TGenericSP@UIPrintProcessorQuery@@V?$TRefPtrCOM@UIPrintProcessorQuery@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<IPrintProcessorQuery,NCoreLibrary::TRefPtrCOM<IPrintProcessorQuery>,IPrintProcessorQuery *,0,IPrintProcessorQuery const *>::Reset(void)
0x14007c59e  mov     rcx, [rbp+var_18]
0x14007c5a2  test    rcx, rcx
0x14007c5a5  jz      short loc_14007C5D9
0x14007c5a7  mov     rax, [rcx]
0x14007c5aa  mov     rax, [rax+10h]
0x14007c5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c5b3  jmp     short loc_14007C5D9
0x14007c5b5  mov     r9d, [rsi+58h]
0x14007c5b9  lea     rdx, aASandboxHostIs; "A sandbox host is going to be recycled "...
0x14007c5c0  mov     r8d, [rsi+60h]
0x14007c5c4  lea     rcx, aSandboxSandbox; "sandbox::SandboxConnection::ValidateInt"...
0x14007c5cb  mov     edi, 800106BAh
0x14007c5d0  call    ?WriteDbgTraceInfo@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14007c5d5  lea     r14, [rsi+50h]
0x14007c5d9  test    r15, r15
0x14007c5dc  jz      short loc_14007C5F7
0x14007c5de  test    edi, edi
0x14007c5e0  js      short loc_14007C5F7
0x14007c5e2  mov     rax, [r14]
0x14007c5e5  mov     [r15], rax
0x14007c5e8  mov     rcx, [r14]
0x14007c5eb  mov     rax, [rcx]
0x14007c5ee  mov     rax, [rax+8]
0x14007c5f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c5f7  mov     rcx, r13; lpCriticalSection
0x14007c5fa  call    cs:__imp_LeaveCriticalSection
0x14007c601  nop     dword ptr [rax+rax+00h]
0x14007c606  test    edi, edi
0x14007c608  jns     short loc_14007C620
0x14007c60a  mov     r8d, edi
0x14007c60d  lea     rdx, aFailedToGetSan; "Failed to get sandbox interface pointer"...
0x14007c614  lea     rcx, aSandboxSandbox; "sandbox::SandboxConnection::ValidateInt"...
0x14007c61b  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14007c620  mov     eax, edi
0x14007c622  add     rsp, 58h
0x14007c626  pop     r15
0x14007c628  pop     r14
0x14007c62a  pop     r13
0x14007c62c  pop     r12
0x14007c62e  pop     rdi
0x14007c62f  pop     rsi
0x14007c630  pop     rbx
0x14007c631  pop     rbp
0x14007c632  retn
```
