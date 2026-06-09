# CScanInformation::ValidateRemoteNamespaceVolumePath(ushort const *)

- ea: `0x180053574`
- end: `0x18005383f`
- name: `?ValidateRemoteNamespaceVolumePath@CScanInformation@@CAXPEBG@Z`
- size: `715`
- prototype: `void __fastcall(LPCWSTR lpszFileName)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800513f8`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18000ad14`
- `0x180053574`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180075510`
- `0x180075eb8`
- `0x18007691c`
- `0x18007d23c`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180053761`
- `msvcrt!_wcsicmp` at `0x180053761`
- `ole32!CoTaskMemFree` at `0x18005368f`
- `ole32!CoTaskMemFree` at `0x180053780`
- `ole32!CoTaskMemFree` at `0x1800537aa`
- `ole32!CoTaskMemFree` at `0x1800537d4`
- `ole32!CoTaskMemFree` at `0x18005368f`
- `ole32!CoTaskMemFree` at `0x180053780`
- `ole32!CoTaskMemFree` at `0x1800537aa`
- `ole32!CoTaskMemFree` at `0x1800537d4`
- `KERNEL32!GetVolumeInformationW` at `0x180053743`
- `KERNEL32!GetVolumeInformationW` at `0x180053743`
- `KERNEL32!GetVolumePathNameW` at `0x180053710`
- `KERNEL32!GetVolumePathNameW` at `0x180053710`

## string_xrefs

- `0x1800535a6`: `base\fs\fsrm\service\pipeline\namespace.cpp`
- `0x1800535b2`: `CScanInformation::ValidateRemoteNamespaceVolumePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CScanInformation::ValidateRemoteNamespaceVolumePath(LPCWSTR lpszFileName)
{
  bool v2; // r9
  __int64 v3; // rbx
  DWORD v4; // r8d
  WCHAR *v5; // rbx
  char Hr; // al
  unsigned int v7; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR lpszVolumePathName; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v9[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v10[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v11[3]; // [rsp+70h] [rbp-90h] BYREF
  int v12; // [rsp+88h] [rbp-78h]
  int v13; // [rsp+8Ch] [rbp-74h]
  int v14; // [rsp+90h] [rbp-70h]
  _BYTE v15[96]; // [rsp+98h] [rbp-68h] BYREF
  int v16; // [rsp+F8h] [rbp-8h]
  void **v17; // [rsp+100h] [rbp+0h] BYREF
  int v18; // [rsp+108h] [rbp+8h]
  WCHAR FileSystemNameBuffer; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v20[126]; // [rsp+1B2h] [rbp+B2h] BYREF

  *(_QWORD *)v9 = v11;
  v11[0] = L"base\\fs\\fsrm\\service\\pipeline\\namespace.cpp";
  v11[1] = L"CScanInformation::ValidateRemoteNamespaceVolumePath";
  v11[2] = L"NAMESPCC";
  v12 = 580;
  v13 = 22;
  v14 = 255;
  v16 = 0x1000000;
  memset_0(v15, 0, sizeof(v15));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v17, (const struct CSrmDebugInfo *)v11, 0);
  lpszVolumePathName = 0;
  FileSystemNameBuffer = 0;
  memset_0(v20, 0, sizeof(v20));
  v10[2] = 0;
  v10[1] = 0;
  v10[0] = (LPVOID)257;
  v7 = 0;
  if ( CSrmRegistryKey::Open((CSrmRegistryKey *)v10, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\Windows\\FCI")
    && CSrmRegistryKey::GetValue((CSrmRegistryKey *)v10, L"RemoteFileSystemCheckDisable", &v7, v2)
    && v7
    || (v7 = 0, v9[0] = 0, !SrmGetRemotePathSMBProtolVersion(lpszFileName, &v7, v9))
    || v7 != 3
    || v9[0] )
  {
    CSrmRegistryKey::~CSrmRegistryKey(v10);
    CoTaskMemFree(0);
    lpszVolumePathName = 0;
    v17 = &CSrmFunctionTracer::`vftable';
  }
  else
  {
    v3 = -1;
    do
      ++v3;
    while ( lpszFileName[v3] );
    CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&lpszVolumePathName, v3 + 1);
    v4 = v3 + 2;
    v5 = lpszVolumePathName;
    if ( GetVolumePathNameW(lpszFileName, lpszVolumePathName, v4)
      && GetVolumeInformationW(v5, 0, 0, 0, 0, 0, &FileSystemNameBuffer, 0x40u) )
    {
      if ( _wcsicmp(&FileSystemNameBuffer, L"NTFS") )
      {
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v17, -2147200250);
        Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v17);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v17, 0x27Du, Hr, 0);
      }
      v18 = 0;
    }
    CSrmRegistryKey::~CSrmRegistryKey(v10);
    CoTaskMemFree(v5);
    lpszVolumePathName = 0;
    v17 = &CSrmFunctionTracer::`vftable';
  }
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v17);
}

```

## disassembly

```asm
0x180053574  push    rbp
0x180053576  push    rbx
0x180053577  push    rsi
0x180053578  push    rdi
0x180053579  lea     rbp, [rsp-148h]
0x180053581  sub     rsp, 248h
0x180053588  mov     rax, cs:__security_cookie
0x18005358f  xor     rax, rsp
0x180053592  mov     [rbp+160h+var_30], rax
0x180053599  mov     rdi, rcx
0x18005359c  lea     rax, [rsp+260h+var_1F0]
0x1800535a1  mov     qword ptr [rsp+260h+var_210], rax
0x1800535a6  lea     rax, aBaseFsFsrmServ_34; "base\\fs\\fsrm\\service\\pipeline\\name"...
0x1800535ad  mov     [rsp+260h+var_1F0], rax
0x1800535b2  lea     rax, aCscaninformati_5; "CScanInformation::ValidateRemoteNamespa"...
0x1800535b9  mov     [rsp+260h+var_1E8], rax
0x1800535be  lea     rax, aNamespcc; "NAMESPCC"
0x1800535c5  mov     [rbp+160h+var_1E0], rax
0x1800535c9  mov     [rbp+160h+var_1D8], 244h
0x1800535d0  mov     [rbp+160h+var_1D4], 16h
0x1800535d7  mov     [rbp+160h+var_1D0], 0FFh
0x1800535de  xor     esi, esi
0x1800535e0  mov     [rbp+160h+var_168], 1000000h
0x1800535e7  xor     edx, edx; Val
0x1800535e9  lea     r8d, [rsi+60h]; Size
0x1800535ed  lea     rcx, [rbp+160h+var_1C8]; void *
0x1800535f1  call    memset_0
0x1800535f6  nop
0x1800535f7  xor     r8d, r8d
0x1800535fa  lea     rdx, [rsp+260h+var_1F0]
0x1800535ff  lea     rcx, [rbp+160h+var_160]
0x180053603  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180053608  nop
0x180053609  mov     [rsp+260h+lpszVolumePathName], rsi
0x18005360e  mov     [rbp+160h+FileSystemNameBuffer], si
0x180053615  xor     edx, edx; Val
0x180053617  lea     r8d, [rsi+7Eh]; Size
0x18005361b  lea     rcx, [rbp+160h+var_AE]; void *
0x180053622  call    memset_0
0x180053627  mov     [rsp+260h+var_1F8], rsi
0x18005362c  mov     [rsp+260h+var_200], rsi
0x180053631  mov     [rsp+260h+var_208], 1
0x18005363a  mov     dword ptr [rsp+260h+var_208], 101h
0x180053642  mov     [rsp+260h+var_220], esi
0x180053646  lea     r8, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18005364d  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180053654  lea     rcx, [rsp+260h+var_208]; this
0x180053659  call    ?Open@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::Open(HKEY__ *,ushort const *,...)
0x18005365e  test    al, al
0x180053660  jz      short loc_1800536AF
0x180053662  lea     r8, [rsp+260h+var_220]; unsigned int *
0x180053667  lea     rdx, aRemotefilesyst; "RemoteFileSystemCheckDisable"
0x18005366e  lea     rcx, [rsp+260h+var_208]; this
0x180053673  call    ?GetValue@CSrmRegistryKey@@QEAA_NPEBGPEAK_N@Z; CSrmRegistryKey::GetValue(ushort const *,ulong *,bool)
0x180053678  test    al, al
0x18005367a  jz      short loc_1800536AF
0x18005367c  cmp     [rsp+260h+var_220], esi
0x180053680  jz      short loc_1800536AF
0x180053682  lea     rcx, [rsp+260h+var_208]; this
0x180053687  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x18005368c  nop
0x18005368d  xor     ecx, ecx; pv
0x18005368f  call    cs:__imp_CoTaskMemFree
0x180053695  mov     [rsp+260h+lpszVolumePathName], rsi
0x18005369a  mov     [rsp+260h+lpszVolumePathName], rsi
0x18005369f  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800536a6  mov     [rbp+160h+var_160], rax
0x1800536aa  jmp     loc_1800537EF
0x1800536af  mov     [rsp+260h+var_220], esi
0x1800536b3  mov     [rsp+260h+var_210], esi
0x1800536b7  lea     r8, [rsp+260h+var_210]; unsigned int *
0x1800536bc  lea     rdx, [rsp+260h+var_220]; unsigned int *
0x1800536c1  mov     rcx, rdi; DosPathName
0x1800536c4  call    ?SrmGetRemotePathSMBProtolVersion@@YA_NPEBGAEAK1@Z; SrmGetRemotePathSMBProtolVersion(ushort const *,ulong &,ulong &)
0x1800536c9  test    al, al
0x1800536cb  jz      loc_1800537C7
0x1800536d1  cmp     [rsp+260h+var_220], 3
0x1800536d6  jnz     loc_18005379D
0x1800536dc  cmp     [rsp+260h+var_210], esi
0x1800536e0  jnz     loc_18005379D
0x1800536e6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800536ea  inc     rbx
0x1800536ed  cmp     [rdi+rbx*2], si
0x1800536f1  jnz     short loc_1800536EA
0x1800536f3  lea     rdx, [rbx+1]; unsigned __int64
0x1800536f7  lea     rcx, [rsp+260h+lpszVolumePathName]; this
0x1800536fc  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x180053701  lea     r8d, [rbx+2]; cchBufferLength
0x180053705  mov     rbx, [rsp+260h+lpszVolumePathName]
0x18005370a  mov     rdx, rbx; lpszVolumePathName
0x18005370d  mov     rcx, rdi; lpszFileName
0x180053710  call    cs:__imp_GetVolumePathNameW
0x180053716  test    eax, eax
0x180053718  jz      short loc_180053772
0x18005371a  mov     [rsp+260h+nFileSystemNameSize], 40h ; '@'; nFileSystemNameSize
0x180053722  lea     rax, [rbp+160h+FileSystemNameBuffer]
0x180053729  mov     [rsp+260h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x18005372e  mov     [rsp+260h+lpFileSystemFlags], rsi; lpFileSystemFlags
0x180053733  mov     [rsp+260h+lpMaximumComponentLength], rsi; lpMaximumComponentLength
0x180053738  xor     r9d, r9d; lpVolumeSerialNumber
0x18005373b  xor     r8d, r8d; nVolumeNameSize
0x18005373e  xor     edx, edx; lpVolumeNameBuffer
0x180053740  mov     rcx, rbx; lpRootPathName
0x180053743  call    cs:__imp_GetVolumeInformationW
0x180053749  test    eax, eax
0x18005374b  jz      short loc_180053772
0x18005374d  mov     eax, [rbp+160h+var_158]
0x180053750  mov     [rbp+160h+var_158], eax
0x180053753  lea     rdx, aNtfs; "NTFS"
0x18005375a  lea     rcx, [rbp+160h+FileSystemNameBuffer]; String1
0x180053761  call    cs:__imp__wcsicmp
0x180053767  test    eax, eax
0x180053769  jnz     loc_180053813
0x18005376f  mov     [rbp+160h+var_158], esi
0x180053772  lea     rcx, [rsp+260h+var_208]; this
0x180053777  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x18005377c  nop
0x18005377d  mov     rcx, rbx; pv
0x180053780  call    cs:__imp_CoTaskMemFree
0x180053786  mov     [rsp+260h+lpszVolumePathName], rsi
0x18005378b  mov     [rsp+260h+lpszVolumePathName], rsi
0x180053790  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180053797  mov     [rbp+160h+var_160], rax
0x18005379b  jmp     short loc_1800537EF
0x18005379d  lea     rcx, [rsp+260h+var_208]; this
0x1800537a2  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x1800537a7  nop
0x1800537a8  xor     ecx, ecx; pv
0x1800537aa  call    cs:__imp_CoTaskMemFree
0x1800537b0  mov     [rsp+260h+lpszVolumePathName], rsi
0x1800537b5  mov     [rsp+260h+lpszVolumePathName], rsi
0x1800537ba  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800537c1  mov     [rbp+160h+var_160], rax
0x1800537c5  jmp     short loc_1800537EF
0x1800537c7  lea     rcx, [rsp+260h+var_208]; this
0x1800537cc  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x1800537d1  nop
0x1800537d2  xor     ecx, ecx; pv
0x1800537d4  call    cs:__imp_CoTaskMemFree
0x1800537da  mov     [rsp+260h+lpszVolumePathName], rsi
0x1800537df  mov     [rsp+260h+lpszVolumePathName], rsi
0x1800537e4  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800537eb  mov     [rbp+160h+var_160], rax
0x1800537ef  lea     rcx, [rbp+160h+var_160]; this
0x1800537f3  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800537f8  mov     rcx, [rbp+160h+var_30]
0x1800537ff  xor     rcx, rsp; StackCookie
0x180053802  call    __security_check_cookie
0x180053807  add     rsp, 248h
0x18005380e  pop     rdi
0x18005380f  pop     rsi
0x180053810  pop     rbx
0x180053811  pop     rbp
0x180053812  retn
0x180053813  mov     edx, 80045306h; int
0x180053818  lea     rcx, [rbp+160h+var_160]; this
0x18005381c  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180053821  lea     rcx, [rbp+160h+var_160]; this
0x180053825  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005382a  mov     r8d, eax; char
0x18005382d  xor     r9d, r9d; unsigned __int16 *
0x180053830  mov     edx, 27Dh; unsigned int
0x180053835  lea     rcx, [rbp+160h+var_160]; this
0x180053839  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
