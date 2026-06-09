# UdmSvcImpl_GenerateValidationToken

- ea: `0x1800a5940`
- end: `0x1800a5b08`
- name: `UdmSvcImpl_GenerateValidationToken`
- size: `456`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x18000bb30`
- `0x180018c20`
- `0x18001b340`
- `0x180020994`
- `0x180068458`
- `0x18009e5e4`
- `0x1800a5940`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a5a7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a5a7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a5ab9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a5ad1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a5ab9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a5ad1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800a5a0b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800a5a0b`

## string_xrefs

- `0x1800a59c0`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800a59ef`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800a5a55`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800a5a9c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`

## pseudocode

```c
__int64 __fastcall UdmSvcImpl_GenerateValidationToken(
        struct __MIDL_UserDataModelService_0001 *a1,
        __int64 a2,
        GUID *a3)
{
  int ServiceDataSession; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  struct ServiceDataSession *v10; // rbx
  int v11; // esi
  __int64 v12; // r9
  int v13; // eax
  int AppPackageFamilyName; // eax
  char *v15; // rcx
  int v17; // [rsp+30h] [rbp-39h] BYREF
  struct ServiceDataSession *v18; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v19[16]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v20; // [rsp+50h] [rbp-19h] BYREF
  int v21; // [rsp+58h] [rbp-11h]
  _BYTE v22[32]; // [rsp+60h] [rbp-9h] BYREF
  struct ServiceDataSession *v23; // [rsp+80h] [rbp+17h]
  GUID pguid; // [rsp+88h] [rbp+1Fh] BYREF

  v18 = 0;
  ServiceDataSession = GetServiceDataSession(a1, &v18);
  v6 = ServiceDataSession;
  if ( ServiceDataSession < 0 )
  {
    v7 = 3457;
    v8 = 1;
    v9 = (unsigned int)ServiceDataSession;
LABEL_8:
    Log_HREvent(
      v9,
      v8,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      v7);
    goto LABEL_17;
  }
  v10 = v18;
  v17 = 0;
  v11 = ServiceDataSession::ValidateCallerSecurityForId(v18, a2, 1u, 0, (enum ObjectAccess *)&v17);
  if ( v11 < 0 )
  {
    v12 = 3460;
LABEL_5:
    Log_HREvent(
      (unsigned int)v11,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      v12);
    v6 = v11;
    goto LABEL_17;
  }
  if ( v17 < 1 )
  {
    v6 = -2147024891;
    v7 = 3461;
    v9 = 2147942405LL;
    v8 = 0;
    goto LABEL_8;
  }
  pguid = 0;
  v11 = CoCreateGuid(&pguid);
  if ( v11 < 0 )
  {
    v12 = 3464;
    goto LABEL_5;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v22);
  v13 = *(_DWORD *)(a2 + 8);
  v20 = *(_QWORD *)a2;
  v21 = v13;
  v23 = v10;
  AppPackageFamilyName = ServiceDataSession::GetAppPackageFamilyName(v10, v22);
  v6 = AppPackageFamilyName;
  if ( AppPackageFamilyName >= 0 )
  {
    EnterCriticalSection(&g_validationTokensLock);
    if ( *(_QWORD *)utl::_HashTable<_GUID,utl::pair<_GUID const,ValidationTokenInfo>,GuidHashTraits,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,ValidationTokenInfo>>,0>::emplace<_GUID &,ValidationTokenInfo,0>(
                      v15,
                      (__int64)v19,
                      &pguid,
                      (__int64)&v20) )
    {
      *a3 = pguid;
      LeaveCriticalSection(&g_validationTokensLock);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v22);
      v6 = 0;
      goto LABEL_17;
    }
    v6 = -2147024882;
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      3472);
    LeaveCriticalSection(&g_validationTokensLock);
  }
  else
  {
    Log_HREvent(
      (unsigned int)AppPackageFamilyName,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      3469);
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v22);
LABEL_17:
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v18);
  return v6;
}

