# DBManager::_InitializeJetInstance(ushort const *)

- ea: `0x180018ab0`
- end: `0x180019100`
- name: `?_InitializeJetInstance@DBManager@@IEAAJPEBG@Z`
- size: `1616`
- prototype: `int(DBManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800189b4`

## callees

- `0x1800068f0`
- `0x18000f530`
- `0x180018ab0`
- `0x180022ee0`
- `0x180043efc`
- `0x18006f180`
- `0x180073330`
- `0x180076734`
- `0x180081398`
- `0x1800c3f20`
- `0x1800c3f54`
- `0x1800c4018`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018c60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018c60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018c78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018c78`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018b5a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018b5a`
- `ESENT!JetSetSystemParameterA` at `0x180018c90`
- `ESENT!JetSetSystemParameterA` at `0x180018cba`
- `ESENT!JetSetSystemParameterA` at `0x180018ce7`
- `ESENT!JetSetSystemParameterA` at `0x180018d14`
- `ESENT!JetSetSystemParameterA` at `0x180018d44`
- `ESENT!JetSetSystemParameterA` at `0x180018d74`
- `ESENT!JetSetSystemParameterA` at `0x180018da1`
- `ESENT!JetSetSystemParameterA` at `0x180018dd1`
- `ESENT!JetSetSystemParameterA` at `0x180018e01`
- `ESENT!JetSetSystemParameterA` at `0x180018e31`
- `ESENT!JetSetSystemParameterA` at `0x180018e61`
- `ESENT!JetSetSystemParameterA` at `0x180018e8e`
- `ESENT!JetSetSystemParameterA` at `0x180018faa`
- `ESENT!JetSetSystemParameterA` at `0x180018fdb`
- `ESENT!JetSetSystemParameterA` at `0x180018c90`
- `ESENT!JetSetSystemParameterA` at `0x180018cba`
- `ESENT!JetSetSystemParameterA` at `0x180018ce7`
- `ESENT!JetSetSystemParameterA` at `0x180018d14`
- `ESENT!JetSetSystemParameterA` at `0x180018d44`
- `ESENT!JetSetSystemParameterA` at `0x180018d74`
- `ESENT!JetSetSystemParameterA` at `0x180018da1`
- `ESENT!JetSetSystemParameterA` at `0x180018dd1`
- `ESENT!JetSetSystemParameterA` at `0x180018e01`
- `ESENT!JetSetSystemParameterA` at `0x180018e31`
- `ESENT!JetSetSystemParameterA` at `0x180018e61`
- `ESENT!JetSetSystemParameterA` at `0x180018e8e`
- `ESENT!JetSetSystemParameterA` at `0x180018faa`
- `ESENT!JetSetSystemParameterA` at `0x180018fdb`
- `ESENT!JetSetSystemParameterW` at `0x180018ebb`
- `ESENT!JetSetSystemParameterW` at `0x180018ee8`
- `ESENT!JetSetSystemParameterW` at `0x180018f16`
- `ESENT!JetSetSystemParameterW` at `0x180018f47`
- `ESENT!JetSetSystemParameterW` at `0x180018f77`
- `ESENT!JetSetSystemParameterW` at `0x180019019`
- `ESENT!JetSetSystemParameterW` at `0x180019041`
- `ESENT!JetSetSystemParameterW` at `0x180018ebb`
- `ESENT!JetSetSystemParameterW` at `0x180018ee8`
- `ESENT!JetSetSystemParameterW` at `0x180018f16`
- `ESENT!JetSetSystemParameterW` at `0x180018f47`
- `ESENT!JetSetSystemParameterW` at `0x180018f77`
- `ESENT!JetSetSystemParameterW` at `0x180019019`
- `ESENT!JetSetSystemParameterW` at `0x180019041`
- `ESENT!JetInit2` at `0x180019062`
- `ESENT!JetInit2` at `0x180019062`
- `ESENT!JetCreateInstance2W` at `0x180018c34`
- `ESENT!JetCreateInstance2W` at `0x180018c34`
- `UserDataPlatformHelperUtil!SetCommsServiceJetGlobalSystemParameters` at `0x180018c0d`
- `UserDataPlatformHelperUtil!SetCommsServiceJetGlobalSystemParameters` at `0x180018c0d`

