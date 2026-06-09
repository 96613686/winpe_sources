# CUpdateServiceManager::AddService2(wchar_t *,long,wchar_t *,IUpdateServiceRegistration * *)

- ea: `0x180072ff0`
- end: `0x180073440`
- name: `?AddService2@CUpdateServiceManager@@UEAAJPEA_WJ0PEAPEAUIUpdateServiceRegistration@@@Z`
- size: `1104`
- prototype: `__int64 __fastcall(CUpdateServiceManager *this, wchar_t *, int, wchar_t *, struct IUpdateServiceRegistration **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x180007ecc`
- `0x18003bbe8`
- `0x18004737c`
- `0x180072ff0`
- `0x180073b30`
- `0x180074c08`
- `0x180082d04`
- `0x18008d284`
- `0x180090bc8`
- `0x18009785c`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800732ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800732fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800732ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800732fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073244`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073244`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073253`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073411`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073253`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073411`
- `RPCRT4!UuidFromStringW` at `0x18007315d`
- `RPCRT4!UuidFromStringW` at `0x18007315d`
- `OLEAUT32!__imp_SysStringLen` at `0x18007313a`
- `OLEAUT32!__imp_SysStringLen` at `0x180073279`
- `OLEAUT32!__imp_SysStringLen` at `0x18007313a`
- `OLEAUT32!__imp_SysStringLen` at `0x180073279`

## string_xrefs

