# CPxeProvider::Initialize(tagPXE_PROVIDER *)

- ea: `0x1800041c4`
- end: `0x180004657`
- name: `?Initialize@CPxeProvider@@QEAAKPEAUtagPXE_PROVIDER@@@Z`
- size: `1171`
- prototype: `unsigned int __fastcall(CPxeProvider *__hidden this, struct tagPXE_PROVIDER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000523c`

## callees

- `0x180002a30`
- `0x1800041c4`
- `0x180004848`
- `0x1800049d8`
- `0x180004ab4`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000432e`
- `KERNEL32!GetLastError` at `0x180004497`
- `KERNEL32!GetLastError` at `0x18000432e`
- `KERNEL32!GetLastError` at `0x180004497`
- `KERNEL32!EnterCriticalSection` at `0x18000421a`
- `KERNEL32!EnterCriticalSection` at `0x18000421a`
- `KERNEL32!LeaveCriticalSection` at `0x1800045d3`
- `KERNEL32!LeaveCriticalSection` at `0x1800045d3`
- `KERNEL32!LoadLibraryExW` at `0x180004303`
- `KERNEL32!LoadLibraryExW` at `0x180004303`
- `KERNEL32!GetProcAddress` at `0x180004470`
- `KERNEL32!GetProcAddress` at `0x180004470`
- `ADVAPI32!RegCloseKey` at `0x18000426d`
- `ADVAPI32!RegCloseKey` at `0x1800045e9`
- `ADVAPI32!RegCloseKey` at `0x18000426d`
- `ADVAPI32!RegCloseKey` at `0x1800045e9`
- `ADVAPI32!RegOpenKeyExW` at `0x18000429a`
- `ADVAPI32!RegOpenKeyExW` at `0x1800042d7`
- `ADVAPI32!RegOpenKeyExW` at `0x18000429a`
- `ADVAPI32!RegOpenKeyExW` at `0x1800042d7`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000422c`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000424d`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000422c`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000424d`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000438b`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800043e4`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000454f`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800045c1`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180004646`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000438b`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800043e4`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000454f`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800045c1`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180004646`
- `WdsCommonLib!WdsGetFileVersion` at `0x180004410`
- `WdsCommonLib!WdsGetFileVersion` at `0x180004410`

## string_xrefs

- `0x18000428c`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE\Providers`
- `0x180004459`: `[%s] Loaded DLL [%s], version %u.%u.%u.%u`

## pseudocode

