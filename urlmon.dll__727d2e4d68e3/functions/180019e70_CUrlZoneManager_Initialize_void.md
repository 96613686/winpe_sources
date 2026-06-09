# CUrlZoneManager::Initialize(void)

- ea: `0x180019e70`
- end: `0x18001a2f4`
- name: `?Initialize@CUrlZoneManager@@UEAAHXZ`
- size: `1156`
- prototype: `__int64 __fastcall(CUrlZoneManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a4ac`

## callees

- `0x180019e70`
- `0x18001db50`
- `0x180028510`
- `0x18003a744`
- `0x18003abdc`
- `0x18003c1b8`
- `0x18005b29c`
- `0x180084d30`
- `0x180086954`
- `0x180128660`

## import_xrefs

- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x18001a049`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x18001a049`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180019f9b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180019f9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019f52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019f52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019f1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019f1b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18001a09f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18001a09f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2c6`
- `ntdll!RtlMoveMemory` at `0x18001a0d7`
- `ntdll!RtlMoveMemory` at `0x18001a0d7`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18001a261`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18001a261`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180019fe5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180019fe5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001a014`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001a014`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1da`
- `SspiCli!GetUserNameExW` at `0x18001a083`
- `SspiCli!GetUserNameExW` at `0x18001a083`

## pseudocode

