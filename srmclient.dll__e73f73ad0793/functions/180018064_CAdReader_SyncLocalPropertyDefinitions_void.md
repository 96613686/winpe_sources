# CAdReader::SyncLocalPropertyDefinitions(void)

- ea: `0x180018064`
- end: `0x1800189f6`
- name: `?SyncLocalPropertyDefinitions@CAdReader@@QEAAXXZ`
- size: `2450`
- prototype: `void __fastcall(CAdReader *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000d114`

## callees

- `0x180001350`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000f818`
- `0x180010e60`
- `0x180014c40`
- `0x180016408`
- `0x180017210`
- `0x180018064`
- `0x180018b04`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x1800718cc`
- `0x180072598`
- `0x180073a80`
- `0x180073f54`
- `0x180075034`
- `0x180075510`
- `0x1800757d0`
- `0x18007691c`
- `0x180076efc`
- `0x180077088`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18001875e`
- `msvcrt!_itow_s` at `0x180018775`
- `msvcrt!_itow_s` at `0x18001878c`
- `msvcrt!_itow_s` at `0x18001875e`
- `msvcrt!_itow_s` at `0x180018775`
- `msvcrt!_itow_s` at `0x18001878c`
- `KERNEL32!SystemTimeToFileTime` at `0x180018246`
- `KERNEL32!SystemTimeToFileTime` at `0x180018246`
- `KERNEL32!GetSystemTime` at `0x180018233`
- `KERNEL32!GetSystemTime` at `0x180018422`
- `KERNEL32!GetSystemTime` at `0x180018443`
- `KERNEL32!GetSystemTime` at `0x180018233`
- `KERNEL32!GetSystemTime` at `0x180018422`
- `KERNEL32!GetSystemTime` at `0x180018443`

## string_xrefs

- `0x1800180b5`: `ADREADRC`
- `0x180018099`: `base\fs\fsrm\service\globalstore\adreader.cpp`
- `0x1800180a7`: `CAdReader::SyncLocalPropertyDefinitions`
- `0x18001815c`: `CAdReader::SetLastAttemptedSyncTime`
- `0x1800188ff`: `CAdReader::SetLastAttemptedSyncTime`
- `0x1800182ca`: `AdLeaveTaskEnabled`
- `0x18001838c`: `AdLeaveTaskEnabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CAdReader::SyncLocalPropertyDefinitions(CAdReader *this)
{
  const unsigned __int16 *v2; // rdx
  int v3; // eax
  volatile signed __int32 *v4; // rbx
  signed __int32 v5; // eax
  int v6; // eax
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  void *v10; // r15
  _QWORD *i; // rsi
  void *v12; // r15
  _QWORD *j; // rsi
  int v14; // eax
  unsigned int v15; // r9d
  const wchar_t *v16; // rax
  int v17; // ecx
  unsigned int v18; // r9d
  _QWORD *v19; // rax
  const wchar_t *v20; // rsi
  void *v21; // r15
  _QWORD *k; // rsi
  __int64 v23; // rax
  int Hr; // eax
  char v25; // r8
  int v26; // eax
  char v27; // al
  int v28; // eax
  char v29; // al
  volatile signed __int32 *v30; // [rsp+40h] [rbp-2F8h] BYREF
  int v31; // [rsp+48h] [rbp-2F0h] BYREF
  CAdReader *v32; // [rsp+50h] [rbp-2E8h]
  struct _FILETIME FileTime; // [rsp+58h] [rbp-2E0h] BYREF
  void *Block[2]; // [rsp+60h] [rbp-2D8h] BYREF
  __int64 v35; // [rsp+70h] [rbp-2C8h]
  _QWORD v36[3]; // [rsp+80h] [rbp-2B8h] BYREF
  const unsigned __int16 *v37; // [rsp+98h] [rbp-2A0h] BYREF
  const wchar_t *v38; // [rsp+A0h] [rbp-298h]
  __int128 v39; // [rsp+A8h] [rbp-290h]
  __int128 v40; // [rsp+B8h] [rbp-280h] BYREF
  __int128 v41; // [rsp+C8h] [rbp-270h]
  __int128 v42; // [rsp+D8h] [rbp-260h]
  int v43; // [rsp+120h] [rbp-218h]
  _BYTE v44[24]; // [rsp+140h] [rbp-1F8h] BYREF
  unsigned __int64 v45; // [rsp+158h] [rbp-1E0h]
  struct _SYSTEMTIME v46; // [rsp+160h] [rbp-1D8h] BYREF
  void **v47; // [rsp+170h] [rbp-1C8h] BYREF
  int v48; // [rsp+178h] [rbp-1C0h]
  _QWORD v49[22]; // [rsp+220h] [rbp-118h] BYREF
  _BYTE SystemTime[18]; // [rsp+2D0h] [rbp-68h] BYREF
  __int16 v51; // [rsp+2E2h] [rbp-56h]
  wchar_t Buffer; // [rsp+2E8h] [rbp-50h] BYREF
  __int128 v53; // [rsp+2EAh] [rbp-4Eh]
  __int16 v54; // [rsp+2FAh] [rbp-3Eh]

  v32 = this;
  v37 = L"base\\fs\\fsrm\\service\\globalstore\\adreader.cpp";
  v38 = L"CAdReader::SyncLocalPropertyDefinitions";
  *(_QWORD *)&v39 = L"ADREADRC";
  *((_QWORD *)&v39 + 1) = 0x1E0000017ELL;
  LODWORD(v40) = 255;
  v43 = 0x1000000;
  memset_0((char *)&v40 + 8, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer(&v47, &v37, 0);
  v30 = 0;
  *(_OWORD *)Block = 0;
  v35 = 0;
  v36[2] = 0;
  v36[1] = 0;
  v36[0] = 131334;
  v31 = 0;
  v37 = L"base\\fs\\fsrm\\service\\globalstore\\adreader.cpp";
  v38 = L"CAdReader::SetLastAttemptedSyncTime";
  *(_QWORD *)&v39 = L"ADREADRC";
  *((_QWORD *)&v39 + 1) = 0x1E00000581LL;
  LODWORD(v40) = 255;
  v43 = 0x1000000;
  memset_0((char *)&v40 + 8, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer(v49, &v37, 0);
  *(_QWORD *)&v44[16] = 0;
  *(_QWORD *)&v44[8] = 0;
  *(_QWORD *)v44 = 131334;
  *(_OWORD *)SystemTime = 0;
  FileTime = 0;
  if ( !CSrmRegistryKey::Open(
          (CSrmRegistryKey *)v44,
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\FileClassificationInfrastructure") )
    CSrmRegistryKey::Create(
      (CSrmRegistryKey *)v44,
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\FileClassificationInfrastructure");
  GetSystemTime((LPSYSTEMTIME)SystemTime);
  if ( !SystemTimeToFileTime((const SYSTEMTIME *)SystemTime, &FileTime) )
  {
    v23 = CSrmDebugInfo::CSrmDebugInfo(
            &v37,
            L"base\\fs\\fsrm\\service\\globalstore\\adreader.cpp",
            L"ADREADRC",
            L"CAdReader::SetLastAttemptedSyncTime",
            1424,
            30);
    CSrmFunctionTracer::TranslateWin32Error(v49, v23, L"SystemTimeToFileTime");
  }
  CSrmRegistryKey::SetValue((CSrmRegistryKey *)v44, v2, *(_QWORD *)&FileTime);
  CSrmRegistryKey::~CSrmRegistryKey((CSrmRegistryKey *)v44);
  v49[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v49);
  if ( !CSrmRegistryKey::Open(
          (CSrmRegistryKey *)v36,
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\FileClassificationInfrastructure") )
    CSrmRegistryKey::Create(
      (CSrmRegistryKey *)v36,
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\FileClassificationInfrastructure");
  CSrmRegistryKey::SetValue((CSrmRegistryKey *)v36, L"AdLeaveTaskEnabled", 0);
  v3 = ATL::CComObject<CFsrmCollection>::CreateInstance(&v30);
  v48 = v3;
  if ( v3 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v47);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v47, Hr);
    v25 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v47);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v47, 0x197u, v25, 0);
  }
  v48 = v3;
  v4 = v30;
  do
    v5 = *((_DWORD *)v4 + 36);
  while ( v5 != 0x7FFFFFFF && v5 != _InterlockedCompareExchange(v4 + 36, v5 + 1, v5) );
  if ( CAdReader::IsDomainJoined() )
    CAdReader::EnumAdPropertyDefinitionsInternalByObject(this, v4);
  else
    CSrmFunctionTracer::Trace(
      (CSrmFunctionTracer *)&v47,
      0x78u,
      0x19Du,
      L"Machine is not domain joined - not syncing definitions from AD");
  v6 = (*(__int64 (__fastcall **)(volatile signed __int32 *, int *))(*(_QWORD *)v4 + 72LL))(v4, &v31);
  v48 = v6;
  if ( v6 < 0 )
  {
    v26 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v47);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v47, v26);
    v27 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v47);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v47, 0x1A4u, v27, 0);
  }
  v48 = v6;
  if ( v31 > 0 )
    CSrmRegistryKey::SetValue((CSrmRegistryKey *)v36, L"AdLeaveTaskEnabled", 1u);
  if ( *(_BYTE *)this )
  {
    CSrmRegistryKey::~CSrmRegistryKey((CSrmRegistryKey *)v36);
    *(_OWORD *)Block = 0;
    v35 = 0;
    if ( v4 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 16LL))(v4);
    goto LABEL_66;
  }
  *(_QWORD *)v44 = &CSrmSharedLockWrite::`vftable';
  *(_QWORD *)&v44[8] = &g_LockConfigGlobal;
  v46 = 0;
  GetSystemTime((LPSYSTEMTIME)&v44[16]);
  (*(void (__fastcall **)(void *))(g_LockConfigGlobal + 32LL))(&g_LockConfigGlobal);
  GetSystemTime(&v46);
  CFciConfigObject::EnumObjects<CFciPropertyDefinition>(v8, v7, v9, 0, (__int64)Block, 0);
  if ( *(_BYTE *)this )
  {
    *(_QWORD *)v44 = &CSrmSharedLockWrite::`vftable';
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v44[8] + 48LL))(*(_QWORD *)&v44[8]);
    CSrmRegistryKey::~CSrmRegistryKey((CSrmRegistryKey *)v36);
    v10 = Block[0];
    if ( Block[0] )
    {
      for ( i = Block[0]; i != Block[1]; ++i )
      {
        if ( *i )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*i + 16LL))(*i);
      }
      operator delete(v10);
    }
    *(_OWORD *)Block = 0;
    v35 = 0;
    if ( v4 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 16LL))(v4);
    goto LABEL_66;
  }
  CAdReader::UpdateLocalPropertyDefinitions(this, v4, Block);
  if ( *(_BYTE *)this )
  {
    *(_QWORD *)v44 = &CSrmSharedLockWrite::`vftable';
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v44[8] + 48LL))(*(_QWORD *)&v44[8]);
    CSrmRegistryKey::~CSrmRegistryKey((CSrmRegistryKey *)v36);
    v12 = Block[0];
    if ( Block[0] )
    {
      for ( j = Block[0]; j != Block[1]; ++j )
      {
        if ( *j )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*j + 16LL))(*j);
      }
      operator delete(v12);
    }
    *(_OWORD *)Block = 0;
    v35 = 0;
    if ( v4 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 16LL))(v4);
    goto LABEL_66;
  }
  CAdReader::RemoveOrphanedPropertyDefinitions(this, v4, Block);
  *(_QWORD *)v44 = &CSrmSharedLockWrite::`vftable';
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v44[8] + 48LL))(*(_QWORD *)&v44[8]);
  v14 = v48;
  if ( v48 < 0 )
    goto LABEL_44;
  if ( *((_BYTE *)this + 1) )
    v14 = -2147200119;
  v48 = v14;
  if ( v14 >= 0 )
  {
    v17 = *((_DWORD *)this + 1);
    if ( !v17 && !*((_DWORD *)this + 2) && !*((_DWORD *)this + 3) )
      goto LABEL_57;
    memset(SystemTime, 0, sizeof(SystemTime));
    v51 = 0;
    Buffer = 0;
    v53 = 0;
    v54 = 0;
    memset(v44, 0, 20);
    _itow_s(v17, (wchar_t *)SystemTime, 0xAu, 10);
    _itow_s(*((_DWORD *)this + 2), &Buffer, 0xAu, 10);
    _itow_s(*((_DWORD *)this + 3), (wchar_t *)v44, 0xAu, 10);
    v19 = (_QWORD *)((char *)this + 56);
    if ( *((_QWORD *)this + 10) >= 8u )
      v19 = (_QWORD *)*v19;
    v20 = (const wchar_t *)((char *)this + 16);
    if ( *((_QWORD *)v20 + 3) >= 8u )
      v20 = *(const wchar_t **)v20;
    LODWORD(v37) = -2147209161;
    v38 = v20;
    *(_QWORD *)&v39 = v19;
    *((_QWORD *)&v39 + 1) = SystemTime;
    *(_QWORD *)&v40 = &Buffer;
    *((_QWORD *)&v40 + 1) = v44;
    v41 = 0;
    v42 = 0;
    CSrmFunctionTracer::LogEvent(
      (CSrmFunctionTracer *)&v47,
      0x1E3u,
      4u,
      v18,
      (const struct EventLogMessageContent *)&v37);
  }
  else
  {
LABEL_44:
    CSrmFunctionTracerBase::GetErrorText(&v47, v44);
    v16 = (const wchar_t *)v44;
    if ( v45 >= 8 )
      v16 = *(const wchar_t **)v44;
    LODWORD(v37) = -2147209160;
    v38 = v16;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    CSrmFunctionTracer::LogEvent(
      (CSrmFunctionTracer *)&v47,
      0x1CCu,
      1u,
      v15,
      (const struct EventLogMessageContent *)&v37);
    if ( v45 >= 8 )
      operator delete(*(void **)v44);
  }
  v14 = v48;
