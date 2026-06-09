# CFciPropertiesShellExt::IsFciUxEnabled(void)

- ea: `0x18000a460`
- end: `0x18000a6fb`
- name: `?IsFciUxEnabled@CFciPropertiesShellExt@@CA_NXZ`
- size: `667`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800096c0`

## callees

- `0x1800022d4`
- `0x1800083e0`
- `0x18000a460`
- `0x18000d368`
- `0x18001623c`
- `0x180016564`
- `0x180018f68`
- `0x18001a280`
- `0x18001a384`
- `0x18001a9f8`
- `0x18001ae30`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18000a5c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18000a5c3`

## string_xrefs

- `0x18000a601`: `SYSTEM\CurrentControlSet\Services\SrmSvc`

## pseudocode

```c
bool CFciPropertiesShellExt::IsFciUxEnabled(void)
{
  int LastFailureAsHRESULT; // eax
  char Hr; // al
  int v3; // eax
  char v4; // al
  bool v5; // [rsp+40h] [rbp-228h]
  unsigned int v6[2]; // [rsp+48h] [rbp-220h] BYREF
  LPVOID v7[3]; // [rsp+50h] [rbp-218h] BYREF
  unsigned int v8; // [rsp+68h] [rbp-200h] BYREF
  _com_error *v9; // [rsp+70h] [rbp-1F8h] BYREF
  const exception *v10; // [rsp+78h] [rbp-1F0h] BYREF
  void **v11; // [rsp+80h] [rbp-1E8h] BYREF
  int v12; // [rsp+88h] [rbp-1E0h]
  unsigned int v13; // [rsp+ACh] [rbp-1BCh]
  _OSVERSIONINFOW VersionInformation; // [rsp+130h] [rbp-138h] BYREF
  unsigned __int8 v15; // [rsp+24Ah] [rbp-1Eh]

  *(_QWORD *)v6 = &VersionInformation;
  *(_QWORD *)&VersionInformation.dwOSVersionInfoSize = L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp";
  *(_QWORD *)&VersionInformation.dwMinorVersion = L"CFciPropertiesShellExt::IsFciUxEnabled";
  *(_QWORD *)&VersionInformation.dwPlatformId = L"FCIPROPC";
  *(_DWORD *)&VersionInformation.szCSDVersion[2] = 139;
  *(_DWORD *)&VersionInformation.szCSDVersion[4] = 17;
  wcscpy(&VersionInformation.szCSDVersion[6], L"ÿ");
  *(_DWORD *)&VersionInformation.szCSDVersion[58] = 0x1000000;
  memset_0(&VersionInformation.szCSDVersion[10], 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v11, (const struct CSrmDebugInfo *)&VersionInformation, 0);
  try
  {
    v7[2] = 0;
    v7[1] = 0;
    v7[0] = (LPVOID)257;
    v6[0] = 0;
    if ( CSrmRegistryKey::Open(
           (CSrmRegistryKey *)v7,
           HKEY_LOCAL_MACHINE,
           L"%s",
           L"SOFTWARE\\Policies\\Microsoft\\Windows\\FCI")
      && CSrmRegistryKey::GetValue((HKEY *)v7, L"EnableManualUX", v6) )
    {
      v5 = v6[0] != 0;
    }
    else
    {
      memset_0(&VersionInformation, 0, 0x11Cu);
      VersionInformation.dwOSVersionInfoSize = 284;
      if ( !GetVersionExW(&VersionInformation) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v11, LastFailureAsHRESULT);
        Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v11);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v11, 0x9Du, Hr, 0);
      }
      v12 = 0;
      if ( v15 == 1 )
      {
        v5 = 0;
      }
      else
      {
        if ( (unsigned int)v15 - 2 > 1 )
        {
          v12 = -2147200234;
          v3 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v11);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v11, v3);
          v4 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v11);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v11, 0xB4u, v4, 0);
        }
        CSrmRegistryKey::Close((CSrmRegistryKey *)v7);
        v5 = CSrmRegistryKey::Open(
               (CSrmRegistryKey *)v7,
               HKEY_LOCAL_MACHINE,
               L"%s",
               L"SYSTEM\\CurrentControlSet\\Services\\SrmSvc");
      }
    }
    CSrmRegistryKey::~CSrmRegistryKey(v7);
  }
  catch ( long v8 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v11,
      v8,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp",
      L"FCIPROPC",
      L"CFciPropertiesShellExt::IsFciUxEnabled",
      0xB9u,
      v13);
  }
  catch ( _com_error *v9 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v11,
      v9,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp",
      L"FCIPROPC",
      L"CFciPropertiesShellExt::IsFciUxEnabled",
      0xB9u,
      v13);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v11,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp",
      L"FCIPROPC",
      L"CFciPropertiesShellExt::IsFciUxEnabled",
      0xB9u,
      v13);
  }
  catch ( const exception *v10 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v11,
      v10,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp",
      L"FCIPROPC",
      L"CFciPropertiesShellExt::IsFciUxEnabled",
      0xB9u,
      v13);
  }
  v7[2] = 0;
  v7[1] = 0;
  v7[0] = (LPVOID)257;
}

```

