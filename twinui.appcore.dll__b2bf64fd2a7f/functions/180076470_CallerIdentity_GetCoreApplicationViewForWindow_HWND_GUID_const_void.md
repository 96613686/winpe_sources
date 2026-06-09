# CallerIdentity::GetCoreApplicationViewForWindow(HWND__ *,_GUID const &,void * *)

- ea: `0x180076470`
- end: `0x180076553`
- name: `?GetCoreApplicationViewForWindow@CallerIdentity@@YAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `227`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004efa0`

## callees

- `0x180003d24`
- `0x180022fb4`
- `0x1800299c8`
- `0x180076470`
- `0x180085010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180076497`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180076497`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x1800764d9`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x1800764d9`

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
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v13);
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
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
      Error = v8(v7, WindowThreadProcessId, &v12);
      if ( Error >= 0 )
        Error = (**v12)(v12, &GUID_2e5500b6_66ad_467f_abb5_022a64283d88, a3);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
    }
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v13);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180076470  mov     qword ptr [rsp-28h+dwProcessId], rdx
0x180076475  push    rbp
0x180076476  push    rbx
0x180076477  push    rsi
0x180076478  push    rdi
0x180076479  push    r14
0x18007647b  mov     rbp, rsp
0x18007647e  sub     rsp, 20h
0x180076482  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180076486  mov     qword ptr [r8], 0
0x18007648d  mov     rsi, r8
0x180076490  mov     [rbp+dwProcessId], 0
0x180076497  call    cs:__imp_GetWindowThreadProcessId
0x18007649d  mov     r14d, eax
0x1800764a0  test    eax, eax
0x1800764a2  jnz     short loc_1800764B3
0x1800764a4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800764a9  mov     ebx, eax
0x1800764ab  test    eax, eax
0x1800764ad  js      loc_180076546
0x1800764b3  lea     rcx, [rbp+arg_18]
0x1800764b7  mov     [rbp+arg_18], 0
0x1800764bf  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800764c4  mov     ecx, [rbp+dwProcessId]
0x1800764c7  lea     r9, [rbp+arg_18]
0x1800764cb  lea     r8, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x1800764d2  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x1800764d9  call    cs:__imp_CoreQueryApplicationService
0x1800764df  mov     ebx, eax
0x1800764e1  test    eax, eax
0x1800764e3  js      short loc_18007653D
0x1800764e5  mov     rdi, [rbp+arg_18]
0x1800764e9  lea     rcx, [rbp+arg_10]
0x1800764ed  mov     [rbp+arg_10], 0
0x1800764f5  mov     rax, [rdi]
0x1800764f8  mov     rbx, [rax+48h]
0x1800764fc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076501  lea     r8, [rbp+arg_10]
0x180076505  mov     edx, r14d
0x180076508  mov     rcx, rdi
0x18007650b  mov     rax, rbx
0x18007650e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076513  mov     ebx, eax
0x180076515  test    eax, eax
0x180076517  js      short loc_180076534
0x180076519  mov     rcx, [rbp+arg_10]
0x18007651d  lea     rdx, _GUID_2e5500b6_66ad_467f_abb5_022a64283d88
0x180076524  mov     r8, rsi
0x180076527  mov     rax, [rcx]
0x18007652a  mov     rax, [rax]
0x18007652d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076532  mov     ebx, eax
0x180076534  lea     rcx, [rbp+arg_10]
0x180076538  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007653d  lea     rcx, [rbp+arg_18]
0x180076541  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180076546  mov     eax, ebx
0x180076548  add     rsp, 20h
0x18007654c  pop     r14
0x18007654e  pop     rdi
0x18007654f  pop     rsi
0x180076550  pop     rbx
0x180076551  pop     rbp
0x180076552  retn
```