LABEL_57:
  v48 = v14;
  if ( v14 < 0 )
  {
    v28 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v47);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v47, v28);
    v29 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v47);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v47, 0x1E7u, v29, 0);
  }
  v48 = v14;
  CSrmRegistryKey::~CSrmRegistryKey((CSrmRegistryKey *)v36);
  v21 = Block[0];
  if ( Block[0] )
  {
    for ( k = Block[0]; k != Block[1]; ++k )
    {
      if ( *k )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*k + 16LL))(*k);
    }
    operator delete(v21);
  }
  if ( v4 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 16LL))(v4);
LABEL_66:
  v47 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v47);
}

```

## disassembly

```asm
0x180018064  mov     r11, rsp
0x180018067  mov     [r11+10h], rbx
0x18001806b  mov     [r11+18h], rsi
0x18001806f  push    rdi
0x180018070  push    r12
0x180018072  push    r13
0x180018074  push    r14
0x180018076  push    r15
0x180018078  sub     rsp, 310h
0x18001807f  mov     rax, cs:__security_cookie
0x180018086  xor     rax, rsp
0x180018089  mov     [rsp+338h+var_38], rax
0x180018091  mov     rsi, rcx
0x180018094  mov     [rsp+338h+var_2E8], rcx
0x180018099  lea     r12, aBaseFsFsrmServ_14; "base\\fs\\fsrm\\service\\globalstore\\a"...
0x1800180a0  mov     [r11-2A0h], r12
0x1800180a7  lea     rax, aCadreaderSyncl; "CAdReader::SyncLocalPropertyDefinitions"
0x1800180ae  mov     [r11-298h], rax
0x1800180b5  lea     r13, aAdreadrc; "ADREADRC"
0x1800180bc  mov     [r11-290h], r13
0x1800180c3  mov     dword ptr [rsp+338h+var_290+8], 17Eh
0x1800180ce  mov     dword ptr [rsp+338h+var_290+0Ch], 1Eh
0x1800180d9  mov     r15d, 0FFh
0x1800180df  mov     [r11-280h], r15d
0x1800180e6  xor     edi, edi
0x1800180e8  mov     [rsp+338h+var_218], 1000000h
0x1800180f3  lea     r14d, [rdi+60h]
0x1800180f7  mov     r8d, r14d; Size
0x1800180fa  xor     edx, edx; Val
0x1800180fc  lea     rcx, [r11-278h]; void *
0x180018103  call    memset_0
0x180018108  xor     r8d, r8d
0x18001810b  lea     rdx, [rsp+338h+var_2A0]
0x180018113  lea     rcx, [rsp+338h+var_1C8]
0x18001811b  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180018120  nop
0x180018121  mov     [rsp+338h+var_2F8], rdi
0x180018126  xorps   xmm0, xmm0
0x180018129  movdqu  xmmword ptr [rsp+338h+Block], xmm0
0x18001812f  mov     [rsp+338h+var_2C8], rdi
0x180018134  mov     [rsp+338h+var_2A8], rdi
0x18001813c  mov     [rsp+338h+var_2B0], rdi
0x180018144  mov     [rsp+338h+var_2B8], 20106h
0x180018150  mov     [rsp+338h+var_2F0], edi
0x180018154  mov     [rsp+338h+var_2A0], r12
0x18001815c  lea     rax, aCadreaderSetla; "CAdReader::SetLastAttemptedSyncTime"
0x180018163  mov     [rsp+338h+var_298], rax
0x18001816b  mov     qword ptr [rsp+338h+var_290], r13
0x180018173  mov     dword ptr [rsp+338h+var_290+8], 581h
0x18001817e  mov     dword ptr [rsp+338h+var_290+0Ch], 1Eh
0x180018189  mov     dword ptr [rsp+338h+var_280], r15d
0x180018191  mov     [rsp+338h+var_218], 1000000h
0x18001819c  mov     r8d, r14d; Size
0x18001819f  xor     edx, edx; Val
0x1800181a1  lea     rcx, [rsp+338h+var_280+8]; void *
0x1800181a9  call    memset_0
0x1800181ae  xor     r8d, r8d
0x1800181b1  lea     rdx, [rsp+338h+var_2A0]
0x1800181b9  lea     rcx, [rsp+338h+var_118]
0x1800181c1  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800181c6  nop
0x1800181c7  mov     qword ptr [rsp+338h+var_1E8.wYear], rdi
0x1800181cf  mov     qword ptr [rsp+338h+var_1F8+8], rdi
0x1800181d7  mov     qword ptr [rsp+338h+var_1F8], 20106h
0x1800181e3  xorps   xmm0, xmm0
0x1800181e6  movups  xmmword ptr [rsp+338h+SystemTime], xmm0
0x1800181ee  mov     qword ptr [rsp+338h+FileTime.dwLowDateTime], rdi
0x1800181f3  lea     rbx, aSoftwareMicros_0; "Software\\Microsoft\\FileClassification"...
0x1800181fa  mov     r8, rbx; unsigned __int16 *
0x1800181fd  mov     r15, 0FFFFFFFF80000002h
0x180018204  mov     rdx, r15; hKey
0x180018207  lea     rcx, [rsp+338h+var_1F8]; this
0x18001820f  call    ?Open@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::Open(HKEY__ *,ushort const *,...)
0x180018214  test    al, al
0x180018216  jnz     short loc_18001822B
0x180018218  mov     r8, rbx; unsigned __int16 *
0x18001821b  mov     rdx, r15; hKey
0x18001821e  lea     rcx, [rsp+338h+var_1F8]; this
0x180018226  call    ?Create@CSrmRegistryKey@@QEAAXPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::Create(HKEY__ *,ushort const *,...)
0x18001822b  lea     rcx, [rsp+338h+SystemTime]; lpSystemTime
0x180018233  call    cs:__imp_GetSystemTime
0x180018239  lea     rdx, [rsp+338h+FileTime]; lpFileTime
0x18001823e  lea     rcx, [rsp+338h+SystemTime]; lpSystemTime
0x180018246  call    cs:__imp_SystemTimeToFileTime
0x18001824c  test    eax, eax
0x18001824e  jz      loc_1800188EF
0x180018254  mov     r8d, [rsp+338h+FileTime.dwHighDateTime]
0x180018259  shl     r8, 20h
0x18001825d  mov     eax, [rsp+338h+FileTime.dwLowDateTime]
0x180018261  or      r8, rax; unsigned __int64
0x180018264  lea     rcx, [rsp+338h+var_1F8]; this
0x18001826c  call    ?SetValue@CSrmRegistryKey@@QEAAXPEBG_K@Z; CSrmRegistryKey::SetValue(ushort const *,unsigned __int64)
0x180018271  nop
0x180018272  lea     rcx, [rsp+338h+var_1F8]; this
0x18001827a  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x18001827f  nop
0x180018280  lea     r14, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180018287  mov     [rsp+338h+var_118], r14
0x18001828f  lea     rcx, [rsp+338h+var_118]; this
0x180018297  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001829c  nop
0x18001829d  mov     r8, rbx; unsigned __int16 *
0x1800182a0  mov     rdx, r15; hKey
0x1800182a3  lea     rcx, [rsp+338h+var_2B8]; this
0x1800182ab  call    ?Open@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::Open(HKEY__ *,ushort const *,...)
0x1800182b0  test    al, al
0x1800182b2  jnz     short loc_1800182C7
0x1800182b4  mov     r8, rbx; unsigned __int16 *
0x1800182b7  mov     rdx, r15; hKey
0x1800182ba  lea     rcx, [rsp+338h+var_2B8]; this
0x1800182c2  call    ?Create@CSrmRegistryKey@@QEAAXPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::Create(HKEY__ *,ushort const *,...)
0x1800182c7  xor     r8d, r8d; unsigned int
0x1800182ca  lea     rdx, aAdleavetaskena_0; "AdLeaveTaskEnabled"
0x1800182d1  lea     rcx, [rsp+338h+var_2B8]; this
0x1800182d9  call    ?SetValue@CSrmRegistryKey@@QEAAXPEBGK@Z; CSrmRegistryKey::SetValue(ushort const *,ulong)
0x1800182de  lea     rcx, [rsp+338h+var_2F8]
0x1800182e3  call    ?CreateInstance@?$CComObject@VCFsrmCollection@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFsrmCollection>::CreateInstance(ATL::CComObject<CFsrmCollection> * *)
0x1800182e8  mov     [rsp+338h+var_1C0], eax
0x1800182ef  test    eax, eax
0x1800182f1  js      loc_180018931
0x1800182f7  mov     [rsp+338h+var_1C0], eax
0x1800182fe  mov     rbx, [rsp+338h+var_2F8]
0x180018303  mov     edx, 7FFFFFFFh
0x180018308  jmp     short loc_180018317
0x18001830a  lea     ecx, [rax+1]
0x18001830d  lock cmpxchg [rbx+90h], ecx
0x180018315  jz      short loc_180018321
0x180018317  mov     eax, [rbx+90h]
0x18001831d  cmp     eax, edx
0x18001831f  jnz     short loc_18001830A
0x180018321  call    ?IsDomainJoined@CAdReader@@CA_NXZ; CAdReader::IsDomainJoined(void)
0x180018326  test    al, al
0x180018328  jnz     short loc_18001834B
0x18001832a  lea     r9, aMachineIsNotDo; "Machine is not domain joined - not sync"...
0x180018331  mov     edx, 78h ; 'x'; unsigned int
0x180018336  mov     r8d, 19Dh; unsigned int
0x18001833c  lea     rcx, [rsp+338h+var_1C8]; this
0x180018344  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x180018349  jmp     short loc_180018356
0x18001834b  mov     rdx, rbx
0x18001834e  mov     rcx, rsi
0x180018351  call    ?EnumAdPropertyDefinitionsInternalByObject@CAdReader@@AEAAXPEAV?$CComObject@VCFsrmCollection@@@ATL@@@Z; CAdReader::EnumAdPropertyDefinitionsInternalByObject(ATL::CComObject<CFsrmCollection> *)
0x180018356  mov     rax, [rbx]
0x180018359  lea     rdx, [rsp+338h+var_2F0]
0x18001835e  mov     rcx, rbx
0x180018361  mov     rax, [rax+48h]
0x180018365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001836a  mov     [rsp+338h+var_1C0], eax
0x180018371  test    eax, eax
0x180018373  js      loc_180018972
0x180018379  mov     [rsp+338h+var_1C0], eax
0x180018380  cmp     [rsp+338h+var_2F0], edi
0x180018384  jle     short loc_1800183A0
0x180018386  mov     r8d, 1; unsigned int
0x18001838c  lea     rdx, aAdleavetaskena_0; "AdLeaveTaskEnabled"
0x180018393  lea     rcx, [rsp+338h+var_2B8]; this
0x18001839b  call    ?SetValue@CSrmRegistryKey@@QEAAXPEBGK@Z; CSrmRegistryKey::SetValue(ushort const *,ulong)
0x1800183a0  mov     al, [rsi]
0x1800183a2  test    al, al
0x1800183a4  jz      short loc_1800183F1
0x1800183a6  lea     rcx, [rsp+338h+var_2B8]; this
0x1800183ae  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x1800183b3  nop
0x1800183b4  xorps   xmm0, xmm0
0x1800183b7  movdqu  xmmword ptr [rsp+338h+Block], xmm0
0x1800183bd  mov     [rsp+338h+var_2C8], rdi
0x1800183c2  test    rbx, rbx
0x1800183c5  jz      short loc_1800183D7
0x1800183c7  mov     rax, [rbx]
0x1800183ca  mov     rcx, rbx
0x1800183cd  mov     rax, [rax+10h]
0x1800183d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183d6  nop
0x1800183d7  mov     [rsp+338h+var_1C8], r14
0x1800183df  lea     rcx, [rsp+338h+var_1C8]; this
0x1800183e7  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800183ec  jmp     loc_1800188C2
0x1800183f1  lea     r12, ??_7CSrmSharedLockWrite@@6B@; const CSrmSharedLockWrite::`vftable'
0x1800183f8  mov     qword ptr [rsp+338h+var_1F8], r12
0x180018400  lea     r15, ?g_LockConfigGlobal@@3VCSrmSharedLock@@A; CSrmSharedLock g_LockConfigGlobal
0x180018407  mov     qword ptr [rsp+338h+var_1F8+8], r15
0x18001840f  xorps   xmm0, xmm0
0x180018412  movups  xmmword ptr [rsp+338h+var_1D8.wYear], xmm0
0x18001841a  lea     rcx, [rsp+338h+var_1E8]; lpSystemTime
0x180018422  call    cs:__imp_GetSystemTime
0x180018428  mov     rax, cs:?g_LockConfigGlobal@@3VCSrmSharedLock@@A; CSrmSharedLock g_LockConfigGlobal
0x18001842f  mov     rcx, r15
0x180018432  mov     rax, [rax+20h]
0x180018436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001843b  lea     rcx, [rsp+338h+var_1D8]; lpSystemTime
0x180018443  call    cs:__imp_GetSystemTime
0x180018449  nop
0x18001844a  mov     [rsp+338h+var_310], edi
0x18001844e  lea     rax, [rsp+338h+Block]
0x180018453  mov     [rsp+338h+var_318], rax
0x180018458  xor     r9d, r9d
0x18001845b  call    ??$EnumObjects@VCFciPropertyDefinition@@@CFciConfigObject@@SAXKQEAPEBG0HAEAV?$vector@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@V?$allocator@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@std@@K@Z; CFciConfigObject::EnumObjects<CFciPropertyDefinition>(ulong,ushort const * * const,ushort const * * const,int,std::vector<ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>> &,ulong)
0x180018460  mov     al, [rsi]
0x180018462  test    al, al
0x180018464  jz      loc_18001850D
0x18001846a  mov     qword ptr [rsp+338h+var_1F8], r12
0x180018472  mov     rcx, qword ptr [rsp+338h+var_1F8+8]
0x18001847a  mov     rax, [rcx]
0x18001847d  mov     rax, [rax+30h]
0x180018481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018486  nop
0x180018487  lea     rcx, [rsp+338h+var_2B8]; this
0x18001848f  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x180018494  nop
0x180018495  mov     r15, [rsp+338h+Block]
0x18001849a  test    r15, r15
0x18001849d  jz      short loc_1800184D0
0x18001849f  mov     rsi, r15
0x1800184a2  cmp     r15, [rsp+338h+Block+8]
0x1800184a7  jz      short loc_1800184C8
0x1800184a9  mov     rcx, [rsi]
0x1800184ac  test    rcx, rcx
0x1800184af  jz      short loc_1800184BD
0x1800184b1  mov     rax, [rcx]
0x1800184b4  mov     rax, [rax+10h]
0x1800184b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184bd  add     rsi, 8
0x1800184c1  cmp     rsi, [rsp+338h+Block+8]
0x1800184c6  jnz     short loc_1800184A9
0x1800184c8  mov     rcx, r15; Block
0x1800184cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800184d0  xorps   xmm0, xmm0
0x1800184d3  movdqu  xmmword ptr [rsp+338h+Block], xmm0
0x1800184d9  mov     [rsp+338h+var_2C8], rdi
0x1800184de  test    rbx, rbx
0x1800184e1  jz      short loc_1800184F3
0x1800184e3  mov     rax, [rbx]
0x1800184e6  mov     rcx, rbx
0x1800184e9  mov     rax, [rax+10h]
0x1800184ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184f2  nop
0x1800184f3  mov     [rsp+338h+var_1C8], r14
0x1800184fb  lea     rcx, [rsp+338h+var_1C8]; this
0x180018503  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180018508  jmp     loc_1800188C2
0x18001850d  lea     r8, [rsp+338h+Block]
0x180018512  mov     rdx, rbx
0x180018515  mov     rcx, rsi
0x180018518  call    ?UpdateLocalPropertyDefinitions@CAdReader@@AEAAXPEAV?$CComObject@VCFsrmCollection@@@ATL@@AEBV?$vector@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@V?$allocator@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@std@@@Z; CAdReader::UpdateLocalPropertyDefinitions(ATL::CComObject<CFsrmCollection> *,std::vector<ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>> const &)
0x18001851d  mov     al, [rsi]
0x18001851f  test    al, al
0x180018521  jz      loc_1800185CA
0x180018527  mov     qword ptr [rsp+338h+var_1F8], r12
0x18001852f  mov     rcx, qword ptr [rsp+338h+var_1F8+8]
0x180018537  mov     rax, [rcx]
0x18001853a  mov     rax, [rax+30h]
0x18001853e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018543  nop
0x180018544  lea     rcx, [rsp+338h+var_2B8]; this
0x18001854c  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x180018551  nop
0x180018552  mov     r15, [rsp+338h+Block]
0x180018557  test    r15, r15
0x18001855a  jz      short loc_18001858D
0x18001855c  mov     rsi, r15
0x18001855f  cmp     r15, [rsp+338h+Block+8]
0x180018564  jz      short loc_180018585
0x180018566  mov     rcx, [rsi]
0x180018569  test    rcx, rcx
0x18001856c  jz      short loc_18001857A
0x18001856e  mov     rax, [rcx]
0x180018571  mov     rax, [rax+10h]
0x180018575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001857a  add     rsi, 8
0x18001857e  cmp     rsi, [rsp+338h+Block+8]
0x180018583  jnz     short loc_180018566
0x180018585  mov     rcx, r15; Block
0x180018588  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001858d  xorps   xmm0, xmm0
0x180018590  movdqu  xmmword ptr [rsp+338h+Block], xmm0
0x180018596  mov     [rsp+338h+var_2C8], rdi
0x18001859b  test    rbx, rbx
0x18001859e  jz      short loc_1800185B0
0x1800185a0  mov     rax, [rbx]
0x1800185a3  mov     rcx, rbx
0x1800185a6  mov     rax, [rax+10h]
0x1800185aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185af  nop
0x1800185b0  mov     [rsp+338h+var_1C8], r14
0x1800185b8  lea     rcx, [rsp+338h+var_1C8]; this
0x1800185c0  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800185c5  jmp     loc_1800188C2
0x1800185ca  lea     r8, [rsp+338h+Block]
0x1800185cf  mov     rdx, rbx
0x1800185d2  mov     rcx, rsi
0x1800185d5  call    ?RemoveOrphanedPropertyDefinitions@CAdReader@@AEAAXPEAV?$CComObject@VCFsrmCollection@@@ATL@@AEBV?$vector@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@V?$allocator@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@std@@@Z; CAdReader::RemoveOrphanedPropertyDefinitions(ATL::CComObject<CFsrmCollection> *,std::vector<ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>> const &)
0x1800185da  nop
0x1800185db  mov     qword ptr [rsp+338h+var_1F8], r12
0x1800185e3  mov     rcx, qword ptr [rsp+338h+var_1F8+8]
0x1800185eb  mov     rax, [rcx]
0x1800185ee  mov     rax, [rax+30h]
0x1800185f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185f7  nop
0x1800185f8  jmp     short loc_18001860D
0x1800185fa  mov     rsi, [rsp+338h+var_2E8]
  ... truncated ...
```
