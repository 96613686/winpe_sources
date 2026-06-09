# CCRLConfig::SavePasswordPolicyToRegistry(IExecutionContextLite *)

- ea: `0x180023f60`
- end: `0x18002416f`
- name: `?SavePasswordPolicyToRegistry@CCRLConfig@@UEAAJPEAVIExecutionContextLite@@@Z`
- size: `527`
- prototype: `__int64 __fastcall(CCRLConfig *__hidden this, struct IExecutionContextLite *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006ac0`
- `0x18000c050`
- `0x18001a530`
- `0x18001a9c0`
- `0x180023d24`
- `0x180023f60`
- `0x1800841b0`
- `0x1800a4784`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002406f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024096`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002406f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024054`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002404a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002404a`

## string_xrefs

- `0x180023fbc`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\configuration.cpp`
- `0x180024028`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\configuration.cpp`
- `0x180024135`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\configuration.cpp`
- `0x180023fa7`: `CCRLConfig::SavePasswordPolicyToRegistry`
- `0x1800240de`: `hr = registryHelper.WriteBufferToRegistry( HKEY_USERS, WLID_REG_SYSTEM_USER_IDCRL_PATH, WLID_REG_PROVIDER_DEFAULT_PASSWORD_LENGTH, REG_DWORD, reinterpret_cast<BYTE*>(&m_ConfigData.m_dwMinPasswordLength), sizeof(m_ConfigData.m_dwMinPasswordLength))`
- `0x18002411d`: `hr = registryHelper.WriteBufferToRegistry( HKEY_USERS, WLID_REG_SYSTEM_USER_IDCRL_PATH, WLID_REG_PROVIDER_DEFAULT_PASSWORD_CHARACTER_GROUPS, REG_DWORD, reinterpret_cast<BYTE*>(&m_ConfigData.m_dwMinPasswordCharacterGroups), sizeof(m_ConfigData.m_dwMinPasswordCharacterGroups))`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCRLConfig::SavePasswordPolicyToRegistry(CCRLConfig *this, struct IExecutionContextLite *a2)
{
  unsigned __int8 *v2; // rdi
  unsigned __int8 *v3; // rbx
  signed int LastError; // eax
  signed int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  const char *v8; // rcx
  unsigned int v9; // r8d
  unsigned int v10; // ebx
  unsigned int v12; // [rsp+30h] [rbp-40h]
  int v13; // [rsp+38h] [rbp-38h]
  void *v14; // [rsp+40h] [rbp-30h] BYREF
  HANDLE Token; // [rsp+48h] [rbp-28h]
  const char *v16[4]; // [rsp+50h] [rbp-20h] BYREF
  signed int v17; // [rsp+90h] [rbp+20h] BYREF
  struct IExecutionContextLite *pExceptionObject; // [rsp+98h] [rbp+28h] BYREF

  v17 = 0;
  pExceptionObject = a2;
  v2 = (unsigned __int8 *)this + 360;
  v3 = (unsigned __int8 *)this + 356;
  v13 = *((_DWORD *)this + 90);
  v12 = *((_DWORD *)this + 89);
  CTraceFuncW<long>::CTraceFuncW<long>(
    v16,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\configuration.cpp",
    1051,
    (const char *)&v17,
    "CCRLConfig::SavePasswordPolicyToRegistry",
    L"minPasswordLength=%d,minPasswordCharacterGroups=%d",
    v12,
    v13);
  LODWORD(v14) = 0;
  Token = 0;
  if ( (unsigned int)CAutoRevertToSelf::Revert(&v14, 0) )
    goto LABEL_15;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v17 = LastError;
  if ( LastError >= 0 )
  {
LABEL_15:
    v7 = RegistryHelper::WriteBufferToRegistry(
           (RegistryHelper *)&pExceptionObject,
           HKEY_USERS,
           L".DEFAULT\\Software\\Microsoft\\IdentityCRL",
           L"ProviderPasswordLength",
           4u,
           v3,
           4u);
    v17 = v7;
    if ( v7 >= 0 )
    {
      v7 = RegistryHelper::WriteBufferToRegistry(
             (RegistryHelper *)&pExceptionObject,
             HKEY_USERS,
             L".DEFAULT\\Software\\Microsoft\\IdentityCRL",
             L"ProviderPasswordCharacterGroups",
             4u,
             v2,
             4u);
      v17 = v7;
      if ( v7 >= 0 )
      {
LABEL_20:
        CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&v14);
        goto LABEL_21;
      }
      v8 = "hr = registryHelper.WriteBufferToRegistry( HKEY_USERS, WLID_REG_SYSTEM_USER_IDCRL_PATH, WLID_REG_PROVIDER_DEF"
           "AULT_PASSWORD_CHARACTER_GROUPS, REG_DWORD, reinterpret_cast<BYTE*>(&m_ConfigData.m_dwMinPasswordCharacterGrou"
           "ps), sizeof(m_ConfigData.m_dwMinPasswordCharacterGroups))";
      v9 = 1072;
    }
    else
    {
      v8 = "hr = registryHelper.WriteBufferToRegistry( HKEY_USERS, WLID_REG_SYSTEM_USER_IDCRL_PATH, WLID_REG_PROVIDER_DEF"
           "AULT_PASSWORD_LENGTH, REG_DWORD, reinterpret_cast<BYTE*>(&m_ConfigData.m_dwMinPasswordLength), sizeof(m_Confi"
           "gData.m_dwMinPasswordLength))";
      v9 = 1064;
    }
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\configuration.cpp",
      "CCRLConfig::SavePasswordPolicyToRegistry",
      v9,
      v7,
      v8);
    goto LABEL_20;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\configuration.cpp",
    "CCRLConfig::SavePasswordPolicyToRegistry",
    0x420u,
    LastError,
    "hr = HRESULT_FROM_WIN32(GetLastError())");
  if ( (_DWORD)v14 )
  {
    if ( !Token )
      goto LABEL_21;
    if ( !SetThreadToken(0, Token) )
    {
      v5 = GetLastError();
      v6 = v5;
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      if ( Token )
        CloseHandle(Token);
      LODWORD(pExceptionObject) = v6;
      throw (long *)&pExceptionObject;
    }
  }
  if ( Token )
    CloseHandle(Token);
