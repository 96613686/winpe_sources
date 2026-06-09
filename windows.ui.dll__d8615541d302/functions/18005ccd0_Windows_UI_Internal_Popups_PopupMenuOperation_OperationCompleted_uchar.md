# Windows::UI::Internal::Popups::PopupMenuOperation::OperationCompleted(uchar)

- ea: `0x18005ccd0`
- end: `0x18005ce34`
- name: `?OperationCompleted@PopupMenuOperation@Popups@Internal@UI@Windows@@AEAAJE@Z`
- size: `356`
- prototype: `__int64 __fastcall(Windows::UI::Internal::Popups::PopupMenuOperation *__hidden this, unsigned __int8)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a3e20`
- `0x1800a3e60`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x180016064`
- `0x180021ee0`
- `0x18005ccd0`
- `0x180098430`
- `0x1800a3a34`
- `0x1800a3bfc`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cd8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cd8c`
- `SHCORE!SHTaskPoolQueueTask` at `0x18005cdab`
- `SHCORE!SHTaskPoolQueueTask` at `0x18005cdab`

## pseudocode

```c
__int64 __fastcall Windows::UI::Internal::Popups::PopupMenuOperation::OperationCompleted(
        Windows::UI::Internal::Popups::PopupMenuOperation *this)
{
  int v2; // eax
  int v3; // edi
  __int64 *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rsi
  Windows::UI::Internal::Popups::PopupMenuOperation *v7; // rcx
  DWORD CurrentThreadId; // eax
  int v10; // [rsp+20h] [rbp-30h]
  Windows::UI::Internal::Popups::PopupMenuOperation *v11; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v12[3]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  void *v14; // [rsp+80h] [rbp+30h] BYREF
  Windows::UI::Internal::Popups::PopupMenuOperation *v15; // [rsp+88h] [rbp+38h] BYREF

  v14 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v14);
  v2 = Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Internal::Popups::PopupMenuOperationCompletedEventArgs,Windows::Internal::PlatformExtensions::PopupMenuExperience::IPopupMenuOperationCompletedEventArgs,unsigned char &>(&v14);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v15 = this;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v15);
    v11 = this;
    v12[0] = this;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v12);
    v12[1] = v14;
    if ( v14 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 8LL))(v14);
    v4 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_49c3b37e74d4a362c1ebd3d7e21489d2_____lambda_49c3b37e74d4a362c1ebd3d7e21489d2___(
                      &v15,
                      &v11);
    v6 = *v4;
    *v4 = 0;
    v7 = v15;
    if ( v15 )
    {
      v15 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler>::Release(
        v7,
        v5);
    }
    CurrentThreadId = GetCurrentThreadId();
    v3 = SHTaskPoolQueueTask(1, 0, CurrentThreadId, 0);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    lambda_49c3b37e74d4a362c1ebd3d7e21489d2_::__lambda_49c3b37e74d4a362c1ebd3d7e21489d2_(&v11);
    if ( v3 >= 0 )
    {
      if ( this )
        (*(void (__fastcall **)(Windows::UI::Internal::Popups::PopupMenuOperation *))(*(_QWORD *)this + 16LL))(this);
      v3 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\popupmenu\\popupmenuoperation.cpp",
        (const char *)(unsigned int)v3,
        v6);
      if ( this )
        (*(void (__fastcall **)(Windows::UI::Internal::Popups::PopupMenuOperation *))(*(_QWORD *)this + 16LL))(this);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\popupmenu\\popupmenuoperation.cpp",
      (const char *)(unsigned int)v2,
      v10);
  }
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18005ccd0  mov     [rsp-18h+arg_0], rbx
0x18005ccd5  mov     [rsp-18h+arg_8], dl
0x18005ccd9  push    rbp
0x18005ccda  push    rsi
0x18005ccdb  push    rdi
0x18005ccdc  mov     rbp, rsp
0x18005ccdf  sub     rsp, 50h
0x18005cce3  mov     rbx, rcx
0x18005cce6  mov     [rbp+arg_10], 0
0x18005ccee  lea     rcx, [rbp+arg_10]
0x18005ccf2  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005ccf7  lea     rdx, [rbp+arg_8]
0x18005ccfb  lea     rcx, [rbp+arg_10]; void **
0x18005ccff  call    ??$MakeAndInitialize@VPopupMenuOperationCompletedEventArgs@Popups@Internal@UI@Windows@@UIPopupMenuOperationCompletedEventArgs@PopupMenuExperience@PlatformExtensions@35@AEAE@Details@WRL@Microsoft@@YAJPEAPEAUIPopupMenuOperationCompletedEventArgs@PopupMenuExperience@PlatformExtensions@Internal@Windows@@AEAE@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Internal::Popups::PopupMenuOperationCompletedEventArgs,Windows::Internal::PlatformExtensions::PopupMenuExperience::IPopupMenuOperationCompletedEventArgs,uchar &>(Windows::Internal::PlatformExtensions::PopupMenuExperience::IPopupMenuOperationCompletedEventArgs * *,uchar &)
0x18005cd04  mov     edi, eax
0x18005cd06  test    eax, eax
0x18005cd08  jns     short loc_18005CD27
0x18005cd0a  mov     rcx, [rbp+18h]; this
0x18005cd0e  mov     r9d, eax; char *
0x18005cd11  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\advcore\\winrt\\po"...
0x18005cd18  mov     edx, 66h ; 'f'; void *
0x18005cd1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cd22  jmp     loc_18005CE1C
0x18005cd27  mov     [rbp+arg_18], rbx
0x18005cd2b  lea     rcx, [rbp+arg_18]
0x18005cd2f  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18005cd34  mov     [rbp+var_20], rbx
0x18005cd38  mov     [rbp+var_18], rbx
0x18005cd3c  lea     rcx, [rbp+var_18]
0x18005cd40  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18005cd45  mov     rcx, [rbp+arg_10]
0x18005cd49  mov     [rbp+var_10], rcx
0x18005cd4d  test    rcx, rcx
0x18005cd50  jz      short loc_18005CD5F
0x18005cd52  mov     rax, [rcx]
0x18005cd55  mov     rax, [rax+8]
0x18005cd59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd5e  nop
0x18005cd5f  lea     rdx, [rbp+var_20]
0x18005cd63  lea     rcx, [rbp+arg_18]
0x18005cd67  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_49c3b37e74d4a362c1ebd3d7e21489d2_____lambda_49c3b37e74d4a362c1ebd3d7e21489d2___
0x18005cd6c  mov     rsi, [rax]
0x18005cd6f  mov     qword ptr [rax], 0
0x18005cd76  mov     rcx, [rbp+arg_18]
0x18005cd7a  test    rcx, rcx
0x18005cd7d  jz      short loc_18005CD8C
0x18005cd7f  mov     [rbp+arg_18], 0
0x18005cd87  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAsyncActionCompletedHandler@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler>::Release(void)
0x18005cd8c  call    cs:__imp_GetCurrentThreadId
0x18005cd92  mov     [rsp+50h+var_28], 0
0x18005cd9b  mov     qword ptr [rsp+50h+var_30], rsi; int
0x18005cda0  xor     r9d, r9d
0x18005cda3  mov     r8d, eax
0x18005cda6  xor     edx, edx
0x18005cda8  lea     ecx, [rdx+1]
0x18005cdab  call    cs:__imp_SHTaskPoolQueueTask
0x18005cdb1  mov     edi, eax
0x18005cdb3  test    rsi, rsi
0x18005cdb6  jz      short loc_18005CDC8
0x18005cdb8  mov     rdx, [rsi]
0x18005cdbb  mov     rcx, rsi
0x18005cdbe  mov     rax, [rdx+10h]
0x18005cdc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cdc7  nop
0x18005cdc8  lea     rcx, [rbp+var_20]
0x18005cdcc  call    _lambda_49c3b37e74d4a362c1ebd3d7e21489d2_____lambda_49c3b37e74d4a362c1ebd3d7e21489d2_
0x18005cdd1  test    edi, edi
0x18005cdd3  jns     short loc_18005CE05
0x18005cdd5  mov     rcx, [rbp+18h]; this
0x18005cdd9  mov     r9d, edi; char *
0x18005cddc  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\advcore\\winrt\\po"...
0x18005cde3  mov     edx, 6Dh ; 'm'; void *
0x18005cde8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cded  nop
0x18005cdee  test    rbx, rbx
0x18005cdf1  jz      short loc_18005CE03
0x18005cdf3  mov     rax, [rbx]
0x18005cdf6  mov     rcx, rbx
0x18005cdf9  mov     rax, [rax+10h]
0x18005cdfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce02  nop
0x18005ce03  jmp     short loc_18005CE1C
0x18005ce05  test    rbx, rbx
0x18005ce08  jz      short loc_18005CE1A
0x18005ce0a  mov     rax, [rbx]
0x18005ce0d  mov     rcx, rbx
0x18005ce10  mov     rax, [rax+10h]
0x18005ce14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce19  nop
0x18005ce1a  xor     edi, edi
0x18005ce1c  lea     rcx, [rbp+arg_10]
0x18005ce20  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005ce25  mov     eax, edi
0x18005ce27  mov     rbx, [rsp+50h+arg_0]
0x18005ce2c  add     rsp, 50h
0x18005ce30  pop     rdi
0x18005ce31  pop     rsi
0x18005ce32  pop     rbp
0x18005ce33  retn
```
