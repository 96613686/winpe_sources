# UwpWindowEventDispatcher::RegisterForViewEventsWithOptions(Windows::Foundation::ITypedEventHandler<Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *,Windows::Internal::Shell::ViewManagerInterop::IViewEventArgs *> *,HSTRING__ *,HSTRING__ *,Windows::Internal::Shell::Desktop::ViewManagerInterop::ViewEventRegistrationFlags,EventRegistrationToken *)

- ea: `0x18004ff50`
- end: `0x1800502e1`
- name: `?RegisterForViewEventsWithOptions@UwpWindowEventDispatcher@@UEAAJPEAU?$ITypedEventHandler@PEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@PEAUIViewEventArgs@2345@@Foundation@Windows@@PEAUHSTRING__@@1W4ViewEventRegistrationFlags@ViewManagerInterop@Desktop@Shell@Internal@4@PEAUEventRegistrationToken@@@Z`
- size: `913`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801c9fd0`

## callees

- `0x1800134f8`
- `0x180019a38`
- `0x180043f00`
- `0x18004ff50`
- `0x1800502e8`
- `0x18005035c`
- `0x18007f488`
- `0x1801afa30`
- `0x18033f27c`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800500bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800500bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005026e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005026e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18005018a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18005018a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004ffab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004ffea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004ffab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004ffea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ffc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050003`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ffc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050003`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180050154`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180050167`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180050154`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180050167`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050215`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005022a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050215`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005022a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800500f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180050113`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800500f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180050113`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005013c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005013c`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180050058`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180050058`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UwpWindowEventDispatcher::RegisterForViewEventsWithOptions(
        RTL_SRWLOCK *a1,
        __int64 a2,
        HSTRING a3,
        HSTRING a4,
        int a5,
        _QWORD *a6)
{
  const char *v10; // r9
  HSTRING *v11; // rbx
  HRESULT v12; // edi
  HSTRING v13; // rcx
  __int64 v14; // rdi
  HRESULT v15; // ebx
  HSTRING v16; // rcx
  __int64 v17; // rbx
  HSTRING v18; // rax
  int AgileReference; // edi
  HSTRING v20; // rcx
  __int64 v21; // r8
  RTL_SRWLOCK *v22; // rbx
  RTL_SRWLOCK *v23; // r13
  HSTRING **Ptr; // rdi
  HSTRING **v25; // r12
  UINT32 StringLen; // r15d
  const WCHAR *StringRawBuffer; // r14
  UINT32 v28; // esi
  const WCHAR *v29; // rax
  char *v30; // rcx
  PVOID v31; // rcx
  const char *v32; // r9
  __int64 result; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-68h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-68h]
  HSTRING newString; // [rsp+30h] [rbp-58h] BYREF
  PCWSTR v37; // [rsp+38h] [rbp-50h] BYREF
  __int64 v38; // [rsp+40h] [rbp-48h] BYREF
  std::_Ref_count_base *v39; // [rsp+48h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  try
  {
    std::make_shared<ViewEventRegistration,>();
    v11 = (HSTRING *)v38;
    if ( !v38 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x819,
        (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindoweventdispatcher.cpp",
        v10);
    newString = 0;
    v12 = WindowsDuplicateString(a3, &newString);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x81A,
        (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindoweventdispatcher.cpp",
        (const char *)(unsigned int)v12,
        bIgnoreCase);
    v13 = *v11;
    *v11 = newString;
    WindowsDeleteString(v13);
    v14 = v38;
    newString = 0;
    v15 = WindowsDuplicateString(a4, &newString);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x81B,
        (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindoweventdispatcher.cpp",
        (const char *)(unsigned int)v15,
        bIgnoreCase);
    v16 = *(HSTRING *)(v14 + 8);
    *(_QWORD *)(v14 + 8) = newString;
    WindowsDeleteString(v16);
    *(_DWORD *)(v38 + 16) = a5;
    v17 = v38;
    v18 = 0;
    newString = 0;
    AgileReference = 0;
    if ( a2 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&newString);
      AgileReference = RoGetAgileReference(0, &GUID_c1659867_0cf6_5f3b_99df_4f036280926c, a2, &newString);
      v18 = newString;
    }
    v20 = 0;
    newString = 0;
    v21 = *(_QWORD *)(v17 + 24);
    *(_QWORD *)(v17 + 24) = v18;
    if ( v21 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v20 = newString;
    }
    if ( v20 )
    {
      newString = 0;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v20 + 16LL))(v20);
    }
    if ( AgileReference < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x81D,
        (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindoweventdispatcher.cpp",
        (const char *)(unsigned int)AgileReference,
        bIgnoreCase);
    v22 = a1 + 58;
    AcquireSRWLockExclusive(a1 + 58);
    v37 = (PCWSTR)&a1[58];
    v23 = a1 + 52;
    Ptr = (HSTRING **)a1[52].Ptr;
    v25 = (HSTRING **)a1[53].Ptr;
    while ( Ptr != v25 )
    {
      StringLen = WindowsGetStringLen(*(HSTRING *)v38);
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)v38, 0);
      v28 = WindowsGetStringLen(**Ptr);
      v29 = WindowsGetStringRawBuffer(**Ptr, 0);
      if ( CompareStringOrdinal(v29, v28, StringRawBuffer, StringLen, 1) == 2 )
      {
        if ( WindowsIsStringEmpty((*Ptr)[1])
          || WindowsIsStringEmpty(*(HSTRING *)(v38 + 8))
          || (LODWORD(newString) = 0,
              WindowsCompareStringOrdinal((*Ptr)[1], *(HSTRING *)(v38 + 8), (INT32 *)&newString),
              !(_DWORD)newString) )
        {
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x83A,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindoweventdispatcher.cpp",
            (const char *)0x80070057LL,
            bIgnoreCasea);
        }
      }
      Ptr += 2;
    }
    v30 = (char *)a1[51].Ptr;
    a1[51].Ptr = v30 + 1;
    *(_QWORD *)(v38 + 32) = v30;
    v31 = v23[1].Ptr;
    if ( v31 == v23[2].Ptr )
    {
      std::vector<std::shared_ptr<ViewEventRegistration>>::_Emplace_reallocate<std::shared_ptr<ViewEventRegistration> const &>(
        v23,
        v23[1].Ptr,
        &v38);
    }
    else
    {
      std::shared_ptr<InputAppViewCoodinatorHandler>::shared_ptr<InputAppViewCoodinatorHandler>(v31, &v38);
      v23[1].Ptr = (char *)v23[1].Ptr + 16;
    }
    *a6 = *(_QWORD *)(v38 + 32);
    newString = (HSTRING)WindowsGetStringRawBuffer(a4, 0);
    v37 = WindowsGetStringRawBuffer(a3, 0);
    ViewManagerInteropTraceLogging::WindowEventDispatcher_RegisterForViewEventsWithOptions<unsigned short const *,unsigned short const *>(
      &v37,
      &newString);
    if ( v22 )
      ReleaseSRWLockExclusive(v22);
    if ( v39 )
      std::_Ref_count_base::_Decref(v39);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x848,
                           (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\uwpwindoweventdispatcher.cpp",
                           v32);
  }
  return result;
}

