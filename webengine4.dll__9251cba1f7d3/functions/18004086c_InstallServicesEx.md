# InstallServicesEx

- ea: `0x18004086c`
- end: `0x180040f61`
- name: `InstallServicesEx`
- size: `1781`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18003c1e8`
- `0x180040860`

## callees

- `0x180007824`
- `0x1800248e4`
- `0x180026bfc`
- `0x180036aa0`
- `0x180039b1c`
- `0x18003a558`
- `0x18003abe4`
- `0x18003ba0c`
- `0x1800400a8`
- `0x18004086c`
- `0x18004d030`
- `0x18004d350`
- `0x18004d754`
- `0x1800653b4`
- `0x180065b60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180040bf9`
- `KERNEL32!GetLastError` at `0x180040bf9`
- `KERNEL32!lstrlenW` at `0x180040936`
- `KERNEL32!lstrlenW` at `0x180040936`
- `KERNEL32!Sleep` at `0x180040b8d`
- `KERNEL32!Sleep` at `0x180040c16`
- `KERNEL32!Sleep` at `0x180040b8d`
- `KERNEL32!Sleep` at `0x180040c16`
- `ADVAPI32!ChangeServiceConfigW` at `0x180040d8e`
- `ADVAPI32!ChangeServiceConfigW` at `0x180040e20`
- `ADVAPI32!ChangeServiceConfigW` at `0x180040d8e`
- `ADVAPI32!ChangeServiceConfigW` at `0x180040e20`
- `ADVAPI32!CloseServiceHandle` at `0x180040e5e`
- `ADVAPI32!CloseServiceHandle` at `0x180040f03`
- `ADVAPI32!CloseServiceHandle` at `0x180040f1f`
- `ADVAPI32!CloseServiceHandle` at `0x180040e5e`
- `ADVAPI32!CloseServiceHandle` at `0x180040f03`
- `ADVAPI32!CloseServiceHandle` at `0x180040f1f`
- `ADVAPI32!LockServiceDatabase` at `0x180040c1f`
- `ADVAPI32!LockServiceDatabase` at `0x180040c1f`
- `ADVAPI32!OpenSCManagerW` at `0x180040a4a`
- `ADVAPI32!OpenSCManagerW` at `0x180040a4a`
- `ADVAPI32!OpenServiceW` at `0x180040c76`
- `ADVAPI32!OpenServiceW` at `0x180040c76`
- `ADVAPI32!UnlockServiceDatabase` at `0x180040e6e`
- `ADVAPI32!UnlockServiceDatabase` at `0x180040f11`
- `ADVAPI32!UnlockServiceDatabase` at `0x180040e6e`
- `ADVAPI32!UnlockServiceDatabase` at `0x180040f11`

## string_xrefs

- `0x180040a2b`: `Connecting to Service Manager`
- `0x180040a5f`: `Connecting to Service Manager`
- `0x180040a32`: `OpenSCManager`
- `0x180040a6e`: `OpenSCManager`
- `0x180040c52`: `Opening Service handle`
- `0x180040c8b`: `Opening Service handle`
- `0x180040c59`: `OpenService`
- `0x180040c9a`: `OpenService`
- `0x180040d25`: `ChangeServiceConfig`
- `0x180040db2`: `ChangeServiceConfig`
- `0x180040ddb`: `ChangeServiceConfig`
- `0x180040e40`: `ChangeServiceConfig`
- `0x1800408b2`: `Install all ASP.NET Services`
- `0x180040ede`: `Install all ASP.NET Services`
- `0x1800408c1`: `InstallServicesEx`
- `0x180040eed`: `InstallServicesEx`
- `0x180040ab9`: `Keep installing service because it is already installed`
- `0x180040ad3`: `Keep installing service because it is already installed`
- `0x180040af1`: `Start installing service`
- `0x180040b10`: `Start installing service`
- `0x180040bde`: `Locking service database`
- `0x180040c2d`: `Locking service database`
- `0x180040ebf`: `Locking service database`
- `0x180040be8`: `LockServiceDatabase`
- `0x180040c3c`: `LockServiceDatabase`
- `0x180040eb0`: `LockServiceDatabase`
- `0x180040d16`: `Changing service account and password`
- `0x180040da8`: `Changing service account and password`
- `0x180040dcc`: `Disabling the service`
- `0x180040e31`: `Disabling the service`

## pseudocode

```c
__int64 __fastcall InstallServicesEx(int a1)
{
  int v1; // r13d
  int v2; // r12d
  SC_HANDLE v3; // r15
  SC_HANDLE v4; // rsi
  void *v5; // r14
  __int64 v6; // rdi
  unsigned int ServiceAccCredentials; // ebx
  __int64 v8; // rdx
  unsigned __int16 *v9; // rcx
  unsigned __int16 v10; // ax
  unsigned __int16 *v11; // rax
  wchar_t *v12; // rcx
  wchar_t v13; // ax
  wchar_t *v14; // rax
  char **v15; // rdi
  int v16; // esi
  signed int LastError; // eax
  void *v18; // r12
  struct _SERVICE_FAILURE_ACTIONSW *v19; // r9
  unsigned __int16 *lpPassword; // rdx
  wchar_t *lpServiceStartName; // rax
  BOOL v22; // r12d
  unsigned int v24[2]; // [rsp+68h] [rbp-A0h] BYREF
  void *lpMem; // [rsp+70h] [rbp-98h] BYREF
  int v26[2]; // [rsp+78h] [rbp-90h] BYREF
  struct ServiceSetupInfo *v27; // [rsp+80h] [rbp-88h]
  int v28; // [rsp+88h] [rbp-80h] BYREF
  __int128 v29; // [rsp+90h] [rbp-78h]
  int v30; // [rsp+A0h] [rbp-68h]
  _QWORD *v31; // [rsp+A8h] [rbp-60h]
  _QWORD v32[3]; // [rsp+B0h] [rbp-58h] BYREF
  wchar_t Str[112]; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int16 v34[112]; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int16 v35[104]; // [rsp+288h] [rbp+180h] BYREF

  v1 = 0;
  v26[1] = a1;
  v2 = a1;
  lpMem = 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  CSetupLogging::Log(1, "InstallServicesEx", 0, "Install all ASP.NET Services", 0);
  XspSecureZeroMemory(v35, 0xD0u);
  XspSecureZeroMemory(Str, 0xD4u);
  v6 = 106;
  ServiceAccCredentials = CRegAccount::GetServiceAccCredentials(Str, 0x6Au, v35, 0x68u);
  if ( !ServiceAccCredentials )
  {
    if ( wcschr_0(Str, 0x5Cu) || (unsigned int)lstrlenW(Str) >= 0x68 )
      goto LABEL_19;
    v8 = 106;
    v9 = v34;
    do
    {
      if ( v8 == -2147483540 )
        break;
      v10 = *(unsigned __int16 *)((char *)v9 + (char *)L".\\" - (char *)v34);
      if ( !v10 )
        break;
      *v9++ = v10;
      --v8;
    }
    while ( v8 );
    v11 = v9 - 1;
    if ( v8 )
      v11 = v9;
    *v11 = 0;
    ServiceAccCredentials = v8 == 0 ? 0x8007007A : 0;
    if ( v8 )
    {
      ServiceAccCredentials = StringCchCatW(v34, 0x6Au, Str);
      if ( !ServiceAccCredentials )
      {
        v12 = Str;
        do
        {
          if ( v6 == -2147483540 )
            break;
          v13 = v12[112];
          if ( !v13 )
            break;
          *v12++ = v13;
          --v6;
        }
        while ( v6 );
        v14 = v12 - 1;
        if ( v6 )
          v14 = v12;
        *v14 = 0;
        ServiceAccCredentials = v6 == 0 ? 0x8007007A : 0;
        if ( v6 )
        {
LABEL_19:
          CSetupLogging::Log(1, "OpenSCManager", 0, "Connecting to Service Manager", 0);
          v3 = OpenSCManagerW(0, 0, 9u);
          if ( !v3 )
            ServiceAccCredentials = GetLastWin32Error();
          CSetupLogging::Log(ServiceAccCredentials, "OpenSCManager", 0, "Connecting to Service Manager", 0);
          if ( !ServiceAccCredentials )
          {
            v15 = &off_18008ED90;
            while ( 1 )
            {
              v24[1] = -1;
              v24[0] = 0;
              if ( !v2 )
                break;
              ServiceAccCredentials = IsCurrentVersionServiceInstalled(v3, (LPCWSTR)*(v15 - 1), v26);
              if ( ServiceAccCredentials || !v26[0] )
                break;
              CSetupLogging::Log(1, "Keep installing service because it is already installed", 0, *v15, 0);
              CSetupLogging::Log(0, "Keep installing service because it is already installed", 0, *v15, 0);
LABEL_55:
              ++v1;
              v15 += 9;
              if ( v1 )
                goto LABEL_56;
            }
            CSetupLogging::Log(1, "Start installing service", 0, *v15, 0);
            CSetupLogging::Log(0, "Start installing service", 0, *v15, 0);
            (**(void (__fastcall ***)(_QWORD))*(v15 - 4))(*(v15 - 4));
            v27 = (struct ServiceSetupInfo *)(&g_rgServiceSetupInfo + 9 * v1);
            ReadServiceSettings(v3, v27, &v24[1], (struct _SERVICE_FAILURE_ACTIONSW **)&lpMem, (int *)v24);
            if ( !v24[0] )
            {
              InstallInfSections(g_DllInstance);
              Sleep(0x3E8u);
            }
            ServiceAccCredentials = InstallInfSections(g_DllInstance);
            if ( ServiceAccCredentials )
            {
LABEL_56:
              v4 = 0;
              v5 = 0;
              goto LABEL_62;
            }
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*(v15 - 4) + 8LL))(*(v15 - 4));
            if ( v15[2] )
            {
              InstallServicePerfCounter((struct ServiceSetupInfo *)(&g_rgServiceSetupInfo + 9 * v1));
              ServiceAccCredentials = 0;
            }
            v16 = 60;
            CSetupLogging::Log(1, "LockServiceDatabase", 0, "Locking service database", 0);
            while ( 1 )
            {
              v5 = LockServiceDatabase(v3);
              if ( v5 )
                break;
              LastError = GetLastError();
              if ( LastError != 1055 )
              {
                ServiceAccCredentials = (unsigned __int16)LastError | 0x80070000;
                if ( LastError <= 0 )
                  ServiceAccCredentials = LastError;
                goto LABEL_60;
              }
              if ( !--v16 )
              {
                ServiceAccCredentials = -2147023843;
LABEL_60:
                CSetupLogging::Log(ServiceAccCredentials, "LockServiceDatabase", 0, "Locking service database", 0);
                v4 = 0;
                goto LABEL_62;
              }
              Sleep(0x3E8u);
            }
            CSetupLogging::Log(0, "LockServiceDatabase", 0, "Locking service database", 0);
            CSetupLogging::Log(1, "OpenService", 0, "Opening Service handle", 0);
            v4 = OpenServiceW(v3, (LPCWSTR)*(v15 - 1), 0x12u);
            if ( !v4 )
              ServiceAccCredentials = GetLastWin32Error();
            CSetupLogging::Log(ServiceAccCredentials, "OpenService", 0, "Opening Service handle", 0);
            if ( !ServiceAccCredentials )
            {
              v18 = lpMem;
              ServiceAccCredentials = 0;
              if ( !lpMem )
              {
                v28 = 86400;
                v30 = 3;
                v29 = 0;
                v31 = v32;
                v32[0] = 1;
                v32[1] = 1;
                v32[2] = 0;
              }
              v19 = (struct _SERVICE_FAILURE_ACTIONSW *)&v28;
              if ( lpMem )
                v19 = (struct _SERVICE_FAILURE_ACTIONSW *)lpMem;
              WriteServiceSettings(v4, v27, v24[1], v19);
              MemFree(v18);
              lpMem = 0;
              CSetupLogging::Log(1, "ChangeServiceConfig", 0, "Changing service account and password", 0);
              lpPassword = v35;
              lpServiceStartName = Str;
              if ( *((_DWORD *)v15 + 8) )
              {
                lpPassword = 0;
                lpServiceStartName = (wchar_t *)L"LocalSystem";
              }
              v22 = ChangeServiceConfigW(
                      v4,
                      0x10u,
                      0xFFFFFFFF,
                      0xFFFFFFFF,
                      0,
                      0,
                      0,
                      0,
                      lpServiceStartName,
                      lpPassword,
                      0);
              if ( !v22 )
                ServiceAccCredentials = GetLastWin32Error();
              CSetupLogging::Log(
                ServiceAccCredentials,
                "ChangeServiceConfig",
                0,
                "Changing service account and password",
                0);
              if ( v22 )
                goto LABEL_71;
              CSetupLogging::Log(1, "ChangeServiceConfig", 0, "Disabling the service", 0);
              if ( !ChangeServiceConfigW(v4, 0x10u, 4u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
                ServiceAccCredentials = GetLastWin32Error();
              CSetupLogging::Log(ServiceAccCredentials, "ChangeServiceConfig", 0, "Disabling the service", 0);
              if ( !ServiceAccCredentials )
              {
LABEL_71:
                if ( CloseServiceHandle(v4) )
                {
                  v4 = 0;
                  if ( UnlockServiceDatabase(v5) )
                  {
                    v2 = v26[1];
                    goto LABEL_55;
                  }
                }
                ServiceAccCredentials = GetLastWin32Error();
              }
            }
          }
        }
      }
    }
  }
LABEL_62:
  CSetupLogging::Log(ServiceAccCredentials, "InstallServicesEx", 0, "Install all ASP.NET Services", 0);
  if ( v4 )
    CloseServiceHandle(v4);
  if ( v5 )
    UnlockServiceDatabase(v5);
  if ( v3 )
    CloseServiceHandle(v3);
  MemFree(lpMem);
  return ServiceAccCredentials;
}