- `0x18007316e`: `C:\__w\1\s\src\Client\comapi\UpdateServiceManager.cpp`
- `0x18007320b`: `C:\__w\1\s\src\Client\comapi\UpdateServiceManager.cpp`
- `0x1800732cc`: `C:\__w\1\s\src\Client\comapi\UpdateServiceManager.cpp`
- `0x18007331a`: `C:\__w\1\s\src\Client\comapi\UpdateServiceManager.cpp`
- `0x180073058`: `IUpdateServiceManager::AddService2`
- `0x18007307f`: `Service ID = {%ws}`
- `0x1800730dc`: `Allow pending registration = %ws; Allow online registration = %ws; Register service with AU = %ws`
- `0x180073389`: `Added service, URL = %ws`
- `0x1800733ab`: `Deferred service opt-in`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
__int64 __fastcall CUpdateServiceManager::AddService2(
        CUpdateServiceManager *this,
        wchar_t *a2,
        int a3,
        wchar_t *a4,
        struct IUpdateServiceRegistration **a5)
{
  CUpdateServiceRegistration *v7; // rbx
  char v8; // r12
  char v9; // r15
  int v10; // edi
  const wchar_t *v11; // rdx
  const wchar_t *v12; // rcx
  int v13; // r12d
  const wchar_t *v14; // rax
  int v15; // r15d
  int v16; // edi
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned int v19; // eax
  unsigned int v20; // edx
  int v21; // r8d
  __int64 *v22; // rsi
  int ProxySettings; // eax
  unsigned int v24; // eax
  unsigned __int64 v25; // rsi
  int v26; // r12d
  const struct tagProxySettings *v27; // rdi
  unsigned int v28; // r15d
  UINT v29; // eax
  const wchar_t *v30; // r9
  const wchar_t *v31; // rdx
  int v32; // eax
  int Instance; // eax
  CUpdateServiceRegistration *v34; // rax
  unsigned int v36; // [rsp+20h] [rbp-71h]
  _BYTE v38[12]; // [rsp+54h] [rbp-3Dh] BYREF
  unsigned int v39; // [rsp+60h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-29h] BYREF
  unsigned int v41; // [rsp+70h] [rbp-21h] BYREF
  UUID Uuid; // [rsp+78h] [rbp-19h] BYREF
  _OWORD v43[2]; // [rsp+88h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  Uuid = 0;
  pv = 0;
  v7 = 0;
  *(_DWORD *)&v38[8] = 0;
  memset(v43, 0, sizeof(v43));
  v41 = 0;
  v39 = 0;
  v8 = a3;
  v9 = a3;
  v10 = a3 & 1;
  *(_QWORD *)v38 = a3 & 1;
  WUTrace(0, 0, 0x10000, 4, 0, L"IUpdateServiceManager::AddService2");
  WUTrace(0, 0, 0x10000, 4, 0, L"Service ID = {%ws}", a2);
  v11 = L"No";
  v12 = L"No";
  v13 = v8 & 4;
  if ( v13 )
    v12 = L"Yes";
  v14 = L"No";
  v15 = v9 & 2;
  if ( v15 )
    v14 = L"Yes";
  if ( v10 )
    v11 = L"Yes";
  WUTrace(
    0,
    0,
    0x10000,
    4,
    0,
    L"Allow pending registration = %ws; Allow online registration = %ws; Register service with AU = %ws",
    v11,
    v14,
    v12);
  if ( !a5 )
  {
    v16 = -2147467261;
    v17 = 450;
LABEL_13:
    v18 = (unsigned int)v16;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateServiceManager.cpp",
      (const char *)v18,
      v36);
    goto LABEL_51;
  }
  *a5 = 0;
  v16 = SecurityCheck((v13 != 0 ? 5 : 1) | 0x80000000);
  if ( v16 < 0 )
  {
    v17 = 469;
    goto LABEL_13;
  }
  if ( !SysStringLen(a2) )
  {
    v16 = -2147024809;
    v17 = 471;
    goto LABEL_13;
  }
  v19 = UuidFromStringW(a2, &Uuid);
  if ( v19 )
  {
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1D8,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateServiceManager.cpp",
            (const char *)v19,
            v36);
    goto LABEL_51;
  }
  if ( (a3 & 0xFFFFFFF8) != 0 )
  {
    v16 = -2147024809;
    v18 = 2147942487LL;
    v17 = 476;
    goto LABEL_28;
  }
  v22 = &qword_1800EF060;
  if ( *((_QWORD *)this + 36) )
    v22 = (__int64 *)*((_QWORD *)this + 36);
  ProxySettings = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v22[6] + 120))(v22 + 6, &v41);
  v16 = ProxySettings;
  if ( ProxySettings < 0 )
  {
    v17 = 485;
LABEL_27:
    v18 = (unsigned int)ProxySettings;
    goto LABEL_28;
  }
  v24 = v39;
  if ( *(_DWORD *)v38 )
  {
    v24 = v39 | 1;
    v39 |= 1u;
  }
  if ( v15 )
  {
    v39 = v24 | 2;
    ProxySettings = CUpdateSession::get_ProxySettings((CUpdateSession *)v22, (struct tagProxySettings *)v43);
    v16 = ProxySettings;
    if ( ProxySettings < 0 )
    {
      v17 = 495;
      goto LABEL_27;
    }
    v24 = v39;
  }
  if ( v13 )
    v39 = v24 | 8;
  v25 = ((unsigned __int64)this + 200) & -(__int64)(this != (CUpdateServiceManager *)24);
  if ( v25 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v25 + 8));
  if ( pv )
    CoTaskMemFree(pv);
  v26 = *((unsigned __int8 *)this + 304);
  v27 = (const struct tagProxySettings *)((unsigned __int64)v43 & -(__int64)(v15 != 0));
  v28 = v41;
  v29 = SysStringLen(*((BSTR *)this + 37));
  v31 = &c_wszEmpty;
  if ( v29 )
    v31 = (const wchar_t *)*((_QWORD *)this + 37);
  v32 = CSusInternalWrapper::AddService2(
          (CUpdateServiceManager *)((char *)this + 8),
          v31,
          &Uuid,
          v30,
          v28,
          &v39,
          v27,
          v26,
          (struct tagDSServiceProps **)&pv);
  v16 = v32;
  if ( v32 >= 0 )
  {
    if ( v25 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v25 + 8));
    Instance = ATL::CComObject<CUpdateServiceRegistration>::CreateInstance(&v38[4]);
    v16 = Instance;
    if ( Instance >= 0 )
    {
      v7 = *(CUpdateServiceRegistration **)&v38[4];
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)&v38[4] + 8LL) + 8LL))(*(_QWORD *)&v38[4] + 8LL);
      ProxySettings = CUpdateServiceRegistration::Initialize(v7, &Uuid, (const struct tagDSServiceProps *)pv, v39);
      v16 = ProxySettings;
      if ( ProxySettings < 0 )
      {
        v17 = 522;
        goto LABEL_27;
      }
      if ( pv )
      {
        WUTrace(0, 0, 0x10000, 4, 0, L"Added service, URL = %ws", *(_QWORD *)pv);
        pv = 0;
      }
      else
      {
        WUTrace(0, 0, 0x10000, 4, 0, L"Deferred service opt-in");
      }
      v34 = v7;
      v7 = 0;
      *a5 = (struct IUpdateServiceRegistration *)(((unsigned __int64)v34 + 8) & -(__int64)(v34 != 0));
      v16 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x206,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateServiceManager.cpp",
        (const char *)(unsigned int)Instance,
        v36);
      v7 = *(CUpdateServiceRegistration **)&v38[4];
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x202,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateServiceManager.cpp",
      (const char *)(unsigned int)v32,
      v36);
    if ( v25 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v25 + 8));
  }
