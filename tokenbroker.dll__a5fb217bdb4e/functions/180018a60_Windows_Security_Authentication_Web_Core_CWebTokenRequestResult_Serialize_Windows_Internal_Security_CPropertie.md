# Windows::Security::Authentication::Web::Core::CWebTokenRequestResult::Serialize(Windows::Internal::Security::CPropertiesSerializer &)

- ea: `0x180018a60`
- end: `0x180018e22`
- name: `?Serialize@CWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@AEAAJAEAVCPropertiesSerializer@5Internal@6@@Z`
- size: `962`
- prototype: `int(Windows::Security::Authentication::Web::Core::CWebTokenRequestResult *__hidden this, struct Windows::Internal::Security::CPropertiesSerializer *)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800189b0`
- `0x1800f7e90`
- `0x1800f8310`

## callees

- `0x18000bd40`
- `0x1800185b4`
- `0x18001873c`
- `0x180018a60`
- `0x180018e28`
- `0x180019898`
- `0x18001a00c`
- `0x180046764`
- `0x180057ad0`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018b0f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018b0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018b5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018db7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018b5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018db7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018d01`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018d5d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018d74`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018d8b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018dd0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018de7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018dfd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018d01`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018d5d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018d74`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018d8b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018dd0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018de7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018dfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018add`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018b30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018bef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018c3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018cbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018d20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018add`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018b30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018bef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018c3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018cbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018d20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180018b7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180018b7a`

## string_xrefs

- `0x180018c93`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x180018d9d`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x180018b96`: `WTResult_ExtensionId`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Security::Authentication::Web::Core::CWebTokenRequestResult::Serialize(
        Windows::Security::Authentication::Web::Core::CWebTokenRequestResult *this,
        struct Windows::Internal::Security::CPropertiesSerializer *a2)
{
  __int64 v4; // rcx
  int v5; // ebx
  unsigned int v6; // esi
  int v7; // eax
  unsigned int v8; // esi
  HSTRING v9; // rbx
  struct Windows::Storage::Streams::IBuffer *v10; // rbx
  __int64 v11; // rbx
  HRESULT StringReference; // eax
  __int64 v14; // rdx
  int v15; // [rsp+20h] [rbp-40h] BYREF
  char *v16; // [rsp+28h] [rbp-38h]
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v15 = 0;
  v4 = *((_QWORD *)this + 14);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v4 + 56LL))(v4, &v15);
    if ( v5 < 0 )
    {
      v14 = 1770;
      goto LABEL_26;
    }
    if ( v15 )
    {
      if ( WindowsCreateStringReference(L"WTResult_Responses", 0x12u, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v5 = Windows::Internal::Security::AddVectorToSerializer<Windows::Security::Authentication::Web::Core::WebTokenResponse *>(
             *((_QWORD *)this + 14),
             string,
             a2);
      if ( v5 < 0 )
      {
        v14 = 1778;
        goto LABEL_26;
      }
    }
  }
  AcquireSRWLockShared((PSRWLOCK)this + 21);
  v16 = (char *)this + 168;
  v6 = *((_DWORD *)this + 30);
  if ( WindowsCreateStringReference(L"WTResult_Status", 0xFu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = Windows::Internal::Security::CPropertiesSerializer::AddUInt32Property(a2, string, v6);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( this != (Windows::Security::Authentication::Web::Core::CWebTokenRequestResult *)-168LL )
      ReleaseSRWLockShared((PSRWLOCK)this + 21);
    if ( !*((_QWORD *)this + 17) )
      goto LABEL_45;
    if ( WindowsCreateStringReference(L"WTResult_Error", 0xEu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v5 = Windows::Internal::Security::AddObjectToSerializer<Windows::Security::Authentication::Web::Core::IWebProviderError *>(
           *((_QWORD *)this + 17),
           string,
           a2);
    if ( v5 < 0 )
    {
      v14 = 1800;
    }
    else
    {
LABEL_45:
      if ( WindowsIsStringEmpty(*((HSTRING *)this + 18)) )
        goto LABEL_17;
      v9 = (HSTRING)*((_QWORD *)this + 18);
      if ( WindowsCreateStringReference(L"WTResult_ExtensionId", 0x14u, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v5 = Windows::Internal::Security::CPropertiesSerializer::AddStringProperty(a2, string, v9);
      if ( v5 >= 0 )
      {
LABEL_17:
        v10 = (struct Windows::Storage::Streams::IBuffer *)*((_QWORD *)this + 16);
        if ( !v10 )
          goto LABEL_18;
        if ( WindowsCreateStringReference(L"WTResult_RequestId", 0x12u, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v5 = Windows::Internal::Security::CPropertiesSerializer::AddBufferProperty(a2, string, v10);
        if ( v5 < 0 )
        {
          v14 = 1821;
        }
        else
        {
LABEL_18:
          v11 = *((_QWORD *)this + 19);
          if ( WindowsCreateStringReference(L"WTResult_ExpirationTime", 0x17u, &hstringHeader, &string) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          v5 = Windows::Internal::Security::CPropertiesSerializer::AddInt64Property(a2, string, v11);
          if ( v5 < 0 )
          {
            v14 = 1830;
          }
          else
          {
            if ( !*((_QWORD *)this + 20) )
              return (unsigned int)v5;
            *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
            StringReference = WindowsCreateStringReference(
                                L"WTResult_Provider",
                                0x11u,
                                (HSTRING_HEADER *)&string,
                                (HSTRING *)&hstringHeader.Reserved.Reserved2[16]);
            if ( StringReference < 0 )
            {
              RaiseException(StringReference, 1u, 0, 0);
              __debugbreak();
            }
            v5 = Windows::Internal::Security::AddObjectToSerializer<Windows::Security::Credentials::IWebAccountProvider *>(
                   *((_QWORD *)this + 20),
                   *(_QWORD *)&hstringHeader.Reserved.Reserved2[16],
                   a2);
            if ( v5 >= 0 )
              return (unsigned int)v5;
            v14 = 1837;
          }
        }
      }
      else
      {
        v14 = 1810;
      }
    }
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
      (const char *)(unsigned int)v5,
      v15);
    return (unsigned int)v5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6FD,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
    (const char *)(unsigned int)v7,
    v15);
  if ( this != (Windows::Security::Authentication::Web::Core::CWebTokenRequestResult *)-168LL )
    ReleaseSRWLockShared((PSRWLOCK)this + 21);
  return v8;
}

```