```

## disassembly

```asm
0x18004ff50  mov     [rsp+string], r9
0x18004ff55  mov     [rsp+arg_10], r8
0x18004ff5a  mov     [rsp+arg_0], rcx
0x18004ff5f  push    rbx
0x18004ff60  push    rsi
0x18004ff61  push    rdi
0x18004ff62  push    r12
0x18004ff64  push    r13
0x18004ff66  push    r14
0x18004ff68  push    r15
0x18004ff6a  sub     rsp, 50h
0x18004ff6e  mov     r15, r9
0x18004ff71  mov     rdi, r8
0x18004ff74  mov     rsi, rdx
0x18004ff77  mov     r14, rcx
0x18004ff7a  lea     rcx, [rsp+88h+var_48]
0x18004ff7f  call    ??$make_shared@UViewEventRegistration@@$$V@std@@YA?AV?$shared_ptr@UViewEventRegistration@@@0@XZ; std::make_shared<ViewEventRegistration,>(void)
0x18004ff84  nop
0x18004ff85  mov     rcx, [rsp+88h]; this
0x18004ff8d  mov     rbx, [rsp+88h+var_48]
0x18004ff92  test    rbx, rbx
0x18004ff95  jz      loc_1800502C6
0x18004ff9b  xor     r12d, r12d
0x18004ff9e  mov     [rsp+88h+newString], r12
0x18004ffa3  lea     rdx, [rsp+88h+newString]; newString
0x18004ffa8  mov     rcx, rdi; string
0x18004ffab  call    cs:__imp_WindowsDuplicateString
0x18004ffb1  mov     edi, eax
0x18004ffb3  test    eax, eax
0x18004ffb5  js      short loc_18004FFC8
0x18004ffb7  mov     rcx, [rbx]; string
0x18004ffba  mov     rdx, [rsp+88h+newString]
0x18004ffbf  mov     [rbx], rdx
0x18004ffc2  call    cs:__imp_WindowsDeleteString
0x18004ffc8  mov     rcx, [rsp+88h]; this
0x18004ffd0  test    edi, edi
0x18004ffd2  js      loc_18005028A
0x18004ffd8  mov     rdi, [rsp+88h+var_48]
0x18004ffdd  mov     [rsp+88h+newString], r12
0x18004ffe2  lea     rdx, [rsp+88h+newString]; newString
0x18004ffe7  mov     rcx, r15; string
0x18004ffea  call    cs:__imp_WindowsDuplicateString
0x18004fff0  mov     ebx, eax
0x18004fff2  test    eax, eax
0x18004fff4  js      short loc_180050009
0x18004fff6  mov     rcx, [rdi+8]; string
0x18004fffa  mov     rdx, [rsp+88h+newString]
0x18004ffff  mov     [rdi+8], rdx
0x180050003  call    cs:__imp_WindowsDeleteString
0x180050009  mov     rcx, [rsp+88h]; this
0x180050011  test    ebx, ebx
0x180050013  js      loc_18005029E
0x180050019  mov     ecx, [rsp+88h+arg_20]
0x180050020  mov     rax, [rsp+88h+var_48]
0x180050025  mov     [rax+10h], ecx
0x180050028  mov     rbx, [rsp+88h+var_48]
0x18005002d  mov     rax, r12
0x180050030  mov     [rsp+88h+newString], rax
0x180050035  mov     edi, r12d
0x180050038  test    rsi, rsi
0x18005003b  jz      short loc_180050065
0x18005003d  lea     rcx, [rsp+88h+newString]
0x180050042  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050047  lea     r9, [rsp+88h+newString]
0x18005004c  mov     r8, rsi
0x18005004f  lea     rdx, _GUID_c1659867_0cf6_5f3b_99df_4f036280926c
0x180050056  xor     ecx, ecx
0x180050058  call    cs:__imp_RoGetAgileReference
0x18005005e  mov     edi, eax
0x180050060  mov     rax, [rsp+88h+newString]
0x180050065  mov     rcx, r12
0x180050068  mov     [rsp+88h+newString], rcx
0x18005006d  mov     r8, [rbx+18h]
0x180050071  mov     [rbx+18h], rax
0x180050075  test    r8, r8
0x180050078  jz      short loc_18005008E
0x18005007a  mov     rdx, [r8]
0x18005007d  mov     rcx, r8
0x180050080  mov     rax, [rdx+10h]
0x180050084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050089  mov     rcx, [rsp+88h+newString]
0x18005008e  test    rcx, rcx
0x180050091  jz      short loc_1800500A5
0x180050093  mov     [rsp+88h+newString], r12
0x180050098  mov     rax, [rcx]
0x18005009b  mov     rax, [rax+10h]
0x18005009f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500a4  nop
0x1800500a5  mov     rcx, [rsp+88h]; this
0x1800500ad  test    edi, edi
0x1800500af  js      loc_1800502B2
0x1800500b5  lea     rbx, [r14+1D0h]
0x1800500bc  mov     rcx, rbx; SRWLock
0x1800500bf  call    cs:__imp_AcquireSRWLockExclusive
0x1800500c5  mov     [rsp+88h+var_50], rbx
0x1800500ca  lea     r13, [r14+1A0h]
0x1800500d1  mov     rdi, [r13+0]
0x1800500d5  mov     r12, [r13+8]
0x1800500d9  nop     dword ptr [rax+00000000h]
0x1800500e0  cmp     rdi, r12
0x1800500e3  jz      loc_1800501B6
0x1800500e9  mov     rcx, [rsp+88h+var_48]
0x1800500ee  mov     rcx, [rcx]; string
0x1800500f1  call    cs:__imp_WindowsGetStringLen
0x1800500f7  mov     r15d, eax
0x1800500fa  xor     edx, edx; length
0x1800500fc  mov     rcx, [rsp+88h+var_48]
0x180050101  mov     rcx, [rcx]; string
0x180050104  call    cs:__imp_WindowsGetStringRawBuffer
0x18005010a  mov     r14, rax
0x18005010d  mov     rcx, [rdi]
0x180050110  mov     rcx, [rcx]; string
0x180050113  call    cs:__imp_WindowsGetStringLen
0x180050119  mov     esi, eax
0x18005011b  mov     rcx, [rdi]
0x18005011e  xor     edx, edx; length
0x180050120  mov     rcx, [rcx]; string
0x180050123  call    cs:__imp_WindowsGetStringRawBuffer
0x180050129  mov     [rsp+88h+bIgnoreCase], 1; int
0x180050131  mov     r9d, r15d; cchCount2
0x180050134  mov     r8, r14; lpString2
0x180050137  mov     edx, esi; cchCount1
0x180050139  mov     rcx, rax; lpString1
0x18005013c  call    cs:__imp_CompareStringOrdinal
0x180050142  cmp     eax, 2
0x180050145  jz      short loc_18005014D
0x180050147  add     rdi, 10h
0x18005014b  jmp     short loc_1800500E0
0x18005014d  mov     rcx, [rdi]
0x180050150  mov     rcx, [rcx+8]; string
0x180050154  call    cs:__imp_WindowsIsStringEmpty
0x18005015a  test    eax, eax
0x18005015c  jnz     short loc_180050197
0x18005015e  mov     rcx, [rsp+88h+var_48]
0x180050163  mov     rcx, [rcx+8]; string
0x180050167  call    cs:__imp_WindowsIsStringEmpty
0x18005016d  test    eax, eax
0x18005016f  jnz     short loc_180050197
0x180050171  mov     dword ptr [rsp+88h+newString], eax
0x180050175  mov     rcx, [rdi]
0x180050178  lea     r8, [rsp+88h+newString]; result
0x18005017d  mov     rdx, [rsp+88h+var_48]
0x180050182  mov     rdx, [rdx+8]; string2
0x180050186  mov     rcx, [rcx+8]; string1
0x18005018a  call    cs:__imp_WindowsCompareStringOrdinal
0x180050190  cmp     dword ptr [rsp+88h+newString], 0
0x180050195  jnz     short loc_180050147
0x180050197  mov     rcx, [rsp+88h]; this
0x18005019f  mov     r9d, 80070057h; char *
0x1800501a5  lea     r8, aPcshellTwinuiV_54; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1800501ac  mov     edx, 83Ah; void *
0x1800501b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800501b6  mov     rdx, [rsp+88h+arg_0]
0x1800501be  mov     rcx, [rdx+198h]
0x1800501c5  lea     rax, [rcx+1]
0x1800501c9  mov     [rdx+198h], rax
0x1800501d0  mov     rax, [rsp+88h+var_48]
0x1800501d5  mov     [rax+20h], rcx
0x1800501d9  mov     rcx, [r13+8]
0x1800501dd  cmp     rcx, [r13+10h]
0x1800501e1  jnz     loc_180050276
0x1800501e7  lea     r8, [rsp+88h+var_48]
0x1800501ec  mov     rdx, rcx
0x1800501ef  mov     rcx, r13
0x1800501f2  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UViewEventRegistration@@@std@@@?$vector@V?$shared_ptr@UViewEventRegistration@@@std@@V?$allocator@V?$shared_ptr@UViewEventRegistration@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UViewEventRegistration@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<ViewEventRegistration>>::_Emplace_reallocate<std::shared_ptr<ViewEventRegistration> const &>(std::shared_ptr<ViewEventRegistration> * const,std::shared_ptr<ViewEventRegistration> const &)
0x1800501f7  mov     rax, [rsp+88h+var_48]
0x1800501fc  mov     rcx, [rax+20h]
0x180050200  mov     rax, [rsp+88h+arg_28]
0x180050208  mov     [rax], rcx
0x18005020b  xor     edx, edx; length
0x18005020d  mov     rcx, [rsp+88h+string]; string
0x180050215  call    cs:__imp_WindowsGetStringRawBuffer
0x18005021b  mov     [rsp+88h+newString], rax
0x180050220  xor     edx, edx; length
0x180050222  mov     rcx, [rsp+88h+arg_10]; string
0x18005022a  call    cs:__imp_WindowsGetStringRawBuffer
0x180050230  mov     [rsp+88h+var_50], rax
0x180050235  lea     rdx, [rsp+88h+newString]
0x18005023a  lea     rcx, [rsp+88h+var_50]
0x18005023f  call    ??$WindowEventDispatcher_RegisterForViewEventsWithOptions@PEBGPEBG@ViewManagerInteropTraceLogging@@SAX$$QEAPEBG0@Z; ViewManagerInteropTraceLogging::WindowEventDispatcher_RegisterForViewEventsWithOptions<ushort const *,ushort const *>(ushort const * &&,ushort const * &&)
0x180050244  nop
0x180050245  test    rbx, rbx
0x180050248  jnz     short loc_18005026B
0x18005024a  mov     rcx, [rsp+88h+var_40]; this
0x18005024f  test    rcx, rcx
0x180050252  jz      short loc_180050259
0x180050254  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180050259  xor     eax, eax
0x18005025b  add     rsp, 50h
0x18005025f  pop     r15
0x180050261  pop     r14
0x180050263  pop     r13
0x180050265  pop     r12
0x180050267  pop     rdi
0x180050268  pop     rsi
0x180050269  pop     rbx
0x18005026a  retn
0x18005026b  mov     rcx, rbx; SRWLock
0x18005026e  call    cs:__imp_ReleaseSRWLockExclusive
0x180050274  jmp     short loc_18005024A
0x180050276  lea     rdx, [rsp+88h+var_48]
0x18005027b  call    ??0?$shared_ptr@VInputAppViewCoodinatorHandler@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<InputAppViewCoodinatorHandler>::shared_ptr<InputAppViewCoodinatorHandler>(std::shared_ptr<InputAppViewCoodinatorHandler> const &)
0x180050280  add     qword ptr [r13+8], 10h
0x180050285  jmp     loc_1800501F7
0x18005028a  mov     r9d, edi; char *
0x18005028d  lea     r8, aPcshellTwinuiV_54; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x180050294  mov     edx, 81Ah; void *
0x180050299  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005029e  mov     r9d, ebx; char *
0x1800502a1  lea     r8, aPcshellTwinuiV_54; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1800502a8  mov     edx, 81Bh; void *
0x1800502ad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800502b2  mov     r9d, edi; char *
0x1800502b5  lea     r8, aPcshellTwinuiV_54; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1800502bc  mov     edx, 81Dh; void *
0x1800502c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800502c6  lea     r8, aPcshellTwinuiV_54; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1800502cd  mov     edx, 819h; void *
0x1800502d2  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800502d8  mov     eax, dword ptr [rsp+88h+newString]
0x1800502dc  jmp     loc_18005025B
```
