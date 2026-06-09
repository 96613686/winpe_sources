# UninstallAllUsingHighest(int,int *)

- ea: `0x18003e808`
- end: `0x18003ea5b`
- name: `?UninstallAllUsingHighest@@YAJHPEAH@Z`
- size: `595`
- prototype: `__int64 __fastcall(int, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18003ef38`

## callees

- `0x18000c534`
- `0x18000c598`
- `0x18000d1d4`
- `0x180012b30`
- `0x18003a498`
- `0x18003abe4`
- `0x18003e808`
- `0x18004d350`
- `0x180065b60`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18003ea2d`
- `KERNEL32!FreeLibrary` at `0x18003ea2d`
- `KERNEL32!GetProcAddress` at `0x18003e9ac`
- `KERNEL32!GetProcAddress` at `0x18003e9ac`
- `KERNEL32!LoadLibraryExW` at `0x18003e972`
- `KERNEL32!LoadLibraryExW` at `0x18003e972`
- `ucrtbase_clr0400!_wcsicmp` at `0x18003e93a`
- `ucrtbase_clr0400!_wcsicmp` at `0x18003e93a`

## string_xrefs

- `0x18003e833`: `Detect and see if we have to load the highest version DLL to uninstall all versions`
- `0x18003ea08`: `Detect and see if we have to load the highest version DLL to uninstall all versions`
- `0x18003e842`: `UninstallAllUsingHighest`
- `0x18003ea17`: `UninstallAllUsingHighest`
- `0x18003e91f`: `Loading previously installed ASP.NET isapi`
- `0x18003e978`: `Loading previously installed ASP.NET isapi`
- `0x18003e950`: `Loading previously installed ASP.NET isapi (re-loading itself)`
- `0x18003e9ba`: `Use the highest version DLL to uninstall all versions`
- `0x18003e9e6`: `Use the highest version DLL to uninstall all versions`

## pseudocode

```c
__int64 __fastcall UninstallAllUsingHighest(unsigned int a1, int *a2)
{
  HMODULE Library; // rsi
  unsigned int LastWin32Error; // edi
  unsigned int inited; // eax
  int v7; // ebx
  int v8; // ecx
  FARPROC ProcAddress; // rbx
  _BYTE v11[24]; // [rsp+30h] [rbp-C8h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-B0h]
  int v13; // [rsp+108h] [rbp+10h] BYREF
  int v14; // [rsp+110h] [rbp+18h] BYREF

  CRegInfo::CRegInfo((CRegInfo *)v11);
  Library = 0;
  CSetupLogging::Log(
    1,
    "UninstallAllUsingHighest",
    0,
    "Detect and see if we have to load the highest version DLL to uninstall all versions",
    0);
  *a2 = 0;
  LastWin32Error = IsCurrentHighest(&v13, &v14);
  if ( LastWin32Error )
  {
    XspLogEvent(0xC0000409);
  }
  else if ( !v13 )
  {
    CSetupLogging::Log(1, "GetHighestVersion", 0, "Getting highest version ASP.NET isapi information", 0);
    inited = CRegInfo::InitHighestInfo((CRegInfo *)v11, 0);
    v7 = (unsigned __int16)inited;
    v8 = inited;
    LastWin32Error = inited;
    if ( (unsigned __int16)inited == 1168 )
      v8 = 0;
    CSetupLogging::Log(
      v8,
      "Getting highest version ASP.NET isapi information",
      0,
      "Getting highest version ASP.NET isapi information",
      0);
    if ( v7 == 1168 )
    {
      LastWin32Error = 0;
    }
    else if ( !LastWin32Error )
    {
      CSetupLogging::Log(1, "LoadIsapi", 0, "Loading previously installed ASP.NET isapi", 0);
      if ( _wcsicmp(String1, &Names::s_wszIsapiFullPath) )
      {
        Library = LoadLibraryExW(String1, 0, 8u);
        CSetupLogging::Log(0, "LoadIsapi", 0, "Loading previously installed ASP.NET isapi", 0);
        if ( Library && (ProcAddress = GetProcAddress(Library, "UnregisterISAPI")) != 0 )
        {
          CSetupLogging::Log(1, "UnregisterISAPI", 0, "Use the highest version DLL to uninstall all versions", 0);
          LastWin32Error = ((__int64 (__fastcall *)(__int64, _QWORD))ProcAddress)(1, a1);
          CSetupLogging::Log(
            LastWin32Error,
            "UnregisterISAPI",
            0,
            "Use the highest version DLL to uninstall all versions",
            0);
          *a2 = 1;
        }
        else
        {
          LastWin32Error = GetLastWin32Error();
        }
      }
      else
      {
        LastWin32Error = -2147418113;
        CSetupLogging::Log(
          -2147418113,
          "LoadIsapi",
          0,
          "Loading previously installed ASP.NET isapi (re-loading itself)",
          0);
      }
    }
  }
  CSetupLogging::Log(
    LastWin32Error,
    "UninstallAllUsingHighest",
    0,
    "Detect and see if we have to load the highest version DLL to uninstall all versions",
    0);
  if ( Library )
    FreeLibrary(Library);
  CRegInfo::~CRegInfo((CRegInfo *)v11);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003e808  mov     [rsp+arg_0], rbx
0x18003e80d  mov     [rsp+arg_18], rbp
0x18003e812  push    rsi
0x18003e813  push    rdi
0x18003e814  push    r13
0x18003e816  push    r14
0x18003e818  push    r15
0x18003e81a  sub     rsp, 0D0h
0x18003e821  mov     ebp, ecx
0x18003e823  mov     r14, rdx
0x18003e826  lea     rcx, [rsp+0F8h+var_C8]; this
0x18003e82b  call    ??0CRegInfo@@QEAA@XZ; CRegInfo::CRegInfo(void)
0x18003e830  xor     r13d, r13d
0x18003e833  lea     r9, aDetectAndSeeIf; "Detect and see if we have to load the h"...
0x18003e83a  xor     r8d, r8d; unsigned int
0x18003e83d  mov     [rsp+0F8h+var_D8], r13; unsigned __int16 *
0x18003e842  lea     rdx, aUninstallallus; "UninstallAllUsingHighest"
0x18003e849  mov     esi, r13d
0x18003e84c  lea     ebx, [r13+1]
0x18003e850  mov     ecx, ebx; int
0x18003e852  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e857  lea     rdx, [rsp+0F8h+arg_10]; int *
0x18003e85f  mov     [r14], r13d
0x18003e862  lea     rcx, [rsp+0F8h+arg_8]; int *
0x18003e86a  call    ?IsCurrentHighest@@YAJPEAH0@Z; IsCurrentHighest(int *,int *)
0x18003e86f  mov     edi, eax
0x18003e871  test    eax, eax
0x18003e873  jz      short loc_18003E88E
0x18003e875  mov     r8d, eax
0x18003e878  lea     rdx, a0x08x_0; "0x%08x"
0x18003e87f  mov     ecx, 0C0000409h; dwEventID
0x18003e884  call    XspLogEvent
0x18003e889  jmp     loc_18003EA08
0x18003e88e  cmp     [rsp+0F8h+arg_8], r13d
0x18003e896  jnz     loc_18003EA08
0x18003e89c  lea     r9, aGettingHighest_0; "Getting highest version ASP.NET isapi i"...
0x18003e8a3  mov     [rsp+0F8h+var_D8], r13; unsigned __int16 *
0x18003e8a8  xor     r8d, r8d; unsigned int
0x18003e8ab  lea     rdx, aGethighestvers; "GetHighestVersion"
0x18003e8b2  mov     ecx, ebx; int
0x18003e8b4  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e8b9  xor     edx, edx; struct ASPNETVER *
0x18003e8bb  lea     rcx, [rsp+0F8h+var_C8]; this
0x18003e8c0  call    ?InitHighestInfo@CRegInfo@@QEAAJPEAVASPNETVER@@@Z; CRegInfo::InitHighestInfo(ASPNETVER *)
0x18003e8c5  movzx   ebx, ax
0x18003e8c8  lea     r9, aGettingHighest_0; "Getting highest version ASP.NET isapi i"...
0x18003e8cf  mov     ecx, eax
0x18003e8d1  mov     [rsp+0F8h+var_D8], r13; unsigned __int16 *
0x18003e8d6  mov     r15d, 490h
0x18003e8dc  lea     rdx, aGettingHighest_0; "Getting highest version ASP.NET isapi i"...
0x18003e8e3  cmp     ebx, r15d
0x18003e8e6  mov     edi, eax
0x18003e8e8  cmovz   ecx, r13d; int
0x18003e8ec  xor     r8d, r8d; unsigned int
0x18003e8ef  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e8f4  cmp     ebx, r15d
0x18003e8f7  jnz     short loc_18003E901
0x18003e8f9  mov     edi, r13d
0x18003e8fc  jmp     loc_18003EA08
0x18003e901  test    edi, edi
0x18003e903  jnz     loc_18003EA08
0x18003e909  lea     rbx, aLoadisapi; "LoadIsapi"
0x18003e910  mov     [rsp+0F8h+var_D8], r13; unsigned __int16 *
0x18003e915  lea     r15d, [rdi+1]
0x18003e919  mov     rdx, rbx; char *
0x18003e91c  mov     ecx, r15d; int
0x18003e91f  lea     r9, aLoadingPreviou_0; "Loading previously installed ASP.NET is"...
0x18003e926  xor     r8d, r8d; unsigned int
0x18003e929  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e92e  mov     rcx, [rsp+0F8h+String1]; String1
0x18003e933  lea     rdx, ?s_wszIsapiFullPath@Names@@0PAGA; String2
0x18003e93a  call    cs:__imp__wcsicmp
0x18003e940  test    eax, eax
0x18003e942  jnz     short loc_18003E967
0x18003e944  mov     edi, 8000FFFFh
0x18003e949  mov     [rsp+0F8h+var_D8], r13; unsigned __int16 *
0x18003e94e  mov     ecx, edi; int
0x18003e950  lea     r9, aLoadingPreviou; "Loading previously installed ASP.NET is"...
0x18003e957  xor     r8d, r8d; unsigned int
0x18003e95a  mov     rdx, rbx; char *
0x18003e95d  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e962  jmp     loc_18003EA08
0x18003e967  mov     rcx, [rsp+0F8h+String1]; lpLibFileName
0x18003e96c  xor     edx, edx; hFile
0x18003e96e  lea     r8d, [rdx+8]; dwFlags
0x18003e972  call    cs:__imp_LoadLibraryExW
0x18003e978  lea     r9, aLoadingPreviou_0; "Loading previously installed ASP.NET is"...
0x18003e97f  mov     [rsp+0F8h+var_D8], r13; unsigned __int16 *
0x18003e984  xor     r8d, r8d; unsigned int
0x18003e987  mov     rdx, rbx; char *
0x18003e98a  xor     ecx, ecx; int
0x18003e98c  mov     rsi, rax
0x18003e98f  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e994  test    rsi, rsi
0x18003e997  jnz     short loc_18003E9A2
0x18003e999  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003e99e  mov     edi, eax
0x18003e9a0  jmp     short loc_18003EA08
0x18003e9a2  lea     rdx, aUnregisterisap; "UnregisterISAPI"
0x18003e9a9  mov     rcx, rsi; hModule
0x18003e9ac  call    cs:__imp_GetProcAddress
0x18003e9b2  mov     rbx, rax
0x18003e9b5  test    rax, rax
0x18003e9b8  jz      short loc_18003E999
0x18003e9ba  lea     r9, aUseTheHighestV; "Use the highest version DLL to uninstal"...
0x18003e9c1  mov     [rsp+0F8h+var_D8], r13; unsigned __int16 *
0x18003e9c6  xor     r8d, r8d; unsigned int
0x18003e9c9  lea     rdx, aUnregisterisap; "UnregisterISAPI"
0x18003e9d0  mov     ecx, r15d; int
0x18003e9d3  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e9d8  mov     edx, ebp
0x18003e9da  mov     ecx, r15d
0x18003e9dd  mov     rax, rbx
0x18003e9e0  call    cs:__guard_dispatch_icall_fptr
0x18003e9e6  lea     r9, aUseTheHighestV; "Use the highest version DLL to uninstal"...
0x18003e9ed  mov     [rsp+0F8h+var_D8], r13; unsigned __int16 *
0x18003e9f2  mov     ecx, eax; int
0x18003e9f4  lea     rdx, aUnregisterisap; "UnregisterISAPI"
0x18003e9fb  xor     r8d, r8d; unsigned int
0x18003e9fe  mov     edi, eax
0x18003ea00  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003ea05  mov     [r14], r15d
0x18003ea08  lea     r9, aDetectAndSeeIf; "Detect and see if we have to load the h"...
0x18003ea0f  mov     [rsp+0F8h+var_D8], r13; unsigned __int16 *
0x18003ea14  xor     r8d, r8d; unsigned int
0x18003ea17  lea     rdx, aUninstallallus; "UninstallAllUsingHighest"
0x18003ea1e  mov     ecx, edi; int
0x18003ea20  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003ea25  test    rsi, rsi
0x18003ea28  jz      short loc_18003EA33
0x18003ea2a  mov     rcx, rsi; hLibModule
0x18003ea2d  call    cs:__imp_FreeLibrary
0x18003ea33  lea     rcx, [rsp+0F8h+var_C8]; this
0x18003ea38  call    ??1CRegInfo@@QEAA@XZ; CRegInfo::~CRegInfo(void)
0x18003ea3d  lea     r11, [rsp+0F8h+var_28]
0x18003ea45  mov     eax, edi
0x18003ea47  mov     rbx, [r11+30h]
0x18003ea4b  mov     rbp, [r11+48h]
0x18003ea4f  mov     rsp, r11
0x18003ea52  pop     r15
0x18003ea54  pop     r14
0x18003ea56  pop     r13
0x18003ea58  pop     rdi
0x18003ea59  pop     rsi
0x18003ea5a  retn
```
