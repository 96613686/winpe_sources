# RegistryJson::RuntimeClassInitialize(Windows::Data::Json::IJsonObject *,HKEY__ *,ushort const *)

- ea: `0x180050b28`
- end: `0x180050fa5`
- name: `?RuntimeClassInitialize@RegistryJson@@QEAAJPEAUIJsonObject@Json@Data@Windows@@PEAUHKEY__@@PEBG@Z`
- size: `1149`
- prototype: `__int64 __fastcall(RegistryJson *this, struct Windows::Data::Json::IJsonObject *, HKEY, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004f75c`
- `0x18004f854`

## callees

- `0x180003110`
- `0x18000b0bc`
- `0x18000e5ac`
- `0x180025180`
- `0x18002ade8`
- `0x180050b28`
- `0x180051ac0`
- `0x180051adc`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050b75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050bfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050c50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050cff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050d17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050d72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050e03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050e39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050e98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050eac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050f7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050b75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050bfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050c50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050cff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050d17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050d72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050e03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050e39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050e98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050eac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050f7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050bc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050c9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050dc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050bc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050c9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050dc3`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180050cb8`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180050cb8`

## string_xrefs

- `0x180050dec`: `onecore\base\flighting\common\regvalet\registryjson.cpp`
- `0x180050e22`: `onecore\base\flighting\common\regvalet\registryjson.cpp`
- `0x180050e7b`: `onecore\base\flighting\common\regvalet\registryjson.cpp`
- `0x180050c14`: `FullPath`

## pseudocode

```c
__int64 __fastcall RegistryJson::RuntimeClassInitialize(
        RegistryJson *this,
        struct Windows::Data::Json::IJsonObject *a2,
        HKEY a3,
        unsigned __int16 *a4)
{
  int (__fastcall *v8)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rdx
  int (__fastcall *v13)(struct Windows::Data::Json::IJsonObject *, __int64, char *); // rbx
  int (__fastcall *v14)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  PCWSTR v15; // rax
  unsigned __int64 v16; // r8
  int (__fastcall *v17)(struct Windows::Data::Json::IJsonObject *, __int64, char *); // rdi
  bool v18; // al
  int (__fastcall *v19)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  const unsigned __int16 *v20; // rax
  int v21; // eax
  void (__fastcall *v22)(struct Windows::Data::Json::IJsonObject *, __int64, char *); // rdi
  int (__fastcall *v23)(struct Windows::Data::Json::IJsonObject *, __int64, char *); // rbx
  int (__fastcall *v24)(struct Windows::Data::Json::IJsonObject *, __int64, char *); // rbx
  int v26; // [rsp+20h] [rbp-E0h]
  HSTRING v27; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v28; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v32[520]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  v27 = (HSTRING)a4;
  string = 0;
  v8 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"HKey", 5u, 4u);
  if ( v8(a2, v31, &string) < 0 )
  {
    *((_QWORD *)this + 2) = a3;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !RegValet::StringType::ToRootHive((HKEY *)this + 2, StringRawBuffer) )
    {
      v10 = -2147467259;
      v11 = 2147500037LL;
      v12 = 89;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\flighting\\common\\regvalet\\registryjson.cpp",
        (const char *)v11,
        v26);
      goto LABEL_30;
    }
  }
  v13 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, char *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(*((HSTRING *)this + 3));
  *((_QWORD *)this + 3) = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"FullPath", 9u, 8u);
  if ( v13(a2, v31, (char *)this + 24) >= 0 )
  {
    v28 = 0;
    v14 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
    WindowsDeleteString(0);
    v28 = 0;
    v31 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"PersistedSourceId", 0x12u, 0x11u);
    if ( v14(a2, v31, &v28) < 0 )
      goto LABEL_12;
    v15 = WindowsGetStringRawBuffer(v28, 0);
    v26 = 0;
    if ( (unsigned int)GetPersistedRegistryLocationW(v15, 0, v32, 1040) )
      goto LABEL_12;
    v16 = -1;
    do
      ++v16;
    while ( v32[v16] );
    if ( v16 > 0xFFFFFFFF )
    {
      v10 = -2147024362;
    }
    else
    {
      v10 = Microsoft::WRL::Wrappers::HString::Set((RegistryJson *)((char *)this + 24), v32, v16);
      if ( v10 >= 0 )
      {
LABEL_12:
        WindowsDeleteString(v28);
        goto LABEL_13;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecore\\base\\flighting\\common\\regvalet\\registryjson.cpp",
      (const char *)(unsigned int)v10,
      0);
    WindowsDeleteString(v28);
    v28 = 0;
    goto LABEL_30;
  }
  if ( a4 )
  {
    if ( *a4 )
    {
      v21 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 24, &v27);
      v10 = v21;
      if ( v21 < 0 )
      {
        v11 = (unsigned int)v21;
        v12 = 121;
        goto LABEL_23;
      }
    }
  }
