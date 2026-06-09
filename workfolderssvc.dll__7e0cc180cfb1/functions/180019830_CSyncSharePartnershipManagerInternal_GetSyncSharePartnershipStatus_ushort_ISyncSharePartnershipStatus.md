# CSyncSharePartnershipManagerInternal::GetSyncSharePartnershipStatus(ushort *,ISyncSharePartnershipStatus * *)

- ea: `0x180019830`
- end: `0x180019ab5`
- name: `?GetSyncSharePartnershipStatus@CSyncSharePartnershipManagerInternal@@UEAAJPEAGPEAPEAUISyncSharePartnershipStatus@@@Z`
- size: `645`
- prototype: `int(CSyncSharePartnershipManagerInternal *__hidden this, unsigned __int16 *, struct ISyncSharePartnershipStatus **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007e10`
- `0x180008b60`
- `0x180009158`
- `0x180009384`
- `0x180011314`
- `0x180016798`
- `0x180019830`
- `0x18001a6a8`
- `0x180023e64`
- `0x180025f1c`
- `0x18002650c`
- `0x18013e010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800198df`
- `OLEAUT32!__imp_SysStringLen` at `0x1800198df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a74`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180019954`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180019954`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSyncSharePartnershipManagerInternal::GetSyncSharePartnershipStatus(
        CSyncStateManager **this,
        unsigned __int16 *a2,
        struct ISyncSharePartnershipStatus **a3)
{
  _BYTE *v6; // rax
  char v7; // al
  HRESULT v8; // eax
  int SyncShareStatusCode; // r15d
  int v10; // eax
  CSyncSharePartnershipStatus *v11; // rdi
  struct ISyncSharePartnershipStatus *v12; // rax
  unsigned int v13; // ebx
  int v15; // [rsp+20h] [rbp-B8h] BYREF
  int v16; // [rsp+24h] [rbp-B4h]
  char v17; // [rsp+28h] [rbp-B0h]
  const char *v18; // [rsp+30h] [rbp-A8h]
  __int64 v19; // [rsp+38h] [rbp-A0h]
  int pExceptionObject; // [rsp+40h] [rbp-98h] BYREF
  int v21; // [rsp+44h] [rbp-94h] BYREF
  HRESULT v22; // [rsp+48h] [rbp-90h] BYREF
  int v23; // [rsp+4Ch] [rbp-8Ch] BYREF
  CSyncSharePartnershipStatus *v24; // [rsp+50h] [rbp-88h] BYREF
  CSyncSharePartnershipStatus *v25; // [rsp+58h] [rbp-80h] BYREF
  int v26; // [rsp+60h] [rbp-78h] BYREF
  struct _FILETIME v27; // [rsp+68h] [rbp-70h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+70h] [rbp-68h] BYREF
  char v29; // [rsp+78h] [rbp-60h]
  const ATL::CAtlException *v30; // [rsp+80h] [rbp-58h] BYREF
  _BYTE v31[32]; // [rsp+88h] [rbp-50h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_8:
      v7 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 93, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( (v6[68] & 8) == 0 || v6[65] < 6u )
    goto LABEL_8;
  v7 = 1;
LABEL_9:
  v15 = 0;
  v16 = 1663;
  v17 = v7;
  v18 = "CSyncSharePartnershipManagerInternal::GetSyncSharePartnershipStatus";
  v19 = 0;
  try
  {
    if ( a3 )
      *a3 = 0;
    if ( !SysStringLen(a2) )
    {
      v15 = -2147024809;
      HIWORD(v16) = 1668;
      pExceptionObject = -2147024809;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v16) = 1668;
    v15 = 0;
    if ( !a3 )
    {
      v15 = -2147024809;
      HIWORD(v16) = 1669;
      v21 = -2147024809;
      throw (long *)&v21;
    }
    LOWORD(v16) = 1669;
    v8 = CoImpersonateClient();
    v15 = v8;
    if ( v8 < 0 )
    {
      HIWORD(v16) = 1671;
      v22 = v8;
      throw (long *)&v22;
    }
    LOWORD(v16) = 1671;
    CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(&lpCriticalSection, this + 27);
    CSyncStateManager::AddImpersonatingUser(this[18], (__int64)v31);
    std::wstring::~wstring(v31);
    SyncShareStatusCode = CSyncStateManager::GetSyncShareStatusCode(this[18], a2);
    CSyncStateManager::GetLastSucceedSyncTime(this[18], (const unsigned __int16 *)&v27);
    v25 = 0;
    v10 = ATL::CComObject<CSyncSharePartnershipStatus>::CreateInstance(&v25);
    v15 = v10;
    if ( v10 < 0 )
    {
      HIWORD(v16) = 1681;
      v23 = v10;
      throw (long *)&v23;
    }
    LOWORD(v16) = 1681;
    v11 = v25;
    v24 = v25;
    if ( v25 )
      (*(void (__fastcall **)(CSyncSharePartnershipStatus *))(*(_QWORD *)v25 + 8LL))(v25);
    CSyncSharePartnershipStatus::Initialize(v11, SyncShareStatusCode, &v27);
    v12 = v24;
    v24 = 0;
    *a3 = v12;
    ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v24);
    if ( v29 )
    {
      LeaveCriticalSection(lpCriticalSection);
      v29 = 0;
    }
  }
  catch ( long v26 )
  {
    v15 = v26;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v16) = 1688;
    v15 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v16) = 1688;
    v15 = -2147418113;
  }
  catch ( const ATL::CAtlException *v30 )
  {
    HIWORD(v16) = 1688;
    v15 = *(_DWORD *)v30;
  }
  v13 = v15;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v15);
  return v13;
}

