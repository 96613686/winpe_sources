# ParseHostConfigFile(ushort const *,long *,long *,long *,long *,long *)

- ea: `0x18005dab4`
- end: `0x18005dead`
- name: `?ParseHostConfigFile@@YAJPEBGPEAJ1111@Z`
- size: `1017`
- prototype: `__int64 __fastcall(LPCWSTR pszFile, int *, int *, int *, int *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005bbb4`

## callees

- `0x180007824`
- `0x18004d030`
- `0x18005d6a4`
- `0x18005d83c`
- `0x18005d8dc`
- `0x18005dab4`
- `0x18006541c`
- `0x18006585c`
- `0x180065b60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005dbb5`
- `KERNEL32!GetLastError` at `0x18005dbb5`
- `KERNEL32!FreeLibrary` at `0x18005de82`
- `KERNEL32!FreeLibrary` at `0x18005de82`
- `KERNEL32!GetProcAddress` at `0x18005dbd8`
- `KERNEL32!GetProcAddress` at `0x18005dbd8`
- `KERNEL32!LoadLibraryW` at `0x18005dba7`
- `KERNEL32!LoadLibraryW` at `0x18005dba7`
- `KERNEL32!GetFileAttributesW` at `0x18005db5a`
- `KERNEL32!GetFileAttributesW` at `0x18005db5a`
- `KERNEL32!GetSystemDirectoryW` at `0x18005db74`
- `KERNEL32!GetSystemDirectoryW` at `0x18005db74`
- `ole32!CoCreateInstance` at `0x18005dc5b`
- `ole32!CoCreateInstance` at `0x18005dc5b`
- `SHLWAPI!SHCreateStreamOnFileW` at `0x18005dc0c`
- `SHLWAPI!SHCreateStreamOnFileW` at `0x18005dc0c`

## string_xrefs

- `0x18005db87`: `\xmllite.dll`
- `0x18005dbce`: `CreateXmlReader`
- `0x18005dd4a`: `ParseHostConfigFile`
- `0x18005ddf3`: `ParseHostConfigFile`
- `0x18005dd58`: `f:\dd\ndp\fx\src\xsp\webengine\mgdconfig.cxx`
- `0x18005ddfe`: `f:\dd\ndp\fx\src\xsp\webengine\mgdconfig.cxx`
- `0x18005dd88`: `GetApplicationPoolSettings succeeded. RequestsPerCPU = %d, ThreadsPerCPU = %d, PercentCpuLimit = %d, PercentCpuLimitMinActiveRequestsPerCpu = %d, QueueLimit = %d\n`

## pseudocode