LABEL_13:
  *((_DWORD *)this + 12) = 0;
  v17 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, char *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(*((HSTRING *)this + 4));
  *((_QWORD *)this + 4) = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ValueName", 0xAu, 9u);
  v18 = v17(a2, v31, (char *)this + 32) >= 0;
  *((_BYTE *)this + 52) = v18;
  if ( v18 )
  {
    v27 = 0;
    v19 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
    WindowsDeleteString(0);
    v27 = 0;
    v31 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"RegValueType", 0xDu, 0xCu);
    if ( v19(a2, v31, &v27) >= 0 )
    {
      v20 = WindowsGetStringRawBuffer(v27, 0);
      if ( !RegValet::StringType::ToValueType((unsigned int *)this + 12, v20) )
      {
        v10 = -2147467259;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x97,
          (unsigned int)"onecore\\base\\flighting\\common\\regvalet\\registryjson.cpp",
          (const char *)0x80004005LL,
          v26);
        WindowsDeleteString(v27);
        v27 = 0;
        goto LABEL_30;
      }
    }
    WindowsDeleteString(v27);
  }
  v22 = *(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, char *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(*((HSTRING *)this + 5));
  *((_QWORD *)this + 5) = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"EncodingType", 0xDu, 0xCu);
  v22(a2, v31, (char *)this + 40);
  v23 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, char *))(*(_QWORD *)a2 + 96LL);
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IfExists", 9u, 8u);
  if ( v23(a2, v31, (char *)this + 53) < 0 )
    *((_BYTE *)this + 53) = 0;
  v24 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, char *))(*(_QWORD *)a2 + 96LL);
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IgnoreWild", 0xBu, 0xAu);
  if ( v24(a2, v31, (char *)this + 54) < 0 )
    *((_BYTE *)this + 54) = 0;
  v10 = 0;
LABEL_30:
  WindowsDeleteString(string);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180050b28  push    rbp
