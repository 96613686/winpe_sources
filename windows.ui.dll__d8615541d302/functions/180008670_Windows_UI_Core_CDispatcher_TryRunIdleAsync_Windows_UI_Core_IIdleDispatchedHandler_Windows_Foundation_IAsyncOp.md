# Windows::UI::Core::CDispatcher::TryRunIdleAsync(Windows::UI::Core::IIdleDispatchedHandler *,Windows::Foundation::IAsyncOperation<bool> * *)

- ea: `0x180008670`
- end: `0x1800088d8`
- name: `?TryRunIdleAsync@CDispatcher@Core@UI@Windows@@UEAAJPEAUIIdleDispatchedHandler@234@PEAPEAU?$IAsyncOperation@_N@Foundation@4@@Z`
- size: `616`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180008670`
- `0x180008b50`
- `0x180009260`
- `0x1800362e0`
- `0x18008aa80`
- `0x18008ac44`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000879e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000879e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008872`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008872`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Core::CDispatcher::TryRunIdleAsync(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rdi
  int v6; // ebx
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, _QWORD); // rdi
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rcx
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  unsigned int NextAsyncInfoId; // eax
  int v15; // r8d
  __int64 (__fastcall ***v16)(_QWORD, GUID *, _QWORD); // rax
  const char *v17; // rax
  __int64 (__fastcall ***v18)(_QWORD, GUID *, _QWORD); // [rsp+60h] [rbp+20h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, _QWORD); // [rsp+70h] [rbp+30h] BYREF

  v19 = 0;
  *a3 = 0;
  v5 = a1 - 24;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v19);
  v19 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_qDdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v13, v5, *(_DWORD *)(v5 + 120), -2, CurrentThreadId);
  }
  if ( *(_DWORD *)(v5 + 188) )
  {
    v18 = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v18);
    NextAsyncInfoId = Windows::UI::Core::CDispatcher::GetNextAsyncInfoId((Windows::UI::Core::CDispatcher *)v5);
    v6 = Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,&unsigned short const near * const Windows::UI::Core::AsyncOperationName,&unsigned short const near * const Windows::UI::Core::CoreAsyncOperationName>>(
           NextAsyncInfoId,
           &v18);
    if ( v6 < 0
      || (v6 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v18)[10])(v18), v6 < 0) )
    {
      RoOriginateError((unsigned int)v6, 0);
    }
    else
    {
      (*v18)[6](v18, 0, 3);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD), _QWORD))(*v18)[8])(v18, 0);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v18)[12])(v18);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v18)[9])(v18);
      v16 = v18;
      v18 = 0;
      v19 = v16;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = "main view CoreWindow";
      if ( !*(_BYTE *)(v5 + 212) )
        v17 = "secondary view or CoreInput";
      WPP_SF_qDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)"secondary view or CoreInput",
        v15,
        v5,
        *(_DWORD *)(v5 + 120),
        (__int64)v17);
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v18);
  }
  else
  {
    v6 = Windows::UI::Core::CDispatcher::EnqueueAsyncWork(
           v5,
           (__int64 (__fastcall *)(__int64, __int64 *))Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,&unsigned short const near * const Windows::UI::Core::AsyncOperationName,&unsigned short const near * const Windows::UI::Core::CoreAsyncOperationName>>,
           -2,
           0,
           a2,
           &v19);
  }
  if ( v6 >= 0 )
  {
    v18 = 0;
    v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19;
    v8 = **v19;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v18);
    v6 = v8(v7, &GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a, &v18);
    if ( v6 < 0 )
    {
      v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v18;
    }
    else
    {
      v9 = 0;
      *a3 = v18;
    }
    if ( v9 )
    {
      v18 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v9)[2])(v9);
    }
  }
  v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19;
  if ( v19 )
  {
    v19 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v10)[2])(v10);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008670  mov     [rsp-18h+arg_8], rbx
0x180008675  mov     [rsp-18h+arg_18], rsi
0x18000867a  push    rbp
0x18000867b  push    rdi
0x18000867c  push    r13
0x18000867e  mov     rbp, rsp
0x180008681  sub     rsp, 40h
0x180008685  mov     rsi, r8
0x180008688  mov     rbx, rdx
0x18000868b  mov     [rbp+arg_10], 0
0x180008693  mov     qword ptr [r8], 0
0x18000869a  lea     rdi, [rcx-18h]
0x18000869e  lea     rcx, [rbp+arg_10]
0x1800086a2  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800086a7  mov     [rbp+arg_10], 0
0x1800086af  lea     r13, WPP_GLOBAL_Control
0x1800086b6  mov     rax, cs:WPP_GLOBAL_Control
0x1800086bd  cmp     rax, r13
0x1800086c0  jz      short loc_1800086CC
0x1800086c2  test    byte ptr [rax+1Ch], 4
0x1800086c6  jnz     loc_180008794
0x1800086cc  cmp     dword ptr [rdi+0BCh], 0
0x1800086d3  jnz     loc_1800087D4
0x1800086d9  lea     rax, [rbp+arg_10]
0x1800086dd  mov     [rsp+40h+var_18], rax
0x1800086e2  mov     [rsp+40h+var_20], rbx
0x1800086e7  xor     r9d, r9d
0x1800086ea  lea     r8d, [r9-2]
0x1800086ee  lea     rdx, ??$CoreAsyncInfo_CreateInstance@V?$CCoreAsyncBase@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@$1?AsyncOperationName@Core@UI@3@3QBGB$1?CoreAsyncOperationName@673@3QBGB@Core@UI@Windows@@@Core@UI@Windows@@YAJIPEAPEAUICoreAsyncInfo@012@@Z; Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,&ushort const near * const Windows::UI::Core::AsyncOperationName,&ushort const near * const Windows::UI::Core::CoreAsyncOperationName>>(uint,Windows::UI::Core::ICoreAsyncInfo * *)
0x1800086f5  mov     rcx, rdi
0x1800086f8  call    ?EnqueueAsyncWork@CDispatcher@Core@UI@Windows@@AEAAJP6AJIPEAPEAUICoreAsyncInfo@234@@ZW4CoreDispatcherPriority@234@PEAUIDispatchedHandler@234@PEAUIIdleDispatchedHandler@234@0@Z; Windows::UI::Core::CDispatcher::EnqueueAsyncWork(long (*)(uint,Windows::UI::Core::ICoreAsyncInfo * *),Windows::UI::Core::CoreDispatcherPriority,Windows::UI::Core::IDispatchedHandler *,Windows::UI::Core::IIdleDispatchedHandler *,Windows::UI::Core::ICoreAsyncInfo * *)
0x1800086fd  mov     ebx, eax
0x1800086ff  test    ebx, ebx
0x180008701  js      short loc_180008761
0x180008703  mov     [rbp+arg_0], 0
0x18000870b  mov     rbx, [rbp+arg_10]
0x18000870f  mov     rax, [rbx]
0x180008712  mov     rdi, [rax]
0x180008715  lea     rcx, [rbp+arg_0]
0x180008719  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000871e  lea     r8, [rbp+arg_0]
0x180008722  lea     rdx, _GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a
0x180008729  mov     rcx, rbx
0x18000872c  mov     rax, rdi
0x18000872f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008734  mov     ebx, eax
0x180008736  test    eax, eax
0x180008738  js      loc_1800088CF
0x18000873e  mov     rax, [rbp+arg_0]
0x180008742  xor     ecx, ecx
0x180008744  mov     [rsi], rax
0x180008747  test    rcx, rcx
0x18000874a  jz      short loc_180008761
0x18000874c  mov     [rbp+arg_0], 0
0x180008754  mov     rax, [rcx]
0x180008757  mov     rax, [rax+10h]
0x18000875b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008760  nop
0x180008761  mov     rcx, [rbp+arg_10]
0x180008765  test    rcx, rcx
0x180008768  jz      short loc_18000877F
0x18000876a  mov     [rbp+arg_10], 0
0x180008772  mov     rdx, [rcx]
0x180008775  mov     rax, [rdx+10h]
0x180008779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000877e  nop
0x18000877f  mov     eax, ebx
0x180008781  mov     rbx, [rsp+40h+arg_8]
0x180008786  mov     rsi, [rsp+40h+arg_18]
0x18000878b  add     rsp, 40h
0x18000878f  pop     r13
0x180008791  pop     rdi
0x180008792  pop     rbp
0x180008793  retn
0x180008794  cmp     byte ptr [rax+19h], 4
0x180008798  jb      loc_1800086CC
0x18000879e  call    cs:__imp_GetCurrentThreadId
0x1800087a4  mov     edx, 13h
0x1800087a9  mov     [rsp+40h+var_10], eax
0x1800087ad  mov     dword ptr [rsp+40h+var_18], 0FFFFFFFEh
0x1800087b5  mov     eax, [rdi+78h]
0x1800087b8  mov     dword ptr [rsp+40h+var_20], eax
0x1800087bc  mov     r9, rdi
0x1800087bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087c6  mov     rcx, [rcx+10h]
0x1800087ca  call    WPP_SF_qDdD
0x1800087cf  jmp     loc_1800086CC
0x1800087d4  mov     [rbp+arg_0], 0
0x1800087dc  lea     rcx, [rbp+arg_0]
0x1800087e0  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800087e5  mov     rcx, rdi; this
0x1800087e8  call    ?GetNextAsyncInfoId@CDispatcher@Core@UI@Windows@@AEAAIXZ; Windows::UI::Core::CDispatcher::GetNextAsyncInfoId(void)
0x1800087ed  lea     rdx, [rbp+arg_0]
0x1800087f1  mov     ecx, eax
0x1800087f3  call    ??$CoreAsyncInfo_CreateInstance@V?$CCoreAsyncBase@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@$1?AsyncOperationName@Core@UI@3@3QBGB$1?CoreAsyncOperationName@673@3QBGB@Core@UI@Windows@@@Core@UI@Windows@@YAJIPEAPEAUICoreAsyncInfo@012@@Z; Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,&ushort const near * const Windows::UI::Core::AsyncOperationName,&ushort const near * const Windows::UI::Core::CoreAsyncOperationName>>(uint,Windows::UI::Core::ICoreAsyncInfo * *)
0x1800087f8  mov     ebx, eax
0x1800087fa  test    eax, eax
0x1800087fc  js      short loc_18000886E
0x1800087fe  mov     rcx, [rbp+arg_0]
0x180008802  mov     rax, [rcx]
0x180008805  mov     rax, [rax+50h]
0x180008809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000880e  mov     ebx, eax
0x180008810  test    eax, eax
0x180008812  js      short loc_18000886E
0x180008814  mov     rcx, [rbp+arg_0]
0x180008818  mov     rax, [rcx]
0x18000881b  xor     edx, edx
0x18000881d  lea     r8d, [rdx+3]
0x180008821  mov     rax, [rax+30h]
0x180008825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000882a  mov     rcx, [rbp+arg_0]
0x18000882e  mov     rax, [rcx]
0x180008831  xor     edx, edx
0x180008833  mov     rax, [rax+40h]
0x180008837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000883c  mov     rcx, [rbp+arg_0]
0x180008840  mov     rax, [rcx]
0x180008843  mov     rax, [rax+60h]
0x180008847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000884c  mov     rcx, [rbp+arg_0]
0x180008850  mov     rax, [rcx]
0x180008853  mov     rax, [rax+48h]
0x180008857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000885c  mov     rax, [rbp+arg_0]
0x180008860  mov     [rbp+arg_0], 0
0x180008868  mov     [rbp+arg_10], rax
0x18000886c  jmp     short loc_180008878
0x18000886e  xor     edx, edx
0x180008870  mov     ecx, ebx
0x180008872  call    cs:__imp_RoOriginateError
0x180008878  mov     rcx, cs:WPP_GLOBAL_Control
0x18000887f  cmp     rcx, r13
0x180008882  jz      short loc_1800088C1
0x180008884  test    byte ptr [rcx+1Ch], 4
0x180008888  jz      short loc_1800088C1
0x18000888a  cmp     byte ptr [rcx+19h], 2
0x18000888e  jb      short loc_1800088C1
0x180008890  lea     rdx, aSecondaryViewO; "secondary view or CoreInput"
0x180008897  lea     rax, aMainViewCorewi; "main view CoreWindow"
0x18000889e  cmp     byte ptr [rdi+0D4h], 0
0x1800088a5  cmovz   rax, rdx
0x1800088a9  mov     [rsp+40h+var_18], rax
0x1800088ae  mov     eax, [rdi+78h]
0x1800088b1  mov     dword ptr [rsp+40h+var_20], eax
0x1800088b5  mov     r9, rdi
0x1800088b8  mov     rcx, [rcx+10h]
0x1800088bc  call    WPP_SF_qDs
0x1800088c1  lea     rcx, [rbp+arg_0]
0x1800088c5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800088ca  jmp     loc_1800086FF
0x1800088cf  mov     rcx, [rbp+arg_0]
0x1800088d3  jmp     loc_180008747
```
