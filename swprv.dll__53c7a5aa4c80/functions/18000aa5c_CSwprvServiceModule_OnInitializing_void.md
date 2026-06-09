# CSwprvServiceModule::OnInitializing(void)

- ea: `0x18000aa5c`
- end: `0x18000af77`
- name: `?OnInitializing@CSwprvServiceModule@@IEAAXXZ`
- size: `1307`
- prototype: `void __fastcall(CSwprvServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b0d8`

## callees

- `0x180001acc`
- `0x18000212c`
- `0x1800048f8`
- `0x180004a0c`
- `0x18000a5a0`
- `0x18000a6c4`
- `0x18000aa5c`
- `0x18000c770`
- `0x180033a8c`
- `0x180033c78`
- `0x180034cfc`
- `0x18003649c`
- `0x1800367b8`
- `0x180037080`
- `0x1800377c4`
- `0x180037e24`
- `0x180039718`
- `0x18003a05c`
- `0x18003b80c`
- `0x18003b978`
- `0x18003ced0`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000abc9`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000abc9`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18000ab5a`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18000ab5a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ac5e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ac5e`

## string_xrefs

- `0x18000aa8d`: `CSwprvServiceModule::OnInitializing`
- `0x18000af5b`: `CoInitializeSecurity`
- `0x18000ac25`: `CreateWaitableTimer`
- `0x18000aca6`: `CoCreateInstance`
- `0x18000ad2b`: `CVssAmsi allocation failed`
- `0x18000ad87`: `CVssAmsi initialization failed`
- `0x18000ae8f`: `SYSTEM\CurrentControlSet\Services\VSS\Settings`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CSwprvServiceModule::OnInitializing(CSwprvServiceModule *this)
{
  CSwprvServiceModule *v1; // rcx
  HRESULT v2; // ebx
  HANDLE WaitableTimer; // rbx
  CVssAmsi *v4; // rax
  CVssAmsi *v5; // rax
  char v6; // r9
  __int64 v7; // rcx
  const unsigned __int16 *v8; // [rsp+58h] [rbp-B0h] BYREF
  const wchar_t *v9; // [rsp+60h] [rbp-A8h]
  const unsigned __int16 *v10; // [rsp+68h] [rbp-A0h]
  int v11; // [rsp+70h] [rbp-98h]
  int v12; // [rsp+74h] [rbp-94h]
  int v13; // [rsp+78h] [rbp-90h]
  _BYTE v14[120]; // [rsp+80h] [rbp-88h] BYREF
  int v15; // [rsp+F8h] [rbp-10h]
  HKEY v16[5]; // [rsp+100h] [rbp-8h] BYREF
  const unsigned __int16 *v17; // [rsp+128h] [rbp+20h] BYREF
  const wchar_t *v18; // [rsp+130h] [rbp+28h]
  __int128 v19; // [rsp+138h] [rbp+30h]
  PSECURITY_DESCRIPTOR pSecDesc[2]; // [rsp+148h] [rbp+40h] BYREF
  __int128 v21; // [rsp+158h] [rbp+50h]
  __int128 v22; // [rsp+168h] [rbp+60h]
  __int128 v23; // [rsp+178h] [rbp+70h]
  __int128 v24; // [rsp+188h] [rbp+80h]
  __int64 v25; // [rsp+198h] [rbp+90h]
  int v26; // [rsp+1C8h] [rbp+C0h]
  LPVOID v27; // [rsp+1D8h] [rbp+D0h] BYREF
  HRESULT Instance; // [rsp+1E0h] [rbp+D8h]
  CSwprvServiceModule *v29; // [rsp+278h] [rbp+170h] BYREF

  v29 = this;
  v17 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
  v18 = L"CSwprvServiceModule::OnInitializing";
  *(_QWORD *)&v19 = L"SPRSWPRC";
  *((_QWORD *)&v19 + 1) = 0x2000001E6LL;
  LODWORD(pSecDesc[0]) = 255;
  v26 = 0x1000000;
  memset_0(&pSecDesc[1], 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v27, (__int64)&v17, 0);
  CSwprvServiceModule::InitializeCOM(v1);
  v18 = 0;
  v19 = 0;
  *(_OWORD *)pSecDesc = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  LOBYTE(v17) = 0;
  v25 = 0;
  CVssSidCollection::Initialize((CVssSidCollection *)&v17);
  v2 = CoInitializeSecurity(pSecDesc[1], -1, 0, 0, 6u, 2u, 0, 0x3002u, 0);
  Instance = v2;
  v8 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
  v9 = L"CSwprvServiceModule::OnInitializing";
  v10 = L"SPRSWPRC";
  v12 = 2;
  v13 = 255;
  v15 = 0x1000000;
  if ( v2 < 0 )
  {
    v11 = 522;
    memset_0(v14, 0, sizeof(v14));
    CVssFunctionTracer::TranslateGenericError(&v27, &v8, (unsigned int)v2, L"CoInitializeSecurity");
  }
  v11 = 525;
  memset_0(v14, 0, sizeof(v14));
  CVssFunctionTracer::ComDisableSEH((__int64)&v27, (struct CVssDebugInfo *)&v8);
  WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  CVssAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close(&qword_18006B498);
  hTimer = WaitableTimer;
  if ( !WaitableTimer )
  {
    v8 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
    v9 = L"CSwprvServiceModule::OnInitializing";
    v10 = L"SPRSWPRC";
    v11 = 535;
    v12 = 2;
    v13 = 255;
    v15 = 0x1000000;
    memset_0(v14, 0, sizeof(v14));
    CVssFunctionTracer::TranslateWin32Error(&v27, &v8, L"CreateWaitableTimer");
  }
  Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &IID_IContextCallback, (LPVOID *)&ppv);
  v8 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
  v9 = L"CSwprvServiceModule::OnInitializing";
  v10 = L"SPRSWPRC";
  v11 = 538;
  v12 = 2;
  v13 = 255;
  v15 = 0x1000000;
  memset_0(v14, 0, sizeof(v14));
  CVssFunctionTracer::CheckForError(&v27, &v8, L"CoCreateInstance");
  v4 = (CVssAmsi *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v29 = v4;
  if ( v4 )
    v5 = CVssAmsi::CVssAmsi(v4);
  else
    v5 = 0;
  qword_18006B4B0 = (__int64)v5;
  if ( !v5 )
  {
    v8 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
    v9 = L"CSwprvServiceModule::OnInitializing";
    v10 = L"SPRSWPRC";
    v11 = 545;
    v12 = 2;
    v13 = 255;
    v15 = 0x1000000;
    memset_0(v14, 0, sizeof(v14));
    CVssFunctionTracer::Throw(&v27, &v8, 2147942414LL, L"CVssAmsi allocation failed");
  }
  if ( !*((_BYTE *)v5 + 16) )
  {
    v8 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
    v9 = L"CSwprvServiceModule::OnInitializing";
    v10 = L"SPRSWPRC";
    v11 = 550;
    v12 = 2;
    v13 = 255;
    v15 = 0x1000000;
    memset_0(v14, 0, sizeof(v14));
    CVssFunctionTracer::Trace(&v27, &v8, L"CVssAmsi initialization failed");
  }
  v8 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
  v9 = L"CSwprvServiceModule::OnInitializing";
  v10 = L"SPRSWPRC";
  v11 = 553;
  v12 = 2;
  v13 = 255;
  v15 = 0x1000000;
  memset_0(v14, 0, sizeof(v14));
  CVssFunctionTracer::Trace(&v27, &v8, L"about to enter context callback ");
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))ppv->lpVtbl[1].QueryInterface)(
               ppv,
               EnterCallback,
               0,
               &IID_IContextCallback,
               5,
               0);
  v8 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
  v9 = L"CSwprvServiceModule::OnInitializing";
  v10 = L"SPRSWPRC";
  v11 = 555;
  v12 = 2;
  v13 = 255;
  v15 = 0x1000000;
  memset_0(v14, 0, sizeof(v14));
  CVssFunctionTracer::CheckForError(&v27, &v8, L"ContextCallback");
  v16[3] = 0;
  v16[2] = (HKEY)&CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v16[1] = 0;
  v16[0] = (HKEY)1;
  if ( CVssRegistryKey::Open(
         (CVssRegistryKey *)v16,
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\VSS\\Settings")
    && (LODWORD(v29) = 0, CVssRegistryKey::GetValue(v16, L"IdleTimeout", (unsigned int *)&v29, v6)) )
  {
    v7 = -10000000LL * (unsigned int)v29;
    qword_18006B488 = v7;
  }
  else
  {
    v7 = qword_18006B488;
  }
  if ( !v7 )
  {
    CVssSKU::IsClient();
    qword_18006B488 = -1800000000;
  }
  CSwprvServiceModule::SetServiceStatus((CSwprvServiceModule *)v7, 4u, 1);
  byte_18006B490 = 1;
  CVssRegistryKey::~CVssRegistryKey((CVssRegistryKey *)v16);
  CVssSidCollection::~CVssSidCollection((HLOCAL *)&v17);
  CVssFunctionTracer::~CVssFunctionTracer(&v27);
}