LABEL_21:
  v10 = v17;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v16);
  return v10;
}

```

## disassembly

```asm
0x180023f60  mov     r11, rsp
0x180023f63  mov     [r11+18h], rbx
0x180023f67  mov     [r11+20h], rdi
0x180023f6b  push    rbp
0x180023f6c  push    r14
0x180023f6e  push    r15
0x180023f70  mov     rbp, rsp
0x180023f73  sub     rsp, 70h
0x180023f77  mov     [rbp+arg_0], 0
0x180023f7e  mov     [rbp+pExceptionObject], rdx
0x180023f82  lea     rdi, [rcx+168h]
0x180023f89  lea     rbx, [rcx+164h]
0x180023f90  mov     eax, [rdi]
0x180023f92  mov     [rsp+70h+var_38], eax
0x180023f96  mov     eax, [rbx]
0x180023f98  mov     [rsp+70h+var_40], eax
0x180023f9c  lea     rax, aMinpasswordlen; "minPasswordLength=%d,minPasswordCharact"...
0x180023fa3  mov     [r11-60h], rax
0x180023fa7  lea     r15, aCcrlconfigSave; "CCRLConfig::SavePasswordPolicyToRegistr"...
0x180023fae  mov     [r11-68h], r15
0x180023fb2  lea     r9, [rbp+arg_0]
0x180023fb6  mov     r8d, 41Bh
0x180023fbc  lea     rdx, aOnecoreuapDsEx_16; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180023fc3  lea     rcx, [rbp+var_20]
0x180023fc7  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x180023fcc  nop
0x180023fcd  mov     dword ptr [rbp+var_30], 0
0x180023fd4  mov     [rbp+Token], 0
0x180023fdc  xor     edx, edx; int
0x180023fde  lea     rcx, [rbp+var_30]; this
0x180023fe2  call    ?Revert@CAutoRevertToSelf@@QEAAHH@Z; CAutoRevertToSelf::Revert(int)
0x180023fe7  test    eax, eax
0x180023fe9  jnz     loc_1800240A1
0x180023fef  call    cs:__imp_GetLastError
0x180023ff5  mov     r14d, 80070000h
0x180023ffb  test    eax, eax
0x180023ffd  jle     short loc_180024005
0x180023fff  movzx   eax, ax
0x180024002  or      eax, r14d
0x180024005  mov     [rbp+arg_0], eax
0x180024008  test    eax, eax
0x18002400a  jns     loc_1800240A1
0x180024010  lea     r8, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180024017  mov     [rsp+70h+var_50], r8; char *
0x18002401c  mov     r9d, eax; int
0x18002401f  mov     r8d, 420h; unsigned int
0x180024025  mov     rdx, r15; char *
0x180024028  lea     rcx, aOnecoreuapDsEx_16; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002402f  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180024034  nop
0x180024035  cmp     dword ptr [rbp+var_30], 0
0x180024039  jz      short loc_180024089
0x18002403b  mov     rdx, [rbp+Token]; Token
0x18002403f  test    rdx, rdx
0x180024042  jz      loc_18002414B
0x180024048  xor     ecx, ecx; Thread
0x18002404a  call    cs:__imp_SetThreadToken
0x180024050  test    eax, eax
0x180024052  jnz     short loc_180024089
0x180024054  call    cs:__imp_GetLastError
0x18002405a  mov     ebx, eax
0x18002405c  test    eax, eax
0x18002405e  jle     short loc_180024066
0x180024060  movzx   ebx, ax
0x180024063  or      ebx, r14d
0x180024066  mov     rcx, [rbp+Token]; hObject
0x18002406a  test    rcx, rcx
0x18002406d  jz      short loc_180024075
0x18002406f  call    cs:__imp_CloseHandle
0x180024075  mov     dword ptr [rbp+pExceptionObject], ebx
0x180024078  lea     rdx, _TI1J; pThrowInfo
0x18002407f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024083  call    _CxxThrowException_0
0x180024089  mov     rcx, [rbp+Token]; hObject
0x18002408d  test    rcx, rcx
0x180024090  jz      loc_18002414B
0x180024096  call    cs:__imp_CloseHandle
0x18002409c  jmp     loc_18002414B
0x1800240a1  mov     r14d, 4
0x1800240a7  mov     [rsp+70h+var_40], r14d; unsigned int
0x1800240ac  mov     [rsp+70h+var_48], rbx; unsigned __int8 *
0x1800240b1  mov     dword ptr [rsp+70h+var_50], r14d; unsigned int
0x1800240b6  lea     r9, aProviderpasswo_0; "ProviderPasswordLength"
0x1800240bd  lea     r8, aDefaultSoftwar_4; ".DEFAULT\\Software\\Microsoft\\Identity"...
0x1800240c4  mov     rbx, 0FFFFFFFF80000003h
0x1800240cb  mov     rdx, rbx; HKEY
0x1800240ce  lea     rcx, [rbp+pExceptionObject]; this
0x1800240d2  call    ?WriteBufferToRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAEK@Z; RegistryHelper::WriteBufferToRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar *,ulong)
0x1800240d7  mov     [rbp+arg_0], eax
0x1800240da  test    eax, eax
0x1800240dc  jns     short loc_1800240ED
0x1800240de  lea     rcx, aHrRegistryhelp_2; "hr = registryHelper.WriteBufferToRegist"...
0x1800240e5  mov     r8d, 428h
0x1800240eb  jmp     short loc_18002412A
0x1800240ed  mov     [rsp+70h+var_40], r14d; unsigned int
0x1800240f2  mov     [rsp+70h+var_48], rdi; unsigned __int8 *
0x1800240f7  mov     dword ptr [rsp+70h+var_50], r14d; unsigned int
0x1800240fc  lea     r9, aProviderpasswo; "ProviderPasswordCharacterGroups"
0x180024103  lea     r8, aDefaultSoftwar_4; ".DEFAULT\\Software\\Microsoft\\Identity"...
0x18002410a  mov     rdx, rbx; HKEY
0x18002410d  lea     rcx, [rbp+pExceptionObject]; this
0x180024111  call    ?WriteBufferToRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAEK@Z; RegistryHelper::WriteBufferToRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar *,ulong)
0x180024116  mov     [rbp+arg_0], eax
0x180024119  test    eax, eax
0x18002411b  jns     short loc_180024142
0x18002411d  lea     rcx, aHrRegistryhelp_0; "hr = registryHelper.WriteBufferToRegist"...
0x180024124  mov     r8d, 430h; unsigned int
0x18002412a  mov     [rsp+70h+var_50], rcx; char *
0x18002412f  mov     r9d, eax; int
0x180024132  mov     rdx, r15; char *
0x180024135  lea     rcx, aOnecoreuapDsEx_16; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002413c  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180024141  nop
0x180024142  lea     rcx, [rbp+var_30]; this
0x180024146  call    ??1CAutoRevertToSelf@@QEAA@XZ; CAutoRevertToSelf::~CAutoRevertToSelf(void)
0x18002414b  mov     ebx, [rbp+arg_0]
0x18002414e  lea     rcx, [rbp+var_20]
0x180024152  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180024157  mov     eax, ebx
0x180024159  lea     r11, [rsp+70h+var_s0]
0x18002415e  mov     rbx, [r11+30h]
0x180024162  mov     rdi, [r11+38h]
0x180024166  mov     rsp, r11
0x180024169  pop     r15
0x18002416b  pop     r14
0x18002416d  pop     rbp
0x18002416e  retn
```
