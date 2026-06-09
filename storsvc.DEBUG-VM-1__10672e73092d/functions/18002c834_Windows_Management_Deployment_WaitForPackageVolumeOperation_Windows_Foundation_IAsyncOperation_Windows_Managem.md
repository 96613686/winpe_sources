# Windows::Management::Deployment::WaitForPackageVolumeOperation(Windows::Foundation::IAsyncOperation<Windows::Management::Deployment::PackageVolume *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *> *,Windows::Management::Deployment::IPackageVolume * *)

- ea: `0x18002c834`
- end: `0x18002ca63`
- name: `?WaitForPackageVolumeOperation@Deployment@Management@Windows@@YAJPEAU?$IAsyncOperation@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@3@PEAU?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@53@PEAPEAUIPackageVolume@123@@Z`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b474`

## callees

- `0x180014a00`
- `0x1800175c0`
- `0x18001ecc8`
- `0x18002c834`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002c873`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002c873`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c97b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c97b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c985`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ca20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ca20`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Management::Deployment::WaitForPackageVolumeOperation(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rdi
  HANDLE Event; // rax
  void *v7; // r14
  signed int v8; // eax
  signed int v9; // ebx
  __int64 *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rbx
  signed int LastError; // eax
  __int64 v16; // [rsp+28h] [rbp-28h] BYREF
  __int64 v17; // [rsp+30h] [rbp-20h]
  __int64 v18; // [rsp+38h] [rbp-18h]
  _QWORD v19[2]; // [rsp+40h] [rbp-10h] BYREF
  int v20; // [rsp+88h] [rbp+38h] BYREF
  int v21; // [rsp+8Ch] [rbp+3Ch]
  __int64 v22; // [rsp+98h] [rbp+48h] BYREF

  v21 = HIDWORD(a2);
  v5 = 0;
  v17 = 0;
  v16 = 0;
  v20 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v7 = Event;
  if ( Event )
  {
    v19[0] = Event;
    v19[1] = 0;
    v10 = (__int64 *)Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Management::Deployment::PackageVolume *,Windows::Management::Deployment::IPackageVolume *>>::*)(Windows::Foundation::IAsyncOperation<Windows::Management::Deployment::PackageVolume *> *,enum ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>,_lambda_c45c6a1ebc6e1958651ded08aead5a1e_,-1,Windows::Foundation::IAsyncOperation<Windows::Management::Deployment::PackageVolume *> *,enum ABI::Windows::Foundation::AsyncStatus>,_lambda_c45c6a1ebc6e1958651ded08aead5a1e_>(
                       &v22,
                       v19);
    v5 = *v10;
    v18 = *v10;
    *v10 = 0;
    v12 = v22;
    if ( v22 )
    {
      v22 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release(
        v12,
        v11);
    }
    v18 = 0;
    v22 = 0;
    v17 = v5;
    if ( v5 )
    {
      v13 = **a1;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
      v9 = v13(a1, &GUID_00000036_0000_0000_c000_000000000046, &v16);
      if ( v9 >= 0 )
      {
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v5);
        if ( v9 >= 0 )
        {
          if ( WaitForSingleObject(v7, 0xFFFFFFFF) )
          {
            LastError = GetLastError();
            v9 = LastError;
            if ( LastError > 0 )
              v9 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 56LL))(v16, &v20);
            if ( v9 >= 0 )
            {
              if ( !a3
                || (v9 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[8])(
                           a1,
                           a3),
                    v9 >= 0) )
              {
                if ( v20 == 2 )
                {
                  v9 = -2147009288;
                }
                else if ( v20 == 3 )
                {
                  LODWORD(v22) = 0;
                  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 64LL))(v16, &v22);
                  if ( v9 >= 0 )
                    v9 = v22;
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 80LL))(v16);
              }
            }
          }
        }
      }
    }
    else
    {
      v9 = -2147024882;
    }
    CloseHandle(v7);
  }
  else
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
  if ( v5 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002c834  mov     [rsp-28h+arg_0], rbx
0x18002c839  mov     [rsp-28h+arg_8], rdx
0x18002c83e  push    rbp
0x18002c83f  push    rsi
0x18002c840  push    rdi
0x18002c841  push    r14
0x18002c843  push    r15
0x18002c845  mov     rbp, rsp
0x18002c848  sub     rsp, 50h
0x18002c84c  mov     r15, r8
0x18002c84f  mov     rsi, rcx
0x18002c852  mov     [rbp+var_30], 0
0x18002c859  xor     edi, edi
0x18002c85b  mov     [rbp+var_20], rdi
0x18002c85f  mov     [rbp+var_28], rdi
0x18002c863  mov     dword ptr [rbp+arg_8], edi
0x18002c866  mov     r9d, 1F0003h; dwDesiredAccess
0x18002c86c  xor     r8d, r8d; dwFlags
0x18002c86f  xor     edx, edx; lpName
0x18002c871  xor     ecx, ecx; lpEventAttributes
0x18002c873  call    cs:__imp_CreateEventExW
0x18002c879  mov     r14, rax
0x18002c87c  test    rax, rax
0x18002c87f  jnz     short loc_18002C89F
0x18002c881  call    cs:__imp_GetLastError
0x18002c887  mov     ebx, eax
0x18002c889  test    eax, eax
0x18002c88b  jle     loc_18002CA27
0x18002c891  movzx   ebx, ax
0x18002c894  or      ebx, 80070000h
0x18002c89a  jmp     loc_18002CA27
0x18002c89f  mov     [rbp+var_10], r14
0x18002c8a3  mov     [rbp+var_8], 0
0x18002c8ab  lea     rdx, [rbp+var_10]
0x18002c8af  lea     rcx, [rbp+arg_18]
0x18002c8b3  call    ??$Make@U?$DelegateInvokeHelper@U?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@Windows@@V_lambda_c45c6a1ebc6e1958651ded08aead5a1e_@@$0?0PEAU?$IAsyncOperation@PEAVPackageVolume@Deployment@Management@Windows@@@23@W4AsyncStatus@23ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationCompletedHandler_impl@U?$AggregateType@PEAVPackageVolume@Deployment@Management@Windows@@PEAUIPackageVolume@234@@Internal@Foundation@Windows@@@Foundation@Windows@@EAAJPEAU?$IAsyncOperation@PEAVPackageVolume@Deployment@Management@Windows@@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@V_lambda_c45c6a1ebc6e1958651ded08aead5a1e_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@Windows@@V_lambda_c45c6a1ebc6e1958651ded08aead5a1e_@@$0?0PEAU?$IAsyncOperation@PEAVPackageVolume@Deployment@Management@Windows@@@23@W4AsyncStatus@23ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationCompletedHandler_impl@U?$AggregateType@PEAVPackageVolume@Deployment@Management@Windows@@PEAUIPackageVolume@234@@Internal@Foundation@Windows@@@Foundation@Windows@@EAAJPEAU?$IAsyncOperation@PEAVPackageVolume@Deployment@Management@Windows@@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_c45c6a1ebc6e1958651ded08aead5a1e_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Management::Deployment::PackageVolume *,Windows::Management::Deployment::IPackageVolume *>>::*)(Windows::Foundation::IAsyncOperation<Windows::Management::Deployment::PackageVolume *> *,ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>,_lambda_c45c6a1ebc6e1958651ded08aead5a1e_,-1,Windows::Foundation::IAsyncOperation<Windows::Management::Deployment::PackageVolume *> *,ABI::Windows::Foundation::AsyncStatus>,_lambda_c45c6a1ebc6e1958651ded08aead5a1e_>(_lambda_c45c6a1ebc6e1958651ded08aead5a1e_ &&)
0x18002c8b8  nop
0x18002c8b9  mov     rdi, [rax]
0x18002c8bc  mov     [rbp+var_18], rdi
0x18002c8c0  mov     qword ptr [rax], 0
0x18002c8c7  mov     [rbp+var_30], 2
0x18002c8ce  mov     rcx, [rbp+arg_18]
0x18002c8d2  test    rcx, rcx
0x18002c8d5  jz      short loc_18002C8E4
0x18002c8d7  mov     [rbp+arg_18], 0
0x18002c8df  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release(void)
0x18002c8e4  mov     eax, 2
0x18002c8e9  and     eax, 0FFFFFFFDh
0x18002c8ec  mov     [rbp+var_30], eax
0x18002c8ef  or      eax, 1
0x18002c8f2  mov     [rbp+var_30], eax
0x18002c8f5  mov     [rbp+arg_18], 0
0x18002c8fd  mov     [rbp+arg_18], rdi
0x18002c901  mov     [rbp+var_18], 0
0x18002c909  mov     [rbp+arg_18], 0
0x18002c911  mov     [rbp+var_20], rdi
0x18002c915  and     eax, 0FFFFFFFEh
0x18002c918  mov     [rbp+var_30], eax
0x18002c91b  test    rdi, rdi
0x18002c91e  jnz     short loc_18002C92A
0x18002c920  mov     ebx, 8007000Eh
0x18002c925  jmp     loc_18002CA1D
0x18002c92a  mov     rax, [rsi]
0x18002c92d  mov     rbx, [rax]
0x18002c930  lea     rcx, [rbp+var_28]
0x18002c934  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002c939  lea     r8, [rbp+var_28]
0x18002c93d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18002c944  mov     rcx, rsi
0x18002c947  mov     rax, rbx
0x18002c94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c94f  mov     ebx, eax
0x18002c951  test    eax, eax
0x18002c953  js      loc_18002CA1D
0x18002c959  mov     rax, [rsi]
0x18002c95c  mov     rdx, rdi
0x18002c95f  mov     rcx, rsi
0x18002c962  mov     rax, [rax+30h]
0x18002c966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c96b  mov     ebx, eax
0x18002c96d  test    eax, eax
0x18002c96f  js      loc_18002CA1D
0x18002c975  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002c978  mov     rcx, r14; hHandle
0x18002c97b  call    cs:__imp_WaitForSingleObject
0x18002c981  test    eax, eax
0x18002c983  jz      short loc_18002C9A0
0x18002c985  call    cs:__imp_GetLastError
0x18002c98b  mov     ebx, eax
0x18002c98d  test    eax, eax
0x18002c98f  jle     loc_18002CA1D
0x18002c995  movzx   ebx, ax
0x18002c998  or      ebx, 80070000h
0x18002c99e  jmp     short loc_18002CA1D
0x18002c9a0  mov     rcx, [rbp+var_28]
0x18002c9a4  mov     rax, [rcx]
0x18002c9a7  lea     rdx, [rbp+arg_8]
0x18002c9ab  mov     rax, [rax+38h]
0x18002c9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9b4  mov     ebx, eax
0x18002c9b6  test    eax, eax
0x18002c9b8  js      short loc_18002CA1D
0x18002c9ba  test    r15, r15
0x18002c9bd  jz      short loc_18002C9D7
0x18002c9bf  mov     rax, [rsi]
0x18002c9c2  mov     rdx, r15
0x18002c9c5  mov     rcx, rsi
0x18002c9c8  mov     rax, [rax+40h]
0x18002c9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9d1  mov     ebx, eax
0x18002c9d3  test    eax, eax
0x18002c9d5  js      short loc_18002CA1D
0x18002c9d7  cmp     dword ptr [rbp+arg_8], 2
0x18002c9db  jnz     short loc_18002C9E4
0x18002c9dd  mov     ebx, 80073CF8h
0x18002c9e2  jmp     short loc_18002CA0D
0x18002c9e4  cmp     dword ptr [rbp+arg_8], 3
0x18002c9e8  jnz     short loc_18002CA0D
0x18002c9ea  mov     dword ptr [rbp+arg_18], 0
0x18002c9f1  mov     rcx, [rbp+var_28]
0x18002c9f5  mov     rax, [rcx]
0x18002c9f8  lea     rdx, [rbp+arg_18]
0x18002c9fc  mov     rax, [rax+40h]
0x18002ca00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca05  mov     ebx, eax
0x18002ca07  test    eax, eax
0x18002ca09  cmovns  ebx, dword ptr [rbp+arg_18]
0x18002ca0d  mov     rcx, [rbp+var_28]
0x18002ca11  mov     rax, [rcx]
0x18002ca14  mov     rax, [rax+50h]
0x18002ca18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca1d  mov     rcx, r14; hObject
0x18002ca20  call    cs:__imp_CloseHandle
0x18002ca26  nop
0x18002ca27  lea     rcx, [rbp+var_28]
0x18002ca2b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002ca30  nop
0x18002ca31  test    rdi, rdi
0x18002ca34  jz      short loc_18002CA4D
0x18002ca36  mov     [rbp+var_20], 0
0x18002ca3e  mov     rax, [rdi]
0x18002ca41  mov     rcx, rdi
0x18002ca44  mov     rax, [rax+10h]
0x18002ca48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca4d  mov     eax, ebx
0x18002ca4f  mov     rbx, [rsp+50h+arg_0]
0x18002ca57  add     rsp, 50h
0x18002ca5b  pop     r15
0x18002ca5d  pop     r14
0x18002ca5f  pop     rdi
0x18002ca60  pop     rsi
0x18002ca61  pop     rbp
0x18002ca62  retn
```
