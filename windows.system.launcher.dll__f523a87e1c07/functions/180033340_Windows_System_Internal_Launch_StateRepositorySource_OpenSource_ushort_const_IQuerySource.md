# Windows::System::Internal::Launch::StateRepositorySource::OpenSource(ushort const *,IQuerySource * *)

- ea: `0x180033340`
- end: `0x180033568`
- name: `?OpenSource@StateRepositorySource@Launch@Internal@System@Windows@@UEAAJPEBGPEAPEAUIQuerySource@@@Z`
- size: `552`
- prototype: `int(Windows::System::Internal::Launch::StateRepositorySource *__hidden this, const unsigned __int16 *, struct IQuerySource **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180010c04`
- `0x180032ecc`
- `0x180033340`
- `0x180033570`
- `0x180033a5c`
- `0x1800aae64`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180033394`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800333a9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800333be`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180033492`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800334ab`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180033394`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800333a9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800333be`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180033492`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800334ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800333dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800334d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800333dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800334d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003344e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003344e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033516`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003341c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003341c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003350e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003355d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003350e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003355d`

## string_xrefs

- `0x180033528`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800334a1`: `command`

## pseudocode

```c
__int64 __fastcall Windows::System::Internal::Launch::StateRepositorySource::OpenSource(
        Windows::System::Internal::Launch::StateRepositorySource *this,
        const unsigned __int16 *a2,
        struct IQuerySource **a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  PCWSTR StringRawBuffer; // rdx
  const char *v11; // r9
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // r15
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rdi
  PCWSTR v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-48h]
  int v22; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a3 = 0;
  if ( !a2 )
  {
    v6 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase>>(
           (__int64)this - 8,
           &GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac,
           a3);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 433;
LABEL_4:
      v9 = (unsigned int)v6;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
        (const char *)v9,
        v21);
LABEL_17:
      WindowsDeleteString(0);
      return v7;
    }
    goto LABEL_26;
  }
  if ( StrStrIW(a2, L"application") != a2
    && StrStrIW(a2, L"defaultIcon") != a2
    && StrStrIW(a2, L"shell") != a2
    && StrStrIW(a2, L"Open") != a2
    && StrStrIW(a2, L"command") != a2 )
  {
    return 2147942402LL;
  }
  if ( !*((_QWORD *)this + 12) )
  {
    v6 = Windows::System::Internal::Launch::StateRepositorySource::Clone(
           (Windows::System::Internal::Launch::StateRepositorySource *)((char *)this - 8),
           a2,
           a3);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 448;
      goto LABEL_4;
    }
    goto LABEL_26;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 12), 0);
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  v13 = -1;
  do
    ++v13;
  while ( StringRawBuffer[v13] );
  v14 = v13 + v12 + 2;
  if ( v14 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v11);
  v15 = (unsigned __int16 *)CoTaskMemAlloc(2 * v14 + 2);
  v16 = v15;
  if ( !v15 )
  {
    v7 = -2147024882;
    v8 = 441;
    v9 = 2147942414LL;
    goto LABEL_16;
  }
  *v15 = 0;
  v15[v14] = 0;
  v18 = WindowsGetStringRawBuffer(*((HSTRING *)this + 12), 0);
  v22 = (int)a2;
  v19 = StringCchPrintfW(v16, v14, L"%ws\\%ws", v18);
  v7 = v19;
  if ( v19 < 0 )
  {
    v20 = 443;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
      (const char *)(unsigned int)v19,
      v22);
    CoTaskMemFree(v16);
    goto LABEL_17;
  }
  v19 = Windows::System::Internal::Launch::StateRepositorySource::Clone(
          (Windows::System::Internal::Launch::StateRepositorySource *)((char *)this - 8),
          v16,
          a3);
  v7 = v19;
  if ( v19 < 0 )
  {
    v20 = 444;
    goto LABEL_30;
  }
  CoTaskMemFree(v16);
LABEL_26:
  WindowsDeleteString(0);
  return 0;
}

```

## disassembly

