# COplockProvider::WaitAndFinishOplockBroken(void)

- ea: `0x180011b68`
- end: `0x180011be7`
- name: `?WaitAndFinishOplockBroken@COplockProvider@@AEAAXXZ`
- size: `127`
- prototype: `void __fastcall(COplockProvider *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003f120`

## callees

- `0x180011b68`
- `0x180011bf0`
- `0x1800259e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bcd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011bdf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011bdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011b9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011b9a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180011b8e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180011b8e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180011bad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180011bad`

## pseudocode

```c
void __fastcall COplockProvider::WaitAndFinishOplockBroken(COplockProvider *this)
{
  struct _TP_WAIT *v2; // rcx
  int v3; // ebx
  struct _TP_TIMER *v4; // rbx
  DWORD LastError; // edi

  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    SetThreadpoolWait(v2, 0, 0);
    v3 = *((_DWORD *)this + 56);
    if ( v3 != GetCurrentThreadId() )
      WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 8), 1);
    wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::reset((char *)this + 216);
    v4 = (struct _TP_TIMER *)_InterlockedExchange64((volatile __int64 *)this + 34, 0);
    if ( v4 )
    {
      LastError = GetLastError();
      wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
      SetLastError(LastError);
    }
  }
}

```

## disassembly

```asm
0x180011b68  mov     [rsp+arg_0], rbx
0x180011b6d  push    rdi
0x180011b6e  sub     rsp, 20h
0x180011b72  mov     rdi, rcx
0x180011b75  mov     rcx, [rcx+40h]; pwa
0x180011b79  test    rcx, rcx
0x180011b7c  jnz     short loc_180011B89
0x180011b7e  mov     rbx, [rsp+28h+arg_0]
0x180011b83  add     rsp, 20h
0x180011b87  pop     rdi
0x180011b88  retn
0x180011b89  xor     r8d, r8d; pftTimeout
0x180011b8c  xor     edx, edx; h
0x180011b8e  call    cs:__imp_SetThreadpoolWait
0x180011b94  mov     ebx, [rdi+0E0h]
0x180011b9a  call    cs:__imp_GetCurrentThreadId
0x180011ba0  cmp     ebx, eax
0x180011ba2  jz      short loc_180011BB3
0x180011ba4  mov     rcx, [rdi+40h]; pwa
0x180011ba8  mov     edx, 1; fCancelPendingCallbacks
0x180011bad  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180011bb3  lea     rcx, [rdi+0D8h]
0x180011bba  call    ?reset@?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::reset(void)
0x180011bbf  xor     ebx, ebx
0x180011bc1  xchg    rbx, [rdi+110h]
0x180011bc8  test    rbx, rbx
0x180011bcb  jz      short loc_180011B7E
0x180011bcd  call    cs:__imp_GetLastError
0x180011bd3  mov     rcx, rbx; pti
0x180011bd6  mov     edi, eax
0x180011bd8  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180011bdd  mov     ecx, edi; dwErrCode
0x180011bdf  call    cs:__imp_SetLastError
0x180011be5  jmp     short loc_180011B7E
```