## string_xrefs

- `0x180018af3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180018bd9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180018bf3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBManager::_InitializeJetInstance(DBManager *this, const unsigned __int16 *a2)
{
  int IsShuttingDown; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  __int64 v7; // rcx
  JET_INSTANCE *v9; // rbx
  LSTATUS ValueW; // eax
  const unsigned __int16 *v11; // rdx
  HKEY v12; // rcx
  bool v13; // sf
  __int64 v14; // r8
  __int64 v15; // rcx
  int v16; // ebp
  __int64 v17; // r9
  JET_ERR Instance2W; // eax
  unsigned int HresultFromJetError; // eax
  JET_ERR v20; // eax
  JET_ERR v21; // eax
  JET_ERR v22; // eax
  JET_ERR v23; // eax
  JET_ERR v24; // eax
  JET_ERR v25; // eax
  JET_ERR v26; // eax
  JET_ERR v27; // eax
  JET_ERR v28; // eax
  JET_ERR v29; // eax
  JET_ERR v30; // eax
  JET_ERR v31; // eax
  JET_ERR v32; // eax
  JET_ERR v33; // eax
  JET_ERR v34; // eax
  JET_ERR v35; // eax
  JET_ERR v36; // eax
  JET_ERR v37; // eax
  JET_ERR v38; // eax
  JET_ERR v39; // eax
  JET_ERR v40; // eax
  JET_ERR v41; // eax
  __int64 v42; // rdx
  __int64 v43; // r8
  unsigned int v44; // ebx
  __int64 v45; // r9
  int pvData; // [rsp+40h] [rbp-48h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-44h] BYREF
  _BYTE v48[16]; // [rsp+48h] [rbp-40h] BYREF

  IsShuttingDown = FailIfServiceIsShuttingDown();
  if ( IsShuttingDown < 0 )
  {
    v5 = 1155;
    v6 = 1;
LABEL_3:
    v7 = (unsigned int)IsShuttingDown;
LABEL_4:
    Log_UnistoreHREvent_0(
      v7,
      v6,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v5);
    return (unsigned int)IsShuttingDown;
  }
  v9 = (JET_INSTANCE *)((char *)this + 64);
  if ( *((_QWORD *)this + 8) == -1 )
  {
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(
               HKEY_CURRENT_USER,
               L"Software\\Microsoft\\Unified Store",
               L"CorruptTestHook",
               0x20000018u,
               0,
               &pvData,
               &pcbData);
    v13 = ValueW < 0;
    if ( ValueW > 0 )
      v13 = 1;
    if ( !v13 && pvData && RegistryDeleteValue(v12, v11, L"CorruptTestHook") >= 0 )
    {
      if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x8000) != 0 )
        McGenEventWrite_EventWriteTransfer(
          &MICROSOFT_WINDOWS_USERDATAACCESS_UNIFIEDSTORE_Context,
          UnifiedStore_CorruptionTest,
          v14,
          1,
          v48);
      v5 = 1178;
      v6 = 0;
      IsShuttingDown = -2147023538;
      goto LABEL_3;
    }
    v16 = EnsureDirectory(a2);
    if ( v16 < 0 )
    {
      v17 = 1183;
LABEL_16:
      Log_UnistoreHREvent_0(
        (unsigned int)v16,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        v17);
      return (unsigned int)v16;
    }
    if ( *v9 != -1 )
      Log_AssertionEvent(
        v15,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        1185);
    v16 = SetCommsServiceJetGlobalSystemParameters();
    if ( v16 < 0 )
    {
      v17 = 1187;
      goto LABEL_16;
    }
    Instance2W = JetCreateInstance2W(v9, L"Unistore", L"Unistore", 0);
    if ( Instance2W < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(Instance2W);
      v5 = 1189;
LABEL_23:
      IsShuttingDown = HresultFromJetError;
      v6 = 0;
      v7 = HresultFromJetError;
      goto LABEL_4;
    }
    EnterCriticalSection(&g_csShutdownLock);
    ++g_numberOfSessions;
    LeaveCriticalSection(&g_csShutdownLock);
    v20 = JetSetSystemParameterA(v9, 0, 5u, 0x80u, 0);
    if ( v20 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v20);
      v5 = 1193;
      goto LABEL_23;
    }
    v21 = JetSetSystemParameterA(v9, 0, 0x11u, 1u, 0);
    if ( v21 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v21);
      v5 = 1194;
      goto LABEL_23;
    }
    v22 = JetSetSystemParameterA(v9, 0, 0x4Du, 1u, 0);
    if ( v22 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v22);
      v5 = 1195;
      goto LABEL_23;
    }
    v23 = JetSetSystemParameterA(v9, 0, 0x30u, 1u, 0);
    if ( v23 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v23);
      v5 = 1196;
      goto LABEL_23;
    }
    v24 = JetSetSystemParameterA(v9, 0, 0x18u, 0x500000u, 0);
    if ( v24 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v24);
      v5 = 1199;
      goto LABEL_23;
    }
    v25 = JetSetSystemParameterA(v9, 0, 0x98u, 2u, 0);
    if ( v25 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v25);
      v5 = 1202;
      goto LABEL_23;
    }
    v26 = JetSetSystemParameterA(v9, 0, 0x2Du, 1u, 0);
    if ( v26 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v26);
      v5 = 1205;
      goto LABEL_23;
    }
    v27 = JetSetSystemParameterA(v9, 0xFFFFFFFFFFFFFFFFuLL, 0x45u, 1u, 0);
    if ( v27 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v27);
      v5 = 1208;
      goto LABEL_23;
    }
    v28 = JetSetSystemParameterA(v9, 0, 0xBu, 0xC00u, 0);
    if ( v28 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v28);
      v5 = 1210;
      goto LABEL_23;
    }
    v29 = JetSetSystemParameterA(v9, 0, 0xCu, 0x500u, 0);
    if ( v29 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v29);
      v5 = 1218;
      goto LABEL_23;
    }
    v30 = JetSetSystemParameterA(v9, 0, 0x12u, 0x80u, 0);
    if ( v30 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v30);
      v5 = 1220;
      goto LABEL_23;
    }
    v31 = JetSetSystemParameterA(v9, 0, 0x10u, 1u, 0);
    if ( v31 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v31);
      v5 = 1223;
      goto LABEL_23;
    }
    v32 = JetSetSystemParameterW(v9, 0xFFFFFFFFFFFFFFFFuLL, 0, 0, a2);
    if ( v32 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v32);
      v5 = 1225;
      goto LABEL_23;
    }
    v33 = JetSetSystemParameterW(v9, 0xFFFFFFFFFFFFFFFFuLL, 1u, 0, a2);
    if ( v33 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v33);
      v5 = 1226;
      goto LABEL_23;
    }
    v34 = JetSetSystemParameterW(v9, 0xFFFFFFFFFFFFFFFFuLL, 2u, 0, a2);
    if ( v34 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v34);
      v5 = 1227;
      goto LABEL_23;
    }
    v35 = JetSetSystemParameterW(v9, 0xFFFFFFFFFFFFFFFFuLL, 0x71u, 0, a2);
    if ( v35 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v35);
      v5 = 1228;
      goto LABEL_23;
    }
    v36 = JetSetSystemParameterW(v9, 0xFFFFFFFFFFFFFFFFuLL, 0xC1u, 1u, 0);
    if ( v36 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v36);
      v5 = 1229;
      goto LABEL_23;
    }
    v37 = JetSetSystemParameterA(v9, 0xFFFFFFFFFFFFFFFFuLL, 0x88u, 2u, 0);
    if ( v37 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v37);
      v5 = 1230;
      goto LABEL_23;
    }
    v38 = JetSetSystemParameterA(v9, 0xFFFFFFFFFFFFFFFFuLL, 0xB2u, 0x50u, 0);
    if ( v38 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v38);
      v5 = 1233;
      goto LABEL_23;
    }
    if ( g_fForceInproc )
    {
      v39 = JetSetSystemParameterW(v9, 0xFFFFFFFFFFFFFFFFuLL, 3u, 0, L"USI");
      if ( v39 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v39);
        v5 = 1237;
        goto LABEL_23;
      }
    }
    else
    {
      v40 = JetSetSystemParameterW(v9, 0xFFFFFFFFFFFFFFFFuLL, 3u, 0, L"USS");
      if ( v40 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v40);
        v5 = 1241;
        goto LABEL_23;
      }
    }
    v41 = JetInit2(v9, 0);
    v44 = v41;
    if ( v41 )
    {
      if ( v41 == -1811 )
      {
        IsShuttingDown = -2147024894;
        v45 = 101;
LABEL_76:
        Log_HREvent_0((unsigned int)IsShuttingDown, v42, v43, v45);
        goto LABEL_77;
      }
      if ( (unsigned int)IsFatalJetInitializationError(v41) )
      {
        if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x40) != 0 )
          McTemplateU0d_EventWriteTransfer(&MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context, JetInitFailed, v44);
        v45 = 113;
        IsShuttingDown = -2147023538;
        goto LABEL_76;
      }
      IsShuttingDown = GetHresultFromJetError(v44);
      if ( IsShuttingDown < 0 )
      {
LABEL_77:
        v5 = 1244;
        v6 = 1;
        goto LABEL_3;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180018ab0  mov     [rsp+arg_10], rbx
0x180018ab5  mov     [rsp+arg_18], rbp
0x180018aba  push    rsi
0x180018abb  push    rdi
0x180018abc  push    r12
0x180018abe  push    r14
0x180018ac0  push    r15
0x180018ac2  sub     rsp, 60h
0x180018ac6  mov     rax, cs:__security_cookie
0x180018acd  xor     rax, rsp
0x180018ad0  mov     [rsp+88h+var_30], rax
0x180018ad5  mov     r14, rdx
0x180018ad8  mov     rdi, rcx
0x180018adb  call    ?FailIfServiceIsShuttingDown@@YAJXZ; FailIfServiceIsShuttingDown(void)
0x180018ae0  xor     r15d, r15d
0x180018ae3  mov     ebx, eax
0x180018ae5  test    eax, eax
0x180018ae7  jns     short loc_180018B08
0x180018ae9  mov     r9d, 483h
0x180018aef  lea     edx, [r15+1]
0x180018af3  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018afa  mov     ecx, ebx
0x180018afc  call    Log_UnistoreHREvent_0
0x180018b01  mov     eax, ebx
0x180018b03  jmp     loc_18001909C
0x180018b08  lea     rbx, [rdi+40h]
0x180018b0c  or      r12, 0FFFFFFFFFFFFFFFFh
0x180018b10  cmp     [rbx], r12
0x180018b13  jnz     loc_18001909A
0x180018b19  lea     rax, [rsp+88h+var_44]
0x180018b1e  mov     [rsp+88h+var_48], r15d
0x180018b23  mov     [rsp+88h+pcbData], rax; pcbData
0x180018b28  lea     r8, ?c_wszUnistoreRegistryCorruptTestHook@@3QBGB; "CorruptTestHook"
0x180018b2f  lea     rax, [rsp+88h+var_48]
0x180018b34  mov     [rsp+88h+var_44], 4
0x180018b3c  mov     [rsp+88h+pvData], rax; pvData
0x180018b41  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x180018b48  mov     r9d, 20000018h; dwFlags
0x180018b4e  mov     [rsp+88h+pdwType], r15; pdwType
0x180018b53  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180018b5a  call    cs:__imp_RegGetValueW
0x180018b60  test    eax, eax
0x180018b62  jle     short loc_180018B6E
0x180018b64  movzx   eax, ax
0x180018b67  or      eax, 80070000h
0x180018b6c  test    eax, eax
0x180018b6e  js      short loc_180018BC5
0x180018b70  cmp     [rsp+88h+var_48], r15d
0x180018b75  jbe     short loc_180018BC5
0x180018b77  lea     r8, ?c_wszUnistoreRegistryCorruptTestHook@@3QBGB; "CorruptTestHook"
0x180018b7e  call    ?RegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; RegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x180018b83  test    eax, eax
0x180018b85  js      short loc_180018BC5
0x180018b87  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits+1, 80h
0x180018b8e  jz      short loc_180018BB3
0x180018b90  lea     rax, [rsp+88h+var_40]
0x180018b95  mov     r9d, 1
0x180018b9b  lea     rdx, UnifiedStore_CorruptionTest
0x180018ba2  mov     [rsp+88h+pdwType], rax
0x180018ba7  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_UNIFIEDSTORE_Context
0x180018bae  call    McGenEventWrite_EventWriteTransfer
0x180018bb3  mov     r9d, 49Ah
0x180018bb9  xor     edx, edx
0x180018bbb  mov     ebx, 8007054Eh
0x180018bc0  jmp     loc_180018AF3
0x180018bc5  mov     rcx, r14; pszPath
0x180018bc8  call    ?EnsureDirectory@@YAJPEBG@Z; EnsureDirectory(ushort const *)
0x180018bcd  mov     ebp, eax
0x180018bcf  test    eax, eax
0x180018bd1  jns     short loc_180018BF3
0x180018bd3  mov     r9d, 49Fh
0x180018bd9  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018be0  mov     edx, 1
0x180018be5  mov     ecx, ebp
0x180018be7  call    Log_UnistoreHREvent_0
0x180018bec  mov     eax, ebp
0x180018bee  jmp     loc_18001909C
0x180018bf3  lea     rdi, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018bfa  cmp     [rbx], r12
0x180018bfd  jz      short loc_180018C0D
0x180018bff  mov     r8d, 4A1h
0x180018c05  mov     rdx, rdi
0x180018c08  call    Log_AssertionEvent
0x180018c0d  call    cs:__imp_SetCommsServiceJetGlobalSystemParameters
0x180018c13  mov     ebp, eax
0x180018c15  test    eax, eax
0x180018c17  jns     short loc_180018C24
0x180018c19  mov     r9d, 4A3h
0x180018c1f  mov     r8, rdi
0x180018c22  jmp     short loc_180018BE0
0x180018c24  lea     rdx, ?gc_szUSStoresFolderName@@3QBGB; "Unistore"
0x180018c2b  xor     r9d, r9d; grbit
0x180018c2e  mov     r8, rdx; szDisplayName
0x180018c31  mov     rcx, rbx; pinstance
0x180018c34  call    cs:__imp_JetCreateInstance2W
0x180018c3a  test    eax, eax
0x180018c3c  jns     short loc_180018C59
0x180018c3e  mov     ecx, eax; int
0x180018c40  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018c45  mov     r9d, 4A5h
0x180018c4b  mov     ebx, eax
0x180018c4d  mov     r8, rdi
0x180018c50  xor     edx, edx
0x180018c52  mov     ecx, eax
0x180018c54  jmp     loc_180018AFC
0x180018c59  lea     rcx, ?g_csShutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180018c60  call    cs:__imp_EnterCriticalSection
0x180018c66  mov     esi, 1
0x180018c6b  lea     rcx, ?g_csShutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180018c72  add     cs:?g_numberOfSessions@@3JA, esi; long g_numberOfSessions
0x180018c78  call    cs:__imp_LeaveCriticalSection
0x180018c7e  xor     edx, edx; sesid
0x180018c80  mov     [rsp+88h+pdwType], r15; szParam
0x180018c85  lea     r9d, [rsi+7Fh]; lParam
0x180018c89  mov     rcx, rbx; pinstance
0x180018c8c  lea     r8d, [rsi+4]; paramid
0x180018c90  call    cs:__imp_JetSetSystemParameterA
0x180018c96  test    eax, eax
0x180018c98  jns     short loc_180018CA9
0x180018c9a  mov     ecx, eax; int
0x180018c9c  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018ca1  mov     r9d, 4A9h
0x180018ca7  jmp     short loc_180018C4B
0x180018ca9  xor     edx, edx; sesid
0x180018cab  mov     [rsp+88h+pdwType], r15; szParam
0x180018cb0  mov     r9, rsi; lParam
0x180018cb3  mov     rcx, rbx; pinstance
0x180018cb6  lea     r8d, [rdx+11h]; paramid
0x180018cba  call    cs:__imp_JetSetSystemParameterA
0x180018cc0  test    eax, eax
0x180018cc2  jns     short loc_180018CD6
0x180018cc4  mov     ecx, eax; int
0x180018cc6  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018ccb  mov     r9d, 4AAh
0x180018cd1  jmp     loc_180018C4B
0x180018cd6  xor     edx, edx; sesid
0x180018cd8  mov     [rsp+88h+pdwType], r15; szParam
0x180018cdd  mov     r9, rsi; lParam
0x180018ce0  mov     rcx, rbx; pinstance
0x180018ce3  lea     r8d, [rdx+4Dh]; paramid
0x180018ce7  call    cs:__imp_JetSetSystemParameterA
0x180018ced  test    eax, eax
0x180018cef  jns     short loc_180018D03
0x180018cf1  mov     ecx, eax; int
0x180018cf3  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018cf8  mov     r9d, 4ABh
0x180018cfe  jmp     loc_180018C4B
0x180018d03  xor     edx, edx; sesid
0x180018d05  mov     [rsp+88h+pdwType], r15; szParam
0x180018d0a  mov     r9, rsi; lParam
0x180018d0d  mov     rcx, rbx; pinstance
0x180018d10  lea     r8d, [rdx+30h]; paramid
0x180018d14  call    cs:__imp_JetSetSystemParameterA
0x180018d1a  test    eax, eax
0x180018d1c  jns     short loc_180018D30
0x180018d1e  mov     ecx, eax; int
0x180018d20  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018d25  mov     r9d, 4ACh
0x180018d2b  jmp     loc_180018C4B
0x180018d30  xor     edx, edx; sesid
0x180018d32  mov     [rsp+88h+pdwType], r15; szParam
0x180018d37  mov     r9d, 500000h; lParam
0x180018d3d  mov     rcx, rbx; pinstance
0x180018d40  lea     r8d, [rdx+18h]; paramid
0x180018d44  call    cs:__imp_JetSetSystemParameterA
0x180018d4a  test    eax, eax
0x180018d4c  jns     short loc_180018D60
0x180018d4e  mov     ecx, eax; int
0x180018d50  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018d55  mov     r9d, 4AFh
0x180018d5b  jmp     loc_180018C4B
0x180018d60  xor     edx, edx; sesid
0x180018d62  mov     [rsp+88h+pdwType], r15; szParam
0x180018d67  mov     r8d, 98h; paramid
0x180018d6d  mov     rcx, rbx; pinstance
0x180018d70  lea     r9d, [rdx+2]; lParam
0x180018d74  call    cs:__imp_JetSetSystemParameterA
0x180018d7a  test    eax, eax
0x180018d7c  jns     short loc_180018D90
0x180018d7e  mov     ecx, eax; int
0x180018d80  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018d85  mov     r9d, 4B2h
0x180018d8b  jmp     loc_180018C4B
0x180018d90  xor     edx, edx; sesid
0x180018d92  mov     [rsp+88h+pdwType], r15; szParam
0x180018d97  mov     r9, rsi; lParam
0x180018d9a  mov     rcx, rbx; pinstance
0x180018d9d  lea     r8d, [rdx+2Dh]; paramid
0x180018da1  call    cs:__imp_JetSetSystemParameterA
0x180018da7  test    eax, eax
0x180018da9  jns     short loc_180018DBD
0x180018dab  mov     ecx, eax; int
0x180018dad  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018db2  mov     r9d, 4B5h
0x180018db8  jmp     loc_180018C4B
0x180018dbd  mov     r9, rsi; lParam
0x180018dc0  mov     [rsp+88h+pdwType], r15; szParam
0x180018dc5  mov     r8d, 45h ; 'E'; paramid
0x180018dcb  mov     rdx, r12; sesid
0x180018dce  mov     rcx, rbx; pinstance
0x180018dd1  call    cs:__imp_JetSetSystemParameterA
0x180018dd7  test    eax, eax
0x180018dd9  jns     short loc_180018DED
0x180018ddb  mov     ecx, eax; int
0x180018ddd  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018de2  mov     r9d, 4B8h
0x180018de8  jmp     loc_180018C4B
0x180018ded  xor     edx, edx; sesid
0x180018def  mov     [rsp+88h+pdwType], r15; szParam
0x180018df4  mov     r9d, 0C00h; lParam
0x180018dfa  mov     rcx, rbx; pinstance
0x180018dfd  lea     r8d, [rdx+0Bh]; paramid
0x180018e01  call    cs:__imp_JetSetSystemParameterA
0x180018e07  test    eax, eax
0x180018e09  jns     short loc_180018E1D
0x180018e0b  mov     ecx, eax; int
0x180018e0d  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018e12  mov     r9d, 4BAh
0x180018e18  jmp     loc_180018C4B
0x180018e1d  xor     edx, edx; sesid
0x180018e1f  mov     [rsp+88h+pdwType], r15; szParam
0x180018e24  mov     r9d, 500h; lParam
0x180018e2a  mov     rcx, rbx; pinstance
0x180018e2d  lea     r8d, [rdx+0Ch]; paramid
0x180018e31  call    cs:__imp_JetSetSystemParameterA
0x180018e37  test    eax, eax
0x180018e39  jns     short loc_180018E4D
0x180018e3b  mov     ecx, eax; int
0x180018e3d  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018e42  mov     r9d, 4C2h
0x180018e48  jmp     loc_180018C4B
0x180018e4d  xor     edx, edx; sesid
0x180018e4f  mov     [rsp+88h+pdwType], r15; szParam
0x180018e54  mov     r9d, 80h; lParam
0x180018e5a  mov     rcx, rbx; pinstance
0x180018e5d  lea     r8d, [rdx+12h]; paramid
0x180018e61  call    cs:__imp_JetSetSystemParameterA
0x180018e67  test    eax, eax
0x180018e69  jns     short loc_180018E7D
0x180018e6b  mov     ecx, eax; int
0x180018e6d  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018e72  mov     r9d, 4C4h
0x180018e78  jmp     loc_180018C4B
0x180018e7d  xor     edx, edx; sesid
0x180018e7f  mov     [rsp+88h+pdwType], r15; szParam
0x180018e84  mov     r9, rsi; lParam
0x180018e87  mov     rcx, rbx; pinstance
0x180018e8a  lea     r8d, [rdx+10h]; paramid
0x180018e8e  call    cs:__imp_JetSetSystemParameterA
0x180018e94  test    eax, eax
0x180018e96  jns     short loc_180018EAA
0x180018e98  mov     ecx, eax; int
0x180018e9a  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018e9f  mov     r9d, 4C7h
0x180018ea5  jmp     loc_180018C4B
0x180018eaa  xor     r9d, r9d; lParam
0x180018ead  mov     [rsp+88h+pdwType], r14; szParam
0x180018eb2  xor     r8d, r8d; paramid
0x180018eb5  mov     rdx, r12; sesid
0x180018eb8  mov     rcx, rbx; pinstance
0x180018ebb  call    cs:__imp_JetSetSystemParameterW
0x180018ec1  test    eax, eax
0x180018ec3  jns     short loc_180018ED7
0x180018ec5  mov     ecx, eax; int
0x180018ec7  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018ecc  mov     r9d, 4C9h
0x180018ed2  jmp     loc_180018C4B
0x180018ed7  xor     r9d, r9d; lParam
0x180018eda  mov     [rsp+88h+pdwType], r14; szParam
0x180018edf  mov     r8d, esi; paramid
0x180018ee2  mov     rdx, r12; sesid
0x180018ee5  mov     rcx, rbx; pinstance
0x180018ee8  call    cs:__imp_JetSetSystemParameterW
0x180018eee  test    eax, eax
0x180018ef0  jns     short loc_180018F04
0x180018ef2  mov     ecx, eax; int
0x180018ef4  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018ef9  mov     r9d, 4CAh
0x180018eff  jmp     loc_180018C4B
0x180018f04  xor     r9d, r9d; lParam
0x180018f07  mov     [rsp+88h+pdwType], r14; szParam
0x180018f0c  mov     rdx, r12; sesid
0x180018f0f  mov     rcx, rbx; pinstance
0x180018f12  lea     r8d, [r9+2]; paramid
0x180018f16  call    cs:__imp_JetSetSystemParameterW
0x180018f1c  test    eax, eax
0x180018f1e  jns     short loc_180018F32
0x180018f20  mov     ecx, eax; int
0x180018f22  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018f27  mov     r9d, 4CBh
0x180018f2d  jmp     loc_180018C4B
0x180018f32  xor     r9d, r9d; lParam
0x180018f35  mov     [rsp+88h+pdwType], r14; szParam
0x180018f3a  mov     rdx, r12; sesid
0x180018f3d  mov     rcx, rbx; pinstance
0x180018f40  lea     ebp, [r9+71h]
0x180018f44  mov     r8d, ebp; paramid
0x180018f47  call    cs:__imp_JetSetSystemParameterW
0x180018f4d  test    eax, eax
0x180018f4f  jns     short loc_180018F63
  ... truncated ...
```
