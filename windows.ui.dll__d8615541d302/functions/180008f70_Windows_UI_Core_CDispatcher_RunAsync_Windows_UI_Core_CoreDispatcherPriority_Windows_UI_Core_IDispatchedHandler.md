# Windows::UI::Core::CDispatcher::RunAsync(Windows::UI::Core::CoreDispatcherPriority,Windows::UI::Core::IDispatchedHandler *,Windows::Foundation::IAsyncAction * *)

- ea: `0x180008f70`
- end: `0x180009251`
- name: `?RunAsync@CDispatcher@Core@UI@Windows@@UEAAJW4CoreDispatcherPriority@234@PEAUIDispatchedHandler@234@PEAPEAUIAsyncAction@Foundation@4@@Z`
- size: `737`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180008f70`
- `0x180009260`
- `0x18000a490`
- `0x1800362e0`
- `0x180071c60`
- `0x18008aa80`
- `0x18008ac44`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800090e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800090e3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800091ad`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800091ad`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180008fcd`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180008fcd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Core::CDispatcher::RunAsync(__int64 a1, int a2, _QWORD *a3, _QWORD *a4)
{
  int v9; // ebx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, _QWORD); // rsi
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rcx
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  unsigned int NextAsyncInfoId; // eax
  int v17; // r8d
  __int64 (__fastcall ***v18)(_QWORD, GUID *, _QWORD); // rax
  const char *v19; // rax
  int v20; // [rsp+28h] [rbp-48h]
  __int64 (__fastcall ***v21)(_QWORD, GUID *, _QWORD); // [rsp+40h] [rbp-30h] BYREF
  __int64 (__fastcall ***v22)(_QWORD, GUID *, _QWORD); // [rsp+48h] [rbp-28h] BYREF
  __int128 v23; // [rsp+50h] [rbp-20h] BYREF
  wchar_t v24; // [rsp+60h] [rbp-10h]

  *a4 = 0;
  if ( (unsigned int)(a2 + 1) <= 2 )
  {
    v22 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_qDdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v15, a1, *(_DWORD *)(a1 + 120), a2, CurrentThreadId);
    }
    if ( *(_DWORD *)(a1 + 188) )
    {
      v21 = 0;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
      NextAsyncInfoId = Windows::UI::Core::CDispatcher::GetNextAsyncInfoId((Windows::UI::Core::CDispatcher *)a1);
      v9 = Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&unsigned short const near * const Windows::UI::Core::AsyncActionName,&unsigned short const near * const Windows::UI::Core::CoreAsyncActionName>>(
             NextAsyncInfoId,
             &v21);
      if ( v9 < 0
        || (v9 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v21)[10])(v21), v9 < 0) )
      {
        RoOriginateError((unsigned int)v9, 0);
      }
      else
      {
        (*v21)[6](v21, 0, 3);
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD), _QWORD))(*v21)[8])(v21, 0);
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v21)[12])(v21);
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v21)[9])(v21);
        v18 = v21;
        v21 = 0;
        v22 = v18;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = "main view CoreWindow";
        if ( !*(_BYTE *)(a1 + 212) )
          v19 = "secondary view or CoreInput";
        WPP_SF_qDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)"secondary view or CoreInput",
          v17,
          a1,
          *(_DWORD *)(a1 + 120),
          (__int64)v19);
      }
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
    }
    else
    {
      v9 = Windows::UI::Core::CDispatcher::EnqueueAsyncWork(
             a1,
             (__int64 (__fastcall *)(__int64, __int64 *))Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&unsigned short const near * const Windows::UI::Core::AsyncActionName,&unsigned short const near * const Windows::UI::Core::CoreAsyncActionName>>,
             a2,
             a3,
             0,
             &v22);
    }
    if ( v9 >= 0 )
    {
      v21 = 0;
      v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v22;
      v11 = **v22;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
      v9 = v11(v10, &GUID_5a648006_843a_4da9_865b_9d26e5dfad7b, &v21);
      if ( v9 < 0 )
      {
        v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v21;
      }
      else
      {
        v12 = 0;
        *a4 = v21;
      }
      if ( v12 )
      {
        v21 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v12)[2])(v12);
      }
    }
    v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v22;
    if ( v22 )
    {
      v22 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v13)[2])(v13);
    }
    return (unsigned int)v9;
  }
  else
  {
    v23 = *(_OWORD *)L"priority";
    v24 = aPriority[8];
    RoOriginateErrorW(2147942487LL, 8, &v23);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = a2;
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids,
        a1,
        *(_DWORD *)(a1 + 120),
        v20);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180008f70  push    rbp