```

## disassembly

```asm
0x180019830  push    rbx
0x180019832  push    rsi
0x180019833  push    rdi
0x180019834  push    r14
0x180019836  push    r15
0x180019838  sub     rsp, 0B0h
0x18001983f  mov     rax, cs:__security_cookie
0x180019846  xor     rax, rsp
0x180019849  mov     [rsp+0D8h+var_30], rax
0x180019851  mov     rsi, r8
0x180019854  mov     rdi, rdx
0x180019857  mov     r14, rcx
0x18001985a  lea     rcx, WPP_GLOBAL_Control
0x180019861  mov     rax, cs:WPP_GLOBAL_Control
0x180019868  cmp     rax, rcx
0x18001986b  jz      short loc_180019895
0x18001986d  test    byte ptr [rax+44h], 8
0x180019871  jz      short loc_1800198A7
0x180019873  cmp     byte ptr [rax+41h], 6
0x180019877  jb      short loc_180019895
0x180019879  mov     edx, 5Dh ; ']'
0x18001987e  lea     r8, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids
0x180019885  mov     rcx, [rax+38h]
0x180019889  call    WPP_SF_
0x18001988e  mov     rax, cs:WPP_GLOBAL_Control
0x180019895  test    byte ptr [rax+44h], 8
0x180019899  jz      short loc_1800198A7
0x18001989b  cmp     byte ptr [rax+41h], 6
0x18001989f  jb      short loc_1800198A7
0x1800198a1  mov     al, 1
0x1800198a3  xor     ebx, ebx
0x1800198a5  jmp     short loc_1800198AB
0x1800198a7  xor     ebx, ebx
0x1800198a9  mov     al, bl
0x1800198ab  mov     [rsp+0D8h+var_B8], ebx
0x1800198af  mov     [rsp+0D8h+var_B4], 67Fh
0x1800198b7  mov     [rsp+0D8h+var_B0], al
0x1800198bb  lea     rax, aCsyncsharepart_41; "CSyncSharePartnershipManagerInternal::G"...
0x1800198c2  mov     [rsp+0D8h+var_A8], rax
0x1800198c7  mov     [rsp+0D8h+var_A0], rbx
0x1800198cc  test    rsi, rsi
0x1800198cf  jz      short loc_1800198D4
0x1800198d1  mov     [rsi], rbx
0x1800198d4  mov     eax, [rsp+0D8h+var_B8]
0x1800198d8  mov     [rsp+0D8h+var_B8], eax
0x1800198dc  mov     rcx, rdi; pbstr
0x1800198df  call    cs:__imp_SysStringLen
0x1800198e5  mov     ecx, 684h
0x1800198ea  test    eax, eax
0x1800198ec  jnz     short loc_180019911
0x1800198ee  mov     eax, 80070057h
0x1800198f3  mov     [rsp+0D8h+var_B8], eax
0x1800198f7  mov     word ptr [rsp+0D8h+var_B4+2], cx
0x1800198fc  mov     [rsp+0D8h+pExceptionObject], eax
0x180019900  lea     rdx, _TI1J; pThrowInfo
0x180019907  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18001990c  call    _CxxThrowException_0
0x180019911  mov     [rsp+0D8h+var_B8], ebx
0x180019915  mov     word ptr [rsp+0D8h+var_B4], cx
0x18001991a  mov     [rsp+0D8h+var_B8], ebx
0x18001991e  mov     ecx, 685h
0x180019923  test    rsi, rsi
0x180019926  jnz     short loc_18001994B
0x180019928  mov     eax, 80070057h
0x18001992d  mov     [rsp+0D8h+var_B8], eax
0x180019931  mov     word ptr [rsp+0D8h+var_B4+2], cx
0x180019936  mov     [rsp+0D8h+var_94], eax
0x18001993a  lea     rdx, _TI1J; pThrowInfo
0x180019941  lea     rcx, [rsp+0D8h+var_94]; pExceptionObject
0x180019946  call    _CxxThrowException_0
0x18001994b  mov     [rsp+0D8h+var_B8], ebx
0x18001994f  mov     word ptr [rsp+0D8h+var_B4], cx
0x180019954  call    cs:__imp_CoImpersonateClient
0x18001995a  mov     [rsp+0D8h+var_B8], eax
0x18001995e  mov     [rsp+0D8h+var_B8], eax
0x180019962  mov     ecx, 687h
0x180019967  test    eax, eax
0x180019969  jns     short loc_180019985
0x18001996b  mov     word ptr [rsp+0D8h+var_B4+2], cx
0x180019970  mov     [rsp+0D8h+var_90], eax
0x180019974  lea     rdx, _TI1J; pThrowInfo
0x18001997b  lea     rcx, [rsp+0D8h+var_90]; pExceptionObject
0x180019980  call    _CxxThrowException_0
0x180019985  mov     word ptr [rsp+0D8h+var_B4], cx
0x18001998a  lea     rdx, [r14+0D8h]
0x180019991  lea     rcx, [rsp+0D8h+lpCriticalSection]
0x180019996  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x18001999b  nop
0x18001999c  lea     rdx, [rsp+0D8h+var_50]
0x1800199a4  mov     rcx, [r14+90h]; this
0x1800199ab  call    ?AddImpersonatingUser@CSyncStateManager@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CSyncStateManager::AddImpersonatingUser(void)
0x1800199b0  lea     rcx, [rsp+0D8h+var_50]
0x1800199b8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800199bd  mov     rdx, rdi; unsigned __int16 *
0x1800199c0  mov     rcx, [r14+90h]; this
0x1800199c7  call    ?GetSyncShareStatusCode@CSyncStateManager@@QEAAJPEBG@Z; CSyncStateManager::GetSyncShareStatusCode(ushort const *)
0x1800199cc  mov     r15d, eax
0x1800199cf  mov     r8, rdi
0x1800199d2  lea     rdx, [rsp+0D8h+var_70]; unsigned __int16 *
0x1800199d7  mov     rcx, [r14+90h]; this
0x1800199de  call    ?GetLastSucceedSyncTime@CSyncStateManager@@QEAA?AU_FILETIME@@PEBG@Z; CSyncStateManager::GetLastSucceedSyncTime(ushort const *)
0x1800199e3  mov     [rsp+0D8h+var_80], rbx
0x1800199e8  lea     rcx, [rsp+0D8h+var_80]
0x1800199ed  call    ?CreateInstance@?$CComObject@VCSyncSharePartnershipStatus@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSyncSharePartnershipStatus>::CreateInstance(ATL::CComObject<CSyncSharePartnershipStatus> * *)
0x1800199f2  mov     [rsp+0D8h+var_B8], eax
0x1800199f6  mov     [rsp+0D8h+var_B8], eax
0x1800199fa  mov     ecx, 691h
0x1800199ff  test    eax, eax
0x180019a01  jns     short loc_180019A1D
0x180019a03  mov     word ptr [rsp+0D8h+var_B4+2], cx
0x180019a08  mov     [rsp+0D8h+var_8C], eax
0x180019a0c  lea     rdx, _TI1J; pThrowInfo
0x180019a13  lea     rcx, [rsp+0D8h+var_8C]; pExceptionObject
0x180019a18  call    _CxxThrowException_0
0x180019a1d  mov     word ptr [rsp+0D8h+var_B4], cx
0x180019a22  mov     rdi, [rsp+0D8h+var_80]
0x180019a27  mov     [rsp+0D8h+var_88], rdi
0x180019a2c  test    rdi, rdi
0x180019a2f  jz      short loc_180019A41
0x180019a31  mov     rax, [rdi]
0x180019a34  mov     rcx, rdi
0x180019a37  mov     rax, [rax+8]
0x180019a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a40  nop
0x180019a41  lea     r8, [rsp+0D8h+var_70]; struct _FILETIME *
0x180019a46  mov     edx, r15d; int
0x180019a49  mov     rcx, rdi; this
0x180019a4c  call    ?Initialize@CSyncSharePartnershipStatus@@QEAAXJAEAU_FILETIME@@@Z; CSyncSharePartnershipStatus::Initialize(long,_FILETIME &)
0x180019a51  mov     rax, [rsp+0D8h+var_88]
0x180019a56  mov     [rsp+0D8h+var_88], rbx
0x180019a5b  mov     [rsi], rax
0x180019a5e  lea     rcx, [rsp+0D8h+var_88]
0x180019a63  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x180019a68  nop
0x180019a69  cmp     [rsp+0D8h+var_60], bl
0x180019a6d  jz      short loc_180019A7E
0x180019a6f  mov     rcx, [rsp+0D8h+lpCriticalSection]; lpCriticalSection
0x180019a74  call    cs:__imp_LeaveCriticalSection
0x180019a7a  mov     [rsp+0D8h+var_60], bl
0x180019a7e  jmp     short loc_180019A86
0x180019a80  jmp     short loc_180019A86
0x180019a82  jmp     short loc_180019A86
0x180019a84  jmp     short $+2
0x180019a86  mov     ebx, [rsp+0D8h+var_B8]
0x180019a8a  lea     rcx, [rsp+0D8h+var_B8]; this
0x180019a8f  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180019a94  mov     eax, ebx
0x180019a96  mov     rcx, [rsp+0D8h+var_30]
0x180019a9e  xor     rcx, rsp; StackCookie
0x180019aa1  call    __security_check_cookie
0x180019aa6  add     rsp, 0B0h
0x180019aad  pop     r15
0x180019aaf  pop     r14
0x180019ab1  pop     rdi
0x180019ab2  pop     rsi
0x180019ab3  pop     rbx
0x180019ab4  retn
```
