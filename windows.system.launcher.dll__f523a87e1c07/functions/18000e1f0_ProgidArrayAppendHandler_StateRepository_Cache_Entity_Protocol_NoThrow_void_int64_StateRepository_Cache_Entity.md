# ProgidArrayAppendHandler<StateRepository::Cache::Entity::Protocol_NoThrow>(void *,__int64,StateRepository::Cache::Entity::Protocol_NoThrow &)

- ea: `0x18000e1f0`
- end: `0x18000e4b8`
- name: `??$ProgidArrayAppendHandler@VProtocol_NoThrow@Entity@Cache@StateRepository@@@@YAJPEAX_JAEAVProtocol_NoThrow@Entity@Cache@StateRepository@@@Z`
- size: `712`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014bd0`

## callees

- `0x18000e1f0`
- `0x18000e4c0`
- `0x180010c04`
- `0x180023044`
- `0x1800596d8`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e343`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e497`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e343`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e497`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000e2dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000e2dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e2ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e2ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e285`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e402`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e427`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e44f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e285`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e402`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e427`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e44f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e36a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e36a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ProgidArrayAppendHandler<StateRepository::Cache::Entity::Protocol_NoThrow>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const WCHAR *v5; // rsi
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rbx
  HRESULT v8; // ebx
  UINT32 v10; // edx
  const WCHAR *v11; // rcx
  const WCHAR *StringRawBuffer; // rbx
  int v13; // eax
  __int64 v14; // rsi
  __int64 v15; // r15
  bool v16; // bl
  unsigned int v17; // eax
  HRESULT v18; // eax
  wil::details::in1diag3 *v19; // rcx
  int v20; // edx
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // [rsp+20h] [rbp-58h] BYREF
  HSTRING string; // [rsp+28h] [rbp-50h] BYREF
  _QWORD v25[2]; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-38h] BYREF
  HSTRING v27; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v25[1] = a1;
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  string = 0;
  v5 = *(const WCHAR **)(a3 + 24);
  v6 = -1;
  if ( v5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v5[v7] );
    if ( v7 > 0xFFFFFFFF )
    {
      v8 = -2147024362;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x682,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v8,
        v23);
      WindowsDeleteString(string);
      string = 0;
      if ( a1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
      return (unsigned int)v8;
    }
    WindowsDeleteString(0);
    v10 = v7;
    v11 = v5;
  }
  else
  {
    WindowsDeleteString(0);
    v10 = 0;
    v11 = &LocaleName;
  }
  string = 0;
  v8 = WindowsCreateString(v11, v10, &string);
  if ( v8 < 0 )
    goto LABEL_8;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v25[0] = 0;
  v13 = Microsoft::WRL::Details::MakeAndInitialize<DynamicProgIdHelpers::Details::DynamicProgIdManagerWrapper,Windows::Internal::PlatformExtensions::FileAssociations::IDynamicProgIdManager,>(v25);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\sharedstoragesources\\DynamicProgIdHelpers.h",
      (const char *)(unsigned int)v13,
      v23);
  v14 = v25[0];
  if ( v25[0] )
  {
    LOBYTE(v23) = 0;
    v15 = *(_QWORD *)v25[0];
    v27 = 0;
    do
      ++v6;
    while ( StringRawBuffer[v6] );
    if ( v6 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    v17 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v6);
    if ( (unsigned int)v6 >= v17 )
      LODWORD(v6) = v17 - 1;
    v18 = WindowsCreateStringReference(StringRawBuffer, v6, &hstringHeader, &v27);
    if ( v18 < 0 )
    {
      RaiseException(v18, 1u, 0, 0);
    }
    else
    {
      LODWORD(StringRawBuffer) = (*(__int64 (__fastcall **)(__int64, HSTRING, int *))(v15 + 48))(v14, v27, &v23);
      v19 = retaddr;
      if ( (int)StringRawBuffer >= 0 )
      {
LABEL_25:
        if ( (int)StringRawBuffer < 0 )
          v20 = 1;
        else
          v20 = (unsigned __int8)v23;
        v16 = v20 != 0;
        v14 = v25[0];
        goto LABEL_28;
      }
    }
    wil::details::in1diag3::_Log_Hr(
      v19,
      (void *)0xBD,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\sharedstoragesources\\DynamicProgIdHelpers.h",
      (const char *)(unsigned int)StringRawBuffer,
      v23);
    goto LABEL_25;
  }
  v16 = 1;
LABEL_28:
  if ( v14 )
  {
    v25[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  if ( v16
    && (v21 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)a1 + 104LL))(a1, string), v22 = v21, v21 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x685,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v21,
      v23);
    WindowsDeleteString(string);
    string = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
    return v22;
  }
  else
  {
    WindowsDeleteString(string);
    string = 0;
    if ( a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
    return 0;
  }
}

```

## disassembly

