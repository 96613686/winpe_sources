# CSWbemServices::ExecQuery(ushort *,ushort *,long,IDispatch *,ISWbemObjectSet * *)

- ea: `0x180008800`
- end: `0x180008dd4`
- name: `?ExecQuery@CSWbemServices@@UEAAJPEAG0JPEAUIDispatch@@PEAPEAUISWbemObjectSet@@@Z`
- size: `1492`
- prototype: `__int64 __usercall@<rax>(CSWbemServices *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, int@<r9d>, struct IDispatch *, struct ISWbemObjectSet **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180001b78`
- `0x180001d0c`
- `0x1800050dc`
- `0x180006300`
- `0x180006710`
- `0x1800077d0`
- `0x180008800`
- `0x18000a270`
- `0x1800128e0`
- `0x180013ee0`
- `0x1800184d4`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800089e7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800089e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008b70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008b70`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008bc2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008bc2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008b23`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008b23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008b0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008b0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008c81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008c81`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180008c96`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180008c96`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008b5b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008b5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ca1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ca1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cf9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180008962`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180008a30`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180008962`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180008a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSWbemServices::ExecQuery(
        CSWbemServices *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        struct IDispatch *a5,
        struct ISWbemObjectSet **a6)
{
  struct ISWbemObjectSet **v8; // rsi
  int v9; // r14d
  __int64 v10; // rbx
  __int64 v11; // rbx
  char v12; // di
  __int64 v13; // rcx
  __int64 v14; // r13
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  CSWbemSecurity *v18; // rcx
  _QWORD *v19; // rax
  _QWORD *v20; // rdi
  struct IUnknown *v21; // r12
  struct CSWbemSecurity *v22; // r14
  __int64 v23; // rax
  __int64 v24; // rcx
  CSWbemSecurity *v25; // rax
  unsigned int v26; // edx
  HANDLE CurrentThread; // rax
  __int64 v29; // rax
  __int64 v30; // rcx
  HANDLE CurrentProcess; // rsi
  BOOL v32; // edi
  int v33; // ecx
  enum WbemImpersonationLevelEnum v34; // [rsp+40h] [rbp-49h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL TokenInformation; // [rsp+44h] [rbp-45h] BYREF
  __int64 v36; // [rsp+48h] [rbp-41h]
  int v37; // [rsp+50h] [rbp-39h] BYREF
  enum WbemAuthenticationLevelEnum v38; // [rsp+54h] [rbp-35h] BYREF
  __int64 v39; // [rsp+58h] [rbp-31h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp-29h] BYREF
  HANDLE Token; // [rsp+68h] [rbp-21h] BYREF
  DWORD ReturnLength; // [rsp+70h] [rbp-19h] BYREF
  __int64 v43; // [rsp+78h] [rbp-11h] BYREF
  void *v44; // [rsp+80h] [rbp-9h]
  struct IUnknown *v45; // [rsp+88h] [rbp-1h] BYREF
  struct IUnknown *Proxy; // [rsp+90h] [rbp+7h]
  int v49; // [rsp+108h] [rbp+7Fh]

