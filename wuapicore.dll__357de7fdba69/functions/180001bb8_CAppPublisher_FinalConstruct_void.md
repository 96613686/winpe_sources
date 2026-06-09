# CAppPublisher::FinalConstruct(void)

- ea: `0x180001bb8`
- end: `0x180001fee`
- name: `?FinalConstruct@CAppPublisher@@QEAAJXZ`
- size: `1078`
- prototype: `__int64 __fastcall(CAppPublisher *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800792dc`

## callees

- `0x180001bb8`
- `0x180006ac4`
- `0x180080de8`
- `0x18008e39c`
- `0x180090bc8`
- `0x180091dfc`
- `0x18009ae75`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180001c7e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180001d25`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180001c7e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180001d25`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180001c48`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180001c48`

## string_xrefs

- `0x180001d9e`: `C:\__w\1\s\src\Client\comapi\AppPublisher.cpp`
- `0x180001fc1`: `C:\__w\1\s\src\Client\comapi\AppPublisher.cpp`
- `0x180001c92`: `Connected to update session.`
- `0x180001cd0`: `User is %wsallowed to install published content.`
- `0x180001db6`: `Found %d potential services`
- `0x180001e4d`: `Service %d is %wsmanaged`
- `0x180001eb7`: `Managed service %wsfound.`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CAppPublisher::FinalConstruct(LPUNKNOWN *this)
{
  IUnknown *v2; // rax
  HRESULT FreeThreadedMarshaler; // ebx
  __int64 v4; // rdx
  LPVOID v5; // rbx
  __int64 (__fastcall *v6)(LPVOID, __int64 *); // rdi
  unsigned int v7; // edi
  int v8; // eax
  const wchar_t *v9; // rax
  const wchar_t *v10; // rax
  int v11; // ecx
  const wchar_t *WUPolicyRegPath; // rax
  __int64 v13; // rcx
  __int64 v15; // rdx
  int ppv; // [rsp+28h] [rbp-89h]
  int ppva; // [rsp+28h] [rbp-89h]
  __int64 v18; // [rsp+38h] [rbp-79h]
  _WORD v19[2]; // [rsp+48h] [rbp-69h] BYREF
  int v20; // [rsp+4Ch] [rbp-65h] BYREF
  __int64 v21; // [rsp+50h] [rbp-61h] BYREF
  int v22; // [rsp+58h] [rbp-59h] BYREF
  __int64 v23; // [rsp+60h] [rbp-51h] BYREF
  LPVOID v24; // [rsp+68h] [rbp-49h] BYREF
  _OWORD v25[2]; // [rsp+78h] [rbp-39h] BYREF
  __int64 v26; // [rsp+98h] [rbp-19h]
  __int64 v27; // [rsp+A0h] [rbp-11h]
  __int128 v28; // [rsp+A8h] [rbp-9h]
  __int128 v29; // [rsp+B8h] [rbp+7h]
  __int128 v30; // [rsp+C8h] [rbp+17h]
  __int128 v31; // [rsp+D8h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+5Fh]

  v24 = 0;
  v21 = 0;
  v20 = 0;
  memset_0(v25, 0, 0x70u);
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  memset(v25, 0, sizeof(v25));
  v26 = 0;
  v2 = (IUnknown *)((__int64 (__fastcall *)(LPUNKNOWN *))(*this)[7].lpVtbl)(this);
  FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v2, this + 8);
  if ( FreeThreadedMarshaler < 0 )
  {
    v4 = 64;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\AppPublisher.cpp",
      (const char *)(unsigned int)FreeThreadedMarshaler,
      ppv);
    goto LABEL_31;
  }
  FreeThreadedMarshaler = CoCreateInstance(
                            &CLSID_UpdateSession,
                            0,
                            0x17u,
                            &GUID_816858a4_260d_4260_933a_2585f1abc76b,
                            (LPVOID *)this + 9);
  if ( FreeThreadedMarshaler < 0 )
  {
    v4 = 67;
    goto LABEL_15;
  }
  WUTrace(0, 0, 0x10000, 4, 0, L"Connected to update session.");
  *((_DWORD *)this + 21) = 1;
  WUTrace(0, 0, 0x10000, 4, 0, L"User is %wsallowed to install published content.", &szDataDescr);
  if ( v24 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  FreeThreadedMarshaler = CoCreateInstance(
                            &CLSID_UpdateServiceManager,
                            0,
                            0x17u,
                            &GUID_23857e3c_02ba_44a3_9423_b1c900805f37,
                            &v24);
  if ( FreeThreadedMarshaler < 0 )
  {
    v4 = 86;
    goto LABEL_15;
  }
  v5 = v24;
  v6 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v24 + 56LL);
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  FreeThreadedMarshaler = v6(v5, &v21);
  if ( FreeThreadedMarshaler < 0 )
  {
    v4 = 90;
    goto LABEL_15;
  }
  FreeThreadedMarshaler = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 72LL))(v21, &v20);
  if ( FreeThreadedMarshaler < 0 )
  {
    v4 = 94;
    goto LABEL_15;
  }
  WUTrace(0, 0, 0x10000, 5, 0, L"Found %d potential services");
  v7 = 0;
  if ( v20 <= 0 )
  {
LABEL_25:
    v10 = L"NOT ";
    if ( *((_DWORD *)this + 20) )
      v10 = &szDataDescr;
    WUTrace(0, 0, 0x10000, 4, 0, L"Managed service %wsfound.", v10);
    v22 = 0;
    WUPolicyRegPath = GetWUPolicyRegPath(v11);
    if ( (int)RegQueryDwordValue(v13, WUPolicyRegPath, L"DisableAppPublisher", &v22) >= 0 && v22 == 1 )
    {
      *((_DWORD *)this + 22) = 1;
      WUTrace(0, 0, 0x10000, 4, 0, L"AppPublisher is disabled through policy \"DisableAppPublisher\".");
    }
    FreeThreadedMarshaler = 0;
  }
  else
  {
    while ( 1 )
    {
      v23 = 0;
      v19[0] = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 56LL))(v21, v7, &v23);
      FreeThreadedMarshaler = v8;
      if ( v8 < 0 )
        break;
      v8 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v23 + 80LL))(v23, v19);
      FreeThreadedMarshaler = v8;
      if ( v8 < 0 )
      {
        v15 = 111;
        goto LABEL_41;
      }
      v9 = L"not ";
      if ( v19[0] == 0xFFFF )
        v9 = &szDataDescr;
      LODWORD(v18) = v7;
      WUTrace(0, 0, 0x10000, 5, 0, L"Service %d is %wsmanaged", v18, v9);
      if ( v19[0] == 0xFFFF )
      {
        *((_DWORD *)this + 20) = 1;
        if ( v23 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        goto LABEL_25;
      }
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      if ( (int)++v7 >= v20 )
        goto LABEL_25;
    }
    v15 = 105;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\AppPublisher.cpp",
      (const char *)(unsigned int)v8,
      ppva);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
