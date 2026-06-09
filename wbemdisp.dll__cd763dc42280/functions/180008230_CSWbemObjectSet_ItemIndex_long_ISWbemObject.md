# CSWbemObjectSet::ItemIndex(long,ISWbemObject * *)

- ea: `0x180008230`
- end: `0x1800087fa`
- name: `?ItemIndex@CSWbemObjectSet@@UEAAJJPEAPEAUISWbemObject@@@Z`
- size: `1482`
- prototype: `__int64 __fastcall(CSWbemObjectSet *__hidden this, int, struct ISWbemObject **)`
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
- `0x180008230`
- `0x180008de0`
- `0x180009320`
- `0x1800128e0`
- `0x1800184d4`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008789`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008651`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008651`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008632`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008632`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000867c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000867c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800085ed`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800085ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800085d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800085d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000872a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000872a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000873f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000873f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008621`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008621`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000874a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008798`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000874a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008798`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180008487`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180008487`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CSWbemObjectSet::ItemIndex(CSWbemObjectSet *this, int a2, struct ISWbemObject **a3)
{
  struct ISWbemObject **v3; // r13
  int v6; // edi
  __int64 v7; // r14
  __int64 v8; // r14
  struct IUnknown *v9; // rbx
  struct IUnknownVtbl *lpVtbl; // rax
  struct IUnknownVtbl *v11; // rcx
  CSWbemSecurity *v12; // rcx
  struct IUnknown *v13; // rsi
  __int64 v14; // r13
  __int64 (__fastcall ***v15)(_QWORD, GUID *, struct IUnknown **); // rbx
  int v16; // edi
  CSWbemProxyCache *v17; // rcx
  int v18; // eax
  int v19; // eax
  CSWbemObject *v20; // rax
  CSWbemObject *v21; // rbx
  HANDLE CurrentThread; // rax
  int v24; // esi
  struct IUnknown *Proxy; // rax
  struct IUnknownVtbl *v26; // rcx
  HANDLE CurrentProcess; // rsi
  BOOL v28; // ebx
  int v29; // ecx
  enum WbemAuthenticationLevelEnum v30; // [rsp+50h] [rbp-39h] BYREF
  enum WbemImpersonationLevelEnum v31; // [rsp+54h] [rbp-35h] BYREF
  HANDLE Token; // [rsp+58h] [rbp-31h] BYREF
  struct IUnknown *v33; // [rsp+60h] [rbp-29h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL TokenInformation; // [rsp+68h] [rbp-21h] BYREF
  struct IUnknown *v35; // [rsp+70h] [rbp-19h] BYREF
  int v36; // [rsp+78h] [rbp-11h] BYREF
  HANDLE TokenHandle; // [rsp+80h] [rbp-9h] BYREF
  DWORD ReturnLength; // [rsp+88h] [rbp-1h] BYREF
  int v39; // [rsp+8Ch] [rbp+3h] BYREF
  int v40; // [rsp+90h] [rbp+7h] BYREF
  void *v41; // [rsp+98h] [rbp+Fh]
  __int64 v42; // [rsp+A0h] [rbp+17h]
  struct ISWbemObject **v43; // [rsp+100h] [rbp+77h] BYREF
  char v44; // [rsp+108h] [rbp+7Fh]

  v43 = a3;
  v3 = a3;
  ResetLastErrors();
  if ( !v3 || a2 < 0 )
  {
    v6 = -2147217400;
    goto LABEL_79;
  }
  v6 = -2147217407;
  v7 = *((_QWORD *)this + 14);
  if ( !v7 )
  {
LABEL_79:
    CDispatchHelp::RaiseException((CSWbemObjectSet *)((char *)this + 32), v6);
    return (unsigned int)v6;
  }
  v42 = 0;
  v8 = *(_QWORD *)(v7 + 128);
  if ( !v8 )
    goto LABEL_40;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v42 = v8;
  v35 = 0;
  v41 = 0;
  v44 = 0;
  if ( !CSWbemSecurity::s_bIsNT )
    goto LABEL_10;
  v9 = (struct IUnknown *)*((_QWORD *)this + 14);
  v33 = v9;
  lpVtbl = v9[15].lpVtbl;
  if ( lpVtbl )
  {
    if ( BYTE1(lpVtbl[13].AddRef) )
      goto LABEL_10;
  }
  v11 = v9[4].lpVtbl;
  if ( !v11 )
    goto LABEL_10;
  v36 = 0;
  (*((void (__fastcall **)(struct IUnknownVtbl *, int *))v11->QueryInterface + 9))(v11, &v36);
  if ( v36 <= 0 )
    goto LABEL_10;
  TokenHandle = 0;
  TokenInformation = SecurityImpersonation;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
  {
    v41 = TokenHandle;
    ReturnLength = 0;
    GetTokenInformation(TokenHandle, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength);
    goto LABEL_53;
  }
  if ( GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    v28 = OpenProcessToken(CurrentProcess, 0x2000Au, &TokenHandle);
    CloseHandle(CurrentProcess);
    if ( v28 )
    {
      v30 = wbemAuthenticationLevelDefault;
      v9 = v33;
      ((void (__fastcall *)(struct IUnknown *, enum WbemAuthenticationLevelEnum *))v33->lpVtbl[2].AddRef)(v33, &v30);
      if ( v30 == wbemAuthenticationLevelCall )
      {
        v29 = 2;
      }
      else
      {
        v29 = 0;
        if ( v30 != wbemAuthenticationLevelNone )
        {
          if ( v30 == wbemAuthenticationLevelConnect )
          {
            v29 = 1;
          }
          else if ( v30 == wbemAuthenticationLevelPkt )
          {
            v29 = 3;
          }
        }
      }
      TokenInformation = v29;
LABEL_53:
      Token = 0;
      EnterCriticalSection(&g_csSecurity);
      v24 = DuplicateTokenSameAcl(TokenHandle, TokenInformation, &Token);
      LeaveCriticalSection(&g_csSecurity);
      if ( v24 && (v24 = CSWbemSecurity::AdjustTokenPrivileges(Token, (struct CSWbemPrivilegeSet *)v9[4].lpVtbl)) != 0 )
      {
        if ( SetThreadToken(0, Token) )
        {
          v44 = 1;
          v31 = 0;
          v30 = wbemAuthenticationLevelDefault;
          if ( !(unsigned int)GetAuthImp((struct IUnknown *)v9[16].lpVtbl, (unsigned int *)&v31, (unsigned int *)&v30) )
          {
            Proxy = CSWbemProxyCache::GetProxy(
                      (CSWbemProxyCache *)v9[15].lpVtbl,
                      (enum WbemAuthenticationLevelEnum)v31,
                      (enum WbemImpersonationLevelEnum)v30,
                      1);
            v33 = Proxy;
            if ( Proxy )
            {
              v26 = v9[16].lpVtbl;
              if ( v26 )
              {
                (*((void (__fastcall **)(struct IUnknownVtbl *))v26->QueryInterface + 2))(v26);
                Proxy = v33;
              }
              v9[16].lpVtbl = (struct IUnknownVtbl *)Proxy;
            }
          }
        }
        else
        {
          v24 = 0;
        }
        CloseHandle(Token);
      }
      else
      {
        GetLastError();
      }
      if ( !v41 )
        CloseHandle(TokenHandle);
      if ( !v24 )
        goto LABEL_36;
LABEL_10:
      v6 = (*(__int64 (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v8 + 48LL))(v8, &v35);
      if ( v6 )
        goto LABEL_36;
      v13 = v35;
      if ( v35 )
      {
        v14 = *((_QWORD *)this + 14);
        v15 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IUnknown **))(v14 + 128);
        if ( v15 )
        {
          v30 = wbemAuthenticationLevelDefault;
          v31 = 0;
          v33 = 0;
          v16 = (**v15)(v15, &IID_IClientSecurity, &v33);
          if ( !v16 )
          {
            LODWORD(Token) = 0;
            v40 = 0;
            v39 = 0;
            v16 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 (__fastcall ***)(_QWORD, GUID *, struct IUnknown **), HANDLE *, int *, _QWORD, enum WbemAuthenticationLevelEnum *, enum WbemImpersonationLevelEnum *, _QWORD, int *))v33->lpVtbl[1].QueryInterface)(
                    v33,
                    v15,
                    &Token,
                    &v40,
                    0,
                    &v30,
                    &v31,
                    0,
                    &v39);
            if ( v16 == -2147023150 )
            {
              v30 = wbemAuthenticationLevelNone;
              v31 = wbemImpersonationLevelIdentify;
              v16 = 0;
            }
            ((void (__fastcall *)(struct IUnknown *))v33->lpVtbl->Release)(v33);
          }
          if ( !v16 )
          {
            v17 = *(CSWbemProxyCache **)(v14 + 120);
            if ( v17 )
              CSWbemProxyCache::SecureProxy(v17, v13, v30, v31);
          }
        }
        v3 = v43;
      }
      v6 = ((__int64 (__fastcall *)(struct IUnknown *))v35->lpVtbl[1].QueryInterface)(v35);
      if ( v6 )
        goto LABEL_36;
      v18 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD))v35->lpVtbl[2].AddRef)(
              v35,
              0xFFFFFFFFLL,
              (unsigned int)a2);
      if ( v18 )
      {
        if ( v18 == 1 )
          v18 = -2147217400;
        v6 = v18;
        goto LABEL_36;
      }
      Token = 0;
      LODWORD(v43) = 0;
      v19 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, HANDLE *, struct ISWbemObject ***))v35->lpVtbl[1].AddRef)(
              v35,
              0xFFFFFFFFLL,
              1,
              &Token,
              &v43);
      v6 = v19;
      if ( v19 )
      {
        if ( v19 == 1 )
          v6 = -2147217400;
      }
      else if ( (_DWORD)v43 )
      {
        v12 = (CSWbemSecurity *)Token;
        if ( !Token )
          goto LABEL_34;
        v20 = (CSWbemObject *)CWin32DefaultArena::WbemMemAlloc(0x78u);
        v33 = (struct IUnknown *)v20;
        if ( v20 )
          v21 = CSWbemObject::CSWbemObject(
                  v20,
                  *((struct CSWbemServices **)this + 3),
                  (struct IWbemClassObject *)Token,
                  *((struct CSWbemSecurity **)this + 14),
                  v6);
        else
          v21 = 0;
        v33 = (struct IUnknown *)v21;
        if ( v21 )
        {
          (*(void (__fastcall **)(CSWbemObject *))(*(_QWORD *)v21 + 8LL))(v21);
          v6 = (**(__int64 (__fastcall ***)(CSWbemObject *, GUID *, struct ISWbemObject **))v21)(
                 v21,
                 &IID_ISWbemObject,
                 v3);
          if ( v6 >= 0 )
          {
            (*(void (__fastcall **)(CSWbemObject *))(*(_QWORD *)v21 + 16LL))(v21);
            v21 = 0;
          }
        }
        else
        {
          v6 = -2147217402;
        }
        if ( v21 )
          (*(void (__fastcall **)(CSWbemObject *))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v12 = (CSWbemSecurity *)Token;
LABEL_34:
      if ( v12 )
        (*(void (__fastcall **)(CSWbemSecurity *))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_36:
      if ( v44 )
        CSWbemSecurity::ResetSecurity(v12, v41);
    }
  }
  SetWbemError(*((struct CSWbemServices **)this + 3));
  if ( v35 )
    ((void (__fastcall *)(struct IUnknown *))v35->lpVtbl->Release)(v35);
LABEL_40:
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v6 < 0 )
    goto LABEL_79;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008230  mov     [rsp-8+arg_0], rbx