0x180008f72  push    rbx
0x180008f73  push    rsi
0x180008f74  push    rdi
0x180008f75  push    r12
0x180008f77  push    r14
0x180008f79  push    r15
0x180008f7b  mov     rbp, rsp
0x180008f7e  sub     rsp, 70h
0x180008f82  mov     rax, cs:__security_cookie
0x180008f89  xor     rax, rsp
0x180008f8c  mov     [rbp+var_8], rax
0x180008f90  mov     rdi, r9
0x180008f93  mov     r14, r8
0x180008f96  mov     ebx, edx
0x180008f98  mov     rsi, rcx
0x180008f9b  xor     r12d, r12d
0x180008f9e  mov     [r9], r12
0x180008fa1  lea     eax, [rdx+1]
0x180008fa4  cmp     eax, 2
0x180008fa7  jbe     short loc_18000900A
0x180008fa9  movups  xmm0, xmmword ptr cs:aPriority; "priority"
0x180008fb0  movups  [rbp+var_20], xmm0
0x180008fb4  movzx   eax, word ptr cs:aPriority+10h; ""
0x180008fbb  mov     [rbp+var_10], ax
0x180008fbf  lea     r8, [rbp+var_20]
0x180008fc3  mov     edx, 8
0x180008fc8  mov     ecx, 80070057h
0x180008fcd  call    cs:__imp_RoOriginateErrorW
0x180008fd3  lea     r15, WPP_GLOBAL_Control
0x180008fda  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fe1  cmp     rcx, r15
0x180008fe4  jnz     loc_180009213
0x180008fea  mov     eax, 80070057h
0x180008fef  mov     rcx, [rbp+var_8]
0x180008ff3  xor     rcx, rsp; StackCookie
0x180008ff6  call    __security_check_cookie
0x180008ffb  add     rsp, 70h
0x180008fff  pop     r15
0x180009001  pop     r14
0x180009003  pop     r12
0x180009005  pop     rdi
0x180009006  pop     rsi
0x180009007  pop     rbx
0x180009008  pop     rbp
0x180009009  retn
0x18000900a  mov     [rbp+var_28], r12
0x18000900e  lea     r15, WPP_GLOBAL_Control
0x180009015  mov     rax, cs:WPP_GLOBAL_Control
0x18000901c  cmp     rax, r15
0x18000901f  jz      short loc_18000902B
0x180009021  test    byte ptr [rax+1Ch], 4
0x180009025  jnz     loc_1800090D9
0x18000902b  cmp     dword ptr [rsi+0BCh], 0
0x180009032  jnz     loc_180009115
0x180009038  lea     rax, [rbp+var_28]
0x18000903c  mov     [rsp+70h+var_48], rax
0x180009041  mov     [rsp+70h+var_50], r12
0x180009046  mov     r9, r14
0x180009049  mov     r8d, ebx
0x18000904c  lea     rdx, ??$CoreAsyncInfo_CreateInstance@V?$CCoreAsyncBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?AsyncActionName@Core@UI@3@3QBGB$1?CoreAsyncActionName@673@3QBGB@Core@UI@Windows@@@Core@UI@Windows@@YAJIPEAPEAUICoreAsyncInfo@012@@Z; Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&ushort const near * const Windows::UI::Core::AsyncActionName,&ushort const near * const Windows::UI::Core::CoreAsyncActionName>>(uint,Windows::UI::Core::ICoreAsyncInfo * *)
0x180009053  mov     rcx, rsi
0x180009056  call    ?EnqueueAsyncWork@CDispatcher@Core@UI@Windows@@AEAAJP6AJIPEAPEAUICoreAsyncInfo@234@@ZW4CoreDispatcherPriority@234@PEAUIDispatchedHandler@234@PEAUIIdleDispatchedHandler@234@0@Z; Windows::UI::Core::CDispatcher::EnqueueAsyncWork(long (*)(uint,Windows::UI::Core::ICoreAsyncInfo * *),Windows::UI::Core::CoreDispatcherPriority,Windows::UI::Core::IDispatchedHandler *,Windows::UI::Core::IIdleDispatchedHandler *,Windows::UI::Core::ICoreAsyncInfo * *)
0x18000905b  mov     ebx, eax
0x18000905d  test    ebx, ebx
0x18000905f  js      short loc_1800090B8
0x180009061  mov     [rbp+var_30], r12
0x180009065  mov     rbx, [rbp+var_28]
0x180009069  mov     rax, [rbx]
0x18000906c  mov     rsi, [rax]
0x18000906f  lea     rcx, [rbp+var_30]
0x180009073  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180009078  lea     r8, [rbp+var_30]
0x18000907c  lea     rdx, _GUID_5a648006_843a_4da9_865b_9d26e5dfad7b
0x180009083  mov     rcx, rbx
0x180009086  mov     rax, rsi
0x180009089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000908e  mov     ebx, eax
0x180009090  test    eax, eax
0x180009092  js      loc_18000920A
0x180009098  mov     rax, [rbp+var_30]
0x18000909c  mov     rcx, r12
0x18000909f  mov     [rdi], rax
0x1800090a2  test    rcx, rcx
0x1800090a5  jz      short loc_1800090B8
0x1800090a7  mov     [rbp+var_30], r12
0x1800090ab  mov     rax, [rcx]
0x1800090ae  mov     rax, [rax+10h]
0x1800090b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090b7  nop
0x1800090b8  mov     rcx, [rbp+var_28]
0x1800090bc  test    rcx, rcx
0x1800090bf  jz      short loc_1800090D2
0x1800090c1  mov     [rbp+var_28], r12
0x1800090c5  mov     rdx, [rcx]
0x1800090c8  mov     rax, [rdx+10h]
0x1800090cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090d1  nop
0x1800090d2  mov     eax, ebx
0x1800090d4  jmp     loc_180008FEF
0x1800090d9  cmp     byte ptr [rax+19h], 4
0x1800090dd  jb      loc_18000902B
0x1800090e3  call    cs:__imp_GetCurrentThreadId
0x1800090e9  mov     edx, 13h
0x1800090ee  mov     [rsp+70h+var_40], eax
0x1800090f2  mov     dword ptr [rsp+70h+var_48], ebx
0x1800090f6  mov     eax, [rsi+78h]
0x1800090f9  mov     dword ptr [rsp+70h+var_50], eax
0x1800090fd  mov     r9, rsi
0x180009100  mov     rcx, cs:WPP_GLOBAL_Control
0x180009107  mov     rcx, [rcx+10h]
0x18000910b  call    WPP_SF_qDdD
0x180009110  jmp     loc_18000902B
0x180009115  mov     [rbp+var_30], r12
0x180009119  lea     rcx, [rbp+var_30]
0x18000911d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180009122  mov     rcx, rsi; this
0x180009125  call    ?GetNextAsyncInfoId@CDispatcher@Core@UI@Windows@@AEAAIXZ; Windows::UI::Core::CDispatcher::GetNextAsyncInfoId(void)
0x18000912a  lea     rdx, [rbp+var_30]
0x18000912e  mov     ecx, eax
0x180009130  call    ??$CoreAsyncInfo_CreateInstance@V?$CCoreAsyncBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?AsyncActionName@Core@UI@3@3QBGB$1?CoreAsyncActionName@673@3QBGB@Core@UI@Windows@@@Core@UI@Windows@@YAJIPEAPEAUICoreAsyncInfo@012@@Z; Windows::UI::Core::CoreAsyncInfo_CreateInstance<Windows::UI::Core::CCoreAsyncBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&ushort const near * const Windows::UI::Core::AsyncActionName,&ushort const near * const Windows::UI::Core::CoreAsyncActionName>>(uint,Windows::UI::Core::ICoreAsyncInfo * *)
0x180009135  mov     ebx, eax
0x180009137  test    eax, eax
0x180009139  js      short loc_1800091A9
0x18000913b  mov     rcx, [rbp+var_30]
0x18000913f  mov     rax, [rcx]
0x180009142  mov     rax, [rax+50h]
0x180009146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000914b  mov     ebx, eax
0x18000914d  test    eax, eax
0x18000914f  js      short loc_1800091A9
0x180009151  mov     rcx, [rbp+var_30]
0x180009155  mov     rax, [rcx]
0x180009158  xor     edx, edx
0x18000915a  mov     r8d, 3
0x180009160  mov     rax, [rax+30h]
0x180009164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009169  mov     rcx, [rbp+var_30]
0x18000916d  mov     rax, [rcx]
0x180009170  xor     edx, edx
0x180009172  mov     rax, [rax+40h]
0x180009176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000917b  mov     rcx, [rbp+var_30]
0x18000917f  mov     rax, [rcx]
0x180009182  mov     rax, [rax+60h]
0x180009186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000918b  mov     rcx, [rbp+var_30]
0x18000918f  mov     rax, [rcx]
0x180009192  mov     rax, [rax+48h]
0x180009196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000919b  mov     rax, [rbp+var_30]
0x18000919f  mov     [rbp+var_30], r12
0x1800091a3  mov     [rbp+var_28], rax
0x1800091a7  jmp     short loc_1800091B3
0x1800091a9  xor     edx, edx
0x1800091ab  mov     ecx, ebx
0x1800091ad  call    cs:__imp_RoOriginateError
0x1800091b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091ba  cmp     rcx, r15
0x1800091bd  jz      short loc_1800091FC
0x1800091bf  test    byte ptr [rcx+1Ch], 4
0x1800091c3  jz      short loc_1800091FC
0x1800091c5  cmp     byte ptr [rcx+19h], 2
0x1800091c9  jb      short loc_1800091FC
0x1800091cb  lea     rdx, aSecondaryViewO; "secondary view or CoreInput"
0x1800091d2  lea     rax, aMainViewCorewi; "main view CoreWindow"
0x1800091d9  cmp     byte ptr [rsi+0D4h], 0
0x1800091e0  cmovz   rax, rdx
0x1800091e4  mov     [rsp+70h+var_48], rax
0x1800091e9  mov     eax, [rsi+78h]
0x1800091ec  mov     dword ptr [rsp+70h+var_50], eax
0x1800091f0  mov     r9, rsi
0x1800091f3  mov     rcx, [rcx+10h]
0x1800091f7  call    WPP_SF_qDs
0x1800091fc  lea     rcx, [rbp+var_30]
0x180009200  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180009205  jmp     loc_18000905D
0x18000920a  mov     rcx, [rbp+var_30]
0x18000920e  jmp     loc_1800090A2
0x180009213  test    byte ptr [rcx+1Ch], 4
0x180009217  jz      loc_180008FEA
0x18000921d  cmp     byte ptr [rcx+19h], 2
0x180009221  jb      loc_180008FEA
0x180009227  mov     edx, 11h
0x18000922c  mov     dword ptr [rsp+70h+var_48], ebx
0x180009230  mov     r8d, [rsi+78h]
0x180009234  mov     dword ptr [rsp+70h+var_50], r8d
0x180009239  mov     r9, rsi
0x18000923c  lea     r8, WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids
0x180009243  mov     rcx, [rcx+10h]
0x180009247  call    WPP_SF_qDD
0x18000924c  jmp     loc_180008FEA
```
