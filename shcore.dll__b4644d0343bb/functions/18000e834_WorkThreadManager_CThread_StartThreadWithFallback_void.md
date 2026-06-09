# WorkThreadManager::CThread::StartThreadWithFallback(void)

- ea: `0x18000e834`
- end: `0x18000e97f`
- name: `?StartThreadWithFallback@CThread@WorkThreadManager@@QEAAJXZ`
- size: `331`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800536ac`

## callees

- `0x18000e834`
- `0x18000eadc`
- `0x18000edf0`
- `0x18000f808`
- `0x180053bd8`
- `0x180068d9c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e916`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000e8f8`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000e8f8`

## string_xrefs

- `0x18000e8b8`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000e965`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
__int64 __fastcall WorkThreadManager::CThread::StartThreadWithFallback(
        WorkThreadManager::CThread *pv,
        __int64 a2,
        __int64 a3)
{
  int started; // edi
  void *v5; // rax
  unsigned int v6; // edx
  WorkThreadManager::TaskData *v7; // rcx
  signed int LastError; // eax
  unsigned int v10; // edx
  WorkThreadManager::TaskData *v11; // rcx
  __int64 v12; // rdx
  int v13[2]; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  started = WorkThreadManager::CThread::StartThreadCommon(pv, a2, a3);
  if ( started < 0 )
  {
    v12 = 679;
    goto LABEL_16;
  }
  v5 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    *(_QWORD *)v13 = *((_QWORD *)pv + 20);
    v5 = (void *)WorkThreadManager::TaskData::TaskData(
                   v5,
                   *((unsigned int *)pv + 36),
                   *((unsigned int *)pv + 37),
                   *((unsigned int *)pv + 38));
  }
  v7 = (WorkThreadManager::TaskData *)*((_QWORD *)pv + 7);
  *((_QWORD *)pv + 7) = v5;
  if ( v7 )
    WorkThreadManager::TaskData::`scalar deleting destructor'(v7, v6);
  if ( !*((_QWORD *)pv + 7) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A9,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)0x8007000ELL,
      v13[0]);
    return 2147942414LL;
  }
  _InterlockedIncrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsStarting);
  (*(void (__fastcall **)(WorkThreadManager::CThread *))(*(_QWORD *)pv + 8LL))(pv);
  if ( TrySubmitThreadpoolCallback(_lambda_142c425290ac4fbd4d5aee2fc3f7d711_::_lambda_invoker_cdecl_, pv, 0) )
    return 0;
  LastError = GetLastError();
  started = LastError;
  if ( LastError > 0 )
    started = (unsigned __int16)LastError | 0x80070000;
  (*(void (__fastcall **)(WorkThreadManager::CThread *))(*(_QWORD *)pv + 16LL))(pv);
  v11 = (WorkThreadManager::TaskData *)*((_QWORD *)pv + 7);
  *((_QWORD *)pv + 7) = 0;
  if ( v11 )
    WorkThreadManager::TaskData::`scalar deleting destructor'(v11, v10);
  _InterlockedDecrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsStarting);
  if ( started < 0 )
  {
    v12 = 699;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)started,
      v13[0]);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000e834  mov     [rsp+arg_0], rbx
0x18000e839  push    rdi
0x18000e83a  sub     rsp, 30h
0x18000e83e  mov     rbx, rcx
0x18000e841  call    ?StartThreadCommon@CThread@WorkThreadManager@@QEAAJXZ; WorkThreadManager::CThread::StartThreadCommon(void)
0x18000e846  mov     edi, eax
0x18000e848  test    eax, eax
0x18000e84a  js      loc_18000E978
0x18000e850  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e857  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000e85c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e861  mov     [rsp+38h+arg_8], rax
0x18000e866  test    rax, rax
0x18000e869  jz      short loc_18000E89F
0x18000e86b  mov     rcx, [rbx+0C0h]
0x18000e872  mov     r9d, [rbx+98h]
0x18000e879  mov     r8d, [rbx+94h]
0x18000e880  mov     edx, [rbx+90h]
0x18000e886  mov     [rsp+38h+var_10], rcx
0x18000e88b  mov     rcx, [rbx+0A0h]
0x18000e892  mov     qword ptr [rsp+38h+var_18], rcx; int
0x18000e897  mov     rcx, rax
0x18000e89a  call    ??0TaskData@WorkThreadManager@@QEAA@W4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAXPEAUIComPoolTask@34@@Z; WorkThreadManager::TaskData::TaskData(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,void *,Windows::Internal::IComPoolTask *)
0x18000e89f  mov     rcx, [rbx+38h]; this
0x18000e8a3  mov     [rbx+38h], rax
0x18000e8a7  test    rcx, rcx
0x18000e8aa  jnz     short loc_18000E90F
0x18000e8ac  cmp     qword ptr [rbx+38h], 0
0x18000e8b1  jnz     short loc_18000E8D5
0x18000e8b3  mov     rcx, [rsp+38h]; this
0x18000e8b8  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000e8bf  mov     ebx, 8007000Eh
0x18000e8c4  mov     edx, 2A9h; void *
0x18000e8c9  mov     r9d, ebx; char *
0x18000e8cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e8d1  mov     eax, ebx
0x18000e8d3  jmp     short loc_18000E904
0x18000e8d5  lock inc cs:?s_cThreadsStarting@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsStarting
0x18000e8dc  mov     rax, [rbx]
0x18000e8df  mov     rcx, rbx
0x18000e8e2  mov     rax, [rax+8]
0x18000e8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8eb  xor     r8d, r8d; pcbe
0x18000e8ee  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_142c425290ac4fbd4d5aee2fc3f7d711_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18000e8f5  mov     rdx, rbx; pv
0x18000e8f8  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000e8fe  test    eax, eax
0x18000e900  jz      short loc_18000E916
0x18000e902  xor     eax, eax
0x18000e904  mov     rbx, [rsp+38h+arg_0]
0x18000e909  add     rsp, 30h
0x18000e90d  pop     rdi
0x18000e90e  retn
0x18000e90f  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x18000e914  jmp     short loc_18000E8AC
0x18000e916  call    cs:__imp_GetLastError
0x18000e91c  mov     edi, eax
0x18000e91e  test    eax, eax
0x18000e920  jle     short loc_18000E92B
0x18000e922  movzx   edi, ax
0x18000e925  or      edi, 80070000h
0x18000e92b  mov     rax, [rbx]
0x18000e92e  mov     rcx, rbx
0x18000e931  mov     rax, [rax+10h]
0x18000e935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e93a  mov     rcx, [rbx+38h]; this
0x18000e93e  mov     qword ptr [rbx+38h], 0
0x18000e946  test    rcx, rcx
0x18000e949  jz      short loc_18000E950
0x18000e94b  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x18000e950  lock dec cs:?s_cThreadsStarting@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsStarting
0x18000e957  test    edi, edi
0x18000e959  jns     short loc_18000E974
0x18000e95b  mov     edx, 2BBh; void *
0x18000e960  mov     rcx, [rsp+38h]; this
0x18000e965  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000e96c  mov     r9d, edi; char *
0x18000e96f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e974  mov     eax, edi
0x18000e976  jmp     short loc_18000E904
0x18000e978  mov     edx, 2A7h
0x18000e97d  jmp     short loc_18000E960
```