LABEL_51:
  DsqFreeObject((struct tagDSServiceProps *)pv, v20, v21);
  FreeObject((struct tagProxySettings *)v43);
  if ( v7 )
    (*(void (__fastcall **)(_QWORD *))(*((_QWORD *)v7 + 1) + 16LL))((_QWORD *)v7 + 1);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180072ff0  mov     [rsp-8+arg_18], rbx
0x180072ff5  push    rbp
0x180072ff6  push    rsi
0x180072ff7  push    rdi
0x180072ff8  push    r12
0x180072ffa  push    r13
0x180072ffc  push    r14
0x180072ffe  push    r15
0x180073000  lea     rbp, [rsp-1Fh]
0x180073005  sub     rsp, 0B0h
0x18007300c  mov     rax, cs:__security_cookie
0x180073013  xor     rax, rsp
0x180073016  mov     [rbp+4Fh+var_38], rax
0x18007301a  mov     [rbp+4Fh+var_90], r8d
0x18007301e  mov     rsi, rdx
0x180073021  mov     r14, rcx
0x180073024  mov     r13, [rbp+4Fh+arg_20]
0x180073028  xorps   xmm0, xmm0
0x18007302b  movups  xmmword ptr [rbp+4Fh+Uuid.Data1], xmm0
0x18007302f  xor     ecx, ecx
0x180073031  mov     [rbp+4Fh+pv], rcx
0x180073035  mov     ebx, ecx
0x180073037  mov     [rbp+4Fh+var_88], rcx
0x18007303b  movups  [rbp+4Fh+var_58], xmm0
0x18007303f  movups  [rbp+4Fh+var_48], xmm0
0x180073043  mov     [rbp+4Fh+var_70], ecx
0x180073046  mov     [rbp+4Fh+var_80], ecx
0x180073049  mov     r12d, r8d
0x18007304c  mov     r15d, r8d
0x18007304f  mov     edi, r8d
0x180073052  and     edi, 1
0x180073055  mov     [rbp+4Fh+var_8C], edi
0x180073058  lea     rax, aIupdateservice; "IUpdateServiceManager::AddService2"
0x18007305f  mov     [rsp+0E0h+var_B8], rax
0x180073064  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x180073069  xor     edx, edx
0x18007306b  lea     r9d, [rcx+4]
0x18007306f  mov     r8d, 10000h
0x180073075  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18007307a  mov     [rsp+0E0h+var_B0], rsi
0x18007307f  lea     rax, aServiceIdWs; "Service ID = {%ws}"
0x180073086  mov     [rsp+0E0h+var_B8], rax
0x18007308b  mov     qword ptr [rsp+0E0h+var_C0], rbx
0x180073090  xor     edx, edx
0x180073092  xor     ecx, ecx
0x180073094  lea     r9d, [rbx+4]
0x180073098  mov     r8d, 10000h
0x18007309e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800730a3  lea     r8, aYes_1; "Yes"
0x1800730aa  lea     rdx, aNo_1; "No"
0x1800730b1  mov     rcx, rdx
0x1800730b4  and     r12d, 4
0x1800730b8  cmovnz  rcx, r8
0x1800730bc  mov     rax, rdx
0x1800730bf  and     r15d, 2
0x1800730c3  cmovnz  rax, r8
0x1800730c7  test    edi, edi
0x1800730c9  cmovnz  rdx, r8
0x1800730cd  mov     [rsp+0E0h+var_A0], rcx
0x1800730d2  mov     qword ptr [rsp+0E0h+var_A8], rax
0x1800730d7  mov     [rsp+0E0h+var_B0], rdx
0x1800730dc  lea     rax, aAllowPendingRe; "Allow pending registration = %ws; Allow"...
0x1800730e3  mov     [rsp+0E0h+var_B8], rax
0x1800730e8  mov     qword ptr [rsp+0E0h+var_C0], rbx; int
0x1800730ed  xor     edx, edx
0x1800730ef  xor     ecx, ecx
0x1800730f1  lea     r9d, [rbx+4]
0x1800730f5  mov     r8d, 10000h
0x1800730fb  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180073100  test    r13, r13
0x180073103  jnz     short loc_180073111
0x180073105  mov     edi, 80004003h
0x18007310a  mov     edx, 1C2h
0x18007310f  jmp     short loc_18007314E
0x180073111  mov     [r13+0], rbx
0x180073115  mov     eax, r12d
0x180073118  neg     eax
0x18007311a  sbb     ecx, ecx
0x18007311c  and     ecx, 4
0x18007311f  inc     ecx
0x180073121  bts     ecx, 1Fh; unsigned int
0x180073125  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x18007312a  mov     edi, eax
0x18007312c  test    eax, eax
0x18007312e  jns     short loc_180073137
0x180073130  mov     edx, 1D5h
0x180073135  jmp     short loc_18007314E
0x180073137  mov     rcx, rsi; pbstr
0x18007313a  call    cs:__imp_SysStringLen
0x180073140  test    eax, eax
0x180073142  jnz     short loc_180073156
0x180073144  mov     edi, 80070057h
0x180073149  mov     edx, 1D7h
0x18007314e  mov     r9d, edi
0x180073151  jmp     loc_180073207
0x180073156  lea     rdx, [rbp+4Fh+Uuid]; Uuid
0x18007315a  mov     rcx, rsi; StringUuid
0x18007315d  call    cs:__imp_UuidFromStringW
0x180073163  test    eax, eax
0x180073165  jz      short loc_180073186
0x180073167  mov     rcx, [rbp+57h]; this
0x18007316b  mov     r9d, eax; char *
0x18007316e  lea     r8, aCW1SSrcClientC_50; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180073175  mov     edx, 1D8h; void *
0x18007317a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007317f  mov     edi, eax
0x180073181  jmp     loc_1800733DF
0x180073186  test    [rbp+4Fh+var_90], 0FFFFFFF8h
0x18007318d  jz      short loc_18007319E
0x18007318f  mov     edi, 80070057h
0x180073194  mov     r9d, edi
0x180073197  mov     edx, 1DCh
0x18007319c  jmp     short loc_180073207
0x18007319e  mov     rax, [r14+120h]
0x1800731a5  lea     rsi, qword_1800EF060
0x1800731ac  test    rax, rax
0x1800731af  cmovnz  rsi, rax
0x1800731b3  lea     rcx, [rsi+30h]
0x1800731b7  mov     rax, [rcx]
0x1800731ba  lea     rdx, [rbp+4Fh+var_70]
0x1800731be  mov     rax, [rax+78h]
0x1800731c2  call    _guard_dispatch_icall
0x1800731c7  mov     edi, eax
0x1800731c9  test    eax, eax
0x1800731cb  jns     short loc_1800731D4
0x1800731cd  mov     edx, 1E5h
0x1800731d2  jmp     short loc_180073204
0x1800731d4  mov     eax, [rbp+4Fh+var_80]
0x1800731d7  cmp     [rbp+4Fh+var_8C], ebx
0x1800731da  jz      short loc_1800731E2
0x1800731dc  or      eax, 1
0x1800731df  mov     [rbp+4Fh+var_80], eax
0x1800731e2  test    r15d, r15d
0x1800731e5  jz      short loc_18007321F
0x1800731e7  or      eax, 2
0x1800731ea  mov     [rbp+4Fh+var_80], eax
0x1800731ed  lea     rdx, [rbp+4Fh+var_58]; struct tagProxySettings *
0x1800731f1  mov     rcx, rsi; this
0x1800731f4  call    ?get_ProxySettings@CUpdateSession@@QEAAJPEAUtagProxySettings@@@Z; CUpdateSession::get_ProxySettings(tagProxySettings *)
0x1800731f9  mov     edi, eax
0x1800731fb  test    eax, eax
0x1800731fd  jns     short loc_18007321C
0x1800731ff  mov     edx, 1EFh; void *
0x180073204  mov     r9d, eax; char *
0x180073207  mov     rcx, [rbp+57h]; this
0x18007320b  lea     r8, aCW1SSrcClientC_50; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180073212  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073217  jmp     loc_1800733DF
0x18007321c  mov     eax, [rbp+4Fh+var_80]
0x18007321f  test    r12d, r12d
0x180073222  jz      short loc_18007322A
0x180073224  or      eax, 8
0x180073227  mov     [rbp+4Fh+var_80], eax
0x18007322a  lea     rax, [r14-18h]
0x18007322e  lea     rcx, [r14+0C8h]
0x180073235  neg     rax
0x180073238  sbb     rsi, rsi
0x18007323b  and     rsi, rcx
0x18007323e  jz      short loc_18007324A
0x180073240  lea     rcx, [rsi+8]; lpCriticalSection
0x180073244  call    cs:__imp_EnterCriticalSection
0x18007324a  mov     rcx, [rbp+4Fh+pv]; pv
0x18007324e  test    rcx, rcx
0x180073251  jz      short loc_180073259
0x180073253  call    cs:__imp_CoTaskMemFree
0x180073259  movzx   r12d, byte ptr [r14+130h]
0x180073261  neg     r15d
0x180073264  sbb     rdi, rdi
0x180073267  lea     rax, [rbp+4Fh+var_58]
0x18007326b  and     rdi, rax
0x18007326e  mov     r15d, [rbp+4Fh+var_70]
0x180073272  mov     rcx, [r14+128h]; pbstr
0x180073279  call    cs:__imp_SysStringLen
0x18007327f  test    eax, eax
0x180073281  lea     rdx, ?c_wszEmpty@@3QB_WB; wchar_t const near * const c_wszEmpty
0x180073288  jz      short loc_180073291
0x18007328a  mov     rdx, [r14+128h]; wchar_t *
0x180073291  lea     rcx, [r14+8]; this
0x180073295  lea     rax, [rbp+4Fh+pv]
0x180073299  mov     [rsp+0E0h+var_A0], rax; struct tagDSServiceProps **
0x18007329e  mov     [rsp+0E0h+var_A8], r12d; int
0x1800732a3  mov     [rsp+0E0h+var_B0], rdi; struct tagProxySettings *
0x1800732a8  lea     rax, [rbp+4Fh+var_80]
0x1800732ac  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x1800732b1  mov     [rsp+0E0h+var_C0], r15d; int
0x1800732b6  lea     r8, [rbp+4Fh+Uuid]; struct _GUID *
0x1800732ba  call    ?AddService2@CSusInternalWrapper@@QEAAJPEB_WAEBU_GUID@@0KPEAKPEBUtagProxySettings@@HPEAPEAUtagDSServiceProps@@@Z; CSusInternalWrapper::AddService2(wchar_t const *,_GUID const &,wchar_t const *,ulong,ulong *,tagProxySettings const *,int,tagDSServiceProps * *)
0x1800732bf  mov     edi, eax
0x1800732c1  test    eax, eax
0x1800732c3  jns     short loc_1800732F5
0x1800732c5  mov     rcx, [rbp+57h]; this
0x1800732c9  mov     r9d, eax; char *
0x1800732cc  lea     r8, aCW1SSrcClientC_50; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x1800732d3  mov     edx, 202h; void *
0x1800732d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800732dd  test    rsi, rsi
0x1800732e0  jz      loc_1800733DF
0x1800732e6  lea     rcx, [rsi+8]; lpCriticalSection
0x1800732ea  call    cs:__imp_LeaveCriticalSection
0x1800732f0  jmp     loc_1800733DF
0x1800732f5  test    rsi, rsi
0x1800732f8  jz      short loc_180073304
0x1800732fa  lea     rcx, [rsi+8]; lpCriticalSection
0x1800732fe  call    cs:__imp_LeaveCriticalSection
0x180073304  lea     rcx, [rbp+4Fh+var_88]
0x180073308  call    ?CreateInstance@?$CComObject@VCUpdateServiceRegistration@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUpdateServiceRegistration>::CreateInstance(ATL::CComObject<CUpdateServiceRegistration> * *)
0x18007330d  mov     edi, eax
0x18007330f  test    eax, eax
0x180073311  jns     short loc_180073334
0x180073313  mov     rcx, [rbp+57h]; this
0x180073317  mov     r9d, eax; char *
0x18007331a  lea     r8, aCW1SSrcClientC_50; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180073321  mov     edx, 206h; void *
0x180073326  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007332b  mov     rbx, [rbp+4Fh+var_88]
0x18007332f  jmp     loc_1800733DF
0x180073334  mov     rbx, [rbp+4Fh+var_88]
0x180073338  lea     rcx, [rbx+8]
0x18007333c  mov     rax, [rcx]
0x18007333f  mov     rax, [rax+8]
0x180073343  call    _guard_dispatch_icall
0x180073348  mov     r9d, [rbp+4Fh+var_80]; unsigned int
0x18007334c  mov     r8, [rbp+4Fh+pv]; struct tagDSServiceProps *
0x180073350  lea     rdx, [rbp+4Fh+Uuid]; Uuid
0x180073354  mov     rcx, rbx; this
0x180073357  call    ?Initialize@CUpdateServiceRegistration@@QEAAJAEBU_GUID@@PEBUtagDSServiceProps@@K@Z; CUpdateServiceRegistration::Initialize(_GUID const &,tagDSServiceProps const *,ulong)
0x18007335c  mov     edi, eax
0x18007335e  test    eax, eax
0x180073360  jns     short loc_18007336C
0x180073362  mov     edx, 20Ah
0x180073367  jmp     loc_180073204
0x18007336c  mov     rax, [rbp+4Fh+pv]
0x180073370  xor     edx, edx
0x180073372  lea     r9d, [rdx+4]
0x180073376  mov     r8d, 10000h
0x18007337c  test    rax, rax
0x18007337f  jz      short loc_1800733AB
0x180073381  mov     rcx, [rax]
0x180073384  mov     [rsp+0E0h+var_B0], rcx
0x180073389  lea     rax, aAddedServiceUr; "Added service, URL = %ws"
0x180073390  mov     [rsp+0E0h+var_B8], rax
0x180073395  mov     qword ptr [rsp+0E0h+var_C0], rdx
0x18007339a  xor     ecx, ecx
0x18007339c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800733a1  mov     [rbp+4Fh+pv], 0
0x1800733a9  jmp     short loc_1800733C7
0x1800733ab  lea     rax, aDeferredServic; "Deferred service opt-in"
0x1800733b2  mov     [rsp+0E0h+var_B8], rax
0x1800733b7  mov     qword ptr [rsp+0E0h+var_C0], 0
0x1800733c0  xor     ecx, ecx
0x1800733c2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800733c7  mov     rax, rbx
0x1800733ca  xor     ebx, ebx
0x1800733cc  lea     rcx, [rax+8]
0x1800733d0  neg     rax
0x1800733d3  sbb     rax, rax
0x1800733d6  and     rax, rcx
0x1800733d9  mov     [r13+0], rax
0x1800733dd  xor     edi, edi
0x1800733df  mov     rcx, [rbp+4Fh+pv]; struct tagDSServiceProps *
0x1800733e3  call    ?DsqFreeObject@@YAXPEAUtagDSServiceProps@@KH@Z; DsqFreeObject(tagDSServiceProps *,ulong,int)
0x1800733e8  lea     rcx, [rbp+4Fh+var_58]; struct tagProxySettings *
0x1800733ec  call    ?FreeObject@@YAXAEAUtagProxySettings@@@Z; FreeObject(tagProxySettings &)
0x1800733f1  nop
0x1800733f2  test    rbx, rbx
0x1800733f5  jz      short loc_180073408
0x1800733f7  lea     rcx, [rbx+8]
0x1800733fb  mov     rax, [rcx]
0x1800733fe  mov     rax, [rax+10h]
0x180073402  call    _guard_dispatch_icall
0x180073407  nop
0x180073408  mov     rcx, [rbp+4Fh+pv]; pv
0x18007340c  test    rcx, rcx
0x18007340f  jz      short loc_180073417
0x180073411  call    cs:__imp_CoTaskMemFree
0x180073417  mov     eax, edi
0x180073419  mov     rcx, [rbp+4Fh+var_38]
0x18007341d  xor     rcx, rsp; StackCookie
0x180073420  call    __security_check_cookie
0x180073425  mov     rbx, [rsp+0E0h+arg_18]
0x18007342d  add     rsp, 0B0h
0x180073434  pop     r15
0x180073436  pop     r14
0x180073438  pop     r13
0x18007343a  pop     r12
0x18007343c  pop     rdi
0x18007343d  pop     rsi
0x18007343e  pop     rbp
0x18007343f  retn
```