  ResetLastErrors();
  v8 = a6;
  if ( !a6 )
  {
    v9 = -2147217400;
LABEL_57:
    CDispatchHelp::RaiseException((CSWbemServices *)((char *)this + 56), v9);
    return (unsigned int)v9;
  }
  v9 = -2147217407;
  v10 = *((_QWORD *)this + 17);
  if ( !v10 )
    goto LABEL_57;
  v11 = *(_QWORD *)(v10 + 128);
  if ( !v11 )
    goto LABEL_57;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  v12 = 0;
  v45 = 0;
  v13 = *((_QWORD *)this + 18);
  v39 = 0;
  v43 = 0;
  if ( v13
    && (*(int (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v13 + 24LL))(
         v13,
         &IID_IWbemContext,
         &IID_IWbemContext,
         &v39) < 0 )
  {
    v39 = 0;
  }
  if ( a5
    && !v39
    && ((__int64 (__fastcall *)(struct IDispatch *, GUID *, __int64 *))a5->lpVtbl->QueryInterface)(
         a5,
         &IID_ISWbemInternalContext,
         &v43) >= 0 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 24LL))(v43, &v39);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v14 = v39;
  v44 = 0;
  if ( !CSWbemSecurity::s_bIsNT )
    goto LABEL_13;
  v15 = *((_QWORD *)this + 17);
  v36 = v15;
  v16 = *(_QWORD *)(v15 + 120);
  if ( v16 )
  {
    if ( *(_BYTE *)(v16 + 321) )
      goto LABEL_13;
  }
  v17 = *(_QWORD *)(v15 + 32);
  if ( !v17 )
    goto LABEL_13;
  v37 = 0;
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 72LL))(v17, &v37);
  if ( v37 <= 0 )
    goto LABEL_13;
  TokenHandle = 0;
  TokenInformation = SecurityImpersonation;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
  {
    v44 = TokenHandle;
    ReturnLength = 0;
    GetTokenInformation(TokenHandle, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength);
  }
  else
  {
    if ( GetLastError() != 1008 )
      goto LABEL_29;
    CurrentProcess = GetCurrentProcess();
    v32 = OpenProcessToken(CurrentProcess, 0x2000Au, &TokenHandle);
    CloseHandle(CurrentProcess);
    if ( !v32 )
      goto LABEL_29;
    v34 = 0;
    (*(void (__fastcall **)(__int64, enum WbemImpersonationLevelEnum *))(*(_QWORD *)v36 + 56LL))(v36, &v34);
    if ( v34 == wbemImpersonationLevelImpersonate )
    {
      v33 = 2;
    }
    else
    {
      v33 = 0;
      if ( v34 != wbemImpersonationLevelAnonymous )
      {
        if ( v34 == wbemImpersonationLevelIdentify )
        {
          v33 = 1;
        }
        else if ( v34 == wbemImpersonationLevelDelegate )
        {
          v33 = 3;
        }
      }
    }
    TokenInformation = v33;
    v12 = 0;
    v8 = a6;
  }
  Token = 0;
  EnterCriticalSection(&g_csSecurity);
  v49 = DuplicateTokenSameAcl(TokenHandle, TokenInformation, &Token);
  LeaveCriticalSection(&g_csSecurity);
  if ( v49 && (v49 = CSWbemSecurity::AdjustTokenPrivileges(Token, *(struct CSWbemPrivilegeSet **)(v36 + 32))) != 0 )
  {
    if ( SetThreadToken(0, Token) )
    {
      v12 = 1;
      v38 = wbemAuthenticationLevelDefault;
      v34 = 0;
      if ( !(unsigned int)GetAuthImp(*(struct IUnknown **)(v36 + 128), (unsigned int *)&v38, (unsigned int *)&v34) )
      {
        Proxy = CSWbemProxyCache::GetProxy(*(CSWbemProxyCache **)(v36 + 120), v38, v34, 1);
        if ( Proxy )
        {
          v29 = v36;
          v30 = *(_QWORD *)(v36 + 128);
          if ( v30 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            v29 = v36;
          }
          *(_QWORD *)(v29 + 128) = Proxy;
        }
      }
    }
    else
    {
      v49 = 0;
    }
    CloseHandle(Token);
  }
  else
  {
    GetLastError();
  }
  if ( !v44 )
    CloseHandle(TokenHandle);
  if ( v49 )