```asm
0x18000e1f0  push    rbp
0x18000e1f2  push    rbx
0x18000e1f3  push    rsi
0x18000e1f4  push    rdi
0x18000e1f5  push    r12
0x18000e1f7  push    r13
0x18000e1f9  push    r14
0x18000e1fb  push    r15
0x18000e1fd  mov     rbp, rsp
0x18000e200  sub     rsp, 78h
0x18000e204  mov     rax, cs:__security_cookie
0x18000e20b  xor     rax, rsp
0x18000e20e  mov     [rbp+var_18], rax
0x18000e212  mov     rsi, r8
0x18000e215  mov     r14, rcx
0x18000e218  mov     [rbp+var_40], rcx
0x18000e21c  test    rcx, rcx
0x18000e21f  jz      short loc_18000E22E
0x18000e221  mov     rax, [rcx]
0x18000e224  mov     rax, [rax+8]
0x18000e228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e22d  nop
0x18000e22e  xor     r12d, r12d
0x18000e231  mov     [rbp+string], r12
0x18000e235  mov     rsi, [rsi+18h]
0x18000e239  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000e240  mov     r13d, 0FFFFFFFFh
0x18000e246  test    rsi, rsi
0x18000e249  jz      short loc_18000E2C3
0x18000e24b  mov     rbx, rdi
0x18000e24e  xchg    ax, ax
0x18000e250  inc     rbx
0x18000e253  cmp     word ptr [rsi+rbx*2], 0
0x18000e258  jnz     short loc_18000E250
0x18000e25a  cmp     rbx, r13
0x18000e25d  jbe     loc_18000E44D
0x18000e263  mov     ebx, 80070216h
0x18000e268  mov     rcx, [rbp+40h]; this
0x18000e26c  mov     r9d, ebx; char *
0x18000e26f  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18000e276  mov     edx, 682h; void *
0x18000e27b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e280  nop
0x18000e281  mov     rcx, [rbp+string]; string
0x18000e285  call    cs:__imp_WindowsDeleteString
0x18000e28b  mov     [rbp+string], r12
0x18000e28f  test    r14, r14
0x18000e292  jz      short loc_18000E2A4
0x18000e294  mov     rax, [r14]
0x18000e297  mov     rcx, r14
0x18000e29a  mov     rax, [rax+10h]
0x18000e29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2a3  nop
0x18000e2a4  mov     eax, ebx
0x18000e2a6  mov     rcx, [rbp+var_18]
0x18000e2aa  xor     rcx, rsp; StackCookie
0x18000e2ad  call    __security_check_cookie
0x18000e2b2  add     rsp, 78h
0x18000e2b6  pop     r15
0x18000e2b8  pop     r14
0x18000e2ba  pop     r13
0x18000e2bc  pop     r12
0x18000e2be  pop     rdi
0x18000e2bf  pop     rsi
0x18000e2c0  pop     rbx
0x18000e2c1  pop     rbp
0x18000e2c2  retn
0x18000e2c3  xor     ecx, ecx; string
0x18000e2c5  call    cs:__imp_WindowsDeleteString
0x18000e2cb  xor     edx, edx; length
0x18000e2cd  lea     rcx, LocaleName; sourceString
0x18000e2d4  mov     [rbp+string], r12
0x18000e2d8  lea     r8, [rbp+string]; string
0x18000e2dc  call    cs:__imp_WindowsCreateString
0x18000e2e2  mov     ebx, eax
0x18000e2e4  test    eax, eax
0x18000e2e6  js      short loc_18000E268
0x18000e2e8  xor     edx, edx; length
0x18000e2ea  mov     rcx, [rbp+string]; string
0x18000e2ee  call    cs:__imp_WindowsGetStringRawBuffer
0x18000e2f4  mov     rbx, rax
0x18000e2f7  mov     [rbp+var_48], r12
0x18000e2fb  lea     rcx, [rbp+var_48]
0x18000e2ff  call    ??$MakeAndInitialize@VDynamicProgIdManagerWrapper@Details@DynamicProgIdHelpers@@UIDynamicProgIdManager@FileAssociations@PlatformExtensions@Internal@Windows@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIDynamicProgIdManager@FileAssociations@PlatformExtensions@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<DynamicProgIdHelpers::Details::DynamicProgIdManagerWrapper,Windows::Internal::PlatformExtensions::FileAssociations::IDynamicProgIdManager,>(Windows::Internal::PlatformExtensions::FileAssociations::IDynamicProgIdManager * *)
0x18000e304  mov     rcx, [rbp+40h]; this
0x18000e308  test    eax, eax
0x18000e30a  js      loc_18000E469
0x18000e310  mov     rsi, [rbp+var_48]
0x18000e314  test    rsi, rsi
0x18000e317  jz      short loc_18000E34A
0x18000e319  mov     byte ptr [rbp+var_58], 0
0x18000e31d  mov     r15, [rsi]
0x18000e320  mov     [rbp+var_20], r12
0x18000e324  inc     rdi
0x18000e327  cmp     word ptr [rbx+rdi*2], 0
0x18000e32c  jnz     short loc_18000E324
0x18000e32e  cmp     rdi, r13
0x18000e331  jbe     short loc_18000E34E
0x18000e333  xor     r9d, r9d; lpArguments
0x18000e336  xor     r8d, r8d; nNumberOfArguments
0x18000e339  mov     edx, 1; dwExceptionFlags
0x18000e33e  mov     ecx, 80070216h; dwExceptionCode
0x18000e343  call    cs:__imp_RaiseException
0x18000e349  int     3; Trap to Debugger
0x18000e34a  mov     bl, 1
0x18000e34c  jmp     short loc_18000E3AF
0x18000e34e  mov     ecx, edi; unsigned int
0x18000e350  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000e355  cmp     edi, eax
0x18000e357  jnb     loc_18000E482
0x18000e35d  lea     r9, [rbp+var_20]; string
0x18000e361  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000e365  mov     edx, edi; length
0x18000e367  mov     rcx, rbx; sourceString
0x18000e36a  call    cs:__imp_WindowsCreateStringReference
0x18000e370  test    eax, eax
0x18000e372  js      loc_18000E48A
0x18000e378  lea     r8, [rbp+var_58]
0x18000e37c  mov     rdx, [rbp+var_20]
0x18000e380  mov     rcx, rsi
0x18000e383  mov     rax, [r15+30h]
0x18000e387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e38c  mov     ebx, eax
0x18000e38e  mov     rcx, [rbp+40h]
0x18000e392  test    eax, eax
0x18000e394  js      loc_18000E49E
0x18000e39a  test    ebx, ebx
0x18000e39c  js      loc_18000E45F
0x18000e3a2  movzx   edx, byte ptr [rbp+var_58]
0x18000e3a6  test    edx, edx
0x18000e3a8  setnz   bl
0x18000e3ab  mov     rsi, [rbp+var_48]
0x18000e3af  test    rsi, rsi
0x18000e3b2  jz      short loc_18000E3C8
0x18000e3b4  mov     [rbp+var_48], r12
0x18000e3b8  mov     rax, [rsi]
0x18000e3bb  mov     rcx, rsi
0x18000e3be  mov     rax, [rax+10h]
0x18000e3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3c7  nop
0x18000e3c8  test    bl, bl
0x18000e3ca  jz      short loc_18000E423
0x18000e3cc  mov     rax, [r14]
0x18000e3cf  mov     rdx, [rbp+string]
0x18000e3d3  mov     rcx, r14
0x18000e3d6  mov     rax, [rax+68h]
0x18000e3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3df  mov     ebx, eax
0x18000e3e1  test    eax, eax
0x18000e3e3  jns     short loc_18000E423
0x18000e3e5  mov     rcx, [rbp+40h]; this
0x18000e3e9  mov     r9d, eax; char *
0x18000e3ec  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18000e3f3  mov     edx, 685h; void *
0x18000e3f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e3fd  nop
0x18000e3fe  mov     rcx, [rbp+string]; string
0x18000e402  call    cs:__imp_WindowsDeleteString
0x18000e408  mov     [rbp+string], r12
0x18000e40c  mov     rax, [r14]
0x18000e40f  mov     rcx, r14
0x18000e412  mov     rax, [rax+10h]
0x18000e416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e41b  nop
0x18000e41c  mov     eax, ebx
0x18000e41e  jmp     loc_18000E2A6
0x18000e423  mov     rcx, [rbp+string]; string
0x18000e427  call    cs:__imp_WindowsDeleteString
0x18000e42d  mov     [rbp+string], r12
0x18000e431  test    r14, r14
0x18000e434  jz      short loc_18000E446
0x18000e436  mov     rax, [r14]
0x18000e439  mov     rcx, r14
0x18000e43c  mov     rax, [rax+10h]
0x18000e440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e445  nop
0x18000e446  xor     eax, eax
0x18000e448  jmp     loc_18000E2A6
0x18000e44d  xor     ecx, ecx; string
0x18000e44f  call    cs:__imp_WindowsDeleteString
0x18000e455  mov     edx, ebx
0x18000e457  mov     rcx, rsi
0x18000e45a  jmp     loc_18000E2D4
0x18000e45f  mov     edx, 1
0x18000e464  jmp     loc_18000E3A6
0x18000e469  mov     r9d, eax; char *
0x18000e46c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18000e473  mov     edx, 0B4h; void *
0x18000e478  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e47d  jmp     loc_18000E310
0x18000e482  lea     edi, [rax-1]
0x18000e485  jmp     loc_18000E35D
0x18000e48a  xor     r9d, r9d; lpArguments
0x18000e48d  xor     r8d, r8d; nNumberOfArguments
0x18000e490  mov     edx, 1; dwExceptionFlags
0x18000e495  mov     ecx, eax; dwExceptionCode
0x18000e497  call    cs:__imp_RaiseException
0x18000e49d  nop
0x18000e49e  mov     r9d, ebx; char *
0x18000e4a1  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18000e4a8  mov     edx, 0BDh; void *
0x18000e4ad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e4b2  jmp     loc_18000E39A
```
