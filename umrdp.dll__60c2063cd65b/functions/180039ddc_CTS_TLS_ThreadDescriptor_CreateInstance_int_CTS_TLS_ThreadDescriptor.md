# CTS_TLS_ThreadDescriptor::CreateInstance(int,CTS_TLS_ThreadDescriptor * *)

- ea: `0x180039ddc`
- end: `0x180039fd0`
- name: `?CreateInstance@CTS_TLS_ThreadDescriptor@@SAJHPEAPEAV1@@Z`
- size: `500`
- prototype: `__int64 __fastcall(int, struct CTS_TLS_ThreadDescriptor **)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800392d0`
- `0x18003cf20`

## callees

- `0x1800010b0`
- `0x18000a118`
- `0x18000b98c`
- `0x18000bd04`
- `0x18001bae0`
- `0x18003864c`
- `0x180039ddc`
- `0x18003b620`
- `0x180049010`

## string_xrefs

- `0x180039e0a`: `CreateInstance`
- `0x180039f48`: `CreateInstance`
- `0x180039e23`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180039f61`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180039e35`: `Thread descriptor creation NULL pointer passed`
- `0x180039f73`: `OOM on thread descriptor`
- `0x180039efc`: `spThreadDescriptor init failed`

## pseudocode

```c
__int64 __fastcall CTS_TLS_ThreadDescriptor::CreateInstance(
        int a1,
        struct CTS_TLS_ThreadDescriptor **a2,
        int a3,
        int a4)
{
  int v6; // ebx
  CTS_TLS_ThreadDescriptor *v7; // rax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  CTS_TLS_ThreadDescriptor *v11; // rdi
  __int64 v12; // rcx
  int ActivityIdPrefix; // eax
  const char *v15; // [rsp+50h] [rbp-20h] BYREF
  const char *v16; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v17[2]; // [rsp+60h] [rbp-10h] BYREF
  int v18; // [rsp+98h] [rbp+28h] BYREF
  int v19; // [rsp+A0h] [rbp+30h] BYREF
  CTS_TLS_ThreadDescriptor *v20; // [rsp+A8h] [rbp+38h] BYREF

  v20 = 0;
  if ( a2 )
  {
    v7 = (CTS_TLS_ThreadDescriptor *)operator new(0x200u);
    if ( v7 && (v11 = CTS_TLS_ThreadDescriptor::CTS_TLS_ThreadDescriptor(v7, a1)) != 0 )
    {
      TCntPtr<CTSBufferResult>::SafeRelease(&v20);
      v12 = *((_QWORD *)v11 + 4);
      v20 = v11;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
      v6 = CTS_TLS_ThreadDescriptor::Initialize((CTS_TLS_ThreadDescriptor *)((char *)v11 + 8));
      if ( v6 >= 0 )
      {
        v20 = 0;
        *a2 = v11;
      }
      else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
             && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          155,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          ActivityIdPrefix,
          (__int64)"spThreadDescriptor init failed",
          v6);
      }
    }
    else
    {
      if ( (unsigned int)dword_18005C008 > 2 )
      {
        v18 = 3340;
        v17[0] = "CreateInstance";
        v19 = -2147467259;
        v16 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v15 = "OOM on thread descriptor";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v8,
          (unsigned int)&byte_180054D97,
          v9,
          v10,
          (__int64)&v15,
          (__int64)&v19,
          (__int64)&v16,
          (__int64)&v18,
          (__int64)v17);
      }
      v6 = -2147024882;
    }
  }
  else
  {
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      v18 = 3333;
      v15 = "CreateInstance";
      v19 = -2147467259;
      v16 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v17[0] = "Thread descriptor creation NULL pointer passed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        a1,
        (unsigned int)&dword_180054DDC,
        a3,
        a4,
        (__int64)v17,
        (__int64)&v19,
        (__int64)&v16,
        (__int64)&v18,
        (__int64)&v15);
    }
    v6 = -2147024809;
  }
  TCntPtr<CTSBufferResult>::SafeRelease(&v20);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180039ddc  mov     r11, rsp
0x180039ddf  mov     [r11+8], rbx
0x180039de3  push    rbp
0x180039de4  push    rsi
0x180039de5  push    rdi
0x180039de6  mov     rbp, rsp
0x180039de9  sub     rsp, 70h
0x180039ded  mov     rsi, rdx
0x180039df0  mov     [rbp+arg_18], 0
0x180039df8  mov     ebx, ecx
0x180039dfa  test    rdx, rdx
0x180039dfd  jnz     short loc_180039E77
0x180039dff  mov     eax, cs:dword_18005C008
0x180039e05  cmp     eax, 2
0x180039e08  jbe     short loc_180039E6D
0x180039e0a  lea     rax, aCreateinstance_1; "CreateInstance"
0x180039e11  mov     [rbp+arg_8], 0D05h
0x180039e18  mov     [rbp+var_20], rax
0x180039e1c  lea     rdx, dword_180054DDC
0x180039e23  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180039e2a  mov     [rbp+arg_10], 80004005h
0x180039e31  mov     [rbp+var_18], rax
0x180039e35  lea     rax, aThreadDescript; "Thread descriptor creation NULL pointer"...
0x180039e3c  mov     [rbp+var_10], rax
0x180039e40  lea     rax, [rbp+var_20]
0x180039e44  mov     [r11-48h], rax
0x180039e48  lea     rax, [rbp+arg_8]
0x180039e4c  mov     [r11-50h], rax
0x180039e50  lea     rax, [rbp+var_18]
0x180039e54  mov     [r11-58h], rax
0x180039e58  lea     rax, [rbp+arg_10]
0x180039e5c  mov     [r11-60h], rax
0x180039e60  lea     rax, [rbp+var_10]
0x180039e64  mov     [r11-68h], rax
0x180039e68  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180039e6d  mov     ebx, 80070057h
0x180039e72  jmp     loc_180039FB5
0x180039e77  mov     ecx, 200h; Size
0x180039e7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039e81  test    rax, rax
0x180039e84  jz      loc_180039F3D
0x180039e8a  mov     edx, ebx; int
0x180039e8c  mov     rcx, rax; this
0x180039e8f  call    ??0CTS_TLS_ThreadDescriptor@@AEAA@H@Z; CTS_TLS_ThreadDescriptor::CTS_TLS_ThreadDescriptor(int)
0x180039e94  mov     rdi, rax
0x180039e97  test    rax, rax
0x180039e9a  jz      loc_180039F3D
0x180039ea0  lea     rcx, [rbp+arg_18]
0x180039ea4  call    ?SafeRelease@?$TCntPtr@VCTSBufferResult@@@@AEAAXXZ; TCntPtr<CTSBufferResult>::SafeRelease(void)
0x180039ea9  mov     rcx, [rdi+20h]
0x180039ead  mov     [rbp+arg_18], rdi
0x180039eb1  mov     rax, [rcx]
0x180039eb4  mov     rax, [rax+8]
0x180039eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ebd  lea     rcx, [rdi+8]; this
0x180039ec1  call    ?Initialize@CTS_TLS_ThreadDescriptor@@EEAAJXZ; CTS_TLS_ThreadDescriptor::Initialize(void)
0x180039ec6  mov     ebx, eax
0x180039ec8  test    eax, eax
0x180039eca  jns     short loc_180039F30
0x180039ecc  mov     rcx, cs:WPP_GLOBAL_Control
0x180039ed3  lea     rax, WPP_GLOBAL_Control
0x180039eda  cmp     rcx, rax
0x180039edd  jz      loc_180039FB5
0x180039ee3  test    byte ptr [rcx+1Ch], 8
0x180039ee7  jz      loc_180039FB5
0x180039eed  cmp     byte ptr [rcx+19h], 2
0x180039ef1  jb      loc_180039FB5
0x180039ef7  call    RdpX_GetActivityIdPrefix
0x180039efc  lea     rcx, aSpthreaddescri; "spThreadDescriptor init failed"
0x180039f03  mov     dword ptr [rsp+70h+var_48], ebx
0x180039f07  mov     [rsp+70h+var_50], rcx
0x180039f0c  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180039f13  mov     rcx, cs:WPP_GLOBAL_Control
0x180039f1a  mov     edx, 9Bh
0x180039f1f  mov     r9d, eax
0x180039f22  mov     rcx, [rcx+10h]
0x180039f26  call    WPP_SF_DsD
0x180039f2b  jmp     loc_180039FB5
0x180039f30  mov     [rbp+arg_18], 0
0x180039f38  mov     [rsi], rdi
0x180039f3b  jmp     short loc_180039FB5
0x180039f3d  mov     eax, cs:dword_18005C008
0x180039f43  cmp     eax, 2
0x180039f46  jbe     short loc_180039FB0
0x180039f48  lea     rax, aCreateinstance_1; "CreateInstance"
0x180039f4f  mov     [rbp+arg_8], 0D0Ch
0x180039f56  mov     [rbp+var_10], rax
0x180039f5a  lea     rdx, byte_180054D97
0x180039f61  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180039f68  mov     [rbp+arg_10], 80004005h
0x180039f6f  mov     [rbp+var_18], rax
0x180039f73  lea     rax, aOomOnThreadDes; "OOM on thread descriptor"
0x180039f7a  mov     [rbp+var_20], rax
0x180039f7e  lea     rax, [rbp+var_10]
0x180039f82  mov     [rsp+70h+var_30], rax
0x180039f87  lea     rax, [rbp+arg_8]
0x180039f8b  mov     [rsp+70h+var_38], rax
0x180039f90  lea     rax, [rbp+var_18]
0x180039f94  mov     [rsp+70h+var_40], rax
0x180039f99  lea     rax, [rbp+arg_10]
0x180039f9d  mov     [rsp+70h+var_48], rax
0x180039fa2  lea     rax, [rbp+var_20]
0x180039fa6  mov     [rsp+70h+var_50], rax
0x180039fab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180039fb0  mov     ebx, 8007000Eh
0x180039fb5  lea     rcx, [rbp+arg_18]
0x180039fb9  call    ?SafeRelease@?$TCntPtr@VCTSBufferResult@@@@AEAAXXZ; TCntPtr<CTSBufferResult>::SafeRelease(void)
0x180039fbe  mov     eax, ebx
0x180039fc0  mov     rbx, [rsp+70h+arg_0]
0x180039fc8  add     rsp, 70h
0x180039fcc  pop     rdi
0x180039fcd  pop     rsi
0x180039fce  pop     rbp
0x180039fcf  retn
```