LABEL_13:
    v9 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, _QWORD, __int64, struct IUnknown **))(*(_QWORD *)v11 + 160LL))(
           v11,
           a3,
           a2,
           a4 | 0x100u,
           v14,
           &v45);
  if ( v12 )
    CSWbemSecurity::ResetSecurity(v18, v44);
  if ( v9 >= 0 )
  {
    v19 = CWin32DefaultArena::WbemMemAlloc(0x80u);
    v20 = v19;
    if ( v19 )
    {
      v21 = v45;
      *v19 = &CSWbemObjectSet::`vftable'{for `ISWbemObjectSet'};
      v19[1] = &CSWbemObjectSet::`vftable'{for `ISupportErrorInfo'};
      v19[2] = &CSWbemObjectSet::`vftable'{for `IProvideClassInfo'};
      v19[4] = &CDispatchHelp::`vftable';
      v22 = 0;
      v19[7] = 0;
      v19[8] = 0;
      v19[9] = 0;
      v19[5] = 0;
      *((_DWORD *)v19 + 12) = 0;
      v19[14] = 0;
      *((_BYTE *)v19 + 121) = 0;
      v19[9] = v19;
      *((GUID *)v19 + 5) = IID_ISWbemObjectSet;
      *((GUID *)v19 + 6) = CLSID_SWbemObjectSet;
      v19[5] = SysAllocString(L"SWbemObjectSet");
      *((_DWORD *)v20 + 31) = 0;
      *((_BYTE *)v20 + 120) = 1;
      v20[3] = this;
      (*(void (__fastcall **)(CSWbemServices *))(*(_QWORD *)this + 8LL))(this);
      v23 = v20[3];
      v24 = *(_QWORD *)(v23 + 136);
      if ( v24 )
      {
        v22 = *(struct CSWbemSecurity **)(v23 + 136);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
      }
      v25 = (CSWbemSecurity *)CWin32DefaultArena::WbemMemAlloc(0x90u);
      Proxy = (struct IUnknown *)v25;
      if ( v25 )
        v25 = CSWbemSecurity::CSWbemSecurity(v25, v21, v22);
      v20[14] = v25;
      if ( v22 )
        (*(void (__fastcall **)(struct CSWbemSecurity *))(*(_QWORD *)v22 + 16LL))(v22);
      _InterlockedIncrement(&g_cObj);
    }
    else
    {
      v20 = 0;
    }
    if ( v20 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct ISWbemObjectSet **))*v20)(v20, &IID_ISWbemObjectSet, v8);
      if ( v9 < 0 )
        CSWbemObjectSet::`scalar deleting destructor'((CSWbemObjectSet *)v20, v26);
    }
    else
    {
      v9 = -2147217402;
    }
    ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
  }
LABEL_29:
  SetWbemError(this);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v9 < 0 )
    goto LABEL_57;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180008800  mov     [rsp-8+arg_0], rbx
