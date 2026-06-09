# CAgentProtocolTalker::GetUserPreferredLanguages(CBSTRList *)

- ea: `0x1800694cc`
- end: `0x180069768`
- name: `?GetUserPreferredLanguages@CAgentProtocolTalker@@AEAAJPEAVCBSTRList@@@Z`
- size: `668`
- prototype: `int(CAgentProtocolTalker *__hidden this, struct CBSTRList *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006a4a8`

## callees

- `0x18000def4`
- `0x180038d00`
- `0x18003b908`
- `0x1800694cc`
- `0x180076784`
- `0x18007b8a4`
- `0x18012b618`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180069650`
- `OLEAUT32!__imp_SysFreeString` at `0x1800696bc`
- `OLEAUT32!__imp_SysFreeString` at `0x180069755`
- `OLEAUT32!__imp_SysFreeString` at `0x180069650`
- `OLEAUT32!__imp_SysFreeString` at `0x1800696bc`
- `OLEAUT32!__imp_SysFreeString` at `0x180069755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006953a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006953a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006963f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800696d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006963f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800696d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180069632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180069632`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180069574`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180069574`

## string_xrefs

- `0x1800695cd`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`
- `0x180069740`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CAgentProtocolTalker::GetUserPreferredLanguages(CAgentProtocolTalker *this, struct CBSTRList *a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  HSTRING v6; // rbx
  __int64 v7; // rcx
  int ActivationFactory; // edi
  __int64 v9; // rdx
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, __int64 *); // rdi
  __int64 v12; // rcx
  unsigned int v13; // esi
  OLECHAR *v14; // rbx
  const wchar_t *StringRawBuffer; // r14
  __int64 v16; // r8
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v22; // [rsp+20h] [rbp-49h]
  BSTR bstrString[2]; // [rsp+40h] [rbp-29h] BYREF
  char v24; // [rsp+50h] [rbp-19h]
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-11h] BYREF
  HSTRING string; // [rsp+70h] [rbp+7h] BYREF
  HSTRING v27; // [rsp+78h] [rbp+Fh] BYREF
  unsigned int v28; // [rsp+80h] [rbp+17h] BYREF
  __int64 v29; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v30; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v30 = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  bstrString[1] = (BSTR)&v27;
  v24 = 1;
  CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::RemoveArraySection(a2);
  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.System.UserProfile.GlobalizationPreferences",
         0x33u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x180069767LL);
  }
  v6 = string;
  v7 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  ActivationFactory = RoGetActivationFactory(v6, &GUID_01bf4326_ed37_4e96_b0e9_c1340d1ea158, &v30);
  if ( ActivationFactory < 0 )
  {
    v9 = 1137;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ProtocolTalker.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v22);
    goto LABEL_23;
  }
  v10 = v30;
  v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 72LL);
  v12 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  ActivationFactory = v11(v10, &v29);
  if ( ActivationFactory < 0 )
  {
    v9 = 1139;
    goto LABEL_10;
  }
  if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v29 + 56LL))(v29, &v28) < 0 || (v13 = 0, !v28) )
  {
LABEL_22:
    ActivationFactory = 0;
    goto LABEL_23;
  }
  while ( (*(int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v29 + 48LL))(v29, v13, &v27) < 0 )
  {
LABEL_21:
    if ( ++v13 >= v28 )
      goto LABEL_22;
  }
  v14 = 0;
  bstrString[0] = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v27, 0);
  WindowsDeleteString(v27);
  v27 = 0;
  if ( StringRawBuffer )
  {
    SysFreeString(0);
    bstrString[0] = 0;
    v16 = -1;
    do
      ++v16;
    while ( StringRawBuffer[v16] );
    v17 = CSusBSTR::Append((CSusBSTR *)bstrString, StringRawBuffer, v16);
    v14 = bstrString[0];
    if ( v17 < 0 )
    {
LABEL_20:
      SysFreeString(v14);
      goto LABEL_21;
    }
  }
  v18 = CBSTRList::AddCopy(a2, v14);
  ActivationFactory = v18;
  if ( v18 >= 0 )
  {
    WUTrace(0, 0, 8, 5, 0, L"UserPreferredLanguage : %ws");
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x483,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ProtocolTalker.cpp",
    (const char *)(unsigned int)v18,
    v22);
  SysFreeString(v14);
LABEL_23:
  WindowsDeleteString(v27);
  v19 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v20 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800694cc  mov     [rsp-8+arg_0], rbx
