# Windows::Management::Deployment::WaitForDeploymentOperation(ulong,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Management::Deployment::IDeploymentResult * *)

- ea: `0x18002c460`
- end: `0x18002c673`
- name: `?WaitForDeploymentOperation@Deployment@Management@Windows@@YAJKPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@3@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAPEAUIDeploymentResult@123@@Z`
- size: `531`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002629c`
- `0x1800282b8`
- `0x18002839c`
- `0x18002b474`

## callees

- `0x180014a00`
- `0x1800175c0`
- `0x18001ed98`
- `0x18002c460`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002c49f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002c49f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c5a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c5a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c639`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c639`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 Windows::Management::Deployment::WaitForDeploymentOperation(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 a3,
        ...)
{
  __int64 v4; // rdi
  HANDLE Event; // rax
  void *v6; // rsi
  signed int v7; // eax
  signed int v8; // ebx
  __int64 *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  DWORD v13; // eax
  signed int LastError; // eax
  _QWORD v16[2]; // [rsp+30h] [rbp-10h] BYREF
  int v17; // [rsp+70h] [rbp+30h] BYREF
  __int64 v18; // [rsp+80h] [rbp+40h] BYREF
  __int64 v19; // [rsp+88h] [rbp+48h] BYREF
  va_list va; // [rsp+88h] [rbp+48h]
  __int64 v21; // [rsp+90h] [rbp+50h]
  va_list va1; // [rsp+98h] [rbp+58h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v19 = va_arg(va1, _QWORD);
  va_arg(va1, _QWORD);
  v4 = 0;
  v21 = 0;
  v18 = 0;
  v17 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v6 = Event;
  if ( Event )
  {
    v16[0] = Event;
    v16[1] = 0;
    v9 = (__int64 *)Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::IDeploymentResult *>,Windows::Management::Deployment::DeploymentProgress>::*)(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,enum ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,_lambda_9a0aae7dbba35881869cec547d91271e_,-1,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,enum ABI::Windows::Foundation::AsyncStatus>,_lambda_9a0aae7dbba35881869cec547d91271e_>(
                      (__int64 *)va,
                      v16);
    v4 = *v9;
    *v9 = 0;
    v11 = v19;
    if ( v19 )
    {
      v19 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release(
        v11,
        v10);
    }
    v19 = 0;
    v21 = v4;
    if ( v4 )
    {
      v12 = **a2;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
      v8 = v12(a2, &GUID_00000036_0000_0000_c000_000000000046, &v18);
      if ( v8 >= 0 )
      {
        v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a2)[8])(a2, v4);
        if ( v8 >= 0 )
        {
          v13 = WaitForSingleObject(v6, 0xFFFFFFFF);
          if ( v13 == 258 )
          {
            v8 = -2147023436;
          }
          else if ( v13 )
          {
            LastError = GetLastError();
            v8 = LastError;
            if ( LastError > 0 )
              v8 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 56LL))(v18, &v17);
            if ( v8 >= 0 )
            {
              if ( v17 == 2 )
              {
                v8 = -2147009288;
              }
              else if ( v17 == 3 )
              {
                LODWORD(v19) = 0;
                v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 64LL))(v18, (__int64 *)va);
                if ( v8 >= 0 )
                  v8 = v19;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 80LL))(v18);
            }
          }
        }
      }
    }
    else
    {
      v8 = -2147024882;
    }
    CloseHandle(v6);
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  if ( v4 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002c460  mov     [rsp-28h+arg_18], r9
0x18002c465  mov     [rsp-28h+arg_10], r8
0x18002c46a  mov     [rsp-28h+arg_0], ecx
0x18002c46e  push    rbp
0x18002c46f  push    rbx
0x18002c470  push    rsi
0x18002c471  push    rdi
0x18002c472  push    r14
0x18002c474  mov     rbp, rsp
0x18002c477  sub     rsp, 40h
0x18002c47b  mov     r14, rdx
0x18002c47e  mov     [rbp+var_20], 0
0x18002c485  xor     edi, edi
0x18002c487  mov     [rbp+arg_20], rdi
0x18002c48b  mov     [rbp+arg_10], rdi
0x18002c48f  mov     [rbp+arg_0], edi
0x18002c492  mov     r9d, 1F0003h; dwDesiredAccess
0x18002c498  xor     r8d, r8d; dwFlags
0x18002c49b  xor     edx, edx; lpName
0x18002c49d  xor     ecx, ecx; lpEventAttributes
0x18002c49f  call    cs:__imp_CreateEventExW
0x18002c4a5  mov     rsi, rax
0x18002c4a8  test    rax, rax
0x18002c4ab  jnz     short loc_18002C4CB
0x18002c4ad  call    cs:__imp_GetLastError
0x18002c4b3  mov     ebx, eax
0x18002c4b5  test    eax, eax
0x18002c4b7  jle     loc_18002C640
0x18002c4bd  movzx   ebx, ax
0x18002c4c0  or      ebx, 80070000h
0x18002c4c6  jmp     loc_18002C640
0x18002c4cb  mov     [rbp+var_10], rsi
0x18002c4cf  mov     [rbp+var_8], 0
0x18002c4d7  lea     rdx, [rbp+var_10]
0x18002c4db  lea     rcx, [rbp+arg_18]
0x18002c4df  call    ??$Make@U?$DelegateInvokeHelper@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@V_lambda_9a0aae7dbba35881869cec547d91271e_@@$0?0PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@W4AsyncStatus@23ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationWithProgressCompletedHandler_impl@U?$AggregateType@PEAVDeploymentResult@Deployment@Management@Windows@@PEAUIDeploymentResult@234@@Internal@Foundation@Windows@@UDeploymentProgress@Deployment@Management@4@@Foundation@Windows@@EAAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@V_lambda_9a0aae7dbba35881869cec547d91271e_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@V_lambda_9a0aae7dbba35881869cec547d91271e_@@$0?0PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@W4AsyncStatus@23ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationWithProgressCompletedHandler_impl@U?$AggregateType@PEAVDeploymentResult@Deployment@Management@Windows@@PEAUIDeploymentResult@234@@Internal@Foundation@Windows@@UDeploymentProgress@Deployment@Management@4@@Foundation@Windows@@EAAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_9a0aae7dbba35881869cec547d91271e_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::IDeploymentResult *>,Windows::Management::Deployment::DeploymentProgress>::*)(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,_lambda_9a0aae7dbba35881869cec547d91271e_,-1,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,ABI::Windows::Foundation::AsyncStatus>,_lambda_9a0aae7dbba35881869cec547d91271e_>(_lambda_9a0aae7dbba35881869cec547d91271e_ &&)
0x18002c4e4  nop
0x18002c4e5  mov     rdi, [rax]
0x18002c4e8  mov     [rbp+var_18], rdi
0x18002c4ec  mov     qword ptr [rax], 0
0x18002c4f3  mov     [rbp+var_20], 2
0x18002c4fa  mov     rcx, [rbp+arg_18]
0x18002c4fe  test    rcx, rcx
0x18002c501  jz      short loc_18002C510
0x18002c503  mov     [rbp+arg_18], 0
0x18002c50b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release(void)
0x18002c510  mov     eax, 2
0x18002c515  and     eax, 0FFFFFFFDh
0x18002c518  mov     [rbp+var_20], eax
0x18002c51b  or      eax, 1
0x18002c51e  mov     [rbp+var_20], eax
0x18002c521  mov     [rbp+arg_18], 0
0x18002c529  mov     [rbp+arg_18], rdi
0x18002c52d  mov     [rbp+var_18], 0
0x18002c535  mov     [rbp+arg_18], 0
0x18002c53d  mov     [rbp+arg_20], rdi
0x18002c541  and     eax, 0FFFFFFFEh
0x18002c544  mov     [rbp+var_20], eax
0x18002c547  test    rdi, rdi
0x18002c54a  jnz     short loc_18002C556
0x18002c54c  mov     ebx, 8007000Eh
0x18002c551  jmp     loc_18002C636
0x18002c556  mov     rax, [r14]
0x18002c559  mov     rbx, [rax]
0x18002c55c  lea     rcx, [rbp+arg_10]
0x18002c560  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002c565  lea     r8, [rbp+arg_10]
0x18002c569  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18002c570  mov     rcx, r14
0x18002c573  mov     rax, rbx
0x18002c576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c57b  mov     ebx, eax
0x18002c57d  test    eax, eax
0x18002c57f  js      loc_18002C636
0x18002c585  mov     rax, [r14]
0x18002c588  mov     rdx, rdi
0x18002c58b  mov     rcx, r14
0x18002c58e  mov     rax, [rax+40h]
0x18002c592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c597  mov     ebx, eax
0x18002c599  test    eax, eax
0x18002c59b  js      loc_18002C636
0x18002c5a1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002c5a4  mov     rcx, rsi; hHandle
0x18002c5a7  call    cs:__imp_WaitForSingleObject
0x18002c5ad  cmp     eax, 102h
0x18002c5b2  jnz     short loc_18002C5BB
0x18002c5b4  mov     ebx, 800705B4h
0x18002c5b9  jmp     short loc_18002C636
0x18002c5bb  test    eax, eax
0x18002c5bd  jz      short loc_18002C5D6
0x18002c5bf  call    cs:__imp_GetLastError
0x18002c5c5  mov     ebx, eax
0x18002c5c7  test    eax, eax
0x18002c5c9  jle     short loc_18002C636
0x18002c5cb  movzx   ebx, ax
0x18002c5ce  or      ebx, 80070000h
0x18002c5d4  jmp     short loc_18002C636
0x18002c5d6  mov     rcx, [rbp+arg_10]
0x18002c5da  mov     rax, [rcx]
0x18002c5dd  lea     rdx, [rbp+arg_0]
0x18002c5e1  mov     rax, [rax+38h]
0x18002c5e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5ea  mov     ebx, eax
0x18002c5ec  test    eax, eax
0x18002c5ee  js      short loc_18002C636
0x18002c5f0  cmp     [rbp+arg_0], 2
0x18002c5f4  jnz     short loc_18002C5FD
0x18002c5f6  mov     ebx, 80073CF8h
0x18002c5fb  jmp     short loc_18002C626
0x18002c5fd  cmp     [rbp+arg_0], 3
0x18002c601  jnz     short loc_18002C626
0x18002c603  mov     dword ptr [rbp+arg_18], 0
0x18002c60a  mov     rcx, [rbp+arg_10]
0x18002c60e  mov     rax, [rcx]
0x18002c611  lea     rdx, [rbp+arg_18]
0x18002c615  mov     rax, [rax+40h]
0x18002c619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c61e  mov     ebx, eax
0x18002c620  test    eax, eax
0x18002c622  cmovns  ebx, dword ptr [rbp+arg_18]
0x18002c626  mov     rcx, [rbp+arg_10]
0x18002c62a  mov     rax, [rcx]
0x18002c62d  mov     rax, [rax+50h]
0x18002c631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c636  mov     rcx, rsi; hObject
0x18002c639  call    cs:__imp_CloseHandle
0x18002c63f  nop
0x18002c640  lea     rcx, [rbp+arg_10]
0x18002c644  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002c649  nop
0x18002c64a  test    rdi, rdi
0x18002c64d  jz      short loc_18002C666
0x18002c64f  mov     [rbp+arg_20], 0
0x18002c657  mov     rax, [rdi]
0x18002c65a  mov     rcx, rdi
0x18002c65d  mov     rax, [rax+10h]
0x18002c661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c666  mov     eax, ebx
0x18002c668  add     rsp, 40h
0x18002c66c  pop     r14
0x18002c66e  pop     rdi
0x18002c66f  pop     rsi
0x18002c670  pop     rbx
0x18002c671  pop     rbp
0x18002c672  retn
```
