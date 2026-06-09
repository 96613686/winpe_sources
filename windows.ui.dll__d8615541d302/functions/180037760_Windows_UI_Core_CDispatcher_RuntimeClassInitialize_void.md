# Windows::UI::Core::CDispatcher::RuntimeClassInitialize(void)

- ea: `0x180037760`
- end: `0x1800378fd`
- name: `?RuntimeClassInitialize@CDispatcher@Core@UI@Windows@@UEAAJXZ`
- size: `413`
- prototype: `__int64 __fastcall(Windows::UI::Core::CDispatcher *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180012858`
- `0x180037760`
- `0x180037904`
- `0x1800379f0`
- `0x180050360`
- `0x18008ace0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037796`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800378db`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037796`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800378db`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037773`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037773`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003784f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003784f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003788b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003788b`
- `combase!__imp_CoSetMessageDispatcher` at `0x180037868`
- `combase!__imp_CoSetMessageDispatcher` at `0x180037868`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x1800377bb`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x1800377d2`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x1800377bb`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x1800377d2`

## string_xrefs

- `0x1800378b7`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\dispatcher.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CDispatcher::RuntimeClassInitialize(Windows::UI::Core::CDispatcher *this)
{
  int Error; // edi
  HANDLE EventW; // rax
  const char *v5; // rax
  HANDLE v6; // rax
  int v7; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( TlsGetValue(Windows::UI::Core::CDispatcher::s_tlsIndex) )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\dispatcher.cpp",
      (const char *)0x8001010ELL,
      v7);
  Error = 0;
  Windows::UI::Core::CDispatcher::CreateDispatcherQueue(this);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 97) = EventW;
  if ( EventW || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    if ( !*((_DWORD *)this + 30) )
    {
      *((_DWORD *)this + 30) = GetCurrentThreadId();
      CoSetMessageDispatcher(((unsigned __int64)this + 40) & -(__int64)(this != 0));
    }
  }
  *((_BYTE *)this + 200) = (unsigned int)QuirkIsEnabled(0x40000) == 1;
  if ( (unsigned int)QuirkIsEnabled(262145) == 1 )
  {
    v6 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 27) = v6;
    if ( !v6 )
      Error = ResultFromKnownLastError();
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v5 = "main view dispatcher";
    if ( !*((_BYTE *)this + 212) )
      v5 = "secondary view or CoreInput dispatcher";
    WPP_SF_qDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *((unsigned __int8 *)this + 200),
      (unsigned int)"secondary view or CoreInput dispatcher",
      (_DWORD)this,
      *((_DWORD *)this + 30),
      (__int64)v5,
      *((_BYTE *)this + 200));
  }
  if ( Error >= 0 )
  {
    (*(void (__fastcall **)(Windows::UI::Core::CDispatcher *))(*(_QWORD *)this + 8LL))(this);
    TlsSetValue(Windows::UI::Core::CDispatcher::s_tlsIndex, this);
    Windows::UI::Core::CDispatcher::RegisterThreadExitCallback(this);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180037760  mov     [rsp+arg_0], rbx
0x180037765  push    rdi
0x180037766  sub     rsp, 40h
0x18003776a  mov     rbx, rcx
0x18003776d  mov     ecx, cs:?s_tlsIndex@CDispatcher@Core@UI@Windows@@0KA; dwTlsIndex
0x180037773  call    cs:__imp_TlsGetValue
0x180037779  test    rax, rax
0x18003777c  jnz     loc_1800378B2
0x180037782  mov     rcx, rbx; this
0x180037785  xor     edi, edi
0x180037787  call    ?CreateDispatcherQueue@CDispatcher@Core@UI@Windows@@AEAAXXZ; Windows::UI::Core::CDispatcher::CreateDispatcherQueue(void)
0x18003778c  xor     r9d, r9d; lpName
0x18003778f  xor     r8d, r8d; bInitialState
0x180037792  xor     edx, edx; bManualReset
0x180037794  xor     ecx, ecx; lpEventAttributes
0x180037796  call    cs:__imp_CreateEventW
0x18003779c  mov     [rbx+308h], rax
0x1800377a3  test    rax, rax
0x1800377a6  jz      loc_18003789E
0x1800377ac  cmp     dword ptr [rbx+78h], 0
0x1800377b0  jz      loc_18003784F
0x1800377b6  mov     ecx, 40000h
0x1800377bb  call    cs:__imp_QuirkIsEnabled
0x1800377c1  cmp     eax, 1
0x1800377c4  mov     ecx, 40001h
0x1800377c9  setz    al
0x1800377cc  mov     [rbx+0C8h], al
0x1800377d2  call    cs:__imp_QuirkIsEnabled
0x1800377d8  cmp     eax, 1
0x1800377db  jz      loc_1800378CF
0x1800377e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800377e8  lea     rax, WPP_GLOBAL_Control
0x1800377ef  cmp     rcx, rax
0x1800377f2  jnz     short loc_180037805
0x1800377f4  test    edi, edi
0x1800377f6  jns     short loc_180037873
0x1800377f8  mov     rbx, [rsp+48h+arg_0]
0x1800377fd  mov     eax, edi
0x1800377ff  add     rsp, 40h
0x180037803  pop     rdi
0x180037804  retn
0x180037805  test    byte ptr [rcx+1Ch], 4
0x180037809  jz      short loc_1800377F4
0x18003780b  cmp     byte ptr [rcx+19h], 4
0x18003780f  jb      short loc_1800377F4
0x180037811  cmp     byte ptr [rbx+0D4h], 0
0x180037818  lea     r8, aSecondaryViewO_0; "secondary view or CoreInput dispatcher"
0x18003781f  movzx   edx, byte ptr [rbx+0C8h]
0x180037826  lea     rax, aMainViewDispat; "main view dispatcher"
0x18003782d  mov     rcx, [rcx+10h]
0x180037831  cmovz   rax, r8
0x180037835  mov     [rsp+48h+var_18], edx
0x180037839  mov     r9, rbx
0x18003783c  mov     [rsp+48h+var_20], rax
0x180037841  mov     eax, [rbx+78h]
0x180037844  mov     [rsp+48h+var_28], eax
0x180037848  call    WPP_SF_qDsd
0x18003784d  jmp     short loc_1800377F4
0x18003784f  call    cs:__imp_GetCurrentThreadId
0x180037855  lea     rdx, [rbx+28h]
0x180037859  mov     rcx, rbx
0x18003785c  neg     rcx
0x18003785f  mov     [rbx+78h], eax
0x180037862  sbb     rcx, rcx
0x180037865  and     rcx, rdx
0x180037868  call    cs:__imp_CoSetMessageDispatcher
0x18003786e  jmp     loc_1800377B6
0x180037873  mov     rax, [rbx]
0x180037876  mov     rcx, rbx
0x180037879  mov     rax, [rax+8]
0x18003787d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037882  mov     ecx, cs:?s_tlsIndex@CDispatcher@Core@UI@Windows@@0KA; dwTlsIndex
0x180037888  mov     rdx, rbx; lpTlsValue
0x18003788b  call    cs:__imp_TlsSetValue
0x180037891  mov     rcx, rbx; pv
0x180037894  call    ?RegisterThreadExitCallback@CDispatcher@Core@UI@Windows@@AEAAXXZ; Windows::UI::Core::CDispatcher::RegisterThreadExitCallback(void)
0x180037899  jmp     loc_1800377F8
0x18003789e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800378a3  mov     edi, eax
0x1800378a5  test    eax, eax
0x1800378a7  js      loc_1800377B6
0x1800378ad  jmp     loc_1800377AC
0x1800378b2  mov     rcx, [rsp+48h]; this
0x1800378b7  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800378be  mov     r9d, 8001010Eh; char *
0x1800378c4  mov     edx, 40h ; '@'; void *
0x1800378c9  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800378cf  xor     r9d, r9d; lpName
0x1800378d2  xor     r8d, r8d; bInitialState
0x1800378d5  xor     ecx, ecx; lpEventAttributes
0x1800378d7  lea     edx, [r9+1]; bManualReset
0x1800378db  call    cs:__imp_CreateEventW
0x1800378e1  mov     [rbx+0D8h], rax
0x1800378e8  test    rax, rax
0x1800378eb  jnz     loc_1800377E1
0x1800378f1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800378f6  mov     edi, eax
0x1800378f8  jmp     loc_1800377E1
```