LABEL_31:
  CSusSecurityChecker::~CSusSecurityChecker((CSusSecurityChecker *)v25);
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v24 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
  return (unsigned int)FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x180001bb8  mov     rax, rsp
0x180001bbb  mov     [rax+10h], rbx
0x180001bbf  mov     [rax+18h], rsi
0x180001bc3  mov     [rax+20h], rdi
0x180001bc7  push    rbp
0x180001bc8  push    r12
0x180001bca  push    r14
0x180001bcc  lea     rbp, [rax-5Fh]
0x180001bd0  sub     rsp, 0F0h
0x180001bd7  mov     rax, cs:__security_cookie
0x180001bde  xor     rax, rsp
0x180001be1  mov     [rbp+57h+var_20], rax
0x180001be5  mov     rsi, rcx
0x180001be8  xor     r14d, r14d
0x180001beb  mov     [rbp+57h+var_A0], r14
0x180001bef  mov     [rbp+57h+var_B8], r14
0x180001bf3  mov     [rbp+57h+var_BC], r14d
0x180001bf7  xor     edx, edx; Val
0x180001bf9  lea     r8d, [r14+70h]; Size
0x180001bfd  lea     rcx, [rbp+57h+var_90]; void *
0x180001c01  call    memset_0
0x180001c06  mov     [rbp+57h+var_68], r14
0x180001c0a  xorps   xmm0, xmm0
0x180001c0d  movdqa  [rbp+57h+var_60], xmm0
0x180001c12  xorps   xmm1, xmm1
0x180001c15  movdqa  [rbp+57h+var_50], xmm1
0x180001c1a  movdqa  [rbp+57h+var_40], xmm0
0x180001c1f  movdqa  [rbp+57h+var_30], xmm1
0x180001c24  xor     eax, eax
0x180001c26  movups  [rbp+57h+var_90], xmm0
0x180001c2a  movups  [rbp+57h+var_80], xmm0
0x180001c2e  mov     [rbp+57h+var_70], rax
0x180001c32  mov     rax, [rsi]
0x180001c35  mov     rcx, rsi
0x180001c38  mov     rax, [rax+38h]
0x180001c3c  call    _guard_dispatch_icall
0x180001c41  mov     rcx, rax; punkOuter
0x180001c44  lea     rdx, [rsi+40h]; ppunkMarshal
0x180001c48  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180001c4e  mov     ebx, eax
0x180001c50  test    eax, eax
0x180001c52  jns     short loc_180001C5D
0x180001c54  lea     edx, [r14+40h]
0x180001c58  jmp     loc_180001D97
0x180001c5d  lea     rax, [rsi+48h]
0x180001c61  mov     [rsp+100h+ppv], rax; ppv
0x180001c66  lea     r9, _GUID_816858a4_260d_4260_933a_2585f1abc76b; riid
0x180001c6d  mov     edi, 17h
0x180001c72  mov     r8d, edi; dwClsContext
0x180001c75  xor     edx, edx; pUnkOuter
0x180001c77  lea     rcx, CLSID_UpdateSession; rclsid
0x180001c7e  call    cs:__imp_CoCreateInstance
0x180001c84  mov     ebx, eax
0x180001c86  test    eax, eax
0x180001c88  jns     short loc_180001C92
0x180001c8a  lea     edx, [rdi+2Ch]
0x180001c8d  jmp     loc_180001D97
0x180001c92  lea     rax, aConnectedToUpd; "Connected to update session."
0x180001c99  mov     [rsp+100h+var_D8], rax
0x180001c9e  mov     [rsp+100h+ppv], r14
0x180001ca3  mov     ebx, 4
0x180001ca8  mov     r9d, ebx
0x180001cab  mov     r12d, 10000h
0x180001cb1  mov     r8d, r12d
0x180001cb4  xor     edx, edx
0x180001cb6  xor     ecx, ecx
0x180001cb8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180001cbd  mov     dword ptr [rsi+54h], 1
0x180001cc4  lea     rax, szDataDescr
0x180001ccb  mov     [rsp+100h+var_D0], rax
0x180001cd0  lea     rax, aUserIsWsallowe; "User is %wsallowed to install published"...
0x180001cd7  mov     [rsp+100h+var_D8], rax
0x180001cdc  mov     [rsp+100h+ppv], r14
0x180001ce1  mov     r9d, ebx
0x180001ce4  mov     r8d, r12d
0x180001ce7  xor     edx, edx
0x180001ce9  xor     ecx, ecx
0x180001ceb  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180001cf0  mov     rcx, [rbp+57h+var_A0]
0x180001cf4  test    rcx, rcx
0x180001cf7  jz      short loc_180001D09
0x180001cf9  mov     rax, [rcx]
0x180001cfc  mov     rax, [rax+10h]
0x180001d00  call    _guard_dispatch_icall
0x180001d05  mov     [rbp+57h+var_A0], r14
0x180001d09  lea     rax, [rbp+57h+var_A0]
0x180001d0d  mov     [rsp+100h+ppv], rax; int
0x180001d12  lea     r9, _GUID_23857e3c_02ba_44a3_9423_b1c900805f37; riid
0x180001d19  mov     r8d, edi; dwClsContext
0x180001d1c  xor     edx, edx; pUnkOuter
0x180001d1e  lea     rcx, CLSID_UpdateServiceManager; rclsid
0x180001d25  call    cs:__imp_CoCreateInstance
0x180001d2b  mov     ebx, eax
0x180001d2d  test    eax, eax
0x180001d2f  jns     short loc_180001D38
0x180001d31  mov     edx, 56h ; 'V'
0x180001d36  jmp     short loc_180001D97
0x180001d38  mov     rbx, [rbp+57h+var_A0]
0x180001d3c  mov     rax, [rbx]
0x180001d3f  mov     rdi, [rax+38h]
0x180001d43  mov     rcx, [rbp+57h+var_B8]
0x180001d47  test    rcx, rcx
0x180001d4a  jz      short loc_180001D5C
0x180001d4c  mov     rdx, [rcx]
0x180001d4f  mov     rax, [rdx+10h]
0x180001d53  call    _guard_dispatch_icall
0x180001d58  mov     [rbp+57h+var_B8], r14
0x180001d5c  lea     rdx, [rbp+57h+var_B8]
0x180001d60  mov     rcx, rbx
0x180001d63  mov     rax, rdi
0x180001d66  call    _guard_dispatch_icall
0x180001d6b  mov     ebx, eax
0x180001d6d  test    eax, eax
0x180001d6f  jns     short loc_180001D78
0x180001d71  mov     edx, 5Ah ; 'Z'
0x180001d76  jmp     short loc_180001D97
0x180001d78  mov     rcx, [rbp+57h+var_B8]
0x180001d7c  mov     rax, [rcx]
0x180001d7f  lea     rdx, [rbp+57h+var_BC]
0x180001d83  mov     rax, [rax+48h]
0x180001d87  call    _guard_dispatch_icall
0x180001d8c  mov     ebx, eax
0x180001d8e  test    eax, eax
0x180001d90  jns     short loc_180001DAF
0x180001d92  mov     edx, 5Eh ; '^'; void *
0x180001d97  mov     rcx, [rbp+5Fh]; this
0x180001d9b  mov     r9d, ebx; char *
0x180001d9e  lea     r8, aCW1SSrcClientC_27; "C:\\__w\\1\\s\\src\\Client\\comapi\\App"...
0x180001da5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001daa  jmp     loc_180001F2C
0x180001daf  mov     eax, [rbp+57h+var_BC]
0x180001db2  mov     dword ptr [rsp+100h+var_D0], eax
0x180001db6  lea     rax, aFoundDPotentia; "Found %d potential services"
0x180001dbd  mov     [rsp+100h+var_D8], rax
0x180001dc2  mov     [rsp+100h+ppv], r14; int
0x180001dc7  mov     r9d, 5
0x180001dcd  mov     r8d, r12d
0x180001dd0  xor     edx, edx
0x180001dd2  xor     ecx, ecx
0x180001dd4  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180001dd9  mov     edi, r14d
0x180001ddc  cmp     [rbp+57h+var_BC], r14d
0x180001de0  jle     loc_180001E9C
0x180001de6  mov     [rbp+57h+var_A8], r14
0x180001dea  mov     [rbp+57h+var_C0], r14w
0x180001def  mov     rcx, [rbp+57h+var_B8]
0x180001df3  mov     rax, [rcx]
0x180001df6  lea     r8, [rbp+57h+var_A8]
0x180001dfa  mov     edx, edi
0x180001dfc  mov     rax, [rax+38h]
0x180001e00  call    _guard_dispatch_icall
0x180001e05  mov     ebx, eax
0x180001e07  test    eax, eax
0x180001e09  js      loc_180001FB9
0x180001e0f  mov     rcx, [rbp+57h+var_A8]
0x180001e13  mov     rax, [rcx]
0x180001e16  lea     rdx, [rbp+57h+var_C0]
0x180001e1a  mov     rax, [rax+50h]
0x180001e1e  call    _guard_dispatch_icall
0x180001e23  mov     ebx, eax
0x180001e25  test    eax, eax
0x180001e27  js      loc_180001FB2
0x180001e2d  lea     rax, aNot_0; "not "
0x180001e34  cmp     [rbp+57h+var_C0], 0FFFFh
0x180001e39  lea     rcx, szDataDescr
0x180001e40  cmovz   rax, rcx
0x180001e44  mov     [rsp+100h+var_C8], rax
0x180001e49  mov     dword ptr [rsp+100h+var_D0], edi
0x180001e4d  lea     rax, aServiceDIsWsma; "Service %d is %wsmanaged"
0x180001e54  mov     [rsp+100h+var_D8], rax
0x180001e59  mov     [rsp+100h+ppv], r14
0x180001e5e  mov     r9d, 5
0x180001e64  mov     r8d, r12d
0x180001e67  xor     edx, edx
0x180001e69  xor     ecx, ecx
0x180001e6b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180001e70  cmp     [rbp+57h+var_C0], 0FFFFh
0x180001e75  jz      loc_180001F90
0x180001e7b  mov     rcx, [rbp+57h+var_A8]
0x180001e7f  test    rcx, rcx
0x180001e82  jz      short loc_180001E91
0x180001e84  mov     rax, [rcx]
0x180001e87  mov     rax, [rax+10h]
0x180001e8b  call    _guard_dispatch_icall
0x180001e90  nop
0x180001e91  inc     edi
0x180001e93  cmp     edi, [rbp+57h+var_BC]
0x180001e96  jl      loc_180001DE6
0x180001e9c  lea     rax, aNot; "NOT "
0x180001ea3  cmp     [rsi+50h], r14d
0x180001ea7  lea     rcx, szDataDescr
0x180001eae  cmovnz  rax, rcx
0x180001eb2  mov     [rsp+100h+var_D0], rax
0x180001eb7  lea     rax, aManagedService; "Managed service %wsfound."
0x180001ebe  mov     [rsp+100h+var_D8], rax
0x180001ec3  mov     [rsp+100h+ppv], r14
0x180001ec8  mov     ebx, 4
0x180001ecd  mov     r9d, ebx
0x180001ed0  mov     r8d, r12d
0x180001ed3  xor     edx, edx
0x180001ed5  xor     ecx, ecx
0x180001ed7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180001edc  mov     [rbp+57h+var_B0], r14d
0x180001ee0  call    ?GetWUPolicyRegPath@@YAPEB_WH@Z; GetWUPolicyRegPath(int)
0x180001ee5  lea     r9, [rbp+57h+var_B0]
0x180001ee9  lea     r8, aDisableapppubl; "DisableAppPublisher"
0x180001ef0  mov     rdx, rax
0x180001ef3  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_W1PEAKW4RegistryHiveType@@@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *,RegistryHiveType)
0x180001ef8  test    eax, eax
0x180001efa  js      short loc_180001F29
0x180001efc  cmp     [rbp+57h+var_B0], 1
0x180001f00  jnz     short loc_180001F29
0x180001f02  mov     dword ptr [rsi+58h], 1
0x180001f09  lea     rax, aApppublisherIs_0; "AppPublisher is disabled through policy"...
0x180001f10  mov     [rsp+100h+var_D8], rax
0x180001f15  mov     [rsp+100h+ppv], r14
0x180001f1a  mov     r9d, ebx
0x180001f1d  mov     r8d, r12d
0x180001f20  xor     edx, edx
0x180001f22  xor     ecx, ecx
0x180001f24  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180001f29  mov     ebx, r14d
0x180001f2c  lea     rcx, [rbp+57h+var_90]; this
0x180001f30  call    ??1CSusSecurityChecker@@QEAA@XZ; CSusSecurityChecker::~CSusSecurityChecker(void)
0x180001f35  nop
0x180001f36  mov     rcx, [rbp+57h+var_B8]
0x180001f3a  test    rcx, rcx
0x180001f3d  jz      short loc_180001F4F
0x180001f3f  mov     rax, [rcx]
0x180001f42  mov     rax, [rax+10h]
0x180001f46  call    _guard_dispatch_icall
0x180001f4b  mov     [rbp+57h+var_B8], r14
0x180001f4f  mov     rcx, [rbp+57h+var_A0]
0x180001f53  test    rcx, rcx
0x180001f56  jz      short loc_180001F65
0x180001f58  mov     rdx, [rcx]
0x180001f5b  mov     rax, [rdx+10h]
0x180001f5f  call    _guard_dispatch_icall
0x180001f64  nop
0x180001f65  mov     eax, ebx
0x180001f67  mov     rcx, [rbp+57h+var_20]
0x180001f6b  xor     rcx, rsp; StackCookie
0x180001f6e  call    __security_check_cookie
0x180001f73  lea     r11, [rsp+100h+var_10]
0x180001f7b  mov     rbx, [r11+28h]
0x180001f7f  mov     rsi, [r11+30h]
0x180001f83  mov     rdi, [r11+38h]
0x180001f87  mov     rsp, r11
0x180001f8a  pop     r14
0x180001f8c  pop     r12
0x180001f8e  pop     rbp
0x180001f8f  retn
0x180001f90  mov     dword ptr [rsi+50h], 1
0x180001f97  mov     rcx, [rbp+57h+var_A8]
0x180001f9b  test    rcx, rcx
0x180001f9e  jz      short loc_180001FAD
0x180001fa0  mov     rax, [rcx]
0x180001fa3  mov     rax, [rax+10h]
0x180001fa7  call    _guard_dispatch_icall
0x180001fac  nop
0x180001fad  jmp     loc_180001E9C
0x180001fb2  mov     edx, 6Fh ; 'o'
0x180001fb7  jmp     short loc_180001FBE
0x180001fb9  mov     edx, 69h ; 'i'; void *
0x180001fbe  mov     r9d, eax; char *
0x180001fc1  lea     r8, aCW1SSrcClientC_27; "C:\\__w\\1\\s\\src\\Client\\comapi\\App"...
0x180001fc8  mov     rcx, [rbp+5Fh]; this
0x180001fcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001fd1  nop
0x180001fd2  mov     rcx, [rbp+57h+var_A8]
0x180001fd6  test    rcx, rcx
0x180001fd9  jz      short loc_180001FE8
0x180001fdb  mov     rax, [rcx]
0x180001fde  mov     rax, [rax+10h]
0x180001fe2  call    _guard_dispatch_icall
0x180001fe7  nop
0x180001fe8  jmp     loc_180001F2C
```