```c
__int64 __fastcall CPxeProvider::Initialize(CPxeProvider *this, struct tagPXE_PROVIDER *a2)
{
  int v2; // ebp
  const unsigned __int16 **p_pwszName; // r14
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  __int64 LastError; // rdi
  struct _RTL_CRITICAL_SECTION *v8; // r13
  LPCWSTR *v9; // rsi
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  HMODULE Library; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned int v19; // edx
  unsigned __int16 *v20; // rax
  FARPROC ProcAddress; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned int v27; // eax
  bool v28; // zf
  PHKEY phkResult; // [rsp+20h] [rbp-78h]
  __int64 v31; // [rsp+28h] [rbp-70h]
  unsigned __int16 *v32; // [rsp+30h] [rbp-68h]
  __int64 v33; // [rsp+38h] [rbp-60h]
  int v34; // [rsp+40h] [rbp-58h]
  HKEY hKey; // [rsp+50h] [rbp-48h] BYREF
  unsigned int v36; // [rsp+A8h] [rbp+10h] BYREF
  unsigned int v37; // [rsp+B0h] [rbp+18h] BYREF

  v2 = 0;
  p_pwszName = (const unsigned __int16 **)&a2->pwszName;
  hKey = 0;
  v37 = 0;
  v36 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 112);
  if ( !a2 )
  {
    LODWORD(LastError) = 87;
    goto LABEL_11;
  }
  Trace(0x20000u, L"Initializing %s Provider using '%s'.", *p_pwszName, a2->pwszFilePath);
  v8 = v6;
  EnterCriticalSection(v6);
  LODWORD(LastError) = DuplicateStringW(*p_pwszName, (unsigned __int16 **)this);
  if ( !(_DWORD)LastError )
  {
    v9 = (LPCWSTR *)((char *)this + 8);
    LODWORD(LastError) = DuplicateStringW(a2->pwszFilePath, (unsigned __int16 **)this + 1);
    if ( !(_DWORD)LastError )
    {
      v10 = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE\\Providers",
              0,
              0xF013Fu,
              &hKey);
      LODWORD(LastError) = ElValidateWin32_1(v10, v11, v12, 149);
      if ( !(_DWORD)LastError )
      {
        v13 = RegOpenKeyExW(hKey, *(LPCWSTR *)this, 0, 0xF003Fu, (PHKEY)this + 5);
        LODWORD(LastError) = ElValidateWin32_1(v13, v14, v15, 157);
        if ( !(_DWORD)LastError )
        {
          Library = LoadLibraryExW(*v9, 0, 8u);
          *((_QWORD *)this + 2) = Library;
          if ( (unsigned int)ElValidateGleTrue(Library == 0, v17, v18, 167) )
          {
            LastError = GetLastError();
            Trace(0x80000u, L"[%s] Failed to load Provider Module (rc=%u)", *(_QWORD *)this, LastError);
            v19 = -1056505597;
            v34 = LastError;
            LODWORD(v33) = 5;
            v32 = *(unsigned __int16 **)this;
            v20 = (unsigned __int16 *)*v9;
          }
          else
          {
            if ( (int)WdsGetFileVersion(*v9, &v37, &v36) >= 0 )
            {
              LODWORD(phkResult) = HIWORD(v37);
              Trace(
                0x20000u,
                L"[%s] Loaded DLL [%s], version %u.%u.%u.%u",
                *(_QWORD *)this,
                *v9,
                phkResult,
                (unsigned __int16)v37,
                HIWORD(v36),
                (unsigned __int16)v36);
            }
            ProcAddress = GetProcAddress(*((HMODULE *)this + 2), "PxeProviderInitialize");
            *((_QWORD *)this + 4) = ProcAddress;
            if ( !(unsigned int)ElValidateGleTrue(ProcAddress == 0, v22, v23, 210) )
            {
              v24 = (*((__int64 (__fastcall **)(CPxeProvider *, _QWORD))this + 4))(this, *((_QWORD *)this + 5));
              v27 = ElValidateWin32_1(v24, v25, v26, 232);
              LODWORD(LastError) = v27;
              if ( v27 )
              {
                Trace(0x80000u, L"[%s] Initialization failed (rc=%u)", *(_QWORD *)this, v27);
                LODWORD(v33) = 5;
                LODWORD(v31) = 1;
                CEventLog::Log(
                  (CEventLog *)qword_18001CC40,
                  0xC1070105,
                  3,
                  1,
                  *(_QWORD *)this,
                  v31,
                  *v9,
                  v33,
                  LastError);
                v2 = 1;
              }
              else
              {
                v28 = *((_QWORD *)this + 6) == 0;
                v2 = 1;
                *((_DWORD *)this + 6) = 1;
                if ( !v28 && *((_QWORD *)this + 8) )
                {
                  Trace(0x20000u, L"%s Provider initialized successfully.", *p_pwszName);
                  goto LABEL_23;
                }
                Trace(
                  0x80000u,
                  L"[%s] Provider did not register required callbacks. Unloading Provider.",
                  *(_QWORD *)this);
                LODWORD(LastError) = -1056505593;
                LODWORD(v31) = 1;
                CEventLog::Log((CEventLog *)qword_18001CC40, 0xC1070107, 2, 1, *(_QWORD *)this, v31, *v9);
              }
              v6 = v8;
LABEL_11:
              CPxeProvider::Shutdown(this);
              CEventLog::Log((CEventLog *)qword_18001CC40, a2->bIsCritical - 1056505592, 2);
              if ( !v2 )
                goto LABEL_25;
              goto LABEL_24;
            }
            LastError = GetLastError();
            Trace(
              0x80000u,
              L"[%s] Provider Module does not export PxeProviderInitialize initialization function (rc=%u)",
              *(_QWORD *)this,
              LastError);
            v19 = -1056505596;
            v34 = LastError;
            LODWORD(v33) = 5;
            v32 = (unsigned __int16 *)*v9;
            v20 = *(unsigned __int16 **)this;
          }
          LODWORD(v31) = 1;
          CEventLog::Log((CEventLog *)qword_18001CC40, v19, 3, 1, v20, v31, v32, v33, v34);
        }
      }
    }
  }
  v2 = 1;
  v6 = v8;
  if ( (_DWORD)LastError )
    goto LABEL_11;
LABEL_23:
  LODWORD(v31) = 1;
  CEventLog::Log((CEventLog *)qword_18001CC40, 0x41070106u, 2, 1, *(_QWORD *)this, v31, *((_QWORD *)this + 1));
  v6 = v8;
LABEL_24:
  LeaveCriticalSection(v6);
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800041c4  mov     rax, rsp
0x1800041c7  push    rbx
0x1800041c8  push    rbp
0x1800041c9  push    rsi
0x1800041ca  push    rdi
0x1800041cb  push    r13
0x1800041cd  push    r14
0x1800041cf  push    r15
0x1800041d1  sub     rsp, 60h
0x1800041d5  xor     ebp, ebp
0x1800041d7  lea     r14, [rdx+8]
0x1800041db  mov     [rax-48h], rbp
0x1800041df  mov     r15, rdx
0x1800041e2  mov     [rax+18h], ebp
0x1800041e5  mov     rbx, rcx
0x1800041e8  mov     [rax+10h], ebp
0x1800041eb  lea     rsi, [rcx+70h]
0x1800041ef  test    rdx, rdx
0x1800041f2  jnz     short loc_1800041FC
0x1800041f4  lea     edi, [rdx+57h]
0x1800041f7  jmp     loc_1800043A7
0x1800041fc  mov     r9, [rdx+10h]
0x180004200  mov     ecx, 20000h; unsigned int
0x180004205  mov     r8, [r14]
0x180004208  lea     rdx, aInitializingSP; "Initializing %s Provider using '%s'."
0x18000420f  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x180004214  mov     rcx, rsi; lpCriticalSection
0x180004217  mov     r13, rsi
0x18000421a  call    cs:__imp_EnterCriticalSection
0x180004221  nop     dword ptr [rax+rax+00h]
0x180004226  mov     rcx, [r14]
0x180004229  mov     rdx, rbx
0x18000422c  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180004233  nop     dword ptr [rax+rax+00h]
0x180004238  mov     edi, eax
0x18000423a  test    eax, eax
0x18000423c  jnz     loc_180004397
0x180004242  mov     rcx, [r15+10h]
0x180004246  lea     rsi, [rbx+8]
0x18000424a  mov     rdx, rsi
0x18000424d  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180004254  nop     dword ptr [rax+rax+00h]
0x180004259  mov     edi, eax
0x18000425b  test    eax, eax
0x18000425d  jnz     loc_180004397
0x180004263  mov     rcx, [rsp+98h+hKey]; hKey
0x180004268  test    rcx, rcx
0x18000426b  jz      short loc_180004279
0x18000426d  call    cs:__imp_RegCloseKey
0x180004274  nop     dword ptr [rax+rax+00h]
0x180004279  lea     rax, [rsp+98h+hKey]
0x18000427e  mov     r9d, 0F013Fh; samDesired
0x180004284  xor     r8d, r8d; ulOptions
0x180004287  mov     [rsp+98h+phkResult], rax; phkResult
0x18000428c  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\WD"...
0x180004293  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000429a  call    cs:__imp_RegOpenKeyExW
0x1800042a1  nop     dword ptr [rax+rax+00h]
0x1800042a6  mov     ecx, eax
0x1800042a8  mov     r9d, 95h
0x1800042ae  call    ElValidateWin32_1
0x1800042b3  mov     edi, eax
0x1800042b5  test    eax, eax
0x1800042b7  jnz     loc_180004397
0x1800042bd  mov     rdx, [rbx]; lpSubKey
0x1800042c0  lea     rbp, [rbx+28h]
0x1800042c4  mov     rcx, [rsp+98h+hKey]; hKey
0x1800042c9  mov     r9d, 0F003Fh; samDesired
0x1800042cf  xor     r8d, r8d; ulOptions
0x1800042d2  mov     [rsp+98h+phkResult], rbp; phkResult
0x1800042d7  call    cs:__imp_RegOpenKeyExW
0x1800042de  nop     dword ptr [rax+rax+00h]
0x1800042e3  mov     ecx, eax
0x1800042e5  mov     r9d, 9Dh
0x1800042eb  call    ElValidateWin32_1
0x1800042f0  mov     edi, eax
0x1800042f2  test    eax, eax
0x1800042f4  jnz     loc_180004397
0x1800042fa  mov     rcx, [rsi]; lpLibFileName
0x1800042fd  lea     r8d, [rax+8]; dwFlags
0x180004301  xor     edx, edx; hFile
0x180004303  call    cs:__imp_LoadLibraryExW
0x18000430a  nop     dword ptr [rax+rax+00h]
0x18000430f  xor     ecx, ecx
0x180004311  mov     r9d, 0A7h
0x180004317  test    rax, rax
0x18000431a  mov     [rbx+10h], rax
0x18000431e  setz    cl
0x180004321  call    ElValidateGleTrue
0x180004326  test    eax, eax
0x180004328  jz      loc_1800043FD
0x18000432e  call    cs:__imp_GetLastError
0x180004335  nop     dword ptr [rax+rax+00h]
0x18000433a  mov     r8, [rbx]
0x18000433d  lea     rdx, aSFailedToLoadP; "[%s] Failed to load Provider Module (rc"...
0x180004344  mov     r9d, eax
0x180004347  mov     ecx, 80000h; unsigned int
0x18000434c  mov     edi, eax
0x18000434e  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x180004353  mov     rax, [rbx]
0x180004356  mov     edx, 0C1070103h
0x18000435b  mov     [rsp+98h+var_58], edi
0x18000435f  mov     dword ptr [rsp+98h+var_60], 5
0x180004367  mov     [rsp+98h+var_68], rax
0x18000436c  mov     rax, [rsi]
0x18000436f  mov     ecx, 1
0x180004374  mov     dword ptr [rsp+98h+var_70], ecx
0x180004378  mov     r9d, ecx
0x18000437b  mov     [rsp+98h+phkResult], rax
0x180004380  lea     r8d, [rcx+2]
0x180004384  lea     rcx, qword_18001CC40
0x18000438b  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180004392  nop     dword ptr [rax+rax+00h]
0x180004397  mov     ebp, 1
0x18000439c  mov     rsi, r13
0x18000439f  test    edi, edi
0x1800043a1  jz      loc_180004597
0x1800043a7  mov     rcx, rbx; this
0x1800043aa  call    ?Shutdown@CPxeProvider@@QEAAKXZ; CPxeProvider::Shutdown(void)
0x1800043af  mov     eax, [r15+18h]
0x1800043b3  lea     rcx, qword_18001CC40
0x1800043ba  neg     eax
0x1800043bc  mov     dword ptr [rsp+98h+var_68], edi
0x1800043c0  mov     rax, [r14]
0x1800043c3  mov     r9d, 1
0x1800043c9  sbb     edx, edx
0x1800043cb  mov     dword ptr [rsp+98h+var_70], 5
0x1800043d3  neg     edx
0x1800043d5  mov     [rsp+98h+phkResult], rax
0x1800043da  add     edx, 0C1070108h
0x1800043e0  lea     r8d, [r9+1]
0x1800043e4  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x1800043eb  nop     dword ptr [rax+rax+00h]
0x1800043f0  test    ebp, ebp
0x1800043f2  jz      loc_1800045DF
0x1800043f8  jmp     loc_1800045D0
0x1800043fd  mov     rcx, [rsi]
0x180004400  lea     r8, [rsp+98h+arg_8]
0x180004408  lea     rdx, [rsp+98h+arg_10]
0x180004410  call    cs:__imp_WdsGetFileVersion
0x180004417  nop     dword ptr [rax+rax+00h]
0x18000441c  test    eax, eax
0x18000441e  js      short loc_180004465
0x180004420  mov     r8d, [rsp+98h+arg_8]
0x180004428  mov     edx, [rsp+98h+arg_10]
0x18000442f  mov     r9, [rsi]
0x180004432  movzx   ecx, r8w
0x180004436  mov     dword ptr [rsp+98h+var_60], ecx
0x18000443a  mov     ecx, 20000h; unsigned int
0x18000443f  movzx   eax, dx
0x180004442  shr     r8d, 10h
0x180004446  mov     dword ptr [rsp+98h+var_68], r8d
0x18000444b  mov     r8, [rbx]
0x18000444e  shr     edx, 10h
0x180004451  mov     dword ptr [rsp+98h+var_70], eax
0x180004455  mov     dword ptr [rsp+98h+phkResult], edx
0x180004459  lea     rdx, aSLoadedDllSVer; "[%s] Loaded DLL [%s], version %u.%u.%u."...
0x180004460  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x180004465  mov     rcx, [rbx+10h]; hModule
0x180004469  lea     rdx, ProcName; "PxeProviderInitialize"
0x180004470  call    cs:__imp_GetProcAddress
0x180004477  nop     dword ptr [rax+rax+00h]
0x18000447c  xor     ecx, ecx
0x18000447e  mov     r9d, 0D2h
0x180004484  test    rax, rax
0x180004487  mov     [rbx+20h], rax
0x18000448b  setz    cl
0x18000448e  call    ElValidateGleTrue
0x180004493  test    eax, eax
0x180004495  jz      short loc_1800044DD
0x180004497  call    cs:__imp_GetLastError
0x18000449e  nop     dword ptr [rax+rax+00h]
0x1800044a3  mov     r8, [rbx]
0x1800044a6  lea     rdx, aSProviderModul; "[%s] Provider Module does not export Px"...
0x1800044ad  mov     r9d, eax
0x1800044b0  mov     ecx, 80000h; unsigned int
0x1800044b5  mov     edi, eax
0x1800044b7  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x1800044bc  mov     rax, [rsi]
0x1800044bf  mov     edx, 0C1070104h
0x1800044c4  mov     [rsp+98h+var_58], edi
0x1800044c8  mov     dword ptr [rsp+98h+var_60], 5
0x1800044d0  mov     [rsp+98h+var_68], rax
0x1800044d5  mov     rax, [rbx]
0x1800044d8  jmp     loc_18000436F
0x1800044dd  mov     rdx, [rbp+0]
0x1800044e1  mov     rcx, rbx
0x1800044e4  mov     rax, [rbx+20h]
0x1800044e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ed  mov     ecx, eax
0x1800044ef  mov     r9d, 0E8h
0x1800044f5  call    ElValidateWin32_1
0x1800044fa  mov     edi, eax
0x1800044fc  test    eax, eax
0x1800044fe  jz      short loc_180004565
0x180004500  mov     r8, [rbx]
0x180004503  lea     rdx, aSInitializatio; "[%s] Initialization failed (rc=%u)"
0x18000450a  mov     r9d, eax
0x18000450d  mov     ecx, 80000h; unsigned int
0x180004512  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x180004517  mov     rax, [rsi]
0x18000451a  lea     rcx, qword_18001CC40
0x180004521  mov     [rsp+98h+var_58], edi
0x180004525  mov     esi, 1
0x18000452a  mov     dword ptr [rsp+98h+var_60], 5
0x180004532  mov     r9d, esi
0x180004535  mov     [rsp+98h+var_68], rax
0x18000453a  mov     edx, 0C1070105h
0x18000453f  mov     rax, [rbx]
0x180004542  lea     r8d, [rsi+2]
0x180004546  mov     dword ptr [rsp+98h+var_70], esi
0x18000454a  mov     [rsp+98h+phkResult], rax
0x18000454f  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180004556  nop     dword ptr [rax+rax+00h]
0x18000455b  mov     ebp, esi
0x18000455d  mov     rsi, r13
0x180004560  jmp     loc_1800043A7
0x180004565  cmp     qword ptr [rbx+30h], 0
0x18000456a  mov     ebp, 1
0x18000456f  mov     [rbx+18h], ebp
0x180004572  jz      loc_180004607
0x180004578  cmp     qword ptr [rbx+40h], 0
0x18000457d  jz      loc_180004607
0x180004583  mov     r8, [r14]
0x180004586  lea     rdx, aSProviderIniti; "%s Provider initialized successfully."
0x18000458d  mov     ecx, 20000h; unsigned int
0x180004592  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x180004597  mov     rax, [rbx+8]
0x18000459b  lea     rcx, qword_18001CC40
0x1800045a2  mov     [rsp+98h+var_68], rax
0x1800045a7  mov     r9d, ebp
0x1800045aa  mov     rax, [rbx]
0x1800045ad  mov     edx, 41070106h
0x1800045b2  mov     dword ptr [rsp+98h+var_70], ebp
0x1800045b6  mov     r8d, 2
0x1800045bc  mov     [rsp+98h+phkResult], rax
0x1800045c1  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x1800045c8  nop     dword ptr [rax+rax+00h]
0x1800045cd  mov     rsi, r13
0x1800045d0  mov     rcx, rsi; lpCriticalSection
0x1800045d3  call    cs:__imp_LeaveCriticalSection
0x1800045da  nop     dword ptr [rax+rax+00h]
0x1800045df  mov     rcx, [rsp+98h+hKey]; hKey
0x1800045e4  test    rcx, rcx
0x1800045e7  jz      short loc_1800045F5
0x1800045e9  call    cs:__imp_RegCloseKey
0x1800045f0  nop     dword ptr [rax+rax+00h]
0x1800045f5  mov     eax, edi
0x1800045f7  add     rsp, 60h
0x1800045fb  pop     r15
0x1800045fd  pop     r14
0x1800045ff  pop     r13
0x180004601  pop     rdi
0x180004602  pop     rsi
0x180004603  pop     rbp
0x180004604  pop     rbx
0x180004605  retn
0x180004607  mov     r8, [rbx]
0x18000460a  lea     rdx, aSProviderDidNo; "[%s] Provider did not register required"...
0x180004611  mov     ecx, 80000h; unsigned int
0x180004616  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x18000461b  mov     rax, [rsi]
0x18000461e  lea     rcx, qword_18001CC40
0x180004625  mov     [rsp+98h+var_68], rax
0x18000462a  mov     edi, 0C1070107h
0x18000462f  mov     rax, [rbx]
0x180004632  mov     r9d, ebp
0x180004635  mov     dword ptr [rsp+98h+var_70], ebp
0x180004639  mov     r8d, 2
0x18000463f  mov     edx, edi
0x180004641  mov     [rsp+98h+phkResult], rax
0x180004646  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000464d  nop     dword ptr [rax+rax+00h]
0x180004652  jmp     loc_18000455D
```