```c
__int64 __fastcall CUrlZoneManager::Initialize(CUrlZoneManager *this)
{
  unsigned int v1; // r12d
  unsigned int v2; // r15d
  __int64 v3; // rax
  const wchar_t *v4; // rdx
  __int64 v5; // r8
  WCHAR *v6; // r9
  __int64 v7; // r10
  wchar_t v8; // cx
  __int64 v9; // rcx
  WCHAR *v10; // rax
  WCHAR *v11; // rbx
  HANDLE FileMappingW; // rax
  char v14; // bl
  signed int v15; // eax
  bool v16; // sf
  PWSTR v17; // rax
  _WORD *v18; // rdx
  __int64 v19; // rax
  CRegZoneContainer *v20; // rax
  CRegZoneContainer *v21; // rdi
  int v22; // ebx
  CFeatureCache *v23; // rcx
  unsigned __int64 v24; // rcx
  void *v25; // rax
  _QWORD *v26; // rbx
  void *v27; // rcx
  CRegZoneContainer *v28; // rax
  __int64 v29; // rdx
  CRegZoneContainer *v30; // rax
  signed int v31; // eax
  signed int LastError; // eax
  ULONG nSize[2]; // [rsp+38h] [rbp-280h] BYREF
  WCHAR Name[280]; // [rsp+40h] [rbp-278h] BYREF

  v1 = 1;
  v2 = 0;
  *(_QWORD *)nSize = 0;
  v3 = 2147483646;
  v4 = L"Local\\UrlZonesSM_";
  v5 = 279;
  v6 = Name;
  v7 = 0;
  do
  {
    if ( !v3 )
      break;
    v8 = *v4;
    if ( !*v4 )
      break;
    ++v4;
    *v6++ = v8;
    --v3;
    ++v7;
    --v5;
  }
  while ( v5 );
  v9 = v7 - 1;
  if ( v5 )
    v9 = v7;
  v10 = v6 - 1;
  if ( v5 )
    v10 = v6;
  *v10 = 0;
  v11 = &Name[v9];
  if ( v5 )
  {
    nSize[0] = 279 - v9;
    if ( GetUserNameExW(NameSamCompatible, &Name[v9], nSize) )
    {
      v17 = StrChrW(v11, 0x5Cu);
      if ( v17 )
      {
        v18 = v17 + 1;
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        RtlMoveMemory(v11, v18, 2LL * (unsigned int)(v19 + 1));
      }
    }
  }
  EnterCriticalSection(&CUrlZoneManager::s_csect);
  if ( !qword_180169588 && !g_SharedMem )
  {
    dwMaximumSizeLow = 28;
    if ( (unsigned __int8)IEConfiguration_GetBool(536870915) )
    {
      FileMappingW = OpenFileMappingW(6u, 0, Name);
      g_SharedMem = (__int64)FileMappingW;
    }
    else
    {
      FileMappingW = (HANDLE)g_SharedMem;
    }
    if ( FileMappingW )
    {
      v14 = 0;
    }
    else
    {
      v14 = 1;
      FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, dwMaximumSizeLow, Name);
      g_SharedMem = (__int64)FileMappingW;
    }
    if ( FileMappingW )
    {
      qword_180169588 = (__int64)MapViewOfFile(FileMappingW, 2u, 0, 0, 0);
      if ( qword_180169588 )
      {
        v15 = 0;
        if ( v14 )
          v15 = SetWindowsHandleAccess((void *)g_SharedMem, 0x2110Fu, 0xC0000002);
        goto LABEL_23;
      }
      LastError = GetLastError();
      v16 = LastError < 0;
      if ( LastError > 0 )
      {
        v15 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_23;
      }
    }
    else
    {
      v31 = GetLastError();
      v16 = v31 < 0;
      if ( v31 > 0 )
      {
        v15 = (unsigned __int16)v31 | 0x80070000;
LABEL_23:
        v16 = v15 < 0;
      }
    }
    if ( v16 )
      CSharedMem::Release((CSharedMem *)&g_SharedMem);
  }
  if ( !CUrlZoneManager::s_pRegZoneContainer )
  {
    v28 = (CRegZoneContainer *)operator new(0x50u);
    if ( v28 )
      v30 = CRegZoneContainer::CRegZoneContainer(v28);
    else
      v30 = 0;
    CUrlZoneManager::s_pRegZoneContainer = v30;
    if ( v30 )
    {
      if ( !(unsigned int)CRegZoneContainer::Attach(v30, v29, 0) )
        v1 = 0;
    }
    else
    {
      v1 = 0;
    }
  }
  if ( !CUrlZoneManager::s_pRegLockZoneContainer )
  {
    v20 = (CRegZoneContainer *)operator new(0x50u);
    if ( v20 )
      v21 = CRegZoneContainer::CRegZoneContainer(v20);
    else
      v21 = 0;
    CUrlZoneManager::s_pRegLockZoneContainer = v21;
    if ( v21 )
    {
      v22 = g_bUseHKLMOnly;
      CRegZoneContainer::Detach(v21);
      *((_DWORD *)v21 + 7) = v22;
      *(_QWORD *)nSize = 0;
      if ( (int)CRegZoneContainer::EnumerateAndLoadZones((__int64)v21, 2, (__int64 ***)nSize, (_DWORD *)v21 + 6) >= 0 )
      {
        if ( g_pFeatureCache )
          CFeatureCache::IsFeatureEnabled(v23, FEATURE_LOCALMACHINE_LOCKDOWN);
        else
          CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::PRIVATE_INTERNETFEATURELIST_FEATURE_LOCALMACHINE_LOCKDOWN);
        v24 = *((unsigned int *)v21 + 6);
        if ( (_DWORD)v24 )
          v25 = operator new(saturated_mul(v24, 8u));
        else
          v25 = 0;
        *((_QWORD *)v21 + 2) = v25;
        if ( v25 )
        {
          if ( *((_DWORD *)v21 + 6) )
          {
            v26 = *(_QWORD **)nSize;
            do
            {
              *(_QWORD *)(*((_QWORD *)v21 + 2) + 8LL * v2) = v26[1];
              v27 = v26;
              v26 = (_QWORD *)*v26;
              if ( v27 )
                CoTaskMemFree(v27);
              ++v2;
            }
            while ( v2 < *((_DWORD *)v21 + 6) );
          }
          goto LABEL_13;
        }
        *((_DWORD *)v21 + 6) = 0;
      }
    }
    v1 = 0;
  }
LABEL_13:
  LeaveCriticalSection(&CUrlZoneManager::s_csect);
  return v1;
}

```

## disassembly

