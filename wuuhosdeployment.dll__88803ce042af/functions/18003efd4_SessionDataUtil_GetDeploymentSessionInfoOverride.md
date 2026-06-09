# SessionDataUtil::GetDeploymentSessionInfoOverride

- ea: `0x18003efd4`
- end: `0x18003f2dd`
- name: `SessionDataUtil::GetDeploymentSessionInfoOverride`
- size: `777`
- prototype: `__int64 __fastcall(SessionDataUtil *this, LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180041448`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000c0b4`
- `0x18002d674`
- `0x18002e000`
- `0x18002ea14`
- `0x18002eb34`
- `0x18003e850`
- `0x18003efd4`
- `0x180041e98`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f12e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f165`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f12e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f165`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f13c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f173`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f13c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003f1b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003f1b2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003f1cf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003f1cf`
- `OLEAUT32!__imp_SysStringLen` at `0x18003f151`
- `OLEAUT32!__imp_SysStringLen` at `0x18003f151`

## string_xrefs

- `0x18003f1ab`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall SessionDataUtil::GetDeploymentSessionInfoOverride(
        const WCHAR *this,
        LPCWCH lpWideCharStr,
        _QWORD *a3)
{
  int v6; // eax
  CHAR *v7; // rcx
  CHAR *v8; // rbx
  int v9; // eax
  wchar_t **v10; // r9
  void *v11; // rcx
  void *v12; // rdi
  int ExtendedSessionData; // eax
  void *v14; // rsi
  HANDLE ProcessHeap; // rax
  UINT v16; // eax
  HANDLE v17; // rax
  HRESULT v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  unsigned int v21; // edi
  __int64 v22; // rbx
  int (__fastcall *v23)(__int64, _QWORD, JsonUtil **); // rdi
  __int64 v24; // rax
  struct ABI::Windows::Data::Json::IJsonObject **v25; // r9
  int NamedObject; // eax
  __int64 v27; // rbx
  __int64 v28; // rdx
  wchar_t v29[4]; // [rsp+20h] [rbp-60h] BYREF
  LPCCH lpMultiByteStr; // [rsp+28h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-50h] BYREF
  HSTRING string; // [rsp+48h] [rbp-38h] BYREF
  LPCWCH v33; // [rsp+50h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-28h] BYREF
  JsonUtil *v35; // [rsp+60h] [rbp-20h] BYREF
  __int64 v36; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v33 = lpWideCharStr;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)0x80004003LL,
      *(int *)v29);
    return 2147500035LL;
  }
  *a3 = 0;
  if ( !this || !*this || !lpWideCharStr || !*lpWideCharStr )
    return 0;
  lpMultiByteStr = 0;
  v6 = ConvertWideToAnsi_Alloc(lpWideCharStr, (char **)&lpMultiByteStr);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)(unsigned int)v6,
      *(int *)v29);
    v7 = (CHAR *)lpMultiByteStr;
    if ( !lpMultiByteStr )
      return 0;
LABEL_9:
    CSusBaseAllocTag<942762101>::operator delete(v7);
    return 0;
  }
  *(_QWORD *)v29 = 0;
  v8 = (CHAR *)lpMultiByteStr;
  v9 = ConvertAnsiToWide_Alloc(lpMultiByteStr, (wchar_t **)v29);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)(unsigned int)v9,
      *(int *)v29);
    v11 = *(void **)v29;
    if ( !*(_QWORD *)v29 )
    {
LABEL_14:
      if ( !v8 )
        return 0;
      v7 = v8;
      goto LABEL_9;
    }
LABEL_13:
    CSusBaseAllocTag<942762101>::operator delete(v11);
    goto LABEL_14;
  }
  lpMem = 0;
  v12 = *(void **)v29;
  ExtendedSessionData = SessionDataUtil::ExtractExtendedSessionData(
                          this,
                          *(const wchar_t **)v29,
                          (wchar_t *)&lpMem,
                          v10);
  if ( ExtendedSessionData < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)(unsigned int)ExtendedSessionData,
      *(int *)v29);
    v14 = lpMem;
LABEL_18:
    if ( v14 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
    }
    if ( !v12 )
      goto LABEL_14;
    v11 = v12;
    goto LABEL_13;
  }
  v16 = SysStringLen((BSTR)lpMem);
  v14 = lpMem;
  if ( !v16 )
    goto LABEL_18;
  if ( lpMem )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v14);
  }
  if ( v12 )
    CSusBaseAllocTag<942762101>::operator delete(v12);
  if ( v8 )
    CSusBaseAllocTag<942762101>::operator delete(v8);
  v36 = 0;
  string = 0;
  v18 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v18 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
    JUMPOUT(0x18003F2DCLL);
  }
  if ( (int)RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v36) >= 0 )
  {
    v35 = 0;
    v22 = v36;
    v23 = *(int (__fastcall **)(__int64, _QWORD, JsonUtil **))(*(_QWORD *)v36 + 48LL);
    v35 = 0;
    v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v33);
    if ( v23(v22, *(_QWORD *)(v24 + 24), &v35) < 0 )
    {
      v21 = 0;
LABEL_43:
      if ( v35 )
        (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v35 + 16LL))(v35);
      goto LABEL_45;
    }
    *(_QWORD *)v29 = 0;
    NamedObject = JsonUtil::GetNamedObject(
                    v35,
                    (struct ABI::Windows::Data::Json::IJsonObject *)L"DeploymentSessionInfo",
                    v29,
                    v25);
    v21 = NamedObject;
    v27 = *(_QWORD *)v29;
    if ( NamedObject >= 0 )
    {
      if ( !*(_QWORD *)v29
        || (NamedObject = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))v29)(
                            *(_QWORD *)v29,
                            &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
                            a3),
            v21 = NamedObject,
            NamedObject >= 0) )
      {
        v21 = 0;
LABEL_41:
        if ( v27 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        goto LABEL_43;
      }
      v28 = 217;
    }
    else
    {
      v28 = 213;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)(unsigned int)NamedObject,
      *(int *)v29);
    goto LABEL_41;
  }
  v21 = 0;
LABEL_45:
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  return v21;
}

```

