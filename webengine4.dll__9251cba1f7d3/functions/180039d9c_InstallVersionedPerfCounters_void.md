# InstallVersionedPerfCounters(void)

- ea: `0x180039d9c`
- end: `0x18003a2f5`
- name: `?InstallVersionedPerfCounters@@YAJXZ`
- size: `1369`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18003c1e8`

## callees

- `0x180007824`
- `0x1800382f0`
- `0x180038440`
- `0x180039214`
- `0x180039d9c`
- `0x18003a43c`
- `0x18003abe4`
- `0x18003b8c0`
- `0x18003fb10`
- `0x180040fa0`
- `0x18004d030`
- `0x18004d690`
- `0x18004d754`
- `0x180064810`
- `0x18006541c`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180039ebf`
- `KERNEL32!lstrlenW` at `0x180039ebf`
- `ucrtbase_clr0400!_wcsicmp` at `0x18003a061`
- `ucrtbase_clr0400!_wcsicmp` at `0x18003a075`
- `ucrtbase_clr0400!_wcsicmp` at `0x18003a061`
- `ucrtbase_clr0400!_wcsicmp` at `0x18003a075`
- `ADVAPI32!RegCloseKey` at `0x18003a287`
- `ADVAPI32!RegCloseKey` at `0x18003a287`
- `ADVAPI32!RegEnumKeyExW` at `0x180039fca`
- `ADVAPI32!RegEnumKeyExW` at `0x180039fca`
- `ADVAPI32!RegOpenKeyExW` at `0x180039f83`
- `ADVAPI32!RegOpenKeyExW` at `0x180039f83`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x18003a219`
- `loadperf!UnloadPerfCounterTextStringsW` at `0x18003a219`
- `loadperf!LoadPerfCounterTextStringsW` at `0x180039ee3`
- `loadperf!LoadPerfCounterTextStringsW` at `0x180039f01`
- `loadperf!LoadPerfCounterTextStringsW` at `0x180039ee3`
- `loadperf!LoadPerfCounterTextStringsW` at `0x180039f01`

## string_xrefs

- `0x180039f75`: `SYSTEM\CurrentControlSet\Services\`
- `0x180039dd6`: `Install the ASP.NET Performance counters`
- `0x18003a264`: `Install the ASP.NET Performance counters`
- `0x18003a26b`: `Install the ASP.NET Performance counters`
- `0x180039de5`: `InstallVersionedPerfCounters`

## pseudocode

```c
__int64 InstallVersionedPerfCounters(void)
{
  DWORD v0; // edi
  struct ServiceName *v1; // r12
  wchar_t *v2; // rsi
  wchar_t *v3; // r13
  wchar_t *v4; // r15
  unsigned int VersionedPerfKeys; // ebx
  int v6; // eax
  const unsigned __int16 *v7; // r8
  int PerfCounterTextStringsW; // eax
  unsigned int ServicePerfValue; // eax
  unsigned __int16 *v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned __int16 *v13; // rcx
  unsigned __int16 v14; // ax
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // r14
  struct ServiceName *v17; // rbx
  WCHAR *v18; // rcx
  __int64 v19; // rdx
  WCHAR v20; // ax
  WCHAR *v21; // rax
  int v22; // ecx
  DWORD cchName[2]; // [rsp+48h] [rbp-C0h] BYREF
  wchar_t *v25; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t *String2; // [rsp+60h] [rbp-A8h] BYREF
  wchar_t *String1; // [rsp+68h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+70h] [rbp-98h] BYREF
  WCHAR String[2]; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 v31[518]; // [rsp+7Ch] [rbp-8Ch] BYREF
  WCHAR Name[528]; // [rsp+488h] [rbp+380h] BYREF

  hKey = 0;
  String2 = 0;
  v0 = 0;
  v25 = 0;
  v1 = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  CSetupLogging::Log(1, "InstallVersionedPerfCounters", 0, "Install the ASP.NET Performance counters", 0);
  VersionedPerfKeys = CreateVersionedPerfKeys();
  if ( !VersionedPerfKeys )
  {
    String[0] = 0;
    VersionedPerfKeys = StringCchCatW(String, 0x208u, L"l \"");
    if ( !VersionedPerfKeys )
    {
      v6 = IsWow64();
      v7 = &Names::s_wszInstallDirectory64;
      if ( !v6 )
        v7 = &Names::s_wszInstallDirectory;
      VersionedPerfKeys = StringCchCatW(String, 0x208u, v7);
      if ( !VersionedPerfKeys )
      {
        VersionedPerfKeys = StringCchCatW(String, 0x208u, L"\\aspnet_perf.ini");
        if ( !VersionedPerfKeys )
        {
          VersionedPerfKeys = StringCchCatW(String, 0x208u, L"\"");
          if ( !VersionedPerfKeys )
          {
            if ( lstrlenW(String) - 4 >= 260 )
            {
              VersionedPerfKeys = -2147024690;
              goto LABEL_56;
            }
            if ( LoadPerfCounterTextStringsW(String, 1) )
            {
              UpdateIniFile(v31);
              PerfCounterTextStringsW = LoadPerfCounterTextStringsW(String, 1);
              if ( PerfCounterTextStringsW )
                goto LABEL_12;
            }
            VersionedPerfKeys = GetServicePerfValue(L"ASP.NET_4.0.30319", L"Library", &String2);
            if ( VersionedPerfKeys )
              goto LABEL_56;
            VersionedPerfKeys = GetServicePerfValue(L"ASP.NET_4.0.30319", L"Open", &v25);
            if ( VersionedPerfKeys )
            {
              v2 = v25;
              goto LABEL_56;
            }
            PerfCounterTextStringsW = RegOpenKeyExW(
                                        HKEY_LOCAL_MACHINE,
                                        L"SYSTEM\\CurrentControlSet\\Services\\",
                                        0,
                                        0x20019u,
                                        &hKey);
            v2 = v25;
            if ( PerfCounterTextStringsW )
            {
LABEL_12:
              VersionedPerfKeys = (unsigned __int16)PerfCounterTextStringsW | 0x80070000;
              if ( PerfCounterTextStringsW <= 0 )
                VersionedPerfKeys = PerfCounterTextStringsW;
            }
            else
            {
              do
              {
                cchName[0] = 522;
                VersionedPerfKeys = RegEnumKeyExW(hKey, v0, Name, cchName, 0, 0, 0, &ftLastWriteTime);
                if ( !VersionedPerfKeys && !(unsigned int)IsAspNet(Name) && wcscmp_0(Name, L"ASP.NET_4.0.30319") )
                {
                  String1 = 0;
                  v25 = 0;
                  GetServicePerfValue(Name, L"Library", &String1);
                  ServicePerfValue = GetServicePerfValue(Name, L"Open", &v25);
                  v3 = String1;
                  VersionedPerfKeys = ServicePerfValue;
                  v4 = v25;
                  if ( !String1 || !v25 || !_wcsicmp(String1, String2) && !_wcsicmp(v4, v2) )
                  {
                    v10 = (unsigned __int16 *)MemAlloc(saturated_mul(cchName[0] + 1, 2u));
                    if ( !v10 )
                      goto LABEL_54;
                    v11 = cchName[0] + 1;
                    if ( (unsigned __int64)(v11 - 1) > 0x7FFFFFFE )
                    {
                      VersionedPerfKeys = -2147024809;
                      if ( cchName[0] != -1 )
                      {
                        *v10 = 0;
                        goto LABEL_56;
                      }
                    }
                    else
                    {
                      v12 = 2147483646 - v11;
                      v13 = v10;
                      do
                      {
                        if ( !(v12 + v11) )
                          break;
                        v14 = *(unsigned __int16 *)((char *)v13 + (char *)Name - (char *)v10);
                        if ( !v14 )
                          break;
                        *v13++ = v14;
                        --v11;
                      }
                      while ( v11 );
                      v15 = v13 - 1;
                      if ( v11 )
                        v15 = v13;
                      VersionedPerfKeys = v11 == 0 ? 0x8007007A : 0;
                      *v15 = 0;
                    }
                    if ( VersionedPerfKeys )
                      goto LABEL_56;
                    v1 = PushServiceName(v1, v10);
                    if ( !v1 )
                    {
LABEL_54:
                      VersionedPerfKeys = -2147024882;
                      goto LABEL_56;
                    }
                  }
                  if ( v3 )
                  {
                    MemFree(v3);
                    v3 = 0;
                  }
                  if ( v4 )
                  {
                    MemFree(v4);
                    v4 = 0;
                  }
                }
                ++v0;
              }
              while ( VersionedPerfKeys != 259 );
              if ( v1 )
              {
                while ( 1 )
                {
                  v16 = *(unsigned __int16 **)v1;
                  v17 = (struct ServiceName *)*((_QWORD *)v1 + 1);
                  operator delete(v1, 0x10u);
                  v18 = String;
                  v19 = 520;
                  v1 = v17;
                  do
                  {
                    if ( v19 == -2147483126 )
                      break;
                    v20 = *(WCHAR *)((char *)v18 + (char *)L"u " - (char *)String);
                    if ( !v20 )
                      break;
                    *v18++ = v20;
                    --v19;
                  }
                  while ( v19 );
                  v21 = v18 - 1;
                  if ( v19 )
                    v21 = v18;
                  *v21 = 0;
                  VersionedPerfKeys = v19 == 0 ? 0x8007007A : 0;
                  if ( !v19 )
                    break;
                  VersionedPerfKeys = StringCchCatW(String, 0x208u, v16);
                  if ( VersionedPerfKeys )
                    break;
                  UnloadPerfCounterTextStringsW(String, 1);
                  DeletePerfKey(v16);
                  MemFree(v16);
                  if ( !v1 )
                    goto LABEL_52;
                }
              }
              else
              {
LABEL_52:
                VersionedPerfKeys = 0;
              }
            }
          }
        }
      }
    }
  }
LABEL_56:
  v22 = 0;
  if ( (_WORD)VersionedPerfKeys != 183 )
    v22 = VersionedPerfKeys;
  CSetupLogging::Log(v22, "Install the ASP.NET Performance counters", 0, "Install the ASP.NET Performance counters", 0);
  if ( hKey )
    RegCloseKey(hKey);
  if ( String2 )
    MemFree(String2);
  if ( v2 )
    MemFree(v2);
  if ( v3 )
    MemFree(v3);
  if ( v4 )
    MemFree(v4);
  return VersionedPerfKeys;
}

