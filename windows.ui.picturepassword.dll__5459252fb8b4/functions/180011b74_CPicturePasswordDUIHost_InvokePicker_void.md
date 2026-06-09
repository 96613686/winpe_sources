# CPicturePasswordDUIHost::_InvokePicker(void)

- ea: `0x180011b74`
- end: `0x180011e7f`
- name: `?_InvokePicker@CPicturePasswordDUIHost@@IEAAXXZ`
- size: `779`
- prototype: `void __fastcall(CPicturePasswordDUIHost *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ee20`

## callees

- `0x180002610`
- `0x1800043a4`
- `0x18000a67c`
- `0x18000c824`
- `0x18000cafc`
- `0x180010cd0`
- `0x180011b74`
- `0x1800135c8`
- `0x1800189c4`
- `0x180018a28`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011be1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011ca3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011d47`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011be1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011ca3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011d47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011bc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011c8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011d5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011bc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011c8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011d5b`

## string_xrefs

- `0x180011bb9`: `Windows.Storage.Pickers.FileOpenPicker`

## pseudocode

```c
void __fastcall CPicturePasswordDUIHost::_InvokePicker(CPicturePasswordDUIHost *this)
{
  int v2; // ebx
  __int64 (__fastcall ***v3)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v4)(_QWORD, GUID *, UINT32 *); // rdi
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v6)(_QWORD, GUID *, UINT32 *); // rdi
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v8)(_QWORD, GUID *, UINT32 *); // rbx
  unsigned int i; // ebx
  __int64 v10; // r14
  unsigned __int64 v11; // rcx
  void (__fastcall *v12)(__int64, HSTRING); // r15
  const WCHAR *v13; // rdi
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v15)(_QWORD, GUID *, UINT32 *); // rbx
  HSTRING v16; // r14
  void *v17; // rax
  volatile signed __int32 *v18; // rdi
  __int64 v19; // rcx
  __int64 (__fastcall ***v20)(_QWORD, GUID *, UINT32 *); // [rsp+20h] [rbp-58h] BYREF
  UINT32 length[2]; // [rsp+28h] [rbp-50h] BYREF
  __int64 v22; // [rsp+30h] [rbp-48h] BYREF
  __int64 v23; // [rsp+38h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF

  *((_BYTE *)this + 865) = 0;
  _TryUnsnapAppView();
  v20 = 0;
  if ( WindowsCreateStringReference(L"Windows.Storage.Pickers.FileOpenPicker", 0x26u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Pickers::IFileOpenPicker>>(
         (__int64)string,
         &v20);
  if ( v2 < 0 )
    goto LABEL_30;
  v3 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v20;
  *(_QWORD *)length = 0;
  v4 = **v20;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(length);
  v2 = v4(v3, &GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1, length);
  if ( v2 >= 0 )
    v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)length + 24LL))(
           *(_QWORD *)length,
           *((_QWORD *)this + 109));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(length);
  if ( v2 < 0 )
    goto LABEL_30;
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, UINT32 *), __int64))(*v20)[7])(v20, 1);
  v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v20;
  v6 = (*v20)[9];
  if ( WindowsCreateStringReference(L"PicturePasswordEnrollment", 0x19u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), HSTRING))v6)(v5, string);
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, UINT32 *), __int64))(*v20)[11])(v20, 6);
  v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v20;
  v23 = 0;
  v8 = (*v20)[14];
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  v2 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v8)(v7, &v23);
  if ( v2 >= 0 )
  {
    for ( i = 0; i < 0xA; ++i )
    {
      v10 = v23;
      length[0] = 0;
      v11 = -1;
      v12 = *(void (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v23 + 104LL);
      v13 = off_180020C70[i];
      do
        ++v11;
      while ( v13[v11] );
      if ( (int)ULongLongToULong(v11, length) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      WindowsCreateStringReference(v13, length[0], &hstringHeader, &string);
      v12(v10, string);
    }
    v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v20;
    v22 = 0;
    v15 = (*v20)[15];
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
    v2 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v15)(v14, &v22);
    if ( v2 >= 0 )
    {
      v16 = (HSTRING)*((_QWORD *)this + 91);
      _InterlockedAdd((volatile signed __int32 *)v16 + 2, 1u);
      v17 = (void *)(*(__int64 (__fastcall **)(CPicturePasswordDUIHost *))(*(_QWORD *)this + 360LL))(this);
      v18 = (volatile signed __int32 *)*((_QWORD *)this + 54);
      if ( v18 )
      {
        v19 = (__int64)(v18 + 8);
        _InterlockedAdd(v18 + 8, 1u);
      }
      else
      {
        v19 = 32;
      }
      string = v16;
      hstringHeader.Reserved.Reserved1 = v17;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v18;
      if ( v18 )
        _InterlockedAdd((volatile signed __int32 *)v19, 1u);
      v2 = StartOperationAndThen_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile____Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile_____lambda_e6df34189ced74daa6b0c48db56ac83e___(
             v22,
             &string);
      if ( v18 )
        CSafeElementProxy::Release((CSafeElementProxy *)v18);
      if ( v2 < 0 )
        CPrivateNotificationWindow::Release((CPrivateNotificationWindow *)v16);
      if ( v18 )
        CSafeElementProxy::Release((CSafeElementProxy *)v18);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  if ( v2 < 0 )
LABEL_30:
    CPrivateNotificationWindow::PostNotification(*((CPrivateNotificationWindow **)this + 91), 0x402u, v2, 0);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
}

```