```asm
0x180033340  push    rbx
0x180033342  push    rbp
0x180033343  push    rsi
0x180033344  push    rdi
0x180033345  push    r12
0x180033347  push    r14
0x180033349  push    r15
0x18003334b  sub     rsp, 30h
0x18003334f  xor     r12d, r12d
0x180033352  mov     rsi, r8
0x180033355  mov     [r8], r12
0x180033358  mov     rbx, rdx
0x18003335b  mov     r14, rcx
0x18003335e  test    rdx, rdx
0x180033361  jnz     short loc_18003338A
0x180033363  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180033367  lea     rdx, _GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac
0x18003336e  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIQuerySource@@UIObjectWithRegistryKey@@UIPropertyBag@@UIObjectWithExtensionInfo@Launch@Internal@System@Windows@@UIAssociationQuerySource@FileAssociations@Shell@9Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIQuerySource@@UIObjectWithRegistryKey@@UIPropertyBag@@UIObjectWithExtensionInfo@Launch@Internal@System@Windows@@UIAssociationQuerySource@FileAssociations@Shell@9Windows@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180033373  mov     ebx, eax
0x180033375  test    eax, eax
0x180033377  jns     loc_180033514
0x18003337d  mov     edx, 1B1h
0x180033382  mov     r9d, eax
0x180033385  jmp     loc_18003343B
0x18003338a  lea     rdx, pszSrch; "application"
0x180033391  mov     rcx, rbx; pszFirst
0x180033394  call    cs:__imp_StrStrIW
0x18003339a  cmp     rax, rbx
0x18003339d  jz      short loc_1800333CD
0x18003339f  lea     rdx, aDefaulticon; "defaultIcon"
0x1800333a6  mov     rcx, rbx; pszFirst
0x1800333a9  call    cs:__imp_StrStrIW
0x1800333af  cmp     rax, rbx
0x1800333b2  jz      short loc_1800333CD
0x1800333b4  lea     rdx, aShell_0; "shell"
0x1800333bb  mov     rcx, rbx; pszFirst
0x1800333be  call    cs:__imp_StrStrIW
0x1800333c4  cmp     rax, rbx
0x1800333c7  jnz     loc_180033488
0x1800333cd  cmp     [r14+60h], r12
0x1800333d1  jz      loc_180033465
0x1800333d7  mov     rcx, [r14+60h]; string
0x1800333db  xor     edx, edx; length
0x1800333dd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800333e3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800333e7  mov     rdx, rax
0x1800333ea  mov     rcx, r8
0x1800333ed  inc     rcx
0x1800333f0  cmp     [rbx+rcx*2], r12w
0x1800333f5  jnz     short loc_1800333ED
0x1800333f7  mov     rax, r8
0x1800333fa  inc     rax
0x1800333fd  cmp     [rdx+rax*2], r12w
0x180033402  jnz     short loc_1800333FA
0x180033404  lea     r15, [rcx+2]
0x180033408  add     r15, rax
0x18003340b  cmp     r15, r8
0x18003340e  jz      loc_180033523
0x180033414  lea     rcx, ds:2[r15*2]; cb
0x18003341c  call    cs:__imp_CoTaskMemAlloc
0x180033422  mov     rdi, rax
0x180033425  test    rax, rax
0x180033428  jnz     loc_1800334C1
0x18003342e  mov     ebx, 8007000Eh
0x180033433  mov     edx, 1B9h; void *
0x180033438  mov     r9d, ebx; char *
0x18003343b  mov     rcx, [rsp+68h]; this
0x180033440  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x180033447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003344c  xor     ecx, ecx; string
0x18003344e  call    cs:__imp_WindowsDeleteString
0x180033454  mov     eax, ebx
0x180033456  add     rsp, 30h
0x18003345a  pop     r15
0x18003345c  pop     r14
0x18003345e  pop     r12
0x180033460  pop     rdi
0x180033461  pop     rsi
0x180033462  pop     rbp
0x180033463  pop     rbx
0x180033464  retn
0x180033465  mov     r8, rsi; struct IQuerySource **
0x180033468  lea     rcx, [r14-8]; this
0x18003346c  mov     rdx, rbx; unsigned __int16 *
0x18003346f  call    ?Clone@StateRepositorySource@Launch@Internal@System@Windows@@AEAAJPEBGPEAPEAUIQuerySource@@@Z; Windows::System::Internal::Launch::StateRepositorySource::Clone(ushort const *,IQuerySource * *)
0x180033474  mov     ebx, eax
0x180033476  test    eax, eax
0x180033478  jns     loc_180033514
0x18003347e  mov     edx, 1C0h
0x180033483  jmp     loc_180033382
0x180033488  lea     rdx, aOpen; "Open"
0x18003348f  mov     rcx, rbx; pszFirst
0x180033492  call    cs:__imp_StrStrIW
0x180033498  cmp     rax, rbx
0x18003349b  jz      loc_1800333CD
0x1800334a1  lea     rdx, aCommand; "command"
0x1800334a8  mov     rcx, rbx; pszFirst
0x1800334ab  call    cs:__imp_StrStrIW
0x1800334b1  cmp     rax, rbx
0x1800334b4  jz      loc_1800333CD
0x1800334ba  mov     eax, 80070002h
0x1800334bf  jmp     short loc_180033456
0x1800334c1  mov     [rax], r12w
0x1800334c5  xor     edx, edx; length
0x1800334c7  mov     [rax+r15*2], r12w
0x1800334cc  mov     rcx, [r14+60h]; string
0x1800334d0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800334d6  lea     r8, aWsWs; "%ws\\%ws"
0x1800334dd  mov     qword ptr [rsp+68h+var_48], rbx; int
0x1800334e2  mov     r9, rax
0x1800334e5  mov     rdx, r15; unsigned __int64
0x1800334e8  mov     rcx, rdi; unsigned __int16 *
0x1800334eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800334f0  mov     ebx, eax
0x1800334f2  test    eax, eax
0x1800334f4  js      short loc_18003353A
0x1800334f6  mov     r8, rsi; struct IQuerySource **
0x1800334f9  lea     rcx, [r14-8]; this
0x1800334fd  mov     rdx, rdi; unsigned __int16 *
0x180033500  call    ?Clone@StateRepositorySource@Launch@Internal@System@Windows@@AEAAJPEBGPEAPEAUIQuerySource@@@Z; Windows::System::Internal::Launch::StateRepositorySource::Clone(ushort const *,IQuerySource * *)
0x180033505  mov     ebx, eax
0x180033507  test    eax, eax
0x180033509  js      short loc_180033541
0x18003350b  mov     rcx, rdi; pv
0x18003350e  call    cs:__imp_CoTaskMemFree
0x180033514  xor     ecx, ecx; string
0x180033516  call    cs:__imp_WindowsDeleteString
0x18003351c  xor     eax, eax
0x18003351e  jmp     loc_180033456
0x180033523  mov     rcx, [rsp+68h]; this
0x180033528  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003352f  mov     edx, 0F89h; void *
0x180033534  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003353a  mov     edx, 1BBh
0x18003353f  jmp     short loc_180033546
0x180033541  mov     edx, 1BCh; void *
0x180033546  mov     rcx, [rsp+68h]; this
0x18003354b  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x180033552  mov     r9d, eax; char *
0x180033555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003355a  mov     rcx, rdi; pv
0x18003355d  call    cs:__imp_CoTaskMemFree
0x180033563  jmp     loc_18003344C
```
