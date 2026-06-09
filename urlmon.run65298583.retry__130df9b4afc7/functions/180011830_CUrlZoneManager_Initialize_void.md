# CUrlZoneManager::Initialize(void)

- ea: `0x180011830`
- end: `0x180011c5d`
- name: `?Initialize@CUrlZoneManager@@UEAAHXZ`
- size: `1069`
- prototype: `__int64 __fastcall(CUrlZoneManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800121e4`

## callees

- `0x180011830`
- `0x1800150e0`
- `0x1800215c0`
- `0x180029298`
- `0x180032c64`
- `0x1800330bc`
- `0x180034574`
- `0x180080b38`
- `0x180080f54`
- `0x18011baa0`

## import_xrefs

- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x1800119ea`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x1800119ea`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18001194e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18001194e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001190c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001190c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800118db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800118db`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180011a34`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180011a34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c35`
- `ntdll!RtlMoveMemory` at `0x180011a66`
- `ntdll!RtlMoveMemory` at `0x180011a66`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180011bdc`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180011bdc`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180011992`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180011992`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800119bb`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800119bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011b5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011b5b`
- `SspiCli!GetUserNameExW` at `0x180011a1e`
- `SspiCli!GetUserNameExW` at `0x180011a1e`

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
  if ( !qword_18015C488 && !g_SharedMem )
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
      qword_18015C488 = (__int64)MapViewOfFile(FileMappingW, 2u, 0, 0, 0);
      if ( qword_18015C488 )
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
      if ( (int)CRegZoneContainer::EnumerateAndLoadZones((__int64)v21, 2u, nSize, (_DWORD *)v21 + 6) >= 0 )
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
0x180011830  push    rbx
0x180011832  push    rsi
0x180011833  push    rdi
0x180011834  push    r12
0x180011836  push    r14
0x180011838  push    r15
0x18001183a  sub     rsp, 288h
0x180011841  mov     rax, cs:__security_cookie
0x180011848  xor     rax, rsp
0x18001184b  mov     [rsp+2B8h+var_48], rax
0x180011853  mov     r12d, 1
0x180011859  mov     [rsp+2B8h+var_288], r12d
0x18001185e  xor     r15d, r15d
0x180011861  mov     qword ptr [rsp+2B8h+nSize], r15
0x180011866  mov     eax, 7FFFFFFEh
0x18001186b  lea     rdx, aLocalUrlzoness; "Local\\UrlZonesSM_"
0x180011872  mov     r11d, 117h
0x180011878  mov     r8d, r11d
0x18001187b  lea     r9, [rsp+2B8h+Name]
0x180011880  mov     r10d, r15d
0x180011883  test    rax, rax
0x180011886  jz      short loc_1800118A7
0x180011888  movzx   ecx, word ptr [rdx]
0x18001188b  test    cx, cx
0x18001188e  jz      short loc_1800118A7
0x180011890  add     rdx, 2
0x180011894  mov     [r9], cx
0x180011898  add     r9, 2
0x18001189c  dec     rax
0x18001189f  inc     r10
0x1800118a2  sub     r8, r12
0x1800118a5  jnz     short loc_180011883
0x1800118a7  lea     rcx, [r10-1]
0x1800118ab  test    r8, r8
0x1800118ae  cmovnz  rcx, r10
0x1800118b2  lea     rax, [r9-2]
0x1800118b6  cmovnz  rax, r9
0x1800118ba  mov     [rax], r15w
0x1800118be  lea     rbx, [rsp+2B8h+Name]
0x1800118c3  lea     rbx, [rbx+rcx*2]
0x1800118c7  jnz     loc_180011A09
0x1800118cd  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800118d4  lea     rcx, ?s_csect@CUrlZoneManager@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800118db  call    cs:__imp_EnterCriticalSection
0x1800118e1  cmp     cs:qword_18015C488, r15
0x1800118e8  jz      short loc_180011936
0x1800118ea  cmp     cs:?s_pRegZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA, r15; CRegZoneContainer * CUrlZoneManager::s_pRegZoneContainer
0x1800118f1  jz      loc_180011B6F
0x1800118f7  cmp     cs:?s_pRegLockZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA, 0; CRegZoneContainer * CUrlZoneManager::s_pRegLockZoneContainer
0x1800118ff  jz      loc_180011A71
0x180011905  lea     rcx, ?s_csect@CUrlZoneManager@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001190c  call    cs:__imp_LeaveCriticalSection
0x180011912  mov     eax, r12d
0x180011915  mov     rcx, [rsp+2B8h+var_48]
0x18001191d  xor     rcx, rsp; StackCookie
0x180011920  call    __security_check_cookie
0x180011925  add     rsp, 288h
0x18001192c  pop     r15
0x18001192e  pop     r14
0x180011930  pop     r12
0x180011932  pop     rdi
0x180011933  pop     rsi
0x180011934  pop     rbx
0x180011935  retn
0x180011936  cmp     cs:?g_SharedMem@@3VCSharedMem@@A, r15; CSharedMem g_SharedMem
0x18001193d  jnz     short loc_1800118EA
0x18001193f  mov     cs:dwMaximumSizeLow, 1Ch
0x180011949  mov     ecx, 20000003h
0x18001194e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180011954  test    al, al
0x180011956  jnz     loc_180011BD0
0x18001195c  mov     rax, cs:?g_SharedMem@@3VCSharedMem@@A; CSharedMem g_SharedMem
0x180011963  test    rax, rax
0x180011966  jnz     loc_180011BEE
0x18001196c  movzx   ebx, r12b
0x180011970  lea     rax, [rsp+2B8h+Name]
0x180011975  mov     [rsp+2B8h+lpName], rax; lpName
0x18001197a  mov     eax, cs:dwMaximumSizeLow
0x180011980  mov     [rsp+2B8h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x180011984  xor     r9d, r9d; dwMaximumSizeHigh
0x180011987  xor     edx, edx; lpFileMappingAttributes
0x180011989  mov     r8d, 4; flProtect
0x18001198f  mov     rcx, r14; hFile
0x180011992  call    cs:__imp_CreateFileMappingW
0x180011998  mov     cs:?g_SharedMem@@3VCSharedMem@@A, rax; CSharedMem g_SharedMem
0x18001199f  test    rax, rax
0x1800119a2  jz      loc_180011C06
0x1800119a8  mov     qword ptr [rsp+2B8h+dwMaximumSizeLow], r15; dwNumberOfBytesToMap
0x1800119ad  xor     r9d, r9d; dwFileOffsetLow
0x1800119b0  xor     r8d, r8d; dwFileOffsetHigh
0x1800119b3  mov     edx, 2; dwDesiredAccess
0x1800119b8  mov     rcx, rax; hFileMappingObject
0x1800119bb  call    cs:__imp_MapViewOfFile
0x1800119c1  mov     cs:qword_18015C488, rax
0x1800119c8  test    rax, rax
0x1800119cb  jz      loc_180011C35
0x1800119d1  mov     eax, r15d
0x1800119d4  test    bl, bl
0x1800119d6  jz      short loc_1800119F0
0x1800119d8  mov     edx, 2110Fh
0x1800119dd  mov     r8d, 0C0000002h
0x1800119e3  mov     rcx, cs:?g_SharedMem@@3VCSharedMem@@A; CSharedMem g_SharedMem
0x1800119ea  call    cs:__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x1800119f0  test    eax, eax
0x1800119f2  jns     loc_1800118EA
0x1800119f8  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x1800119ff  call    ?Release@CSharedMem@@QEAAXXZ; CSharedMem::Release(void)
0x180011a04  jmp     loc_1800118EA
0x180011a09  sub     r11d, ecx
0x180011a0c  mov     [rsp+2B8h+nSize], r11d
0x180011a11  lea     r8, [rsp+2B8h+nSize]; nSize
0x180011a16  mov     rdx, rbx; lpNameBuffer
0x180011a19  mov     ecx, 2; NameFormat
0x180011a1e  call    cs:__imp_GetUserNameExW
0x180011a24  test    al, al
0x180011a26  jz      loc_1800118CD
0x180011a2c  mov     edx, 5Ch ; '\'; wMatch
0x180011a31  mov     rcx, rbx; pszStart
0x180011a34  call    cs:__imp_StrChrW
0x180011a3a  test    rax, rax
0x180011a3d  jz      loc_1800118CD
0x180011a43  lea     rdx, [rax+2]; Source
0x180011a47  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180011a4e  mov     rax, r14
0x180011a51  lea     rax, [rax+1]
0x180011a55  cmp     [rdx+rax*2], r15w
0x180011a5a  jnz     short loc_180011A51
0x180011a5c  lea     r8d, [rax+1]
0x180011a60  add     r8, r8; Length
0x180011a63  mov     rcx, rbx; Destination
0x180011a66  call    cs:__imp_RtlMoveMemory
0x180011a6c  jmp     loc_1800118D4
0x180011a71  mov     ecx, 50h ; 'P'; Size
0x180011a76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011a7b  test    rax, rax
0x180011a7e  jz      short loc_180011A8D
0x180011a80  mov     rcx, rax; this
0x180011a83  call    ??0CRegZoneContainer@@QEAA@XZ; CRegZoneContainer::CRegZoneContainer(void)
0x180011a88  mov     rdi, rax
0x180011a8b  jmp     short loc_180011A90
0x180011a8d  mov     rdi, r15
0x180011a90  mov     cs:?s_pRegLockZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA, rdi; CRegZoneContainer * CUrlZoneManager::s_pRegLockZoneContainer
0x180011a97  jmp     short loc_180011AB1
0x180011a99  xor     edi, edi
0x180011a9b  mov     cs:?s_pRegLockZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA, rdi; CRegZoneContainer * CUrlZoneManager::s_pRegLockZoneContainer
0x180011aa2  xor     r15d, r15d
0x180011aa5  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180011aac  mov     r12d, [rsp+2B8h+var_288]
0x180011ab1  test    rdi, rdi
0x180011ab4  jz      loc_180011C25
0x180011aba  mov     ebx, cs:?g_bUseHKLMOnly@@3HA; int g_bUseHKLMOnly
0x180011ac0  mov     rcx, rdi; this
0x180011ac3  call    ?Detach@CRegZoneContainer@@QEAAHXZ; CRegZoneContainer::Detach(void)
0x180011ac8  mov     [rdi+1Ch], ebx
0x180011acb  mov     qword ptr [rsp+2B8h+nSize], r15
0x180011ad0  lea     r9, [rdi+18h]
0x180011ad4  lea     r8, [rsp+2B8h+nSize]
0x180011ad9  mov     edx, 2
0x180011ade  mov     rcx, rdi
0x180011ae1  call    ?EnumerateAndLoadZones@CRegZoneContainer@@QEAAJW4REGZONEUSE@@PEAPEAUCRegListElem@1@PEAK@Z; CRegZoneContainer::EnumerateAndLoadZones(REGZONEUSE,CRegZoneContainer::CRegListElem * *,ulong *)
0x180011ae6  test    eax, eax
0x180011ae8  js      loc_180011C25
0x180011aee  cmp     cs:?g_pFeatureCache@@3PEAVCFeatureCache@@EA, 0; CFeatureCache * g_pFeatureCache
0x180011af6  jz      loc_180011BF5
0x180011afc  mov     edx, 8; enum _tagINTERNETFEATURELIST
0x180011b01  call    ?IsFeatureEnabled@CFeatureCache@@QEAA_NW4_tagINTERNETFEATURELIST@@@Z; CFeatureCache::IsFeatureEnabled(_tagINTERNETFEATURELIST)
0x180011b06  mov     ecx, [rdi+18h]
0x180011b09  test    ecx, ecx
0x180011b0b  jz      loc_180011C2D
0x180011b11  mov     eax, 8
0x180011b16  mul     rcx
0x180011b19  cmovb   rax, r14
0x180011b1d  mov     rcx, rax; Size
0x180011b20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011b25  mov     [rdi+10h], rax
0x180011b29  test    rax, rax
0x180011b2c  jz      loc_180011C21
0x180011b32  cmp     dword ptr [rdi+18h], 0
0x180011b36  jbe     loc_180011905
0x180011b3c  mov     rbx, qword ptr [rsp+2B8h+nSize]
0x180011b41  mov     edx, r15d
0x180011b44  mov     rcx, [rdi+10h]
0x180011b48  mov     rax, [rbx+8]
0x180011b4c  mov     [rcx+rdx*8], rax
0x180011b50  mov     rcx, rbx; pv
0x180011b53  mov     rbx, [rbx]
0x180011b56  test    rcx, rcx
0x180011b59  jz      short loc_180011B61
0x180011b5b  call    cs:__imp_CoTaskMemFree
0x180011b61  inc     r15d
0x180011b64  cmp     r15d, [rdi+18h]
0x180011b68  jb      short loc_180011B41
0x180011b6a  jmp     loc_180011905
0x180011b6f  mov     ecx, 50h ; 'P'; Size
0x180011b74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011b79  test    rax, rax
0x180011b7c  jnz     short loc_180011B83
0x180011b7e  mov     rax, r15
0x180011b81  jmp     short loc_180011B8B
0x180011b83  mov     rcx, rax; this
0x180011b86  call    ??0CRegZoneContainer@@QEAA@XZ; CRegZoneContainer::CRegZoneContainer(void)
0x180011b8b  mov     cs:?s_pRegZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA, rax; CRegZoneContainer * CUrlZoneManager::s_pRegZoneContainer
0x180011b92  jmp     short loc_180011BAC
0x180011b94  xor     eax, eax
0x180011b96  mov     cs:?s_pRegZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA, rax; CRegZoneContainer * CUrlZoneManager::s_pRegZoneContainer
0x180011b9d  xor     r15d, r15d
0x180011ba0  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180011ba7  mov     r12d, [rsp+2B8h+var_288]
0x180011bac  test    rax, rax
0x180011baf  jz      loc_180011C50
0x180011bb5  xor     r8d, r8d
0x180011bb8  mov     rcx, rax
0x180011bbb  call    ?Attach@CRegZoneContainer@@QEAAHHW4REGZONEUSE@@@Z; CRegZoneContainer::Attach(int,REGZONEUSE)
0x180011bc0  test    eax, eax
0x180011bc2  cmovz   r12d, r15d
0x180011bc6  mov     [rsp+2B8h+var_288], r12d
0x180011bcb  jmp     loc_1800118F7
0x180011bd0  lea     r8, [rsp+2B8h+Name]; lpName
0x180011bd5  xor     edx, edx; bInheritHandle
0x180011bd7  mov     ecx, 6; dwDesiredAccess
0x180011bdc  call    cs:__imp_OpenFileMappingW
0x180011be2  mov     cs:?g_SharedMem@@3VCSharedMem@@A, rax; CSharedMem g_SharedMem
0x180011be9  jmp     loc_180011963
0x180011bee  xor     bl, bl
0x180011bf0  jmp     loc_18001199F
0x180011bf5  lea     rcx, ?PRIVATE_INTERNETFEATURELIST_FEATURE_LOCALMACHINE_LOCKDOWN@FCK@@3VCFeatureControlKey@@A; this
0x180011bfc  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180011c01  jmp     loc_180011B06
0x180011c06  call    cs:__imp_GetLastError
0x180011c0c  test    eax, eax
0x180011c0e  jle     loc_1800119F2
0x180011c14  movzx   eax, ax
0x180011c17  or      eax, 80070000h
0x180011c1c  jmp     loc_1800119F0
0x180011c21  mov     [rdi+18h], r15d
0x180011c25  mov     r12d, r15d
0x180011c28  jmp     loc_180011905
0x180011c2d  mov     rax, r15
0x180011c30  jmp     loc_180011B25
0x180011c35  call    cs:__imp_GetLastError
0x180011c3b  test    eax, eax
0x180011c3d  jle     loc_1800119F2
0x180011c43  movzx   eax, ax
0x180011c46  or      eax, 80070000h
0x180011c4b  jmp     loc_1800119F0
0x180011c50  mov     r12d, r15d
0x180011c53  mov     [rsp+2B8h+var_288], r15d
0x180011c58  jmp     loc_1800118F7
0x18011bbe0  push    rbp
0x18011bbe2  sub     rsp, 30h
0x18011bbe6  mov     rbp, rdx
0x18011bbe9  mov     rax, [rcx]
0x18011bbec  xor     ecx, ecx
0x18011bbee  cmp     dword ptr [rax], 0C0000017h
0x18011bbf4  setz    cl
0x18011bbf7  mov     eax, ecx
0x18011bbf9  add     rsp, 30h
0x18011bbfd  pop     rbp
0x18011bbfe  retn
```
