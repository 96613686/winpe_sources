# Windows::Management::Deployment::WaitForDeploymentOperation(ulong,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Management::Deployment::IDeploymentResult * *)

- ea: `0x180039fa0`
- end: `0x18003a162`
- name: `?WaitForDeploymentOperation@Deployment@Management@Windows@@YAJKPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@3@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAPEAUIDeploymentResult@123@@Z`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180037558`

## callees

- `0x180003d24`
- `0x1800160c0`
- `0x180035f50`
- `0x180039fa0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180039fd4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180039fd4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a09d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a0b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a0b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a12f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a12f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 Windows::Management::Deployment::WaitForDeploymentOperation(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 a3,
        ...)
{
  __int64 v4; // rbx
  HANDLE Event; // rax
  void *v6; // rsi
  signed int v7; // eax
  signed int v8; // edi
  __int64 *v9; // rax
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rdi
  DWORD v11; // eax
  signed int LastError; // eax
  _QWORD v14[2]; // [rsp+20h] [rbp-10h] BYREF
  int v15; // [rsp+60h] [rbp+30h] BYREF
  __int64 v16; // [rsp+70h] [rbp+40h] BYREF
  __int64 v17; // [rsp+78h] [rbp+48h] BYREF
  va_list va; // [rsp+78h] [rbp+48h]
  __int64 v19; // [rsp+80h] [rbp+50h]
  va_list va1; // [rsp+88h] [rbp+58h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v17 = va_arg(va1, _QWORD);
  v19 = va_arg(va1, _QWORD);
  v4 = 0;
  v16 = 0;
  v15 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v6 = Event;
  if ( Event )
  {
    v14[0] = Event;
    v14[1] = 0;
    v9 = (__int64 *)Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::IDeploymentResult *>,Windows::Management::Deployment::DeploymentProgress>::*)(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,enum ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,_lambda_9a0aae7dbba35881869cec547d91271e_,-1,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,enum ABI::Windows::Foundation::AsyncStatus>,_lambda_9a0aae7dbba35881869cec547d91271e_>(
                      (__int64 *)va,
                      v14);
    v4 = *v9;
    *v9 = 0;
    if ( v17 )
    {
      v17 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
    }
    v19 = v4;
    if ( v4 )
    {
      v10 = **a2;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
      v8 = v10(a2, &GUID_00000036_0000_0000_c000_000000000046, &v16);
      if ( v8 >= 0 )
      {
        v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a2)[8])(a2, v4);
        if ( v8 >= 0 )
        {
          v11 = WaitForSingleObject(v6, 0xFFFFFFFF);
          if ( v11 == 258 )
          {
            v8 = -2147023436;
          }
          else if ( v11 )
          {
            LastError = GetLastError();
            v8 = LastError;
            if ( LastError > 0 )
              v8 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 56LL))(v16, &v15);
            if ( v8 >= 0 )
            {
              if ( v15 == 2 )
              {
                v8 = -2147009288;
              }
              else if ( v15 == 3 )
              {
                LODWORD(v17) = 0;
                v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 64LL))(v16, (__int64 *)va);
                if ( v8 >= 0 )
                  v8 = v17;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 80LL))(v16);
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
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180039fa0  mov     [rsp-28h+arg_18], r9
0x180039fa5  mov     [rsp-28h+arg_10], r8
0x180039faa  mov     [rsp-28h+arg_0], ecx
0x180039fae  push    rbp
0x180039faf  push    rbx
0x180039fb0  push    rsi
0x180039fb1  push    rdi
0x180039fb2  push    r14
0x180039fb4  mov     rbp, rsp
0x180039fb7  sub     rsp, 30h
0x180039fbb  mov     r14, rdx
0x180039fbe  xor     ebx, ebx
0x180039fc0  mov     [rbp+arg_10], rbx
0x180039fc4  mov     [rbp+arg_0], ebx
0x180039fc7  mov     r9d, 1F0003h; dwDesiredAccess
0x180039fcd  xor     r8d, r8d; dwFlags
0x180039fd0  xor     edx, edx; lpName
0x180039fd2  xor     ecx, ecx; lpEventAttributes
0x180039fd4  call    cs:__imp_CreateEventExW
0x180039fda  mov     rsi, rax
0x180039fdd  test    rax, rax
0x180039fe0  jnz     short loc_18003A000
0x180039fe2  call    cs:__imp_GetLastError
0x180039fe8  mov     edi, eax
0x180039fea  test    eax, eax
0x180039fec  jle     loc_18003A136
0x180039ff2  movzx   edi, ax
0x180039ff5  or      edi, 80070000h
0x180039ffb  jmp     loc_18003A136
0x18003a000  mov     [rbp+var_10], rsi
0x18003a004  mov     [rbp+var_8], 0
0x18003a00c  lea     rdx, [rbp+var_10]
0x18003a010  lea     rcx, [rbp+arg_18]
0x18003a014  call    ??$Make@U?$DelegateInvokeHelper@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@V_lambda_9a0aae7dbba35881869cec547d91271e_@@$0?0PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@W4AsyncStatus@23ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationWithProgressCompletedHandler_impl@U?$AggregateType@PEAVDeploymentResult@Deployment@Management@Windows@@PEAUIDeploymentResult@234@@Internal@Foundation@Windows@@UDeploymentProgress@Deployment@Management@4@@Foundation@Windows@@EAAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@V_lambda_9a0aae7dbba35881869cec547d91271e_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@V_lambda_9a0aae7dbba35881869cec547d91271e_@@$0?0PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@W4AsyncStatus@23ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationWithProgressCompletedHandler_impl@U?$AggregateType@PEAVDeploymentResult@Deployment@Management@Windows@@PEAUIDeploymentResult@234@@Internal@Foundation@Windows@@UDeploymentProgress@Deployment@Management@4@@Foundation@Windows@@EAAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_9a0aae7dbba35881869cec547d91271e_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::IDeploymentResult *>,Windows::Management::Deployment::DeploymentProgress>::*)(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,_lambda_9a0aae7dbba35881869cec547d91271e_,-1,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,ABI::Windows::Foundation::AsyncStatus>,_lambda_9a0aae7dbba35881869cec547d91271e_>(_lambda_9a0aae7dbba35881869cec547d91271e_ &&)
0x18003a019  mov     rbx, [rax]
0x18003a01c  mov     qword ptr [rax], 0
0x18003a023  mov     rcx, [rbp+arg_18]
0x18003a027  test    rcx, rcx
0x18003a02a  jz      short loc_18003A039
0x18003a02c  mov     [rbp+arg_18], 0
0x18003a034  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18003a039  mov     [rbp+arg_20], rbx
0x18003a03d  test    rbx, rbx
0x18003a040  jnz     short loc_18003A04C
0x18003a042  mov     edi, 8007000Eh
0x18003a047  jmp     loc_18003A12C
0x18003a04c  mov     rax, [r14]
0x18003a04f  mov     rdi, [rax]
0x18003a052  lea     rcx, [rbp+arg_10]
0x18003a056  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a05b  lea     r8, [rbp+arg_10]
0x18003a05f  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18003a066  mov     rcx, r14
0x18003a069  mov     rax, rdi
0x18003a06c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a071  mov     edi, eax
0x18003a073  test    eax, eax
0x18003a075  js      loc_18003A12C
0x18003a07b  mov     rax, [r14]
0x18003a07e  mov     rdx, rbx
0x18003a081  mov     rcx, r14
0x18003a084  mov     rax, [rax+40h]
0x18003a088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a08d  mov     edi, eax
0x18003a08f  test    eax, eax
0x18003a091  js      loc_18003A12C
0x18003a097  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003a09a  mov     rcx, rsi; hHandle
0x18003a09d  call    cs:__imp_WaitForSingleObject
0x18003a0a3  cmp     eax, 102h
0x18003a0a8  jnz     short loc_18003A0B1
0x18003a0aa  mov     edi, 800705B4h
0x18003a0af  jmp     short loc_18003A12C
0x18003a0b1  test    eax, eax
0x18003a0b3  jz      short loc_18003A0CC
0x18003a0b5  call    cs:__imp_GetLastError
0x18003a0bb  mov     edi, eax
0x18003a0bd  test    eax, eax
0x18003a0bf  jle     short loc_18003A12C
0x18003a0c1  movzx   edi, ax
0x18003a0c4  or      edi, 80070000h
0x18003a0ca  jmp     short loc_18003A12C
0x18003a0cc  mov     rcx, [rbp+arg_10]
0x18003a0d0  mov     rax, [rcx]
0x18003a0d3  lea     rdx, [rbp+arg_0]
0x18003a0d7  mov     rax, [rax+38h]
0x18003a0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0e0  mov     edi, eax
0x18003a0e2  test    eax, eax
0x18003a0e4  js      short loc_18003A12C
0x18003a0e6  cmp     [rbp+arg_0], 2
0x18003a0ea  jnz     short loc_18003A0F3
0x18003a0ec  mov     edi, 80073CF8h
0x18003a0f1  jmp     short loc_18003A11C
0x18003a0f3  cmp     [rbp+arg_0], 3
0x18003a0f7  jnz     short loc_18003A11C
0x18003a0f9  mov     dword ptr [rbp+arg_18], 0
0x18003a100  mov     rcx, [rbp+arg_10]
0x18003a104  mov     rax, [rcx]
0x18003a107  lea     rdx, [rbp+arg_18]
0x18003a10b  mov     rax, [rax+40h]
0x18003a10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a114  mov     edi, eax
0x18003a116  test    eax, eax
0x18003a118  cmovns  edi, dword ptr [rbp+arg_18]
0x18003a11c  mov     rcx, [rbp+arg_10]
0x18003a120  mov     rax, [rcx]
0x18003a123  mov     rax, [rax+50h]
0x18003a127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a12c  mov     rcx, rsi; hObject
0x18003a12f  call    cs:__imp_CloseHandle
0x18003a135  nop
0x18003a136  lea     rcx, [rbp+arg_10]
0x18003a13a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a13f  nop
0x18003a140  test    rbx, rbx
0x18003a143  jz      short loc_18003A155
0x18003a145  mov     rax, [rbx]
0x18003a148  mov     rcx, rbx
0x18003a14b  mov     rax, [rax+10h]
0x18003a14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a154  nop
0x18003a155  mov     eax, edi
0x18003a157  add     rsp, 30h
0x18003a15b  pop     r14
0x18003a15d  pop     rdi
0x18003a15e  pop     rsi
0x18003a15f  pop     rbx
0x18003a160  pop     rbp
0x18003a161  retn
```
