# COleScript::SetScriptSite(IActiveScriptSite *)

- ea: `0x1800403a0`
- end: `0x1800405fc`
- name: `?SetScriptSite@COleScript@@UEAAJPEAUIActiveScriptSite@@@Z`
- size: `604`
- prototype: `__int64 __fastcall(COleScript *__hidden this, struct IActiveScriptSite *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180018710`
- `0x180018b50`
- `0x180020398`
- `0x180022e04`
- `0x180035710`
- `0x1800379e0`
- `0x18003c464`
- `0x18003cbbc`
- `0x18003fc2c`
- `0x1800403a0`
- `0x180041984`
- `0x180076468`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x1800405d6`
- `KERNEL32!GetTickCount64` at `0x1800405d6`
- `KERNEL32!GetCurrentThreadId` at `0x1800403d4`
- `KERNEL32!GetCurrentThreadId` at `0x1800403d4`
- `OLE32!CoCreateInstance` at `0x180040531`
- `OLE32!CoCreateInstance` at `0x180040531`

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
0x1800403a0  push    rbx
0x1800403a2  push    rbp
0x1800403a3  push    rsi
0x1800403a4  push    rdi
0x1800403a5  push    r14
0x1800403a7  sub     rsp, 30h
0x1800403ab  mov     rdi, rdx
0x1800403ae  mov     rbx, rcx
0x1800403b1  test    rdx, rdx
0x1800403b4  jnz     short loc_1800403C0
0x1800403b6  mov     eax, 80004003h
0x1800403bb  jmp     loc_1800405F1
0x1800403c0  cmp     qword ptr [rcx+0A0h], 0
0x1800403c8  jz      short loc_1800403D4
0x1800403ca  mov     eax, 8000FFFFh
0x1800403cf  jmp     loc_1800405F1
0x1800403d4  call    cs:__imp_GetCurrentThreadId
0x1800403da  lea     r14, [rbx+280h]
0x1800403e1  mov     r8, rdi; struct IActiveScriptSite *
0x1800403e4  mov     rcx, r14; struct CSession **
0x1800403e7  mov     [rbx+0F4h], eax
0x1800403ed  mov     rdx, rbx; struct COleScript *
0x1800403f0  call    ?Create@CSession@@SAJPEAPEAV1@PEAVCOleScript@@PEAUIActiveScriptSite@@@Z; CSession::Create(CSession * *,COleScript *,IActiveScriptSite *)
0x1800403f5  test    eax, eax
0x1800403f7  jns     short loc_180040408
0x1800403f9  mov     dword ptr [rbx+0F4h], 0FFFFFFFFh
0x180040403  jmp     loc_1800405F1
0x180040408  mov     [rbx+0A0h], rdi
0x18004040f  mov     rcx, rdi
0x180040412  mov     rax, [rdi]
0x180040415  mov     rax, [rax+8]
0x180040419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004041e  mov     qword ptr [rbx+2B4h], 0
0x180040429  lea     rdx, [rsp+58h+arg_8]
0x18004042e  mov     rax, [rdi]
0x180040431  mov     rcx, rdi
0x180040434  mov     [rsp+58h+arg_8], 0
0x18004043c  mov     rax, [rax+18h]
0x180040440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040445  test    eax, eax
0x180040447  js      short loc_18004046B
0x180040449  mov     edx, [rsp+58h+arg_8]; unsigned int
0x18004044d  mov     rcx, rbx; this
0x180040450  call    ?SetCurrentLocale@COleScript@@QEAAHK@Z; COleScript::SetCurrentLocale(ulong)
0x180040455  test    eax, eax
0x180040457  jz      short loc_18004046B
0x180040459  mov     eax, [rbx+0B8h]
0x18004045f  mov     [rbx+0C0h], eax
0x180040465  mov     [rbx+0C4h], eax
0x18004046b  mov     rcx, rbx; this
0x18004046e  call    ?RegisterNamedItems@COleScript@@AEAAJXZ; COleScript::RegisterNamedItems(void)
0x180040473  cmp     dword ptr [rbx+0F8h], 0
0x18004047a  jz      short loc_180040489
0x18004047c  mov     edx, 5; enum tagSCRIPTSTATE
0x180040481  mov     rcx, rbx; this
0x180040484  call    ?ChangeScriptState@COleScript@@AEAAXW4tagSCRIPTSTATE@@@Z; COleScript::ChangeScriptState(tagSCRIPTSTATE)
0x180040489  mov     ecx, [rbx+288h]
0x18004048f  mov     eax, ecx
0x180040491  xor     eax, [rbx+320h]
0x180040497  and     ecx, 0FFFFFFFDh
0x18004049a  and     eax, 0FFFFFFFCh
0x18004049d  xor     eax, ecx
0x18004049f  mov     rcx, rbx; this
0x1800404a2  mov     [rbx+320h], eax
0x1800404a8  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x1800404ad  test    eax, eax
0x1800404af  jz      short loc_18004050B
0x1800404b1  mov     rcx, rbx; this
0x1800404b4  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x1800404b9  test    eax, eax
0x1800404bb  jnz     short loc_1800404C7
0x1800404bd  mov     eax, 80004005h
0x1800404c2  jmp     loc_1800405F1
0x1800404c7  mov     rax, [rbx+290h]
0x1800404ce  test    rax, rax
0x1800404d1  jz      short loc_180040503
0x1800404d3  mov     ebp, [rax+1Ch]
0x1800404d6  test    ebp, ebp
0x1800404d8  jle     short loc_180040503
0x1800404da  xor     esi, esi
0x1800404dc  mov     rdx, [rbx+290h]
0x1800404e3  mov     eax, esi
0x1800404e5  imul    eax, [rdx+0Ch]
0x1800404e9  mov     rdx, [rdx+10h]
0x1800404ed  movsxd  rcx, eax
0x1800404f0  mov     rdx, [rcx+rdx+8]; struct CScriptBody *
0x1800404f5  mov     rcx, rbx; this
0x1800404f8  call    ?DbgRegisterScriptBlock@COleScript@@QEAAJPEAVCScriptBody@@@Z; COleScript::DbgRegisterScriptBlock(CScriptBody *)
0x1800404fd  inc     esi
0x1800404ff  cmp     esi, ebp
0x180040501  jl      short loc_1800404DC
0x180040503  mov     rcx, rbx; this
0x180040506  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x18004050b  add     rbx, 368h
0x180040512  cmp     qword ptr [rbx], 0
0x180040516  jnz     short loc_180040537
0x180040518  xor     edx, edx; pUnkOuter
0x18004051a  mov     [rsp+58h+ppv], rbx; ppv
0x18004051f  lea     r9, IID_ISystemDebugEventFire; riid
0x180040526  lea     rcx, CLSID_VSA_IEC; rclsid
0x18004052d  lea     r8d, [rdx+1]; dwClsContext
0x180040531  call    cs:__imp_CoCreateInstance
0x180040537  mov     rdx, [rbx]; struct ISystemDebugEventFire *
0x18004053a  test    rdx, rdx
0x18004053d  jz      short loc_180040547
0x18004053f  mov     rcx, [r14]; this
0x180040542  call    ?StartDebugEvents@CSession@@QEAAJPEAUISystemDebugEventFire@@@Z; CSession::StartDebugEvents(ISystemDebugEventFire *)
0x180040547  mov     rax, cs:QueryProtectedPolicyPtr
0x18004054e  lea     rdx, [rsp+58h+arg_10]
0x180040553  lea     rcx, PPID_ProhibitUnsafeExtensions
0x18004055a  mov     [rsp+58h+arg_10], 0
0x180040563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040568  test    eax, eax
0x18004056a  jz      short loc_1800405B3
0x18004056c  cmp     [rsp+58h+arg_10], 2
0x180040572  jnz     short loc_1800405B3
0x180040574  mov     rax, [rdi]
0x180040577  lea     r8, [rsp+58h+arg_18]
0x18004057c  lea     rdx, IID_IActiveScriptSiteDebugEx
0x180040583  mov     [rsp+58h+arg_18], 0
0x18004058c  mov     rcx, rdi
0x18004058f  mov     rax, [rax]
0x180040592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040597  test    eax, eax
0x180040599  js      short loc_1800405AE
0x18004059b  mov     rcx, [rsp+58h+arg_18]
0x1800405a0  mov     rax, [rcx]
0x1800405a3  mov     rax, [rax+10h]
0x1800405a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405ac  jmp     short loc_1800405B3
0x1800405ae  call    SuppressUnsafeExtensionPolicy
0x1800405b3  mov     rdi, cs:g_pTraceLoggingClient
0x1800405ba  cmp     dword ptr [rdi+130h], 0
0x1800405c1  jnz     short loc_1800405CF
0x1800405c3  mov     rcx, rdi; this
0x1800405c6  call    ?ReadLoggedLocalTickCountFromRegistry@RegistryBasedThrottle@@AEAAJPEBD@Z; RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(char const *)
0x1800405cb  test    eax, eax
0x1800405cd  js      short loc_1800405EF
0x1800405cf  mov     rbx, [rdi+128h]
0x1800405d6  call    cs:__imp_GetTickCount64
0x1800405dc  sub     rax, rbx
0x1800405df  cmp     rax, [rdi+18h]
0x1800405e3  ja      short loc_1800405EF
0x1800405e5  mov     cs:?s_fAlreadyLoggedTelemetryOnScriptStateStarted@COleScript@@0HA, 1; int COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted
0x1800405ef  xor     eax, eax
0x1800405f1  add     rsp, 30h
0x1800405f5  pop     r14
0x1800405f7  pop     rdi
0x1800405f8  pop     rsi
0x1800405f9  pop     rbp
0x1800405fa  pop     rbx
0x1800405fb  retn
```
