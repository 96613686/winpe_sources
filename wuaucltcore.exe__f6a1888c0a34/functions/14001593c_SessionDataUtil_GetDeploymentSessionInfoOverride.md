# SessionDataUtil::GetDeploymentSessionInfoOverride

- ea: `0x14001593c`
- end: `0x140015c45`
- name: `SessionDataUtil::GetDeploymentSessionInfoOverride`
- size: `777`
- prototype: `__int64 __fastcall(SessionDataUtil *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017db0`

## callees

- `0x140002ac0`
- `0x14000b1f4`
- `0x14000d4cc`
- `0x1400151b8`
- `0x14001593c`
- `0x1400182d8`
- `0x1400182f0`
- `0x1400188c8`
- `0x1400189f4`
- `0x140018b14`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015aa4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015adb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015aa4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015adb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015a96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015acd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015a96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015acd`
- `OLEAUT32!__imp_SysStringLen` at `0x140015ab9`
- `OLEAUT32!__imp_SysStringLen` at `0x140015ab9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140015b1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140015b1a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140015b37`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140015b37`

## string_xrefs

- `0x140015b13`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall SessionDataUtil::GetDeploymentSessionInfoOverride(const WCHAR *this, const WCHAR *a2, _QWORD *a3)
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
  const WCHAR *v33; // [rsp+50h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-28h] BYREF
  JsonUtil *v35; // [rsp+60h] [rbp-20h] BYREF
  __int64 v36; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v33 = a2;
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
  if ( !this || !*this || !a2 || !*a2 )
    return 0;
  lpMultiByteStr = 0;
  v6 = ConvertWideToAnsi_Alloc(a2, (char **)&lpMultiByteStr);
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
    SusFree(v7);
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
    SusFree(v11);
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
    SusFree(v12);
  if ( v8 )
    SusFree(v8);
  v36 = 0;
  string = 0;
  v18 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v18 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
    JUMPOUT(0x140015C44LL);
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
0x14001593c  mov     [rsp-28h+arg_18], rbx
0x140015941  push    rbp
0x140015942  push    rsi
0x140015943  push    rdi
0x140015944  push    r14
0x140015946  push    r15
0x140015948  mov     rbp, rsp
0x14001594b  sub     rsp, 80h
0x140015952  mov     rax, cs:__security_cookie
0x140015959  xor     rax, rsp
0x14001595c  mov     [rbp+var_10], rax
0x140015960  mov     r14, r8
0x140015963  mov     rax, rdx
0x140015966  mov     rsi, rcx
0x140015969  mov     [rbp+var_30], rdx
0x14001596d  xor     r15d, r15d
0x140015970  test    r8, r8
0x140015973  jnz     short loc_140015996
0x140015975  mov     rcx, [rbp+28h]; this
0x140015979  mov     ebx, 80004003h
0x14001597e  mov     r9d, ebx; char *
0x140015981  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140015988  mov     edx, 0C4h; void *
0x14001598d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015992  mov     eax, ebx
0x140015994  jmp     short loc_1400159EC
0x140015996  mov     [r8], r15
0x140015999  test    rsi, rsi
0x14001599c  jz      short loc_1400159EA
0x14001599e  cmp     [rcx], r15w
0x1400159a2  jz      short loc_1400159EA
0x1400159a4  test    rax, rax
0x1400159a7  jz      short loc_1400159EA
0x1400159a9  cmp     [rdx], r15w
0x1400159ad  jz      short loc_1400159EA
0x1400159af  mov     [rbp+lpMultiByteStr], r15
0x1400159b3  lea     rdx, [rbp+lpMultiByteStr]; char **
0x1400159b7  mov     rcx, rax; lpWideCharStr
0x1400159ba  call    ?ConvertWideToAnsi_Alloc@@YAJPEB_WPEAPEAD@Z; ConvertWideToAnsi_Alloc(wchar_t const *,char * *)
0x1400159bf  mov     rcx, [rbp+28h]; this
0x1400159c3  test    eax, eax
0x1400159c5  jns     short loc_140015A0F
0x1400159c7  mov     r9d, eax; char *
0x1400159ca  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400159d1  mov     edx, 0A7h; void *
0x1400159d6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400159db  nop
0x1400159dc  mov     rcx, [rbp+lpMultiByteStr]; lpMem
0x1400159e0  test    rcx, rcx
0x1400159e3  jz      short loc_1400159EA
0x1400159e5  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400159ea  xor     eax, eax
0x1400159ec  mov     rcx, [rbp+var_10]
0x1400159f0  xor     rcx, rsp; StackCookie
0x1400159f3  call    __security_check_cookie
0x1400159f8  mov     rbx, [rsp+80h+arg_18]
0x140015a00  add     rsp, 80h
0x140015a07  pop     r15
0x140015a09  pop     r14
0x140015a0b  pop     rdi
0x140015a0c  pop     rsi
0x140015a0d  pop     rbp
0x140015a0e  retn
0x140015a0f  mov     qword ptr [rbp+var_60], r15
0x140015a13  lea     rdx, [rbp+var_60]; wchar_t **
0x140015a17  mov     rbx, [rbp+lpMultiByteStr]
0x140015a1b  mov     rcx, rbx; lpMultiByteStr
0x140015a1e  call    ?ConvertAnsiToWide_Alloc@@YAJPEBDPEAPEA_W@Z; ConvertAnsiToWide_Alloc(char const *,wchar_t * *)
0x140015a23  mov     rcx, [rbp+28h]; this
0x140015a27  test    eax, eax
0x140015a29  jns     short loc_140015A59
0x140015a2b  mov     r9d, eax; char *
0x140015a2e  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140015a35  mov     edx, 0ADh; void *
0x140015a3a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140015a3f  nop
0x140015a40  mov     rcx, qword ptr [rbp+var_60]; lpMem
0x140015a44  test    rcx, rcx
0x140015a47  jz      short loc_140015A4F
0x140015a49  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140015a4e  nop
0x140015a4f  test    rbx, rbx
0x140015a52  jz      short loc_1400159EA
0x140015a54  mov     rcx, rbx
0x140015a57  jmp     short loc_1400159E5
0x140015a59  mov     [rbp+lpMem], r15
0x140015a5d  lea     r8, [rbp+lpMem]; wchar_t *
0x140015a61  mov     rdi, qword ptr [rbp+var_60]
0x140015a65  mov     rdx, rdi; wchar_t *
0x140015a68  mov     rcx, rsi; this
0x140015a6b  call    ?ExtractExtendedSessionData@SessionDataUtil@@YAJPEB_W0PEAPEA_W@Z; SessionDataUtil::ExtractExtendedSessionData(wchar_t const *,wchar_t const *,wchar_t * *)
0x140015a70  mov     rcx, [rbp+28h]; this
0x140015a74  test    eax, eax
0x140015a76  jns     short loc_140015AB5
0x140015a78  mov     r9d, eax; char *
0x140015a7b  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140015a82  mov     edx, 0B3h; void *
0x140015a87  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140015a8c  nop
0x140015a8d  mov     rsi, [rbp+lpMem]
0x140015a91  test    rsi, rsi
0x140015a94  jz      short loc_140015AAB
0x140015a96  call    cs:__imp_GetProcessHeap
0x140015a9c  mov     rcx, rax; hHeap
0x140015a9f  mov     r8, rsi; lpMem
0x140015aa2  xor     edx, edx; dwFlags
0x140015aa4  call    cs:__imp_HeapFree
0x140015aaa  nop
0x140015aab  test    rdi, rdi
0x140015aae  jz      short loc_140015A4F
0x140015ab0  mov     rcx, rdi
0x140015ab3  jmp     short loc_140015A49
0x140015ab5  mov     rcx, [rbp+lpMem]; pbstr
0x140015ab9  call    cs:__imp_SysStringLen
0x140015abf  nop
0x140015ac0  mov     rsi, [rbp+lpMem]
0x140015ac4  test    eax, eax
0x140015ac6  jz      short loc_140015A91
0x140015ac8  test    rsi, rsi
0x140015acb  jz      short loc_140015AE2
0x140015acd  call    cs:__imp_GetProcessHeap
0x140015ad3  mov     rcx, rax; hHeap
0x140015ad6  mov     r8, rsi; lpMem
0x140015ad9  xor     edx, edx; dwFlags
0x140015adb  call    cs:__imp_HeapFree
0x140015ae1  nop
0x140015ae2  test    rdi, rdi
0x140015ae5  jz      short loc_140015AF0
0x140015ae7  mov     rcx, rdi; lpMem
0x140015aea  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140015aef  nop
0x140015af0  test    rbx, rbx
0x140015af3  jz      short loc_140015AFE
0x140015af5  mov     rcx, rbx; lpMem
0x140015af8  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140015afd  nop
0x140015afe  mov     [rbp+var_18], r15
0x140015b02  mov     [rbp+string], r15
0x140015b06  lea     r9, [rbp+string]; string
0x140015b0a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x140015b0e  mov     edx, 1Ch; length
0x140015b13  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x140015b1a  call    cs:__imp_WindowsCreateStringReference
0x140015b20  test    eax, eax
0x140015b22  js      loc_140015C3D
0x140015b28  lea     r8, [rbp+var_18]
0x140015b2c  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x140015b33  mov     rcx, [rbp+string]
0x140015b37  call    cs:__imp_RoGetActivationFactory
0x140015b3d  shr     eax, 1Fh
0x140015b40  test    al, al
0x140015b42  jz      short loc_140015B4C
0x140015b44  mov     edi, r15d
0x140015b47  jmp     loc_140015C20
0x140015b4c  mov     [rbp+var_20], r15
0x140015b50  mov     rbx, [rbp+var_18]
0x140015b54  mov     rax, [rbx]
0x140015b57  mov     rdi, [rax+30h]
0x140015b5b  mov     [rbp+var_20], r15
0x140015b5f  lea     rdx, [rbp+var_30]
0x140015b63  lea     rcx, [rbp+hstringHeader]
0x140015b67  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x140015b6c  nop
0x140015b6d  lea     r8, [rbp+var_20]
0x140015b71  mov     rdx, [rax+18h]
0x140015b75  mov     rcx, rbx
0x140015b78  mov     rax, rdi
0x140015b7b  call    _guard_dispatch_icall
0x140015b80  shr     eax, 1Fh
0x140015b83  test    al, al
0x140015b85  jz      short loc_140015B8C
0x140015b87  mov     edi, r15d
0x140015b8a  jmp     short loc_140015C0A
0x140015b8c  mov     qword ptr [rbp+var_60], r15
0x140015b90  lea     r8, [rbp+var_60]; wchar_t *
0x140015b94  lea     rdx, aDeploymentsess; "DeploymentSessionInfo"
0x140015b9b  mov     rcx, [rbp+var_20]; this
0x140015b9f  call    ?GetNamedObject@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WPEAPEAU23456@@Z; JsonUtil::GetNamedObject(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,ABI::Windows::Data::Json::IJsonObject * *)
0x140015ba4  mov     edi, eax
0x140015ba6  mov     rbx, qword ptr [rbp+var_60]
0x140015baa  test    eax, eax
0x140015bac  jns     short loc_140015BB5
0x140015bae  mov     edx, 0D5h
0x140015bb3  jmp     short loc_140015BDD
0x140015bb5  test    rbx, rbx
0x140015bb8  jz      short loc_140015BF2
0x140015bba  mov     rax, [rbx]
0x140015bbd  mov     r8, r14
0x140015bc0  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x140015bc7  mov     rcx, rbx
0x140015bca  mov     rax, [rax]
0x140015bcd  call    _guard_dispatch_icall
0x140015bd2  mov     edi, eax
0x140015bd4  test    eax, eax
0x140015bd6  jns     short loc_140015BF2
0x140015bd8  mov     edx, 0D9h; void *
0x140015bdd  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140015be4  mov     r9d, eax; char *
0x140015be7  mov     rcx, [rbp+28h]; this
0x140015beb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015bf0  jmp     short loc_140015BF5
0x140015bf2  mov     edi, r15d
0x140015bf5  test    rbx, rbx
0x140015bf8  jz      short loc_140015C0A
0x140015bfa  mov     rax, [rbx]
0x140015bfd  mov     rcx, rbx
0x140015c00  mov     rax, [rax+10h]
0x140015c04  call    _guard_dispatch_icall
0x140015c09  nop
0x140015c0a  mov     rcx, [rbp+var_20]
0x140015c0e  test    rcx, rcx
0x140015c11  jz      short loc_140015C20
0x140015c13  mov     rax, [rcx]
0x140015c16  mov     rax, [rax+10h]
0x140015c1a  call    _guard_dispatch_icall
0x140015c1f  nop
0x140015c20  mov     rcx, [rbp+var_18]
0x140015c24  test    rcx, rcx
0x140015c27  jz      short loc_140015C36
0x140015c29  mov     rdx, [rcx]
0x140015c2c  mov     rax, [rdx+10h]
0x140015c30  call    _guard_dispatch_icall
0x140015c35  nop
0x140015c36  mov     eax, edi
0x140015c38  jmp     loc_1400159EC
0x140015c3d  mov     ecx, eax; this
0x140015c3f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
