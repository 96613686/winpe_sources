# _lambda_7322bff9dbafb524f5c3fdecbc3ef0d8_::operator()(Windows::Storage::Streams::IRandomAccessStream *,Windows::Internal::CNoResult &)

- ea: `0x1800b48e8`
- end: `0x1800b4ac7`
- name: `??R_lambda_7322bff9dbafb524f5c3fdecbc3ef0d8_@@QEBAJPEAUIRandomAccessStream@Streams@Storage@Windows@@AEAVCNoResult@Internal@4@@Z`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bb910`

## callees

- `0x180032328`
- `0x1800343ec`
- `0x1800388ec`
- `0x18003902c`
- `0x18003ae60`
- `0x1800b2648`
- `0x1800b48e8`
- `0x1800ed010`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x1800b4a72`
- `ntdll!WinSqmSetDWORD` at `0x1800b4a72`
- `ntdll!WinSqmIncrementDWORD` at `0x1800b4a5b`
- `ntdll!WinSqmIncrementDWORD` at `0x1800b4a5b`
- `USER32!SystemParametersInfoW` at `0x1800b4a17`
- `USER32!SystemParametersInfoW` at `0x1800b4a17`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800b4918`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800b4918`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b49c7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b49c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall _lambda_7322bff9dbafb524f5c3fdecbc3ef0d8_::operator()(
        __int64 a1,
        int (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 a3)
{
  HRESULT v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  int (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rbx
  int v9; // edi
  HKEY v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-20h] BYREF
  int (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // [rsp+38h] [rbp-18h] BYREF
  __int64 v14; // [rsp+40h] [rbp-10h] BYREF
  __int64 v15; // [rsp+80h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+38h] BYREF

  v15 = a3;
  v5 = 1;
  if ( !(unsigned int)SHWindowsPolicy(POLID_NoChangingLockScreen) )
  {
    v13 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v13, v6, v7);
    v12 = 0;
    LOBYTE(v15) = 0;
    v8 = **a2;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
    if ( v8(a2, &GUID_29d25bfc_e5db_473e_9e19_cdb9c77393a4, &v12) >= 0
      && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 48LL))(v12, &v15) >= 0
      && (_BYTE)v15 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      v5 = CoCreateInstance(&CLSID_LockScreenStore, 0, 1u, &GUID_fb37854f_513a_4ca8_9a06_4adab5968a23, &ppv);
      v9 = 0;
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 40LL))(ppv, 1);
        if ( v5 >= 0 )
        {
          SHRegSetBOOL(v10, L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen", L"SlideshowEnabled", 0);
          SystemParametersInfoW(0xA9u, 0, 0, 1u);
          v9 = 1;
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    }
    else
    {
      v5 = CSetLockScreenImageTask::SetStream<Windows::Storage::Streams::IRandomAccessStream>(*(CSetLockScreenImageTask **)a1);
      v9 = 0;
    }
    if ( v5 >= 0 )
    {
      CSetLockScreenImageTask::s_SendChangeNotification();
      WinSqmIncrementDWORD(0, 8874, 1);
      WinSqmSetDWORD(0, 10453, 6);
      v14 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL);
      LODWORD(ppv) = v9 + 1;
      LockScreenTelemetry::SetImageByApiEvent<enum LockScreenTelemetry::SetImageApiType,unsigned short const *>(
        &ppv,
        &v14);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800b48e8  mov     [rsp-18h+arg_0], rbx
0x1800b48ed  mov     [rsp-18h+arg_8], rsi
0x1800b48f2  mov     [rsp-18h+arg_10], r8
0x1800b48f7  push    rbp
0x1800b48f8  push    rdi
0x1800b48f9  push    r15
0x1800b48fb  mov     rbp, rsp
0x1800b48fe  sub     rsp, 50h
0x1800b4902  mov     rdi, rdx
0x1800b4905  mov     rsi, rcx
0x1800b4908  mov     r15d, 1
0x1800b490e  mov     ebx, r15d
0x1800b4911  lea     rcx, POLID_NoChangingLockScreen
0x1800b4918  call    cs:__imp_SHWindowsPolicy
0x1800b491f  nop     dword ptr [rax+rax+00h]
0x1800b4924  test    eax, eax
0x1800b4926  jnz     loc_1800B4AB1
0x1800b492c  mov     [rbp+var_18], rdi
0x1800b4930  lea     rcx, [rbp+var_18]
0x1800b4934  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x1800b4939  nop
0x1800b493a  mov     [rbp+var_20], 0
0x1800b4942  mov     byte ptr [rbp+arg_10], 0
0x1800b4946  mov     rax, [rdi]
0x1800b4949  mov     rbx, [rax]
0x1800b494c  lea     rcx, [rbp+var_20]
0x1800b4950  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4955  lea     r8, [rbp+var_20]
0x1800b4959  lea     rdx, _GUID_29d25bfc_e5db_473e_9e19_cdb9c77393a4
0x1800b4960  mov     rcx, rdi
0x1800b4963  mov     rax, rbx
0x1800b4966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b496b  nop
0x1800b496c  test    eax, eax
0x1800b496e  js      loc_1800B4A31
0x1800b4974  mov     rcx, [rbp+var_20]
0x1800b4978  mov     rax, [rcx]
0x1800b497b  lea     rdx, [rbp+arg_10]
0x1800b497f  mov     rax, [rax+30h]
0x1800b4983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4988  test    eax, eax
0x1800b498a  js      loc_1800B4A31
0x1800b4990  cmp     byte ptr [rbp+arg_10], 0
0x1800b4994  jz      loc_1800B4A31
0x1800b499a  mov     [rbp+arg_18], 0
0x1800b49a2  lea     rcx, [rbp+arg_18]
0x1800b49a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b49ab  lea     rax, [rbp+arg_18]
0x1800b49af  mov     [rsp+50h+ppv], rax; ppv
0x1800b49b4  lea     r9, _GUID_fb37854f_513a_4ca8_9a06_4adab5968a23; riid
0x1800b49bb  mov     r8d, r15d; dwClsContext
0x1800b49be  xor     edx, edx; pUnkOuter
0x1800b49c0  lea     rcx, CLSID_LockScreenStore; rclsid
0x1800b49c7  call    cs:__imp_CoCreateInstance
0x1800b49ce  nop     dword ptr [rax+rax+00h]
0x1800b49d3  mov     ebx, eax
0x1800b49d5  xor     edi, edi
0x1800b49d7  test    eax, eax
0x1800b49d9  js      short loc_1800B4A26
0x1800b49db  mov     rcx, [rbp+arg_18]
0x1800b49df  mov     rax, [rcx]
0x1800b49e2  mov     edx, r15d
0x1800b49e5  mov     rax, [rax+28h]
0x1800b49e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b49ee  mov     ebx, eax
0x1800b49f0  test    eax, eax
0x1800b49f2  js      short loc_1800B4A26
0x1800b49f4  xor     r9d, r9d; int
0x1800b49f7  lea     r8, aSlideshowenabl; "SlideshowEnabled"
0x1800b49fe  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800b4a05  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1800b4a0a  mov     r9d, r15d; fWinIni
0x1800b4a0d  xor     r8d, r8d; pvParam
0x1800b4a10  xor     edx, edx; uiParam
0x1800b4a12  mov     ecx, 0A9h; uiAction
0x1800b4a17  call    cs:__imp_SystemParametersInfoW
0x1800b4a1e  nop     dword ptr [rax+rax+00h]
0x1800b4a23  mov     edi, r15d
0x1800b4a26  lea     rcx, [rbp+arg_18]
0x1800b4a2a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4a2f  jmp     short loc_1800B4A48
0x1800b4a31  mov     r8, [rsi+8]
0x1800b4a35  mov     r8, [r8+8]
0x1800b4a39  mov     rdx, rdi
0x1800b4a3c  mov     rcx, [rsi]; this
0x1800b4a3f  call    ??$SetStream@UIRandomAccessStream@Streams@Storage@Windows@@@CSetLockScreenImageTask@@QEAAJPEAUIRandomAccessStream@Streams@Storage@Windows@@PEBGPEBU_GUID@@@Z; CSetLockScreenImageTask::SetStream<Windows::Storage::Streams::IRandomAccessStream>(Windows::Storage::Streams::IRandomAccessStream *,ushort const *,_GUID const *)
0x1800b4a44  mov     ebx, eax
0x1800b4a46  xor     edi, edi
0x1800b4a48  test    ebx, ebx
0x1800b4a4a  js      short loc_1800B4A9E
0x1800b4a4c  call    ?s_SendChangeNotification@CSetLockScreenImageTask@@SAXXZ; CSetLockScreenImageTask::s_SendChangeNotification(void)
0x1800b4a51  mov     r8d, r15d
0x1800b4a54  mov     edx, 22AAh
0x1800b4a59  xor     ecx, ecx
0x1800b4a5b  call    cs:__imp_WinSqmIncrementDWORD
0x1800b4a62  nop     dword ptr [rax+rax+00h]
0x1800b4a67  mov     edx, 28D5h
0x1800b4a6c  xor     ecx, ecx
0x1800b4a6e  lea     r8d, [rcx+6]
0x1800b4a72  call    cs:__imp_WinSqmSetDWORD
0x1800b4a79  nop     dword ptr [rax+rax+00h]
0x1800b4a7e  mov     rax, [rsi+8]
0x1800b4a82  mov     rcx, [rax+8]
0x1800b4a86  mov     [rbp+var_10], rcx
0x1800b4a8a  lea     eax, [rdi+1]
0x1800b4a8d  mov     dword ptr [rbp+arg_18], eax
0x1800b4a90  lea     rdx, [rbp+var_10]
0x1800b4a94  lea     rcx, [rbp+arg_18]
0x1800b4a98  call    ??$SetImageByApiEvent@W4SetImageApiType@LockScreenTelemetry@@PEBG@LockScreenTelemetry@@SAX$$QEAW4SetImageApiType@0@$$QEAPEBG@Z; LockScreenTelemetry::SetImageByApiEvent<LockScreenTelemetry::SetImageApiType,ushort const *>(LockScreenTelemetry::SetImageApiType &&,ushort const * &&)
0x1800b4a9d  nop
0x1800b4a9e  lea     rcx, [rbp+var_20]
0x1800b4aa2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4aa7  nop
0x1800b4aa8  lea     rcx, [rbp+var_18]
0x1800b4aac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4ab1  mov     eax, ebx
0x1800b4ab3  mov     rbx, [rsp+50h+arg_0]
0x1800b4ab8  mov     rsi, [rsp+50h+arg_8]
0x1800b4abd  add     rsp, 50h
0x1800b4ac1  pop     r15
0x1800b4ac3  pop     rdi
0x1800b4ac4  pop     rbp
0x1800b4ac5  retn
```
