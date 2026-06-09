# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180008698`
- end: `0x1800087dd`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `325`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b3e0`

## callees

- `0x180008698`
- `0x18000b8ac`
- `0x18000ba50`
- `0x18000d700`
- `0x18000e010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180008773`
- `KERNEL32!SetLastError` at `0x180008773`
- `KERNEL32!GetLastError` at `0x18000873f`
- `KERNEL32!GetLastError` at `0x18000873f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800087b6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800087b6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800086f9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800086f9`
- `KERNEL32!SetThreadpoolTimer` at `0x18000879e`
- `KERNEL32!SetThreadpoolTimer` at `0x18000879e`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000875a`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000875a`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v14; // [rsp+2Ch] [rbp-4Ch]
  __int16 v15; // [rsp+2Eh] [rbp-4Ah]
  int v16; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v15 = 0;
    Source = a2;
    v14 = a3;
    v16 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[29], &Source, 0xCu);
    v8 = (struct _TP_TIMER **)&pv[7];
    if ( !LOBYTE(pv[8].Ptr) )
    {
      if ( !*v8 )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (struct _TP_TIMER **)&pv[7],
          ThreadpoolTimer);
        SetLastError(LastError);
      }
      v11 = *v8;
      if ( *v8 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v11, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x180008698  push    rbx
0x18000869a  push    rbp
0x18000869b  push    rsi
0x18000869c  push    rdi
0x18000869d  push    r14
0x18000869f  push    r15
0x1800086a1  sub     rsp, 48h
0x1800086a5  mov     rax, cs:__security_cookie
0x1800086ac  xor     rax, rsp
0x1800086af  mov     [rsp+78h+var_40], rax
0x1800086b4  xor     r15d, r15d
0x1800086b7  mov     r14d, r9d
0x1800086ba  movzx   ebp, r8w
0x1800086be  mov     ebx, edx
0x1800086c0  mov     rdi, rcx
0x1800086c3  cmp     [rcx], r15b
0x1800086c6  jz      loc_1800087C2
0x1800086cc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r15b; bool wil::details::g_processShutdownInProgress
0x1800086d3  jnz     loc_1800087C2
0x1800086d9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800086e0  test    rax, rax
0x1800086e3  jz      short loc_1800086F2
0x1800086e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ea  test    al, al
0x1800086ec  jnz     loc_1800087C2
0x1800086f2  lea     rsi, [rdi+28h]
0x1800086f6  mov     rcx, rsi; SRWLock
0x1800086f9  call    cs:__imp_AcquireSRWLockExclusive
0x180008700  nop     dword ptr [rax+rax+00h]
0x180008705  lea     rcx, [rdi+0E8h]; this
0x18000870c  mov     [rsp+78h+var_4A], r15w
0x180008712  mov     r8d, 0Ch; SourceSize
0x180008718  mov     [rsp+78h+Source], ebx
0x18000871c  lea     rdx, [rsp+78h+Source]; Source
0x180008721  mov     [rsp+78h+var_4C], bp
0x180008726  mov     [rsp+78h+var_48], r14d
0x18000872b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180008730  lea     r14, [rdi+38h]
0x180008734  cmp     [rdi+40h], r15b
0x180008738  jnz     short loc_1800087AE
0x18000873a  cmp     [r14], r15
0x18000873d  jnz     short loc_18000877F
0x18000873f  call    cs:__imp_GetLastError
0x180008746  nop     dword ptr [rax+rax+00h]
0x18000874b  xor     r8d, r8d; pcbe
0x18000874e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008755  mov     rdx, rdi; pv
0x180008758  mov     ebx, eax
0x18000875a  call    cs:__imp_CreateThreadpoolTimer
0x180008761  nop     dword ptr [rax+rax+00h]
0x180008766  mov     rdx, rax
0x180008769  mov     rcx, r14
0x18000876c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180008771  mov     ecx, ebx; dwErrCode
0x180008773  call    cs:__imp_SetLastError
0x18000877a  nop     dword ptr [rax+rax+00h]
0x18000877f  mov     rcx, [r14]; pti
0x180008782  test    rcx, rcx
0x180008785  jz      short loc_1800087AE
0x180008787  mov     r9d, 4E2h; msWindowLength
0x18000878d  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180008796  xor     r8d, r8d; msPeriod
0x180008799  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000879e  call    cs:__imp_SetThreadpoolTimer
0x1800087a5  nop     dword ptr [rax+rax+00h]
0x1800087aa  mov     byte ptr [rdi+40h], 1
0x1800087ae  test    rsi, rsi
0x1800087b1  jz      short loc_1800087C2
0x1800087b3  mov     rcx, rsi; SRWLock
0x1800087b6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800087bd  nop     dword ptr [rax+rax+00h]
0x1800087c2  mov     rcx, [rsp+78h+var_40]
0x1800087c7  xor     rcx, rsp; StackCookie
0x1800087ca  call    __security_check_cookie
0x1800087cf  add     rsp, 48h
0x1800087d3  pop     r15
0x1800087d5  pop     r14
0x1800087d7  pop     rdi
0x1800087d8  pop     rsi
0x1800087d9  pop     rbp
0x1800087da  pop     rbx
0x1800087db  retn
```