```

## disassembly

```asm
0x18004086c  mov     rax, rsp
0x18004086f  mov     [rax+8], rbx
0x180040873  mov     [rax+10h], rsi
0x180040877  mov     [rax+18h], rdi
0x18004087b  push    rbp
0x18004087c  push    r12
0x18004087e  push    r13
0x180040880  push    r14
0x180040882  push    r15
0x180040884  lea     rbp, [rax-288h]
0x18004088b  sub     rsp, 360h
0x180040892  mov     rax, cs:__security_cookie
0x180040899  xor     rax, rsp
0x18004089c  mov     [rbp+280h+var_30], rax
0x1800408a3  xor     r13d, r13d
0x1800408a6  mov     [rsp+380h+var_310+4], ecx
0x1800408aa  mov     r12d, ecx
0x1800408ad  mov     [rsp+380h+lpMem], r13
0x1800408b2  lea     r9, aInstallAllAspN; "Install all ASP.NET Services"
0x1800408b9  mov     [rsp+380h+lpBinaryPathName], r13; unsigned __int16 *
0x1800408be  xor     r8d, r8d; unsigned int
0x1800408c1  lea     rdx, aInstallservice_0; "InstallServicesEx"
0x1800408c8  lea     ecx, [r13+1]; int
0x1800408cc  mov     r15d, r13d
0x1800408cf  mov     esi, r13d
0x1800408d2  mov     r14d, r13d
0x1800408d5  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x1800408da  mov     edx, 0D0h; unsigned __int64
0x1800408df  lea     rcx, [rbp+280h+var_100]; void *
0x1800408e6  call    ?XspSecureZeroMemory@@YAXPEAX_K@Z; XspSecureZeroMemory(void *,unsigned __int64)
0x1800408eb  mov     edx, 0D4h; unsigned __int64
0x1800408f0  lea     rcx, [rbp+280h+Str]; void *
0x1800408f4  call    ?XspSecureZeroMemory@@YAXPEAX_K@Z; XspSecureZeroMemory(void *,unsigned __int64)
0x1800408f9  lea     edi, [r13+6Ah]
0x1800408fd  mov     edx, edi; unsigned int
0x1800408ff  lea     r9d, [r13+68h]; unsigned int
0x180040903  lea     r8, [rbp+280h+var_100]; unsigned __int16 *
0x18004090a  lea     rcx, [rbp+280h+Str]; unsigned __int16 *
0x18004090e  call    ?GetServiceAccCredentials@CRegAccount@@SAJPEAGK0K@Z; CRegAccount::GetServiceAccCredentials(ushort *,ulong,ushort *,ulong)
0x180040913  mov     ebx, eax
0x180040915  test    eax, eax
0x180040917  jnz     loc_180040EDB
0x18004091d  lea     edx, [rdi-0Eh]; Ch
0x180040920  lea     rcx, [rbp+280h+Str]; Str
0x180040924  call    wcschr_0
0x180040929  test    rax, rax
0x18004092c  jnz     loc_180040A23
0x180040932  lea     rcx, [rbp+280h+Str]; lpString
0x180040936  call    cs:__imp_lstrlenW
0x18004093c  cmp     eax, 68h ; 'h'
0x18004093f  jnb     loc_180040A23
0x180040945  lea     r8, asc_18006E760; ".\\"
0x18004094c  mov     edx, edi
0x18004094e  lea     rax, [rbp+280h+var_1E0]
0x180040955  sub     r8, rax
0x180040958  lea     rcx, [rbp+280h+var_1E0]
0x18004095f  lea     rax, [rdx+7FFFFF94h]
0x180040966  test    rax, rax
0x180040969  jz      short loc_180040982
0x18004096b  movzx   eax, word ptr [r8+rcx]
0x180040970  test    ax, ax
0x180040973  jz      short loc_180040982
0x180040975  mov     [rcx], ax
0x180040978  add     rcx, 2
0x18004097c  sub     rdx, 1
0x180040980  jnz     short loc_18004095F
0x180040982  test    rdx, rdx
0x180040985  lea     rax, [rcx-2]
0x180040989  cmovnz  rax, rcx
0x18004098d  mov     [rax], r13w
0x180040991  mov     rax, rdx
0x180040994  neg     rax
0x180040997  sbb     ebx, ebx
0x180040999  not     ebx
0x18004099b  and     ebx, 8007007Ah
0x1800409a1  test    rdx, rdx
0x1800409a4  jz      loc_180040EDB
0x1800409aa  lea     r8, [rbp+280h+Str]; unsigned __int16 *
0x1800409ae  mov     rdx, rdi; unsigned __int64
0x1800409b1  lea     rcx, [rbp+280h+var_1E0]; unsigned __int16 *
0x1800409b8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800409bd  mov     ebx, eax
0x1800409bf  test    eax, eax
0x1800409c1  jnz     loc_180040EDB
0x1800409c7  lea     rdx, [rbp+280h+var_1E0]
0x1800409ce  lea     rax, [rbp+280h+Str]
0x1800409d2  sub     rdx, rax
0x1800409d5  lea     rcx, [rbp+280h+Str]
0x1800409d9  lea     rax, [rdi+7FFFFF94h]
0x1800409e0  test    rax, rax
0x1800409e3  jz      short loc_1800409FB
0x1800409e5  movzx   eax, word ptr [rdx+rcx]
0x1800409e9  test    ax, ax
0x1800409ec  jz      short loc_1800409FB
0x1800409ee  mov     [rcx], ax
0x1800409f1  add     rcx, 2
0x1800409f5  sub     rdi, 1
0x1800409f9  jnz     short loc_1800409D9
0x1800409fb  test    rdi, rdi
0x1800409fe  lea     rax, [rcx-2]
0x180040a02  cmovnz  rax, rcx
0x180040a06  mov     [rax], r13w
0x180040a0a  mov     rax, rdi
0x180040a0d  neg     rax
0x180040a10  sbb     ebx, ebx
0x180040a12  not     ebx
0x180040a14  and     ebx, 8007007Ah
0x180040a1a  test    rdi, rdi
0x180040a1d  jz      loc_180040EDB
0x180040a23  xor     r8d, r8d; unsigned int
0x180040a26  mov     [rsp+380h+lpBinaryPathName], r13; unsigned __int16 *
0x180040a2b  lea     r9, aConnectingToSe; "Connecting to Service Manager"
0x180040a32  lea     rdx, aOpenscmanager; "OpenSCManager"
0x180040a39  lea     ecx, [r8+1]; int
0x180040a3d  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180040a42  xor     edx, edx; lpDatabaseName
0x180040a44  xor     ecx, ecx; lpMachineName
0x180040a46  lea     r8d, [rdx+9]; dwDesiredAccess
0x180040a4a  call    cs:__imp_OpenSCManagerW
0x180040a50  mov     r15, rax
0x180040a53  test    rax, rax
0x180040a56  jnz     short loc_180040A5F
0x180040a58  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180040a5d  mov     ebx, eax
0x180040a5f  lea     r9, aConnectingToSe; "Connecting to Service Manager"
0x180040a66  mov     [rsp+380h+lpBinaryPathName], r13; unsigned __int16 *
0x180040a6b  xor     r8d, r8d; unsigned int
0x180040a6e  lea     rdx, aOpenscmanager; "OpenSCManager"
0x180040a75  mov     ecx, ebx; int
0x180040a77  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180040a7c  test    ebx, ebx
0x180040a7e  jnz     loc_180040EDB
0x180040a84  lea     rdi, off_18008ED90; "aspnet_state"
0x180040a8b  or      [rsp+380h+var_320+4], 0FFFFFFFFh
0x180040a90  mov     [rsp+380h+var_320], esi
0x180040a94  test    r12d, r12d
0x180040a97  jz      short loc_180040AEE
0x180040a99  mov     rdx, [rdi-8]; lpServiceName
0x180040a9d  lea     r8, [rsp+380h+var_310]; int *
0x180040aa2  mov     rcx, r15; hSCManager
0x180040aa5  call    ?IsCurrentVersionServiceInstalled@@YAJPEAUSC_HANDLE__@@PEAGPEAH@Z; IsCurrentVersionServiceInstalled(SC_HANDLE__ *,ushort *,int *)
0x180040aaa  mov     ebx, eax
0x180040aac  test    eax, eax
0x180040aae  jnz     short loc_180040AEE
0x180040ab0  cmp     [rsp+380h+var_310], esi
0x180040ab4  jz      short loc_180040AEE
0x180040ab6  mov     r9, [rdi]; char *
0x180040ab9  lea     rdx, aKeepInstalling; "Keep installing service because it is a"...
0x180040ac0  xor     r8d, r8d; unsigned int
0x180040ac3  mov     [rsp+380h+lpBinaryPathName], rsi; unsigned __int16 *
0x180040ac8  lea     ecx, [rax+1]; int
0x180040acb  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180040ad0  mov     r9, [rdi]; char *
0x180040ad3  lea     rdx, aKeepInstalling; "Keep installing service because it is a"...
0x180040ada  xor     r8d, r8d; unsigned int
0x180040add  mov     [rsp+380h+lpBinaryPathName], rsi; unsigned __int16 *
0x180040ae2  xor     ecx, ecx; int
0x180040ae4  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180040ae9  jmp     loc_180040E7F
0x180040aee  mov     r9, [rdi]; char *
0x180040af1  lea     rdx, aStartInstallin; "Start installing service"
0x180040af8  xor     r12d, r12d
0x180040afb  xor     r8d, r8d; unsigned int
0x180040afe  mov     [rsp+380h+lpBinaryPathName], r12; unsigned __int16 *
0x180040b03  lea     ecx, [r12+1]; int
0x180040b08  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180040b0d  mov     r9, [rdi]; char *
0x180040b10  lea     rdx, aStartInstallin; "Start installing service"
0x180040b17  xor     r8d, r8d; unsigned int
0x180040b1a  mov     [rsp+380h+lpBinaryPathName], r12; unsigned __int16 *
0x180040b1f  xor     ecx, ecx; int
0x180040b21  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180040b26  mov     rcx, [rdi-20h]
0x180040b2a  mov     rax, [rcx]
0x180040b2d  mov     rax, [rax]
0x180040b30  call    cs:__guard_dispatch_icall_fptr
0x180040b36  movsxd  rax, r13d
0x180040b39  lea     r9, [rsp+380h+lpMem]; struct _SERVICE_FAILURE_ACTIONSW **
0x180040b3e  lea     r8, [rsp+380h+var_320+4]; unsigned int *
0x180040b43  lea     rcx, [rax+rax*8]
0x180040b47  lea     rax, ?g_rgServiceSetupInfo@@3PAUServiceSetupInfo@@A; ServiceSetupInfo near * g_rgServiceSetupInfo
0x180040b4e  lea     rsi, [rax+rcx*8]
0x180040b52  mov     rcx, r15; hSCManager
0x180040b55  lea     rax, [rsp+380h+var_320]
0x180040b5a  mov     [rsp+380h+var_308], rsi
0x180040b5f  mov     rdx, rsi; struct ServiceSetupInfo *
0x180040b62  mov     [rsp+380h+lpBinaryPathName], rax; int *
0x180040b67  call    ?ReadServiceSettings@@YAJPEAUSC_HANDLE__@@PEAUServiceSetupInfo@@PEAKPEAPEAU_SERVICE_FAILURE_ACTIONSW@@PEAH@Z; ReadServiceSettings(SC_HANDLE__ *,ServiceSetupInfo *,ulong *,_SERVICE_FAILURE_ACTIONSW * *,int *)
0x180040b6c  cmp     [rsp+380h+var_320], r12d
0x180040b71  jnz     short loc_180040B93
0x180040b73  mov     r8, [rdi-10h]
0x180040b77  xor     r9d, r9d
0x180040b7a  mov     rcx, cs:?g_DllInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180040b81  mov     dl, 1
0x180040b83  call    InstallInfSections
0x180040b88  mov     ecx, 3E8h; dwMilliseconds
0x180040b8d  call    cs:__imp_Sleep
0x180040b93  mov     r8, [rdi-18h]
0x180040b97  xor     r9d, r9d
0x180040b9a  mov     rcx, cs:?g_DllInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180040ba1  mov     dl, 1
0x180040ba3  call    InstallInfSections
0x180040ba8  mov     ebx, eax
0x180040baa  test    eax, eax
0x180040bac  jnz     loc_180040E93
0x180040bb2  mov     rcx, [rdi-20h]
0x180040bb6  mov     rax, [rcx]
0x180040bb9  mov     rax, [rax+8]
0x180040bbd  call    cs:__guard_dispatch_icall_fptr
0x180040bc3  cmp     [rdi+10h], r12
0x180040bc7  jz      short loc_180040BD4
0x180040bc9  mov     rcx, rsi; struct ServiceSetupInfo *
0x180040bcc  call    ?InstallServicePerfCounter@@YAJPEAUServiceSetupInfo@@@Z; InstallServicePerfCounter(ServiceSetupInfo *)
0x180040bd1  mov     ebx, r12d
0x180040bd4  mov     esi, 3Ch ; '<'
0x180040bd9  mov     [rsp+380h+lpBinaryPathName], r12; unsigned __int16 *
0x180040bde  lea     r9, aLockingService; "Locking service database"
0x180040be5  xor     r8d, r8d; unsigned int
0x180040be8  lea     rdx, aLockservicedat_0; "LockServiceDatabase"
0x180040bef  lea     ecx, [rsi-3Bh]; int
0x180040bf2  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180040bf7  jmp     short loc_180040C1C
0x180040bf9  call    cs:__imp_GetLastError
0x180040bff  cmp     eax, 41Fh
0x180040c04  jnz     loc_180040EA2
0x180040c0a  sub     esi, 1
0x180040c0d  jz      loc_180040E9B
0x180040c13  lea     ecx, [rax-37h]; dwMilliseconds
0x180040c16  call    cs:__imp_Sleep
0x180040c1c  mov     rcx, r15; hSCManager
0x180040c1f  call    cs:__imp_LockServiceDatabase
0x180040c25  mov     r14, rax
0x180040c28  test    rax, rax
0x180040c2b  jz      short loc_180040BF9
0x180040c2d  lea     r9, aLockingService; "Locking service database"
0x180040c34  mov     [rsp+380h+lpBinaryPathName], r12; unsigned __int16 *
0x180040c39  xor     r8d, r8d; unsigned int
0x180040c3c  lea     rdx, aLockservicedat_0; "LockServiceDatabase"
0x180040c43  xor     ecx, ecx; int
0x180040c45  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180040c4a  xor     r8d, r8d; unsigned int
0x180040c4d  mov     [rsp+380h+lpBinaryPathName], r12; unsigned __int16 *
0x180040c52  lea     r9, aOpeningService; "Opening Service handle"
0x180040c59  lea     rdx, aOpenservice; "OpenService"
0x180040c60  lea     ecx, [r8+1]; int
0x180040c64  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180040c69  mov     rdx, [rdi-8]; lpServiceName
0x180040c6d  mov     r8d, 12h; dwDesiredAccess
0x180040c73  mov     rcx, r15; hSCManager
0x180040c76  call    cs:__imp_OpenServiceW
0x180040c7c  mov     rsi, rax
0x180040c7f  test    rax, rax
0x180040c82  jnz     short loc_180040C8B
0x180040c84  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180040c89  mov     ebx, eax
0x180040c8b  lea     r9, aOpeningService; "Opening Service handle"
0x180040c92  mov     [rsp+380h+lpBinaryPathName], r12; unsigned __int16 *
0x180040c97  xor     r8d, r8d; unsigned int
0x180040c9a  lea     rdx, aOpenservice; "OpenService"
0x180040ca1  mov     ecx, ebx; int
0x180040ca3  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180040ca8  test    ebx, ebx
0x180040caa  jnz     loc_180040EDE
0x180040cb0  mov     r12, [rsp+380h+lpMem]
0x180040cb5  xor     ebx, ebx
0x180040cb7  test    r12, r12
0x180040cba  jnz     short loc_180040CEE
0x180040cbc  xorps   xmm0, xmm0
0x180040cbf  mov     [rbp+280h+var_300], 15180h
0x180040cc6  lea     rax, [rbp+280h+var_2D8]
0x180040cca  mov     [rbp+280h+var_2E8], 3
0x180040cd1  movdqu  [rbp+280h+var_2F8], xmm0
0x180040cd6  mov     [rbp+280h+var_2E0], rax
0x180040cda  mov     [rbp+280h+var_2D8], 1
0x180040ce2  mov     [rbp+280h+var_2D0], 1
0x180040cea  mov     [rbp+280h+var_2C8], rbx
0x180040cee  mov     r8d, [rsp+380h+var_320+4]; unsigned int
0x180040cf3  lea     r9, [rbp+280h+var_300]
0x180040cf7  mov     rdx, [rsp+380h+var_308]; struct ServiceSetupInfo *
0x180040cfc  test    r12, r12
0x180040cff  mov     rcx, rsi; hService
0x180040d02  cmovnz  r9, r12; struct _SERVICE_FAILURE_ACTIONSW *
0x180040d06  call    ?WriteServiceSettings@@YAJPEAUSC_HANDLE__@@PEAUServiceSetupInfo@@KPEAU_SERVICE_FAILURE_ACTIONSW@@@Z; WriteServiceSettings(SC_HANDLE__ *,ServiceSetupInfo *,ulong,_SERVICE_FAILURE_ACTIONSW *)
0x180040d0b  mov     rcx, r12; lpMem
0x180040d0e  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180040d13  xor     r12d, r12d
0x180040d16  lea     r9, aChangingServic; "Changing service account and password"
0x180040d1d  xor     r8d, r8d; unsigned int
0x180040d20  mov     [rsp+380h+lpMem], r12
0x180040d25  lea     rdx, aChangeservicec_1; "ChangeServiceConfig"
0x180040d2c  mov     [rsp+380h+lpBinaryPathName], r12; unsigned __int16 *
0x180040d31  lea     ecx, [r12+1]; int
0x180040d36  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180040d3b  mov     ecx, [rdi+20h]
0x180040d3e  lea     r8, ServiceStartName; "LocalSystem"
0x180040d45  mov     [rsp+380h+lpDisplayName], r12; lpDisplayName
0x180040d4a  lea     rdx, [rbp+280h+var_100]
0x180040d51  test    ecx, ecx
0x180040d53  lea     rax, [rbp+280h+Str]
0x180040d57  mov     rcx, rsi; hService
  ... truncated ...
```
