# DefaultHumanProvider::StartMonitoringIpdChange(void)

- ea: `0x18000e468`
- end: `0x18000e781`
- name: `?StartMonitoringIpdChange@DefaultHumanProvider@@AEAAJXZ`
- size: `793`
- prototype: `__int64 __fastcall(DefaultHumanProvider *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e3f4`

## callees

- `0x180006ea0`
- `0x180006ee4`
- `0x1800071e4`
- `0x18000d780`
- `0x18000e330`
- `0x18000e468`
- `0x18000e990`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e5c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e5c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000e581`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000e581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5ae`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000e4ea`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000e4ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e4aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e4aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DefaultHumanProvider::StartMonitoringIpdChange(DefaultHumanProvider *this)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  __int64 *v5; // rdi
  HSTRING v6; // rsi
  __int64 v7; // rcx
  int ActivationFactory; // eax
  unsigned int v9; // esi
  const char *v10; // r9
  __int64 result; // rax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, char *); // r14
  _QWORD *v14; // rsi
  __int64 v15; // rcx
  int v16; // eax
  unsigned int v17; // edi
  unsigned int v18; // r8d
  const char *v19; // r9
  HANDLE Event; // r14
  void *v21; // rdi
  DWORD LastError; // r15d
  unsigned int v23; // r8d
  const char *v24; // r9
  int v25; // eax
  unsigned int v26; // edi
  __int64 v27; // rcx
  int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rcx
  int v31; // eax
  unsigned int v32; // ebx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // [rsp+20h] [rbp-58h] BYREF
  DefaultHumanProvider *v36; // [rsp+28h] [rbp-50h] BYREF
  HSTRING_HEADER v37; // [rsp+30h] [rbp-48h] BYREF
  HSTRING v38; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v38 = 0;
  v2 = WindowsCreateStringReference(L"Windows.Graphics.Holographic.HolographicDisplay", 0x2Fu, &v37, &v38);
  try
  {
    if ( v2 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
      __debugbreak();
    }
    v5 = (__int64 *)((char *)this + 24);
    v6 = v38;
    v7 = *((_QWORD *)this + 3);
    if ( v7 )
    {
      *v5 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    ActivationFactory = RoGetActivationFactory(v6, &GUID_e464b452_7eb3_434b_95d6_1339477e80c7, (char *)this + 24);
    v9 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v12 = *v5;
      v13 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 48LL);
      v14 = (_QWORD *)((char *)this + 40);
      v15 = *((_QWORD *)this + 5);
      if ( v15 )
      {
        *v14 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      v16 = v13(v12, (char *)this + 40);
      v17 = v16;
      if ( v16 >= 0 )
      {
        Event = CreateEventExW(0, 0, 0, 0x1F0003u);
        if ( !Event )
          wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x1CC8, v18, v19);
        GetLastError();
        v21 = (void *)*((_QWORD *)this + 2);
        if ( v21 )
        {
          LastError = GetLastError();
          if ( !CloseHandle(v21) )
            wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
          SetLastError(LastError);
        }
        *((_QWORD *)this + 2) = Event;
        v37.Reserved.Reserved1 = DefaultHumanProvider::HandleDisplayChange;
        *(_DWORD *)&v37.Reserved.Reserved2[8] = 0;
        v36 = this;
        wil::MakeAgileCallback<Windows::Foundation::ITypedEventHandler<Windows::Graphics::Holographic::Internal::HolographicDisplayWatcher *,Windows::Graphics::Holographic::HolographicDisplay *>,DefaultHumanProvider *,long (DefaultHumanProvider::*)(Windows::Graphics::Holographic::Internal::IHolographicDisplayWatcher *,Windows::Graphics::Holographic::IHolographicDisplay *)>(
          &v35,
          &v36,
          &v37);
        v25 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v14 + 56LL))(
                *v14,
                v35,
                (char *)this + 56);
        v26 = v25;
        if ( v25 >= 0 )
        {
          v28 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v14 + 72LL))(
                  *v14,
                  v35,
                  (char *)this + 64);
          v29 = v28;
          if ( v28 >= 0 )
          {
            v31 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 120LL))(*v14);
            v32 = v31;
            if ( v31 >= 0 )
            {
              v34 = v35;
              if ( v35 )
              {
                v35 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
              }
              result = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x37,
                (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\defaulthumanprovider.cpp",
                (const char *)(unsigned int)v31,
                v35);
              v33 = v35;
              if ( v35 )
              {
                v35 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
              }
              result = v32;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x36,
              (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\defaulthumanprovider.cpp",
              (const char *)(unsigned int)v28,
              v35);
            v30 = v35;
            if ( v35 )
            {
              v35 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            }
            result = v29;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x35,
            (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\defaulthumanprovider.cpp",
            (const char *)(unsigned int)v25,
            v35);
          v27 = v35;
          if ( v35 )
          {
            v35 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          }
          result = v26;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B,
          (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\defaulthumanprovider.cpp",
          (const char *)(unsigned int)v16,
          v35);
        result = v17;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\defaulthumanprovider.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v35);
      result = v9;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3A,
                           (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\defaulthumanprovider.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x18000e468  mov     r11, rsp
0x18000e46b  mov     [r11+10h], rbx
0x18000e46f  mov     [r11+18h], rsi
0x18000e473  push    rdi
0x18000e474  push    r14
0x18000e476  push    r15
0x18000e478  sub     rsp, 60h
0x18000e47c  mov     rax, cs:__security_cookie
0x18000e483  xor     rax, rsp
0x18000e486  mov     [rsp+78h+var_28], rax
0x18000e48b  mov     rbx, rcx
0x18000e48e  mov     qword ptr [r11-30h], 0
0x18000e496  lea     r9, [r11-30h]; string
0x18000e49a  lea     r8, [r11-48h]; hstringHeader
0x18000e49e  mov     edx, 2Fh ; '/'; length
0x18000e4a3  lea     rcx, ?RuntimeClass_Windows_Graphics_Holographic_HolographicDisplay@@3QB_WB; "Windows.Graphics.Holographic.Holographi"...
0x18000e4aa  call    cs:__imp_WindowsCreateStringReference
0x18000e4b0  test    eax, eax
0x18000e4b2  js      loc_18000E75D
0x18000e4b8  lea     rdi, [rbx+18h]
0x18000e4bc  mov     rsi, [rsp+78h+var_30]
0x18000e4c1  mov     rcx, [rdi]
0x18000e4c4  test    rcx, rcx
0x18000e4c7  jz      short loc_18000E4DD
0x18000e4c9  mov     qword ptr [rdi], 0
0x18000e4d0  mov     rax, [rcx]
0x18000e4d3  mov     rax, [rax+10h]
0x18000e4d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4dc  nop
0x18000e4dd  mov     r8, rdi
0x18000e4e0  lea     rdx, _GUID_e464b452_7eb3_434b_95d6_1339477e80c7
0x18000e4e7  mov     rcx, rsi
0x18000e4ea  call    cs:__imp_RoGetActivationFactory
0x18000e4f0  mov     esi, eax
0x18000e4f2  test    eax, eax
0x18000e4f4  jns     short loc_18000E516
0x18000e4f6  mov     rcx, [rsp+78h]; this
0x18000e4fb  mov     r9d, eax; char *
0x18000e4fe  lea     r8, aAvcoreXaudioHr_5; "avcore\\xaudio\\hrtf\\ssdm\\lib\\defaul"...
0x18000e505  mov     edx, 28h ; '('; void *
0x18000e50a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e50f  mov     eax, esi
0x18000e511  jmp     loc_18000E73A
0x18000e516  mov     rdi, [rdi]
0x18000e519  mov     rax, [rdi]
0x18000e51c  mov     r14, [rax+30h]
0x18000e520  lea     rsi, [rbx+28h]
0x18000e524  mov     rcx, [rsi]
0x18000e527  test    rcx, rcx
0x18000e52a  jz      short loc_18000E540
0x18000e52c  mov     qword ptr [rsi], 0
0x18000e533  mov     rdx, [rcx]
0x18000e536  mov     rax, [rdx+10h]
0x18000e53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e53f  nop
0x18000e540  mov     rdx, rsi
0x18000e543  mov     rcx, rdi
0x18000e546  mov     rax, r14
0x18000e549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e54e  mov     edi, eax
0x18000e550  test    eax, eax
0x18000e552  jns     short loc_18000E574
0x18000e554  mov     rcx, [rsp+78h]; this
0x18000e559  mov     r9d, eax; char *
0x18000e55c  lea     r8, aAvcoreXaudioHr_5; "avcore\\xaudio\\hrtf\\ssdm\\lib\\defaul"...
0x18000e563  mov     edx, 2Bh ; '+'; void *
0x18000e568  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e56d  mov     eax, edi
0x18000e56f  jmp     loc_18000E73A
0x18000e574  mov     r9d, 1F0003h; dwDesiredAccess
0x18000e57a  xor     r8d, r8d; dwFlags
0x18000e57d  xor     edx, edx; lpName
0x18000e57f  xor     ecx, ecx; lpEventAttributes
0x18000e581  call    cs:__imp_CreateEventExW
0x18000e587  mov     r14, rax
0x18000e58a  test    rax, rax
0x18000e58d  jz      loc_18000E770
0x18000e593  call    cs:__imp_GetLastError
0x18000e599  mov     rdi, [rbx+10h]
0x18000e59d  test    rdi, rdi
0x18000e5a0  jz      short loc_18000E5CA
0x18000e5a2  call    cs:__imp_GetLastError
0x18000e5a8  mov     r15d, eax
0x18000e5ab  mov     rcx, rdi; hObject
0x18000e5ae  call    cs:__imp_CloseHandle
0x18000e5b4  mov     rcx, [rsp+78h]; this
0x18000e5b9  test    eax, eax
0x18000e5bb  jz      loc_18000E765
0x18000e5c1  mov     ecx, r15d; dwErrCode
0x18000e5c4  call    cs:__imp_SetLastError
0x18000e5ca  mov     [rbx+10h], r14
0x18000e5ce  lea     rax, ?HandleDisplayChange@DefaultHumanProvider@@AEAAJPEAUIHolographicDisplayWatcher@Internal@Holographic@Graphics@Windows@@PEAUIHolographicDisplay@456@@Z; DefaultHumanProvider::HandleDisplayChange(Windows::Graphics::Holographic::Internal::IHolographicDisplayWatcher *,Windows::Graphics::Holographic::IHolographicDisplay *)
0x18000e5d5  mov     [rsp+78h+var_48], rax
0x18000e5da  mov     [rsp+78h+var_40], 0
0x18000e5e2  mov     eax, [rsp+78h+var_3C]
0x18000e5e6  mov     [rsp+78h+var_3C], eax
0x18000e5ea  mov     [rsp+78h+var_50], rbx
0x18000e5ef  lea     r8, [rsp+78h+var_48]
0x18000e5f4  lea     rdx, [rsp+78h+var_50]
0x18000e5f9  lea     rcx, [rsp+78h+var_58]
0x18000e5fe  call    ??$MakeAgileCallback@U?$ITypedEventHandler@PEAVHolographicDisplayWatcher@Internal@Holographic@Graphics@Windows@@PEAVHolographicDisplay@345@@Foundation@Windows@@PEAVDefaultHumanProvider@@P84@EAAJPEAUIHolographicDisplayWatcher@Internal@Holographic@Graphics@3@PEAUIHolographicDisplay@783@@Z@wil@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVHolographicDisplayWatcher@Internal@Holographic@Graphics@Windows@@PEAVHolographicDisplay@345@@Foundation@Windows@@@WRL@Microsoft@@$$QEAPEAVDefaultHumanProvider@@$$QEAP84@EAAJPEAUIHolographicDisplayWatcher@Internal@Holographic@Graphics@Windows@@PEAUIHolographicDisplay@789@@Z@Z; wil::MakeAgileCallback<Windows::Foundation::ITypedEventHandler<Windows::Graphics::Holographic::Internal::HolographicDisplayWatcher *,Windows::Graphics::Holographic::HolographicDisplay *>,DefaultHumanProvider *,long (DefaultHumanProvider::*)(Windows::Graphics::Holographic::Internal::IHolographicDisplayWatcher *,Windows::Graphics::Holographic::IHolographicDisplay *)>(DefaultHumanProvider * &&,long (DefaultHumanProvider::*&&)(Windows::Graphics::Holographic::Internal::IHolographicDisplayWatcher *,Windows::Graphics::Holographic::IHolographicDisplay *))
0x18000e603  nop
0x18000e604  mov     rcx, [rsi]
0x18000e607  mov     rax, [rcx]
0x18000e60a  lea     r8, [rbx+38h]
0x18000e60e  mov     rdx, [rsp+78h+var_58]
0x18000e613  mov     rax, [rax+38h]
0x18000e617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e61c  mov     edi, eax
0x18000e61e  test    eax, eax
0x18000e620  jns     short loc_18000E663
0x18000e622  mov     rcx, [rsp+78h]; this
0x18000e627  mov     r9d, eax; char *
0x18000e62a  lea     r8, aAvcoreXaudioHr_5; "avcore\\xaudio\\hrtf\\ssdm\\lib\\defaul"...
0x18000e631  mov     edx, 35h ; '5'; void *
0x18000e636  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e63b  nop
0x18000e63c  mov     rcx, [rsp+78h+var_58]
0x18000e641  test    rcx, rcx
0x18000e644  jz      short loc_18000E65C
0x18000e646  mov     [rsp+78h+var_58], 0
0x18000e64f  mov     rax, [rcx]
0x18000e652  mov     rax, [rax+10h]
0x18000e656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e65b  nop
0x18000e65c  mov     eax, edi
0x18000e65e  jmp     loc_18000E73A
0x18000e663  mov     rcx, [rsi]
0x18000e666  mov     rax, [rcx]
0x18000e669  lea     r8, [rbx+40h]
0x18000e66d  mov     rdx, [rsp+78h+var_58]
0x18000e672  mov     rax, [rax+48h]
0x18000e676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e67b  mov     ebx, eax
0x18000e67d  test    eax, eax
0x18000e67f  jns     short loc_18000E6BF
0x18000e681  mov     rcx, [rsp+78h]; this
0x18000e686  mov     r9d, eax; char *
0x18000e689  lea     r8, aAvcoreXaudioHr_5; "avcore\\xaudio\\hrtf\\ssdm\\lib\\defaul"...
0x18000e690  mov     edx, 36h ; '6'; void *
0x18000e695  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e69a  nop
0x18000e69b  mov     rcx, [rsp+78h+var_58]
0x18000e6a0  test    rcx, rcx
0x18000e6a3  jz      short loc_18000E6BB
0x18000e6a5  mov     [rsp+78h+var_58], 0
0x18000e6ae  mov     rax, [rcx]
0x18000e6b1  mov     rax, [rax+10h]
0x18000e6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ba  nop
0x18000e6bb  mov     eax, ebx
0x18000e6bd  jmp     short loc_18000E73A
0x18000e6bf  mov     rcx, [rsi]
0x18000e6c2  mov     rax, [rcx]
0x18000e6c5  mov     rax, [rax+78h]
0x18000e6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ce  mov     ebx, eax
0x18000e6d0  test    eax, eax
0x18000e6d2  jns     short loc_18000E712
0x18000e6d4  mov     rcx, [rsp+78h]; this
0x18000e6d9  mov     r9d, eax; char *
0x18000e6dc  lea     r8, aAvcoreXaudioHr_5; "avcore\\xaudio\\hrtf\\ssdm\\lib\\defaul"...
0x18000e6e3  mov     edx, 37h ; '7'; void *
0x18000e6e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e6ed  nop
0x18000e6ee  mov     rcx, [rsp+78h+var_58]
0x18000e6f3  test    rcx, rcx
0x18000e6f6  jz      short loc_18000E70E
0x18000e6f8  mov     [rsp+78h+var_58], 0
0x18000e701  mov     rax, [rcx]
0x18000e704  mov     rax, [rax+10h]
0x18000e708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e70d  nop
0x18000e70e  mov     eax, ebx
0x18000e710  jmp     short loc_18000E73A
0x18000e712  mov     rcx, [rsp+78h+var_58]
0x18000e717  test    rcx, rcx
0x18000e71a  jz      short loc_18000E732
0x18000e71c  mov     [rsp+78h+var_58], 0
0x18000e725  mov     rax, [rcx]
0x18000e728  mov     rax, [rax+10h]
0x18000e72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e731  nop
0x18000e732  xor     eax, eax
0x18000e734  jmp     short loc_18000E73A
0x18000e736  mov     eax, dword ptr [rsp+78h+var_58]
0x18000e73a  mov     rcx, [rsp+78h+var_28]
0x18000e73f  xor     rcx, rsp; StackCookie
0x18000e742  call    __security_check_cookie
0x18000e747  lea     r11, [rsp+78h+var_18]
0x18000e74c  mov     rbx, [r11+28h]
0x18000e750  mov     rsi, [r11+30h]
0x18000e754  mov     rsp, r11
0x18000e757  pop     r15
0x18000e759  pop     r14
0x18000e75b  pop     rdi
0x18000e75c  retn
0x18000e75d  mov     ecx, eax; this
0x18000e75f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000e764  int     3; Trap to Debugger
0x18000e765  mov     edx, 0A0Bh; void *
0x18000e76a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e770  mov     rcx, [rsp+78h]; this
0x18000e775  mov     edx, 1CC8h; void *
0x18000e77a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
