# CUpdateServiceManager::QueryServiceRegistration(wchar_t *,IUpdateServiceRegistration * *)

- ea: `0x180072dd0`
- end: `0x180072fe1`
- name: `?QueryServiceRegistration@CUpdateServiceManager@@UEAAJPEA_WPEAPEAUIUpdateServiceRegistration@@@Z`
- size: `529`
- prototype: `int(CUpdateServiceManager *__hidden this, wchar_t *, struct IUpdateServiceRegistration **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x180007ecc`
- `0x18004737c`
- `0x180072dd0`
- `0x180073b30`
- `0x180074c08`
- `0x18009785c`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072eb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072fbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072eb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072fbf`
- `RPCRT4!UuidFromStringW` at `0x180072e4a`
- `RPCRT4!UuidFromStringW` at `0x180072e4a`
- `OLEAUT32!__imp_SysStringLen` at `0x180072e27`
- `OLEAUT32!__imp_SysStringLen` at `0x180072e27`

## string_xrefs

- `0x180072e5b`: `C:\__w\1\s\src\Client\comapi\UpdateServiceManager.cpp`
- `0x180072f1a`: `C:\__w\1\s\src\Client\comapi\UpdateServiceManager.cpp`
- `0x180072f67`: `C:\__w\1\s\src\Client\comapi\UpdateServiceManager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CUpdateServiceManager::QueryServiceRegistration(
        CUpdateServiceManager *this,
        wchar_t *a2,
        struct IUpdateServiceRegistration **a3)
{
  CUpdateServiceRegistration *v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rdx
  unsigned __int64 v9; // r9
  unsigned int v10; // eax
  __int64 *v11; // rcx
  int v12; // eax
  const wchar_t *v13; // r9
  int v14; // eax
  struct tagDSServiceProps *v15; // rcx
  CUpdateServiceRegistration *v16; // rax
  unsigned int v18; // [rsp+20h] [rbp-60h]
  CUpdateServiceRegistration *v19; // [rsp+50h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v21; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v22; // [rsp+64h] [rbp-1Ch] BYREF
  UUID Uuid; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  Uuid = 0;
  pv = 0;
  v6 = 0;
  v19 = 0;
  v21 = 0;
  if ( !a3 )
  {
    v7 = -2147467261;
    v8 = 336;
LABEL_5:
    v9 = v7;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateServiceManager.cpp",
      (const char *)v9,
      v18);
    goto LABEL_22;
  }
  *a3 = 0;
  if ( !SysStringLen(a2) )
  {
    v7 = -2147024809;
    v8 = 340;
    goto LABEL_5;
  }
  v10 = UuidFromStringW(a2, &Uuid);
  if ( v10 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x155,
           (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateServiceManager.cpp",
           (const char *)v10,
           v18);
LABEL_22:
    v15 = (struct tagDSServiceProps *)pv;
    goto LABEL_24;
  }
  v11 = &qword_1800EF060;
  if ( *((_QWORD *)this + 36) )
    v11 = (__int64 *)*((_QWORD *)this + 36);
  v12 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v11[6] + 120))(v11 + 6, &v21);
  v7 = v12;
  if ( v12 < 0 )
  {
    v8 = 350;
LABEL_20:
    v9 = (unsigned int)v12;
    goto LABEL_21;
  }
  v22 = 0;
  if ( pv )
    CoTaskMemFree(pv);
  v12 = CSusInternalWrapper::AddService2(
          (CUpdateServiceManager *)((char *)this + 8),
          0,
          &Uuid,
          v13,
          v21,
          &v22,
          0,
          *((unsigned __int8 *)this + 304),
          (struct tagDSServiceProps **)&pv);
  v7 = v12;
  if ( v12 < 0 )
  {
    v8 = 361;
    goto LABEL_20;
  }
  v14 = ATL::CComObject<CUpdateServiceRegistration>::CreateInstance(&v19);
  v7 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16C,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateServiceManager.cpp",
      (const char *)(unsigned int)v14,
      v18);
    v6 = v19;
    goto LABEL_22;
  }
  v6 = v19;
  (*(void (__fastcall **)(char *))(*((_QWORD *)v19 + 1) + 8LL))((char *)v19 + 8);
  v12 = CUpdateServiceRegistration::Initialize(v6, &Uuid, (const struct tagDSServiceProps *)pv, v22);
  v7 = v12;
  if ( v12 < 0 )
  {
    v8 = 368;
    goto LABEL_20;
  }
  v15 = 0;
  pv = 0;
  v16 = v6;
  v6 = 0;
  *a3 = (struct IUpdateServiceRegistration *)(((unsigned __int64)v16 + 8) & -(__int64)(v16 != 0));
  v7 = 0;