## disassembly

```asm
0x180018a60  mov     [rsp-28h+arg_10], rbx
0x180018a65  mov     [rsp-28h+arg_18], rsi
0x180018a6a  push    rbp
0x180018a6b  push    rdi
0x180018a6c  push    r12
0x180018a6e  push    r13
0x180018a70  push    r14
0x180018a72  mov     rbp, rsp
0x180018a75  sub     rsp, 60h
0x180018a79  mov     rax, cs:__security_cookie
0x180018a80  xor     rax, rsp
0x180018a83  mov     [rbp+var_10], rax
0x180018a87  mov     r14, rdx
0x180018a8a  mov     rdi, rcx
0x180018a8d  mov     [rbp+var_40], 0
0x180018a94  mov     rcx, [rcx+70h]
0x180018a98  mov     r12d, 1
0x180018a9e  mov     r13d, 0C000000Dh
0x180018aa4  test    rcx, rcx
0x180018aa7  jz      short loc_180018B05
0x180018aa9  mov     rax, [rcx]
0x180018aac  lea     rdx, [rbp+var_40]
0x180018ab0  mov     rax, [rax+38h]
0x180018ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ab9  mov     ebx, eax
0x180018abb  test    eax, eax
0x180018abd  js      loc_180018C8E
0x180018ac3  cmp     [rbp+var_40], 0
0x180018ac7  jbe     short loc_180018B05
0x180018ac9  lea     r9, [rbp+string]; string
0x180018acd  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180018ad1  lea     edx, [r12+11h]; length
0x180018ad6  lea     rcx, aWtresultRespon; "WTResult_Responses"
0x180018add  call    cs:__imp_WindowsCreateStringReference
0x180018ae3  test    eax, eax
0x180018ae5  js      loc_180018D51
0x180018aeb  mov     r8, r14
0x180018aee  mov     rdx, [rbp+string]
0x180018af2  mov     rcx, [rdi+70h]
0x180018af6  call    ??$AddVectorToSerializer@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@@Security@Internal@Windows@@YAJPEAU?$IVector@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@@Collections@Foundation@2@PEAUHSTRING__@@AEAVCPropertiesSerializer@012@@Z; Windows::Internal::Security::AddVectorToSerializer<Windows::Security::Authentication::Web::Core::WebTokenResponse *>(Windows::Foundation::Collections::IVector<Windows::Security::Authentication::Web::Core::WebTokenResponse *> *,HSTRING__ *,Windows::Internal::Security::CPropertiesSerializer &)
0x180018afb  mov     ebx, eax
0x180018afd  test    eax, eax
0x180018aff  js      loc_180018E04
0x180018b05  lea     rbx, [rdi+0A8h]
0x180018b0c  mov     rcx, rbx; SRWLock
0x180018b0f  call    cs:__imp_AcquireSRWLockShared
0x180018b15  mov     [rbp+var_38], rbx
0x180018b19  mov     esi, [rdi+78h]
0x180018b1c  lea     r9, [rbp+string]; string
0x180018b20  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180018b24  mov     edx, 0Fh; length
0x180018b29  lea     rcx, aWtresultStatus; "WTResult_Status"
0x180018b30  call    cs:__imp_WindowsCreateStringReference
0x180018b36  test    eax, eax
0x180018b38  js      loc_180018CF5
0x180018b3e  mov     r8d, esi; unsigned int
0x180018b41  mov     rdx, [rbp+string]; HSTRING
0x180018b45  mov     rcx, r14; this
0x180018b48  call    ?AddUInt32Property@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@I@Z; Windows::Internal::Security::CPropertiesSerializer::AddUInt32Property(HSTRING__ *,uint)
0x180018b4d  mov     esi, eax
0x180018b4f  test    eax, eax
0x180018b51  js      loc_180018D96
0x180018b57  test    rbx, rbx
0x180018b5a  jz      short loc_180018B65
0x180018b5c  mov     rcx, rbx; SRWLock
0x180018b5f  call    cs:__imp_ReleaseSRWLockShared
0x180018b65  cmp     qword ptr [rdi+88h], 0
0x180018b6d  jnz     loc_180018CA8
0x180018b73  mov     rcx, [rdi+90h]; string
0x180018b7a  call    cs:__imp_WindowsIsStringEmpty
0x180018b80  test    eax, eax
0x180018b82  jnz     short loc_180018BC4
0x180018b84  mov     rbx, [rdi+90h]
0x180018b8b  lea     r9, [rbp+string]; string
0x180018b8f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180018b93  lea     edx, [rax+14h]; length
0x180018b96  lea     rcx, aWtresultExtens; "WTResult_ExtensionId"
0x180018b9d  call    cs:__imp_WindowsCreateStringReference
0x180018ba3  test    eax, eax
0x180018ba5  js      loc_180018DDB
0x180018bab  mov     r8, rbx; HSTRING
0x180018bae  mov     rdx, [rbp+string]; HSTRING
0x180018bb2  mov     rcx, r14; this
0x180018bb5  call    ?AddStringProperty@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::Internal::Security::CPropertiesSerializer::AddStringProperty(HSTRING__ *,HSTRING__ *)
0x180018bba  mov     ebx, eax
0x180018bbc  test    eax, eax
0x180018bbe  js      loc_180018CEE
0x180018bc4  mov     rbx, [rdi+80h]
0x180018bcb  test    rbx, rbx
0x180018bce  jnz     loc_180018D0C
0x180018bd4  mov     rbx, [rdi+98h]
0x180018bdb  lea     r9, [rbp+string]; string
0x180018bdf  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180018be3  mov     edx, 17h; length
0x180018be8  lea     rcx, aWtresultExpira; "WTResult_ExpirationTime"
0x180018bef  call    cs:__imp_WindowsCreateStringReference
0x180018bf5  test    eax, eax
0x180018bf7  js      loc_180018D68
0x180018bfd  mov     r8, rbx; __int64
0x180018c00  mov     rdx, [rbp+string]; HSTRING
0x180018c04  mov     rcx, r14; this
0x180018c07  call    ?AddInt64Property@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@_J@Z; Windows::Internal::Security::CPropertiesSerializer::AddInt64Property(HSTRING__ *,__int64)
0x180018c0c  mov     ebx, eax
0x180018c0e  test    eax, eax
0x180018c10  js      loc_180018E0E
0x180018c16  cmp     qword ptr [rdi+0A0h], 0
0x180018c1e  jz      short loc_180018C67
0x180018c20  mov     qword ptr [rbp+hstringHeader.Reserved+10h], 0
0x180018c28  lea     r9, [rbp+hstringHeader.Reserved+10h]; string
0x180018c2c  lea     r8, [rbp+string]; hstringHeader
0x180018c30  mov     edx, 11h; length
0x180018c35  lea     rcx, aWtresultProvid; "WTResult_Provider"
0x180018c3c  call    cs:__imp_WindowsCreateStringReference
0x180018c42  test    eax, eax
0x180018c44  js      loc_180018DF2
0x180018c4a  mov     r8, r14
0x180018c4d  mov     rdx, qword ptr [rbp+hstringHeader.Reserved+10h]
0x180018c51  mov     rcx, [rdi+0A0h]
0x180018c58  call    ??$AddObjectToSerializer@PEAUIWebAccountProvider@Credentials@Security@Windows@@@Security@Internal@Windows@@YAJPEAUIWebAccountProvider@Credentials@02@PEAUHSTRING__@@AEAVCPropertiesSerializer@012@@Z; Windows::Internal::Security::AddObjectToSerializer<Windows::Security::Credentials::IWebAccountProvider *>(Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ *,Windows::Internal::Security::CPropertiesSerializer &)
0x180018c5d  mov     ebx, eax
0x180018c5f  test    eax, eax
0x180018c61  js      loc_180018E18
0x180018c67  mov     eax, ebx
0x180018c69  mov     rcx, [rbp+var_10]
0x180018c6d  xor     rcx, rsp; StackCookie
0x180018c70  call    __security_check_cookie
0x180018c75  lea     r11, [rsp+60h+var_s0]
0x180018c7a  mov     rbx, [r11+40h]
0x180018c7e  mov     rsi, [r11+48h]
0x180018c82  mov     rsp, r11
0x180018c85  pop     r14
0x180018c87  pop     r13
0x180018c89  pop     r12
0x180018c8b  pop     rdi
0x180018c8c  pop     rbp
0x180018c8d  retn
0x180018c8e  mov     edx, 6EAh; void *
0x180018c93  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x180018c9a  mov     r9d, ebx; char *
0x180018c9d  mov     rcx, [rbp+28h]; this
0x180018ca1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018ca6  jmp     short loc_180018C67
0x180018ca8  lea     r9, [rbp+string]; string
0x180018cac  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180018cb0  mov     edx, 0Eh; length
0x180018cb5  lea     rcx, aWtresultError; "WTResult_Error"
0x180018cbc  call    cs:__imp_WindowsCreateStringReference
0x180018cc2  test    eax, eax
0x180018cc4  js      loc_180018D7F
0x180018cca  mov     r8, r14
0x180018ccd  mov     rdx, [rbp+string]
0x180018cd1  mov     rcx, [rdi+88h]
0x180018cd8  call    ??$AddObjectToSerializer@PEAUIWebProviderError@Core@Web@Authentication@Security@Windows@@@Security@Internal@Windows@@YAJPEAUIWebProviderError@Core@Web@Authentication@02@PEAUHSTRING__@@AEAVCPropertiesSerializer@012@@Z; Windows::Internal::Security::AddObjectToSerializer<Windows::Security::Authentication::Web::Core::IWebProviderError *>(Windows::Security::Authentication::Web::Core::IWebProviderError *,HSTRING__ *,Windows::Internal::Security::CPropertiesSerializer &)
0x180018cdd  mov     ebx, eax
0x180018cdf  test    eax, eax
0x180018ce1  jns     loc_180018B73
0x180018ce7  mov     edx, 708h
0x180018cec  jmp     short loc_180018C93
0x180018cee  mov     edx, 712h
0x180018cf3  jmp     short loc_180018C93
0x180018cf5  xor     r9d, r9d; lpArguments
0x180018cf8  xor     r8d, r8d; nNumberOfArguments
0x180018cfb  mov     edx, r12d; dwExceptionFlags
0x180018cfe  mov     ecx, r13d; dwExceptionCode
0x180018d01  call    cs:__imp_RaiseException
0x180018d07  jmp     loc_180018B3E
0x180018d0c  lea     r9, [rbp+string]; string
0x180018d10  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180018d14  mov     edx, 12h; length
0x180018d19  lea     rcx, aWtresultReques; "WTResult_RequestId"
0x180018d20  call    cs:__imp_WindowsCreateStringReference
0x180018d26  test    eax, eax
0x180018d28  js      loc_180018DC4
0x180018d2e  mov     r8, rbx; struct Windows::Storage::Streams::IBuffer *
0x180018d31  mov     rdx, [rbp+string]; HSTRING
0x180018d35  mov     rcx, r14; this
0x180018d38  call    ?AddBufferProperty@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@PEAUIBuffer@Streams@Storage@4@@Z; Windows::Internal::Security::CPropertiesSerializer::AddBufferProperty(HSTRING__ *,Windows::Storage::Streams::IBuffer *)
0x180018d3d  mov     ebx, eax
0x180018d3f  test    eax, eax
0x180018d41  jns     loc_180018BD4
0x180018d47  mov     edx, 71Dh
0x180018d4c  jmp     loc_180018C93
0x180018d51  xor     r9d, r9d; lpArguments
0x180018d54  xor     r8d, r8d; nNumberOfArguments
0x180018d57  mov     edx, r12d; dwExceptionFlags
0x180018d5a  mov     ecx, r13d; dwExceptionCode
0x180018d5d  call    cs:__imp_RaiseException
0x180018d63  jmp     loc_180018AEB
0x180018d68  xor     r9d, r9d; lpArguments
0x180018d6b  xor     r8d, r8d; nNumberOfArguments
0x180018d6e  mov     edx, r12d; dwExceptionFlags
0x180018d71  mov     ecx, r13d; dwExceptionCode
0x180018d74  call    cs:__imp_RaiseException
0x180018d7a  jmp     loc_180018BFD
0x180018d7f  xor     r9d, r9d; lpArguments
0x180018d82  xor     r8d, r8d; nNumberOfArguments
0x180018d85  mov     edx, r12d; dwExceptionFlags
0x180018d88  mov     ecx, r13d; dwExceptionCode
0x180018d8b  call    cs:__imp_RaiseException
0x180018d91  jmp     loc_180018CCA
0x180018d96  mov     rcx, [rbp+28h]; this
0x180018d9a  mov     r9d, esi; char *
0x180018d9d  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x180018da4  mov     edx, 6FDh; void *
0x180018da9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018dae  nop
0x180018daf  test    rbx, rbx
0x180018db2  jz      short loc_180018DBD
0x180018db4  mov     rcx, rbx; SRWLock
0x180018db7  call    cs:__imp_ReleaseSRWLockShared
0x180018dbd  mov     eax, esi
0x180018dbf  jmp     loc_180018C69
0x180018dc4  xor     r9d, r9d; lpArguments
0x180018dc7  xor     r8d, r8d; nNumberOfArguments
0x180018dca  mov     edx, r12d; dwExceptionFlags
0x180018dcd  mov     ecx, r13d; dwExceptionCode
0x180018dd0  call    cs:__imp_RaiseException
0x180018dd6  jmp     loc_180018D2E
0x180018ddb  xor     r9d, r9d; lpArguments
0x180018dde  xor     r8d, r8d; nNumberOfArguments
0x180018de1  mov     edx, r12d; dwExceptionFlags
0x180018de4  mov     ecx, r13d; dwExceptionCode
0x180018de7  call    cs:__imp_RaiseException
0x180018ded  jmp     loc_180018BAB
0x180018df2  xor     r9d, r9d; lpArguments
0x180018df5  xor     r8d, r8d; nNumberOfArguments
0x180018df8  mov     edx, r12d; dwExceptionFlags
0x180018dfb  mov     ecx, eax; dwExceptionCode
0x180018dfd  call    cs:__imp_RaiseException
0x180018e03  int     3; Trap to Debugger
0x180018e04  mov     edx, 6F2h
0x180018e09  jmp     loc_180018C93
0x180018e0e  mov     edx, 726h
0x180018e13  jmp     loc_180018C93
0x180018e18  mov     edx, 72Dh
0x180018e1d  jmp     loc_180018C93
```