## disassembly

```asm
0x18000a460  mov     r11, rsp
0x18000a463  sub     rsp, 268h
0x18000a46a  mov     rax, cs:__security_cookie
0x18000a471  xor     rax, rsp
0x18000a474  mov     [rsp+268h+var_18], rax
0x18000a47c  lea     rax, [r11-138h]
0x18000a483  mov     qword ptr [rsp+268h+var_220], rax
0x18000a488  lea     rax, aBaseFsFsrmClie_1; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x18000a48f  mov     [r11-138h], rax
0x18000a496  lea     rax, aCfciproperties_5; "CFciPropertiesShellExt::IsFciUxEnabled"
0x18000a49d  mov     [r11-130h], rax
0x18000a4a4  lea     rax, aFcipropc; "FCIPROPC"
0x18000a4ab  mov     [r11-128h], rax
0x18000a4b2  mov     dword ptr [rsp+268h+VersionInformation.szCSDVersion+4], 8Bh
0x18000a4bd  mov     dword ptr [rsp+268h+VersionInformation.szCSDVersion+8], 11h
0x18000a4c8  mov     dword ptr [rsp+268h+VersionInformation.szCSDVersion+0Ch], 0FFh
0x18000a4d3  mov     dword ptr [rsp+268h+VersionInformation.szCSDVersion+74h], 1000000h
0x18000a4de  xor     edx, edx; Val
0x18000a4e0  lea     r8d, [rdx+60h]; Size
0x18000a4e4  lea     rcx, [r11-110h]; void *
0x18000a4eb  call    memset_0
0x18000a4f0  nop
0x18000a4f1  xor     r8d, r8d
0x18000a4f4  lea     rdx, [rsp+268h+VersionInformation]
0x18000a4fc  lea     rcx, [rsp+268h+var_1E8]
0x18000a504  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000a509  nop
0x18000a50a  mov     [rsp+268h+var_228], 0
0x18000a50f  mov     [rsp+268h+var_208], 0
0x18000a518  mov     [rsp+268h+var_210], 0
0x18000a521  mov     [rsp+268h+var_214], 0
0x18000a529  mov     [rsp+268h+var_218], 1
0x18000a531  mov     [rsp+268h+var_218], 101h
0x18000a539  mov     [rsp+268h+var_220], 0
0x18000a541  lea     r9, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18000a548  lea     r8, aS_0; "%s"
0x18000a54f  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18000a556  lea     rcx, [rsp+268h+var_218]; this
0x18000a55b  call    ?Open@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::Open(HKEY__ *,ushort const *,...)
0x18000a560  test    al, al
0x18000a562  jz      short loc_18000A58D
0x18000a564  lea     r8, [rsp+268h+var_220]; unsigned int *
0x18000a569  lea     rdx, aEnablemanualux; "EnableManualUX"
0x18000a570  lea     rcx, [rsp+268h+var_218]; this
0x18000a575  call    ?GetValue@CSrmRegistryKey@@QEAA_NPEBGPEAK_N@Z; CSrmRegistryKey::GetValue(ushort const *,ulong *,bool)
0x18000a57a  test    al, al
0x18000a57c  jz      short loc_18000A58D
0x18000a57e  cmp     [rsp+268h+var_220], 0
0x18000a583  setnz   [rsp+268h+var_228]
0x18000a588  jmp     loc_18000A62B
0x18000a58d  xor     edx, edx; Val
0x18000a58f  mov     r8d, 11Ch; Size
0x18000a595  lea     rcx, [rsp+268h+VersionInformation]; void *
0x18000a59d  call    memset_0
0x18000a5a2  mov     [rsp+268h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18000a5ad  mov     eax, [rsp+268h+var_1E0]
0x18000a5b4  mov     [rsp+268h+var_1E0], eax
0x18000a5bb  lea     rcx, [rsp+268h+VersionInformation]; lpVersionInformation
0x18000a5c3  call    cs:__imp_GetVersionExW
0x18000a5c9  test    eax, eax
0x18000a5cb  jz      loc_18000A674
0x18000a5d1  mov     [rsp+268h+var_1E0], 0
0x18000a5dc  movzx   ecx, [rsp+268h+var_1E]
0x18000a5e4  sub     ecx, 1
0x18000a5e7  jz      short loc_18000A626
0x18000a5e9  sub     ecx, 1
0x18000a5ec  jz      short loc_18000A5F7
0x18000a5ee  cmp     ecx, 1
0x18000a5f1  jnz     loc_18000A6AD
0x18000a5f7  lea     rcx, [rsp+268h+var_218]; this
0x18000a5fc  call    ?Close@CSrmRegistryKey@@QEAAXXZ; CSrmRegistryKey::Close(void)
0x18000a601  lea     r9, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sr"...
0x18000a608  lea     r8, aS_0; "%s"
0x18000a60f  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18000a616  lea     rcx, [rsp+268h+var_218]; this
0x18000a61b  call    ?Open@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::Open(HKEY__ *,ushort const *,...)
0x18000a620  mov     [rsp+268h+var_228], al
0x18000a624  jmp     short loc_18000A62B
0x18000a626  mov     [rsp+268h+var_228], 0
0x18000a62b  lea     rcx, [rsp+268h+var_218]; this
0x18000a630  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x18000a635  nop
0x18000a636  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000a63d  mov     [rsp+268h+var_1E8], rax
0x18000a645  lea     rcx, [rsp+268h+var_1E8]; this
0x18000a64d  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000a652  mov     al, [rsp+268h+var_228]
0x18000a656  mov     rcx, [rsp+268h+var_18]
0x18000a65e  xor     rcx, rsp; StackCookie
0x18000a661  call    __security_check_cookie
0x18000a666  add     rsp, 268h
0x18000a66d  retn
0x18000a66e  jmp     short loc_18000A636
0x18000a670  jmp     short loc_18000A636
0x18000a672  jmp     short loc_18000A636
0x18000a674  call    GetLastFailureAsHRESULT
0x18000a679  mov     edx, eax; int
0x18000a67b  lea     rcx, [rsp+268h+var_1E8]; this
0x18000a683  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000a688  lea     rcx, [rsp+268h+var_1E8]; this
0x18000a690  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000a695  mov     r8d, eax; char
0x18000a698  xor     r9d, r9d; unsigned __int16 *
0x18000a69b  mov     edx, 9Dh; unsigned int
0x18000a6a0  lea     rcx, [rsp+268h+var_1E8]; this
0x18000a6a8  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000a6ad  mov     [rsp+268h+var_1E0], 80045316h
0x18000a6b8  lea     rcx, [rsp+268h+var_1E8]; this
0x18000a6c0  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000a6c5  mov     edx, eax; int
0x18000a6c7  lea     rcx, [rsp+268h+var_1E8]; this
0x18000a6cf  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000a6d4  lea     rcx, [rsp+268h+var_1E8]; this
0x18000a6dc  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000a6e1  mov     r8d, eax; char
0x18000a6e4  xor     r9d, r9d; unsigned __int16 *
0x18000a6e7  mov     edx, 0B4h; unsigned int
0x18000a6ec  lea     rcx, [rsp+268h+var_1E8]; this
0x18000a6f4  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