LABEL_24:
  DsqFreeObject(v15);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v6 + 1) + 16LL))((__int64)v6 + 8);
  if ( pv )
    CoTaskMemFree(pv);
  return v7;
}

```

## disassembly

```asm
0x180072dd0  push    rbp
0x180072dd2  push    rbx
0x180072dd3  push    rsi
0x180072dd4  push    rdi
0x180072dd5  push    r14
0x180072dd7  mov     rbp, rsp
0x180072dda  sub     rsp, 80h
0x180072de1  mov     rax, cs:__security_cookie
0x180072de8  xor     rax, rsp
0x180072deb  mov     [rbp+var_8], rax
0x180072def  mov     rsi, r8
0x180072df2  mov     rdi, rdx
0x180072df5  mov     r14, rcx
0x180072df8  xorps   xmm0, xmm0
0x180072dfb  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180072dff  mov     [rbp+pv], 0
0x180072e07  xor     ebx, ebx
0x180072e09  mov     [rbp+var_30], rbx
0x180072e0d  mov     [rbp+var_20], ebx
0x180072e10  test    r8, r8
0x180072e13  jnz     short loc_180072E21
0x180072e15  mov     edi, 80004003h
0x180072e1a  mov     edx, 150h
0x180072e1f  jmp     short loc_180072E3B
0x180072e21  mov     [r8], rbx
0x180072e24  mov     rcx, rdi; pbstr
0x180072e27  call    cs:__imp_SysStringLen
0x180072e2d  test    eax, eax
0x180072e2f  jnz     short loc_180072E43
0x180072e31  mov     edi, 80070057h
0x180072e36  mov     edx, 154h
0x180072e3b  mov     r9d, edi
0x180072e3e  jmp     loc_180072F67
0x180072e43  lea     rdx, [rbp+Uuid]; Uuid
0x180072e47  mov     rcx, rdi; StringUuid
0x180072e4a  call    cs:__imp_UuidFromStringW
0x180072e50  test    eax, eax
0x180072e52  jz      short loc_180072E73
0x180072e54  mov     rcx, [rbp+28h]; this
0x180072e58  mov     r9d, eax; char *
0x180072e5b  lea     r8, aCW1SSrcClientC_50; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180072e62  mov     edx, 155h; void *
0x180072e67  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180072e6c  mov     edi, eax
0x180072e6e  jmp     loc_180072F77
0x180072e73  mov     rax, [r14+120h]
0x180072e7a  lea     rcx, qword_1800EF060
0x180072e81  test    rax, rax
0x180072e84  cmovnz  rcx, rax
0x180072e88  add     rcx, 30h ; '0'
0x180072e8c  mov     rax, [rcx]
0x180072e8f  lea     rdx, [rbp+var_20]
0x180072e93  mov     rax, [rax+78h]
0x180072e97  call    _guard_dispatch_icall
0x180072e9c  mov     edi, eax
0x180072e9e  test    eax, eax
0x180072ea0  jns     short loc_180072EAC
0x180072ea2  mov     edx, 15Eh
0x180072ea7  jmp     loc_180072F64
0x180072eac  mov     [rbp+var_1C], ebx
0x180072eaf  mov     rcx, [rbp+pv]; pv
0x180072eb3  test    rcx, rcx
0x180072eb6  jz      short loc_180072EBE
0x180072eb8  call    cs:__imp_CoTaskMemFree
0x180072ebe  mov     edx, [rbp+var_20]
0x180072ec1  movzx   eax, byte ptr [r14+130h]
0x180072ec9  lea     rcx, [r14+8]; this
0x180072ecd  lea     r8, [rbp+pv]
0x180072ed1  mov     [rsp+80h+var_40], r8; struct tagDSServiceProps **
0x180072ed6  mov     [rsp+80h+var_48], eax; int
0x180072eda  mov     [rsp+80h+var_50], rbx; struct tagProxySettings *
0x180072edf  lea     rax, [rbp+var_1C]
0x180072ee3  mov     [rsp+80h+var_58], rax; unsigned int *
0x180072ee8  mov     [rsp+80h+var_60], edx; int
0x180072eec  lea     r8, [rbp+Uuid]; struct _GUID *
0x180072ef0  xor     edx, edx; wchar_t *
0x180072ef2  call    ?AddService2@CSusInternalWrapper@@QEAAJPEB_WAEBU_GUID@@0KPEAKPEBUtagProxySettings@@HPEAPEAUtagDSServiceProps@@@Z; CSusInternalWrapper::AddService2(wchar_t const *,_GUID const &,wchar_t const *,ulong,ulong *,tagProxySettings const *,int,tagDSServiceProps * *)
0x180072ef7  mov     edi, eax
0x180072ef9  test    eax, eax
0x180072efb  jns     short loc_180072F04
0x180072efd  mov     edx, 169h
0x180072f02  jmp     short loc_180072F64
0x180072f04  lea     rcx, [rbp+var_30]
0x180072f08  call    ?CreateInstance@?$CComObject@VCUpdateServiceRegistration@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUpdateServiceRegistration>::CreateInstance(ATL::CComObject<CUpdateServiceRegistration> * *)
0x180072f0d  mov     edi, eax
0x180072f0f  test    eax, eax
0x180072f11  jns     short loc_180072F31
0x180072f13  mov     rcx, [rbp+28h]; this
0x180072f17  mov     r9d, eax; char *
0x180072f1a  lea     r8, aCW1SSrcClientC_50; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180072f21  mov     edx, 16Ch; void *
0x180072f26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072f2b  mov     rbx, [rbp+var_30]
0x180072f2f  jmp     short loc_180072F77
0x180072f31  mov     rbx, [rbp+var_30]
0x180072f35  lea     rcx, [rbx+8]
0x180072f39  mov     rax, [rcx]
0x180072f3c  mov     rax, [rax+8]
0x180072f40  call    _guard_dispatch_icall
0x180072f45  mov     r9d, [rbp+var_1C]; unsigned int
0x180072f49  mov     r8, [rbp+pv]; struct tagDSServiceProps *
0x180072f4d  lea     rdx, [rbp+Uuid]; Uuid
0x180072f51  mov     rcx, rbx; this
0x180072f54  call    ?Initialize@CUpdateServiceRegistration@@QEAAJAEBU_GUID@@PEBUtagDSServiceProps@@K@Z; CUpdateServiceRegistration::Initialize(_GUID const &,tagDSServiceProps const *,ulong)
0x180072f59  mov     edi, eax
0x180072f5b  test    eax, eax
0x180072f5d  jns     short loc_180072F7D
0x180072f5f  mov     edx, 170h; void *
0x180072f64  mov     r9d, eax; char *
0x180072f67  lea     r8, aCW1SSrcClientC_50; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180072f6e  mov     rcx, [rbp+28h]; this
0x180072f72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072f77  mov     rcx, [rbp+pv]
0x180072f7b  jmp     short loc_180072F9A
0x180072f7d  xor     ecx, ecx; struct tagDSServiceProps *
0x180072f7f  mov     [rbp+pv], rcx
0x180072f83  mov     rax, rbx
0x180072f86  xor     ebx, ebx
0x180072f88  lea     rdx, [rax+8]; unsigned int
0x180072f8c  neg     rax
0x180072f8f  sbb     rax, rax
0x180072f92  and     rax, rdx
0x180072f95  mov     [rsi], rax
0x180072f98  xor     edi, edi
0x180072f9a  call    ?DsqFreeObject@@YAXPEAUtagDSServiceProps@@KH@Z; DsqFreeObject(tagDSServiceProps *,ulong,int)
0x180072f9f  nop
0x180072fa0  test    rbx, rbx
0x180072fa3  jz      short loc_180072FB6
0x180072fa5  lea     rcx, [rbx+8]
0x180072fa9  mov     rax, [rcx]
0x180072fac  mov     rax, [rax+10h]
0x180072fb0  call    _guard_dispatch_icall
0x180072fb5  nop
0x180072fb6  mov     rcx, [rbp+pv]; pv
0x180072fba  test    rcx, rcx
0x180072fbd  jz      short loc_180072FC5
0x180072fbf  call    cs:__imp_CoTaskMemFree
0x180072fc5  mov     eax, edi
0x180072fc7  mov     rcx, [rbp+var_8]
0x180072fcb  xor     rcx, rsp; StackCookie
0x180072fce  call    __security_check_cookie
0x180072fd3  add     rsp, 80h
0x180072fda  pop     r14
0x180072fdc  pop     rdi
0x180072fdd  pop     rsi
0x180072fde  pop     rbx
0x180072fdf  pop     rbp
0x180072fe0  retn
```