## disassembly

```asm
0x180011b74  push    rbp
0x180011b76  push    rbx
0x180011b77  push    rsi
0x180011b78  push    rdi
0x180011b79  push    r12
0x180011b7b  push    r13
0x180011b7d  push    r14
0x180011b7f  push    r15
0x180011b81  mov     rbp, rsp
0x180011b84  sub     rsp, 78h
0x180011b88  mov     rax, cs:__security_cookie
0x180011b8f  xor     rax, rsp
0x180011b92  mov     [rbp+var_18], rax
0x180011b96  xor     r12d, r12d
0x180011b99  mov     rsi, rcx
0x180011b9c  mov     [rcx+361h], r12b
0x180011ba3  call    ?_TryUnsnapAppView@@YAXXZ; _TryUnsnapAppView(void)
0x180011ba8  lea     r9, [rbp+string]; string
0x180011bac  mov     [rbp+var_58], r12
0x180011bb0  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180011bb4  lea     edx, [r12+26h]; length
0x180011bb9  lea     rcx, ?RuntimeClass_Windows_Storage_Pickers_FileOpenPicker@@3QBGB; "Windows.Storage.Pickers.FileOpenPicker"
0x180011bc0  call    cs:__imp_WindowsCreateStringReference
0x180011bc6  lea     r13d, [r12+1]
0x180011bcb  mov     r14d, 0C000000Dh
0x180011bd1  test    eax, eax
0x180011bd3  jns     short loc_180011BE7
0x180011bd5  xor     r9d, r9d; lpArguments
0x180011bd8  xor     r8d, r8d; nNumberOfArguments
0x180011bdb  mov     edx, r13d; dwExceptionFlags
0x180011bde  mov     ecx, r14d; dwExceptionCode
0x180011be1  call    cs:__imp_RaiseException
0x180011be7  mov     rcx, [rbp+string]
0x180011beb  lea     rdx, [rbp+var_58]
0x180011bef  call    ??$ActivateInstance@V?$ComPtr@UIFileOpenPicker@Pickers@Storage@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIFileOpenPicker@Pickers@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Pickers::IFileOpenPicker>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Pickers::IFileOpenPicker>>)
0x180011bf4  mov     ebx, eax
0x180011bf6  test    eax, eax
0x180011bf8  js      loc_180011E42
0x180011bfe  mov     rbx, [rbp+var_58]
0x180011c02  lea     rcx, [rbp+length]
0x180011c06  mov     qword ptr [rbp+length], r12
0x180011c0a  mov     rax, [rbx]
0x180011c0d  mov     rdi, [rax]
0x180011c10  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011c15  lea     r8, [rbp+length]
0x180011c19  mov     rcx, rbx
0x180011c1c  lea     rdx, _GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1
0x180011c23  mov     rax, rdi
0x180011c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c2b  mov     ebx, eax
0x180011c2d  test    eax, eax
0x180011c2f  js      short loc_180011C4A
0x180011c31  mov     rcx, qword ptr [rbp+length]
0x180011c35  mov     rdx, [rsi+368h]
0x180011c3c  mov     rax, [rcx]
0x180011c3f  mov     rax, [rax+18h]
0x180011c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c48  mov     ebx, eax
0x180011c4a  lea     rcx, [rbp+length]
0x180011c4e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011c53  test    ebx, ebx
0x180011c55  js      loc_180011E42
0x180011c5b  mov     rcx, [rbp+var_58]
0x180011c5f  mov     edx, r13d
0x180011c62  mov     rax, [rcx]
0x180011c65  mov     rax, [rax+38h]
0x180011c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c6e  mov     rbx, [rbp+var_58]
0x180011c72  lea     r9, [rbp+string]; string
0x180011c76  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180011c7a  mov     edx, 19h; length
0x180011c7f  lea     rcx, sourceString; "PicturePasswordEnrollment"
0x180011c86  mov     rax, [rbx]
0x180011c89  mov     rdi, [rax+48h]
0x180011c8d  call    cs:__imp_WindowsCreateStringReference
0x180011c93  test    eax, eax
0x180011c95  jns     short loc_180011CA9
0x180011c97  xor     r9d, r9d; lpArguments
0x180011c9a  xor     r8d, r8d; nNumberOfArguments
0x180011c9d  mov     edx, r13d; dwExceptionFlags
0x180011ca0  mov     ecx, r14d; dwExceptionCode
0x180011ca3  call    cs:__imp_RaiseException
0x180011ca9  mov     rdx, [rbp+string]
0x180011cad  mov     rcx, rbx
0x180011cb0  mov     rax, rdi
0x180011cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cb8  mov     rcx, [rbp+var_58]
0x180011cbc  mov     edx, 6
0x180011cc1  mov     rax, [rcx]
0x180011cc4  mov     rax, [rax+58h]
0x180011cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ccd  mov     rdi, [rbp+var_58]
0x180011cd1  lea     rcx, [rbp+var_40]
0x180011cd5  mov     [rbp+var_40], r12
0x180011cd9  mov     rax, [rdi]
0x180011cdc  mov     rbx, [rax+70h]
0x180011ce0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011ce5  lea     rdx, [rbp+var_40]
0x180011ce9  mov     rcx, rdi
0x180011cec  mov     rax, rbx
0x180011cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cf4  mov     ebx, eax
0x180011cf6  test    eax, eax
0x180011cf8  js      loc_180011E35
0x180011cfe  mov     ebx, r12d
0x180011d01  mov     r14, [rbp+var_40]
0x180011d05  lea     rdi, off_180020C70; ".jpg"
0x180011d0c  mov     [rbp+length], r12d
0x180011d10  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180011d14  mov     rax, [r14]
0x180011d17  mov     r15, [rax+68h]
0x180011d1b  movsxd  rax, ebx
0x180011d1e  mov     rdi, [rdi+rax*8]
0x180011d22  inc     rcx; unsigned __int64
0x180011d25  cmp     [rdi+rcx*2], r12w
0x180011d2a  jnz     short loc_180011D22
0x180011d2c  lea     rdx, [rbp+length]; unsigned int *
0x180011d30  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180011d35  test    eax, eax
0x180011d37  jns     short loc_180011D4D
0x180011d39  xor     r9d, r9d; lpArguments
0x180011d3c  xor     r8d, r8d; nNumberOfArguments
0x180011d3f  mov     edx, r13d; dwExceptionFlags
0x180011d42  mov     ecx, 0C000000Dh; dwExceptionCode
0x180011d47  call    cs:__imp_RaiseException
0x180011d4d  mov     edx, [rbp+length]; length
0x180011d50  lea     r9, [rbp+string]; string
0x180011d54  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180011d58  mov     rcx, rdi; sourceString
0x180011d5b  call    cs:__imp_WindowsCreateStringReference
0x180011d61  mov     rdx, [rbp+string]
0x180011d65  mov     rcx, r14
0x180011d68  mov     rax, r15
0x180011d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d70  add     ebx, r13d
0x180011d73  cmp     ebx, 0Ah
0x180011d76  jb      short loc_180011D01
0x180011d78  mov     rdi, [rbp+var_58]
0x180011d7c  lea     rcx, [rbp+var_48]
0x180011d80  mov     [rbp+var_48], r12
0x180011d84  mov     rax, [rdi]
0x180011d87  mov     rbx, [rax+78h]
0x180011d8b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011d90  lea     rdx, [rbp+var_48]
0x180011d94  mov     rcx, rdi
0x180011d97  mov     rax, rbx
0x180011d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d9f  mov     ebx, eax
0x180011da1  test    eax, eax
0x180011da3  js      loc_180011E2C
0x180011da9  mov     r14, [rsi+2D8h]
0x180011db0  lock add [r14+8], r13d
0x180011db5  mov     rax, [rsi]
0x180011db8  mov     rcx, rsi
0x180011dbb  mov     rax, [rax+168h]
0x180011dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dc7  mov     rdi, [rsi+1B0h]
0x180011dce  test    rdi, rdi
0x180011dd1  jz      short loc_180011DDD
0x180011dd3  lea     rcx, [rdi+20h]
0x180011dd7  lock add [rcx], r13d
0x180011ddb  jmp     short loc_180011DE2
0x180011ddd  mov     ecx, 20h ; ' '
0x180011de2  mov     [rbp+string], r14
0x180011de6  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x180011dea  mov     qword ptr [rbp+hstringHeader.Reserved+8], rdi
0x180011dee  test    rdi, rdi
0x180011df1  jz      short loc_180011DF7
0x180011df3  lock add [rcx], r13d
0x180011df7  mov     rcx, [rbp+var_48]
0x180011dfb  lea     rdx, [rbp+string]
0x180011dff  call    StartOperationAndThen_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Storage__StorageFile____Windows__Foundation__IAsyncOperation_Windows__Storage__StorageFile_____lambda_e6df34189ced74daa6b0c48db56ac83e___
0x180011e04  mov     ebx, eax
0x180011e06  test    rdi, rdi
0x180011e09  jz      short loc_180011E13
0x180011e0b  mov     rcx, rdi; this
0x180011e0e  call    ?Release@CSafeElementProxy@@QEAAKXZ; CSafeElementProxy::Release(void)
0x180011e13  test    ebx, ebx
0x180011e15  jns     short loc_180011E1F
0x180011e17  mov     rcx, r14; this
0x180011e1a  call    ?Release@CPrivateNotificationWindow@@QEAAKXZ; CPrivateNotificationWindow::Release(void)
0x180011e1f  test    rdi, rdi
0x180011e22  jz      short loc_180011E2C
0x180011e24  mov     rcx, rdi; this
0x180011e27  call    ?Release@CSafeElementProxy@@QEAAKXZ; CSafeElementProxy::Release(void)
0x180011e2c  lea     rcx, [rbp+var_48]
0x180011e30  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011e35  lea     rcx, [rbp+var_40]
0x180011e39  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011e3e  test    ebx, ebx
0x180011e40  jns     short loc_180011E59
0x180011e42  mov     rcx, [rsi+2D8h]; this
0x180011e49  xor     r9d, r9d; __int64
0x180011e4c  movsxd  r8, ebx; unsigned __int64
0x180011e4f  mov     edx, 402h; unsigned int
0x180011e54  call    ?PostNotification@CPrivateNotificationWindow@@QEAA_NI_K_J@Z; CPrivateNotificationWindow::PostNotification(uint,unsigned __int64,__int64)
0x180011e59  lea     rcx, [rbp+var_58]
0x180011e5d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011e62  mov     rcx, [rbp+var_18]
0x180011e66  xor     rcx, rsp; StackCookie
0x180011e69  call    __security_check_cookie
0x180011e6e  add     rsp, 78h
0x180011e72  pop     r15
0x180011e74  pop     r14
0x180011e76  pop     r13
0x180011e78  pop     r12
0x180011e7a  pop     rdi
0x180011e7b  pop     rsi
0x180011e7c  pop     rbx
0x180011e7d  pop     rbp
0x180011e7e  retn
```
