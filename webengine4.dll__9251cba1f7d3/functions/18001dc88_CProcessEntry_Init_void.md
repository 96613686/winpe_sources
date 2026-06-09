# CProcessEntry::Init(void)

- ea: `0x18001dc88`
- end: `0x18001e4bb`
- name: `?Init@CProcessEntry@@QEAAJXZ`
- size: `2099`
- prototype: `__int64 __fastcall(CProcessEntry *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000e744`

## callees

- `0x180001924`
- `0x18000245c`
- `0x180007824`
- `0x18000b7e0`
- `0x18000bb40`
- `0x18000dd78`
- `0x180012b30`
- `0x1800139a4`
- `0x18001b780`
- `0x18001cc34`
- `0x18001ce48`
- `0x18001d3c0`
- `0x18001dc88`
- `0x18001e504`
- `0x18001ef80`
- `0x1800205f4`
- `0x18002064c`
- `0x180049b60`
- `0x18004c7e3`
- `0x18004c7e9`
- `0x18004d030`
- `0x18004d350`
- `0x18004d754`
- `0x180064c30`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001e47b`
- `KERNEL32!CloseHandle` at `0x18001e47b`
- `KERNEL32!GetLastError` at `0x18001e023`
- `KERNEL32!GetLastError` at `0x18001e064`
- `KERNEL32!GetLastError` at `0x18001e023`
- `KERNEL32!GetLastError` at `0x18001e064`
- `KERNEL32!lstrlenW` at `0x18001e0b0`
- `KERNEL32!lstrlenW` at `0x18001e0bf`
- `KERNEL32!lstrlenW` at `0x18001e0ce`
- `KERNEL32!lstrlenW` at `0x18001e0b0`
- `KERNEL32!lstrlenW` at `0x18001e0bf`
- `KERNEL32!lstrlenW` at `0x18001e0ce`
- `KERNEL32!GetCurrentProcessId` at `0x18001dce4`
- `KERNEL32!GetCurrentProcessId` at `0x18001dce4`
- `KERNEL32!WaitForSingleObject` at `0x18001e3cd`
- `KERNEL32!WaitForSingleObject` at `0x18001e3cd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001e377`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001e377`
- `KERNEL32!SetLastError` at `0x18001dff7`
- `KERNEL32!SetLastError` at `0x18001e038`
- `KERNEL32!SetLastError` at `0x18001dff7`
- `KERNEL32!SetLastError` at `0x18001e038`
- `KERNEL32!SetEvent` at `0x18001e120`
- `KERNEL32!SetEvent` at `0x18001e120`
- `KERNEL32!CreateEventW` at `0x18001e00d`
- `KERNEL32!CreateEventW` at `0x18001e04e`
- `KERNEL32!CreateEventW` at `0x18001e00d`
- `KERNEL32!CreateEventW` at `0x18001e04e`
- `KERNEL32!GetSystemInfo` at `0x18001dde3`
- `KERNEL32!GetSystemInfo` at `0x18001dde3`
- `ADVAPI32!OpenProcessToken` at `0x18001e40e`
- `ADVAPI32!OpenProcessToken` at `0x18001e40e`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18001de40`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18001de40`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18001de5b`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18001de5b`
- `ADVAPI32!DuplicateToken` at `0x18001e460`
- `ADVAPI32!DuplicateToken` at `0x18001e460`
- `ADVAPI32!SetKernelObjectSecurity` at `0x18001e443`
- `ADVAPI32!SetKernelObjectSecurity` at `0x18001e443`

## pseudocode

