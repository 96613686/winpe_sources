# GetAppDataFolder(HSTRING__ * *)

- ea: `0x18001eb90`
- end: `0x18001edd8`
- name: `?GetAppDataFolder@@YAJPEAPEAUHSTRING__@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(HSTRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18025a1e0`

## callees

- `0x18001ce70`
- `0x18001eb90`
- `0x180021944`
- `0x180079e30`
- `0x1800fe40c`
- `0x180259fec`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec55`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ebe8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ebe8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ebd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ebd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ec01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ec01`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001ec11`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001ec11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec61`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ec40`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ec40`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetAppDataFolder(HSTRING *a1)
{
  int v2; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // ebx
  HANDLE CurrentProcess; // rax
  __int64 (__fastcall ***v6)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, DWORD *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, void **); // rbx
  void *TokenHandle; // [rsp+30h] [rbp-50h] BYREF
  __int64 TokenInformation; // [rsp+38h] [rbp-48h] BYREF
  DWORD ReturnLength[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v16; // [rsp+48h] [rbp-38h] BYREF
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v19; // [rsp+70h] [rbp-10h]

  LODWORD(TokenInformation) = 0;
  TokenHandle = 0;
  ReturnLength[0] = 0;
  v2 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      goto LABEL_11;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      goto LABEL_11;
    }
  }
  if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, ReturnLength) )
  {
    if ( (_DWORD)TokenInformation )
      v2 = 1;
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  CloseHandle(TokenHandle);
LABEL_11:
  if ( LastError >= 0 && v2 )
  {
    v17 = 0;
    TokenInformation = 0;
    *(_QWORD *)ReturnLength = 0;
    TokenHandle = 0;
    v16 = 0;
    v19 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Storage.ApplicationData",
      0x20u,
      0x1Fu);
    LastError = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<IActivationFactory>>(v19, &v17);
    if ( LastError >= 0 )
    {
      v6 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
      v7 = **v17;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&TokenInformation);
      LastError = v7(v6, &GUID_5612147b_e843_45e3_94d8_06169e3c8e17, &TokenInformation);
      if ( LastError >= 0 )
      {
        v8 = TokenInformation;
        v9 = *(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)TokenInformation + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ReturnLength);
        LastError = v9(v8, ReturnLength);
        if ( LastError >= 0 )
        {
          v10 = *(_QWORD *)ReturnLength;
          v11 = *(__int64 (__fastcall **)(__int64, void **))(**(_QWORD **)ReturnLength + 96LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&TokenHandle);
          LastError = v11(v10, &TokenHandle);
          if ( LastError >= 0 )
          {
            LastError = Microsoft::WRL::ComPtr<Windows::Storage::IStorageFolder>::As<Windows::Storage::IStorageItem>(
                          &TokenHandle,
                          &v16);
            if ( LastError >= 0 )
              LastError = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v16 + 96LL))(v16, a1);
          }
        }
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&TokenHandle);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ReturnLength);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&TokenInformation);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001eb90  mov     [rsp-18h+arg_8], rbx
0x18001eb95  mov     [rsp-18h+arg_10], rsi
0x18001eb9a  push    rbp
0x18001eb9b  push    rdi
0x18001eb9c  push    r15
0x18001eb9e  mov     rbp, rsp
0x18001eba1  sub     rsp, 80h
0x18001eba8  mov     rax, cs:__security_cookie
0x18001ebaf  xor     rax, rsp
0x18001ebb2  mov     [rbp+var_8], rax
0x18001ebb6  mov     rsi, rcx
0x18001ebb9  mov     dword ptr [rbp+TokenInformation], 0
0x18001ebc0  mov     [rbp+TokenHandle], 0
0x18001ebc8  mov     [rbp+var_40], 0
0x18001ebcf  xor     edi, edi
0x18001ebd1  call    cs:__imp_GetCurrentThread
0x18001ebd7  mov     rcx, rax; ThreadHandle
0x18001ebda  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001ebde  lea     r15d, [rdi+1]
0x18001ebe2  mov     r8d, r15d; OpenAsSelf
0x18001ebe5  lea     edx, [rdi+8]; DesiredAccess
0x18001ebe8  call    cs:__imp_OpenThreadToken
0x18001ebee  test    eax, eax
0x18001ebf0  jnz     short loc_18001EC25
0x18001ebf2  call    cs:__imp_GetLastError
0x18001ebf8  mov     ebx, eax
0x18001ebfa  cmp     eax, 3F0h
0x18001ebff  jnz     short loc_18001EC67
0x18001ec01  call    cs:__imp_GetCurrentProcess
0x18001ec07  mov     rcx, rax; ProcessHandle
0x18001ec0a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001ec0e  lea     edx, [rdi+8]; DesiredAccess
0x18001ec11  call    cs:__imp_OpenProcessToken
0x18001ec17  test    eax, eax
0x18001ec19  jnz     short loc_18001EC25
0x18001ec1b  call    cs:__imp_GetLastError
0x18001ec21  mov     ebx, eax
0x18001ec23  jmp     short loc_18001EC67
0x18001ec25  lea     rax, [rbp+var_40]
0x18001ec29  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x18001ec2e  mov     r9d, 4; TokenInformationLength
0x18001ec34  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18001ec38  lea     edx, [r9+19h]; TokenInformationClass
0x18001ec3c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001ec40  call    cs:__imp_GetTokenInformation
0x18001ec46  test    eax, eax
0x18001ec48  jz      short loc_18001EC55
0x18001ec4a  cmp     dword ptr [rbp+TokenInformation], edi
0x18001ec4d  cmovnz  edi, r15d
0x18001ec51  xor     ebx, ebx
0x18001ec53  jmp     short loc_18001EC5D
0x18001ec55  call    cs:__imp_GetLastError
0x18001ec5b  mov     ebx, eax
0x18001ec5d  mov     rcx, [rbp+TokenHandle]; hObject
0x18001ec61  call    cs:__imp_CloseHandle
0x18001ec67  test    ebx, ebx
0x18001ec69  js      loc_18001EDB2
0x18001ec6f  test    edi, edi
0x18001ec71  jz      loc_18001EDB2
0x18001ec77  mov     [rbp+var_30], 0
0x18001ec7f  mov     [rbp+TokenInformation], 0
0x18001ec87  mov     qword ptr [rbp+var_40], 0
0x18001ec8f  mov     [rbp+TokenHandle], 0
0x18001ec97  mov     [rbp+var_38], 0
0x18001ec9f  mov     [rbp+var_10], 0
0x18001eca7  mov     r9d, 1Fh; unsigned int
0x18001ecad  lea     r8d, [r9+1]; unsigned int
0x18001ecb1  lea     rdx, ?RuntimeClass_Windows_Storage_ApplicationData@@3QBGB; "Windows.Storage.ApplicationData"
0x18001ecb8  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18001ecbc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001ecc1  lea     rdx, [rbp+var_30]
0x18001ecc5  mov     rcx, [rbp+var_10]
0x18001ecc9  call    ??$GetActivationFactory@V?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<IActivationFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IActivationFactory>>)
0x18001ecce  mov     ebx, eax
0x18001ecd0  test    eax, eax
0x18001ecd2  js      loc_18001ED81
0x18001ecd8  mov     rbx, [rbp+var_30]
0x18001ecdc  mov     rax, [rbx]
0x18001ecdf  mov     rdi, [rax]
0x18001ece2  lea     rcx, [rbp+TokenInformation]
0x18001ece6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001eceb  lea     r8, [rbp+TokenInformation]
0x18001ecef  lea     rdx, _GUID_5612147b_e843_45e3_94d8_06169e3c8e17
0x18001ecf6  mov     rcx, rbx
0x18001ecf9  mov     rax, rdi
0x18001ecfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed01  mov     ebx, eax
0x18001ed03  test    eax, eax
0x18001ed05  js      short loc_18001ED81
0x18001ed07  mov     rdi, [rbp+TokenInformation]
0x18001ed0b  mov     rax, [rdi]
0x18001ed0e  mov     rbx, [rax+30h]
0x18001ed12  lea     rcx, [rbp+var_40]
0x18001ed16  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001ed1b  lea     rdx, [rbp+var_40]
0x18001ed1f  mov     rcx, rdi
0x18001ed22  mov     rax, rbx
0x18001ed25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed2a  mov     ebx, eax
0x18001ed2c  test    eax, eax
0x18001ed2e  js      short loc_18001ED81
0x18001ed30  mov     rdi, qword ptr [rbp+var_40]
0x18001ed34  mov     rax, [rdi]
0x18001ed37  mov     rbx, [rax+60h]
0x18001ed3b  lea     rcx, [rbp+TokenHandle]
0x18001ed3f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001ed44  lea     rdx, [rbp+TokenHandle]
0x18001ed48  mov     rcx, rdi
0x18001ed4b  mov     rax, rbx
0x18001ed4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed53  mov     ebx, eax
0x18001ed55  test    eax, eax
0x18001ed57  js      short loc_18001ED81
0x18001ed59  lea     rdx, [rbp+var_38]
0x18001ed5d  lea     rcx, [rbp+TokenHandle]
0x18001ed61  call    ??$As@UIStorageItem@Storage@Windows@@@?$ComPtr@UIStorageFolder@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIStorageItem@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::IStorageFolder>::As<Windows::Storage::IStorageItem>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>>)
0x18001ed66  mov     ebx, eax
0x18001ed68  test    eax, eax
0x18001ed6a  js      short loc_18001ED81
0x18001ed6c  mov     rcx, [rbp+var_38]
0x18001ed70  mov     rax, [rcx]
0x18001ed73  mov     rdx, rsi
0x18001ed76  mov     rax, [rax+60h]
0x18001ed7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed7f  mov     ebx, eax
0x18001ed81  lea     rcx, [rbp+var_38]
0x18001ed85  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001ed8a  nop
0x18001ed8b  lea     rcx, [rbp+TokenHandle]
0x18001ed8f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001ed94  nop
0x18001ed95  lea     rcx, [rbp+var_40]
0x18001ed99  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001ed9e  nop
0x18001ed9f  lea     rcx, [rbp+TokenInformation]
0x18001eda3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001eda8  nop
0x18001eda9  lea     rcx, [rbp+var_30]
0x18001edad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001edb2  mov     eax, ebx
0x18001edb4  mov     rcx, [rbp+var_8]
0x18001edb8  xor     rcx, rsp; StackCookie
0x18001edbb  call    __security_check_cookie
0x18001edc0  lea     r11, [rsp+80h+var_s0]
0x18001edc8  mov     rbx, [r11+28h]
0x18001edcc  mov     rsi, [r11+30h]
0x18001edd0  mov     rsp, r11
0x18001edd3  pop     r15
0x18001edd5  pop     rdi
0x18001edd6  pop     rbp
0x18001edd7  retn
```
