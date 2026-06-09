# IslandEnvironmentOwner::GetIslandEnvironment(Windows::UI::Composition::ICompositionIslandEnvironment * *)

- ea: `0x180028844`
- end: `0x1800289c5`
- name: `?GetIslandEnvironment@IslandEnvironmentOwner@@QEAAJPEAPEAUICompositionIslandEnvironment@Composition@UI@Windows@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(IslandEnvironmentOwner *__hidden this, struct Windows::UI::Composition::ICompositionIslandEnvironment **)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028800`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x180026c9c`
- `0x180028844`
- `0x1800289cc`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002894b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028999`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002894b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028999`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028879`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028879`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800289af`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800289af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800288b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800288b1`

## string_xrefs

- `0x1800288aa`: `Windows.UI.Composition.CompositionIslandEnvironment`
- `0x180028973`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IslandEnvironmentOwner::GetIslandEnvironment(RTL_SRWLOCK *this, PVOID *a2)
{
  RTL_SRWLOCK *v4; // rsi
  HRESULT v5; // eax
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, RTL_SRWLOCK *); // rbx
  __int64 v9; // rcx
  __int64 v11; // rdx
  _QWORD v12[2]; // [rsp+20h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  *a2 = 0;
  v4 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  v12[1] = v4;
  if ( this->Ptr )
  {
LABEL_7:
    if ( this->Ptr )
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)this->Ptr + 8LL))(this->Ptr);
    *a2 = this->Ptr;
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    return 0;
  }
  v12[0] = 0;
  string = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.UI.Composition.CompositionIslandEnvironment",
         0x33u,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionIslandEnvironmentStatics>>(
         string,
         v12);
  if ( v6 < 0 )
  {
    v11 = 792;
  }
  else
  {
    v7 = v12[0];
    v8 = *(__int64 (__fastcall **)(__int64, RTL_SRWLOCK *))(*(_QWORD *)v12[0] + 48LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(this);
    v6 = v8(v7, this);
    if ( v6 >= 0 )
    {
      IslandEnvironmentOwner::UpdateMetricsWorker((IslandEnvironmentOwner *)this);
      v9 = v12[0];
      if ( v12[0] )
      {
        v12[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      goto LABEL_7;
    }
    v11 = 794;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
    (const char *)(unsigned int)v6,
    v12[0]);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v12);
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180028844  mov     [rsp-28h+arg_10], rbx
0x180028849  push    rbp
0x18002884a  push    rsi
0x18002884b  push    rdi
0x18002884c  push    r14
0x18002884e  push    r15
0x180028850  mov     rbp, rsp
0x180028853  sub     rsp, 60h
0x180028857  mov     rax, cs:__security_cookie
0x18002885e  xor     rax, rsp
0x180028861  mov     [rbp+var_10], rax
0x180028865  mov     r15, rdx
0x180028868  mov     r14, rcx
0x18002886b  mov     qword ptr [rdx], 0
0x180028872  lea     rsi, [rcx+8]
0x180028876  mov     rcx, rsi; SRWLock
0x180028879  call    cs:__imp_AcquireSRWLockExclusive
0x18002887f  mov     [rbp+var_38], rsi
0x180028883  cmp     qword ptr [r14], 0
0x180028887  jnz     loc_180028928
0x18002888d  mov     [rbp+var_40], 0
0x180028895  mov     [rbp+string], 0
0x18002889d  lea     r9, [rbp+string]; string
0x1800288a1  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800288a5  mov     edx, 33h ; '3'; length
0x1800288aa  lea     rcx, ?RuntimeClass_Windows_UI_Composition_CompositionIslandEnvironment@@3QBGB; "Windows.UI.Composition.CompositionIslan"...
0x1800288b1  call    cs:__imp_WindowsCreateStringReference
0x1800288b7  test    eax, eax
0x1800288b9  js      loc_1800289A3
0x1800288bf  lea     rdx, [rbp+var_40]
0x1800288c3  mov     rcx, [rbp+string]
0x1800288c7  call    ??$GetActivationFactory@V?$ComPtr@UICompositionIslandEnvironmentStatics@Composition@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICompositionIslandEnvironmentStatics@Composition@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionIslandEnvironmentStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionIslandEnvironmentStatics>>)
0x1800288cc  mov     ebx, eax
0x1800288ce  test    eax, eax
0x1800288d0  js      loc_1800289B6
0x1800288d6  mov     rdi, [rbp+var_40]
0x1800288da  mov     rax, [rdi]
0x1800288dd  mov     rbx, [rax+30h]
0x1800288e1  mov     rcx, r14
0x1800288e4  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800288e9  mov     rdx, r14
0x1800288ec  mov     rcx, rdi
0x1800288ef  mov     rax, rbx
0x1800288f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288f7  mov     ebx, eax
0x1800288f9  test    eax, eax
0x1800288fb  js      loc_1800289BD
0x180028901  mov     rcx, r14; this
0x180028904  call    ?UpdateMetricsWorker@IslandEnvironmentOwner@@AEAAXXZ; IslandEnvironmentOwner::UpdateMetricsWorker(void)
0x180028909  nop
0x18002890a  mov     rcx, [rbp+var_40]
0x18002890e  test    rcx, rcx
0x180028911  jz      short loc_180028928
0x180028913  mov     [rbp+var_40], 0
0x18002891b  mov     rax, [rcx]
0x18002891e  mov     rax, [rax+10h]
0x180028922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028927  nop
0x180028928  mov     rcx, [r14]
0x18002892b  test    rcx, rcx
0x18002892e  jz      short loc_18002893D
0x180028930  mov     rax, [rcx]
0x180028933  mov     rax, [rax+8]
0x180028937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002893c  nop
0x18002893d  mov     rax, [r14]
0x180028940  mov     [r15], rax
0x180028943  test    rsi, rsi
0x180028946  jz      short loc_180028951
0x180028948  mov     rcx, rsi; SRWLock
0x18002894b  call    cs:__imp_ReleaseSRWLockExclusive
0x180028951  xor     eax, eax
0x180028953  mov     rcx, [rbp+var_10]
0x180028957  xor     rcx, rsp; StackCookie
0x18002895a  call    __security_check_cookie
0x18002895f  mov     rbx, [rsp+60h+arg_10]
0x180028967  add     rsp, 60h
0x18002896b  pop     r15
0x18002896d  pop     r14
0x18002896f  pop     rdi
0x180028970  pop     rsi
0x180028971  pop     rbp
0x180028972  retn
0x180028973  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18002897a  mov     r9d, ebx; char *
0x18002897d  mov     rcx, [rbp+28h]; this
0x180028981  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028986  nop
0x180028987  lea     rcx, [rbp+var_40]
0x18002898b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180028990  nop
0x180028991  test    rsi, rsi
0x180028994  jz      short loc_18002899F
0x180028996  mov     rcx, rsi; SRWLock
0x180028999  call    cs:__imp_ReleaseSRWLockExclusive
0x18002899f  mov     eax, ebx
0x1800289a1  jmp     short loc_180028953
0x1800289a3  xor     r9d, r9d; lpArguments
0x1800289a6  xor     r8d, r8d; nNumberOfArguments
0x1800289a9  lea     edx, [r9+1]; dwExceptionFlags
0x1800289ad  mov     ecx, eax; dwExceptionCode
0x1800289af  call    cs:__imp_RaiseException
0x1800289b5  int     3; Trap to Debugger
0x1800289b6  mov     edx, 318h; void *
0x1800289bb  jmp     short loc_180028973
0x1800289bd  mov     edx, 31Ah
0x1800289c2  jmp     short loc_180028973
```