0x180008235  mov     [rsp-8+arg_10], r8
0x18000823a  push    rbp
0x18000823b  push    rsi
0x18000823c  push    rdi
0x18000823d  push    r12
0x18000823f  push    r13
0x180008241  push    r14
0x180008243  push    r15
0x180008245  lea     rbp, [rsp-27h]
0x18000824a  sub     rsp, 0B0h
0x180008251  mov     r13, r8
0x180008254  mov     r12d, edx
0x180008257  mov     r15, rcx
0x18000825a  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18000825f  test    r13, r13
0x180008262  jz      loc_1800087E5
0x180008268  test    r12d, r12d
0x18000826b  js      loc_1800087E5
0x180008271  mov     edi, 80041001h
0x180008276  mov     r14, [r15+70h]
0x18000827a  test    r14, r14
0x18000827d  jz      loc_1800087EA
0x180008283  xor     esi, esi
0x180008285  mov     [rbp+57h+var_40], rsi
0x180008289  mov     r14, [r14+80h]
0x180008290  test    r14, r14
0x180008293  jz      loc_18000855D
0x180008299  mov     rax, [r14]
0x18000829c  mov     rcx, r14
0x18000829f  mov     rax, [rax+8]
0x1800082a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082a8  mov     [rbp+57h+var_40], r14
0x1800082ac  mov     [rbp+57h+var_70], rsi
0x1800082b0  mov     [rbp+57h+var_48], rsi
0x1800082b4  mov     [rbp+57h+arg_18], sil
0x1800082b8  cmp     cs:?s_bIsNT@CSWbemSecurity@@0_NA, sil; bool CSWbemSecurity::s_bIsNT
0x1800082bf  jz      short loc_180008301
0x1800082c1  mov     rbx, [r15+70h]
0x1800082c5  mov     [rbp+57h+var_80], rbx
0x1800082c9  mov     rax, [rbx+78h]
0x1800082cd  test    rax, rax
0x1800082d0  jz      short loc_1800082DB
0x1800082d2  cmp     [rax+141h], sil
0x1800082d9  jnz     short loc_180008301
0x1800082db  mov     rcx, [rbx+20h]
0x1800082df  test    rcx, rcx
0x1800082e2  jz      short loc_180008301
0x1800082e4  mov     [rbp+57h+var_68], esi
0x1800082e7  mov     rax, [rcx]
0x1800082ea  lea     rdx, [rbp+57h+var_68]
0x1800082ee  mov     rax, [rax+48h]
0x1800082f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082f7  cmp     [rbp+57h+var_68], 0
0x1800082fb  jg      loc_1800085CA
0x180008301  mov     rax, [r14]
0x180008304  lea     rdx, [rbp+57h+var_70]
0x180008308  mov     rcx, r14
0x18000830b  mov     rax, [rax+30h]
0x18000830f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008314  mov     edi, eax
0x180008316  test    eax, eax
0x180008318  jnz     loc_180008533
0x18000831e  mov     rsi, [rbp+57h+var_70]
0x180008322  test    rsi, rsi
0x180008325  jz      loc_1800083F7
0x18000832b  mov     r13, [r15+70h]
0x18000832f  mov     rbx, [r13+80h]
0x180008336  test    rbx, rbx
0x180008339  jz      loc_1800083F3
0x18000833f  xor     eax, eax
0x180008341  mov     [rbp+57h+var_90], eax
0x180008344  mov     [rbp+57h+var_8C], eax
0x180008347  mov     [rbp+57h+var_80], rax
0x18000834b  mov     rax, [rbx]
0x18000834e  lea     r8, [rbp+57h+var_80]
0x180008352  lea     rdx, IID_IClientSecurity
0x180008359  mov     rcx, rbx
0x18000835c  mov     rax, [rax]
0x18000835f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008364  mov     edi, eax
0x180008366  test    eax, eax
0x180008368  jnz     short loc_1800083D6
0x18000836a  xor     r8d, r8d
0x18000836d  mov     dword ptr [rbp+57h+Token], r8d
0x180008371  mov     [rbp+57h+var_50], r8d
0x180008375  mov     [rbp+57h+var_54], r8d
0x180008379  mov     rcx, [rbp+57h+var_80]
0x18000837d  mov     rax, [rcx]
0x180008380  lea     rdx, [rbp+57h+var_54]
0x180008384  mov     [rsp+0E0h+var_A0], rdx
0x180008389  mov     [rsp+0E0h+var_A8], r8
0x18000838e  lea     rdx, [rbp+57h+var_8C]
0x180008392  mov     [rsp+0E0h+var_B0], rdx
0x180008397  lea     rdx, [rbp+57h+var_90]
0x18000839b  mov     [rsp+0E0h+var_B8], rdx
0x1800083a0  mov     [rsp+0E0h+ReturnLength], r8
0x1800083a5  lea     r9, [rbp+57h+var_50]
0x1800083a9  lea     r8, [rbp+57h+Token]
0x1800083ad  mov     rdx, rbx
0x1800083b0  mov     rax, [rax+18h]
0x1800083b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083b9  mov     edi, eax
0x1800083bb  cmp     eax, 800706D2h
0x1800083c0  jz      loc_1800087C2
0x1800083c6  mov     rcx, [rbp+57h+var_80]
0x1800083ca  mov     rax, [rcx]
0x1800083cd  mov     rax, [rax+10h]
0x1800083d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083d6  test    edi, edi
0x1800083d8  jnz     short loc_1800083F3
0x1800083da  mov     rcx, [r13+78h]; this
0x1800083de  test    rcx, rcx
0x1800083e1  jz      short loc_1800083F3
0x1800083e3  mov     r9d, [rbp+57h+var_8C]; enum WbemImpersonationLevelEnum
0x1800083e7  mov     r8d, [rbp+57h+var_90]; enum WbemAuthenticationLevelEnum
0x1800083eb  mov     rdx, rsi; struct IUnknown *
0x1800083ee  call    ?SecureProxy@CSWbemProxyCache@@QEAAXPEAUIUnknown@@W4WbemAuthenticationLevelEnum@@W4WbemImpersonationLevelEnum@@@Z; CSWbemProxyCache::SecureProxy(IUnknown *,WbemAuthenticationLevelEnum,WbemImpersonationLevelEnum)
0x1800083f3  mov     r13, [rbp+57h+arg_10]
0x1800083f7  mov     rcx, [rbp+57h+var_70]
0x1800083fb  mov     rax, [rcx]
0x1800083fe  mov     rax, [rax+18h]
0x180008402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008407  mov     edi, eax
0x180008409  test    eax, eax
0x18000840b  jnz     loc_180008533
0x180008411  mov     rcx, [rbp+57h+var_70]
0x180008415  mov     rax, [rcx]
0x180008418  mov     r8d, r12d
0x18000841b  mov     edx, 0FFFFFFFFh
0x180008420  mov     rax, [rax+38h]
0x180008424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008429  test    eax, eax
0x18000842b  jnz     loc_1800085A6
0x180008431  xor     esi, esi
0x180008433  mov     [rbp+57h+Token], rsi
0x180008437  mov     dword ptr [rbp+57h+arg_10], esi
0x18000843a  mov     rcx, [rbp+57h+var_70]
0x18000843e  mov     rax, [rcx]
0x180008441  lea     r9, [rbp+57h+arg_10]
0x180008445  mov     [rsp+0E0h+ReturnLength], r9
0x18000844a  lea     r9, [rbp+57h+Token]
0x18000844e  mov     edx, 0FFFFFFFFh
0x180008453  mov     r8d, 1
0x180008459  mov     rax, [rax+20h]
0x18000845d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008462  mov     edi, eax
0x180008464  test    eax, eax
0x180008466  jnz     loc_180008597
0x18000846c  cmp     dword ptr [rbp+57h+arg_10], eax
0x18000846f  jbe     loc_18000851D
0x180008475  mov     rcx, [rbp+57h+Token]
0x180008479  test    rcx, rcx
0x18000847c  jz      loc_180008521
0x180008482  mov     ecx, 78h ; 'x'
0x180008487  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000848d  mov     [rbp+57h+var_80], rax
0x180008491  test    rax, rax
0x180008494  jz      loc_1800085B8
0x18000849a  mov     byte ptr [rsp+0E0h+ReturnLength], dil; bool
0x18000849f  mov     r9, [r15+70h]; struct CSWbemSecurity *
0x1800084a3  mov     r8, [rbp+57h+Token]; struct IWbemClassObject *
0x1800084a7  mov     rdx, [r15+18h]; struct CSWbemServices *
0x1800084ab  mov     rcx, rax; this
0x1800084ae  call    ??0CSWbemObject@@QEAA@PEAVCSWbemServices@@PEAUIWbemClassObject@@PEAVCSWbemSecurity@@_N@Z; CSWbemObject::CSWbemObject(CSWbemServices *,IWbemClassObject *,CSWbemSecurity *,bool)
0x1800084b3  mov     rbx, rax
0x1800084b6  mov     [rbp+57h+var_80], rbx
0x1800084ba  test    rbx, rbx
0x1800084bd  jz      short loc_1800084CF
0x1800084bf  mov     rax, [rbx]
0x1800084c2  mov     rcx, rbx
0x1800084c5  mov     rax, [rax+8]
0x1800084c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084ce  nop
0x1800084cf  test    rbx, rbx
0x1800084d2  jz      loc_1800085C0
0x1800084d8  mov     rax, [rbx]
0x1800084db  mov     r8, r13
0x1800084de  lea     rdx, IID_ISWbemObject
0x1800084e5  mov     rcx, rbx
0x1800084e8  mov     rax, [rax]
0x1800084eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084f0  mov     edi, eax
0x1800084f2  test    eax, eax
0x1800084f4  js      short loc_180008508
0x1800084f6  mov     rax, [rbx]
0x1800084f9  mov     rcx, rbx
0x1800084fc  mov     rax, [rax+10h]
0x180008500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008505  mov     rbx, rsi
0x180008508  test    rbx, rbx
0x18000850b  jz      short loc_18000851D
0x18000850d  mov     rax, [rbx]
0x180008510  mov     rcx, rbx
0x180008513  mov     rax, [rax+10h]
0x180008517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000851c  nop
0x18000851d  mov     rcx, [rbp+57h+Token]
0x180008521  test    rcx, rcx
0x180008524  jz      short loc_180008533
0x180008526  mov     rax, [rcx]
0x180008529  mov     rax, [rax+10h]
0x18000852d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008532  nop
0x180008533  cmp     [rbp+57h+arg_18], 0
0x180008537  jnz     loc_1800087D7
0x18000853d  mov     rcx, [r15+18h]; this
0x180008541  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x180008546  nop
0x180008547  mov     rcx, [rbp+57h+var_70]
0x18000854b  test    rcx, rcx
0x18000854e  jz      short loc_18000855D
0x180008550  mov     rax, [rcx]
0x180008553  mov     rax, [rax+10h]
0x180008557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000855c  nop
0x18000855d  test    r14, r14
0x180008560  jz      short loc_180008572
0x180008562  mov     rax, [r14]
0x180008565  mov     rcx, r14
0x180008568  mov     rax, [rax+10h]
0x18000856c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008571  nop
0x180008572  test    edi, edi
0x180008574  js      loc_1800087EA
0x18000857a  mov     eax, edi
0x18000857c  mov     rbx, [rsp+0E0h+arg_0]
0x180008584  add     rsp, 0B0h
0x18000858b  pop     r15
0x18000858d  pop     r14
0x18000858f  pop     r13
0x180008591  pop     r12
0x180008593  pop     rdi
0x180008594  pop     rsi
0x180008595  pop     rbp
0x180008596  retn
0x180008597  cmp     eax, 1
0x18000859a  jnz     short loc_18000851D
0x18000859c  mov     edi, 80041008h
0x1800085a1  jmp     loc_18000851D
0x1800085a6  mov     edi, 80041008h
0x1800085ab  cmp     eax, 1
0x1800085ae  cmovz   eax, edi
0x1800085b1  mov     edi, eax
0x1800085b3  jmp     loc_180008533
0x1800085b8  mov     rbx, rsi
0x1800085bb  jmp     loc_1800084B6
0x1800085c0  mov     edi, 80041006h
0x1800085c5  jmp     loc_180008508
0x1800085ca  mov     [rbp+57h+TokenHandle], rsi
0x1800085ce  mov     [rbp+57h+TokenInformation], 2
0x1800085d5  call    cs:__imp_GetCurrentThread
0x1800085db  mov     rcx, rax; ThreadHandle
0x1800085de  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800085e2  mov     edx, 2000Eh; DesiredAccess
0x1800085e7  mov     r8d, 1; OpenAsSelf
0x1800085ed  call    cs:__imp_OpenThreadToken
0x1800085f3  test    eax, eax
0x1800085f5  jz      loc_180008719
0x1800085fb  mov     rax, [rbp+57h+TokenHandle]
0x1800085ff  mov     [rbp+57h+var_48], rax
0x180008603  mov     [rbp+57h+var_58], esi
0x180008606  lea     rcx, [rbp+57h+var_58]
0x18000860a  mov     [rsp+0E0h+ReturnLength], rcx; ReturnLength
0x18000860f  mov     r9d, 4; TokenInformationLength
0x180008615  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180008619  mov     edx, 9; TokenInformationClass
0x18000861e  mov     rcx, rax; TokenHandle
0x180008621  call    cs:__imp_GetTokenInformation
0x180008627  mov     [rbp+57h+Token], rsi
0x18000862b  lea     rcx, ?g_csSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008632  call    cs:__imp_EnterCriticalSection
0x180008638  lea     r8, [rbp+57h+Token]; void **
0x18000863c  mov     edx, [rbp+57h+TokenInformation]; enum _SECURITY_IMPERSONATION_LEVEL
0x18000863f  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180008643  call    ?DuplicateTokenSameAcl@@YAHPEAXW4_SECURITY_IMPERSONATION_LEVEL@@PEAPEAX@Z; DuplicateTokenSameAcl(void *,_SECURITY_IMPERSONATION_LEVEL,void * *)
0x180008648  mov     esi, eax
0x18000864a  lea     rcx, ?g_csSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008651  call    cs:__imp_LeaveCriticalSection
0x180008657  test    esi, esi
0x180008659  jz      loc_180008789
0x18000865f  mov     rdx, [rbx+20h]; struct CSWbemPrivilegeSet *
0x180008663  mov     rcx, [rbp+57h+Token]; TokenHandle
0x180008667  call    ?AdjustTokenPrivileges@CSWbemSecurity@@SAHPEAXPEAVCSWbemPrivilegeSet@@@Z; CSWbemSecurity::AdjustTokenPrivileges(void *,CSWbemPrivilegeSet *)
0x18000866c  mov     esi, eax
0x18000866e  test    eax, eax
0x180008670  jz      loc_180008789
0x180008676  mov     rdx, [rbp+57h+Token]; Token
0x18000867a  xor     ecx, ecx; Thread
0x18000867c  call    cs:__imp_SetThreadToken
0x180008682  test    eax, eax
0x180008684  jz      loc_180008715
0x18000868a  mov     [rbp+57h+arg_18], 1
0x18000868e  mov     [rbp+57h+var_8C], 0
0x180008695  mov     [rbp+57h+var_90], 0
0x18000869c  lea     r8, [rbp+57h+var_90]; unsigned int *
0x1800086a0  lea     rdx, [rbp+57h+var_8C]; unsigned int *
0x1800086a4  mov     rcx, [rbx+80h]; struct IUnknown *
0x1800086ab  call    ?GetAuthImp@@YAJPEAUIUnknown@@PEAK1@Z; GetAuthImp(IUnknown *,ulong *,ulong *)
0x1800086b0  test    eax, eax
  ... truncated ...
```
