# Windows::UI::Internal::Popups::MessageDialogOperation::OperationCompleted(uchar)

- ea: `0x18005c4c4`
- end: `0x18005c628`
- name: `?OperationCompleted@MessageDialogOperation@Popups@Internal@UI@Windows@@AEAAJE@Z`
- size: `356`
- prototype: `__int64 __fastcall(Windows::UI::Internal::Popups::MessageDialogOperation *__hidden this, unsigned __int8)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180098e00`
- `0x180098e50`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x180016064`
- `0x180021ee0`
- `0x18005c4c4`
- `0x180097890`
- `0x180097efc`
- `0x180098430`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c580`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c580`
- `SHCORE!SHTaskPoolQueueTask` at `0x18005c59f`
- `SHCORE!SHTaskPoolQueueTask` at `0x18005c59f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Internal::Popups::MessageDialogOperation::OperationCompleted(
        Windows::UI::Internal::Popups::MessageDialogOperation *this,
        char a2)
{
  int v3; // eax
  int v4; // edi
  __int64 *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rsi
  Windows::UI::Internal::Popups::MessageDialogOperation *v8; // rcx
  DWORD CurrentThreadId; // eax
  int v11; // [rsp+20h] [rbp-30h]
  Windows::UI::Internal::Popups::MessageDialogOperation *v12; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v13[3]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  char v15; // [rsp+78h] [rbp+28h] BYREF
  __int64 v16; // [rsp+80h] [rbp+30h] BYREF
  Windows::UI::Internal::Popups::MessageDialogOperation *v17; // [rsp+88h] [rbp+38h] BYREF

  v15 = a2;
  v16 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v16);
  v3 = Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Internal::Popups::MessageDialogOperationCompletedEventArgs,Windows::Internal::PlatformExtensions::MessageDialogExperience::IMessageDialogOperationCompletedEventArgs,unsigned char &>(
         &v16,
         &v15);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v17 = this;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v17);
    v12 = this;
    v13[0] = this;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v13);
    v13[1] = v16;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_ba5ec37e4eafbe37e5c29fdfb36dfe03_____lambda_ba5ec37e4eafbe37e5c29fdfb36dfe03___(
                      &v17,
                      &v12);
    v7 = *v5;
    *v5 = 0;
    v8 = v17;
    if ( v17 )
    {
      v17 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler>::Release(
        v8,
        v6);
    }
    CurrentThreadId = GetCurrentThreadId();
    v4 = SHTaskPoolQueueTask(1, 0, CurrentThreadId, 0);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    lambda_49c3b37e74d4a362c1ebd3d7e21489d2_::__lambda_49c3b37e74d4a362c1ebd3d7e21489d2_(&v12);
    if ( v4 >= 0 )
    {
      if ( this )
        (*(void (__fastcall **)(Windows::UI::Internal::Popups::MessageDialogOperation *))(*(_QWORD *)this + 16LL))(this);
      v4 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\popup\\messagedialogoperation.cpp",
        (const char *)(unsigned int)v4,
        v7);
      if ( this )
        (*(void (__fastcall **)(Windows::UI::Internal::Popups::MessageDialogOperation *))(*(_QWORD *)this + 16LL))(this);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\popup\\messagedialogoperation.cpp",
      (const char *)(unsigned int)v3,
      v11);
  }
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v16);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005c4c4  mov     [rsp-18h+arg_0], rbx
0x18005c4c9  mov     [rsp-18h+arg_8], dl
0x18005c4cd  push    rbp
0x18005c4ce  push    rsi
0x18005c4cf  push    rdi
0x18005c4d0  mov     rbp, rsp
0x18005c4d3  sub     rsp, 50h
0x18005c4d7  mov     rbx, rcx
0x18005c4da  mov     [rbp+arg_10], 0
0x18005c4e2  lea     rcx, [rbp+arg_10]
0x18005c4e6  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005c4eb  lea     rdx, [rbp+arg_8]
0x18005c4ef  lea     rcx, [rbp+arg_10]
0x18005c4f3  call    ??$MakeAndInitialize@VMessageDialogOperationCompletedEventArgs@Popups@Internal@UI@Windows@@UIMessageDialogOperationCompletedEventArgs@MessageDialogExperience@PlatformExtensions@35@AEAE@Details@WRL@Microsoft@@YAJPEAPEAUIMessageDialogOperationCompletedEventArgs@MessageDialogExperience@PlatformExtensions@Internal@Windows@@AEAE@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Internal::Popups::MessageDialogOperationCompletedEventArgs,Windows::Internal::PlatformExtensions::MessageDialogExperience::IMessageDialogOperationCompletedEventArgs,uchar &>(Windows::Internal::PlatformExtensions::MessageDialogExperience::IMessageDialogOperationCompletedEventArgs * *,uchar &)
0x18005c4f8  mov     edi, eax
0x18005c4fa  test    eax, eax
0x18005c4fc  jns     short loc_18005C51B
0x18005c4fe  mov     rcx, [rbp+18h]; this
0x18005c502  mov     r9d, eax; char *
0x18005c505  lea     r8, aOnecoreuapWind_24; "onecoreuap\\windows\\advcore\\winrt\\po"...
0x18005c50c  mov     edx, 99h; void *
0x18005c511  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c516  jmp     loc_18005C610
0x18005c51b  mov     [rbp+arg_18], rbx
0x18005c51f  lea     rcx, [rbp+arg_18]
0x18005c523  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18005c528  mov     [rbp+var_20], rbx
0x18005c52c  mov     [rbp+var_18], rbx
0x18005c530  lea     rcx, [rbp+var_18]
0x18005c534  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18005c539  mov     rcx, [rbp+arg_10]
0x18005c53d  mov     [rbp+var_10], rcx
0x18005c541  test    rcx, rcx
0x18005c544  jz      short loc_18005C553
0x18005c546  mov     rax, [rcx]
0x18005c549  mov     rax, [rax+8]
0x18005c54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c552  nop
0x18005c553  lea     rdx, [rbp+var_20]
0x18005c557  lea     rcx, [rbp+arg_18]
0x18005c55b  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_ba5ec37e4eafbe37e5c29fdfb36dfe03_____lambda_ba5ec37e4eafbe37e5c29fdfb36dfe03___
0x18005c560  mov     rsi, [rax]
0x18005c563  mov     qword ptr [rax], 0
0x18005c56a  mov     rcx, [rbp+arg_18]
0x18005c56e  test    rcx, rcx
0x18005c571  jz      short loc_18005C580
0x18005c573  mov     [rbp+arg_18], 0
0x18005c57b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAsyncActionCompletedHandler@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler>::Release(void)
0x18005c580  call    cs:__imp_GetCurrentThreadId
0x18005c586  mov     [rsp+50h+var_28], 0
0x18005c58f  mov     qword ptr [rsp+50h+var_30], rsi; int
0x18005c594  xor     r9d, r9d
0x18005c597  mov     r8d, eax
0x18005c59a  xor     edx, edx
0x18005c59c  lea     ecx, [rdx+1]
0x18005c59f  call    cs:__imp_SHTaskPoolQueueTask
0x18005c5a5  mov     edi, eax
0x18005c5a7  test    rsi, rsi
0x18005c5aa  jz      short loc_18005C5BC
0x18005c5ac  mov     rdx, [rsi]
0x18005c5af  mov     rcx, rsi
0x18005c5b2  mov     rax, [rdx+10h]
0x18005c5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c5bb  nop
0x18005c5bc  lea     rcx, [rbp+var_20]
0x18005c5c0  call    _lambda_49c3b37e74d4a362c1ebd3d7e21489d2_____lambda_49c3b37e74d4a362c1ebd3d7e21489d2_
0x18005c5c5  test    edi, edi
0x18005c5c7  jns     short loc_18005C5F9
0x18005c5c9  mov     rcx, [rbp+18h]; this
0x18005c5cd  mov     r9d, edi; char *
0x18005c5d0  lea     r8, aOnecoreuapWind_24; "onecoreuap\\windows\\advcore\\winrt\\po"...
0x18005c5d7  mov     edx, 0A0h; void *
0x18005c5dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c5e1  nop
0x18005c5e2  test    rbx, rbx
0x18005c5e5  jz      short loc_18005C5F7
0x18005c5e7  mov     rax, [rbx]
0x18005c5ea  mov     rcx, rbx
0x18005c5ed  mov     rax, [rax+10h]
0x18005c5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c5f6  nop
0x18005c5f7  jmp     short loc_18005C610
0x18005c5f9  test    rbx, rbx
0x18005c5fc  jz      short loc_18005C60E
0x18005c5fe  mov     rax, [rbx]
0x18005c601  mov     rcx, rbx
0x18005c604  mov     rax, [rax+10h]
0x18005c608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c60d  nop
0x18005c60e  xor     edi, edi
0x18005c610  lea     rcx, [rbp+arg_10]
0x18005c614  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005c619  mov     eax, edi
0x18005c61b  mov     rbx, [rsp+50h+arg_0]
0x18005c620  add     rsp, 50h
0x18005c624  pop     rdi
0x18005c625  pop     rsi
0x18005c626  pop     rbp
0x18005c627  retn
```