```c
__int64 __fastcall CProcessEntry::Init(CProcessEntry *this)
{
  struct _SECURITY_ATTRIBUTES *v2; // r15
  DWORD CurrentProcessId; // r13d
  int v4; // r12d
  unsigned int RandomString; // ebx
  void *WorkerProcessToken; // rax
  void *v7; // r14
  BOOL v8; // eax
  HANDLE EventW; // rax
  HANDLE v10; // rax
  const WCHAR *v11; // rsi
  __int64 *v12; // rax
  int v13; // ebx
  int v14; // ebx
  void *v15; // rcx
  __int64 v17; // rdx
  signed __int64 v18; // rsi
  unsigned __int16 *v19; // rcx
  unsigned __int16 v20; // ax
  unsigned __int16 *v21; // rax
  int v22; // r12d
  int v23; // esi
  void *v24; // rcx
  BOOL v25; // esi
  void *v26; // rcx
  struct _STARTUPINFOW *v27; // [rsp+20h] [rbp-E0h]
  struct _STARTUPINFOW *v28; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v29; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v30; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v31; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v32; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v33; // [rsp+28h] [rbp-D8h]
  void *v34; // [rsp+30h] [rbp-D0h]
  void *v35; // [rsp+30h] [rbp-D0h]
  void *v36; // [rsp+30h] [rbp-D0h]
  void *v37; // [rsp+30h] [rbp-D0h]
  void *v38; // [rsp+30h] [rbp-D0h]
  __int64 v39; // [rsp+38h] [rbp-C8h]
  __int64 v40; // [rsp+40h] [rbp-C0h]
  __int64 v41; // [rsp+48h] [rbp-B8h]
  int RegForNumSyncPipes; // [rsp+60h] [rbp-A0h]
  LPVOID Environment; // [rsp+68h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  PACL pDacl; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v46[3]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v48; // [rsp+B8h] [rbp-48h]
  struct _STARTUPINFOW v49; // [rsp+C0h] [rbp-40h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v51[32]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v52[264]; // [rsp+1A0h] [rbp+A0h] BYREF
  wchar_t Buffer[264]; // [rsp+3B0h] [rbp+2B0h] BYREF
  wchar_t v54[264]; // [rsp+5C0h] [rbp+4C0h] BYREF
  WCHAR Name[264]; // [rsp+7D0h] [rbp+6D0h] BYREF
  WCHAR v56[264]; // [rsp+9E0h] [rbp+8E0h] BYREF
  wchar_t v57[1024]; // [rsp+BF0h] [rbp+AF0h] BYREF

  if ( g_fShuttingDown == 1 || !*((_QWORD *)this + 21) )
    return 2147500037LL;
  v2 = 0;
  pDacl = 0;
  CurrentProcessId = GetCurrentProcessId();
  v4 = 0;
  Environment = 0;
  RegForNumSyncPipes = CProcessEntry::ReadRegForNumSyncPipes();
  memset_0(v54, 0, 0x20Au);
  memset_0(Buffer, 0, 0x20Au);
  memset_0(v57, 0, sizeof(v57));
  memset_0(Name, 0, 0x20Au);
  memset_0(v56, 0, 0x20Au);
  memset_0(v52, 0, 0x20Au);
  memset_0(v51, 0, sizeof(v51));
  memset_0(&v49, 0, sizeof(v49));
  v48 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  RandomString = GenerateRandomString(v51, 31);
  if ( RandomString )
    goto LABEL_37;
  if ( *((_DWORD *)this + 82) == 1 )
    goto LABEL_40;
  if ( (unsigned int)CProcessTableManager::GetUseCPUAffinity() )
  {
    v4 = *((_DWORD *)this + 83);
    if ( v4 )
    {
      GetSystemInfo(&SystemInfo);
      v4 &= LODWORD(SystemInfo.dwActiveProcessorMask);
    }
  }
  WorkerProcessToken = CProcessTableManager::GetWorkerProcessToken();
  v7 = WorkerProcessToken;
  if ( WorkerProcessToken == (void *)-1LL )
  {
    XspLogEvent(0xC00003EF);
    goto LABEL_10;
  }
  if ( !WorkerProcessToken )
  {
LABEL_18:
    if ( *((_QWORD *)this + 23) )
    {
      RandomString = StringCchPrintfW(
                       Buffer,
                       0x104u,
                       L"\\\\.\\pipe\\ASP.NETPMSyncPipe_%s_%s_%u_%u",
                       v51,
                       L"4.0.30319.0",
                       CurrentProcessId,
                       *((_DWORD *)this + 84));
      if ( RandomString )
        goto LABEL_37;
      RandomString = CAckReceiver::Init((CProcessEntry *)((char *)this + 16), this, Buffer, v2, RegForNumSyncPipes);
      if ( RandomString )
        goto LABEL_37;
      LODWORD(v34) = *((_DWORD *)this + 84);
      LODWORD(v29) = CurrentProcessId;
      RandomString = StringCchPrintfW(
                       v54,
                       0x104u,
                       L"\\\\.\\pipe\\ASP.NETPMAsyncPipe_%s_%s_%u_%u",
                       v51,
                       L"4.0.30319.0",
                       v29,
                       v34);
      if ( RandomString )
        goto LABEL_37;
      RandomString = CAsyncPipe::Init((CProcessEntry *)((char *)this + 80), this, v54, v2);
      if ( RandomString )
        goto LABEL_37;
      LODWORD(v35) = *((_DWORD *)this + 84);
      LODWORD(v30) = CurrentProcessId;
      RandomString = StringCchPrintfW(Name, 0x104u, L"ASP.NETPMEvent_%s_%s_%u_%u", v51, L"4.0.30319.0", v30, v35);
      if ( RandomString )
        goto LABEL_37;
      LODWORD(v36) = *((_DWORD *)this + 84);
      LODWORD(v31) = CurrentProcessId;
      RandomString = StringCchPrintfW(v56, 0x104u, L"ASP.NETPMEvent_%s_%s_%u_%u_Ping", v51, L"4.0.30319.0", v31, v36);
      if ( RandomString )
        goto LABEL_37;
      SetLastError(0);
      EventW = CreateEventW(v2, 1, 0, Name);
      *((_QWORD *)this + 24) = EventW;
      if ( EventW )
      {
        if ( GetLastError() != 183 )
        {
          SetLastError(0);
          v10 = CreateEventW(v2, 1, 0, v56);
          *((_QWORD *)this + 25) = v10;
          if ( v10 )
          {
            if ( GetLastError() != 183 )
            {
              v11 = &Names::s_wszInstallDirectory;
              if ( Names::s_wszInstallDirectory == 92 && word_18008F8A2 == 92 && word_18008F8A4 == 63 )
              {
                v12 = qword_18008F8A8;
                if ( word_18008F8A6 != 92 )
                  v12 = (__int64 *)&Names::s_wszInstallDirectory;
                v11 = (const WCHAR *)v12;
              }
              v13 = lstrlenW(v11);
              v14 = lstrlenW(L"aspnet_wp.exe") + v13;
              if ( (unsigned int)(v14 + lstrlenW(L"\\") + 1) >= 0x105 )
              {
LABEL_36:
                RandomString = -2147467259;
                goto LABEL_37;
              }
              v17 = 261;
              v18 = (char *)v11 - (char *)v52;
              v19 = v52;
              do
              {
                if ( v17 == -2147483385 )
                  break;
                v20 = *(unsigned __int16 *)((char *)v19 + v18);
                if ( !v20 )
                  break;
                *v19++ = v20;
                --v17;
              }
              while ( v17 );
              v21 = v19 - 1;
              if ( v17 )
                v21 = v19;
              *v21 = 0;
              RandomString = v17 == 0 ? 0x8007007A : 0;
              if ( !v17 )
                goto LABEL_37;
              RandomString = StringCchCatW(v52, 0x105u, L"\\");
              if ( RandomString )
                goto LABEL_37;
              RandomString = StringCchCatW(v52, 0x105u, L"aspnet_wp.exe");
              if ( RandomString )
                goto LABEL_37;
              LODWORD(v37) = RegForNumSyncPipes;
              LODWORD(v32) = *((_DWORD *)this + 84);
              LODWORD(v27) = CurrentProcessId;
              RandomString = StringCchPrintfW(
                               v57,
                               0x3FFu,
                               L"%s %u %u %d %u %u %u %s",
                               v52,
                               v27,
                               v32,
                               v37,
                               g_dwRPCAuthLevel,
                               g_dwRPCImperLevel,
                               v4,
                               v51);
              if ( RandomString )
                goto LABEL_37;
              v49.cb = 104;
              if ( (unsigned int)CProcessEntry::LaunchWP(this, v52, v57, v7, &v49, v2, Environment) )
              {
                memset_0(&v49, 0, sizeof(v49));
                v49.cb = 104;
                v49.lpDesktop = (LPWSTR)&Class;
                LODWORD(v41) = v4;
                v22 = RegForNumSyncPipes;
                LODWORD(v40) = g_dwRPCImperLevel;
                LODWORD(v39) = g_dwRPCAuthLevel;
                LODWORD(v38) = RegForNumSyncPipes;
                LODWORD(v33) = *((_DWORD *)this + 84);
                LODWORD(v28) = CurrentProcessId;
                RandomString = StringCchPrintfW(
                                 v57,
                                 0x3FFu,
                                 L"%s %u %u %d %u %u %u %s",
                                 v52,
                                 v28,
                                 v33,
                                 v38,
                                 v39,
                                 v40,
                                 v41,
                                 v51);
                if ( RandomString )
                  goto LABEL_37;
                RandomString = CProcessEntry::LaunchWP(this, v52, v57, v7, &v49, v2, Environment);
                if ( RandomString )
                  goto LABEL_37;
              }
              else
              {
                v22 = RegForNumSyncPipes;
              }
              TimeClass::SnapCurrentTime((CProcessEntry *)((char *)this + 296));
              TimeClass::SnapCurrentTime((CProcessEntry *)((char *)this + 312));
              *((_DWORD *)this + 89) = *((_DWORD *)this + 84);
              GetSystemTimeAsFileTime((LPFILETIME)this + 47);
              CHistoryTable::AddEntry((CProcessEntry *)((char *)this + 352));
              RandomString = CAsyncPipe::StartRead((CProcessEntry *)((char *)this + 80), 0);
              if ( !RandomString )
              {
                RandomString = 0;
                v23 = 0;
                if ( v22 > 0 )
                {
                  while ( 1 )
                  {
                    RandomString = CAckReceiver::StartRead((CProcessEntry *)((char *)this + 16), 0, v23);
                    if ( RandomString )
                      goto LABEL_37;
                    if ( ++v23 >= v22 )
                    {
                      RandomString = 0;
                      break;
                    }
                  }
                }
                if ( WaitForSingleObject(*(HANDLE *)this, 0) == 258 )
                {
                  *((_DWORD *)this + 82) = 1;
                  *((_DWORD *)this + 101) = 1;
                  PerfIncrementGlobalCounter(6u);
                  v24 = *(void **)this;
                  TokenHandle = 0;
                  v25 = OpenProcessToken(v24, 0xF01FFu, &TokenHandle);
                  if ( !v25 )
                    GetLastWin32Error();
                  v26 = TokenHandle;
                  if ( TokenHandle && v25 )
                  {
                    RandomString = 0;
                    if ( v7 )
                    {
                      if ( !SetKernelObjectSecurity(TokenHandle, 4u, pSecurityDescriptor) )
                        GetLastWin32Error();
                      v26 = TokenHandle;
                    }
                    if ( !DuplicateToken(v26, SecurityImpersonation, (PHANDLE)this + 1) )
                    {
                      GetLastWin32Error();
                      *((_QWORD *)this + 1) = -1;
                    }
                    CloseHandle(TokenHandle);
                  }
                  goto LABEL_40;
                }
                goto LABEL_36;
              }
LABEL_37:
              if ( g_iLogLevel )
                XspLogEvent(0xC000043C);
              CProcessEntry::Close(this, 1);
              goto LABEL_40;
            }
          }
        }
      }
    }
    goto LABEL_10;
  }
  RandomString = CProcessEntry::CreateDACL(&pDacl, WorkerProcessToken);
  if ( RandomString )
    goto LABEL_37;
  if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0) )
  {
    v46[0] = 24;
    v46[1] = pSecurityDescriptor;
    v46[2] = 0;
    v2 = (struct _SECURITY_ATTRIBUTES *)v46;
    v8 = CreateEnvironmentBlock_0(&Environment, v7, 0);
    Environment = (LPVOID)(-(__int64)v8 & (unsigned __int64)Environment);
    if ( !Environment )
      GetLastWin32Error();
    goto LABEL_18;
  }
LABEL_10:
  RandomString = GetLastWin32Error();
  if ( RandomString )
    goto LABEL_37;
LABEL_40:
  v15 = (void *)*((_QWORD *)this + 23);
  if ( v15 )
    SetEvent(v15);
  if ( Environment )
    DestroyEnvironmentBlock_0(Environment);
  MemFree(pDacl);
  return RandomString;
}

```