0x180050b2a  push    rbx
0x180050b2b  push    rsi
0x180050b2c  push    rdi
0x180050b2d  push    r12
0x180050b2f  push    r14
0x180050b31  push    r15
0x180050b33  lea     rbp, [rsp-390h]
0x180050b3b  sub     rsp, 490h
0x180050b42  mov     rax, cs:__security_cookie
0x180050b49  xor     rax, rsp
0x180050b4c  mov     [rbp+3C0h+var_40], rax
0x180050b53  mov     r14, r9
0x180050b56  mov     rdi, r8
0x180050b59  mov     rsi, rdx
0x180050b5c  mov     r15, rcx
0x180050b5f  mov     [rsp+4C0h+var_490], r9
0x180050b64  xor     r12d, r12d
0x180050b67  mov     [rsp+4C0h+string], r12
0x180050b6c  mov     rax, [rdx]
0x180050b6f  mov     rbx, [rax+50h]
0x180050b73  xor     ecx, ecx; string
0x180050b75  call    cs:__imp_WindowsDeleteString
0x180050b7b  mov     [rsp+4C0h+string], r12
0x180050b80  mov     [rsp+4C0h+var_460], r12
0x180050b85  lea     r9d, [r12+4]; unsigned int
0x180050b8a  lea     r8d, [r12+5]; unsigned int
0x180050b8f  lea     rdx, ?c_jsonRegHKey@RegistryJson@@0QBGB; "HKey"
0x180050b96  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x180050b9b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180050ba0  nop
0x180050ba1  lea     r8, [rsp+4C0h+string]
0x180050ba6  mov     rdx, [rsp+4C0h+var_460]
0x180050bab  mov     rcx, rsi
0x180050bae  mov     rax, rbx
0x180050bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050bb6  nop
0x180050bb7  test    eax, eax
0x180050bb9  js      short loc_180050BEA
0x180050bbb  xor     edx, edx; length
0x180050bbd  mov     rcx, [rsp+4C0h+string]; string
0x180050bc2  call    cs:__imp_WindowsGetStringRawBuffer
0x180050bc8  mov     rdx, rax; unsigned __int16 *
0x180050bcb  lea     rcx, [r15+10h]; HKEY *
0x180050bcf  call    ?ToRootHive@StringType@RegValet@@SA_NPEAPEAUHKEY__@@PEBG@Z; RegValet::StringType::ToRootHive(HKEY__ * *,ushort const *)
0x180050bd4  cmp     al, 1
0x180050bd6  jz      short loc_180050BEE
0x180050bd8  mov     ebx, 80004005h
0x180050bdd  mov     r9d, ebx
0x180050be0  lea     edx, [r12+59h]
0x180050be5  jmp     loc_180050E7B
0x180050bea  mov     [r15+10h], rdi
0x180050bee  mov     rax, [rsi]
0x180050bf1  mov     rbx, [rax+50h]
0x180050bf5  lea     rdi, [r15+18h]
0x180050bf9  mov     rcx, [rdi]; string
0x180050bfc  call    cs:__imp_WindowsDeleteString
0x180050c02  mov     [rdi], r12
0x180050c05  mov     [rsp+4C0h+var_460], r12
0x180050c0a  mov     r9d, 8; unsigned int
0x180050c10  lea     r8d, [r9+1]; unsigned int
0x180050c14  lea     rdx, ?c_jsonRegFullPath@RegistryJson@@0QBGB; "FullPath"
0x180050c1b  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x180050c20  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180050c25  nop
0x180050c26  mov     r8, rdi
0x180050c29  mov     rdx, [rsp+4C0h+var_460]
0x180050c2e  mov     rcx, rsi
0x180050c31  mov     rax, rbx
0x180050c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c39  nop
0x180050c3a  test    eax, eax
0x180050c3c  js      loc_180050E49
0x180050c42  mov     [rsp+4C0h+var_488], r12
0x180050c47  mov     rax, [rsi]
0x180050c4a  mov     rbx, [rax+50h]
0x180050c4e  xor     ecx, ecx; string
0x180050c50  call    cs:__imp_WindowsDeleteString
0x180050c56  mov     [rsp+4C0h+var_488], r12
0x180050c5b  mov     [rsp+4C0h+var_460], r12
0x180050c60  mov     r9d, 11h; unsigned int
0x180050c66  lea     r8d, [r9+1]; unsigned int
0x180050c6a  lea     rdx, ?c_jsonPersistedSourceId@RegistryJson@@0QBGB; "PersistedSourceId"
0x180050c71  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x180050c76  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180050c7b  nop
0x180050c7c  lea     r8, [rsp+4C0h+var_488]
0x180050c81  mov     rdx, [rsp+4C0h+var_460]
0x180050c86  mov     rcx, rsi
0x180050c89  mov     rax, rbx
0x180050c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c91  nop
0x180050c92  test    eax, eax
0x180050c94  js      short loc_180050CFA
0x180050c96  xor     edx, edx; length
0x180050c98  mov     rcx, [rsp+4C0h+var_488]; string
0x180050c9d  call    cs:__imp_WindowsGetStringRawBuffer
0x180050ca3  mov     qword ptr [rsp+4C0h+var_4A0], r12; int
0x180050ca8  mov     r9d, 410h
0x180050cae  lea     r8, [rsp+4C0h+var_450]
0x180050cb3  xor     edx, edx
0x180050cb5  mov     rcx, rax
0x180050cb8  call    cs:__imp_GetPersistedRegistryLocationW
0x180050cbe  test    eax, eax
0x180050cc0  jnz     short loc_180050CFA
0x180050cc2  lea     rax, [rsp+4C0h+var_450]
0x180050cc7  or      r8, 0FFFFFFFFFFFFFFFFh
0x180050ccb  inc     r8; unsigned int
0x180050cce  cmp     [rax+r8*2], r12w
0x180050cd3  jnz     short loc_180050CCB
0x180050cd5  mov     eax, 0FFFFFFFFh
0x180050cda  cmp     r8, rax
0x180050cdd  ja      loc_180050E13
0x180050ce3  lea     rdx, [rsp+4C0h+var_450]; unsigned __int16 *
0x180050ce8  mov     rcx, rdi; this
0x180050ceb  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180050cf0  mov     ebx, eax
0x180050cf2  test    eax, eax
0x180050cf4  js      loc_180050E18
0x180050cfa  mov     rcx, [rsp+4C0h+var_488]; string
0x180050cff  call    cs:__imp_WindowsDeleteString
0x180050d05  mov     [r15+30h], r12d
0x180050d09  mov     rax, [rsi]
0x180050d0c  mov     rdi, [rax+50h]
0x180050d10  lea     rbx, [r15+20h]
0x180050d14  mov     rcx, [rbx]; string
0x180050d17  call    cs:__imp_WindowsDeleteString
0x180050d1d  mov     [rbx], r12
0x180050d20  mov     [rsp+4C0h+var_460], r12
0x180050d25  mov     r9d, 9; unsigned int
0x180050d2b  lea     r8d, [r9+1]; unsigned int
0x180050d2f  lea     rdx, ?c_jsonRegValueName@RegistryJson@@0QBGB; "ValueName"
0x180050d36  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x180050d3b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180050d40  nop
0x180050d41  mov     r8, rbx
0x180050d44  mov     rdx, [rsp+4C0h+var_460]
0x180050d49  mov     rcx, rsi
0x180050d4c  mov     rax, rdi
0x180050d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d54  nop
0x180050d55  shr     eax, 1Fh
0x180050d58  xor     al, 1
0x180050d5a  mov     [r15+34h], al
0x180050d5e  jz      loc_180050E9E
0x180050d64  mov     [rsp+4C0h+var_490], r12
0x180050d69  mov     rax, [rsi]
0x180050d6c  mov     rbx, [rax+50h]
0x180050d70  xor     ecx, ecx; string
0x180050d72  call    cs:__imp_WindowsDeleteString
0x180050d78  mov     [rsp+4C0h+var_490], r12
0x180050d7d  mov     [rsp+4C0h+var_460], r12
0x180050d82  mov     r9d, 0Ch; unsigned int
0x180050d88  lea     r8d, [r9+1]; unsigned int
0x180050d8c  lea     rdx, ?c_jsonRegValueType@RegistryJson@@0QBGB; "RegValueType"
0x180050d93  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x180050d98  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180050d9d  nop
0x180050d9e  lea     r8, [rsp+4C0h+var_490]
0x180050da3  mov     rdx, [rsp+4C0h+var_460]
0x180050da8  mov     rcx, rsi
0x180050dab  mov     rax, rbx
0x180050dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050db3  nop
0x180050db4  test    eax, eax
0x180050db6  js      loc_180050E93
0x180050dbc  xor     edx, edx; length
0x180050dbe  mov     rcx, [rsp+4C0h+var_490]; string
0x180050dc3  call    cs:__imp_WindowsGetStringRawBuffer
0x180050dc9  mov     rdx, rax; unsigned __int16 *
0x180050dcc  lea     rcx, [r15+30h]; unsigned int *
0x180050dd0  call    ?ToValueType@StringType@RegValet@@SA_NPEAKPEBG@Z; RegValet::StringType::ToValueType(ulong *,ushort const *)
0x180050dd5  test    al, al
0x180050dd7  jnz     loc_180050E93
0x180050ddd  mov     rcx, [rbp+3C8h]; this
0x180050de4  mov     ebx, 80004005h
0x180050de9  mov     r9d, ebx; char *
0x180050dec  lea     r8, aOnecoreBaseFli_4; "onecore\\base\\flighting\\common\\regva"...
0x180050df3  mov     edx, 97h; void *
0x180050df8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050dfd  nop
0x180050dfe  mov     rcx, [rsp+4C0h+var_490]; string
0x180050e03  call    cs:__imp_WindowsDeleteString
0x180050e09  mov     [rsp+4C0h+var_490], r12
0x180050e0e  jmp     loc_180050F77
0x180050e13  mov     ebx, 80070216h
0x180050e18  mov     rcx, [rbp+3C8h]; this
0x180050e1f  mov     r9d, ebx; char *
0x180050e22  lea     r8, aOnecoreBaseFli_4; "onecore\\base\\flighting\\common\\regva"...
0x180050e29  mov     edx, 6Eh ; 'n'; void *
0x180050e2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050e33  nop
0x180050e34  mov     rcx, [rsp+4C0h+var_488]; string
0x180050e39  call    cs:__imp_WindowsDeleteString
0x180050e3f  mov     [rsp+4C0h+var_488], r12
0x180050e44  jmp     loc_180050F77
0x180050e49  test    r14, r14
0x180050e4c  jz      loc_180050D05
0x180050e52  cmp     [r14], r12w
0x180050e56  jz      loc_180050D05
0x180050e5c  lea     rdx, [rsp+4C0h+var_490]
0x180050e61  mov     rcx, rdi
0x180050e64  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180050e69  mov     ebx, eax
0x180050e6b  test    eax, eax
0x180050e6d  jns     loc_180050D05
0x180050e73  mov     r9d, eax; char *
0x180050e76  mov     edx, 79h ; 'y'; void *
0x180050e7b  lea     r8, aOnecoreBaseFli_4; "onecore\\base\\flighting\\common\\regva"...
0x180050e82  mov     rcx, [rbp+3C8h]; this
0x180050e89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050e8e  jmp     loc_180050F77
0x180050e93  mov     rcx, [rsp+4C0h+var_490]; string
0x180050e98  call    cs:__imp_WindowsDeleteString
0x180050e9e  mov     rax, [rsi]
0x180050ea1  mov     rdi, [rax+50h]
0x180050ea5  lea     rbx, [r15+28h]
0x180050ea9  mov     rcx, [rbx]; string
0x180050eac  call    cs:__imp_WindowsDeleteString
0x180050eb2  mov     [rbx], r12
0x180050eb5  mov     [rsp+4C0h+var_460], r12
0x180050eba  mov     r9d, 0Ch; unsigned int
0x180050ec0  lea     r8d, [r9+1]; unsigned int
0x180050ec4  lea     rdx, ?c_jsonEncodingType@RegistryJson@@0QBGB; "EncodingType"
0x180050ecb  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x180050ed0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180050ed5  nop
0x180050ed6  mov     r8, rbx
0x180050ed9  mov     rdx, [rsp+4C0h+var_460]
0x180050ede  mov     rcx, rsi
0x180050ee1  mov     rax, rdi
0x180050ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ee9  nop
0x180050eea  mov     rax, [rsi]
0x180050eed  mov     rbx, [rax+60h]
0x180050ef1  mov     [rsp+4C0h+var_460], r12
0x180050ef6  mov     r9d, 8; unsigned int
0x180050efc  lea     r8d, [r9+1]; unsigned int
0x180050f00  lea     rdx, ?c_jsonRegExists@RegistryJson@@0QBGB; "IfExists"
0x180050f07  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x180050f0c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180050f11  nop
0x180050f12  lea     r8, [r15+35h]
0x180050f16  mov     rdx, [rsp+4C0h+var_460]
0x180050f1b  mov     rcx, rsi
0x180050f1e  mov     rax, rbx
0x180050f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f26  nop
0x180050f27  test    eax, eax
0x180050f29  jns     short loc_180050F2F
0x180050f2b  mov     [r15+35h], r12b
0x180050f2f  mov     rax, [rsi]
0x180050f32  mov     rbx, [rax+60h]
0x180050f36  mov     [rsp+4C0h+var_460], r12
0x180050f3b  mov     r9d, 0Ah; unsigned int
0x180050f41  lea     r8d, [r9+1]; unsigned int
0x180050f45  lea     rdx, ?c_jsonIgnoreWild@RegistryJson@@0QBGB; "IgnoreWild"
0x180050f4c  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x180050f51  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180050f56  nop
0x180050f57  lea     r8, [r15+36h]
0x180050f5b  mov     rdx, [rsp+4C0h+var_460]
0x180050f60  mov     rcx, rsi
0x180050f63  mov     rax, rbx
0x180050f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f6b  nop
0x180050f6c  test    eax, eax
0x180050f6e  jns     short loc_180050F74
0x180050f70  mov     [r15+36h], r12b
0x180050f74  mov     ebx, r12d
0x180050f77  mov     rcx, [rsp+4C0h+string]; string
0x180050f7c  call    cs:__imp_WindowsDeleteString
0x180050f82  mov     eax, ebx
0x180050f84  mov     rcx, [rbp+3C0h+var_40]
0x180050f8b  xor     rcx, rsp; StackCookie
0x180050f8e  call    __security_check_cookie
0x180050f93  add     rsp, 490h
0x180050f9a  pop     r15
0x180050f9c  pop     r14
0x180050f9e  pop     r12
0x180050fa0  pop     rdi
0x180050fa1  pop     rsi
0x180050fa2  pop     rbx
0x180050fa3  pop     rbp
0x180050fa4  retn
```