0x180008805  mov     [rsp-8+arg_10], r8
0x18000880a  mov     [rsp-8+arg_8], rdx
0x18000880f  push    rbp
0x180008810  push    rsi
0x180008811  push    rdi
0x180008812  push    r12
0x180008814  push    r13
0x180008816  push    r14
0x180008818  push    r15
0x18000881a  lea     rbp, [rsp-17h]
0x18000881f  sub     rsp, 0A0h
0x180008826  mov     r12d, r9d
0x180008829  mov     r15, rcx
0x18000882c  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x180008831  mov     rsi, [rbp+47h+arg_28]
0x180008835  test    rsi, rsi
0x180008838  jz      loc_180008D04
0x18000883e  mov     r14d, 80041001h
0x180008844  mov     rbx, [r15+88h]
0x18000884b  test    rbx, rbx
0x18000884e  jz      loc_180008D0A
0x180008854  mov     rbx, [rbx+80h]
0x18000885b  test    rbx, rbx
0x18000885e  jz      loc_180008D0A
0x180008864  mov     rax, [rbx]
0x180008867  mov     rcx, rbx
0x18000886a  mov     rax, [rax+8]
0x18000886e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008873  xor     edi, edi
0x180008875  mov     [rbp+47h+var_48], rdi
0x180008879  mov     rcx, [r15+90h]
0x180008880  mov     [rbp+47h+var_78], rdi
0x180008884  mov     [rbp+47h+var_58], rdi
0x180008888  test    rcx, rcx
0x18000888b  jz      short loc_1800088B3
0x18000888d  mov     rax, [rcx]
0x180008890  lea     r9, [rbp+47h+var_78]
0x180008894  lea     r8, IID_IWbemContext
0x18000889b  lea     rdx, IID_IWbemContext
0x1800088a2  mov     rax, [rax+18h]
0x1800088a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088ab  test    eax, eax
0x1800088ad  jns     short loc_1800088B3
0x1800088af  mov     [rbp+47h+var_78], rdi
0x1800088b3  mov     rcx, [rbp+47h+arg_20]
0x1800088b7  test    rcx, rcx
0x1800088ba  jnz     loc_180008D1B
0x1800088c0  mov     r13, [rbp+47h+var_78]
0x1800088c4  mov     [rbp+47h+var_50], rdi
0x1800088c8  cmp     cs:?s_bIsNT@CSWbemSecurity@@0_NA, dil; bool CSWbemSecurity::s_bIsNT
0x1800088cf  jz      short loc_180008918
0x1800088d1  mov     rcx, [r15+88h]
0x1800088d8  mov     [rbp+47h+var_88], rcx
0x1800088dc  mov     rax, [rcx+78h]
0x1800088e0  test    rax, rax
0x1800088e3  jz      short loc_1800088EE
0x1800088e5  cmp     [rax+141h], dil
0x1800088ec  jnz     short loc_180008918
0x1800088ee  mov     rcx, [rcx+20h]
0x1800088f2  test    rcx, rcx
0x1800088f5  jz      short loc_180008918
0x1800088f7  mov     [rbp+47h+var_80], 0
0x1800088fe  mov     rax, [rcx]
0x180008901  lea     rdx, [rbp+47h+var_80]
0x180008905  mov     rax, [rax+48h]
0x180008909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000890e  cmp     [rbp+47h+var_80], 0
0x180008912  jg      loc_180008AFC
0x180008918  mov     rax, [rbx]
0x18000891b  bts     r12d, 8
0x180008920  lea     rcx, [rbp+47h+var_48]
0x180008924  mov     [rsp+0D0h+var_A8], rcx
0x180008929  mov     [rsp+0D0h+ReturnLength], r13
0x18000892e  mov     r9d, r12d
0x180008931  mov     r8, [rbp+47h+arg_8]
0x180008935  mov     rdx, [rbp+47h+arg_10]
0x180008939  mov     rcx, rbx
0x18000893c  mov     rax, [rax+0A0h]
0x180008943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008948  mov     r14d, eax
0x18000894b  test    dil, dil
0x18000894e  jnz     loc_180008D99
0x180008954  test    r14d, r14d
0x180008957  js      loc_180008AA9
0x18000895d  mov     ecx, 80h
0x180008962  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180008968  mov     rdi, rax
0x18000896b  mov     [rbp+47h+arg_28], rax
0x18000896f  test    rax, rax
0x180008972  jz      loc_180008AF5
0x180008978  mov     r12, [rbp+47h+var_48]
0x18000897c  lea     rax, ??_7CSWbemObjectSet@@6BISWbemObjectSet@@@; const CSWbemObjectSet::`vftable'{for `ISWbemObjectSet'}
0x180008983  mov     [rdi], rax
0x180008986  lea     rax, ??_7CSWbemObjectSet@@6BISupportErrorInfo@@@; const CSWbemObjectSet::`vftable'{for `ISupportErrorInfo'}
0x18000898d  mov     [rdi+8], rax
0x180008991  lea     rax, ??_7CSWbemObjectSet@@6BIProvideClassInfo@@@; const CSWbemObjectSet::`vftable'{for `IProvideClassInfo'}
0x180008998  mov     [rdi+10h], rax
0x18000899c  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x1800089a3  mov     [rdi+20h], rax
0x1800089a7  xor     r14d, r14d
0x1800089aa  mov     [rdi+38h], r14
0x1800089ae  mov     [rdi+40h], r14
0x1800089b2  mov     [rdi+48h], r14
0x1800089b6  mov     [rdi+28h], r14
0x1800089ba  mov     [rdi+30h], r14d
0x1800089be  mov     [rdi+70h], r14
0x1800089c2  mov     [rdi+79h], r14b
0x1800089c6  movups  xmm1, xmmword ptr cs:CLSID_SWbemObjectSet.Data1
0x1800089cd  movups  xmm0, xmmword ptr cs:IID_ISWbemObjectSet.Data1
0x1800089d4  mov     [rdi+48h], rdi
0x1800089d8  movups  xmmword ptr [rdi+50h], xmm0
0x1800089dc  movups  xmmword ptr [rdi+60h], xmm1
0x1800089e0  lea     rcx, aSwbemobjectset; "SWbemObjectSet"
0x1800089e7  call    cs:__imp_SysAllocString
0x1800089ed  mov     [rdi+28h], rax
0x1800089f1  mov     [rdi+7Ch], r14d
0x1800089f5  mov     byte ptr [rdi+78h], 1
0x1800089f9  mov     [rdi+18h], r15
0x1800089fd  mov     rax, [r15]
0x180008a00  mov     rcx, r15
0x180008a03  mov     rax, [rax+8]
0x180008a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a0c  mov     rax, [rdi+18h]
0x180008a10  mov     rcx, [rax+88h]
0x180008a17  test    rcx, rcx
0x180008a1a  jz      short loc_180008A2B
0x180008a1c  mov     r14, rcx
0x180008a1f  mov     rax, [rcx]
0x180008a22  mov     rax, [rax+8]
0x180008a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a2b  mov     ecx, 90h
0x180008a30  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180008a36  mov     [rbp+47h+var_40], rax
0x180008a3a  test    rax, rax
0x180008a3d  jz      short loc_180008A4E
0x180008a3f  mov     r8, r14; struct CSWbemSecurity *
0x180008a42  mov     rdx, r12; struct IUnknown *
0x180008a45  mov     rcx, rax; this
0x180008a48  call    ??0CSWbemSecurity@@QEAA@PEAUIUnknown@@PEAV0@@Z; CSWbemSecurity::CSWbemSecurity(IUnknown *,CSWbemSecurity *)
0x180008a4d  nop
0x180008a4e  mov     [rdi+70h], rax
0x180008a52  test    r14, r14
0x180008a55  jz      short loc_180008A66
0x180008a57  mov     rax, [r14]
0x180008a5a  mov     rcx, r14
0x180008a5d  mov     rax, [rax+10h]
0x180008a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a66  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180008a6d  test    rdi, rdi
0x180008a70  jz      loc_180008DA7
0x180008a76  mov     rax, [rdi]
0x180008a79  mov     r8, rsi
0x180008a7c  lea     rdx, IID_ISWbemObjectSet
0x180008a83  mov     rcx, rdi
0x180008a86  mov     rax, [rax]
0x180008a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a8e  mov     r14d, eax
0x180008a91  test    eax, eax
0x180008a93  js      loc_180008DB2
0x180008a99  mov     rcx, [rbp+47h+var_48]
0x180008a9d  mov     rax, [rcx]
0x180008aa0  mov     rax, [rax+10h]
0x180008aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aa9  mov     rcx, r15; this
0x180008aac  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x180008ab1  test    r13, r13
0x180008ab4  jnz     loc_180008DBF
0x180008aba  mov     rax, [rbx]
0x180008abd  mov     rcx, rbx
0x180008ac0  mov     rax, [rax+10h]
0x180008ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ac9  test    r14d, r14d
0x180008acc  js      loc_180008D0A
0x180008ad2  mov     eax, r14d
0x180008ad5  mov     rbx, [rsp+0D0h+arg_0]
0x180008add  add     rsp, 0A0h
0x180008ae4  pop     r15
0x180008ae6  pop     r14
0x180008ae8  pop     r13
0x180008aea  pop     r12
0x180008aec  pop     rdi
0x180008aed  pop     rsi
0x180008aee  pop     rbp
0x180008aef  retn
0x180008af0  jmp     loc_180008A4E
0x180008af5  xor     edi, edi
0x180008af7  jmp     loc_180008A6D
0x180008afc  mov     [rbp+47h+TokenHandle], 0
0x180008b04  mov     [rbp+47h+TokenInformation], 2
0x180008b0b  call    cs:__imp_GetCurrentThread
0x180008b11  mov     rcx, rax; ThreadHandle
0x180008b14  lea     r9, [rbp+47h+TokenHandle]; TokenHandle
0x180008b18  mov     edx, 2000Eh; DesiredAccess
0x180008b1d  mov     r8d, 1; OpenAsSelf
0x180008b23  call    cs:__imp_OpenThreadToken
0x180008b29  test    eax, eax
0x180008b2b  jz      loc_180008C70
0x180008b31  mov     rax, [rbp+47h+TokenHandle]
0x180008b35  mov     [rbp+47h+var_50], rax
0x180008b39  mov     [rbp+47h+var_60], 0
0x180008b40  lea     rcx, [rbp+47h+var_60]
0x180008b44  mov     [rsp+0D0h+ReturnLength], rcx; ReturnLength
0x180008b49  mov     r9d, 4; TokenInformationLength
0x180008b4f  lea     r8, [rbp+47h+TokenInformation]; TokenInformation
0x180008b53  mov     edx, 9; TokenInformationClass
0x180008b58  mov     rcx, rax; TokenHandle
0x180008b5b  call    cs:__imp_GetTokenInformation
0x180008b61  mov     [rbp+47h+Token], 0
0x180008b69  lea     rcx, ?g_csSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008b70  call    cs:__imp_EnterCriticalSection
0x180008b76  lea     r8, [rbp+47h+Token]; void **
0x180008b7a  mov     edx, [rbp+47h+TokenInformation]; enum _SECURITY_IMPERSONATION_LEVEL
0x180008b7d  mov     rcx, [rbp+47h+TokenHandle]; Handle
0x180008b81  call    ?DuplicateTokenSameAcl@@YAHPEAXW4_SECURITY_IMPERSONATION_LEVEL@@PEAPEAX@Z; DuplicateTokenSameAcl(void *,_SECURITY_IMPERSONATION_LEVEL,void * *)
0x180008b86  mov     dword ptr [rbp+47h+arg_28], eax
0x180008b89  lea     rcx, ?g_csSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008b90  call    cs:__imp_LeaveCriticalSection
0x180008b96  cmp     dword ptr [rbp+47h+arg_28], 0
0x180008b9a  jz      loc_180008CEA
0x180008ba0  mov     rdx, [rbp+47h+var_88]
0x180008ba4  mov     rdx, [rdx+20h]; struct CSWbemPrivilegeSet *
0x180008ba8  mov     rcx, [rbp+47h+Token]; TokenHandle
0x180008bac  call    ?AdjustTokenPrivileges@CSWbemSecurity@@SAHPEAXPEAVCSWbemPrivilegeSet@@@Z; CSWbemSecurity::AdjustTokenPrivileges(void *,CSWbemPrivilegeSet *)
0x180008bb1  mov     dword ptr [rbp+47h+arg_28], eax
0x180008bb4  test    eax, eax
0x180008bb6  jz      loc_180008CEA
0x180008bbc  mov     rdx, [rbp+47h+Token]; Token
0x180008bc0  xor     ecx, ecx; Thread
0x180008bc2  call    cs:__imp_SetThreadToken
0x180008bc8  test    eax, eax
0x180008bca  jz      loc_180008C67
0x180008bd0  mov     dil, 1
0x180008bd3  xor     eax, eax
0x180008bd5  mov     [rbp+47h+var_7C], eax
0x180008bd8  mov     [rbp+47h+var_90], eax
0x180008bdb  lea     r8, [rbp+47h+var_90]; unsigned int *
0x180008bdf  lea     rdx, [rbp+47h+var_7C]; unsigned int *
0x180008be3  mov     rax, [rbp+47h+var_88]
0x180008be7  mov     rcx, [rax+80h]; struct IUnknown *
0x180008bee  call    ?GetAuthImp@@YAJPEAUIUnknown@@PEAK1@Z; GetAuthImp(IUnknown *,ulong *,ulong *)
0x180008bf3  test    eax, eax
0x180008bf5  jnz     short loc_180008C43
0x180008bf7  movzx   r9d, dil; bool
0x180008bfb  mov     r8d, [rbp+47h+var_90]; enum WbemImpersonationLevelEnum
0x180008bff  mov     edx, [rbp+47h+var_7C]; enum WbemAuthenticationLevelEnum
0x180008c02  mov     rax, [rbp+47h+var_88]
0x180008c06  mov     rcx, [rax+78h]; this
0x180008c0a  call    ?GetProxy@CSWbemProxyCache@@QEAAPEAUIUnknown@@W4WbemAuthenticationLevelEnum@@W4WbemImpersonationLevelEnum@@_N@Z; CSWbemProxyCache::GetProxy(WbemAuthenticationLevelEnum,WbemImpersonationLevelEnum,bool)
0x180008c0f  mov     [rbp+47h+var_40], rax
0x180008c13  test    rax, rax
0x180008c16  jz      short loc_180008C43
0x180008c18  mov     rax, [rbp+47h+var_88]
0x180008c1c  mov     rcx, [rax+80h]
0x180008c23  test    rcx, rcx
0x180008c26  jz      short loc_180008C38
0x180008c28  mov     rax, [rcx]
0x180008c2b  mov     rax, [rax+10h]
0x180008c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c34  mov     rax, [rbp+47h+var_88]
0x180008c38  mov     rcx, [rbp+47h+var_40]
0x180008c3c  mov     [rax+80h], rcx
0x180008c43  mov     rcx, [rbp+47h+Token]; hObject
0x180008c47  call    cs:__imp_CloseHandle
0x180008c4d  cmp     [rbp+47h+var_50], 0
0x180008c52  jz      loc_180008CF5
0x180008c58  cmp     dword ptr [rbp+47h+arg_28], 0
0x180008c5c  jz      loc_18000894B
0x180008c62  jmp     loc_180008918
0x180008c67  mov     dword ptr [rbp+47h+arg_28], 0
0x180008c6e  jmp     short loc_180008C43
0x180008c70  call    cs:__imp_GetLastError
0x180008c76  cmp     eax, 3F0h
0x180008c7b  jnz     loc_180008AA9
0x180008c81  call    cs:__imp_GetCurrentProcess
0x180008c87  mov     rsi, rax
0x180008c8a  lea     r8, [rbp+47h+TokenHandle]; TokenHandle
0x180008c8e  mov     edx, 2000Ah; DesiredAccess
0x180008c93  mov     rcx, rax; ProcessHandle
0x180008c96  call    cs:__imp_OpenProcessToken
0x180008c9c  mov     edi, eax
0x180008c9e  mov     rcx, rsi; hObject
0x180008ca1  call    cs:__imp_CloseHandle
0x180008ca7  test    edi, edi
0x180008ca9  jz      loc_180008AA9
0x180008caf  mov     [rbp+47h+var_90], 0
0x180008cb6  mov     rcx, [rbp+47h+var_88]
0x180008cba  mov     rax, [rcx]
0x180008cbd  lea     rdx, [rbp+47h+var_90]
0x180008cc1  mov     rax, [rax+38h]
0x180008cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cca  mov     edx, [rbp+47h+var_90]
0x180008ccd  cmp     edx, 3
0x180008cd0  jnz     loc_180008D6C
0x180008cd6  mov     ecx, 2
0x180008cdb  mov     [rbp+47h+TokenInformation], ecx
0x180008cde  xor     dil, dil
0x180008ce1  mov     rsi, [rbp+47h+arg_28]
0x180008ce5  jmp     loc_180008B61
0x180008cea  call    cs:__imp_GetLastError
  ... truncated ...
```
