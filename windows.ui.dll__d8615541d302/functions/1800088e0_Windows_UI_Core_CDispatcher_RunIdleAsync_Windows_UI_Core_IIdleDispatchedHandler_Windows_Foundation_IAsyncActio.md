# Windows::UI::Core::CDispatcher::RunIdleAsync(Windows::UI::Core::IIdleDispatchedHandler *,Windows::Foundation::IAsyncAction * *)

- ea: `0x1800088e0`
- end: `0x180008b47`
- name: `?RunIdleAsync@CDispatcher@Core@UI@Windows@@UEAAJPEAUIIdleDispatchedHandler@234@PEAPEAUIAsyncAction@Foundation@4@@Z`
- size: `615`
- prototype: `__int64 __fastcall(Windows::UI::Core::CDispatcher *__hidden this, struct Windows::UI::Core::IIdleDispatchedHandler *, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800038e0`
- `0x1800088e0`
- `0x180009260`
- `0x18000a490`
- `0x1800362e0`
- `0x18008aa80`
- `0x18008ac44`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008a0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008a0d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008ae1`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008ae1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Core::CDispatcher::RunIdleAsync(
        Windows::UI::Core::CDispatcher *this,
        struct Windows::UI::Core::IIdleDispatchedHandler *a2,
        struct Windows::Foundation::IAsyncAction **a3)
{
  int v6; // ebx
  struct Windows::Foundation::IAsyncAction *v7; // rbx
  __int64 (__fastcall *v8)(struct Windows::Foundation::IAsyncAction *, GUID *, struct Windows::Foundation::IAsyncAction **); // rdi
  struct Windows::Foundation::IAsyncAction *v9; // rcx
  struct Windows::Foundation::IAsyncAction *v10; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  unsigned int NextAsyncInfoId; // eax
  int v15; // r8d
  struct Windows::Foundation::IAsyncAction *v16; // rax
  const char *v17; // rax
  struct Windows::Foundation::IAsyncAction *v18; // [rsp+60h] [rbp+20h] BYREF
  struct Windows::Foundation::IAsyncAction *v19; // [rsp+70h] [rbp+30h] BYREF

  v19 = 0;
  *a3 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v19);
  v19 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_qDdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v13, this, *((_DWORD *)this + 30), -2, CurrentThreadId);
  }
  if ( *((_DWORD *)this + 47) )
  {
    v18 = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v18);
    NextAsyncInfoId = Windows::UI::Core::CDispatcher::GetNextAsyncInfoId(this);
    v6 = Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&unsigned short const near * const Windows::UI::Core::AsyncActionName,&unsigned short const near * const Windows::UI::Core::CoreAsyncActionName>>(
           NextAsyncInfoId,
           &v18);
    if ( v6 < 0
      || (v6 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IAsyncAction *))(*(_QWORD *)v18 + 80LL))(v18),
          v6 < 0) )
    {
      RoOriginateError((unsigned int)v6, 0);
    }
    else
    {
      (*(void (__fastcall **)(struct Windows::Foundation::IAsyncAction *, _QWORD, __int64))(*(_QWORD *)v18 + 48LL))(
        v18,
        0,
        3);
      (*(void (__fastcall **)(struct Windows::Foundation::IAsyncAction *, _QWORD))(*(_QWORD *)v18 + 64LL))(v18, 0);
      (*(void (__fastcall **)(struct Windows::Foundation::IAsyncAction *))(*(_QWORD *)v18 + 96LL))(v18);
      (*(void (__fastcall **)(struct Windows::Foundation::IAsyncAction *))(*(_QWORD *)v18 + 72LL))(v18);
      v16 = v18;
      v18 = 0;
      v19 = v16;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = "main view CoreWindow";
      if ( !*((_BYTE *)this + 212) )
        v17 = "secondary view or CoreInput";
      WPP_SF_qDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)"secondary view or CoreInput",
        v15,
        (_DWORD)this,
        *((_DWORD *)this + 30),
        (__int64)v17);
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v18);
  }
  else
  {
    v6 = Windows::UI::Core::CDispatcher::EnqueueAsyncWork(
           (__int64)this,
           (__int64 (__fastcall *)(__int64, __int64 *))Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&unsigned short const near * const Windows::UI::Core::AsyncActionName,&unsigned short const near * const Windows::UI::Core::CoreAsyncActionName>>,
           -2,
           0,
           a2,
           &v19);
  }
  if ( v6 >= 0 )
  {
    v18 = 0;
    v7 = v19;
    v8 = **(__int64 (__fastcall ***)(struct Windows::Foundation::IAsyncAction *, GUID *, struct Windows::Foundation::IAsyncAction **))v19;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v18);
    v6 = v8(v7, &GUID_5a648006_843a_4da9_865b_9d26e5dfad7b, &v18);
    if ( v6 < 0 )
    {
      v9 = v18;
    }
    else
    {
      v9 = 0;
      *a3 = v18;
    }
    if ( v9 )
    {
      v18 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::IAsyncAction *))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  v10 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(struct Windows::Foundation::IAsyncAction *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800088e0  mov     [rsp-18h+arg_8], rbx
0x1800088e5  mov     [rsp-18h+arg_18], rsi
0x1800088ea  push    rbp
0x1800088eb  push    rdi
0x1800088ec  push    r13
0x1800088ee  mov     rbp, rsp
0x1800088f1  sub     rsp, 40h
0x1800088f5  mov     rsi, r8
0x1800088f8  mov     rbx, rdx
0x1800088fb  mov     rdi, rcx
0x1800088fe  mov     [rbp+arg_10], 0
0x180008906  mov     qword ptr [r8], 0
0x18000890d  lea     rcx, [rbp+arg_10]
0x180008911  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180008916  mov     [rbp+arg_10], 0
0x18000891e  lea     r13, WPP_GLOBAL_Control
0x180008925  mov     rax, cs:WPP_GLOBAL_Control
0x18000892c  cmp     rax, r13
0x18000892f  jz      short loc_18000893B
0x180008931  test    byte ptr [rax+1Ch], 4
0x180008935  jnz     loc_180008A03
0x18000893b  cmp     dword ptr [rdi+0BCh], 0
0x180008942  jnz     loc_180008A43
0x180008948  lea     rax, [rbp+arg_10]
0x18000894c  mov     [rsp+40h+var_18], rax
0x180008951  mov     [rsp+40h+var_20], rbx
0x180008956  xor     r9d, r9d
0x180008959  lea     r8d, [r9-2]
0x18000895d  lea     rdx, ??$CoreAsyncInfo_CreateInstance@V?$CCoreAsyncBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?AsyncActionName@Core@UI@3@3QBGB$1?CoreAsyncActionName@673@3QBGB@Core@UI@Windows@@@Core@UI@Windows@@YAJIPEAPEAUICoreAsyncInfo@012@@Z; Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&ushort const near * const Windows::UI::Core::AsyncActionName,&ushort const near * const Windows::UI::Core::CoreAsyncActionName>>(uint,Windows::UI::Core::ICoreAsyncInfo * *)
0x180008964  mov     rcx, rdi
0x180008967  call    ?EnqueueAsyncWork@CDispatcher@Core@UI@Windows@@AEAAJP6AJIPEAPEAUICoreAsyncInfo@234@@ZW4CoreDispatcherPriority@234@PEAUIDispatchedHandler@234@PEAUIIdleDispatchedHandler@234@0@Z; Windows::UI::Core::CDispatcher::EnqueueAsyncWork(long (*)(uint,Windows::UI::Core::ICoreAsyncInfo * *),Windows::UI::Core::CoreDispatcherPriority,Windows::UI::Core::IDispatchedHandler *,Windows::UI::Core::IIdleDispatchedHandler *,Windows::UI::Core::ICoreAsyncInfo * *)
0x18000896c  mov     ebx, eax
0x18000896e  test    ebx, ebx
0x180008970  js      short loc_1800089D0
0x180008972  mov     [rbp+arg_0], 0
0x18000897a  mov     rbx, [rbp+arg_10]
0x18000897e  mov     rax, [rbx]
0x180008981  mov     rdi, [rax]
0x180008984  lea     rcx, [rbp+arg_0]
0x180008988  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000898d  lea     r8, [rbp+arg_0]
0x180008991  lea     rdx, _GUID_5a648006_843a_4da9_865b_9d26e5dfad7b
0x180008998  mov     rcx, rbx
0x18000899b  mov     rax, rdi
0x18000899e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089a3  mov     ebx, eax
0x1800089a5  test    eax, eax
0x1800089a7  js      loc_180008B3E
0x1800089ad  mov     rax, [rbp+arg_0]
0x1800089b1  xor     ecx, ecx
0x1800089b3  mov     [rsi], rax
0x1800089b6  test    rcx, rcx
0x1800089b9  jz      short loc_1800089D0
0x1800089bb  mov     [rbp+arg_0], 0
0x1800089c3  mov     rax, [rcx]
0x1800089c6  mov     rax, [rax+10h]
0x1800089ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089cf  nop
0x1800089d0  mov     rcx, [rbp+arg_10]
0x1800089d4  test    rcx, rcx
0x1800089d7  jz      short loc_1800089EE
0x1800089d9  mov     [rbp+arg_10], 0
0x1800089e1  mov     rdx, [rcx]
0x1800089e4  mov     rax, [rdx+10h]
0x1800089e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089ed  nop
0x1800089ee  mov     eax, ebx
0x1800089f0  mov     rbx, [rsp+40h+arg_8]
0x1800089f5  mov     rsi, [rsp+40h+arg_18]
0x1800089fa  add     rsp, 40h
0x1800089fe  pop     r13
0x180008a00  pop     rdi
0x180008a01  pop     rbp
0x180008a02  retn
0x180008a03  cmp     byte ptr [rax+19h], 4
0x180008a07  jb      loc_18000893B
0x180008a0d  call    cs:__imp_GetCurrentThreadId
0x180008a13  mov     edx, 13h
0x180008a18  mov     [rsp+40h+var_10], eax
0x180008a1c  mov     dword ptr [rsp+40h+var_18], 0FFFFFFFEh
0x180008a24  mov     eax, [rdi+78h]
0x180008a27  mov     dword ptr [rsp+40h+var_20], eax
0x180008a2b  mov     r9, rdi
0x180008a2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a35  mov     rcx, [rcx+10h]
0x180008a39  call    WPP_SF_qDdD
0x180008a3e  jmp     loc_18000893B
0x180008a43  mov     [rbp+arg_0], 0
0x180008a4b  lea     rcx, [rbp+arg_0]
0x180008a4f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180008a54  mov     rcx, rdi; this
0x180008a57  call    ?GetNextAsyncInfoId@CDispatcher@Core@UI@Windows@@AEAAIXZ; Windows::UI::Core::CDispatcher::GetNextAsyncInfoId(void)
0x180008a5c  lea     rdx, [rbp+arg_0]
0x180008a60  mov     ecx, eax
0x180008a62  call    ??$CoreAsyncInfo_CreateInstance@V?$CCoreAsyncBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?AsyncActionName@Core@UI@3@3QBGB$1?CoreAsyncActionName@673@3QBGB@Core@UI@Windows@@@Core@UI@Windows@@YAJIPEAPEAUICoreAsyncInfo@012@@Z; Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&ushort const near * const Windows::UI::Core::AsyncActionName,&ushort const near * const Windows::UI::Core::CoreAsyncActionName>>(uint,Windows::UI::Core::ICoreAsyncInfo * *)
0x180008a67  mov     ebx, eax
0x180008a69  test    eax, eax
0x180008a6b  js      short loc_180008ADD
0x180008a6d  mov     rcx, [rbp+arg_0]
0x180008a71  mov     rax, [rcx]
0x180008a74  mov     rax, [rax+50h]
0x180008a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a7d  mov     ebx, eax
0x180008a7f  test    eax, eax
0x180008a81  js      short loc_180008ADD
0x180008a83  mov     rcx, [rbp+arg_0]
0x180008a87  mov     rax, [rcx]
0x180008a8a  xor     edx, edx
0x180008a8c  lea     r8d, [rdx+3]
0x180008a90  mov     rax, [rax+30h]
0x180008a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a99  mov     rcx, [rbp+arg_0]
0x180008a9d  mov     rax, [rcx]
0x180008aa0  xor     edx, edx
0x180008aa2  mov     rax, [rax+40h]
0x180008aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aab  mov     rcx, [rbp+arg_0]
0x180008aaf  mov     rax, [rcx]
0x180008ab2  mov     rax, [rax+60h]
0x180008ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008abb  mov     rcx, [rbp+arg_0]
0x180008abf  mov     rax, [rcx]
0x180008ac2  mov     rax, [rax+48h]
0x180008ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008acb  mov     rax, [rbp+arg_0]
0x180008acf  mov     [rbp+arg_0], 0
0x180008ad7  mov     [rbp+arg_10], rax
0x180008adb  jmp     short loc_180008AE7
0x180008add  xor     edx, edx
0x180008adf  mov     ecx, ebx
0x180008ae1  call    cs:__imp_RoOriginateError
0x180008ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x180008aee  cmp     rcx, r13
0x180008af1  jz      short loc_180008B30
0x180008af3  test    byte ptr [rcx+1Ch], 4
0x180008af7  jz      short loc_180008B30
0x180008af9  cmp     byte ptr [rcx+19h], 2
0x180008afd  jb      short loc_180008B30
0x180008aff  lea     rdx, aSecondaryViewO; "secondary view or CoreInput"
0x180008b06  lea     rax, aMainViewCorewi; "main view CoreWindow"
0x180008b0d  cmp     byte ptr [rdi+0D4h], 0
0x180008b14  cmovz   rax, rdx
0x180008b18  mov     [rsp+40h+var_18], rax
0x180008b1d  mov     eax, [rdi+78h]
0x180008b20  mov     dword ptr [rsp+40h+var_20], eax
0x180008b24  mov     r9, rdi
0x180008b27  mov     rcx, [rcx+10h]
0x180008b2b  call    WPP_SF_qDs
0x180008b30  lea     rcx, [rbp+arg_0]
0x180008b34  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180008b39  jmp     loc_18000896E
0x180008b3e  mov     rcx, [rbp+arg_0]
0x180008b42  jmp     loc_1800089B6
```
