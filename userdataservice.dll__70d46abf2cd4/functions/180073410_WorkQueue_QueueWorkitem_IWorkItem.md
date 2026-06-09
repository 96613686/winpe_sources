# WorkQueue::QueueWorkitem(IWorkItem *)

- ea: `0x180073410`
- end: `0x180073517`
- name: `?QueueWorkitem@WorkQueue@@UEAAJPEAUIWorkItem@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(WorkQueue *this, struct IWorkItem *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180008ee8`
- `0x18001fd5c`
- `0x180021c40`
- `0x180073410`
- `0x180073520`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073429`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073429`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800734ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800734ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007349c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007349c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007347f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007347f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800734d6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800734d6`

## pseudocode

```c
__int64 __fastcall WorkQueue::QueueWorkitem(WorkQueue *this, struct IWorkItem *a2)
{
  __int64 v4; // r8
  unsigned int v5; // ebx
  struct _TP_CALLBACK_ENVIRON_V3 *v6; // r8
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax
  __int64 v9; // r8
  PTP_WORK pwk; // [rsp+40h] [rbp+8h] BYREF
  struct IWorkItem *v12; // [rsp+50h] [rbp+18h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_DWORD *)this + 26) )
  {
    v12 = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct IWorkItem *))(*(_QWORD *)a2 + 8LL))(a2);
    v6 = (struct _TP_CALLBACK_ENVIRON_V3 *)*((_QWORD *)this + 24);
    pwk = 0;
    ThreadpoolWork = CreateThreadpoolWork(_DoWorkCallback, a2, v6);
    tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&void CloseThreadpoolWork(_TP_WORK *),0>::reset(&pwk, ThreadpoolWork);
    if ( pwk )
    {
      SubmitThreadpoolWork(pwk);
      v12 = 0;
      tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&void CloseThreadpoolWork(_TP_WORK *),0>::_Delete(&pwk);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v12);
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      Log_HREvent_3(v5, 0, v9, 135);
      tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&void CloseThreadpoolWork(_TP_WORK *),0>::_Delete(&pwk);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v12);
    }
  }
  else
  {
    v5 = -2147418113;
    Log_HREvent_3(2147549183LL, 0, v4, 124);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return v5;
}

```

## disassembly

```asm
0x180073410  mov     [rsp+arg_8], rbx
0x180073415  mov     [rsp+arg_18], rsi
0x18007341a  push    rdi
0x18007341b  sub     rsp, 30h
0x18007341f  mov     rdi, rcx
0x180073422  mov     rbx, rdx
0x180073425  add     rcx, 40h ; '@'; lpCriticalSection
0x180073429  call    cs:__imp_EnterCriticalSection
0x18007342f  cmp     dword ptr [rdi+68h], 0
0x180073433  jnz     short loc_18007344C
0x180073435  xor     edx, edx
0x180073437  mov     ebx, 8000FFFFh
0x18007343c  mov     ecx, ebx
0x18007343e  lea     r9d, [rdx+7Ch]
0x180073442  call    Log_HREvent_3
0x180073447  jmp     loc_1800734FB
0x18007344c  mov     [rsp+38h+arg_10], rbx
0x180073451  test    rbx, rbx
0x180073454  jz      short loc_180073465
0x180073456  mov     rax, [rbx]
0x180073459  mov     rcx, rbx
0x18007345c  mov     rax, [rax+8]
0x180073460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073465  mov     r8, [rdi+0C0h]; pcbe
0x18007346c  lea     rcx, ?_DoWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180073473  mov     rdx, rbx; pv
0x180073476  mov     [rsp+38h+pwk], 0
0x18007347f  call    cs:__imp_CreateThreadpoolWork
0x180073485  mov     rdx, rax
0x180073488  lea     rcx, [rsp+38h+pwk]
0x18007348d  call    ?reset@?$auto_xxx@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?CloseThreadpoolWork@@YAX0@Z$0A@@tlx@@QEAAXPEAU_TP_WORK@@@Z; tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&CloseThreadpoolWork(_TP_WORK *),0>::reset(_TP_WORK *)
0x180073492  mov     rcx, [rsp+38h+pwk]; pwk
0x180073497  test    rcx, rcx
0x18007349a  jnz     short loc_1800734D6
0x18007349c  call    cs:__imp_GetLastError
0x1800734a2  mov     ebx, eax
0x1800734a4  test    eax, eax
0x1800734a6  jle     short loc_1800734B1
0x1800734a8  movzx   ebx, ax
0x1800734ab  or      ebx, 80070000h
0x1800734b1  xor     edx, edx
0x1800734b3  mov     r9d, 87h
0x1800734b9  mov     ecx, ebx
0x1800734bb  call    Log_HREvent_3
0x1800734c0  lea     rcx, [rsp+38h+pwk]
0x1800734c5  call    ?_Delete@?$auto_xxx@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?CloseThreadpoolWork@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&CloseThreadpoolWork(_TP_WORK *),0>::_Delete(void)
0x1800734ca  lea     rcx, [rsp+38h+arg_10]
0x1800734cf  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800734d4  jmp     short loc_1800734FB
0x1800734d6  call    cs:__imp_SubmitThreadpoolWork
0x1800734dc  lea     rcx, [rsp+38h+pwk]
0x1800734e1  mov     [rsp+38h+arg_10], 0
0x1800734ea  call    ?_Delete@?$auto_xxx@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?CloseThreadpoolWork@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&CloseThreadpoolWork(_TP_WORK *),0>::_Delete(void)
0x1800734ef  lea     rcx, [rsp+38h+arg_10]
0x1800734f4  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800734f9  xor     ebx, ebx
0x1800734fb  lea     rcx, [rdi+40h]; lpCriticalSection
0x1800734ff  call    cs:__imp_LeaveCriticalSection
0x180073505  mov     rsi, [rsp+38h+arg_18]
0x18007350a  mov     eax, ebx
0x18007350c  mov     rbx, [rsp+38h+arg_8]
0x180073511  add     rsp, 30h
0x180073515  pop     rdi
0x180073516  retn
```