```

## disassembly

```asm
0x18000aa5c  mov     rax, rsp
0x18000aa5f  mov     [rax+10h], rbx
0x18000aa63  mov     [rax+18h], rdi
0x18000aa67  mov     [rax+8], rcx
0x18000aa6b  push    rbp
0x18000aa6c  push    r12
0x18000aa6e  push    r13
0x18000aa70  push    r14
0x18000aa72  push    r15
0x18000aa74  lea     rbp, [rax-168h]
0x18000aa7b  sub     rsp, 240h
0x18000aa82  lea     r15, aBaseStorVssMod_15; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000aa89  mov     [rbp+160h+var_140], r15
0x18000aa8d  lea     r12, aCswprvservicem_5; "CSwprvServiceModule::OnInitializing"
0x18000aa94  mov     [rbp+160h+var_138], r12
0x18000aa98  lea     r13, aSprswprc; "SPRSWPRC"
0x18000aa9f  mov     qword ptr [rbp+160h+var_130], r13
0x18000aaa3  mov     dword ptr [rbp+160h+var_130+8], 1E6h
0x18000aaaa  mov     r14d, 2
0x18000aab0  mov     dword ptr [rbp+160h+var_130+0Ch], r14d
0x18000aab4  mov     dword ptr [rbp+160h+pSecDesc], 0FFh
0x18000aabb  xor     edi, edi
0x18000aabd  mov     [rbp+160h+var_A0], 1000000h
0x18000aac7  xor     edx, edx; Val
0x18000aac9  lea     r8d, [r14+76h]; Size
0x18000aacd  lea     rcx, [rbp+160h+pSecDesc+8]; void *
0x18000aad1  call    memset_0
0x18000aad6  xor     r8d, r8d
0x18000aad9  lea     rdx, [rbp+160h+var_140]
0x18000aadd  lea     rcx, [rbp+160h+var_90]
0x18000aae4  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18000aae9  nop
0x18000aaea  call    ?InitializeCOM@CSwprvServiceModule@@QEAAX_N@Z; CSwprvServiceModule::InitializeCOM(bool)
0x18000aaef  mov     [rbp+160h+var_138], rdi
0x18000aaf3  xorps   xmm0, xmm0
0x18000aaf6  movdqa  [rbp+160h+var_130], xmm0
0x18000aafb  xorps   xmm1, xmm1
0x18000aafe  movdqa  xmmword ptr [rbp+160h+pSecDesc], xmm1
0x18000ab03  movdqa  [rbp+160h+var_110], xmm0
0x18000ab08  movdqa  [rbp+160h+var_100], xmm1
0x18000ab0d  movdqa  [rbp+160h+var_F0], xmm0
0x18000ab12  movdqa  [rbp+160h+var_E0], xmm1
0x18000ab1a  mov     byte ptr [rbp+160h+var_140], dil
0x18000ab1e  mov     [rbp+160h+var_D0], rdi
0x18000ab25  lea     rcx, [rbp+160h+var_140]; this
0x18000ab29  call    ?Initialize@CVssSidCollection@@QEAAXXZ; CVssSidCollection::Initialize(void)
0x18000ab2e  mov     [rsp+260h+pReserved3], rdi; pReserved3
0x18000ab33  mov     [rsp+260h+dwCapabilities], 3002h; dwCapabilities
0x18000ab3b  mov     [rsp+260h+pAuthList], rdi; pAuthList
0x18000ab40  mov     [rsp+260h+dwImpLevel], r14d; dwImpLevel
0x18000ab45  mov     [rsp+260h+dwAuthnLevel], 6; dwAuthnLevel
0x18000ab4d  xor     r9d, r9d; pReserved1
0x18000ab50  xor     r8d, r8d; asAuthSvc
0x18000ab53  or      edx, 0FFFFFFFFh; cAuthSvc
0x18000ab56  mov     rcx, [rbp+160h+pSecDesc+8]; pSecDesc
0x18000ab5a  call    cs:__imp_CoInitializeSecurity
0x18000ab60  mov     ebx, eax
0x18000ab62  mov     [rbp+160h+var_88], eax
0x18000ab68  mov     [rsp+260h+var_210], r15
0x18000ab6d  mov     [rsp+260h+var_208], r12
0x18000ab72  mov     [rsp+260h+var_200], r13
0x18000ab77  mov     [rsp+260h+var_1F4], r14d
0x18000ab7c  mov     [rsp+260h+var_1F0], 0FFh
0x18000ab84  mov     [rbp+160h+var_170], 1000000h
0x18000ab8b  xor     edx, edx; Val
0x18000ab8d  lea     r8d, [r14+76h]; Size
0x18000ab91  lea     rcx, [rsp+260h+var_1E8]; void *
0x18000ab96  test    eax, eax
0x18000ab98  js      loc_18000AF4E
0x18000ab9e  mov     [rsp+260h+var_1F8], 20Dh
0x18000aba6  call    memset_0
0x18000abab  lea     rdx, [rsp+260h+var_210]
0x18000abb0  lea     rcx, [rbp+160h+var_90]
0x18000abb7  call    ?ComDisableSEH@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@@Z; CVssFunctionTracer::ComDisableSEH(CVssDebugInfo)
0x18000abbc  mov     r9d, 1F0003h; dwDesiredAccess
0x18000abc2  xor     r8d, r8d; dwFlags
0x18000abc5  xor     edx, edx; lpTimerName
0x18000abc7  xor     ecx, ecx; lpTimerAttributes
0x18000abc9  call    cs:__imp_CreateWaitableTimerExW
0x18000abcf  mov     rbx, rax
0x18000abd2  lea     rcx, qword_18006B498
0x18000abd9  call    ?Close@?$CVssAutoGenericValue_Storage@PEAX$0A@P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<void *,0,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::Close(void)
0x18000abde  mov     cs:hTimer, rbx
0x18000abe5  xor     edx, edx; Val
0x18000abe7  test    rbx, rbx
0x18000abea  jnz     short loc_18000AC3E
0x18000abec  mov     [rsp+260h+var_210], r15
0x18000abf1  mov     [rsp+260h+var_208], r12
0x18000abf6  mov     [rsp+260h+var_200], r13
0x18000abfb  mov     [rsp+260h+var_1F8], 217h
0x18000ac03  mov     [rsp+260h+var_1F4], r14d
0x18000ac08  mov     [rsp+260h+var_1F0], 0FFh
0x18000ac10  mov     [rbp+160h+var_170], 1000000h
0x18000ac17  lea     r8d, [r14+76h]; Size
0x18000ac1b  lea     rcx, [rsp+260h+var_1E8]; void *
0x18000ac20  call    memset_0
0x18000ac25  lea     r8, aCreatewaitable; "CreateWaitableTimer"
0x18000ac2c  lea     rdx, [rsp+260h+var_210]
0x18000ac31  lea     rcx, [rbp+160h+var_90]
0x18000ac38  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x18000ac3e  lea     rax, ppv
0x18000ac45  mov     qword ptr [rsp+260h+dwAuthnLevel], rax; ppv
0x18000ac4a  lea     r9, IID_IContextCallback; riid
0x18000ac51  mov     r8d, 1; dwClsContext
0x18000ac57  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18000ac5e  call    cs:__imp_CoCreateInstance
0x18000ac64  mov     [rbp+160h+var_88], eax
0x18000ac6a  mov     [rsp+260h+var_210], r15
0x18000ac6f  mov     [rsp+260h+var_208], r12
0x18000ac74  mov     [rsp+260h+var_200], r13
0x18000ac79  mov     [rsp+260h+var_1F8], 21Ah
0x18000ac81  mov     [rsp+260h+var_1F4], r14d
0x18000ac86  mov     ebx, 0FFh
0x18000ac8b  mov     [rsp+260h+var_1F0], ebx
0x18000ac8f  mov     [rbp+160h+var_170], 1000000h
0x18000ac96  xor     edx, edx; Val
0x18000ac98  lea     r8d, [rdx+78h]; Size
0x18000ac9c  lea     rcx, [rsp+260h+var_1E8]; void *
0x18000aca1  call    memset_0
0x18000aca6  lea     r8, aCocreateinstan_0; "CoCreateInstance"
0x18000acad  lea     rdx, [rsp+260h+var_210]
0x18000acb2  lea     rcx, [rbp+160h+var_90]
0x18000acb9  call    ?CheckForError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForError(CVssDebugInfo,ushort const *)
0x18000acbe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000acc5  mov     ecx, 40h ; '@'; unsigned __int64
0x18000acca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000accf  mov     [rbp+160h+arg_0], rax
0x18000acd6  test    rax, rax
0x18000acd9  jz      short loc_18000ACE5
0x18000acdb  mov     rcx, rax; this
0x18000acde  call    ??0CVssAmsi@@QEAA@XZ; CVssAmsi::CVssAmsi(void)
0x18000ace3  jmp     short loc_18000ACE8
0x18000ace5  mov     rax, rdi
0x18000ace8  mov     cs:qword_18006B4B0, rax
0x18000acef  test    rax, rax
0x18000acf2  jnz     short loc_18000AD4A
0x18000acf4  mov     [rsp+260h+var_210], r15
0x18000acf9  mov     [rsp+260h+var_208], r12
0x18000acfe  mov     [rsp+260h+var_200], r13
0x18000ad03  mov     [rsp+260h+var_1F8], 221h
0x18000ad0b  mov     [rsp+260h+var_1F4], r14d
0x18000ad10  mov     [rsp+260h+var_1F0], ebx
0x18000ad14  mov     [rbp+160h+var_170], 1000000h
0x18000ad1b  xor     edx, edx; Val
0x18000ad1d  lea     r8d, [rax+78h]; Size
0x18000ad21  lea     rcx, [rsp+260h+var_1E8]; void *
0x18000ad26  call    memset_0
0x18000ad2b  lea     r9, aCvssamsiAlloca; "CVssAmsi allocation failed"
0x18000ad32  mov     r8d, 8007000Eh
0x18000ad38  lea     rdx, [rsp+260h+var_210]
0x18000ad3d  lea     rcx, [rbp+160h+var_90]
0x18000ad44  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18000ad4a  cmp     [rax+10h], dil
0x18000ad4e  jnz     short loc_18000AD9F
0x18000ad50  mov     [rsp+260h+var_210], r15
0x18000ad55  mov     [rsp+260h+var_208], r12
0x18000ad5a  mov     [rsp+260h+var_200], r13
0x18000ad5f  mov     [rsp+260h+var_1F8], 226h
0x18000ad67  mov     [rsp+260h+var_1F4], r14d
0x18000ad6c  mov     [rsp+260h+var_1F0], ebx
0x18000ad70  mov     [rbp+160h+var_170], 1000000h
0x18000ad77  xor     edx, edx; Val
0x18000ad79  lea     r8d, [rdx+78h]; Size
0x18000ad7d  lea     rcx, [rsp+260h+var_1E8]; void *
0x18000ad82  call    memset_0
0x18000ad87  lea     r8, aCvssamsiInitia; "CVssAmsi initialization failed"
0x18000ad8e  lea     rdx, [rsp+260h+var_210]
0x18000ad93  lea     rcx, [rbp+160h+var_90]
0x18000ad9a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18000ad9f  mov     [rsp+260h+var_210], r15
0x18000ada4  mov     [rsp+260h+var_208], r12
0x18000ada9  mov     [rsp+260h+var_200], r13
0x18000adae  mov     [rsp+260h+var_1F8], 229h
0x18000adb6  mov     [rsp+260h+var_1F4], r14d
0x18000adbb  mov     [rsp+260h+var_1F0], ebx
0x18000adbf  mov     [rbp+160h+var_170], 1000000h
0x18000adc6  xor     edx, edx; Val
0x18000adc8  lea     r8d, [rdx+78h]; Size
0x18000adcc  lea     rcx, [rsp+260h+var_1E8]; void *
0x18000add1  call    memset_0
0x18000add6  lea     r8, aAboutToEnterCo_0; "about to enter context callback "
0x18000addd  lea     rdx, [rsp+260h+var_210]
0x18000ade2  lea     rcx, [rbp+160h+var_90]
0x18000ade9  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18000adee  mov     rcx, cs:ppv
0x18000adf5  mov     rax, [rcx]
0x18000adf8  mov     qword ptr [rsp+260h+dwImpLevel], rdi
0x18000adfd  mov     [rsp+260h+dwAuthnLevel], 5
0x18000ae05  lea     r9, IID_IContextCallback
0x18000ae0c  xor     r8d, r8d
0x18000ae0f  lea     rdx, ?EnterCallback@@YAJPEAUtagComCallData@@@Z; EnterCallback(tagComCallData *)
0x18000ae16  mov     rax, [rax+18h]
0x18000ae1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae1f  mov     [rbp+160h+var_88], eax
0x18000ae25  mov     [rsp+260h+var_210], r15
0x18000ae2a  mov     [rsp+260h+var_208], r12
0x18000ae2f  mov     [rsp+260h+var_200], r13
0x18000ae34  mov     [rsp+260h+var_1F8], 22Bh
0x18000ae3c  mov     [rsp+260h+var_1F4], r14d
0x18000ae41  mov     [rsp+260h+var_1F0], ebx
0x18000ae45  mov     [rbp+160h+var_170], 1000000h
0x18000ae4c  xor     edx, edx; Val
0x18000ae4e  lea     r8d, [rdx+78h]; Size
0x18000ae52  lea     rcx, [rsp+260h+var_1E8]; void *
0x18000ae57  call    memset_0
0x18000ae5c  lea     r8, aContextcallbac; "ContextCallback"
0x18000ae63  lea     rdx, [rsp+260h+var_210]
0x18000ae68  lea     rcx, [rbp+160h+var_90]
0x18000ae6f  call    ?CheckForError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForError(CVssDebugInfo,ushort const *)
0x18000ae74  mov     [rbp+160h+var_150], rdi
0x18000ae78  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x18000ae7f  mov     [rbp+160h+var_158], rax
0x18000ae83  mov     [rbp+160h+var_160], rdi
0x18000ae87  mov     [rbp+160h+var_168], 1
0x18000ae8f  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\VS"...
0x18000ae96  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18000ae9d  lea     rcx, [rbp+160h+var_168]; this
0x18000aea1  call    ?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Open(HKEY__ *,ushort const *,...)
0x18000aea6  test    al, al
0x18000aea8  jz      short loc_18000AEE1
0x18000aeaa  mov     dword ptr [rbp+160h+arg_0], edi
0x18000aeb0  lea     r8, [rbp+160h+arg_0]; unsigned int *
0x18000aeb7  lea     rdx, aIdletimeout; "IdleTimeout"
0x18000aebe  lea     rcx, [rbp+160h+var_168]; this
0x18000aec2  call    ?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAK_N@Z; CVssRegistryKey::GetValue(ushort const *,ulong &,bool)
0x18000aec7  test    al, al
0x18000aec9  jz      short loc_18000AEE1
0x18000aecb  mov     eax, dword ptr [rbp+160h+arg_0]
0x18000aed1  imul    rcx, rax, 0FFFFFFFFFF676980h
0x18000aed8  mov     cs:qword_18006B488, rcx
0x18000aedf  jmp     short loc_18000AEE8
0x18000aee1  mov     rcx, cs:qword_18006B488
0x18000aee8  test    rcx, rcx
0x18000aeeb  jnz     short loc_18000AEFD
0x18000aeed  call    ?IsClient@CVssSKU@@SAHXZ; CVssSKU::IsClient(void)
0x18000aef2  mov     cs:qword_18006B488, 0FFFFFFFF94B62E00h
0x18000aefd  mov     r8b, 1; bool
0x18000af00  mov     edx, 4; unsigned int
0x18000af05  call    ?SetServiceStatus@CSwprvServiceModule@@IEAAXK_N@Z; CSwprvServiceModule::SetServiceStatus(ulong,bool)
0x18000af0a  mov     cs:byte_18006B490, 1
0x18000af11  lea     rcx, [rbp+160h+var_168]; this
0x18000af15  call    ??1CVssRegistryKey@@QEAA@XZ; CVssRegistryKey::~CVssRegistryKey(void)
0x18000af1a  nop
0x18000af1b  lea     rcx, [rbp+160h+var_140]; this
0x18000af1f  call    ??1CVssSidCollection@@QEAA@XZ; CVssSidCollection::~CVssSidCollection(void)
0x18000af24  nop
0x18000af25  lea     rcx, [rbp+160h+var_90]; this
0x18000af2c  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18000af31  lea     r11, [rsp+260h+var_20]
0x18000af39  mov     rbx, [r11+38h]
0x18000af3d  mov     rdi, [r11+40h]
0x18000af41  mov     rsp, r11
0x18000af44  pop     r15
0x18000af46  pop     r14
0x18000af48  pop     r13
0x18000af4a  pop     r12
0x18000af4c  pop     rbp
0x18000af4d  retn
0x18000af4e  mov     [rsp+260h+var_1F8], 20Ah
0x18000af56  call    memset_0
0x18000af5b  lea     r9, aCoinitializese_0; "CoInitializeSecurity"
0x18000af62  mov     r8d, ebx
0x18000af65  lea     rdx, [rsp+260h+var_210]
0x18000af6a  lea     rcx, [rbp+160h+var_90]
0x18000af71  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
```