```

## disassembly

```asm
0x180039d9c  mov     rax, rsp
0x180039d9f  mov     [rax+8], rbx
0x180039da3  mov     [rax+10h], rsi
0x180039da7  mov     [rax+18h], rdi
0x180039dab  push    rbp
0x180039dac  push    r12
0x180039dae  push    r13
0x180039db0  push    r14
0x180039db2  push    r15
0x180039db4  lea     rbp, [rax-7D8h]
0x180039dbb  sub     rsp, 8B0h
0x180039dc2  mov     rax, cs:__security_cookie
0x180039dc9  xor     rax, rsp
0x180039dcc  mov     [rbp+7D0h+var_30], rax
0x180039dd3  xor     r14d, r14d
0x180039dd6  lea     r9, aInstallTheAspN; "Install the ASP.NET Performance counter"...
0x180039ddd  xor     r8d, r8d; unsigned int
0x180039de0  mov     [rsp+8D0h+hKey], r14
0x180039de5  lea     rdx, aInstallversion; "InstallVersionedPerfCounters"
0x180039dec  mov     [rsp+8D0h+String2], r14
0x180039df1  mov     edi, r14d
0x180039df4  mov     [rsp+8D0h+var_888], r14
0x180039df9  lea     ecx, [r14+1]; int
0x180039dfd  mov     [rsp+8D0h+phkResult], r14; unsigned __int16 *
0x180039e02  mov     r12d, r14d
0x180039e05  mov     esi, r14d
0x180039e08  mov     r13d, r14d
0x180039e0b  mov     r15d, r14d
0x180039e0e  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180039e13  call    ?CreateVersionedPerfKeys@@YAJXZ; CreateVersionedPerfKeys(void)
0x180039e18  mov     ebx, eax
0x180039e1a  test    eax, eax
0x180039e1c  jnz     loc_18003A257
0x180039e22  lea     r8, asc_180074000; "l \""
0x180039e29  mov     [rsp+8D0h+String], r14w
0x180039e2f  mov     edx, 208h; unsigned __int64
0x180039e34  lea     rcx, [rsp+8D0h+String]; unsigned __int16 *
0x180039e39  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180039e3e  mov     ebx, eax
0x180039e40  test    eax, eax
0x180039e42  jnz     loc_18003A257
0x180039e48  call    IsWow64
0x180039e4d  test    eax, eax
0x180039e4f  lea     rcx, ?s_wszInstallDirectory@Names@@0PAGA; ushort near * Names::s_wszInstallDirectory
0x180039e56  lea     r8, ?s_wszInstallDirectory64@Names@@0PAGA; ushort near * Names::s_wszInstallDirectory64
0x180039e5d  mov     edx, 208h; unsigned __int64
0x180039e62  cmovz   r8, rcx; unsigned __int16 *
0x180039e66  lea     rcx, [rsp+8D0h+String]; unsigned __int16 *
0x180039e6b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180039e70  mov     ebx, eax
0x180039e72  test    eax, eax
0x180039e74  jnz     loc_18003A257
0x180039e7a  lea     r8, aAspnetPerfIni; "\\aspnet_perf.ini"
0x180039e81  mov     edx, 208h; unsigned __int64
0x180039e86  lea     rcx, [rsp+8D0h+String]; unsigned __int16 *
0x180039e8b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180039e90  mov     ebx, eax
0x180039e92  test    eax, eax
0x180039e94  jnz     loc_18003A257
0x180039e9a  lea     r8, asc_180073488; "\""
0x180039ea1  mov     edx, 208h; unsigned __int64
0x180039ea6  lea     rcx, [rsp+8D0h+String]; unsigned __int16 *
0x180039eab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180039eb0  mov     ebx, eax
0x180039eb2  test    eax, eax
0x180039eb4  jnz     loc_18003A257
0x180039eba  lea     rcx, [rsp+8D0h+String]; lpString
0x180039ebf  call    cs:__imp_lstrlenW
0x180039ec5  sub     eax, 4
0x180039ec8  cmp     eax, 104h
0x180039ecd  jl      short loc_180039ED9
0x180039ecf  mov     ebx, 800700CEh
0x180039ed4  jmp     loc_18003A257
0x180039ed9  mov     edx, 1; bQuietModeArg
0x180039ede  lea     rcx, [rsp+8D0h+String]; lpCommandLine
0x180039ee3  call    cs:__imp_LoadPerfCounterTextStringsW
0x180039ee9  test    eax, eax
0x180039eeb  jz      short loc_180039F1E
0x180039eed  lea     rcx, [rsp+8D0h+var_85C]; unsigned __int16 *
0x180039ef2  call    ?UpdateIniFile@@YAXPEBG@Z; UpdateIniFile(ushort const *)
0x180039ef7  mov     edx, 1; bQuietModeArg
0x180039efc  lea     rcx, [rsp+8D0h+String]; lpCommandLine
0x180039f01  call    cs:__imp_LoadPerfCounterTextStringsW
0x180039f07  test    eax, eax
0x180039f09  jz      short loc_180039F1E
0x180039f0b  movzx   ebx, ax
0x180039f0e  or      ebx, 80070000h
0x180039f14  test    eax, eax
0x180039f16  cmovle  ebx, eax
0x180039f19  jmp     loc_18003A257
0x180039f1e  lea     r8, [rsp+8D0h+String2]; unsigned __int16 **
0x180039f23  lea     rdx, aLibrary; "Library"
0x180039f2a  lea     rcx, aAspNet4030319; "ASP.NET_4.0.30319"
0x180039f31  call    ?GetServicePerfValue@@YAJPEBG0PEAPEAG@Z; GetServicePerfValue(ushort const *,ushort const *,ushort * *)
0x180039f36  mov     ebx, eax
0x180039f38  test    eax, eax
0x180039f3a  jnz     loc_18003A257
0x180039f40  lea     r8, [rsp+8D0h+var_888]; unsigned __int16 **
0x180039f45  lea     rdx, aOpen; "Open"
0x180039f4c  lea     rcx, aAspNet4030319; "ASP.NET_4.0.30319"
0x180039f53  call    ?GetServicePerfValue@@YAJPEBG0PEAPEAG@Z; GetServicePerfValue(ushort const *,ushort const *,ushort * *)
0x180039f58  mov     ebx, eax
0x180039f5a  test    eax, eax
0x180039f5c  jnz     loc_18003A24D
0x180039f62  lea     rax, [rsp+8D0h+hKey]
0x180039f67  mov     r9d, 20019h; samDesired
0x180039f6d  xor     r8d, r8d; ulOptions
0x180039f70  mov     [rsp+8D0h+phkResult], rax; phkResult
0x180039f75  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\"
0x180039f7c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039f83  call    cs:__imp_RegOpenKeyExW
0x180039f89  mov     rsi, [rsp+8D0h+var_888]
0x180039f8e  test    eax, eax
0x180039f90  jnz     loc_180039F0B
0x180039f96  mov     rcx, [rsp+8D0h+hKey]; hKey
0x180039f9b  lea     rax, [rsp+8D0h+ftLastWriteTime]
0x180039fa0  mov     [rsp+8D0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180039fa5  lea     r9, [rsp+8D0h+cchName]; lpcchName
0x180039faa  mov     [rsp+8D0h+lpcchClass], r14; lpcchClass
0x180039faf  lea     r8, [rbp+7D0h+Name]; lpName
0x180039fb6  mov     [rsp+8D0h+lpClass], r14; lpClass
0x180039fbb  mov     edx, edi; dwIndex
0x180039fbd  mov     [rsp+8D0h+phkResult], r14; lpReserved
0x180039fc2  mov     [rsp+8D0h+cchName], 20Ah
0x180039fca  call    cs:__imp_RegEnumKeyExW
0x180039fd0  mov     ebx, eax
0x180039fd2  test    eax, eax
0x180039fd4  jnz     loc_18003A165
0x180039fda  lea     rcx, [rbp+7D0h+Name]; unsigned __int16 *
0x180039fe1  call    ?IsAspNet@@YAHPEAG@Z; IsAspNet(ushort *)
0x180039fe6  test    eax, eax
0x180039fe8  jnz     loc_18003A165
0x180039fee  lea     rdx, aAspNet4030319; "ASP.NET_4.0.30319"
0x180039ff5  lea     rcx, [rbp+7D0h+Name]; String1
0x180039ffc  call    wcscmp_0
0x18003a001  test    eax, eax
0x18003a003  jz      loc_18003A165
0x18003a009  lea     r8, [rsp+8D0h+String1]; unsigned __int16 **
0x18003a00e  mov     [rsp+8D0h+String1], r14
0x18003a013  lea     rdx, aLibrary; "Library"
0x18003a01a  mov     [rsp+8D0h+var_888], r14
0x18003a01f  lea     rcx, [rbp+7D0h+Name]; lpString
0x18003a026  call    ?GetServicePerfValue@@YAJPEBG0PEAPEAG@Z; GetServicePerfValue(ushort const *,ushort const *,ushort * *)
0x18003a02b  lea     r8, [rsp+8D0h+var_888]; unsigned __int16 **
0x18003a030  lea     rdx, aOpen; "Open"
0x18003a037  lea     rcx, [rbp+7D0h+Name]; lpString
0x18003a03e  call    ?GetServicePerfValue@@YAJPEBG0PEAPEAG@Z; GetServicePerfValue(ushort const *,ushort const *,ushort * *)
0x18003a043  mov     r13, [rsp+8D0h+String1]
0x18003a048  mov     ebx, eax
0x18003a04a  mov     r15, [rsp+8D0h+var_888]
0x18003a04f  test    r13, r13
0x18003a052  jz      short loc_18003A083
0x18003a054  test    r15, r15
0x18003a057  jz      short loc_18003A083
0x18003a059  mov     rdx, [rsp+8D0h+String2]; String2
0x18003a05e  mov     rcx, r13; String1
0x18003a061  call    cs:__imp__wcsicmp
0x18003a067  test    eax, eax
0x18003a069  jnz     loc_18003A145
0x18003a06f  mov     rdx, rsi; String2
0x18003a072  mov     rcx, r15; String1
0x18003a075  call    cs:__imp__wcsicmp
0x18003a07b  test    eax, eax
0x18003a07d  jnz     loc_18003A145
0x18003a083  mov     ecx, [rsp+8D0h+cchName]
0x18003a087  mov     eax, 2
0x18003a08c  inc     ecx
0x18003a08e  mul     rcx
0x18003a091  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003a098  cmovo   rax, rcx
0x18003a09c  mov     rcx, rax; unsigned __int64
0x18003a09f  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18003a0a4  mov     r8, rax
0x18003a0a7  test    rax, rax
0x18003a0aa  jz      loc_18003A246
0x18003a0b0  mov     ecx, [rsp+8D0h+cchName]
0x18003a0b4  mov     eax, 7FFFFFFEh
0x18003a0b9  inc     ecx
0x18003a0bb  mov     edx, ecx
0x18003a0bd  dec     rcx
0x18003a0c0  cmp     rcx, rax
0x18003a0c3  ja      short loc_18003A116
0x18003a0c5  mov     r9d, eax
0x18003a0c8  lea     r10, [rbp+7D0h+Name]
0x18003a0cf  sub     r9, rdx
0x18003a0d2  mov     rcx, r8
0x18003a0d5  sub     r10, r8
0x18003a0d8  lea     rax, [r9+rdx]
0x18003a0dc  test    rax, rax
0x18003a0df  jz      short loc_18003A0F8
0x18003a0e1  movzx   eax, word ptr [r10+rcx]
0x18003a0e6  test    ax, ax
0x18003a0e9  jz      short loc_18003A0F8
0x18003a0eb  mov     [rcx], ax
0x18003a0ee  add     rcx, 2
0x18003a0f2  sub     rdx, 1
0x18003a0f6  jnz     short loc_18003A0D8
0x18003a0f8  test    rdx, rdx
0x18003a0fb  lea     rax, [rcx-2]
0x18003a0ff  cmovnz  rax, rcx
0x18003a103  neg     rdx
0x18003a106  sbb     ebx, ebx
0x18003a108  not     ebx
0x18003a10a  and     ebx, 8007007Ah
0x18003a110  mov     [rax], r14w
0x18003a114  jmp     short loc_18003A126
0x18003a116  mov     eax, 80070057h
0x18003a11b  mov     ebx, eax
0x18003a11d  test    rdx, rdx
0x18003a120  jnz     loc_18003A240
0x18003a126  test    ebx, ebx
0x18003a128  jnz     loc_18003A257
0x18003a12e  mov     rdx, r8; unsigned __int16 *
0x18003a131  mov     rcx, r12; struct ServiceName *
0x18003a134  call    ?PushServiceName@@YAPEAUServiceName@@PEAU1@PEAG@Z; PushServiceName(ServiceName *,ushort *)
0x18003a139  mov     r12, rax
0x18003a13c  test    rax, rax
0x18003a13f  jz      loc_18003A246
0x18003a145  test    r13, r13
0x18003a148  jz      short loc_18003A155
0x18003a14a  mov     rcx, r13; lpMem
0x18003a14d  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18003a152  mov     r13, r14
0x18003a155  test    r15, r15
0x18003a158  jz      short loc_18003A165
0x18003a15a  mov     rcx, r15; lpMem
0x18003a15d  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18003a162  mov     r15, r14
0x18003a165  inc     edi
0x18003a167  cmp     ebx, 103h
0x18003a16d  jnz     loc_180039F96
0x18003a173  test    r12, r12
0x18003a176  jz      loc_18003A23B
0x18003a17c  lea     rdi, aU_0; "u "
0x18003a183  lea     rax, [rsp+8D0h+String]
0x18003a188  sub     rdi, rax
0x18003a18b  mov     r14, [r12]
0x18003a18f  mov     edx, 10h; unsigned __int64
0x18003a194  mov     rbx, [r12+8]
0x18003a199  mov     rcx, r12; void *
0x18003a19c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003a1a1  mov     r9d, 208h
0x18003a1a7  lea     rcx, [rsp+8D0h+String]
0x18003a1ac  mov     edx, r9d
0x18003a1af  mov     r12, rbx
0x18003a1b2  xor     r8d, r8d
0x18003a1b5  lea     rax, [rdx+7FFFFDF6h]
0x18003a1bc  test    rax, rax
0x18003a1bf  jz      short loc_18003A1D7
0x18003a1c1  movzx   eax, word ptr [rdi+rcx]
0x18003a1c5  test    ax, ax
0x18003a1c8  jz      short loc_18003A1D7
0x18003a1ca  mov     [rcx], ax
0x18003a1cd  add     rcx, 2
0x18003a1d1  sub     rdx, 1
0x18003a1d5  jnz     short loc_18003A1B5
0x18003a1d7  test    rdx, rdx
0x18003a1da  lea     rax, [rcx-2]
0x18003a1de  cmovnz  rax, rcx
0x18003a1e2  mov     [rax], r8w
0x18003a1e6  mov     rax, rdx
0x18003a1e9  neg     rax
0x18003a1ec  sbb     ebx, ebx
0x18003a1ee  not     ebx
0x18003a1f0  and     ebx, 8007007Ah
0x18003a1f6  test    rdx, rdx
0x18003a1f9  jz      short loc_18003A254
0x18003a1fb  mov     r8, r14; unsigned __int16 *
0x18003a1fe  lea     rcx, [rsp+8D0h+String]; unsigned __int16 *
0x18003a203  mov     rdx, r9; unsigned __int64
0x18003a206  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003a20b  mov     ebx, eax
0x18003a20d  test    eax, eax
0x18003a20f  jnz     short loc_18003A254
0x18003a211  lea     edx, [rax+1]; bQuietModeArg
0x18003a214  lea     rcx, [rsp+8D0h+String]; lpCommandLine
0x18003a219  call    cs:__imp_UnloadPerfCounterTextStringsW
0x18003a21f  mov     rcx, r14; lpSubKey
0x18003a222  call    ?DeletePerfKey@@YAJPEBG@Z; DeletePerfKey(ushort const *)
0x18003a227  mov     rcx, r14; lpMem
0x18003a22a  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18003a22f  xor     r14d, r14d
0x18003a232  test    r12, r12
0x18003a235  jnz     loc_18003A18B
0x18003a23b  mov     ebx, r14d
0x18003a23e  jmp     short loc_18003A257
0x18003a240  mov     [r8], r14w
0x18003a244  jmp     short loc_18003A257
0x18003a246  mov     ebx, 8007000Eh
0x18003a24b  jmp     short loc_18003A257
0x18003a24d  mov     rsi, [rsp+8D0h+var_888]
0x18003a252  jmp     short loc_18003A257
0x18003a254  xor     r14d, r14d
0x18003a257  mov     ecx, r14d
0x18003a25a  mov     [rsp+8D0h+phkResult], r14; unsigned __int16 *
0x18003a25f  cmp     bx, 0B7h
0x18003a264  lea     r9, aInstallTheAspN; "Install the ASP.NET Performance counter"...
0x18003a26b  lea     rdx, aInstallTheAspN; "Install the ASP.NET Performance counter"...
0x18003a272  cmovnz  ecx, ebx; int
0x18003a275  xor     r8d, r8d; unsigned int
  ... truncated ...
```