## disassembly

```asm
0x18001dc88  mov     rax, rsp
0x18001dc8b  mov     [rax+10h], rbx
0x18001dc8f  mov     [rax+18h], rsi
0x18001dc93  mov     [rax+20h], rdi
0x18001dc97  push    rbp
0x18001dc98  push    r12
0x18001dc9a  push    r13
0x18001dc9c  push    r14
0x18001dc9e  push    r15
0x18001dca0  lea     rbp, [rax-1328h]
0x18001dca7  mov     eax, 1400h
0x18001dcac  call    _alloca_probe
0x18001dcb1  sub     rsp, rax
0x18001dcb4  mov     rax, cs:__security_cookie
0x18001dcbb  xor     rax, rsp
0x18001dcbe  mov     [rbp+1320h+var_30], rax
0x18001dcc5  cmp     cs:?g_fShuttingDown@@3HA, 1; int g_fShuttingDown
0x18001dccc  mov     rdi, rcx
0x18001dccf  jz      loc_18001E486
0x18001dcd5  xor     ebx, ebx
0x18001dcd7  cmp     [rcx+0A8h], rbx
0x18001dcde  jz      loc_18001E486
0x18001dce4  call    cs:__imp_GetCurrentProcessId
0x18001dcea  mov     r15d, ebx
0x18001dced  mov     [rsp+1420h+pDacl], rbx
0x18001dcf2  mov     r13d, eax
0x18001dcf5  call    ?ReadRegForNumSyncPipes@CProcessEntry@@CAHXZ; CProcessEntry::ReadRegForNumSyncPipes(void)
0x18001dcfa  mov     r12d, ebx
0x18001dcfd  mov     [rsp+1420h+Environment], rbx
0x18001dd02  mov     ebx, 20Ah
0x18001dd07  mov     dword ptr [rsp+1420h+var_13C0], eax
0x18001dd0b  mov     r8d, ebx; Size
0x18001dd0e  lea     rcx, [rbp+1320h+var_E60]; void *
0x18001dd15  xor     edx, edx; Val
0x18001dd17  mov     esi, eax
0x18001dd19  call    memset_0
0x18001dd1e  mov     r8d, ebx; Size
0x18001dd21  lea     rcx, [rbp+1320h+Buffer]; void *
0x18001dd28  xor     edx, edx; Val
0x18001dd2a  call    memset_0
0x18001dd2f  xor     edx, edx; Val
0x18001dd31  lea     rcx, [rbp+1320h+var_830]; void *
0x18001dd38  mov     r8d, 800h; Size
0x18001dd3e  call    memset_0
0x18001dd43  mov     r8d, ebx; Size
0x18001dd46  lea     rcx, [rbp+1320h+Name]; void *
0x18001dd4d  xor     edx, edx; Val
0x18001dd4f  call    memset_0
0x18001dd54  mov     r8d, ebx; Size
0x18001dd57  lea     rcx, [rbp+1320h+var_A40]; void *
0x18001dd5e  xor     edx, edx; Val
0x18001dd60  call    memset_0
0x18001dd65  mov     r8d, ebx; Size
0x18001dd68  lea     rcx, [rbp+1320h+var_1280]; void *
0x18001dd6f  xor     edx, edx; Val
0x18001dd71  call    memset_0
0x18001dd76  xor     edx, edx; Val
0x18001dd78  lea     r8d, [r15+40h]; Size
0x18001dd7c  lea     rcx, [rbp+1320h+var_12C0]; void *
0x18001dd80  call    memset_0
0x18001dd85  xor     edx, edx; Val
0x18001dd87  lea     r8d, [r15+68h]; Size
0x18001dd8b  lea     rcx, [rbp+1320h+var_1360]; void *
0x18001dd8f  call    memset_0
0x18001dd94  xor     eax, eax
0x18001dd96  lea     rcx, [rbp+1320h+var_12C0]; unsigned __int16 *
0x18001dd9a  xorps   xmm0, xmm0
0x18001dd9d  mov     [rbp+1320h+var_1368], rax
0x18001dda1  movups  [rbp+1320h+pSecurityDescriptor], xmm0
0x18001dda5  lea     edx, [rax+1Fh]; int
0x18001dda8  movups  [rbp+1320h+var_1378], xmm0
0x18001ddac  call    ?GenerateRandomString@@YAJPEAGH@Z; GenerateRandomString(ushort *,int)
0x18001ddb1  mov     ebx, eax
0x18001ddb3  test    eax, eax
0x18001ddb5  jnz     loc_18001E0E9
0x18001ddbb  cmp     dword ptr [rdi+148h], 1
0x18001ddc2  jz      loc_18001E114
0x18001ddc8  call    ?GetUseCPUAffinity@CProcessTableManager@@SAHXZ; CProcessTableManager::GetUseCPUAffinity(void)
0x18001ddcd  xor     ebx, ebx
0x18001ddcf  test    eax, eax
0x18001ddd1  jz      short loc_18001DDED
0x18001ddd3  mov     r12d, [rdi+14Ch]
0x18001ddda  test    r12d, r12d
0x18001dddd  jz      short loc_18001DDED
0x18001dddf  lea     rcx, [rbp+1320h+SystemInfo]; lpSystemInfo
0x18001dde3  call    cs:__imp_GetSystemInfo
0x18001dde9  and     r12d, dword ptr [rbp+1320h+SystemInfo.dwActiveProcessorMask]
0x18001dded  call    ?GetWorkerProcessToken@CProcessTableManager@@SAPEAXXZ; CProcessTableManager::GetWorkerProcessToken(void)
0x18001ddf2  mov     r14, rax
0x18001ddf5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ddf9  jnz     short loc_18001DE1D
0x18001ddfb  xor     edx, edx
0x18001ddfd  mov     ecx, 0C00003EFh; dwEventID
0x18001de02  call    XspLogEvent
0x18001de07  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001de0c  xor     esi, esi
0x18001de0e  mov     ebx, eax
0x18001de10  test    eax, eax
0x18001de12  jz      loc_18001E114
0x18001de18  jmp     loc_18001E0EB
0x18001de1d  test    r14, r14
0x18001de20  jz      short loc_18001DE9E
0x18001de22  mov     rdx, r14; TokenHandle
0x18001de25  lea     rcx, [rsp+1420h+pDacl]; struct _ACL **
0x18001de2a  call    ?CreateDACL@CProcessEntry@@CAJPEAPEAU_ACL@@PEAX@Z; CProcessEntry::CreateDACL(_ACL * *,void *)
0x18001de2f  mov     ebx, eax
0x18001de31  test    eax, eax
0x18001de33  jnz     loc_18001E0E9
0x18001de39  lea     edx, [rax+1]; dwRevision
0x18001de3c  lea     rcx, [rbp+1320h+pSecurityDescriptor]; pSecurityDescriptor
0x18001de40  call    cs:__imp_InitializeSecurityDescriptor
0x18001de46  xor     ebx, ebx
0x18001de48  test    eax, eax
0x18001de4a  jz      short loc_18001DE07
0x18001de4c  mov     r8, [rsp+1420h+pDacl]; pDacl
0x18001de51  lea     edx, [rbx+1]; bDaclPresent
0x18001de54  xor     r9d, r9d; bDaclDefaulted
0x18001de57  lea     rcx, [rbp+1320h+pSecurityDescriptor]; pSecurityDescriptor
0x18001de5b  call    cs:__imp_SetSecurityDescriptorDacl
0x18001de61  test    eax, eax
0x18001de63  jz      short loc_18001DE07
0x18001de65  lea     rax, [rbp+1320h+pSecurityDescriptor]
0x18001de69  mov     [rbp+1320h+var_13A0], 18h
0x18001de71  xor     r8d, r8d; bInherit
0x18001de74  mov     [rbp+1320h+var_1398], rax
0x18001de78  mov     rdx, r14; hToken
0x18001de7b  mov     [rbp+1320h+var_1390], rbx
0x18001de7f  lea     rcx, [rsp+1420h+Environment]; lpEnvironment
0x18001de84  lea     r15, [rbp+1320h+var_13A0]
0x18001de88  call    CreateEnvironmentBlock_0
0x18001de8d  neg     eax
0x18001de8f  sbb     rcx, rcx
0x18001de92  and     [rsp+1420h+Environment], rcx
0x18001de97  jnz     short loc_18001DE9E
0x18001de99  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001de9e  cmp     [rdi+0B8h], rbx
0x18001dea5  jz      loc_18001DE07
0x18001deab  mov     eax, [rdi+150h]
0x18001deb1  lea     r9, [rbp+1320h+var_12C0]
0x18001deb5  mov     dword ptr [rsp+1420h+var_13F0], eax
0x18001deb9  lea     r8, aPipeAspNetpmsy; "\\\\.\\pipe\\ASP.NETPMSyncPipe_%s_%s_%u"...
0x18001dec0  lea     rax, a40303190; "4.0.30319.0"
0x18001dec7  mov     dword ptr [rsp+1420h+var_13F8], r13d
0x18001decc  mov     edx, 104h; unsigned __int64
0x18001ded1  mov     [rsp+1420h+var_1400], rax
0x18001ded6  lea     rcx, [rbp+1320h+Buffer]; Buffer
0x18001dedd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001dee2  mov     ebx, eax
0x18001dee4  test    eax, eax
0x18001dee6  jnz     loc_18001E0E9
0x18001deec  lea     rcx, [rdi+10h]; this
0x18001def0  mov     dword ptr [rsp+1420h+var_1400], esi; int
0x18001def4  mov     r9, r15; struct _SECURITY_ATTRIBUTES *
0x18001def7  lea     r8, [rbp+1320h+Buffer]; unsigned __int16 *
0x18001defe  mov     rdx, rdi; struct CProcessEntry *
0x18001df01  call    ?Init@CAckReceiver@@QEAAJPEAVCProcessEntry@@PEBGPEAU_SECURITY_ATTRIBUTES@@H@Z; CAckReceiver::Init(CProcessEntry *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x18001df06  xor     esi, esi
0x18001df08  mov     ebx, eax
0x18001df0a  test    eax, eax
0x18001df0c  jnz     loc_18001E0EB
0x18001df12  mov     eax, [rdi+150h]
0x18001df18  lea     r9, [rbp+1320h+var_12C0]
0x18001df1c  mov     dword ptr [rsp+1420h+var_13F0], eax
0x18001df20  lea     r8, aPipeAspNetpmas; "\\\\.\\pipe\\ASP.NETPMAsyncPipe_%s_%s_%"...
0x18001df27  lea     rax, a40303190; "4.0.30319.0"
0x18001df2e  mov     dword ptr [rsp+1420h+var_13F8], r13d
0x18001df33  mov     edx, 104h; unsigned __int64
0x18001df38  mov     [rsp+1420h+var_1400], rax
0x18001df3d  lea     rcx, [rbp+1320h+var_E60]; Buffer
0x18001df44  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001df49  mov     ebx, eax
0x18001df4b  test    eax, eax
0x18001df4d  jnz     loc_18001E0EB
0x18001df53  lea     rcx, [rdi+50h]; this
0x18001df57  mov     r9, r15; struct _SECURITY_ATTRIBUTES *
0x18001df5a  lea     r8, [rbp+1320h+var_E60]; unsigned __int16 *
0x18001df61  mov     rdx, rdi; struct CProcessEntry *
0x18001df64  call    ?Init@CAsyncPipe@@QEAAJPEAVCProcessEntry@@PEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CAsyncPipe::Init(CProcessEntry *,ushort const *,_SECURITY_ATTRIBUTES *)
0x18001df69  mov     ebx, eax
0x18001df6b  test    eax, eax
0x18001df6d  jnz     loc_18001E0EB
0x18001df73  mov     eax, [rdi+150h]
0x18001df79  lea     r9, [rbp+1320h+var_12C0]
0x18001df7d  mov     dword ptr [rsp+1420h+var_13F0], eax
0x18001df81  lea     r8, aAspNetpmeventS; "ASP.NETPMEvent_%s_%s_%u_%u"
0x18001df88  lea     rax, a40303190; "4.0.30319.0"
0x18001df8f  mov     dword ptr [rsp+1420h+var_13F8], r13d
0x18001df94  mov     edx, 104h; unsigned __int64
0x18001df99  mov     [rsp+1420h+var_1400], rax
0x18001df9e  lea     rcx, [rbp+1320h+Name]; Buffer
0x18001dfa5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001dfaa  mov     ebx, eax
0x18001dfac  test    eax, eax
0x18001dfae  jnz     loc_18001E0EB
0x18001dfb4  mov     eax, [rdi+150h]
0x18001dfba  lea     r9, [rbp+1320h+var_12C0]
0x18001dfbe  mov     dword ptr [rsp+1420h+var_13F0], eax
0x18001dfc2  lea     r8, aAspNetpmeventS_0; "ASP.NETPMEvent_%s_%s_%u_%u_Ping"
0x18001dfc9  lea     rax, a40303190; "4.0.30319.0"
0x18001dfd0  mov     dword ptr [rsp+1420h+var_13F8], r13d
0x18001dfd5  mov     edx, 104h; unsigned __int64
0x18001dfda  mov     [rsp+1420h+var_1400], rax
0x18001dfdf  lea     rcx, [rbp+1320h+var_A40]; Buffer
0x18001dfe6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001dfeb  mov     ebx, eax
0x18001dfed  test    eax, eax
0x18001dfef  jnz     loc_18001E0EB
0x18001dff5  xor     ecx, ecx; dwErrCode
0x18001dff7  call    cs:__imp_SetLastError
0x18001dffd  lea     r9, [rbp+1320h+Name]; lpName
0x18001e004  xor     r8d, r8d; bInitialState
0x18001e007  lea     edx, [rsi+1]; bManualReset
0x18001e00a  mov     rcx, r15; lpEventAttributes
0x18001e00d  call    cs:__imp_CreateEventW
0x18001e013  mov     [rdi+0C0h], rax
0x18001e01a  test    rax, rax
0x18001e01d  jz      loc_18001DE07
0x18001e023  call    cs:__imp_GetLastError
0x18001e029  mov     esi, 0B7h
0x18001e02e  cmp     eax, esi
0x18001e030  jz      loc_18001DE07
0x18001e036  xor     ecx, ecx; dwErrCode
0x18001e038  call    cs:__imp_SetLastError
0x18001e03e  lea     r9, [rbp+1320h+var_A40]; lpName
0x18001e045  xor     r8d, r8d; bInitialState
0x18001e048  lea     edx, [rbx+1]; bManualReset
0x18001e04b  mov     rcx, r15; lpEventAttributes
0x18001e04e  call    cs:__imp_CreateEventW
0x18001e054  mov     [rdi+0C8h], rax
0x18001e05b  test    rax, rax
0x18001e05e  jz      loc_18001DE07
0x18001e064  call    cs:__imp_GetLastError
0x18001e06a  cmp     eax, esi
0x18001e06c  jz      loc_18001DE07
0x18001e072  cmp     cs:?s_wszInstallDirectory@Names@@0PAGA, 5Ch ; '\'; ushort near * Names::s_wszInstallDirectory
0x18001e07a  lea     rsi, ?s_wszInstallDirectory@Names@@0PAGA; ushort near * Names::s_wszInstallDirectory
0x18001e081  jnz     short loc_18001E0AD
0x18001e083  cmp     cs:word_18008F8A2, 5Ch ; '\'
0x18001e08b  jnz     short loc_18001E0AD
0x18001e08d  cmp     cs:word_18008F8A4, 3Fh ; '?'
0x18001e095  jnz     short loc_18001E0AD
0x18001e097  cmp     cs:word_18008F8A6, 5Ch ; '\'
0x18001e09f  lea     rax, qword_18008F8A8
0x18001e0a6  cmovnz  rax, rsi
0x18001e0aa  mov     rsi, rax
0x18001e0ad  mov     rcx, rsi; lpString
0x18001e0b0  call    cs:__imp_lstrlenW
0x18001e0b6  lea     rcx, aAspnetWpExe; "aspnet_wp.exe"
0x18001e0bd  mov     ebx, eax
0x18001e0bf  call    cs:__imp_lstrlenW
0x18001e0c5  lea     rcx, SubBlock; "\\"
0x18001e0cc  add     ebx, eax
0x18001e0ce  call    cs:__imp_lstrlenW
0x18001e0d4  mov     r9d, 105h
0x18001e0da  lea     ecx, [rax+1]
0x18001e0dd  add     ecx, ebx
0x18001e0df  cmp     ecx, r9d
0x18001e0e2  jb      short loc_18001E146
0x18001e0e4  mov     ebx, 80004005h
0x18001e0e9  xor     esi, esi
0x18001e0eb  cmp     cs:?g_iLogLevel@@3HA, esi; int g_iLogLevel
0x18001e0f1  jz      short loc_18001E107
0x18001e0f3  mov     r8d, ebx
0x18001e0f6  lea     rdx, asc_18006D700; "%X"
0x18001e0fd  mov     ecx, 0C000043Ch; dwEventID
0x18001e102  call    XspLogEvent
0x18001e107  mov     edx, 1; int
0x18001e10c  mov     rcx, rdi; this
0x18001e10f  call    ?Close@CProcessEntry@@QEAAXH@Z; CProcessEntry::Close(int)
0x18001e114  mov     rcx, [rdi+0B8h]; hEvent
0x18001e11b  test    rcx, rcx
0x18001e11e  jz      short loc_18001E126
0x18001e120  call    cs:__imp_SetEvent
0x18001e126  mov     rcx, [rsp+1420h+Environment]; lpEnvironment
0x18001e12b  test    rcx, rcx
0x18001e12e  jz      short loc_18001E135
0x18001e130  call    DestroyEnvironmentBlock_0
0x18001e135  mov     rcx, [rsp+1420h+pDacl]; lpMem
0x18001e13a  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001e13f  mov     eax, ebx
0x18001e141  jmp     loc_18001E48B
0x18001e146  lea     rax, [rbp+1320h+var_1280]
0x18001e14d  mov     rdx, r9
0x18001e150  sub     rsi, rax
0x18001e153  lea     rcx, [rbp+1320h+var_1280]
0x18001e15a  xor     ebx, ebx
0x18001e15c  lea     rax, [rdx+7FFFFEF9h]
0x18001e163  test    rax, rax
0x18001e166  jz      short loc_18001E17E
0x18001e168  movzx   eax, word ptr [rsi+rcx]
0x18001e16c  test    ax, ax
0x18001e16f  jz      short loc_18001E17E
0x18001e171  mov     [rcx], ax
0x18001e174  add     rcx, 2
0x18001e178  sub     rdx, 1
0x18001e17c  jnz     short loc_18001E15C
0x18001e17e  test    rdx, rdx
0x18001e181  lea     rax, [rcx-2]
0x18001e185  cmovnz  rax, rcx
0x18001e189  mov     [rax], bx
  ... truncated ...
```
