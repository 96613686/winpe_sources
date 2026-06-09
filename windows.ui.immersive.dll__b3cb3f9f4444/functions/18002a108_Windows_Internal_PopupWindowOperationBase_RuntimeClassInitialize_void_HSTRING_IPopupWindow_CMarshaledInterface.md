# Windows::Internal::PopupWindowOperationBase::RuntimeClassInitialize(void *,HSTRING__ *,IPopupWindow *,CMarshaledInterface,uint,uint,uint,CMarshaledInterface,bool)

- ea: `0x18002a108`
- end: `0x18002a365`
- name: `?RuntimeClassInitialize@PopupWindowOperationBase@Internal@Windows@@QEAAJPEAXPEAUHSTRING__@@PEAUIPopupWindow@@VCMarshaledInterface@@III3_N@Z`
- size: `605`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003e794`
- `0x18004f404`

## callees

- `0x180013f14`
- `0x18002a108`
- `0x18002a36c`
- `0x18003ae60`
- `0x18003d244`
- `0x180041e3c`
- `0x18004933c`
- `0x1800884e0`
- `0x18008c954`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002a241`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002a241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002a167`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002a167`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a18d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a18d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002a278`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002a278`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::PopupWindowOperationBase::RuntimeClassInitialize(
        __int64 a1,
        __int64 a2,
        HSTRING a3,
        HSTRING a4,
        __int64 a5,
        int a6,
        unsigned int a7,
        unsigned int a8,
        CMarshaledInterface *a9,
        bool a10)
{
  HRESULT v13; // ebx
  CMarshaledInterface *v14; // r14
  HSTRING v15; // rcx
  HANDLE Event; // rbx
  int Error; // eax
  __int64 (__fastcall *v19)(); // [rsp+20h] [rbp-10h] BYREF
  int v20; // [rsp+28h] [rbp-8h]
  HSTRING newString; // [rsp+50h] [rbp+20h] BYREF
  __int64 v22; // [rsp+58h] [rbp+28h] BYREF

  *(_QWORD *)(a1 + 88) = a2;
  if ( *(HSTRING *)(a1 + 32) != a4 )
  {
    newString = a4;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&newString, a2, a3);
    newString = *(HSTRING *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = a4;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&newString);
  }
  *(_DWORD *)(a1 + 76) = a6;
  newString = 0;
  v13 = WindowsDuplicateString(a3, &newString);
  v14 = a9;
  if ( v13 >= 0 )
  {
    v15 = *(HSTRING *)(a1 + 40);
    *(_QWORD *)(a1 + 40) = newString;
    WindowsDeleteString(v15);
    v13 = CMarshaledInterface::Unmarshal<Windows::Foundation::Collections::IVector<Windows::UI::Popups::IUICommand *>>(
            a5,
            a1 + 56);
    if ( v13 >= 0 )
    {
      if ( !*(_QWORD *)v14
        || (Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(a1 + 64),
            v13 = CMarshaledInterface::_Unmarshal(
                    v14,
                    &GUID_daf77a4f_c27a_4298_9ac6_2922c45e7da6,
                    (void **)(a1 + 64),
                    0),
            v13 >= 0) )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 32) + 120LL))(*(_QWORD *)(a1 + 32), a8);
        if ( v13 >= 0 )
        {
          v13 = Windows::Internal::PopupWindowOperationBase::_AdjustButtons(
                  (Windows::Internal::PopupWindowOperationBase *)a1,
                  *(struct IPopupWindow **)(a1 + 32),
                  a10);
          if ( v13 >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 32) + 88LL))(*(_QWORD *)(a1 + 32), a7);
            if ( v13 >= 0 )
            {
              Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
              CAutoHandle<void *>::~CAutoHandle<void *>(a1 + 80);
              *(_QWORD *)(a1 + 80) = Event;
              if ( (((unsigned __int64)Event + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
                || (Error = ResultFromKnownLastError(), v13 = Error, Error >= 0) )
              {
                v19 =  Windows::Internal::PopupWindowOperationBase::`vcall'{24,{flat}};
                v20 = 0;
                Microsoft::WRL::Callback<IPopupEventHandler,Windows::Internal::PopupWindowOperationBase,IPopupWindow *>(
                  &v22,
                  a1,
                  &v19);
                if ( v22 )
                {
                  v13 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 168LL))(*(_QWORD *)(a1 + 32));
                  if ( v13 >= 0 )
                  {
                    v19 =  Windows::Internal::PopupWindowOperationBase::`vcall'{32,{flat}};
                    v20 = 0;
                    Microsoft::WRL::Callback<IPopupEventHandler,Windows::Internal::PopupWindowOperationBase,IPopupWindow *>(
                      &newString,
                      a1,
                      &v19);
                    if ( newString )
                      v13 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 320LL))(*(_QWORD *)(a1 + 32));
                    else
                      v13 = -2147024882;
                    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&newString);
                  }
                }
                else
                {
                  v13 = -2147024882;
                }
                Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v22);
              }
              else
              {
                RoOriginateError((unsigned int)Error, 0);
              }
            }
          }
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(a5);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v14);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002a108  mov     [rsp-18h+arg_10], rbx
0x18002a10d  mov     [rsp-18h+arg_18], rsi
0x18002a112  push    rbp
0x18002a113  push    rdi
0x18002a114  push    r14
0x18002a116  mov     rbp, rsp
0x18002a119  sub     rsp, 30h
0x18002a11d  mov     rbx, r9
0x18002a120  mov     rdi, r8
0x18002a123  mov     rsi, rcx
0x18002a126  mov     [rcx+58h], rdx
0x18002a12a  cmp     [rcx+20h], r9
0x18002a12e  jz      short loc_18002A152
0x18002a130  mov     [rbp+newString], rbx
0x18002a134  lea     rcx, [rbp+newString]
0x18002a138  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002a13d  mov     rax, [rsi+20h]
0x18002a141  mov     [rbp+newString], rax
0x18002a145  mov     [rsi+20h], rbx
0x18002a149  lea     rcx, [rbp+newString]
0x18002a14d  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18002a152  mov     eax, [rbp+arg_28]
0x18002a155  mov     [rsi+4Ch], eax
0x18002a158  mov     [rbp+newString], 0
0x18002a160  lea     rdx, [rbp+newString]; newString
0x18002a164  mov     rcx, rdi; string
0x18002a167  call    cs:__imp_WindowsDuplicateString
0x18002a16e  nop     dword ptr [rax+rax+00h]
0x18002a173  mov     ebx, eax
0x18002a175  mov     r14, [rbp+arg_40]
0x18002a179  test    eax, eax
0x18002a17b  js      loc_18002A33D
0x18002a181  mov     rcx, [rsi+28h]; string
0x18002a185  mov     rax, [rbp+newString]
0x18002a189  mov     [rsi+28h], rax
0x18002a18d  call    cs:__imp_WindowsDeleteString
0x18002a194  nop     dword ptr [rax+rax+00h]
0x18002a199  lea     rdx, [rsi+38h]
0x18002a19d  mov     rcx, [rbp+arg_20]
0x18002a1a1  call    ??$Unmarshal@U?$IVector@PEAUIUICommand@Popups@UI@Windows@@@Collections@Foundation@Windows@@@CMarshaledInterface@@QEAAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIUICommand@Popups@UI@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; CMarshaledInterface::Unmarshal<Windows::Foundation::Collections::IVector<Windows::UI::Popups::IUICommand *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::UI::Popups::IUICommand *>>>)
0x18002a1a6  mov     ebx, eax
0x18002a1a8  test    eax, eax
0x18002a1aa  js      loc_18002A33D
0x18002a1b0  cmp     qword ptr [r14], 0
0x18002a1b4  jz      short loc_18002A1DF
0x18002a1b6  lea     rcx, [rsi+40h]
0x18002a1ba  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18002a1bf  xor     r9d, r9d; bool
0x18002a1c2  lea     r8, [rsi+40h]; void **
0x18002a1c6  lea     rdx, _GUID_daf77a4f_c27a_4298_9ac6_2922c45e7da6; struct _GUID *
0x18002a1cd  mov     rcx, r14; this
0x18002a1d0  call    ?_Unmarshal@CMarshaledInterface@@AEAAJAEBU_GUID@@PEAPEAX_N@Z; CMarshaledInterface::_Unmarshal(_GUID const &,void * *,bool)
0x18002a1d5  mov     ebx, eax
0x18002a1d7  test    eax, eax
0x18002a1d9  js      loc_18002A33D
0x18002a1df  mov     rcx, [rsi+20h]
0x18002a1e3  mov     rax, [rcx]
0x18002a1e6  mov     edx, [rbp+arg_38]
0x18002a1e9  mov     rax, [rax+78h]
0x18002a1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1f2  mov     ebx, eax
0x18002a1f4  test    eax, eax
0x18002a1f6  js      loc_18002A33D
0x18002a1fc  mov     r8b, [rbp+arg_48]; bool
0x18002a200  mov     rdx, [rsi+20h]; struct IPopupWindow *
0x18002a204  mov     rcx, rsi; this
0x18002a207  call    ?_AdjustButtons@PopupWindowOperationBase@Internal@Windows@@AEAAJPEAUIPopupWindow@@_N@Z; Windows::Internal::PopupWindowOperationBase::_AdjustButtons(IPopupWindow *,bool)
0x18002a20c  mov     ebx, eax
0x18002a20e  test    eax, eax
0x18002a210  js      loc_18002A33D
0x18002a216  mov     rcx, [rsi+20h]
0x18002a21a  mov     rax, [rcx]
0x18002a21d  mov     edx, [rbp+arg_30]
0x18002a220  mov     rax, [rax+58h]
0x18002a224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a229  mov     ebx, eax
0x18002a22b  test    eax, eax
0x18002a22d  js      loc_18002A33D
0x18002a233  xor     edx, edx; lpName
0x18002a235  xor     ecx, ecx; lpEventAttributes
0x18002a237  mov     r9d, 1F0003h; dwDesiredAccess
0x18002a23d  lea     r8d, [rdx+1]; dwFlags
0x18002a241  call    cs:__imp_CreateEventExW
0x18002a248  nop     dword ptr [rax+rax+00h]
0x18002a24d  mov     rbx, rax
0x18002a250  lea     rcx, [rsi+50h]
0x18002a254  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x18002a259  mov     [rsi+50h], rbx
0x18002a25d  lea     rax, [rbx+1]
0x18002a261  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a267  jnz     short loc_18002A289
0x18002a269  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002a26e  mov     ebx, eax
0x18002a270  test    eax, eax
0x18002a272  jns     short loc_18002A289
0x18002a274  xor     edx, edx
0x18002a276  mov     ecx, eax
0x18002a278  call    cs:__imp_RoOriginateError
0x18002a27f  nop     dword ptr [rax+rax+00h]
0x18002a284  jmp     loc_18002A33D
0x18002a289  lea     rax, ??_9PopupWindowOperationBase@Internal@Windows@@$BBI@AA; [thunk]: Windows::Internal::PopupWindowOperationBase::`vcall'{24,{flat}}
0x18002a290  mov     [rbp+var_10], rax
0x18002a294  mov     [rbp+var_8], 0
0x18002a29b  mov     eax, [rbp+var_4]
0x18002a29e  mov     [rbp+var_4], eax
0x18002a2a1  lea     r8, [rbp+var_10]
0x18002a2a5  mov     rdx, rsi
0x18002a2a8  lea     rcx, [rbp+arg_8]
0x18002a2ac  call    ??$Callback@UIPopupEventHandler@@VPopupWindowOperationBase@Internal@Windows@@PEAUIPopupWindow@@@WRL@Microsoft@@YA?AV?$ComPtr@UIPopupEventHandler@@@01@PEAVPopupWindowOperationBase@Internal@Windows@@P8345@EAAJPEAUIPopupWindow@@@Z@Z; Microsoft::WRL::Callback<IPopupEventHandler,Windows::Internal::PopupWindowOperationBase,IPopupWindow *>(Windows::Internal::PopupWindowOperationBase *,long (Windows::Internal::PopupWindowOperationBase::*)(IPopupWindow *))
0x18002a2b1  nop
0x18002a2b2  mov     rdx, [rbp+arg_8]
0x18002a2b6  test    rdx, rdx
0x18002a2b9  jnz     short loc_18002A2C2
0x18002a2bb  mov     ebx, 8007000Eh
0x18002a2c0  jmp     short loc_18002A333
0x18002a2c2  mov     rcx, [rsi+20h]
0x18002a2c6  mov     rax, [rcx]
0x18002a2c9  mov     rax, [rax+0A8h]
0x18002a2d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2d5  mov     ebx, eax
0x18002a2d7  test    eax, eax
0x18002a2d9  js      short loc_18002A333
0x18002a2db  lea     rax, ??_9PopupWindowOperationBase@Internal@Windows@@$BCA@AA; [thunk]: Windows::Internal::PopupWindowOperationBase::`vcall'{32,{flat}}
0x18002a2e2  mov     [rbp+var_10], rax
0x18002a2e6  mov     [rbp+var_8], 0
0x18002a2ed  mov     eax, [rbp+var_4]
0x18002a2f0  mov     [rbp+var_4], eax
0x18002a2f3  lea     r8, [rbp+var_10]
0x18002a2f7  mov     rdx, rsi
0x18002a2fa  lea     rcx, [rbp+newString]
0x18002a2fe  call    ??$Callback@UIPopupEventHandler@@VPopupWindowOperationBase@Internal@Windows@@PEAUIPopupWindow@@@WRL@Microsoft@@YA?AV?$ComPtr@UIPopupEventHandler@@@01@PEAVPopupWindowOperationBase@Internal@Windows@@P8345@EAAJPEAUIPopupWindow@@@Z@Z; Microsoft::WRL::Callback<IPopupEventHandler,Windows::Internal::PopupWindowOperationBase,IPopupWindow *>(Windows::Internal::PopupWindowOperationBase *,long (Windows::Internal::PopupWindowOperationBase::*)(IPopupWindow *))
0x18002a303  nop
0x18002a304  mov     rdx, [rbp+newString]
0x18002a308  test    rdx, rdx
0x18002a30b  jnz     short loc_18002A314
0x18002a30d  mov     ebx, 8007000Eh
0x18002a312  jmp     short loc_18002A329
0x18002a314  mov     rcx, [rsi+20h]
0x18002a318  mov     rax, [rcx]
0x18002a31b  mov     rax, [rax+140h]
0x18002a322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a327  mov     ebx, eax
0x18002a329  lea     rcx, [rbp+newString]
0x18002a32d  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18002a332  nop
0x18002a333  lea     rcx, [rbp+arg_8]
0x18002a337  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18002a33c  nop
0x18002a33d  mov     rcx, [rbp+arg_20]
0x18002a341  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18002a346  nop
0x18002a347  mov     rcx, r14
0x18002a34a  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18002a34f  mov     eax, ebx
0x18002a351  mov     rbx, [rsp+30h+arg_10]
0x18002a356  mov     rsi, [rsp+30h+arg_18]
0x18002a35b  add     rsp, 30h
0x18002a35f  pop     r14
0x18002a361  pop     rdi
0x18002a362  pop     rbp
0x18002a363  retn
```
