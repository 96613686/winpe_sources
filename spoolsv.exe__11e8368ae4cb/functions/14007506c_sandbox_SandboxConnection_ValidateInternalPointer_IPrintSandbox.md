# sandbox::SandboxConnection::ValidateInternalPointer(IPrintSandbox * *)

- ea: `0x14007506c`
- end: `0x140075411`
- name: `?ValidateInternalPointer@SandboxConnection@sandbox@@AEAAJPEAPEAUIPrintSandbox@@@Z`
- size: `933`
- prototype: `__int64 __fastcall(sandbox::SandboxConnection *__hidden this, struct IPrintSandbox **)`
- caller_count: `9`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400746c0`
- `0x140074750`
- `0x140074810`
- `0x140074930`
- `0x140074a30`
- `0x140074b30`
- `0x140074bf0`
- `0x140074e20`
- `0x140074f40`

## callees

- `0x14000fa4c`
- `0x140014e14`
- `0x140017894`
- `0x14005d618`
- `0x140073064`
- `0x14007310c`
- `0x14007506c`
- `0x140075cb0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140075180`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140075193`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140075180`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140075193`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400750d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400753de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400750d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400753de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14007509f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14007533f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14007509f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14007533f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400750b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140075370`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400750b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140075370`
- `KERNEL32!FreeLibrary` at `0x140075229`
- `KERNEL32!FreeLibrary` at `0x140075229`
- `KERNEL32!LoadLibraryExW` at `0x140075149`
- `KERNEL32!LoadLibraryExW` at `0x140075149`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14007511a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14007511a`

## string_xrefs

- `0x14007539d`: `A sandbox host is going to be recycled because of policies. m_dwObjectsCreated %u m_dwTimeBeforeRecycle %u`
- `0x14007513c`: `ole32.dll`
- `0x1400751dc`: `Session:%u!clsid:E7B3C0E0-FB47-49F6-A66B-8A7C2E4E7B9C`
- `0x140075176`: `CreateBindCtx`
- `0x140075326`: `SetComSecurityBlanket failed: hr: 0x%x`

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
0x14007506c  mov     [rsp-40h+arg_8], rdx
0x140075071  push    rbp
0x140075072  push    rbx
0x140075073  push    rsi
0x140075074  push    rdi
0x140075075  push    r12
0x140075077  push    r13
0x140075079  push    r14
0x14007507b  push    r15
0x14007507d  mov     rbp, rsp
0x140075080  sub     rsp, 58h
0x140075084  mov     edi, [rcx+48h]
0x140075087  xor     r12d, r12d
0x14007508a  mov     r15, rdx
0x14007508d  mov     rsi, rcx
0x140075090  test    edi, edi
0x140075092  js      loc_1400753E8
0x140075098  lea     r13, [rcx+20h]
0x14007509c  mov     rcx, r13; lpCriticalSection
0x14007509f  call    cs:__imp_EnterCriticalSection
0x1400750a5  inc     dword ptr [rsi+60h]
0x1400750a8  mov     eax, [rsi+60h]
0x1400750ab  cmp     eax, [rsi+5Ch]
0x1400750ae  jnb     loc_140075399
0x1400750b4  call    cs:__imp_GetTickCount
0x1400750ba  sub     eax, [rsi+64h]
0x1400750bd  cmp     eax, [rsi+58h]
0x1400750c0  jnb     loc_140075399
0x1400750c6  lea     r14, [rsi+50h]
0x1400750ca  cmp     [r14], r12
0x1400750cd  jnz     loc_1400753BD
0x1400750d3  mov     rcx, r13; lpCriticalSection
0x1400750d6  call    cs:__imp_LeaveCriticalSection
0x1400750dc  lea     rdx, aSandboxInterfa; "Sandbox interface pointer is NULL. Recr"...
0x1400750e3  lea     rcx, aSandboxSandbox; "sandbox::SandboxConnection::ValidateInt"...
0x1400750ea  call    ?WriteDbgTraceInfo@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400750ef  mov     r8d, [rsi+68h]
0x1400750f3  mov     [rbp+var_18], r12
0x1400750f7  test    r8d, r8d
0x1400750fa  jnz     short loc_140075127
0x1400750fc  lea     rax, [rbp+var_18]
0x140075100  xor     edx, edx; pUnkOuter
0x140075102  lea     r9, IID_IPrintSandboxFactory; riid
0x140075109  mov     [rsp+58h+ppv], rax; ppv
0x14007510e  lea     r8d, [r12+4]; dwClsContext
0x140075113  lea     rcx, CLSID_CoPrintIsolationHost; rclsid
0x14007511a  call    cs:__imp_CoCreateInstance
0x140075120  mov     edi, eax
0x140075122  jmp     loc_1400752EC
0x140075127  lea     rdx, aConnectingToCo; "Connecting to CoPrintIsolationSessionHo"...
0x14007512e  lea     rcx, aSandboxSandbox; "sandbox::SandboxConnection::ValidateInt"...
0x140075135  call    ?WriteDbgTraceInfo@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14007513a  xor     edx, edx; hFile
0x14007513c  lea     rcx, aOle32Dll; "ole32.dll"
0x140075143  mov     r8d, 800h; dwFlags
0x140075149  call    cs:__imp_LoadLibraryExW
0x14007514f  mov     r15, rax
0x140075152  test    rax, rax
0x140075155  jnz     short loc_140075176
0x140075157  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14007515c  mov     edi, eax
0x14007515e  test    eax, eax
0x140075160  jns     short loc_140075176
0x140075162  mov     [rbp+var_28], r12
0x140075166  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x14007516d  mov     [rbp+arg_18], r12
0x140075171  jmp     loc_1400752AE
0x140075176  lea     rdx, aCreatebindctx; "CreateBindCtx"
0x14007517d  mov     rcx, r15; hModule
0x140075180  call    cs:__imp_GetProcAddress
0x140075186  lea     rdx, aMkparsedisplay; "MkParseDisplayName"
0x14007518d  mov     rcx, r15; hModule
0x140075190  mov     rbx, rax
0x140075193  call    cs:__imp_GetProcAddress
0x140075199  mov     r12, rax
0x14007519c  test    rbx, rbx
0x14007519f  jz      short loc_1400751A6
0x1400751a1  test    rax, rax
0x1400751a4  jnz     short loc_1400751AD
0x1400751a6  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1400751ab  mov     edi, eax
0x1400751ad  mov     [rbp+var_28], 0
0x1400751b5  test    edi, edi
0x1400751b7  js      short loc_1400751C9
0x1400751b9  lea     rdx, [rbp+var_28]
0x1400751bd  xor     ecx, ecx
0x1400751bf  mov     rax, rbx
0x1400751c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400751c7  mov     edi, eax
0x1400751c9  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x1400751d0  mov     [rbp+arg_0], rbx
0x1400751d4  test    edi, edi
0x1400751d6  js      short loc_1400751F2
0x1400751d8  mov     r8d, [rsi+68h]
0x1400751dc  lea     rdx, aSessionUClsidE; "Session:%u!clsid:E7B3C0E0-FB47-49F6-A66"...
0x1400751e3  lea     rcx, [rbp+arg_0]; this
0x1400751e7  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x1400751ec  mov     rbx, [rbp+arg_0]
0x1400751f0  mov     edi, eax
0x1400751f2  mov     [rbp+arg_18], 0
0x1400751fa  test    edi, edi
0x1400751fc  js      short loc_14007521E
0x1400751fe  mov     rcx, [rbp+var_28]
0x140075202  lea     r9, [rbp+arg_18]
0x140075206  lea     r8, [rbp+arg_0]
0x14007520a  mov     dword ptr [rbp+arg_0], 0
0x140075211  mov     rdx, rbx
0x140075214  mov     rax, r12
0x140075217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007521c  mov     edi, eax
0x14007521e  xor     r12d, r12d
0x140075221  test    r15, r15
0x140075224  jz      short loc_14007522F
0x140075226  mov     rcx, r15; hLibModule
0x140075229  call    cs:__imp_FreeLibrary
0x14007522f  mov     [rbp+arg_10], r12
0x140075233  test    edi, edi
0x140075235  js      short loc_1400752B2
0x140075237  mov     rcx, [rbp+arg_18]
0x14007523b  lea     rdx, [rbp+arg_10]
0x14007523f  mov     [rsp+58h+ppv], rdx
0x140075244  lea     r9, _GUID_00000001_0000_0000_c000_000000000046
0x14007524b  mov     rdx, [rbp+var_28]
0x14007524f  xor     r8d, r8d
0x140075252  mov     rax, [rcx]
0x140075255  mov     rax, [rax+40h]
0x140075259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007525e  mov     edi, eax
0x140075260  test    eax, eax
0x140075262  jns     short loc_14007527C
0x140075264  mov     r8d, eax
0x140075267  lea     rdx, aBindtoobjectFa; "BindToObject failed: hr: 0x%x"
0x14007526e  lea     rcx, aSandboxSandbox; "sandbox::SandboxConnection::ValidateInt"...
0x140075275  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14007527a  jmp     short loc_140075299
0x14007527c  mov     rcx, [rbp+arg_10]
0x140075280  lea     r9, [rbp+var_18]
0x140075284  lea     r8, _GUID_f47e1b73_d682_4715_a684_305ebffaafe2
0x14007528b  xor     edx, edx
0x14007528d  mov     rax, [rcx]
0x140075290  mov     rax, [rax+18h]
0x140075294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075299  mov     rcx, [rbp+arg_10]
0x14007529d  test    rcx, rcx
0x1400752a0  jz      short loc_1400752B2
0x1400752a2  mov     rax, [rcx]
0x1400752a5  mov     rax, [rax+10h]
0x1400752a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400752ae  mov     [rbp+arg_10], r12
0x1400752b2  mov     rcx, [rbp+arg_18]
0x1400752b6  test    rcx, rcx
0x1400752b9  jz      short loc_1400752CB
0x1400752bb  mov     rax, [rcx]
0x1400752be  mov     rax, [rax+10h]
0x1400752c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400752c7  mov     [rbp+arg_18], r12
0x1400752cb  mov     rdx, rbx; void *
0x1400752ce  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x1400752d3  mov     rcx, [rbp+var_28]
0x1400752d7  test    rcx, rcx
0x1400752da  jz      short loc_1400752E8
0x1400752dc  mov     rax, [rcx]
0x1400752df  mov     rax, [rax+10h]
0x1400752e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400752e8  mov     r15, [rbp+arg_8]
0x1400752ec  mov     [rbp+var_20], r12
0x1400752f0  test    edi, edi
0x1400752f2  js      short loc_14007533C
0x1400752f4  mov     rcx, [rbp+var_18]
0x1400752f8  lea     rdx, [rbp+var_20]
0x1400752fc  mov     rax, [rcx]
0x1400752ff  mov     rax, [rax+18h]
0x140075303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075308  mov     edi, eax
0x14007530a  test    eax, eax
0x14007530c  jns     short loc_140075317
0x14007530e  lea     rdx, aGetprintsandbo; "GetPrintSandboxInterface failed: hr: 0x"...
0x140075315  jmp     short loc_14007532D
0x140075317  mov     rcx, [rbp+var_20]; this
0x14007531b  call    ?SetComSecurityBlanket@sandbox@@YAJPEAUIUnknown@@@Z; sandbox::SetComSecurityBlanket(IUnknown *)
0x140075320  mov     edi, eax
0x140075322  test    eax, eax
0x140075324  jns     short loc_14007533C
0x140075326  lea     rdx, aSetcomsecurity; "SetComSecurityBlanket failed: hr: 0x%x"
0x14007532d  mov     r8d, eax
0x140075330  lea     rcx, aSandboxSandbox; "sandbox::SandboxConnection::ValidateInt"...
0x140075337  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14007533c  mov     rcx, r13; lpCriticalSection
0x14007533f  call    cs:__imp_EnterCriticalSection
0x140075345  test    edi, edi
0x140075347  js      short loc_140075379
0x140075349  cmp     [r14], r12
0x14007534c  jnz     short loc_140075379
0x14007534e  mov     rax, [rbp+var_20]
0x140075352  mov     rbx, r12
0x140075355  test    rax, rax
0x140075358  jz      short loc_140075361
0x14007535a  mov     rbx, rax
0x14007535d  mov     [rbp+var_20], r12
0x140075361  mov     rcx, r14
0x140075364  call    ?Reset@?$TGenericSP@UIPrintProcessorQuery@@V?$TRefPtrCOM@UIPrintProcessorQuery@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<IPrintProcessorQuery,NCoreLibrary::TRefPtrCOM<IPrintProcessorQuery>,IPrintProcessorQuery *,0,IPrintProcessorQuery const *>::Reset(void)
0x140075369  mov     [r14], rbx
0x14007536c  mov     [rsi+60h], r12d
0x140075370  call    cs:__imp_GetTickCount
0x140075376  mov     [rsi+64h], eax
0x140075379  lea     rcx, [rbp+var_20]
0x14007537d  call    ?Reset@?$TGenericSP@UIPrintProcessorQuery@@V?$TRefPtrCOM@UIPrintProcessorQuery@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<IPrintProcessorQuery,NCoreLibrary::TRefPtrCOM<IPrintProcessorQuery>,IPrintProcessorQuery *,0,IPrintProcessorQuery const *>::Reset(void)
0x140075382  mov     rcx, [rbp+var_18]
0x140075386  test    rcx, rcx
0x140075389  jz      short loc_1400753BD
0x14007538b  mov     rax, [rcx]
0x14007538e  mov     rax, [rax+10h]
0x140075392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075397  jmp     short loc_1400753BD
0x140075399  mov     r9d, [rsi+58h]
0x14007539d  lea     rdx, aASandboxHostIs; "A sandbox host is going to be recycled "...
0x1400753a4  mov     r8d, [rsi+60h]
0x1400753a8  lea     rcx, aSandboxSandbox; "sandbox::SandboxConnection::ValidateInt"...
0x1400753af  mov     edi, 800106BAh
0x1400753b4  call    ?WriteDbgTraceInfo@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400753b9  lea     r14, [rsi+50h]
0x1400753bd  test    r15, r15
0x1400753c0  jz      short loc_1400753DB
0x1400753c2  test    edi, edi
0x1400753c4  js      short loc_1400753DB
0x1400753c6  mov     rax, [r14]
0x1400753c9  mov     [r15], rax
0x1400753cc  mov     rcx, [r14]
0x1400753cf  mov     rax, [rcx]
0x1400753d2  mov     rax, [rax+8]
0x1400753d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400753db  mov     rcx, r13; lpCriticalSection
0x1400753de  call    cs:__imp_LeaveCriticalSection
0x1400753e4  test    edi, edi
0x1400753e6  jns     short loc_1400753FE
0x1400753e8  mov     r8d, edi
0x1400753eb  lea     rdx, aFailedToGetSan; "Failed to get sandbox interface pointer"...
0x1400753f2  lea     rcx, aSandboxSandbox; "sandbox::SandboxConnection::ValidateInt"...
0x1400753f9  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400753fe  mov     eax, edi
0x140075400  add     rsp, 58h
0x140075404  pop     r15
0x140075406  pop     r14
0x140075408  pop     r13
0x14007540a  pop     r12
0x14007540c  pop     rdi
0x14007540d  pop     rsi
0x14007540e  pop     rbx
0x14007540f  pop     rbp
0x140075410  retn
```