0x1800694d1  mov     [rsp-8+arg_10], rsi
0x1800694d6  push    rbp
0x1800694d7  push    rdi
0x1800694d8  push    r12
0x1800694da  push    r14
0x1800694dc  push    r15
0x1800694de  lea     rbp, [rsp-37h]
0x1800694e3  sub     rsp, 0A0h
0x1800694ea  mov     rax, cs:__security_cookie
0x1800694f1  xor     rax, rsp
0x1800694f4  mov     [rbp+57h+var_28], rax
0x1800694f8  mov     r15, rdx
0x1800694fb  xor     r12d, r12d
0x1800694fe  mov     [rbp+57h+var_30], r12
0x180069502  mov     [rbp+57h+var_38], r12
0x180069506  mov     [rbp+57h+var_40], r12d
0x18006950a  mov     [rbp+57h+var_48], r12
0x18006950e  lea     rax, [rbp+57h+var_48]
0x180069512  mov     [rbp+57h+var_78], rax
0x180069516  mov     [rbp+57h+var_70], 1
0x18006951a  mov     rcx, rdx
0x18006951d  call    ?RemoveArraySection@?$CSusArrayList@PEA_WVCSusArrayBSTRListItemOpDelete@@@@IEAAXKKH@Z; CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::RemoveArraySection(ulong,ulong,int)
0x180069522  mov     [rbp+57h+string], r12
0x180069526  lea     r9, [rbp+57h+string]; string
0x18006952a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006952e  lea     edx, [r12+33h]; length
0x180069533  lea     rcx, ?RuntimeClass_Windows_System_UserProfile_GlobalizationPreferences@@3QB_WB; "Windows.System.UserProfile.Globalizatio"...
0x18006953a  call    cs:__imp_WindowsCreateStringReference
0x180069540  test    eax, eax
0x180069542  js      loc_180069760
0x180069548  mov     rbx, [rbp+57h+string]
0x18006954c  mov     rcx, [rbp+57h+var_30]
0x180069550  test    rcx, rcx
0x180069553  jz      short loc_180069566
0x180069555  mov     [rbp+57h+var_30], r12
0x180069559  mov     rax, [rcx]
0x18006955c  mov     rax, [rax+10h]
0x180069560  call    _guard_dispatch_icall
0x180069565  nop
0x180069566  lea     r8, [rbp+57h+var_30]
0x18006956a  lea     rdx, _GUID_01bf4326_ed37_4e96_b0e9_c1340d1ea158
0x180069571  mov     rcx, rbx
0x180069574  call    cs:__imp_RoGetActivationFactory
0x18006957a  mov     edi, eax
0x18006957c  test    eax, eax
0x18006957e  jns     short loc_180069587
0x180069580  mov     edx, 471h
0x180069585  jmp     short loc_1800695C6
0x180069587  mov     rbx, [rbp+57h+var_30]
0x18006958b  mov     rax, [rbx]
0x18006958e  mov     rdi, [rax+48h]
0x180069592  mov     rcx, [rbp+57h+var_38]
0x180069596  test    rcx, rcx
0x180069599  jz      short loc_1800695AC
0x18006959b  mov     [rbp+57h+var_38], r12
0x18006959f  mov     rdx, [rcx]
0x1800695a2  mov     rax, [rdx+10h]
0x1800695a6  call    _guard_dispatch_icall
0x1800695ab  nop
0x1800695ac  lea     rdx, [rbp+57h+var_38]
0x1800695b0  mov     rcx, rbx
0x1800695b3  mov     rax, rdi
0x1800695b6  call    _guard_dispatch_icall
0x1800695bb  mov     edi, eax
0x1800695bd  test    eax, eax
0x1800695bf  jns     short loc_1800695DE
0x1800695c1  mov     edx, 473h; void *
0x1800695c6  mov     rcx, [rbp+5Fh]; this
0x1800695ca  mov     r9d, edi; char *
0x1800695cd  lea     r8, aCW1SSrcClientE_67; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800695d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800695d9  jmp     loc_1800696D0
0x1800695de  mov     rcx, [rbp+57h+var_38]
0x1800695e2  mov     rax, [rcx]
0x1800695e5  lea     rdx, [rbp+57h+var_40]
0x1800695e9  mov     rax, [rax+38h]
0x1800695ed  call    _guard_dispatch_icall
0x1800695f2  test    eax, eax
0x1800695f4  js      loc_1800696CD
0x1800695fa  mov     esi, r12d
0x1800695fd  cmp     [rbp+57h+var_40], r12d
0x180069601  jbe     loc_1800696CD
0x180069607  mov     rcx, [rbp+57h+var_38]
0x18006960b  mov     rax, [rcx]
0x18006960e  lea     r8, [rbp+57h+var_48]
0x180069612  mov     edx, esi
0x180069614  mov     rax, [rax+30h]
0x180069618  call    _guard_dispatch_icall
0x18006961d  test    eax, eax
0x18006961f  js      loc_1800696C2
0x180069625  mov     rbx, r12
0x180069628  mov     [rbp+57h+bstrString], rbx
0x18006962c  xor     edx, edx; length
0x18006962e  mov     rcx, [rbp+57h+var_48]; string
0x180069632  call    cs:__imp_WindowsGetStringRawBuffer
0x180069638  mov     r14, rax
0x18006963b  mov     rcx, [rbp+57h+var_48]; string
0x18006963f  call    cs:__imp_WindowsDeleteString
0x180069645  mov     [rbp+57h+var_48], r12
0x180069649  test    r14, r14
0x18006964c  jz      short loc_18006967C
0x18006964e  xor     ecx, ecx; bstrString
0x180069650  call    cs:__imp_SysFreeString
0x180069656  mov     [rbp+57h+bstrString], r12
0x18006965a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006965e  inc     r8; unsigned int
0x180069661  cmp     [r14+r8*2], r12w
0x180069666  jnz     short loc_18006965E
0x180069668  mov     rdx, r14; wchar_t *
0x18006966b  lea     rcx, [rbp+57h+bstrString]; this
0x18006966f  call    ?Append@CSusBSTR@@QEAAJPEB_WK@Z; CSusBSTR::Append(wchar_t const *,ulong)
0x180069674  mov     rbx, [rbp+57h+bstrString]
0x180069678  test    eax, eax
0x18006967a  js      short loc_1800696B9
0x18006967c  mov     rdx, rbx; wchar_t *
0x18006967f  mov     rcx, r15; this
0x180069682  call    ?AddCopy@CBSTRList@@QEAAJQEA_W@Z; CBSTRList::AddCopy(wchar_t * const)
0x180069687  mov     edi, eax
0x180069689  test    eax, eax
0x18006968b  js      loc_180069739
0x180069691  mov     [rsp+0C0h+var_90], r14
0x180069696  lea     rax, aUserpreferredl; "UserPreferredLanguage : %ws"
0x18006969d  mov     [rsp+0C0h+var_98], rax
0x1800696a2  mov     [rsp+0C0h+var_A0], r12
0x1800696a7  xor     edx, edx
0x1800696a9  xor     ecx, ecx
0x1800696ab  lea     r9d, [rdx+5]
0x1800696af  lea     r8d, [rdx+8]
0x1800696b3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800696b8  nop
0x1800696b9  mov     rcx, rbx; bstrString
0x1800696bc  call    cs:__imp_SysFreeString
0x1800696c2  inc     esi
0x1800696c4  cmp     esi, [rbp+57h+var_40]
0x1800696c7  jb      loc_180069607
0x1800696cd  mov     edi, r12d
0x1800696d0  mov     rcx, [rbp+57h+var_48]; string
0x1800696d4  call    cs:__imp_WindowsDeleteString
0x1800696da  nop
0x1800696db  mov     rcx, [rbp+57h+var_38]
0x1800696df  test    rcx, rcx
0x1800696e2  jz      short loc_1800696F5
0x1800696e4  mov     [rbp+57h+var_38], r12
0x1800696e8  mov     rax, [rcx]
0x1800696eb  mov     rax, [rax+10h]
0x1800696ef  call    _guard_dispatch_icall
0x1800696f4  nop
0x1800696f5  mov     rcx, [rbp+57h+var_30]
0x1800696f9  test    rcx, rcx
0x1800696fc  jz      short loc_18006970F
0x1800696fe  mov     [rbp+57h+var_30], r12
0x180069702  mov     rdx, [rcx]
0x180069705  mov     rax, [rdx+10h]
0x180069709  call    _guard_dispatch_icall
0x18006970e  nop
0x18006970f  mov     eax, edi
0x180069711  mov     rcx, [rbp+57h+var_28]
0x180069715  xor     rcx, rsp; StackCookie
0x180069718  call    __security_check_cookie
0x18006971d  lea     r11, [rsp+0C0h+var_20]
0x180069725  mov     rbx, [r11+30h]
0x180069729  mov     rsi, [r11+40h]
0x18006972d  mov     rsp, r11
0x180069730  pop     r15
0x180069732  pop     r14
0x180069734  pop     r12
0x180069736  pop     rdi
0x180069737  pop     rbp
0x180069738  retn
0x180069739  mov     rcx, [rbp+5Fh]; this
0x18006973d  mov     r9d, eax; char *
0x180069740  lea     r8, aCW1SSrcClientE_67; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x180069747  mov     edx, 483h; void *
0x18006974c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180069751  nop
0x180069752  mov     rcx, rbx; bstrString
0x180069755  call    cs:__imp_SysFreeString
0x18006975b  jmp     loc_1800696D0
0x180069760  mov     ecx, eax; this
0x180069762  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
