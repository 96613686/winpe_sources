# COleScript::SetScriptSite(IActiveScriptSite *)

- ea: `0x180041a70`
- end: `0x180041cdf`
- name: `?SetScriptSite@COleScript@@UEAAJPEAUIActiveScriptSite@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(COleScript *__hidden this, struct IActiveScriptSite *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800132c0`
- `0x180013708`
- `0x18001b588`
- `0x18001e2e4`
- `0x18002d5f8`
- `0x180036c6c`
- `0x180039814`
- `0x18003e094`
- `0x1800412e0`
- `0x180041a70`
- `0x180042fe0`
- `0x18007912c`
- `0x18007a010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180041cb2`
- `KERNEL32!GetTickCount64` at `0x180041cb2`
- `KERNEL32!GetCurrentThreadId` at `0x180041aa4`
- `KERNEL32!GetCurrentThreadId` at `0x180041aa4`
- `OLE32!CoCreateInstance` at `0x180041c07`
- `OLE32!CoCreateInstance` at `0x180041c07`

## pseudocode

```c
int __fastcall COleScript::SetScriptSite(COleScript *this, struct IActiveScriptSite *a2)
{
  int result; // eax
  CSession **v5; // r14
  struct IActiveScriptSiteVtbl *lpVtbl; // rax
  int v7; // eax
  __int64 v8; // rax
  int v9; // ebp
  int i; // esi
  LPVOID *ppv; // rbx
  const char *v12; // rdx
  struct IActiveScriptSiteVtbl *v13; // rax
  RegistryBasedThrottle *v14; // rdi
  __int64 v15; // rbx
  unsigned int v16; // [rsp+68h] [rbp+10h] BYREF
  __int64 v17; // [rsp+70h] [rbp+18h] BYREF
  __int64 v18; // [rsp+78h] [rbp+20h] BYREF

  if ( !a2 )
    return -2147467261;
  if ( *((_QWORD *)this + 20) )
    return -2147418113;
  v5 = (CSession **)((char *)this + 640);
  *((_DWORD *)this + 61) = GetCurrentThreadId();
  result = CSession::Create((struct CSession **)this + 80, this, a2);
  if ( result < 0 )
  {
    *((_DWORD *)this + 61) = -1;
    return result;
  }
  *((_QWORD *)this + 20) = a2;
  ((void (__fastcall *)(struct IActiveScriptSite *))a2->lpVtbl->AddRef)(a2);
  *(_QWORD *)((char *)this + 692) = 0;
  lpVtbl = a2->lpVtbl;
  v16 = 0;
  if ( ((int (__fastcall *)(struct IActiveScriptSite *, unsigned int *))lpVtbl->GetLCID)(a2, &v16) >= 0
    && COleScript::SetCurrentLocale(this, v16) )
  {
    v7 = *((_DWORD *)this + 46);
    *((_DWORD *)this + 48) = v7;
    *((_DWORD *)this + 49) = v7;
  }
  COleScript::RegisterNamedItems(this);
  if ( *((_DWORD *)this + 62) )
    COleScript::ChangeScriptState(this, SCRIPTSTATE_INITIALIZED);
  *((_DWORD *)this + 200) = *((_DWORD *)this + 162)
                          & 0xFFFFFFFD
                          ^ (*((_DWORD *)this + 200)
                           ^ *((_DWORD *)this + 162))
                          & 0xFFFFFFFC;
  if ( (unsigned int)COleScript::FDebuggerEnabled(this) )
  {
    if ( !(unsigned int)COleScript::DisableInterrupts(this) )
      return -2147467259;
    v8 = *((_QWORD *)this + 82);
    if ( v8 )
    {
      v9 = *(_DWORD *)(v8 + 28);
      if ( v9 > 0 )
      {
        for ( i = 0; i < v9; ++i )
          COleScript::DbgRegisterScriptBlock(
            this,
            *(struct CScriptBody **)(*(_DWORD *)(*((_QWORD *)this + 82) + 12LL) * i
                                   + *(_QWORD *)(*((_QWORD *)this + 82) + 16LL)
                                   + 8LL));
      }
    }
    COleScript::EnableInterrupts(this);
  }
  ppv = (LPVOID *)((char *)this + 872);
  if ( !*ppv )
    CoCreateInstance(&CLSID_VSA_IEC, 0, 1u, &IID_ISystemDebugEventFire, ppv);
  if ( *ppv )
    CSession::StartDebugEvents(*v5, (struct ISystemDebugEventFire *)*ppv);
  v17 = 0;
  if ( (unsigned int)((__int64 (__fastcall *)(__int64 *, __int64 *))QueryProtectedPolicyPtr)(
                       PPID_ProhibitUnsafeExtensions,
                       &v17)
    && v17 == 2 )
  {
    v13 = a2->lpVtbl;
    v18 = 0;
    if ( ((__int64 (__fastcall *)(struct IActiveScriptSite *, GUID *, __int64 *))v13->QueryInterface)(
           a2,
           &IID_IActiveScriptSiteDebugEx,
           &v18) < 0 )
      SuppressUnsafeExtensionPolicy();
    else
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v14 = g_pTraceLoggingClient;
  if ( *((_DWORD *)g_pTraceLoggingClient + 76)
    || (int)RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry((BYTE *)g_pTraceLoggingClient, v12) >= 0 )
  {
    v15 = *((_QWORD *)v14 + 37);
    if ( GetTickCount64() - v15 <= *((_QWORD *)v14 + 3) )
      COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180041a70  push    rbx
0x180041a72  push    rbp
0x180041a73  push    rsi
0x180041a74  push    rdi
0x180041a75  push    r14
0x180041a77  sub     rsp, 30h
0x180041a7b  mov     rdi, rdx
0x180041a7e  mov     rbx, rcx
0x180041a81  test    rdx, rdx
0x180041a84  jnz     short loc_180041A90
0x180041a86  mov     eax, 80004003h
0x180041a8b  jmp     loc_180041CD3
0x180041a90  cmp     qword ptr [rcx+0A0h], 0
0x180041a98  jz      short loc_180041AA4
0x180041a9a  mov     eax, 8000FFFFh
0x180041a9f  jmp     loc_180041CD3
0x180041aa4  call    cs:__imp_GetCurrentThreadId
0x180041aab  nop     dword ptr [rax+rax+00h]
0x180041ab0  lea     r14, [rbx+280h]
0x180041ab7  mov     r8, rdi; struct IActiveScriptSite *
0x180041aba  mov     rcx, r14; struct CSession **
0x180041abd  mov     [rbx+0F4h], eax
0x180041ac3  mov     rdx, rbx; struct COleScript *
0x180041ac6  call    ?Create@CSession@@SAJPEAPEAV1@PEAVCOleScript@@PEAUIActiveScriptSite@@@Z; CSession::Create(CSession * *,COleScript *,IActiveScriptSite *)
0x180041acb  test    eax, eax
0x180041acd  jns     short loc_180041ADE
0x180041acf  mov     dword ptr [rbx+0F4h], 0FFFFFFFFh
0x180041ad9  jmp     loc_180041CD3
0x180041ade  mov     [rbx+0A0h], rdi
0x180041ae5  mov     rcx, rdi
0x180041ae8  mov     rax, [rdi]
0x180041aeb  mov     rax, [rax+8]
0x180041aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041af4  mov     qword ptr [rbx+2B4h], 0
0x180041aff  lea     rdx, [rsp+58h+arg_8]
0x180041b04  mov     rax, [rdi]
0x180041b07  mov     rcx, rdi
0x180041b0a  mov     [rsp+58h+arg_8], 0
0x180041b12  mov     rax, [rax+18h]
0x180041b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b1b  test    eax, eax
0x180041b1d  js      short loc_180041B41
0x180041b1f  mov     edx, [rsp+58h+arg_8]; unsigned int
0x180041b23  mov     rcx, rbx; this
0x180041b26  call    ?SetCurrentLocale@COleScript@@QEAAHK@Z; COleScript::SetCurrentLocale(ulong)
0x180041b2b  test    eax, eax
0x180041b2d  jz      short loc_180041B41
0x180041b2f  mov     eax, [rbx+0B8h]
0x180041b35  mov     [rbx+0C0h], eax
0x180041b3b  mov     [rbx+0C4h], eax
0x180041b41  mov     rcx, rbx; this
0x180041b44  call    ?RegisterNamedItems@COleScript@@AEAAJXZ; COleScript::RegisterNamedItems(void)
0x180041b49  cmp     dword ptr [rbx+0F8h], 0
0x180041b50  jz      short loc_180041B5F
0x180041b52  mov     edx, 5; enum tagSCRIPTSTATE
0x180041b57  mov     rcx, rbx; this
0x180041b5a  call    ?ChangeScriptState@COleScript@@AEAAXW4tagSCRIPTSTATE@@@Z; COleScript::ChangeScriptState(tagSCRIPTSTATE)
0x180041b5f  mov     ecx, [rbx+288h]
0x180041b65  mov     eax, ecx
0x180041b67  xor     eax, [rbx+320h]
0x180041b6d  and     ecx, 0FFFFFFFDh
0x180041b70  and     eax, 0FFFFFFFCh
0x180041b73  xor     eax, ecx
0x180041b75  mov     rcx, rbx; this
0x180041b78  mov     [rbx+320h], eax
0x180041b7e  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x180041b83  test    eax, eax
0x180041b85  jz      short loc_180041BE1
0x180041b87  mov     rcx, rbx; this
0x180041b8a  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x180041b8f  test    eax, eax
0x180041b91  jnz     short loc_180041B9D
0x180041b93  mov     eax, 80004005h
0x180041b98  jmp     loc_180041CD3
0x180041b9d  mov     rax, [rbx+290h]
0x180041ba4  test    rax, rax
0x180041ba7  jz      short loc_180041BD9
0x180041ba9  mov     ebp, [rax+1Ch]
0x180041bac  test    ebp, ebp
0x180041bae  jle     short loc_180041BD9
0x180041bb0  xor     esi, esi
0x180041bb2  mov     rdx, [rbx+290h]
0x180041bb9  mov     eax, esi
0x180041bbb  imul    eax, [rdx+0Ch]
0x180041bbf  mov     rdx, [rdx+10h]
0x180041bc3  movsxd  rcx, eax
0x180041bc6  mov     rdx, [rcx+rdx+8]; struct CScriptBody *
0x180041bcb  mov     rcx, rbx; this
0x180041bce  call    ?DbgRegisterScriptBlock@COleScript@@QEAAJPEAVCScriptBody@@@Z; COleScript::DbgRegisterScriptBlock(CScriptBody *)
0x180041bd3  inc     esi
0x180041bd5  cmp     esi, ebp
0x180041bd7  jl      short loc_180041BB2
0x180041bd9  mov     rcx, rbx; this
0x180041bdc  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x180041be1  add     rbx, 368h
0x180041be8  cmp     qword ptr [rbx], 0
0x180041bec  jnz     short loc_180041C13
0x180041bee  xor     edx, edx; pUnkOuter
0x180041bf0  mov     [rsp+58h+ppv], rbx; ppv
0x180041bf5  lea     r9, IID_ISystemDebugEventFire; riid
0x180041bfc  lea     rcx, CLSID_VSA_IEC; rclsid
0x180041c03  lea     r8d, [rdx+1]; dwClsContext
0x180041c07  call    cs:__imp_CoCreateInstance
0x180041c0e  nop     dword ptr [rax+rax+00h]
0x180041c13  mov     rdx, [rbx]; struct ISystemDebugEventFire *
0x180041c16  test    rdx, rdx
0x180041c19  jz      short loc_180041C23
0x180041c1b  mov     rcx, [r14]; this
0x180041c1e  call    ?StartDebugEvents@CSession@@QEAAJPEAUISystemDebugEventFire@@@Z; CSession::StartDebugEvents(ISystemDebugEventFire *)
0x180041c23  mov     rax, cs:QueryProtectedPolicyPtr
0x180041c2a  lea     rdx, [rsp+58h+arg_10]
0x180041c2f  lea     rcx, PPID_ProhibitUnsafeExtensions
0x180041c36  mov     [rsp+58h+arg_10], 0
0x180041c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c44  test    eax, eax
0x180041c46  jz      short loc_180041C8F
0x180041c48  cmp     [rsp+58h+arg_10], 2
0x180041c4e  jnz     short loc_180041C8F
0x180041c50  mov     rax, [rdi]
0x180041c53  lea     r8, [rsp+58h+arg_18]
0x180041c58  lea     rdx, IID_IActiveScriptSiteDebugEx
0x180041c5f  mov     [rsp+58h+arg_18], 0
0x180041c68  mov     rcx, rdi
0x180041c6b  mov     rax, [rax]
0x180041c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c73  test    eax, eax
0x180041c75  js      short loc_180041C8A
0x180041c77  mov     rcx, [rsp+58h+arg_18]
0x180041c7c  mov     rax, [rcx]
0x180041c7f  mov     rax, [rax+10h]
0x180041c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c88  jmp     short loc_180041C8F
0x180041c8a  call    SuppressUnsafeExtensionPolicy
0x180041c8f  mov     rdi, cs:g_pTraceLoggingClient
0x180041c96  cmp     dword ptr [rdi+130h], 0
0x180041c9d  jnz     short loc_180041CAB
0x180041c9f  mov     rcx, rdi; this
0x180041ca2  call    ?ReadLoggedLocalTickCountFromRegistry@RegistryBasedThrottle@@AEAAJPEBD@Z; RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(char const *)
0x180041ca7  test    eax, eax
0x180041ca9  js      short loc_180041CD1
0x180041cab  mov     rbx, [rdi+128h]
0x180041cb2  call    cs:__imp_GetTickCount64
0x180041cb9  nop     dword ptr [rax+rax+00h]
0x180041cbe  sub     rax, rbx
0x180041cc1  cmp     rax, [rdi+18h]
0x180041cc5  ja      short loc_180041CD1
0x180041cc7  mov     cs:?s_fAlreadyLoggedTelemetryOnScriptStateStarted@COleScript@@0HA, 1; int COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted
0x180041cd1  xor     eax, eax
0x180041cd3  add     rsp, 30h
0x180041cd7  pop     r14
0x180041cd9  pop     rdi
0x180041cda  pop     rsi
0x180041cdb  pop     rbp
0x180041cdc  pop     rbx
0x180041cdd  retn
```
