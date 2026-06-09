# CallerIdentity::GetCoreApplicationViewForWindow(HWND__ *,_GUID const &,void * *)

- ea: `0x1800c62c0`
- end: `0x1800c63a3`
- name: `?GetCoreApplicationViewForWindow@CallerIdentity@@YAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `227`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800bfda0`

## callees

- `0x1800038e0`
- `0x180004dd4`
- `0x180012858`
- `0x1800c62c0`
- `0x1800ca010`

## import_xrefs

- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x1800c6329`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x1800c6329`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800c62e7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800c62e7`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCoreApplicationViewForWindow(
        CallerIdentity *this,
        HWND a2,
        const struct _GUID *a3,
        void **a4)
{
  DWORD WindowThreadProcessId; // r14d
  int Error; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, _QWORD); // rbx
  DWORD dwProcessId; // [rsp+58h] [rbp+38h] BYREF
  int v11; // [rsp+5Ch] [rbp+3Ch]
  __int64 (__fastcall ***v12)(_QWORD, GUID *, const struct _GUID *); // [rsp+60h] [rbp+40h] BYREF
  __int64 v13; // [rsp+68h] [rbp+48h] BYREF

  v11 = HIDWORD(a2);
  *(_QWORD *)&a3->Data1 = 0;
  dwProcessId = 0;
  WindowThreadProcessId = GetWindowThreadProcessId((HWND)this, &dwProcessId);
  if ( WindowThreadProcessId || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    v13 = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v13);
    Error = CoreQueryApplicationService(
              dwProcessId,
              &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1,
              &GUID_17b0e613_942a_422d_904c_f90dc71a7dae,
              &v13);
    if ( Error >= 0 )
    {
      v7 = v13;
      v12 = 0;
      v8 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v13 + 72LL);
      Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v12);
      Error = v8(v7, WindowThreadProcessId, &v12);
      if ( Error >= 0 )
        Error = (**v12)(v12, &GUID_638bb2db_451d_4661_b099_414f34ffb9f1, a3);
      Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v12);
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v13);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800c62c0  mov     qword ptr [rsp-28h+dwProcessId], rdx
0x1800c62c5  push    rbp
0x1800c62c6  push    rbx
0x1800c62c7  push    rsi
0x1800c62c8  push    rdi
0x1800c62c9  push    r14
0x1800c62cb  mov     rbp, rsp
0x1800c62ce  sub     rsp, 20h
0x1800c62d2  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x1800c62d6  mov     qword ptr [r8], 0
0x1800c62dd  mov     rsi, r8
0x1800c62e0  mov     [rbp+dwProcessId], 0
0x1800c62e7  call    cs:__imp_GetWindowThreadProcessId
0x1800c62ed  mov     r14d, eax
0x1800c62f0  test    eax, eax
0x1800c62f2  jnz     short loc_1800C6303
0x1800c62f4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800c62f9  mov     ebx, eax
0x1800c62fb  test    eax, eax
0x1800c62fd  js      loc_1800C6396
0x1800c6303  lea     rcx, [rbp+arg_18]
0x1800c6307  mov     [rbp+arg_18], 0
0x1800c630f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c6314  mov     ecx, [rbp+dwProcessId]
0x1800c6317  lea     r9, [rbp+arg_18]
0x1800c631b  lea     r8, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x1800c6322  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x1800c6329  call    cs:__imp_CoreQueryApplicationService
0x1800c632f  mov     ebx, eax
0x1800c6331  test    eax, eax
0x1800c6333  js      short loc_1800C638D
0x1800c6335  mov     rdi, [rbp+arg_18]
0x1800c6339  lea     rcx, [rbp+arg_10]
0x1800c633d  mov     [rbp+arg_10], 0
0x1800c6345  mov     rax, [rdi]
0x1800c6348  mov     rbx, [rax+48h]
0x1800c634c  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800c6351  lea     r8, [rbp+arg_10]
0x1800c6355  mov     edx, r14d
0x1800c6358  mov     rcx, rdi
0x1800c635b  mov     rax, rbx
0x1800c635e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6363  mov     ebx, eax
0x1800c6365  test    eax, eax
0x1800c6367  js      short loc_1800C6384
0x1800c6369  mov     rcx, [rbp+arg_10]
0x1800c636d  lea     rdx, _GUID_638bb2db_451d_4661_b099_414f34ffb9f1
0x1800c6374  mov     r8, rsi
0x1800c6377  mov     rax, [rcx]
0x1800c637a  mov     rax, [rax]
0x1800c637d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6382  mov     ebx, eax
0x1800c6384  lea     rcx, [rbp+arg_10]
0x1800c6388  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800c638d  lea     rcx, [rbp+arg_18]
0x1800c6391  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c6396  mov     eax, ebx
0x1800c6398  add     rsp, 20h
0x1800c639c  pop     r14
0x1800c639e  pop     rdi
0x1800c639f  pop     rsi
0x1800c63a0  pop     rbx
0x1800c63a1  pop     rbp
0x1800c63a2  retn
```