```c
__int64 __fastcall ParseHostConfigFile(LPCWSTR pszFile, int *a2, int *a3, int *a4, int *a5, int *a6)
{
  int v9; // ebx
  HMODULE v10; // rdi
  BOOL v11; // r14d
  int *v13; // rax
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  int ApplicationPoolSettings; // eax
  struct _XMLLITE_IXmlReader *v19; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *String1; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  IStream *ppstm; // [rsp+70h] [rbp-90h] BYREF
  int *v24; // [rsp+78h] [rbp-88h]
  int *v25; // [rsp+80h] [rbp-80h]
  WCHAR Buffer[264]; // [rsp+90h] [rbp-70h] BYREF

  v25 = a5;
  v24 = a6;
  v9 = 0;
  ppstm = 0;
  v10 = 0;
  ppv = 0;
  v19 = 0;
  v11 = 0;
  String1 = 0;
  *a2 = GetConfigValue(L"MaxConcurrentRequestsPerCPU", 5000);
  *a3 = 0;
  v13 = v25;
  *a4 = 90;
  *v13 = 100;
  *v24 = GetQueueLimit();
  if ( GetFileAttributesW(pszFile) != -1 )
  {
    if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
    {
      v9 = -2147467259;
    }
    else
    {
      v9 = StringCchCatW(Buffer, 0x104u, L"\\xmllite.dll");
      if ( v9 >= 0 )
      {
        LibraryW = LoadLibraryW(Buffer);
        v10 = LibraryW;
        if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "CreateXmlReader")) != 0 )
        {
          v9 = ((__int64 (__fastcall *)(GUID *, struct _XMLLITE_IXmlReader **, _QWORD))ProcAddress)(
                 &GUID_7279fc81_709d_4095_b63d_69fe4b0d9030,
                 &v19,
                 0);
          if ( v9 >= 0 )
          {
            v9 = SHCreateStreamOnFileW(pszFile, 0, &ppstm);
            if ( v9 >= 0 )
            {
              v9 = (*(__int64 (__fastcall **)(struct _XMLLITE_IXmlReader *, IStream *))(*(_QWORD *)v19 + 24LL))(
                     v19,
                     ppstm);
              if ( v9 >= 0 )
              {
                if ( CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage3, &ppv) < 0
                  || (v9 = (*(__int64 (__fastcall **)(struct _XMLLITE_IXmlReader *, _QWORD, LPVOID))(*(_QWORD *)v19 + 40LL))(
                             v19,
                             0,
                             ppv),
                      v9 >= 0) )
                {
                  while ( 1 )
                  {
                    v9 = (*(__int64 (__fastcall **)(struct _XMLLITE_IXmlReader *, int *))(*(_QWORD *)v19 + 48LL))(
                           v19,
                           &v20);
                    if ( v9 )
                      break;
                    if ( v20 == 1 )
                    {
                      v9 = (*(__int64 (__fastcall **)(struct _XMLLITE_IXmlReader *, wchar_t **, _QWORD))(*(_QWORD *)v19 + 112LL))(
                             v19,
                             &String1,
                             0);
                      if ( v9 < 0 )
                        break;
                      if ( v11 )
                      {
                        if ( !wcscmp_0(String1, L"applicationPool") )
                        {
                          ApplicationPoolSettings = GetApplicationPoolSettings(v19, a2, a3, a4, v25, v24);
                          v9 = ApplicationPoolSettings;
                          if ( ApplicationPoolSettings < 0 )
                          {
                            if ( (g_dwDebugFlags & 3) != 0 )
                              PuDbgPrint(
                                g_pDebug,
                                "f:\\dd\\ndp\\fx\\src\\xsp\\webengine\\mgdconfig.cxx",
                                0x22Du,
                                "ParseHostConfigFile",
                                "GetApplicationPoolSettings failed. hr = 0x%x \n",
                                ApplicationPoolSettings);
                            break;
                          }
                          if ( (g_dwDebugFlags & 3) != 0 )
                            PuDbgPrint(
                              g_pDebug,
                              "f:\\dd\\ndp\\fx\\src\\xsp\\webengine\\mgdconfig.cxx",
                              0x238u,
                              "ParseHostConfigFile",
                              "GetApplicationPoolSettings succeeded. RequestsPerCPU = %d, ThreadsPerCPU = %d, PercentCpuL"
                              "imit = %d, PercentCpuLimitMinActiveRequestsPerCpu = %d, QueueLimit = %d\n",
                              *a2);
                        }
                      }
                      else
                      {
                        v11 = wcscmp_0(String1, L"system.web") == 0;
                      }
                    }
                    else if ( v20 == 15 )
                    {
                      v9 = (*(__int64 (__fastcall **)(struct _XMLLITE_IXmlReader *, wchar_t **, _QWORD))(*(_QWORD *)v19 + 112LL))(
                             v19,
                             &String1,
                             0);
                      if ( v9 < 0 || !wcscmp_0(String1, L"system.web") )
                        break;
                    }
                  }
                }
              }
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v9 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v9 = LastError;
        }
      }
    }
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( ppstm )
  {
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(struct _XMLLITE_IXmlReader *))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v10 )
    FreeLibrary(v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005dab4  push    rbp
0x18005dab6  push    rbx
0x18005dab7  push    rsi
0x18005dab8  push    rdi
0x18005dab9  push    r12
0x18005dabb  push    r13
0x18005dabd  push    r14
0x18005dabf  push    r15
0x18005dac1  lea     rbp, [rsp-1B8h]
0x18005dac9  sub     rsp, 2B8h
0x18005dad0  mov     rax, cs:__security_cookie
0x18005dad7  xor     rax, rsp
0x18005dada  mov     [rbp+1F0h+var_50], rax
0x18005dae1  mov     rax, [rbp+1F0h+arg_20]
0x18005dae8  mov     r15, rdx
0x18005daeb  mov     [rbp+1F0h+var_270], rax
0x18005daef  mov     rsi, rcx
0x18005daf2  mov     rax, [rbp+1F0h+arg_28]
0x18005daf9  lea     rcx, aMaxconcurrentr; "MaxConcurrentRequestsPerCPU"
0x18005db00  mov     [rsp+2F0h+var_278], rax
0x18005db05  mov     edx, 1388h; int
0x18005db0a  xor     eax, eax
0x18005db0c  mov     r13, r9
0x18005db0f  mov     ebx, eax
0x18005db11  mov     [rsp+2F0h+ppstm], rax
0x18005db16  mov     edi, eax
0x18005db18  mov     [rsp+2F0h+var_288], rax
0x18005db1d  mov     [rsp+2F0h+var_2A0], rax
0x18005db22  mov     r14d, eax
0x18005db25  mov     [rsp+2F0h+String1], rax
0x18005db2a  mov     r12, r8
0x18005db2d  call    ?GetConfigValue@@YAJPEBGJ@Z; GetConfigValue(ushort const *,long)
0x18005db32  mov     [r15], eax
0x18005db35  and     [r12], ebx
0x18005db39  mov     rax, [rbp+1F0h+var_270]
0x18005db3d  mov     dword ptr [r13+0], 5Ah ; 'Z'
0x18005db45  mov     dword ptr [rax], 64h ; 'd'
0x18005db4b  call    ?GetQueueLimit@@YAJXZ; GetQueueLimit(void)
0x18005db50  mov     rcx, [rsp+2F0h+var_278]
0x18005db55  mov     [rcx], eax
0x18005db57  mov     rcx, rsi; lpFileName
0x18005db5a  call    cs:__imp_GetFileAttributesW
0x18005db60  cmp     eax, 0FFFFFFFFh
0x18005db63  jz      loc_18005DE23
0x18005db69  mov     ebx, 104h
0x18005db6e  lea     rcx, [rbp+1F0h+Buffer]; lpBuffer
0x18005db72  mov     edx, ebx; uSize
0x18005db74  call    cs:__imp_GetSystemDirectoryW
0x18005db7a  dec     eax
0x18005db7c  cmp     eax, 103h
0x18005db81  ja      loc_18005DE1E
0x18005db87  lea     r8, aXmlliteDll; "\\xmllite.dll"
0x18005db8e  mov     edx, ebx; unsigned __int64
0x18005db90  lea     rcx, [rbp+1F0h+Buffer]; unsigned __int16 *
0x18005db94  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005db99  mov     ebx, eax
0x18005db9b  test    eax, eax
0x18005db9d  js      loc_18005DE23
0x18005dba3  lea     rcx, [rbp+1F0h+Buffer]; lpLibFileName
0x18005dba7  call    cs:__imp_LoadLibraryW
0x18005dbad  mov     rdi, rax
0x18005dbb0  test    rax, rax
0x18005dbb3  jnz     short loc_18005DBCE
0x18005dbb5  call    cs:__imp_GetLastError
0x18005dbbb  movzx   ebx, ax
0x18005dbbe  or      ebx, 80070000h
0x18005dbc4  test    eax, eax
0x18005dbc6  cmovle  ebx, eax
0x18005dbc9  jmp     loc_18005DE23
0x18005dbce  lea     rdx, aCreatexmlreade; "CreateXmlReader"
0x18005dbd5  mov     rcx, rax; hModule
0x18005dbd8  call    cs:__imp_GetProcAddress
0x18005dbde  test    rax, rax
0x18005dbe1  jz      short loc_18005DBB5
0x18005dbe3  xor     r8d, r8d
0x18005dbe6  lea     rdx, [rsp+2F0h+var_2A0]
0x18005dbeb  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030
0x18005dbf2  call    cs:__guard_dispatch_icall_fptr
0x18005dbf8  mov     ebx, eax
0x18005dbfa  test    eax, eax
0x18005dbfc  js      loc_18005DE23
0x18005dc02  lea     r8, [rsp+2F0h+ppstm]; ppstm
0x18005dc07  xor     edx, edx; grfMode
0x18005dc09  mov     rcx, rsi; pszFile
0x18005dc0c  call    cs:__imp_SHCreateStreamOnFileW
0x18005dc12  mov     ebx, eax
0x18005dc14  test    eax, eax
0x18005dc16  js      loc_18005DE23
0x18005dc1c  mov     rcx, [rsp+2F0h+var_2A0]
0x18005dc21  mov     rdx, [rsp+2F0h+ppstm]
0x18005dc26  mov     rax, [rcx]
0x18005dc29  mov     rax, [rax+18h]
0x18005dc2d  call    cs:__guard_dispatch_icall_fptr
0x18005dc33  mov     ebx, eax
0x18005dc35  test    eax, eax
0x18005dc37  js      loc_18005DE23
0x18005dc3d  xor     edx, edx; pUnkOuter
0x18005dc3f  lea     rax, [rsp+2F0h+var_288]
0x18005dc44  lea     r9, IID_IMultiLanguage3; riid
0x18005dc4b  mov     [rsp+2F0h+ppv], rax; ppv
0x18005dc50  lea     rcx, CLSID_CMultiLanguage; rclsid
0x18005dc57  lea     r8d, [rdx+1]; dwClsContext
0x18005dc5b  call    cs:__imp_CoCreateInstance
0x18005dc61  test    eax, eax
0x18005dc63  js      short loc_18005DC88
0x18005dc65  mov     rcx, [rsp+2F0h+var_2A0]
0x18005dc6a  xor     edx, edx
0x18005dc6c  mov     r8, [rsp+2F0h+var_288]
0x18005dc71  mov     rax, [rcx]
0x18005dc74  mov     rax, [rax+28h]
0x18005dc78  call    cs:__guard_dispatch_icall_fptr
0x18005dc7e  mov     ebx, eax
0x18005dc80  test    eax, eax
0x18005dc82  js      loc_18005DE23
0x18005dc88  mov     rcx, [rsp+2F0h+var_2A0]
0x18005dc8d  lea     rdx, [rsp+2F0h+var_298]
0x18005dc92  mov     rax, [rcx]
0x18005dc95  mov     rax, [rax+30h]
0x18005dc99  call    cs:__guard_dispatch_icall_fptr
0x18005dc9f  mov     ebx, eax
0x18005dca1  test    eax, eax
0x18005dca3  jnz     loc_18005DE23
0x18005dca9  cmp     [rsp+2F0h+var_298], 1
0x18005dcae  jnz     loc_18005DD9E
0x18005dcb4  mov     rcx, [rsp+2F0h+var_2A0]
0x18005dcb9  lea     rdx, [rsp+2F0h+String1]
0x18005dcbe  xor     r8d, r8d
0x18005dcc1  mov     rax, [rcx]
0x18005dcc4  mov     rax, [rax+70h]
0x18005dcc8  call    cs:__guard_dispatch_icall_fptr
0x18005dcce  mov     ebx, eax
0x18005dcd0  test    eax, eax
0x18005dcd2  js      loc_18005DE23
0x18005dcd8  mov     rcx, [rsp+2F0h+String1]; String1
0x18005dcdd  test    r14d, r14d
0x18005dce0  jnz     short loc_18005DCF8
0x18005dce2  lea     rdx, aSystemWeb_0; "system.web"
0x18005dce9  call    wcscmp_0
0x18005dcee  test    eax, eax
0x18005dcf0  jnz     short loc_18005DC88
0x18005dcf2  lea     r14d, [rax+1]
0x18005dcf6  jmp     short loc_18005DC88
0x18005dcf8  lea     rdx, aApplicationpoo; "applicationPool"
0x18005dcff  call    wcscmp_0
0x18005dd04  test    eax, eax
0x18005dd06  jnz     short loc_18005DC88
0x18005dd08  mov     rax, [rsp+2F0h+var_278]
0x18005dd0d  mov     r9, r13; int *
0x18005dd10  mov     rsi, [rbp+1F0h+var_270]
0x18005dd14  mov     r8, r12; int *
0x18005dd17  mov     rcx, [rsp+2F0h+var_2A0]; struct _XMLLITE_IXmlReader *
0x18005dd1c  mov     rdx, r15; int *
0x18005dd1f  mov     [rsp+2F0h+var_2C8], rax; int *
0x18005dd24  mov     [rsp+2F0h+ppv], rsi; int *
0x18005dd29  call    ?GetApplicationPoolSettings@@YAJPEAU_XMLLITE_IXmlReader@@PEAJ1111@Z; GetApplicationPoolSettings(_XMLLITE_IXmlReader *,long *,long *,long *,long *,long *)
0x18005dd2e  mov     ebx, eax
0x18005dd30  test    eax, eax
0x18005dd32  js      loc_18005DDE3
0x18005dd38  test    byte ptr cs:g_dwDebugFlags, 3
0x18005dd3f  jz      loc_18005DC88
0x18005dd45  mov     rax, [rsp+2F0h+var_278]
0x18005dd4a  lea     r9, aParsehostconfi; "ParseHostConfigFile"
0x18005dd51  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18005dd58  lea     rdx, aFDdNdpFxSrcXsp; "f:\\dd\\ndp\\fx\\src\\xsp\\webengine\\m"...
0x18005dd5f  mov     r8d, 238h; unsigned int
0x18005dd65  mov     eax, [rax]
0x18005dd67  mov     [rsp+2F0h+var_2A8], eax
0x18005dd6b  mov     eax, [rsi]
0x18005dd6d  mov     [rsp+2F0h+var_2B0], eax
0x18005dd71  mov     eax, [r13+0]
0x18005dd75  mov     [rsp+2F0h+var_2B8], eax
0x18005dd79  mov     eax, [r12]
0x18005dd7d  mov     [rsp+2F0h+var_2C0], eax
0x18005dd81  mov     eax, [r15]
0x18005dd84  mov     dword ptr [rsp+2F0h+var_2C8], eax; char
0x18005dd88  lea     rax, aGetapplication_0; "GetApplicationPoolSettings succeeded. R"...
0x18005dd8f  mov     [rsp+2F0h+ppv], rax; char *
0x18005dd94  call    PuDbgPrint
0x18005dd99  jmp     loc_18005DC88
0x18005dd9e  cmp     [rsp+2F0h+var_298], 0Fh
0x18005dda3  jnz     loc_18005DC88
0x18005dda9  mov     rcx, [rsp+2F0h+var_2A0]
0x18005ddae  lea     rdx, [rsp+2F0h+String1]
0x18005ddb3  xor     r8d, r8d
0x18005ddb6  mov     rax, [rcx]
0x18005ddb9  mov     rax, [rax+70h]
0x18005ddbd  call    cs:__guard_dispatch_icall_fptr
0x18005ddc3  mov     ebx, eax
0x18005ddc5  test    eax, eax
0x18005ddc7  js      short loc_18005DE23
0x18005ddc9  mov     rcx, [rsp+2F0h+String1]; String1
0x18005ddce  lea     rdx, aSystemWeb_0; "system.web"
0x18005ddd5  call    wcscmp_0
0x18005ddda  test    eax, eax
0x18005dddc  jz      short loc_18005DE23
0x18005ddde  jmp     loc_18005DC88
0x18005dde3  test    byte ptr cs:g_dwDebugFlags, 3
0x18005ddea  jz      short loc_18005DE23
0x18005ddec  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18005ddf3  lea     r9, aParsehostconfi; "ParseHostConfigFile"
0x18005ddfa  mov     dword ptr [rsp+2F0h+var_2C8], eax; char
0x18005ddfe  lea     rdx, aFDdNdpFxSrcXsp; "f:\\dd\\ndp\\fx\\src\\xsp\\webengine\\m"...
0x18005de05  lea     rax, aGetapplication; "GetApplicationPoolSettings failed. hr ="...
0x18005de0c  mov     r8d, 22Dh; unsigned int
0x18005de12  mov     [rsp+2F0h+ppv], rax; char *
0x18005de17  call    PuDbgPrint
0x18005de1c  jmp     short loc_18005DE23
0x18005de1e  mov     ebx, 80004005h
0x18005de23  mov     rcx, [rsp+2F0h+var_288]
0x18005de28  test    rcx, rcx
0x18005de2b  jz      short loc_18005DE40
0x18005de2d  mov     rax, [rcx]
0x18005de30  mov     rax, [rax+10h]
0x18005de34  call    cs:__guard_dispatch_icall_fptr
0x18005de3a  and     [rsp+2F0h+var_288], 0
0x18005de40  mov     rcx, [rsp+2F0h+ppstm]
0x18005de45  test    rcx, rcx
0x18005de48  jz      short loc_18005DE5D
0x18005de4a  mov     rax, [rcx]
0x18005de4d  mov     rax, [rax+10h]
0x18005de51  call    cs:__guard_dispatch_icall_fptr
0x18005de57  and     [rsp+2F0h+ppstm], 0
0x18005de5d  mov     rcx, [rsp+2F0h+var_2A0]
0x18005de62  test    rcx, rcx
0x18005de65  jz      short loc_18005DE7A
0x18005de67  mov     rax, [rcx]
0x18005de6a  mov     rax, [rax+10h]
0x18005de6e  call    cs:__guard_dispatch_icall_fptr
0x18005de74  and     [rsp+2F0h+var_2A0], 0
0x18005de7a  test    rdi, rdi
0x18005de7d  jz      short loc_18005DE88
0x18005de7f  mov     rcx, rdi; hLibModule
0x18005de82  call    cs:__imp_FreeLibrary
0x18005de88  mov     eax, ebx
0x18005de8a  mov     rcx, [rbp+1F0h+var_50]
0x18005de91  xor     rcx, rsp; StackCookie
0x18005de94  call    __security_check_cookie
0x18005de99  add     rsp, 2B8h
0x18005dea0  pop     r15
0x18005dea2  pop     r14
0x18005dea4  pop     r13
0x18005dea6  pop     r12
0x18005dea8  pop     rdi
0x18005dea9  pop     rsi
0x18005deaa  pop     rbx
0x18005deab  pop     rbp
0x18005deac  retn
```