```asm
0x180019e70  push    rbx
0x180019e72  push    rsi
0x180019e73  push    rdi
0x180019e74  push    r12
0x180019e76  push    r14
0x180019e78  push    r15
0x180019e7a  sub     rsp, 288h
0x180019e81  mov     rax, cs:__security_cookie
0x180019e88  xor     rax, rsp
0x180019e8b  mov     [rsp+2B8h+var_48], rax
0x180019e93  mov     r12d, 1
0x180019e99  mov     [rsp+2B8h+var_288], r12d
0x180019e9e  xor     r15d, r15d
0x180019ea1  mov     qword ptr [rsp+2B8h+nSize], r15
0x180019ea6  mov     eax, 7FFFFFFEh
0x180019eab  lea     rdx, aLocalUrlzoness; "Local\\UrlZonesSM_"
0x180019eb2  mov     r11d, 117h
0x180019eb8  mov     r8d, r11d
0x180019ebb  lea     r9, [rsp+2B8h+Name]
0x180019ec0  mov     r10d, r15d
0x180019ec3  test    rax, rax
0x180019ec6  jz      short loc_180019EE7
0x180019ec8  movzx   ecx, word ptr [rdx]
0x180019ecb  test    cx, cx
0x180019ece  jz      short loc_180019EE7
0x180019ed0  add     rdx, 2
0x180019ed4  mov     [r9], cx
0x180019ed8  add     r9, 2
0x180019edc  dec     rax
0x180019edf  inc     r10
0x180019ee2  sub     r8, r12
0x180019ee5  jnz     short loc_180019EC3
0x180019ee7  lea     rcx, [r10-1]
0x180019eeb  test    r8, r8
0x180019eee  cmovnz  rcx, r10
0x180019ef2  lea     rax, [r9-2]
0x180019ef6  cmovnz  rax, r9
0x180019efa  mov     [rax], r15w
0x180019efe  lea     rbx, [rsp+2B8h+Name]
0x180019f03  lea     rbx, [rbx+rcx*2]
0x180019f07  jnz     loc_18001A06E
0x180019f0d  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180019f14  lea     rcx, ?s_csect@CUrlZoneManager@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019f1b  call    cs:__imp_EnterCriticalSection
0x180019f22  nop     dword ptr [rax+rax+00h]
0x180019f27  cmp     cs:qword_180169588, r15
0x180019f2e  jz      short loc_180019F83
0x180019f30  cmp     cs:?s_pRegZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA, r15; CRegZoneContainer * CUrlZoneManager::s_pRegZoneContainer
0x180019f37  jz      loc_18001A1F4
0x180019f3d  cmp     cs:?s_pRegLockZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA, 0; CRegZoneContainer * CUrlZoneManager::s_pRegLockZoneContainer
0x180019f45  jz      loc_18001A0E8
0x180019f4b  lea     rcx, ?s_csect@CUrlZoneManager@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019f52  call    cs:__imp_LeaveCriticalSection
0x180019f59  nop     dword ptr [rax+rax+00h]
0x180019f5e  mov     eax, r12d
0x180019f61  mov     rcx, [rsp+2B8h+var_48]
0x180019f69  xor     rcx, rsp; StackCookie
0x180019f6c  call    __security_check_cookie
0x180019f71  add     rsp, 288h
0x180019f78  pop     r15
0x180019f7a  pop     r14
0x180019f7c  pop     r12
0x180019f7e  pop     rdi
0x180019f7f  pop     rsi
0x180019f80  pop     rbx
0x180019f81  retn
0x180019f83  cmp     cs:?g_SharedMem@@3VCSharedMem@@A, r15; CSharedMem g_SharedMem
0x180019f8a  jnz     short loc_180019F30
0x180019f8c  mov     cs:dwMaximumSizeLow, 1Ch
0x180019f96  mov     ecx, 20000003h
0x180019f9b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180019fa2  nop     dword ptr [rax+rax+00h]
0x180019fa7  test    al, al
0x180019fa9  jnz     loc_18001A255
0x180019faf  mov     rax, cs:?g_SharedMem@@3VCSharedMem@@A; CSharedMem g_SharedMem
0x180019fb6  test    rax, rax
0x180019fb9  jnz     loc_18001A279
0x180019fbf  movzx   ebx, r12b
0x180019fc3  lea     rax, [rsp+2B8h+Name]
0x180019fc8  mov     [rsp+2B8h+lpName], rax; lpName
0x180019fcd  mov     eax, cs:dwMaximumSizeLow
0x180019fd3  mov     [rsp+2B8h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x180019fd7  xor     r9d, r9d; dwMaximumSizeHigh
0x180019fda  xor     edx, edx; lpFileMappingAttributes
0x180019fdc  mov     r8d, 4; flProtect
0x180019fe2  mov     rcx, r14; hFile
0x180019fe5  call    cs:__imp_CreateFileMappingW
0x180019fec  nop     dword ptr [rax+rax+00h]
0x180019ff1  mov     cs:?g_SharedMem@@3VCSharedMem@@A, rax; CSharedMem g_SharedMem
0x180019ff8  test    rax, rax
0x180019ffb  jz      loc_18001A291
0x18001a001  mov     qword ptr [rsp+2B8h+dwMaximumSizeLow], r15; dwNumberOfBytesToMap
0x18001a006  xor     r9d, r9d; dwFileOffsetLow
0x18001a009  xor     r8d, r8d; dwFileOffsetHigh
0x18001a00c  mov     edx, 2; dwDesiredAccess
0x18001a011  mov     rcx, rax; hFileMappingObject
0x18001a014  call    cs:__imp_MapViewOfFile
0x18001a01b  nop     dword ptr [rax+rax+00h]
0x18001a020  mov     cs:qword_180169588, rax
0x18001a027  test    rax, rax
0x18001a02a  jz      loc_18001A2C6
0x18001a030  mov     eax, r15d
0x18001a033  test    bl, bl
0x18001a035  jz      short loc_18001A055
0x18001a037  mov     edx, 2110Fh
0x18001a03c  mov     r8d, 0C0000002h
0x18001a042  mov     rcx, cs:?g_SharedMem@@3VCSharedMem@@A; CSharedMem g_SharedMem
0x18001a049  call    cs:__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x18001a050  nop     dword ptr [rax+rax+00h]
0x18001a055  test    eax, eax
0x18001a057  jns     loc_180019F30
0x18001a05d  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x18001a064  call    ?Release@CSharedMem@@QEAAXXZ; CSharedMem::Release(void)
0x18001a069  jmp     loc_180019F30
0x18001a06e  sub     r11d, ecx
0x18001a071  mov     [rsp+2B8h+nSize], r11d
0x18001a076  lea     r8, [rsp+2B8h+nSize]; nSize
0x18001a07b  mov     rdx, rbx; lpNameBuffer
0x18001a07e  mov     ecx, 2; NameFormat
0x18001a083  call    cs:__imp_GetUserNameExW
0x18001a08a  nop     dword ptr [rax+rax+00h]
0x18001a08f  test    al, al
0x18001a091  jz      loc_180019F0D
0x18001a097  mov     edx, 5Ch ; '\'; wMatch
0x18001a09c  mov     rcx, rbx; pszStart
0x18001a09f  call    cs:__imp_StrChrW
0x18001a0a6  nop     dword ptr [rax+rax+00h]
0x18001a0ab  test    rax, rax
0x18001a0ae  jz      loc_180019F0D
0x18001a0b4  lea     rdx, [rax+2]; Source
0x18001a0b8  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001a0bf  mov     rax, r14
0x18001a0c2  lea     rax, [rax+1]
0x18001a0c6  cmp     [rdx+rax*2], r15w
0x18001a0cb  jnz     short loc_18001A0C2
0x18001a0cd  lea     r8d, [rax+1]
0x18001a0d1  add     r8, r8; Length
0x18001a0d4  mov     rcx, rbx; Destination
0x18001a0d7  call    cs:__imp_RtlMoveMemory
0x18001a0de  nop     dword ptr [rax+rax+00h]
0x18001a0e3  jmp     loc_180019F14
0x18001a0e8  mov     ecx, 50h ; 'P'; Size
0x18001a0ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a0f2  test    rax, rax
0x18001a0f5  jz      short loc_18001A104
0x18001a0f7  mov     rcx, rax; this
0x18001a0fa  call    ??0CRegZoneContainer@@QEAA@XZ; CRegZoneContainer::CRegZoneContainer(void)
0x18001a0ff  mov     rdi, rax
0x18001a102  jmp     short loc_18001A107
0x18001a104  mov     rdi, r15
0x18001a107  mov     cs:?s_pRegLockZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA, rdi; CRegZoneContainer * CUrlZoneManager::s_pRegLockZoneContainer
0x18001a10e  jmp     short loc_18001A128
0x18001a110  xor     edi, edi
0x18001a112  mov     cs:?s_pRegLockZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA, rdi; CRegZoneContainer * CUrlZoneManager::s_pRegLockZoneContainer
0x18001a119  xor     r15d, r15d
0x18001a11c  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001a123  mov     r12d, [rsp+2B8h+var_288]
0x18001a128  test    rdi, rdi
0x18001a12b  jz      loc_18001A2B6
0x18001a131  mov     ebx, cs:?g_bUseHKLMOnly@@3HA; int g_bUseHKLMOnly
0x18001a137  mov     rcx, rdi; this
0x18001a13a  call    ?Detach@CRegZoneContainer@@QEAAHXZ; CRegZoneContainer::Detach(void)
0x18001a13f  mov     [rdi+1Ch], ebx
0x18001a142  mov     qword ptr [rsp+2B8h+nSize], r15
0x18001a147  lea     r9, [rdi+18h]
0x18001a14b  lea     r8, [rsp+2B8h+nSize]
0x18001a150  mov     edx, 2
0x18001a155  mov     rcx, rdi
0x18001a158  call    ?EnumerateAndLoadZones@CRegZoneContainer@@QEAAJW4REGZONEUSE@@PEAPEAUCRegListElem@1@PEAK@Z; CRegZoneContainer::EnumerateAndLoadZones(REGZONEUSE,CRegZoneContainer::CRegListElem * *,ulong *)
0x18001a15d  test    eax, eax
0x18001a15f  js      loc_18001A2B6
0x18001a165  cmp     cs:?g_pFeatureCache@@3PEAVCFeatureCache@@EA, 0; CFeatureCache * g_pFeatureCache
0x18001a16d  jz      loc_18001A280
0x18001a173  mov     edx, 8; enum _tagINTERNETFEATURELIST
0x18001a178  call    ?IsFeatureEnabled@CFeatureCache@@QEAA_NW4_tagINTERNETFEATURELIST@@@Z; CFeatureCache::IsFeatureEnabled(_tagINTERNETFEATURELIST)
0x18001a17d  mov     ecx, [rdi+18h]
0x18001a180  test    ecx, ecx
0x18001a182  jz      loc_18001A2BE
0x18001a188  mov     eax, 8
0x18001a18d  mul     rcx
0x18001a190  cmovb   rax, r14
0x18001a194  mov     rcx, rax; Size
0x18001a197  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a19c  mov     [rdi+10h], rax
0x18001a1a0  test    rax, rax
0x18001a1a3  jz      loc_18001A2B2
0x18001a1a9  cmp     dword ptr [rdi+18h], 0
0x18001a1ad  jbe     loc_180019F4B
0x18001a1b3  mov     rbx, qword ptr [rsp+2B8h+nSize]
0x18001a1b8  nop     dword ptr [rax+rax+00000000h]
0x18001a1c0  mov     edx, r15d
0x18001a1c3  mov     rcx, [rdi+10h]
0x18001a1c7  mov     rax, [rbx+8]
0x18001a1cb  mov     [rcx+rdx*8], rax
0x18001a1cf  mov     rcx, rbx; pv
0x18001a1d2  mov     rbx, [rbx]
0x18001a1d5  test    rcx, rcx
0x18001a1d8  jz      short loc_18001A1E6
0x18001a1da  call    cs:__imp_CoTaskMemFree
0x18001a1e1  nop     dword ptr [rax+rax+00h]
0x18001a1e6  inc     r15d
0x18001a1e9  cmp     r15d, [rdi+18h]
0x18001a1ed  jb      short loc_18001A1C0
0x18001a1ef  jmp     loc_180019F4B
0x18001a1f4  mov     ecx, 50h ; 'P'; Size
0x18001a1f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a1fe  test    rax, rax
0x18001a201  jnz     short loc_18001A208
0x18001a203  mov     rax, r15
0x18001a206  jmp     short loc_18001A210
0x18001a208  mov     rcx, rax; this
0x18001a20b  call    ??0CRegZoneContainer@@QEAA@XZ; CRegZoneContainer::CRegZoneContainer(void)
0x18001a210  mov     cs:?s_pRegZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA, rax; CRegZoneContainer * CUrlZoneManager::s_pRegZoneContainer
0x18001a217  jmp     short loc_18001A231
0x18001a219  xor     eax, eax
0x18001a21b  mov     cs:?s_pRegZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA, rax; CRegZoneContainer * CUrlZoneManager::s_pRegZoneContainer
0x18001a222  xor     r15d, r15d
0x18001a225  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001a22c  mov     r12d, [rsp+2B8h+var_288]
0x18001a231  test    rax, rax
0x18001a234  jz      loc_18001A2E7
0x18001a23a  xor     r8d, r8d
0x18001a23d  mov     rcx, rax
0x18001a240  call    ?Attach@CRegZoneContainer@@QEAAHHW4REGZONEUSE@@@Z; CRegZoneContainer::Attach(int,REGZONEUSE)
0x18001a245  test    eax, eax
0x18001a247  cmovz   r12d, r15d
0x18001a24b  mov     [rsp+2B8h+var_288], r12d
0x18001a250  jmp     loc_180019F3D
0x18001a255  lea     r8, [rsp+2B8h+Name]; lpName
0x18001a25a  xor     edx, edx; bInheritHandle
0x18001a25c  mov     ecx, 6; dwDesiredAccess
0x18001a261  call    cs:__imp_OpenFileMappingW
0x18001a268  nop     dword ptr [rax+rax+00h]
0x18001a26d  mov     cs:?g_SharedMem@@3VCSharedMem@@A, rax; CSharedMem g_SharedMem
0x18001a274  jmp     loc_180019FB6
0x18001a279  xor     bl, bl
0x18001a27b  jmp     loc_180019FF8
0x18001a280  lea     rcx, ?PRIVATE_INTERNETFEATURELIST_FEATURE_LOCALMACHINE_LOCKDOWN@FCK@@3VCFeatureControlKey@@A; this
0x18001a287  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x18001a28c  jmp     loc_18001A17D
0x18001a291  call    cs:__imp_GetLastError
0x18001a298  nop     dword ptr [rax+rax+00h]
0x18001a29d  test    eax, eax
0x18001a29f  jle     loc_18001A057
0x18001a2a5  movzx   eax, ax
0x18001a2a8  or      eax, 80070000h
0x18001a2ad  jmp     loc_18001A055
0x18001a2b2  mov     [rdi+18h], r15d
0x18001a2b6  mov     r12d, r15d
0x18001a2b9  jmp     loc_180019F4B
0x18001a2be  mov     rax, r15
0x18001a2c1  jmp     loc_18001A19C
0x18001a2c6  call    cs:__imp_GetLastError
0x18001a2cd  nop     dword ptr [rax+rax+00h]
0x18001a2d2  test    eax, eax
0x18001a2d4  jle     loc_18001A057
0x18001a2da  movzx   eax, ax
0x18001a2dd  or      eax, 80070000h
0x18001a2e2  jmp     loc_18001A055
0x18001a2e7  mov     r12d, r15d
0x18001a2ea  mov     [rsp+2B8h+var_288], r15d
0x18001a2ef  jmp     loc_180019F3D
0x1801287a0  push    rbp
0x1801287a2  sub     rsp, 30h
0x1801287a6  mov     rbp, rdx
0x1801287a9  mov     rax, [rcx]
0x1801287ac  xor     ecx, ecx
0x1801287ae  cmp     dword ptr [rax], 0C0000017h
0x1801287b4  setz    cl
0x1801287b7  mov     eax, ecx
0x1801287b9  add     rsp, 30h
0x1801287bd  pop     rbp
0x1801287be  retn
```
