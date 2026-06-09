# Windows::UI::Core::CDispatcher::TryRunAsync(Windows::UI::Core::CoreDispatcherPriority,Windows::UI::Core::IDispatchedHandler *,Windows::Foundation::IAsyncOperation<bool> * *)

- ea: `0x180008c60`
- end: `0x180008f5d`
- name: `?TryRunAsync@CDispatcher@Core@UI@Windows@@UEAAJW4CoreDispatcherPriority@234@PEAUIDispatchedHandler@234@PEAPEAU?$IAsyncOperation@_N@Foundation@4@@Z`
- size: `765`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180008b50`
- `0x180008c60`
- `0x180009260`
- `0x1800362e0`
- `0x180071c60`
- `0x18008aa80`
- `0x18008ac44`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e27`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008ef7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008ef7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180008dcd`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180008dcd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Core::CDispatcher::TryRunAsync(__int64 a1, int a2, _QWORD *a3, _QWORD *a4)
{
  __int64 v8; // rdi
  int v9; // ebx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, _QWORD); // rdi
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rcx
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  unsigned int NextAsyncInfoId; // eax
  int v18; // r8d
  __int64 (__fastcall ***v19)(_QWORD, GUID *, _QWORD); // rax
  const char *v20; // rax
  int v21; // [rsp+28h] [rbp-50h]
  __int64 (__fastcall ***v22)(_QWORD, GUID *, _QWORD); // [rsp+40h] [rbp-38h] BYREF
  __int64 (__fastcall ***v23)(_QWORD, GUID *, _QWORD); // [rsp+48h] [rbp-30h] BYREF
  __int128 v24; // [rsp+50h] [rbp-28h] BYREF
  wchar_t v25; // [rsp+60h] [rbp-18h]

  *a4 = 0;
  if ( (unsigned int)(a2 + 1) > 2 )
  {
    v9 = -2147024809;
    v24 = *(_OWORD *)L"priority";
    v25 = aPriority[8];
    RoOriginateErrorW(2147942487LL, 8, &v24);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = a2;
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids,
        a1 - 24,
        *(_DWORD *)(a1 - 24 + 120),
        v21);
    }
  }
  else
  {
    v23 = 0;
    v8 = a1 - 24;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v23);
    v23 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_qDdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v16, v8, *(_DWORD *)(v8 + 120), a2, CurrentThreadId);
    }
    if ( *(_DWORD *)(v8 + 188) )
    {
      v22 = 0;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v22);
      NextAsyncInfoId = Windows::UI::Core::CDispatcher::GetNextAsyncInfoId((Windows::UI::Core::CDispatcher *)v8);
      v9 = Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,&unsigned short const near * const Windows::UI::Core::AsyncOperationName,&unsigned short const near * const Windows::UI::Core::CoreAsyncOperationName>>(
             NextAsyncInfoId,
             &v22);
      if ( v9 < 0
        || (v9 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v22)[10])(v22), v9 < 0) )
      {
        RoOriginateError((unsigned int)v9, 0);
      }
      else
      {
        (*v22)[6](v22, 0, 3);
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD), _QWORD))(*v22)[8])(v22, 0);
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v22)[12])(v22);
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v22)[9])(v22);
        v19 = v22;
        v22 = 0;
        v23 = v19;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = "main view CoreWindow";
        if ( !*(_BYTE *)(v8 + 212) )
          v20 = "secondary view or CoreInput";
        WPP_SF_qDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)"secondary view or CoreInput",
          v18,
          v8,
          *(_DWORD *)(v8 + 120),
          (__int64)v20);
      }
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v22);
    }
    else
    {
      v9 = Windows::UI::Core::CDispatcher::EnqueueAsyncWork(
             v8,
             (__int64 (__fastcall *)(__int64, __int64 *))Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,&unsigned short const near * const Windows::UI::Core::AsyncOperationName,&unsigned short const near * const Windows::UI::Core::CoreAsyncOperationName>>,
             a2,
             a3,
             0,
             &v23);
    }
    if ( v9 >= 0 )
    {
      v22 = 0;
      v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
      v11 = **v23;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v22);
      v9 = v11(v10, &GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a, &v22);
      if ( v9 < 0 )
      {
        v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v22;
      }
      else
      {
        v12 = 0;
        *a4 = v22;
      }
      if ( v12 )
      {
        v22 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v12)[2])(v12);
      }
    }
    v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
    if ( v23 )
    {
      v23 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v13)[2])(v13);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180008c60  push    rbp
0x180008c62  push    rbx
0x180008c63  push    rsi
0x180008c64  push    rdi
0x180008c65  push    r14
0x180008c67  push    r15
0x180008c69  mov     rbp, rsp
0x180008c6c  sub     rsp, 78h
0x180008c70  mov     rax, cs:__security_cookie
0x180008c77  xor     rax, rsp
0x180008c7a  mov     [rbp+var_10], rax
0x180008c7e  mov     r15, r9
0x180008c81  mov     rbx, r8
0x180008c84  mov     esi, edx
0x180008c86  mov     rdi, rcx
0x180008c89  mov     qword ptr [r9], 0
0x180008c90  lea     eax, [rdx+1]
0x180008c93  cmp     eax, 2
0x180008c96  ja      loc_180008DA7
0x180008c9c  mov     [rbp+var_30], 0
0x180008ca4  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180008ca8  lea     rcx, [rbp+var_30]
0x180008cac  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180008cb1  mov     [rbp+var_30], 0
0x180008cb9  lea     r14, WPP_GLOBAL_Control
0x180008cc0  mov     rax, cs:WPP_GLOBAL_Control
0x180008cc7  cmp     rax, r14
0x180008cca  jz      short loc_180008CD6
0x180008ccc  test    byte ptr [rax+1Ch], 4
0x180008cd0  jnz     loc_180008E1D
0x180008cd6  cmp     dword ptr [rdi+0BCh], 0
0x180008cdd  jnz     loc_180008E59
0x180008ce3  lea     rax, [rbp+var_30]
0x180008ce7  mov     [rsp+78h+var_50], rax
0x180008cec  mov     [rsp+78h+var_58], 0
0x180008cf5  mov     r9, rbx
0x180008cf8  mov     r8d, esi
0x180008cfb  lea     rdx, ??$CoreAsyncInfo_CreateInstance@V?$CCoreAsyncBase@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@$1?AsyncOperationName@Core@UI@3@3QBGB$1?CoreAsyncOperationName@673@3QBGB@Core@UI@Windows@@@Core@UI@Windows@@YAJIPEAPEAUICoreAsyncInfo@012@@Z; Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,&ushort const near * const Windows::UI::Core::AsyncOperationName,&ushort const near * const Windows::UI::Core::CoreAsyncOperationName>>(uint,Windows::UI::Core::ICoreAsyncInfo * *)
0x180008d02  mov     rcx, rdi
0x180008d05  call    ?EnqueueAsyncWork@CDispatcher@Core@UI@Windows@@AEAAJP6AJIPEAPEAUICoreAsyncInfo@234@@ZW4CoreDispatcherPriority@234@PEAUIDispatchedHandler@234@PEAUIIdleDispatchedHandler@234@0@Z; Windows::UI::Core::CDispatcher::EnqueueAsyncWork(long (*)(uint,Windows::UI::Core::ICoreAsyncInfo * *),Windows::UI::Core::CoreDispatcherPriority,Windows::UI::Core::IDispatchedHandler *,Windows::UI::Core::IIdleDispatchedHandler *,Windows::UI::Core::ICoreAsyncInfo * *)
0x180008d0a  mov     ebx, eax
0x180008d0c  test    ebx, ebx
0x180008d0e  js      short loc_180008D6E
0x180008d10  mov     [rbp+var_38], 0
0x180008d18  mov     rbx, [rbp+var_30]
0x180008d1c  mov     rax, [rbx]
0x180008d1f  mov     rdi, [rax]
0x180008d22  lea     rcx, [rbp+var_38]
0x180008d26  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180008d2b  lea     r8, [rbp+var_38]
0x180008d2f  lea     rdx, _GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a
0x180008d36  mov     rcx, rbx
0x180008d39  mov     rax, rdi
0x180008d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d41  mov     ebx, eax
0x180008d43  test    eax, eax
0x180008d45  js      loc_180008F54
0x180008d4b  mov     rax, [rbp+var_38]
0x180008d4f  xor     ecx, ecx
0x180008d51  mov     [r15], rax
0x180008d54  test    rcx, rcx
0x180008d57  jz      short loc_180008D6E
0x180008d59  mov     [rbp+var_38], 0
0x180008d61  mov     rax, [rcx]
0x180008d64  mov     rax, [rax+10h]
0x180008d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d6d  nop
0x180008d6e  mov     rcx, [rbp+var_30]
0x180008d72  test    rcx, rcx
0x180008d75  jz      short loc_180008D8C
0x180008d77  mov     [rbp+var_30], 0
0x180008d7f  mov     rax, [rcx]
0x180008d82  mov     rax, [rax+10h]
0x180008d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d8b  nop
0x180008d8c  mov     eax, ebx
0x180008d8e  mov     rcx, [rbp+var_10]
0x180008d92  xor     rcx, rsp; StackCookie
0x180008d95  call    __security_check_cookie
0x180008d9a  add     rsp, 78h
0x180008d9e  pop     r15
0x180008da0  pop     r14
0x180008da2  pop     rdi
0x180008da3  pop     rsi
0x180008da4  pop     rbx
0x180008da5  pop     rbp
0x180008da6  retn
0x180008da7  mov     ebx, 80070057h
0x180008dac  movups  xmm0, xmmword ptr cs:aPriority; "priority"
0x180008db3  movups  [rbp+var_28], xmm0
0x180008db7  movzx   eax, word ptr cs:aPriority+10h; ""
0x180008dbe  mov     [rbp+var_18], ax
0x180008dc2  lea     r8, [rbp+var_28]
0x180008dc6  mov     edx, 8
0x180008dcb  mov     ecx, ebx
0x180008dcd  call    cs:__imp_RoOriginateErrorW
0x180008dd3  lea     r14, WPP_GLOBAL_Control
0x180008dda  mov     rcx, cs:WPP_GLOBAL_Control
0x180008de1  cmp     rcx, r14
0x180008de4  jz      short loc_180008D8C
0x180008de6  test    byte ptr [rcx+1Ch], 4
0x180008dea  jz      short loc_180008D8C
0x180008dec  cmp     byte ptr [rcx+19h], 2
0x180008df0  jb      short loc_180008D8C
0x180008df2  lea     r9, [rdi-18h]
0x180008df6  mov     edx, 12h
0x180008dfb  mov     dword ptr [rsp+78h+var_50], esi
0x180008dff  mov     r8d, [r9+78h]
0x180008e03  mov     dword ptr [rsp+78h+var_58], r8d
0x180008e08  lea     r8, WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids
0x180008e0f  mov     rcx, [rcx+10h]
0x180008e13  call    WPP_SF_qDD
0x180008e18  jmp     loc_180008D8C
0x180008e1d  cmp     byte ptr [rax+19h], 4
0x180008e21  jb      loc_180008CD6
0x180008e27  call    cs:__imp_GetCurrentThreadId
0x180008e2d  mov     edx, 13h
0x180008e32  mov     [rsp+78h+var_48], eax
0x180008e36  mov     dword ptr [rsp+78h+var_50], esi
0x180008e3a  mov     eax, [rdi+78h]
0x180008e3d  mov     dword ptr [rsp+78h+var_58], eax
0x180008e41  mov     r9, rdi
0x180008e44  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e4b  mov     rcx, [rcx+10h]
0x180008e4f  call    WPP_SF_qDdD
0x180008e54  jmp     loc_180008CD6
0x180008e59  mov     [rbp+var_38], 0
0x180008e61  lea     rcx, [rbp+var_38]
0x180008e65  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180008e6a  mov     rcx, rdi; this
0x180008e6d  call    ?GetNextAsyncInfoId@CDispatcher@Core@UI@Windows@@AEAAIXZ; Windows::UI::Core::CDispatcher::GetNextAsyncInfoId(void)
0x180008e72  lea     rdx, [rbp+var_38]
0x180008e76  mov     ecx, eax
0x180008e78  call    ??$CoreAsyncInfo_CreateInstance@V?$CCoreAsyncBase@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@$1?AsyncOperationName@Core@UI@3@3QBGB$1?CoreAsyncOperationName@673@3QBGB@Core@UI@Windows@@@Core@UI@Windows@@YAJIPEAPEAUICoreAsyncInfo@012@@Z; Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,&ushort const near * const Windows::UI::Core::AsyncOperationName,&ushort const near * const Windows::UI::Core::CoreAsyncOperationName>>(uint,Windows::UI::Core::ICoreAsyncInfo * *)
0x180008e7d  mov     ebx, eax
0x180008e7f  test    eax, eax
0x180008e81  js      short loc_180008EF3
0x180008e83  mov     rcx, [rbp+var_38]
0x180008e87  mov     rax, [rcx]
0x180008e8a  mov     rax, [rax+50h]
0x180008e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e93  mov     ebx, eax
0x180008e95  test    eax, eax
0x180008e97  js      short loc_180008EF3
0x180008e99  mov     rcx, [rbp+var_38]
0x180008e9d  mov     rax, [rcx]
0x180008ea0  xor     edx, edx
0x180008ea2  lea     r8d, [rdx+3]
0x180008ea6  mov     rax, [rax+30h]
0x180008eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eaf  mov     rcx, [rbp+var_38]
0x180008eb3  mov     rax, [rcx]
0x180008eb6  xor     edx, edx
0x180008eb8  mov     rax, [rax+40h]
0x180008ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ec1  mov     rcx, [rbp+var_38]
0x180008ec5  mov     rax, [rcx]
0x180008ec8  mov     rax, [rax+60h]
0x180008ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ed1  mov     rcx, [rbp+var_38]
0x180008ed5  mov     rax, [rcx]
0x180008ed8  mov     rax, [rax+48h]
0x180008edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ee1  mov     rax, [rbp+var_38]
0x180008ee5  mov     [rbp+var_38], 0
0x180008eed  mov     [rbp+var_30], rax
0x180008ef1  jmp     short loc_180008EFD
0x180008ef3  xor     edx, edx
0x180008ef5  mov     ecx, ebx
0x180008ef7  call    cs:__imp_RoOriginateError
0x180008efd  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f04  cmp     rcx, r14
0x180008f07  jz      short loc_180008F46
0x180008f09  test    byte ptr [rcx+1Ch], 4
0x180008f0d  jz      short loc_180008F46
0x180008f0f  cmp     byte ptr [rcx+19h], 2
0x180008f13  jb      short loc_180008F46
0x180008f15  lea     rdx, aSecondaryViewO; "secondary view or CoreInput"
0x180008f1c  lea     rax, aMainViewCorewi; "main view CoreWindow"
0x180008f23  cmp     byte ptr [rdi+0D4h], 0
0x180008f2a  cmovz   rax, rdx
0x180008f2e  mov     [rsp+78h+var_50], rax
0x180008f33  mov     eax, [rdi+78h]
0x180008f36  mov     dword ptr [rsp+78h+var_58], eax
0x180008f3a  mov     r9, rdi
0x180008f3d  mov     rcx, [rcx+10h]
0x180008f41  call    WPP_SF_qDs
0x180008f46  lea     rcx, [rbp+var_38]
0x180008f4a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180008f4f  jmp     loc_180008D0C
0x180008f54  mov     rcx, [rbp+var_38]
0x180008f58  jmp     loc_180008D54
```
