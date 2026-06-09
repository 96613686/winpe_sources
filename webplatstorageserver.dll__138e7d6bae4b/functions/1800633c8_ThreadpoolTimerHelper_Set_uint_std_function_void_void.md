# ThreadpoolTimerHelper::Set(uint,std::function<void (void)> &&)

- ea: `0x1800633c8`
- end: `0x1800634f8`
- name: `?Set@ThreadpoolTimerHelper@@QEAAJI$$QEAV?$function@$$A6AXXZ@std@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180061704`
- `0x180063318`
- `0x180063690`
- `0x180063a68`

## callees

- `0x180006fa4`
- `0x180007010`
- `0x18000e1c0`
- `0x18001dd98`
- `0x180062f54`
- `0x1800633c8`
- `0x180063500`
- `0x1800814bc`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800634e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800634e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800633ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800633ee`

## string_xrefs

- `0x18006340a`: `onecoreuap\inetcore\inc\ThreadpoolHelpers.hxx`

## pseudocode

```c
__int64 __fastcall ThreadpoolTimerHelper::Set(ThreadpoolTimerHelper *pv, unsigned int a2, __int64 a3)
{
  __int64 v4; // rbp
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v7; // r9
  _QWORD *v9; // rax
  _QWORD *v10; // rsi
  __int64 v11; // rcx
  _DWORD *v12; // rbx
  std::_Ref_count_base *v13; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF
  __int64 v16; // [rsp+58h] [rbp+20h] BYREF

  v4 = a2;
  ThreadpoolTimerHelper::Cancel(pv);
  ThreadpoolTimer = CreateThreadpoolTimer(ThreadpoolTimerHelper::s_Callback, pv, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    pv,
    ThreadpoolTimer);
  if ( !*(_QWORD *)pv )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x53,
             (unsigned int)"onecoreuap\\inetcore\\inc\\ThreadpoolHelpers.hxx",
             v7);
  v9 = operator new(0x48u);
  v10 = v9;
  v9[7] = 0;
  v11 = *(_QWORD *)(a3 + 56);
  if ( v11 )
  {
    if ( v11 == a3 )
    {
      v9[7] = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v11 + 8LL))(v11, v9);
      std::_Func_class<void,>::_Tidy(a3);
    }
    else
    {
      v9[7] = v11;
      *(_QWORD *)(a3 + 56) = 0;
    }
  }
  *((_DWORD *)v10 + 16) = 0;
  v12 = operator new(0x18u);
  v12[2] = 1;
  v12[3] = 1;
  *(_QWORD *)v12 = &std::_Ref_count<ThreadpoolTimerHelper::CallbackData>::`vftable';
  *((_QWORD *)v12 + 2) = v10;
  v16 = 0;
  std::_Temporary_owner<ThreadpoolTimerHelper::CallbackData>::~_Temporary_owner<ThreadpoolTimerHelper::CallbackData>(&v16);
  *((_QWORD *)pv + 1) = v10;
  v13 = (std::_Ref_count_base *)*((_QWORD *)pv + 2);
  *((_QWORD *)pv + 2) = v12;
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  pftDueTime = (struct _FILETIME)(-10000 * v4);
  SetThreadpoolTimer(*(PTP_TIMER *)pv, &pftDueTime, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x1800633c8  mov     [rsp+arg_8], rbx
0x1800633cd  push    rbp
0x1800633ce  push    rsi
0x1800633cf  push    rdi
0x1800633d0  sub     rsp, 20h
0x1800633d4  mov     rbx, r8
0x1800633d7  mov     ebp, edx
0x1800633d9  mov     rdi, rcx
0x1800633dc  call    ?Cancel@ThreadpoolTimerHelper@@QEAAXXZ; ThreadpoolTimerHelper::Cancel(void)
0x1800633e1  xor     r8d, r8d; pcbe
0x1800633e4  mov     rdx, rdi; pv
0x1800633e7  lea     rcx, ?s_Callback@ThreadpoolTimerHelper@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800633ee  call    cs:__imp_CreateThreadpoolTimer
0x1800633f4  mov     rdx, rax
0x1800633f7  mov     rcx, rdi
0x1800633fa  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800633ff  cmp     qword ptr [rdi], 0
0x180063403  jnz     short loc_180063420
0x180063405  mov     rcx, [rsp+38h]; this
0x18006340a  lea     r8, aOnecoreuapInet_72; "onecoreuap\\inetcore\\inc\\ThreadpoolHe"...
0x180063411  mov     edx, 53h ; 'S'; void *
0x180063416  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006341b  jmp     loc_1800634EB
0x180063420  mov     ecx, 48h ; 'H'; Size
0x180063425  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006342a  mov     rsi, rax
0x18006342d  mov     qword ptr [rax+38h], 0
0x180063435  mov     rcx, [rbx+38h]
0x180063439  test    rcx, rcx
0x18006343c  jz      short loc_18006346C
0x18006343e  cmp     rcx, rbx
0x180063441  jnz     short loc_180063460
0x180063443  mov     rdx, [rcx]
0x180063446  mov     rax, [rdx+8]
0x18006344a  mov     rdx, rsi
0x18006344d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063452  mov     [rsi+38h], rax
0x180063456  mov     rcx, rbx
0x180063459  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18006345e  jmp     short loc_18006346C
0x180063460  mov     [rax+38h], rcx
0x180063464  mov     qword ptr [rbx+38h], 0
0x18006346c  mov     dword ptr [rsi+40h], 0
0x180063473  mov     ecx, 18h; Size
0x180063478  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006347d  mov     rbx, rax
0x180063480  mov     eax, 1
0x180063485  mov     [rbx+8], eax
0x180063488  mov     [rbx+0Ch], eax
0x18006348b  lea     rax, ??_7?$_Ref_count@VCallbackData@ThreadpoolTimerHelper@@@std@@6B@; const std::_Ref_count<ThreadpoolTimerHelper::CallbackData>::`vftable'
0x180063492  mov     [rbx], rax
0x180063495  mov     [rbx+10h], rsi
0x180063499  mov     [rsp+38h+arg_18], 0
0x1800634a2  lea     rcx, [rsp+38h+arg_18]
0x1800634a7  call    ??1?$_Temporary_owner@VCallbackData@ThreadpoolTimerHelper@@@std@@QEAA@XZ; std::_Temporary_owner<ThreadpoolTimerHelper::CallbackData>::~_Temporary_owner<ThreadpoolTimerHelper::CallbackData>(void)
0x1800634ac  mov     [rdi+8], rsi
0x1800634b0  mov     rcx, [rdi+10h]; this
0x1800634b4  mov     [rdi+10h], rbx
0x1800634b8  test    rcx, rcx
0x1800634bb  jz      short loc_1800634C2
0x1800634bd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800634c2  imul    rax, rbp, 0FFFFFFFFFFFFD8F0h
0x1800634c9  mov     [rsp+38h+pftDueTime.dwLowDateTime], eax
0x1800634cd  shr     rax, 20h
0x1800634d1  mov     [rsp+38h+pftDueTime.dwHighDateTime], eax
0x1800634d5  xor     r9d, r9d; msWindowLength
0x1800634d8  xor     r8d, r8d; msPeriod
0x1800634db  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800634e0  mov     rcx, [rdi]; pti
0x1800634e3  call    cs:__imp_SetThreadpoolTimer
0x1800634e9  xor     eax, eax
0x1800634eb  mov     rbx, [rsp+38h+arg_8]
0x1800634f0  add     rsp, 20h
0x1800634f4  pop     rdi
0x1800634f5  pop     rsi
0x1800634f6  pop     rbp
0x1800634f7  retn
```