## disassembly

```asm
0x18003efd4  mov     [rsp-28h+arg_18], rbx
0x18003efd9  push    rbp
0x18003efda  push    rsi
0x18003efdb  push    rdi
0x18003efdc  push    r14
0x18003efde  push    r15
0x18003efe0  mov     rbp, rsp
0x18003efe3  sub     rsp, 80h
0x18003efea  mov     rax, cs:__security_cookie
0x18003eff1  xor     rax, rsp
0x18003eff4  mov     [rbp+var_10], rax
0x18003eff8  mov     r14, r8
0x18003effb  mov     rax, rdx
0x18003effe  mov     rsi, rcx
0x18003f001  mov     [rbp+var_30], rdx
0x18003f005  xor     r15d, r15d
0x18003f008  test    r8, r8
0x18003f00b  jnz     short loc_18003F02E
0x18003f00d  mov     rcx, [rbp+28h]; this
0x18003f011  mov     ebx, 80004003h
0x18003f016  mov     r9d, ebx; char *
0x18003f019  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003f020  mov     edx, 0C4h; void *
0x18003f025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f02a  mov     eax, ebx
0x18003f02c  jmp     short loc_18003F084
0x18003f02e  mov     [r8], r15
0x18003f031  test    rsi, rsi
0x18003f034  jz      short loc_18003F082
0x18003f036  cmp     [rcx], r15w
0x18003f03a  jz      short loc_18003F082
0x18003f03c  test    rax, rax
0x18003f03f  jz      short loc_18003F082
0x18003f041  cmp     [rdx], r15w
0x18003f045  jz      short loc_18003F082
0x18003f047  mov     [rbp+lpMultiByteStr], r15
0x18003f04b  lea     rdx, [rbp+lpMultiByteStr]; char **
0x18003f04f  mov     rcx, rax; lpWideCharStr
0x18003f052  call    ?ConvertWideToAnsi_Alloc@@YAJPEB_WPEAPEAD@Z; ConvertWideToAnsi_Alloc(wchar_t const *,char * *)
0x18003f057  mov     rcx, [rbp+28h]; this
0x18003f05b  test    eax, eax
0x18003f05d  jns     short loc_18003F0A7
0x18003f05f  mov     r9d, eax; char *
0x18003f062  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003f069  mov     edx, 0A7h; void *
0x18003f06e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f073  nop
0x18003f074  mov     rcx, [rbp+lpMultiByteStr]; lpMem
0x18003f078  test    rcx, rcx
0x18003f07b  jz      short loc_18003F082
0x18003f07d  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18003f082  xor     eax, eax
0x18003f084  mov     rcx, [rbp+var_10]
0x18003f088  xor     rcx, rsp; StackCookie
0x18003f08b  call    __security_check_cookie
0x18003f090  mov     rbx, [rsp+80h+arg_18]
0x18003f098  add     rsp, 80h
0x18003f09f  pop     r15
0x18003f0a1  pop     r14
0x18003f0a3  pop     rdi
0x18003f0a4  pop     rsi
0x18003f0a5  pop     rbp
0x18003f0a6  retn
0x18003f0a7  mov     qword ptr [rbp+var_60], r15
0x18003f0ab  lea     rdx, [rbp+var_60]; wchar_t **
0x18003f0af  mov     rbx, [rbp+lpMultiByteStr]
0x18003f0b3  mov     rcx, rbx; lpMultiByteStr
0x18003f0b6  call    ?ConvertAnsiToWide_Alloc@@YAJPEBDPEAPEA_W@Z; ConvertAnsiToWide_Alloc(char const *,wchar_t * *)
0x18003f0bb  mov     rcx, [rbp+28h]; this
0x18003f0bf  test    eax, eax
0x18003f0c1  jns     short loc_18003F0F1
0x18003f0c3  mov     r9d, eax; char *
0x18003f0c6  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003f0cd  mov     edx, 0ADh; void *
0x18003f0d2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f0d7  nop
0x18003f0d8  mov     rcx, qword ptr [rbp+var_60]; lpMem
0x18003f0dc  test    rcx, rcx
0x18003f0df  jz      short loc_18003F0E7
0x18003f0e1  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18003f0e6  nop
0x18003f0e7  test    rbx, rbx
0x18003f0ea  jz      short loc_18003F082
0x18003f0ec  mov     rcx, rbx
0x18003f0ef  jmp     short loc_18003F07D
0x18003f0f1  mov     [rbp+lpMem], r15
0x18003f0f5  lea     r8, [rbp+lpMem]; wchar_t *
0x18003f0f9  mov     rdi, qword ptr [rbp+var_60]
0x18003f0fd  mov     rdx, rdi; wchar_t *
0x18003f100  mov     rcx, rsi; this
0x18003f103  call    ?ExtractExtendedSessionData@SessionDataUtil@@YAJPEB_W0PEAPEA_W@Z; SessionDataUtil::ExtractExtendedSessionData(wchar_t const *,wchar_t const *,wchar_t * *)
0x18003f108  mov     rcx, [rbp+28h]; this
0x18003f10c  test    eax, eax
0x18003f10e  jns     short loc_18003F14D
0x18003f110  mov     r9d, eax; char *
0x18003f113  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003f11a  mov     edx, 0B3h; void *
0x18003f11f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f124  nop
0x18003f125  mov     rsi, [rbp+lpMem]
0x18003f129  test    rsi, rsi
0x18003f12c  jz      short loc_18003F143
0x18003f12e  call    cs:__imp_GetProcessHeap
0x18003f134  mov     rcx, rax; hHeap
0x18003f137  mov     r8, rsi; lpMem
0x18003f13a  xor     edx, edx; dwFlags
0x18003f13c  call    cs:__imp_HeapFree
0x18003f142  nop
0x18003f143  test    rdi, rdi
0x18003f146  jz      short loc_18003F0E7
0x18003f148  mov     rcx, rdi
0x18003f14b  jmp     short loc_18003F0E1
0x18003f14d  mov     rcx, [rbp+lpMem]; pbstr
0x18003f151  call    cs:__imp_SysStringLen
0x18003f157  nop
0x18003f158  mov     rsi, [rbp+lpMem]
0x18003f15c  test    eax, eax
0x18003f15e  jz      short loc_18003F129
0x18003f160  test    rsi, rsi
0x18003f163  jz      short loc_18003F17A
0x18003f165  call    cs:__imp_GetProcessHeap
0x18003f16b  mov     rcx, rax; hHeap
0x18003f16e  mov     r8, rsi; lpMem
0x18003f171  xor     edx, edx; dwFlags
0x18003f173  call    cs:__imp_HeapFree
0x18003f179  nop
0x18003f17a  test    rdi, rdi
0x18003f17d  jz      short loc_18003F188
0x18003f17f  mov     rcx, rdi; lpMem
0x18003f182  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18003f187  nop
0x18003f188  test    rbx, rbx
0x18003f18b  jz      short loc_18003F196
0x18003f18d  mov     rcx, rbx; lpMem
0x18003f190  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18003f195  nop
0x18003f196  mov     [rbp+var_18], r15
0x18003f19a  mov     [rbp+string], r15
0x18003f19e  lea     r9, [rbp+string]; string
0x18003f1a2  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003f1a6  mov     edx, 1Ch; length
0x18003f1ab  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x18003f1b2  call    cs:__imp_WindowsCreateStringReference
0x18003f1b8  test    eax, eax
0x18003f1ba  js      loc_18003F2D5
0x18003f1c0  lea     r8, [rbp+var_18]
0x18003f1c4  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18003f1cb  mov     rcx, [rbp+string]
0x18003f1cf  call    cs:__imp_RoGetActivationFactory
0x18003f1d5  shr     eax, 1Fh
0x18003f1d8  test    al, al
0x18003f1da  jz      short loc_18003F1E4
0x18003f1dc  mov     edi, r15d
0x18003f1df  jmp     loc_18003F2B8
0x18003f1e4  mov     [rbp+var_20], r15
0x18003f1e8  mov     rbx, [rbp+var_18]
0x18003f1ec  mov     rax, [rbx]
0x18003f1ef  mov     rdi, [rax+30h]
0x18003f1f3  mov     [rbp+var_20], r15
0x18003f1f7  lea     rdx, [rbp+var_30]
0x18003f1fb  lea     rcx, [rbp+hstringHeader]
0x18003f1ff  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x18003f204  nop
0x18003f205  lea     r8, [rbp+var_20]
0x18003f209  mov     rdx, [rax+18h]
0x18003f20d  mov     rcx, rbx
0x18003f210  mov     rax, rdi
0x18003f213  call    _guard_dispatch_icall
0x18003f218  shr     eax, 1Fh
0x18003f21b  test    al, al
0x18003f21d  jz      short loc_18003F224
0x18003f21f  mov     edi, r15d
0x18003f222  jmp     short loc_18003F2A2
0x18003f224  mov     qword ptr [rbp+var_60], r15
0x18003f228  lea     r8, [rbp+var_60]; wchar_t *
0x18003f22c  lea     rdx, aDeploymentsess; "DeploymentSessionInfo"
0x18003f233  mov     rcx, [rbp+var_20]; this
0x18003f237  call    ?GetNamedObject@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WPEAPEAU23456@@Z; JsonUtil::GetNamedObject(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,ABI::Windows::Data::Json::IJsonObject * *)
0x18003f23c  mov     edi, eax
0x18003f23e  mov     rbx, qword ptr [rbp+var_60]
0x18003f242  test    eax, eax
0x18003f244  jns     short loc_18003F24D
0x18003f246  mov     edx, 0D5h
0x18003f24b  jmp     short loc_18003F275
0x18003f24d  test    rbx, rbx
0x18003f250  jz      short loc_18003F28A
0x18003f252  mov     rax, [rbx]
0x18003f255  mov     r8, r14
0x18003f258  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x18003f25f  mov     rcx, rbx
0x18003f262  mov     rax, [rax]
0x18003f265  call    _guard_dispatch_icall
0x18003f26a  mov     edi, eax
0x18003f26c  test    eax, eax
0x18003f26e  jns     short loc_18003F28A
0x18003f270  mov     edx, 0D9h; void *
0x18003f275  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003f27c  mov     r9d, eax; char *
0x18003f27f  mov     rcx, [rbp+28h]; this
0x18003f283  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f288  jmp     short loc_18003F28D
0x18003f28a  mov     edi, r15d
0x18003f28d  test    rbx, rbx
0x18003f290  jz      short loc_18003F2A2
0x18003f292  mov     rax, [rbx]
0x18003f295  mov     rcx, rbx
0x18003f298  mov     rax, [rax+10h]
0x18003f29c  call    _guard_dispatch_icall
0x18003f2a1  nop
0x18003f2a2  mov     rcx, [rbp+var_20]
0x18003f2a6  test    rcx, rcx
0x18003f2a9  jz      short loc_18003F2B8
0x18003f2ab  mov     rax, [rcx]
0x18003f2ae  mov     rax, [rax+10h]
0x18003f2b2  call    _guard_dispatch_icall
0x18003f2b7  nop
0x18003f2b8  mov     rcx, [rbp+var_18]
0x18003f2bc  test    rcx, rcx
0x18003f2bf  jz      short loc_18003F2CE
0x18003f2c1  mov     rdx, [rcx]
0x18003f2c4  mov     rax, [rdx+10h]
0x18003f2c8  call    _guard_dispatch_icall
0x18003f2cd  nop
0x18003f2ce  mov     eax, edi
0x18003f2d0  jmp     loc_18003F084
0x18003f2d5  mov     ecx, eax; this
0x18003f2d7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
