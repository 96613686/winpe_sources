# Windows::UI::Core::CompositionHelper::SetCompositionRoot_Impl(Windows::UI::Composition::IVisual *,bool)

- ea: `0x180051120`
- end: `0x180051562`
- name: `?SetCompositionRoot_Impl@CompositionHelper@Core@UI@Windows@@UEAAJPEAUIVisual@Composition@34@_N@Z`
- size: `1090`
- prototype: `__int64 __fastcall(Windows::UI::Core::CompositionHelper *__hidden this, struct Windows::UI::Composition::IVisual *, bool)`
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800038e0`
- `0x18000cdc8`
- `0x180014754`
- `0x180025228`
- `0x180026820`
- `0x18002b770`
- `0x1800493cc`
- `0x18004f474`
- `0x180050360`
- `0x180051120`
- `0x180051568`
- `0x1800516b0`
- `0x180051750`
- `0x1800517a0`
- `0x180097110`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800514e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051533`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800514e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051533`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180051195`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18005150c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180051195`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18005150c`

## string_xrefs

- `0x18005117b`: `Composition Root already set!`
- `0x1800514f2`: `Composition Root already set!`
- `0x180051236`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\componenthelper.cpp`
- `0x180051434`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\componenthelper.cpp`
- `0x180051494`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\componenthelper.cpp`
- `0x18005151a`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\componenthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Core::CompositionHelper::SetCompositionRoot_Impl(
        Windows::UI::Core::CompositionHelper *this,
        struct Windows::UI::Composition::IVisual *a2,
        char a3)
{
  struct Windows::UI::Composition::IVisual *v6; // rax
  _QWORD *v7; // rax
  __int64 v8; // rdx
  int updated; // edi
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 (__fastcall ***v14)(_QWORD, GUID *, struct Windows::ApplicationModel::Core::ICoreApplicationView **); // rdi
  __int64 (__fastcall *v15)(_QWORD, GUID *, struct Windows::ApplicationModel::Core::ICoreApplicationView **); // rbx
  struct Windows::ApplicationModel::Core::ICoreApplicationView *v16; // rdi
  __int64 (__fastcall *v17)(struct Windows::ApplicationModel::Core::ICoreApplicationView *, _QWORD, _QWORD, __int64 *); // rbx
  bool v18; // sf
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, char *); // rbx
  char *v21; // r14
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64 *); // rbx
  int CoreApplicationViewOfCurrentThread; // eax
  _QWORD *v26; // rax
  int v27; // [rsp+20h] [rbp-59h]
  struct Windows::ApplicationModel::Core::ICoreApplicationView *v28; // [rsp+30h] [rbp-49h] BYREF
  __int64 v29; // [rsp+38h] [rbp-41h] BYREF
  __int64 v30; // [rsp+40h] [rbp-39h] BYREF
  __int64 v31; // [rsp+48h] [rbp-31h] BYREF
  __int64 v32; // [rsp+50h] [rbp-29h] BYREF
  __int64 v33; // [rsp+58h] [rbp-21h] BYREF
  __int64 v34; // [rsp+60h] [rbp-19h] BYREF
  PSRWLOCK SRWLock; // [rsp+68h] [rbp-11h] BYREF
  HSTRING string[4]; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 104);
  if ( *((_QWORD *)this + 12) )
  {
    v26 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, L"Composition Root already set!");
    RoOriginateError(2291664896LL, *v26);
    v8 = 53;
    goto LABEL_51;
  }
  v6 = (struct Windows::UI::Composition::IVisual *)*((_QWORD *)this + 6);
  if ( a2 && v6 )
  {
    v7 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, L"Composition Root already set!");
    RoOriginateError(2291664896LL, *v7);
    v8 = 55;
LABEL_51:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\componenthelper.cpp",
      (const char *)0x88980800LL,
      v27);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 2291664896LL;
  }
  if ( v6 == a2 )
    goto LABEL_6;
  if ( a2 )
  {
    v34 = 0;
    v30 = 0;
    v33 = 0;
    v32 = 0;
    v31 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::operator=((char *)this + 48, a2);
    updated = Microsoft::WRL::ComPtr<Windows::UI::Composition::Internal::ICompositionIslandPartner>::As<Windows::UI::Composition::ICompositionObject>(
                (char *)this + 48,
                &v34);
    if ( updated >= 0 )
    {
      v10 = v34;
      v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 48LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v30);
      updated = v11(v10, &v30);
      if ( updated >= 0 )
      {
        if ( !v30 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x68,
            (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\componenthelper.cpp",
            (const char *)0x8000FFFFLL,
            v27);
        updated = Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<Windows::UI::Composition::ICompositorPartner>(
                    &v30,
                    &v33);
        if ( updated >= 0 )
        {
          v12 = v33;
          if ( *((_QWORD *)this + 4) != v33 )
          {
            v13 = *((_QWORD *)this + 5);
            if ( v13 )
            {
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 56LL))(v13, 0);
              Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 40);
              v12 = v33;
            }
            if ( *((_QWORD *)this + 4) != v12 )
            {
              if ( v12 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
              v28 = (struct Windows::ApplicationModel::Core::ICoreApplicationView *)*((_QWORD *)this + 4);
              *((_QWORD *)this + 4) = v12;
              Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
            }
          }
          if ( !*((_QWORD *)this + 5) )
          {
            v28 = 0;
            v29 = 0;
            if ( !a3 )
            {
              v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct Windows::ApplicationModel::Core::ICoreApplicationView **))*((_QWORD *)this + 4);
              v15 = **v14;
              Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
              updated = v15(v14, &GUID_29e691fa_4567_4dca_b319_d0f207eb6807, &v28);
              if ( updated >= 0 )
              {
                v16 = v28;
                v17 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Core::ICoreApplicationView *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v28 + 24LL);
                Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
                updated = v17(v16, *((_QWORD *)this + 14), 0, &v29);
                if ( updated >= 0 )
                  updated = Microsoft::WRL::ComPtr<Windows::UI::Composition::Desktop::IDesktopWindowTarget>::As<Windows::UI::Composition::Private::ICompositionTargetPartner>(
                              &v29,
                              (char *)this + 40);
              }
            }
            Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
            Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
          }
        }
      }
    }
    v18 = updated < 0;
    if ( !updated )
    {
      v19 = v30;
      v20 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v30 + 72LL);
      v21 = (char *)this + 56;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 56);
      updated = v20(v19, (char *)this + 56);
      if ( !updated )
      {
        v22 = *(_QWORD *)v21;
        v23 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)v21 + 48LL);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v32);
        updated = v23(v22, &v32);
        if ( !updated )
        {
          updated = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 72LL))(v32, *((_QWORD *)this + 6));
          if ( !updated )
          {
            updated = Microsoft::WRL::ComPtr<Windows::UI::Composition::ISpriteVisual>::As<Windows::UI::Composition::IVisual>(
                        (char *)this + 56,
                        &v31);
            if ( !updated )
            {
              updated = Windows::UI::Core::CompositionHelper::UpdateScaleAndRelativeSize(this);
              if ( !updated )
              {
                *((_BYTE *)this + 64) = 1;
                goto LABEL_36;
              }
            }
          }
        }
      }
      v18 = updated < 0;
    }
    if ( v18 )
    {
LABEL_45:
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v33);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v30);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v34);
      if ( updated < 0 )
        Windows::UI::Core::CompositionHelper::DisconnectCompositionInternal(this);
      goto LABEL_47;
    }
LABEL_36:
    if ( a3 )
    {
      v28 = 0;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
      CoreApplicationViewOfCurrentThread = GetCoreApplicationViewOfCurrentThread(&v28);
      if ( CoreApplicationViewOfCurrentThread < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0xC4,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\componenthelper.cpp",
          (const char *)(unsigned int)CoreApplicationViewOfCurrentThread,
          v27);
      v29 = 0;
      updated = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationView>::As<Windows::Foundation::Private::ICoreApplicationView4>(
                  &v28,
                  &v29);
      if ( updated >= 0 )
        updated = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 72LL))(v29, v31);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
    }
    else
    {
      updated = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 56LL))(
                  *((_QWORD *)this + 5),
                  v31);
    }
    if ( updated >= 1 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\componenthelper.cpp",
        (const char *)0x8000FFFFLL,
        v27);
    goto LABEL_45;
  }
  Windows::UI::Core::CompositionHelper::DisconnectCompositionInternal(this);
LABEL_6:
  updated = 0;
LABEL_47:
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180051120  mov     [rsp-8+arg_10], rbx
0x180051125  push    rbp
0x180051126  push    rsi
0x180051127  push    rdi
0x180051128  push    r12
0x18005112a  push    r13
0x18005112c  push    r14
0x18005112e  push    r15
0x180051130  lea     rbp, [rsp-27h]
0x180051135  sub     rsp, 0A0h
0x18005113c  mov     rax, cs:__security_cookie
0x180051143  xor     rax, rsp
0x180051146  mov     [rbp+57h+var_40], rax
0x18005114a  mov     r12b, r8b
0x18005114d  mov     rbx, rdx
0x180051150  mov     rsi, rcx
0x180051153  lea     rdx, [rcx+68h]
0x180051157  lea     rcx, [rbp+57h+SRWLock]
0x18005115b  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180051160  xor     r13d, r13d
0x180051163  cmp     [rsi+60h], r13
0x180051167  jnz     loc_1800514F2
0x18005116d  mov     rax, [rsi+30h]
0x180051171  test    rbx, rbx
0x180051174  jz      short loc_1800511A4
0x180051176  test    rax, rax
0x180051179  jz      short loc_1800511A4
0x18005117b  lea     rdx, aCompositionRoo; "Composition Root already set!"
0x180051182  lea     rcx, [rbp+57h+string]; string
0x180051186  call    ??$?0$0BO@@StringReference@Internal@Windows@@QEAA@AEAY0BO@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[30])
0x18005118b  mov     rdx, [rax]
0x18005118e  mov     ebx, 88980800h
0x180051193  mov     ecx, ebx
0x180051195  call    cs:__imp_RoOriginateError
0x18005119b  lea     edx, [r13+37h]
0x18005119f  jmp     loc_180051517
0x1800511a4  cmp     rax, rbx
0x1800511a7  jnz     short loc_1800511B1
0x1800511a9  mov     edi, r13d
0x1800511ac  jmp     loc_1800514DF
0x1800511b1  test    rbx, rbx
0x1800511b4  jnz     short loc_1800511C0
0x1800511b6  mov     rcx, rsi; this
0x1800511b9  call    ?DisconnectCompositionInternal@CompositionHelper@Core@UI@Windows@@AEAAXXZ; Windows::UI::Core::CompositionHelper::DisconnectCompositionInternal(void)
0x1800511be  jmp     short loc_1800511A9
0x1800511c0  lea     r15, [rsi+30h]
0x1800511c4  mov     [rbp+57h+var_70], r13
0x1800511c8  mov     [rbp+57h+var_90], r13
0x1800511cc  mov     [rbp+57h+var_78], r13
0x1800511d0  mov     [rbp+57h+var_80], r13
0x1800511d4  mov     [rbp+57h+var_88], r13
0x1800511d8  mov     rdx, rbx
0x1800511db  mov     rcx, r15
0x1800511de  call    ??4?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUnknown@@@Z; Microsoft::WRL::ComPtr<IUnknown>::operator=(IUnknown *)
0x1800511e3  lea     rdx, [rbp+57h+var_70]
0x1800511e7  mov     rcx, r15
0x1800511ea  call    ??$As@UICompositionObject@Composition@UI@Windows@@@?$ComPtr@UICompositionIslandPartner@Internal@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionObject@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::Internal::ICompositionIslandPartner>::As<Windows::UI::Composition::ICompositionObject>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject>>)
0x1800511ef  mov     edi, eax
0x1800511f1  test    eax, eax
0x1800511f3  js      loc_180051354
0x1800511f9  mov     rdi, [rbp+57h+var_70]
0x1800511fd  mov     rax, [rdi]
0x180051200  mov     rbx, [rax+30h]
0x180051204  lea     rcx, [rbp+57h+var_90]
0x180051208  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005120d  lea     rdx, [rbp+57h+var_90]
0x180051211  mov     rcx, rdi
0x180051214  mov     rax, rbx
0x180051217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005121c  mov     edi, eax
0x18005121e  test    eax, eax
0x180051220  js      loc_180051354
0x180051226  cmp     [rbp+57h+var_90], r13
0x18005122a  jnz     short loc_180051248
0x18005122c  mov     rcx, [rbp+5Fh]; this
0x180051230  mov     r9d, 8000FFFFh; char *
0x180051236  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18005123d  mov     edx, 68h ; 'h'; void *
0x180051242  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180051248  lea     rdx, [rbp+57h+var_78]
0x18005124c  lea     rcx, [rbp+57h+var_90]
0x180051250  call    ??$As@UICompositorPartner@Composition@UI@Windows@@@?$ComPtr@UICompositor@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositorPartner@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<Windows::UI::Composition::ICompositorPartner>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositorPartner>>)
0x180051255  mov     edi, eax
0x180051257  test    eax, eax
0x180051259  js      loc_180051354
0x18005125f  mov     rbx, [rbp+57h+var_78]
0x180051263  cmp     [rsi+20h], rbx
0x180051267  jz      short loc_1800512BD
0x180051269  mov     rcx, [rsi+28h]
0x18005126d  test    rcx, rcx
0x180051270  jz      short loc_18005128D
0x180051272  mov     rax, [rcx]
0x180051275  xor     edx, edx
0x180051277  mov     rax, [rax+38h]
0x18005127b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051280  lea     rcx, [rsi+28h]
0x180051284  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180051289  mov     rbx, [rbp+57h+var_78]
0x18005128d  cmp     [rsi+20h], rbx
0x180051291  jz      short loc_1800512BD
0x180051293  test    rbx, rbx
0x180051296  jz      short loc_1800512A8
0x180051298  mov     rax, [rbx]
0x18005129b  mov     rcx, rbx
0x18005129e  mov     rax, [rax+8]
0x1800512a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512a7  nop
0x1800512a8  mov     rax, [rsi+20h]
0x1800512ac  mov     [rbp+57h+var_A0], rax
0x1800512b0  mov     [rsi+20h], rbx
0x1800512b4  lea     rcx, [rbp+57h+var_A0]
0x1800512b8  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800512bd  cmp     [rsi+28h], r13
0x1800512c1  jnz     loc_180051354
0x1800512c7  mov     [rbp+57h+var_A0], r13
0x1800512cb  mov     [rbp+57h+var_98], r13
0x1800512cf  test    r12b, r12b
0x1800512d2  jnz     short loc_180051342
0x1800512d4  mov     rdi, [rsi+20h]
0x1800512d8  mov     rax, [rdi]
0x1800512db  mov     rbx, [rax]
0x1800512de  lea     rcx, [rbp+57h+var_A0]
0x1800512e2  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800512e7  lea     r8, [rbp+57h+var_A0]
0x1800512eb  lea     rdx, _GUID_29e691fa_4567_4dca_b319_d0f207eb6807
0x1800512f2  mov     rcx, rdi
0x1800512f5  mov     rax, rbx
0x1800512f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512fd  mov     edi, eax
0x1800512ff  test    eax, eax
0x180051301  js      short loc_180051342
0x180051303  mov     rdi, [rbp+57h+var_A0]
0x180051307  mov     rax, [rdi]
0x18005130a  mov     rbx, [rax+18h]
0x18005130e  lea     rcx, [rbp+57h+var_98]
0x180051312  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180051317  lea     r9, [rbp+57h+var_98]
0x18005131b  xor     r8d, r8d
0x18005131e  mov     rdx, [rsi+70h]
0x180051322  mov     rcx, rdi
0x180051325  mov     rax, rbx
0x180051328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005132d  mov     edi, eax
0x18005132f  test    eax, eax
0x180051331  js      short loc_180051342
0x180051333  lea     rdx, [rsi+28h]
0x180051337  lea     rcx, [rbp+57h+var_98]
0x18005133b  call    ??$As@UICompositionTargetPartner@Private@Composition@UI@Windows@@@?$ComPtr@UIDesktopWindowTarget@Desktop@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionTargetPartner@Private@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::Desktop::IDesktopWindowTarget>::As<Windows::UI::Composition::Private::ICompositionTargetPartner>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::Private::ICompositionTargetPartner>>)
0x180051340  mov     edi, eax
0x180051342  lea     rcx, [rbp+57h+var_98]
0x180051346  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005134b  lea     rcx, [rbp+57h+var_A0]
0x18005134f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180051354  test    edi, edi
0x180051356  jnz     loc_1800513F0
0x18005135c  mov     rdi, [rbp+57h+var_90]
0x180051360  mov     rax, [rdi]
0x180051363  mov     rbx, [rax+48h]
0x180051367  lea     r14, [rsi+38h]
0x18005136b  mov     rcx, r14
0x18005136e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180051373  mov     rdx, r14
0x180051376  mov     rcx, rdi
0x180051379  mov     rax, rbx
0x18005137c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051381  mov     edi, eax
0x180051383  test    eax, eax
0x180051385  jnz     short loc_1800513EE
0x180051387  mov     rdi, [r14]
0x18005138a  mov     rax, [rdi]
0x18005138d  mov     rbx, [rax+30h]
0x180051391  lea     rcx, [rbp+57h+var_80]
0x180051395  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005139a  lea     rdx, [rbp+57h+var_80]
0x18005139e  mov     rcx, rdi
0x1800513a1  mov     rax, rbx
0x1800513a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800513a9  mov     edi, eax
0x1800513ab  test    eax, eax
0x1800513ad  jnz     short loc_1800513EE
0x1800513af  mov     rcx, [rbp+57h+var_80]
0x1800513b3  mov     rax, [rcx]
0x1800513b6  mov     rdx, [r15]
0x1800513b9  mov     rax, [rax+48h]
0x1800513bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800513c2  mov     edi, eax
0x1800513c4  test    eax, eax
0x1800513c6  jnz     short loc_1800513EE
0x1800513c8  lea     rdx, [rbp+57h+var_88]
0x1800513cc  mov     rcx, r14
0x1800513cf  call    ??$As@UIVisual@Composition@UI@Windows@@@?$ComPtr@UISpriteVisual@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIVisual@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ISpriteVisual>::As<Windows::UI::Composition::IVisual>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisual>>)
0x1800513d4  mov     edi, eax
0x1800513d6  test    eax, eax
0x1800513d8  jnz     short loc_1800513EE
0x1800513da  mov     rcx, rsi; this
0x1800513dd  call    ?UpdateScaleAndRelativeSize@CompositionHelper@Core@UI@Windows@@AEAAJXZ; Windows::UI::Core::CompositionHelper::UpdateScaleAndRelativeSize(void)
0x1800513e2  mov     edi, eax
0x1800513e4  test    eax, eax
0x1800513e6  jnz     short loc_1800513EE
0x1800513e8  mov     byte ptr [rsi+40h], 1
0x1800513ec  jmp     short loc_1800513F6
0x1800513ee  test    edi, edi
0x1800513f0  js      loc_1800514A6
0x1800513f6  test    r12b, r12b
0x1800513f9  jnz     short loc_180051413
0x1800513fb  mov     rcx, [rsi+28h]
0x1800513ff  mov     rax, [rcx]
0x180051402  mov     rdx, [rbp+57h+var_88]
0x180051406  mov     rax, [rax+38h]
0x18005140a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005140f  mov     edi, eax
0x180051411  jmp     short loc_180051485
0x180051413  mov     [rbp+57h+var_A0], r13
0x180051417  lea     rcx, [rbp+57h+var_A0]
0x18005141b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180051420  lea     rcx, [rbp+57h+var_A0]; struct Windows::ApplicationModel::Core::ICoreApplicationView **
0x180051424  call    ?GetCoreApplicationViewOfCurrentThread@@YAJPEAPEAUICoreApplicationView@Core@ApplicationModel@Windows@@@Z; GetCoreApplicationViewOfCurrentThread(Windows::ApplicationModel::Core::ICoreApplicationView * *)
0x180051429  test    eax, eax
0x18005142b  jns     short loc_180051446
0x18005142d  mov     rcx, [rbp+5Fh]; this
0x180051431  mov     r9d, eax; char *
0x180051434  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18005143b  mov     edx, 0C4h; void *
0x180051440  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180051446  mov     [rbp+57h+var_98], r13
0x18005144a  lea     rdx, [rbp+57h+var_98]
0x18005144e  lea     rcx, [rbp+57h+var_A0]
0x180051452  call    ??$As@UICoreApplicationView4@Private@Foundation@Windows@@@?$ComPtr@UICoreApplicationView@Core@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICoreApplicationView4@Private@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationView>::As<Windows::Foundation::Private::ICoreApplicationView4>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Private::ICoreApplicationView4>>)
0x180051457  mov     edi, eax
0x180051459  test    eax, eax
0x18005145b  js      short loc_180051473
0x18005145d  mov     rcx, [rbp+57h+var_98]
0x180051461  mov     rax, [rcx]
0x180051464  mov     rdx, [rbp+57h+var_88]
0x180051468  mov     rax, [rax+48h]
0x18005146c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051471  mov     edi, eax
0x180051473  lea     rcx, [rbp+57h+var_98]
0x180051477  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005147c  lea     rcx, [rbp+57h+var_A0]
0x180051480  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180051485  cmp     edi, 1
0x180051488  jl      short loc_1800514A6
0x18005148a  mov     rcx, [rbp+5Fh]; this
0x18005148e  mov     r9d, 8000FFFFh; char *
0x180051494  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18005149b  mov     edx, 0D5h; void *
0x1800514a0  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800514a6  lea     rcx, [rbp+57h+var_88]
0x1800514aa  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800514af  lea     rcx, [rbp+57h+var_80]
0x1800514b3  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800514b8  lea     rcx, [rbp+57h+var_78]
0x1800514bc  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800514c1  lea     rcx, [rbp+57h+var_90]
0x1800514c5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800514ca  lea     rcx, [rbp+57h+var_70]
0x1800514ce  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800514d3  test    edi, edi
0x1800514d5  jns     short loc_1800514DF
0x1800514d7  mov     rcx, rsi; this
0x1800514da  call    ?DisconnectCompositionInternal@CompositionHelper@Core@UI@Windows@@AEAAXXZ; Windows::UI::Core::CompositionHelper::DisconnectCompositionInternal(void)
0x1800514df  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800514e3  test    rcx, rcx
0x1800514e6  jz      short loc_1800514EE
0x1800514e8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800514ee  mov     eax, edi
0x1800514f0  jmp     short loc_18005153B
0x1800514f2  lea     rdx, aCompositionRoo; "Composition Root already set!"
0x1800514f9  lea     rcx, [rbp+57h+string]; string
0x1800514fd  call    ??$?0$0BO@@StringReference@Internal@Windows@@QEAA@AEAY0BO@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[30])
0x180051502  mov     rdx, [rax]
0x180051505  mov     ebx, 88980800h
0x18005150a  mov     ecx, ebx
0x18005150c  call    cs:__imp_RoOriginateError
0x180051512  mov     edx, 35h ; '5'; void *
0x180051517  mov     r9d, ebx; char *
0x18005151a  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180051521  mov     rcx, [rbp+5Fh]; this
0x180051525  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005152a  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18005152e  test    rcx, rcx
0x180051531  jz      short loc_180051539
0x180051533  call    cs:__imp_ReleaseSRWLockExclusive
0x180051539  mov     eax, ebx
0x18005153b  mov     rcx, [rbp+57h+var_40]
0x18005153f  xor     rcx, rsp; StackCookie
0x180051542  call    __security_check_cookie
0x180051547  mov     rbx, [rsp+0D0h+arg_10]
0x18005154f  add     rsp, 0A0h
0x180051556  pop     r15
0x180051558  pop     r14
0x18005155a  pop     r13
0x18005155c  pop     r12
0x18005155e  pop     rdi
0x18005155f  pop     rsi
0x180051560  pop     rbp
0x180051561  retn
```