```

## disassembly

```asm
0x1800a5940  push    rbp
0x1800a5942  push    rbx
0x1800a5943  push    rsi
0x1800a5944  push    r14
0x1800a5946  push    r15
0x1800a5948  lea     rbp, [rsp-37h]
0x1800a594d  sub     rsp, 0A0h
0x1800a5954  mov     rax, cs:__security_cookie
0x1800a595b  xor     rax, rsp
0x1800a595e  mov     [rbp+57h+var_28], rax
0x1800a5962  mov     r14, rdx
0x1800a5965  mov     [rbp+57h+var_88], 0
0x1800a596d  lea     rdx, [rbp+57h+var_88]; struct ServiceDataSession **
0x1800a5971  mov     r15, r8
0x1800a5974  call    ?GetServiceDataSession@@YAJPEAU__MIDL_UserDataModelService_0001@@PEAPEAVServiceDataSession@@@Z; GetServiceDataSession(__MIDL_UserDataModelService_0001 *,ServiceDataSession * *)
0x1800a5979  mov     ebx, eax
0x1800a597b  test    eax, eax
0x1800a597d  jns     short loc_1800A598E
0x1800a597f  mov     r9d, 0D81h
0x1800a5985  mov     edx, 1
0x1800a598a  mov     ecx, eax
0x1800a598c  jmp     short loc_1800A59EF
0x1800a598e  mov     rbx, [rbp+57h+var_88]
0x1800a5992  lea     rax, [rbp+57h+var_90]
0x1800a5996  xor     r9d, r9d
0x1800a5999  mov     [rbp+57h+var_90], 0
0x1800a59a0  mov     rdx, r14
0x1800a59a3  mov     [rsp+0C0h+var_A0], rax
0x1800a59a8  mov     rcx, rbx
0x1800a59ab  lea     r8d, [r9+1]
0x1800a59af  call    ?ValidateCallerSecurityForId@ServiceDataSession@@QEAAJAEBUUdmObjectId@@W4DataSessionAccessType@@PEAW4ObjectAccess@@2@Z; ServiceDataSession::ValidateCallerSecurityForId(UdmObjectId const &,DataSessionAccessType,ObjectAccess *,ObjectAccess *)
0x1800a59b4  mov     esi, eax
0x1800a59b6  test    eax, eax
0x1800a59b8  jns     short loc_1800A59DA
0x1800a59ba  mov     r9d, 0D84h
0x1800a59c0  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800a59c7  mov     edx, 1
0x1800a59cc  mov     ecx, esi
0x1800a59ce  call    Log_HREvent
0x1800a59d3  mov     ebx, esi
0x1800a59d5  jmp     loc_1800A5AE2
0x1800a59da  cmp     [rbp+57h+var_90], 1
0x1800a59de  jge     short loc_1800A5A00
0x1800a59e0  mov     ebx, 80070005h
0x1800a59e5  mov     r9d, 0D85h
0x1800a59eb  mov     ecx, ebx
0x1800a59ed  xor     edx, edx
0x1800a59ef  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800a59f6  call    Log_HREvent
0x1800a59fb  jmp     loc_1800A5AE2
0x1800a5a00  xorps   xmm0, xmm0
0x1800a5a03  lea     rcx, [rbp+57h+pguid]; pguid
0x1800a5a07  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x1800a5a0b  call    cs:__imp_CoCreateGuid
0x1800a5a11  mov     esi, eax
0x1800a5a13  test    eax, eax
0x1800a5a15  jns     short loc_1800A5A1F
0x1800a5a17  mov     r9d, 0D88h
0x1800a5a1d  jmp     short loc_1800A59C0
0x1800a5a1f  lea     rcx, [rbp+57h+var_60]; void *
0x1800a5a23  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800a5a28  movsd   xmm0, qword ptr [r14]
0x1800a5a2d  lea     rdx, [rbp+57h+var_60]
0x1800a5a31  mov     eax, [r14+8]
0x1800a5a35  mov     rcx, rbx
0x1800a5a38  movsd   [rbp+57h+var_70], xmm0
0x1800a5a3d  mov     [rbp+57h+var_68], eax
0x1800a5a40  mov     [rbp+57h+var_40], rbx
0x1800a5a44  call    ?GetAppPackageFamilyName@ServiceDataSession@@QEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; ServiceDataSession::GetAppPackageFamilyName(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x1800a5a49  mov     ebx, eax
0x1800a5a4b  test    eax, eax
0x1800a5a4d  jns     short loc_1800A5A73
0x1800a5a4f  mov     r9d, 0D8Dh
0x1800a5a55  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800a5a5c  mov     edx, 1
0x1800a5a61  mov     ecx, eax
0x1800a5a63  call    Log_HREvent
0x1800a5a68  lea     rcx, [rbp+57h+var_60]; void *
0x1800a5a6c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800a5a71  jmp     short loc_1800A5AE2
0x1800a5a73  lea     rcx, ?g_validationTokensLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800a5a7a  call    cs:__imp_EnterCriticalSection
0x1800a5a80  lea     r9, [rbp+57h+var_70]
0x1800a5a84  lea     r8, [rbp+57h+pguid]
0x1800a5a88  lea     rdx, [rbp+57h+var_80]
0x1800a5a8c  call    ??$emplace@AEAU_GUID@@UValidationTokenInfo@@$0A@@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UValidationTokenInfo@@@utl@@UGuidHashTraits@@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UValidationTokenInfo@@@utl@@@3@$0A@@utl@@QEAA?AU?$pair@V?$_DlistIt@U?$_HashNode@U?$pair@$$CBU_GUID@@UValidationTokenInfo@@@utl@@@utl@@U?$pair@$$CBU_GUID@@UValidationTokenInfo@@@2@@utl@@_N@1@AEAU_GUID@@$$QEAUValidationTokenInfo@@@Z; utl::_HashTable<_GUID,utl::pair<_GUID const,ValidationTokenInfo>,GuidHashTraits,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,ValidationTokenInfo>>,0>::emplace<_GUID &,ValidationTokenInfo,0>(_GUID &,ValidationTokenInfo &&)
0x1800a5a91  cmp     qword ptr [rax], 0
0x1800a5a95  jnz     short loc_1800A5AC1
0x1800a5a97  mov     ebx, 8007000Eh
0x1800a5a9c  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800a5aa3  mov     ecx, ebx
0x1800a5aa5  mov     r9d, 0D90h
0x1800a5aab  xor     edx, edx
0x1800a5aad  call    Log_HREvent
0x1800a5ab2  lea     rcx, ?g_validationTokensLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800a5ab9  call    cs:__imp_LeaveCriticalSection
0x1800a5abf  jmp     short loc_1800A5A68
0x1800a5ac1  movups  xmm0, xmmword ptr [rbp+57h+pguid.Data1]
0x1800a5ac5  lea     rcx, ?g_validationTokensLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800a5acc  movdqu  xmmword ptr [r15], xmm0
0x1800a5ad1  call    cs:__imp_LeaveCriticalSection
0x1800a5ad7  lea     rcx, [rbp+57h+var_60]; void *
0x1800a5adb  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800a5ae0  xor     ebx, ebx
0x1800a5ae2  lea     rcx, [rbp+57h+var_88]
0x1800a5ae6  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800a5aeb  mov     eax, ebx
0x1800a5aed  mov     rcx, [rbp+57h+var_28]
0x1800a5af1  xor     rcx, rsp; StackCookie
0x1800a5af4  call    __security_check_cookie
0x1800a5af9  add     rsp, 0A0h
0x1800a5b00  pop     r15
0x1800a5b02  pop     r14
0x1800a5b04  pop     rsi
0x1800a5b05  pop     rbx
0x1800a5b06  pop     rbp
0x1800a5b07  retn
```
