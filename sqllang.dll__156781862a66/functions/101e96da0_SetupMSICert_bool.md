# SetupMSICert(bool)

- ea: `0x101e96da0`
- end: `0x101e97d5f`
- name: `?SetupMSICert@@YAJ_N@Z`
- size: `4031`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `5`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x10133a630`
- `0x10133a710`
- `0x1014dcdb0`
- `0x101e97d70`
- `0x101e97d80`

## callees

- `0x100401070`
- `0x100401433`
- `0x100403080`
- `0x1004076a0`
- `0x100430960`
- `0x100430d60`
- `0x10071db70`
- `0x100755b10`
- `0x100755bd0`
- `0x10149cf70`
- `0x1014be2a0`
- `0x1014c1830`
- `0x101e88ac0`
- `0x101e88fe0`
- `0x101e890c0`
- `0x101e90180`
- `0x101e96da0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x101e975a5`
- `KERNEL32!HeapFree` at `0x101e9764c`
- `KERNEL32!HeapFree` at `0x101e97735`
- `KERNEL32!HeapFree` at `0x101e978fe`
- `KERNEL32!HeapFree` at `0x101e97ab0`
- `KERNEL32!HeapFree` at `0x101e97c46`
- `KERNEL32!HeapFree` at `0x101e97cc2`
- `KERNEL32!HeapFree` at `0x101e97d10`
- `KERNEL32!HeapFree` at `0x101e975a5`
- `KERNEL32!HeapFree` at `0x101e9764c`
- `KERNEL32!HeapFree` at `0x101e97735`
- `KERNEL32!HeapFree` at `0x101e978fe`
- `KERNEL32!HeapFree` at `0x101e97ab0`
- `KERNEL32!HeapFree` at `0x101e97c46`
- `KERNEL32!HeapFree` at `0x101e97cc2`
- `KERNEL32!HeapFree` at `0x101e97d10`
- `KERNEL32!GetProcessHeap` at `0x101e97596`
- `KERNEL32!GetProcessHeap` at `0x101e9763d`
- `KERNEL32!GetProcessHeap` at `0x101e97726`
- `KERNEL32!GetProcessHeap` at `0x101e978ef`
- `KERNEL32!GetProcessHeap` at `0x101e97aa1`
- `KERNEL32!GetProcessHeap` at `0x101e97c37`
- `KERNEL32!GetProcessHeap` at `0x101e97cb3`
- `KERNEL32!GetProcessHeap` at `0x101e97d01`
- `KERNEL32!GetProcessHeap` at `0x101e97596`
- `KERNEL32!GetProcessHeap` at `0x101e9763d`
- `KERNEL32!GetProcessHeap` at `0x101e97726`
- `KERNEL32!GetProcessHeap` at `0x101e978ef`
- `KERNEL32!GetProcessHeap` at `0x101e97aa1`
- `KERNEL32!GetProcessHeap` at `0x101e97c37`
- `KERNEL32!GetProcessHeap` at `0x101e97cb3`
- `KERNEL32!GetProcessHeap` at `0x101e97d01`
- `KERNEL32!InitializeCriticalSection` at `0x101e96e75`
- `KERNEL32!InitializeCriticalSection` at `0x101e96e75`
- `KERNEL32!DeleteCriticalSection` at `0x101e975b0`
- `KERNEL32!DeleteCriticalSection` at `0x101e97657`
- `KERNEL32!DeleteCriticalSection` at `0x101e97740`
- `KERNEL32!DeleteCriticalSection` at `0x101e97909`
- `KERNEL32!DeleteCriticalSection` at `0x101e97abb`
- `KERNEL32!DeleteCriticalSection` at `0x101e97c51`
- `KERNEL32!DeleteCriticalSection` at `0x101e97ccd`
- `KERNEL32!DeleteCriticalSection` at `0x101e97d1b`
- `KERNEL32!DeleteCriticalSection` at `0x101e975b0`
- `KERNEL32!DeleteCriticalSection` at `0x101e97657`
- `KERNEL32!DeleteCriticalSection` at `0x101e97740`
- `KERNEL32!DeleteCriticalSection` at `0x101e97909`
- `KERNEL32!DeleteCriticalSection` at `0x101e97abb`
- `KERNEL32!DeleteCriticalSection` at `0x101e97c51`
- `KERNEL32!DeleteCriticalSection` at `0x101e97ccd`
- `KERNEL32!DeleteCriticalSection` at `0x101e97d1b`
- `ADVAPI32!CryptReleaseContext` at `0x101e974ba`
- `ADVAPI32!CryptReleaseContext` at `0x101e97610`
- `ADVAPI32!CryptReleaseContext` at `0x101e974ba`
- `ADVAPI32!CryptReleaseContext` at `0x101e97610`
- `secforwarder!CertFreeCertificateContext` at `0x101e97484`
- `secforwarder!CertFreeCertificateContext` at `0x101e975da`
- `secforwarder!CertFreeCertificateContext` at `0x101e97484`
- `secforwarder!CertFreeCertificateContext` at `0x101e975da`
- `secforwarder!CertCloseStore` at `0x101e97499`
- `secforwarder!CertCloseStore` at `0x101e975ef`
- `secforwarder!CertCloseStore` at `0x101e97499`
- `secforwarder!CertCloseStore` at `0x101e975ef`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101e979cb`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101e970f6`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101e9732b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101e970f6`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101e9732b`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101e96f07`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101e96f07`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101e97b93`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101e97b93`
- `sqldk!SystemThread_TlsIndex` at `0x101e96ec8`
- `sqldk!SystemThread_TlsIndex` at `0x101e96f1c`
- `sqldk!SystemThread_TlsIndex` at `0x101e97506`
- `sqldk!SystemThread_TlsIndex` at `0x101e97681`
- `sqldk!SystemThread_TlsIndex` at `0x101e977c9`
- `sqldk!SystemThread_TlsIndex` at `0x101e9784a`
- `sqldk!SystemThread_TlsIndex` at `0x101e9798c`
- `sqldk!SystemThread_TlsIndex` at `0x101e97b28`
- `sqldk!SystemThread_TlsOffset` at `0x101e96ed1`
- `sqldk!SystemThread_TlsOffset` at `0x101e96f25`
- `sqldk!SystemThread_TlsOffset` at `0x101e9750f`
- `sqldk!SystemThread_TlsOffset` at `0x101e9768a`
- `sqldk!SystemThread_TlsOffset` at `0x101e977d2`
- `sqldk!SystemThread_TlsOffset` at `0x101e97853`
- `sqldk!SystemThread_TlsOffset` at `0x101e97995`
- `sqldk!SystemThread_TlsOffset` at `0x101e97b31`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e96eea`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e96f40`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e9752a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e976a5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e977ed`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e9786e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e979b0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e97b4b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e96eea`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e96f40`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e9752a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e976a5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e977ed`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e9786e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e979b0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e97b4b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e971c5`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e9726a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e972f1`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e97575`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e97705`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e977a8`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e97836`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e978ce`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e97970`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e97a80`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e97c14`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e971c5`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e9726a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e972f1`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e97575`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e97705`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e977a8`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e97836`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e978ce`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e97970`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e97a80`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e97c14`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x101e97bc6`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x101e97be2`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x101e97bc6`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x101e97be2`
- `sqlmin!??0AutoForcePhysMaster@@QEAA@XZ` at `0x101e96df7`
- `sqlmin!??0AutoForcePhysMaster@@QEAA@XZ` at `0x101e96df7`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x101e97761`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x101e9792a`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x101e97adc`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x101e97c72`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x101e97cd9`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x101e97d27`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x101e97761`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x101e9792a`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x101e97adc`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x101e97c72`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x101e97cd9`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x101e97d27`
- `sqlmin!GetXdbServerGlobals` at `0x101e976c0`
- `sqlmin!GetXdbServerGlobals` at `0x101e9776f`
- `sqlmin!GetXdbServerGlobals` at `0x101e9777b`
- `sqlmin!GetXdbServerGlobals` at `0x101e97787`
- `sqlmin!GetXdbServerGlobals` at `0x101e97889`
- `sqlmin!GetXdbServerGlobals` at `0x101e97937`
- `sqlmin!GetXdbServerGlobals` at `0x101e97943`
- `sqlmin!GetXdbServerGlobals` at `0x101e9794f`
- `sqlmin!GetXdbServerGlobals` at `0x101e97aec`
- `sqlmin!GetXdbServerGlobals` at `0x101e97bb1`
- `sqlmin!GetXdbServerGlobals` at `0x101e97bef`
- `sqlmin!GetXdbServerGlobals` at `0x101e97bfc`
- `sqlmin!GetXdbServerGlobals` at `0x101e976c0`
- `sqlmin!GetXdbServerGlobals` at `0x101e9776f`
- `sqlmin!GetXdbServerGlobals` at `0x101e9777b`
- `sqlmin!GetXdbServerGlobals` at `0x101e97787`
- `sqlmin!GetXdbServerGlobals` at `0x101e97889`
- `sqlmin!GetXdbServerGlobals` at `0x101e97937`
- `sqlmin!GetXdbServerGlobals` at `0x101e97943`
- `sqlmin!GetXdbServerGlobals` at `0x101e9794f`
- `sqlmin!GetXdbServerGlobals` at `0x101e97aec`
- `sqlmin!GetXdbServerGlobals` at `0x101e97bb1`
- `sqlmin!GetXdbServerGlobals` at `0x101e97bef`
- `sqlmin!GetXdbServerGlobals` at `0x101e97bfc`
- `sqlfabric!GetManagedIdentityRegionalAuthNEndpoint` at `0x101e978a2`
- `sqlfabric!GetManagedIdentityRegionalAuthNEndpoint` at `0x101e978a2`
- `sqlfabric!GetServerManagedIdentityTypeWinFabProperty` at `0x101e9754a`
- `sqlfabric!GetServerManagedIdentityTypeWinFabProperty` at `0x101e9780d`
- `sqlfabric!GetServerManagedIdentityTypeWinFabProperty` at `0x101e9754a`
- `sqlfabric!GetServerManagedIdentityTypeWinFabProperty` at `0x101e9780d`
- `sqlfabric!GetAzureKeyVaultClientId` at `0x101e976d9`
- `sqlfabric!GetAzureKeyVaultClientId` at `0x101e976d9`
- `hostregdll!HostReg_GetSecretElements` at `0x101e970b9`
- `hostregdll!HostReg_GetSecretElements` at `0x101e970b9`
- `hostregdll!HostReg_FreeElementData` at `0x101e97588`
- `hostregdll!HostReg_FreeElementData` at `0x101e9762f`
- `hostregdll!HostReg_FreeElementData` at `0x101e97718`
- `hostregdll!HostReg_FreeElementData` at `0x101e978e1`
- `hostregdll!HostReg_FreeElementData` at `0x101e97a93`
- `hostregdll!HostReg_FreeElementData` at `0x101e97c29`
- `hostregdll!HostReg_FreeElementData` at `0x101e97ca5`
- `hostregdll!HostReg_FreeElementData` at `0x101e97588`
- `hostregdll!HostReg_FreeElementData` at `0x101e9762f`
- `hostregdll!HostReg_FreeElementData` at `0x101e97718`
- `hostregdll!HostReg_FreeElementData` at `0x101e978e1`
- `hostregdll!HostReg_FreeElementData` at `0x101e97a93`
- `hostregdll!HostReg_FreeElementData` at `0x101e97c29`
- `hostregdll!HostReg_FreeElementData` at `0x101e97ca5`
- `hostregdll!HostReg_GetSecret` at `0x101e96f94`
- `hostregdll!HostReg_GetSecret` at `0x101e96f94`

## string_xrefs

- `0x101e97a28`: `SetupMSICert`
- `0x101e97a53`: `SetupMSICert`

## pseudocode

```c
// Hidden C++ exception states: #wind=38
__int64 __fastcall SetupMSICert(unsigned __int8 a1)
{
  int v1; // esi
  const wchar_t *v2; // r13
  const wchar_t *v3; // rax
  wchar_t *v4; // rax
  const wchar_t *v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rdx
  int Secret; // ebx
  int SecretElements; // eax
  errno_t v13; // r14d
  struct __crt_locale_pointers *DefaultLocale; // r9
  const wchar_t *v15; // r8
  unsigned int v16; // r15d
  unsigned int v17; // ecx
  int v18; // r12d
  int v19; // ecx
  bool v20; // zf
  int v21; // esi
  const wchar_t *v22; // rdi
  struct __crt_locale_pointers *v23; // rax
  int v24; // r8d
  int v25; // r8d
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rax
  int ServerManagedIdentityTypeWinFabProperty; // eax
  HANDLE v30; // rax
  HANDLE v31; // rax
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v33; // rcx
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 v36; // rbx
  __int64 XdbServerGlobals; // rax
  int AzureKeyVaultClientId; // eax
  __int64 v39; // rdx
  __int64 v40; // rcx
  HANDLE v41; // rax
  unsigned int v43; // edi
  __int64 v44; // rdx
  __int64 v45; // rcx
  unsigned int v46; // ebx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rbx
  __int64 v51; // rax
  int v52; // eax
  _QWORD *v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rbx
  __int64 v56; // rax
  __int64 v57; // rbx
  __int64 v58; // rax
  int ManagedIdentityRegionalAuthNEndpoint; // eax
  __int64 v60; // rdx
  __int64 v61; // rcx
  HANDLE v62; // rax
  unsigned int v63; // edi
  __int64 v64; // rdx
  __int64 v65; // rcx
  unsigned int v66; // ebx
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // rax
  __int64 v70; // rbx
  __int64 v71; // rax
  char v72; // al
  __int64 v73; // rdx
  __int64 v74; // rcx
  wchar_t *v75; // rsi
  unsigned int v76; // eax
  int v77; // ebx
  HANDLE v78; // rax
  __int64 v79; // rax
  __int64 v80; // rbx
  __int64 v81; // rdi
  int v82; // r13d
  __int64 v83; // r14
  __int64 v84; // rcx
  __int64 v85; // rcx
  unsigned __int64 v86; // rax
  wchar_t *v87; // rax
  wchar_t *v88; // r15
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // rax
  __int64 v92; // rdx
  __int64 v93; // rcx
  __int64 v94; // rdx
  __int64 v95; // rcx
  HANDLE v96; // rax
  HANDLE v97; // rax
  HANDLE ProcessHeap; // rax
  __int64 v99; // [rsp+28h] [rbp-E0h]
  __int64 v100; // [rsp+30h] [rbp-D8h]
  __int64 v101; // [rsp+58h] [rbp-B0h] BYREF
  void (__fastcall ***v102)(_QWORD, __int64); // [rsp+60h] [rbp-A8h] BYREF
  __int64 v103; // [rsp+68h] [rbp-A0h]
  void *v104; // [rsp+70h] [rbp-98h] BYREF
  void *v105; // [rsp+78h] [rbp-90h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+80h] [rbp-88h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp-60h]
  int v108; // [rsp+B0h] [rbp-58h]
  int v109; // [rsp+B8h] [rbp-50h] BYREF
  int v110; // [rsp+BCh] [rbp-4Ch]
  int *v111; // [rsp+C0h] [rbp-48h]
  HCERTSTORE hCertStore[2]; // [rsp+C8h] [rbp-40h] BYREF
  int v113; // [rsp+D8h] [rbp-30h]
  char *v114; // [rsp+E0h] [rbp-28h]
  PCCERT_CONTEXT pCertContext; // [rsp+E8h] [rbp-20h]
  char v116; // [rsp+F0h] [rbp-18h]
  const wchar_t *v117; // [rsp+F8h] [rbp-10h]
  wchar_t *v118; // [rsp+100h] [rbp-8h]
  void *Source; // [rsp+108h] [rbp+0h] BYREF
  void *v120; // [rsp+110h] [rbp+8h] BYREF
  wchar_t *v121; // [rsp+118h] [rbp+10h] BYREF
  int v122; // [rsp+128h] [rbp+20h] BYREF
  __int64 v123; // [rsp+130h] [rbp+28h]
  int v124; // [rsp+138h] [rbp+30h] BYREF
  int v125; // [rsp+13Ch] [rbp+34h]
  __int64 v126; // [rsp+140h] [rbp+38h]
  int v127; // [rsp+148h] [rbp+40h] BYREF
  __int64 v128; // [rsp+150h] [rbp+48h]
  __int64 v129; // [rsp+158h] [rbp+50h]
  __int64 v130; // [rsp+160h] [rbp+58h]
  __int64 v131; // [rsp+168h] [rbp+60h]
  bool v132; // [rsp+178h] [rbp+70h]
  __int64 v133; // [rsp+188h] [rbp+80h] BYREF
  int v134; // [rsp+190h] [rbp+88h]
  __int128 v135; // [rsp+198h] [rbp+90h]
  __int128 v136; // [rsp+1A8h] [rbp+A0h]
  _DWORD *v137; // [rsp+1B8h] [rbp+B0h]
  int v138; // [rsp+1C0h] [rbp+B8h]
  __int128 v139; // [rsp+1C8h] [rbp+C0h] BYREF
  __int128 v140; // [rsp+1D8h] [rbp+D0h] BYREF
  wchar_t *v141; // [rsp+1E8h] [rbp+E0h]
  _BYTE *v142; // [rsp+1F0h] [rbp+E8h]
  __int64 v143; // [rsp+1F8h] [rbp+F0h]
  _BYTE v144[24]; // [rsp+200h] [rbp+F8h] BYREF
  __int64 v145; // [rsp+218h] [rbp+110h]
  _DWORD v146[6]; // [rsp+228h] [rbp+120h] BYREF
  void *v147; // [rsp+240h] [rbp+138h]
  _BYTE v148[24]; // [rsp+250h] [rbp+148h] BYREF
  __int64 v149; // [rsp+268h] [rbp+160h]
  _DWORD v150[6]; // [rsp+278h] [rbp+170h] BYREF
  void *v151; // [rsp+290h] [rbp+188h]
  _BYTE v152[24]; // [rsp+2A0h] [rbp+198h] BYREF
  void *v153; // [rsp+2B8h] [rbp+1B0h]
  char v154[8]; // [rsp+2C8h] [rbp+1C0h] BYREF
  HCRYPTPROV hProv; // [rsp+2D0h] [rbp+1C8h]
  int v156; // [rsp+2D8h] [rbp+1D0h]
  __int64 v157; // [rsp+2E0h] [rbp+1D8h]
  _DWORD v158[2]; // [rsp+4F8h] [rbp+3F0h] BYREF
  __int64 v159; // [rsp+500h] [rbp+3F8h]
  const wchar_t *v160; // [rsp+508h] [rbp+400h]
  __int128 v161; // [rsp+510h] [rbp+408h]
  __int64 v162; // [rsp+520h] [rbp+418h]
  __int64 v163; // [rsp+528h] [rbp+420h]
  const WCHAR *v164; // [rsp+530h] [rbp+428h]
  __int128 v165; // [rsp+538h] [rbp+430h]
  int v166; // [rsp+548h] [rbp+440h]
  int v167; // [rsp+54Ch] [rbp+444h]
  __int64 v168; // [rsp+550h] [rbp+448h]
  const wchar_t *v169; // [rsp+558h] [rbp+450h]
  __int128 v170; // [rsp+560h] [rbp+458h]
  __int128 v171; // [rsp+578h] [rbp+470h] BYREF
  int v172; // [rsp+588h] [rbp+480h]
  wchar_t v173[256]; // [rsp+598h] [rbp+490h] BYREF
  wchar_t v174[256]; // [rsp+798h] [rbp+690h] BYREF
  wchar_t v175[256]; // [rsp+998h] [rbp+890h] BYREF
  wchar_t v176[512]; // [rsp+B98h] [rbp+A90h] BYREF

  v143 = -2;
  v1 = a1;
  BYTE4(v101) = a1;
  LODWORD(v103) = 0;
  AutoForcePhysMaster::AutoForcePhysMaster((AutoForcePhysMaster *)&v101);
  v102 = 0;
  v2 = L"SetupUserManagedIdentityCert";
  if ( !(_BYTE)v1 )
    v2 = L"SetupAkvPrincipalCert";
  v110 = 2 * (v1 ^ 1) + 58;
  v3 = L"##MS_UserManagedCertificate##";
  if ( !(_BYTE)v1 )
    v3 = L"##MS_AkvPrincipalCertificate##";
  v117 = v3;
  v4 = L"MS_UserManagedCertificate_%s";
  if ( !(_BYTE)v1 )
    v4 = L"MS_AkvPrincipalCertificate_%s";
  v118 = v4;
  v5 = L"AzureUserManagedIdentityCertificate";
  if ( !(_BYTE)v1 )
    v5 = L"AzureKeyVaultPrincipalCertificate";
  lpMem = 0;
  v108 = 0;
  InitializeCriticalSection(&CriticalSection);
  LogSystemMetadata(L"[%s]:Retrieving SQL Instance Fabric property %s \n", v2, v5);
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v122, 1);
  v111 = &v124;
  v127 = 536872037;
  v128 = 0;
  v130 = 0;
  v129 = 0;
  v131 = 0;
  v132 = 0;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = *(_QWORD *)(v7 + 600);
  if ( v8 )
    v132 = (unsigned int)SOS_Task::PushWait(v8, &v127) == 0;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v126 = v10;
  v125 = (*(_DWORD *)(v10 + 800) >> 11) & 1;
  if ( v125 || (*(_BYTE *)(v10 + 800) & 4) == 0 )
  {
    v124 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 608) + 8LL))(*(_QWORD *)(v10 + 608));
  }
  else
  {
    v124 = 0;
  }
  Secret = HostReg_GetSecret(v5, &CriticalSection, 0xFFFFFFFFLL);
  v111 = &v124;
  if ( v124 )
  {
    if ( v125 )
      *(_DWORD *)(v126 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v126 + 608) + 16LL))(
        *(_QWORD *)(v126 + 608),
        v126,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v127);
  *(_DWORD *)(v123 + 616) &= ~v122;
  if ( Secret < 0 || Secret == 1 )
  {
    LogSystemMetadata(
      L"[%s]:HostReg_GetSecret on fabric property '%s' failed with result: %d",
      v2,
      v5,
      (unsigned int)Secret);
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
    DeleteCriticalSection(&CriticalSection);
LABEL_145:
    AutoMasterUsageContext::~AutoMasterUsageContext((AutoMasterUsageContext *)&v101);
    return (unsigned int)Secret;
  }
  else
  {
    v158[0] = 1;
    v158[1] = 1;
    v159 = 0;
    v160 = L"Base64EncodedCertificate";
    v161 = 0;
    v162 = 1;
    v163 = 0;
    v164 = L"Thumbprint";
    v165 = 0;
    v166 = 1;
    v167 = 2;
    v168 = 0;
    v169 = L"IsPrimary";
    v170 = 0;
    v137 = v158;
    v138 = 3;
    SecretElements = HostReg_GetSecretElements(
                       &CriticalSection,
                       L"/ArrayOfAzureKeyVaultPrincipalCertificateInfo/AzureKeyVaultPrincipalCertificateInfo",
                       3,
                       v158);
    v13 = SecretElements;
    if ( SecretElements >= 0 && SecretElements != 1 )
    {
      if ( !SecretElements )
      {
        memset_0(v174, 0, sizeof(v174));
        DefaultLocale = GetDefaultLocale();
        v15 = L"user managed identity cert: Found %u User Managed Identity Cert";
        if ( !(_BYTE)v1 )
          v15 = L"AKV principal cert: Found %u AKV Principal Cert";
        StringCchPrintf_lW(v174, 0x100u, v15, DefaultLocale, (_DWORD)v161);
        v16 = 0;
        v17 = v161;
        if ( (_DWORD)v161 )
        {
          v18 = v103;
          do
          {
            if ( *(_QWORD *)(*((_QWORD *)&v161 + 1) + 16LL * v16) )
            {
              v154[0] = 1;
              hProv = 0;
              v156 = 0;
              v157 = 0;
              CSECCryptoContext::Init(v154, v152, 3, 4026531904LL, 0);
              v18 &= ~1u;
              LODWORD(v103) = v18;
              if ( v153 )
                operator delete[](v153);
              *(_OWORD *)hCertStore = 0;
              v113 = 0;
              v114 = v154;
              pCertContext = 0;
              v116 = 0;
              v19 = *(_DWORD *)(*((_QWORD *)&v161 + 1) + 16LL * v16 + 8);
              v133 = *(_QWORD *)(*((_QWORD *)&v161 + 1) + 16LL * v16);
              v134 = v19;
              CSECCertificate::InitFromPFXBytes(hCertStore, v146, &v133, 0);
              if ( v146[0] )
              {
                v111 = (int *)v144;
                v145 = 0;
                CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v144, (const struct CSECCryptoError *)v146);
                RaiseCryptoError(v144, 0);
              }
              if ( v147 )
                operator delete[](v147);
              v171 = 0;
              v172 = 0;
              v109 = 20;
              CSECCertificate::GetThumbprint(hCertStore, v150, &v109, &v171);
              if ( v150[0] )
              {
                v142 = v148;
                v149 = 0;
                CSECCryptoError::DeepCopyCSECCryptoError((CSECCryptoError *)v148, (const struct CSECCryptoError *)v150);
                RaiseCryptoError(v148, 0);
              }
              if ( v151 )
                operator delete[](v151);
              memset_0(v176, 0, sizeof(v176));
              v20 = (_BYTE)v1 == 0;
              v21 = **(_DWORD **)(*((_QWORD *)&v170 + 1) + 16LL * v16);
              v22 = L"Certificate: User managed cert %u, Is Primary %u";
              if ( v20 )
                v22 = L"Certificate: AKV principal cert %u, Is Primary %u";
              v23 = GetDefaultLocale();
              LODWORD(v100) = v21;
              LODWORD(v99) = v16;
              StringCchPrintf_lW(v176, 0x200u, v22, v23, v99, v100);
              if ( **(_DWORD **)(*((_QWORD *)&v170 + 1) + 16LL * v16) )
              {
                *(_QWORD *)&v135 = v117;
                DWORD2(v135) = v110;
                v139 = v135;
                LOBYTE(v24) = 1;
                CreateDropCertificate(
                  (unsigned int)v154,
                  (unsigned int)hCertStore,
                  v24,
                  (unsigned int)&v139,
                  1,
                  1,
                  (__int64)&v102,
                  1,
                  0);
              }
              else
              {
                v173[0] = 0;
                Secret = StringCchPrintfW(v173, 0x100u, v118, *(_QWORD *)(*((_QWORD *)&v165 + 1) + 16LL * v16));
                if ( Secret )
                {
                  if ( pCertContext )
                  {
                    CertFreeCertificateContext(pCertContext);
                    pCertContext = 0;
                  }
                  if ( hCertStore[0] )
                  {
                    CertCloseStore(hCertStore[0], 0);
                    hCertStore[0] = 0;
                  }
                  if ( hProv && v154[0] )
                    CryptReleaseContext(hProv, 0);
                  hProv = 0;
                  v156 = 0;
                  HostReg_FreeElementData(3, v158);
                  if ( lpMem )
                  {
                    v31 = GetProcessHeap();
                    HeapFree(v31, 0, lpMem);
                  }
                  DeleteCriticalSection(&CriticalSection);
                  if ( v102 )
                    (**v102)(v102, 1);
                  goto LABEL_145;
                }
                v26 = -1;
                do
                  ++v26;
                while ( v173[v26] );
                *(_QWORD *)&v136 = v173;
                DWORD2(v136) = 2 * v26;
                v140 = v136;
                LOBYTE(v25) = 1;
                CreateDropCertificate(
                  (unsigned int)v154,
                  (unsigned int)hCertStore,
                  v25,
                  (unsigned int)&v140,
                  1,
                  1,
                  (__int64)&v102,
                  1,
                  0);
              }
              if ( pCertContext )
              {
                CertFreeCertificateContext(pCertContext);
                pCertContext = 0;
              }
              if ( hCertStore[0] )
              {
                CertCloseStore(hCertStore[0], 0);
                hCertStore[0] = 0;
              }
              if ( hProv && v154[0] )
                CryptReleaseContext(hProv, 0);
              hProv = 0;
              v156 = 0;
              v17 = v161;
              LOBYTE(v1) = BYTE4(v101);
            }
            ++v16;
          }
          while ( v16 < v17 );
        }
      }
      if ( byte_102EDCB4C )
      {
        v105 = 0;
        v27 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v28 = *(_QWORD *)(v27 + 256);
        if ( !v28 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v28 = *(_QWORD *)(v27 + 256);
        }
        ServerManagedIdentityTypeWinFabProperty = GetServerManagedIdentityTypeWinFabProperty(
                                                    &v105,
                                                    *(_QWORD *)(*(_QWORD *)(v28 + 992) + 320LL));
        Secret = ServerManagedIdentityTypeWinFabProperty;
        if ( ServerManagedIdentityTypeWinFabProperty < 0 )
        {
          _mm_lfence();
          LogSystemMetadata(
            L"[%s]:Call to get AKV identity type fabric property failed with result: %d",
            v2,
            (unsigned int)ServerManagedIdentityTypeWinFabProperty);
          operator delete[](v105);
          HostReg_FreeElementData(3, v158);
          if ( lpMem )
          {
            v30 = GetProcessHeap();
            HeapFree(v30, 0, lpMem);
          }
          DeleteCriticalSection(&CriticalSection);
          if ( v102 )
            (**v102)(v102, 1);
          goto LABEL_145;
        }
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        v33 = SystemThread_TlsIndex;
        v34 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v35 = *(_QWORD *)(v34 + 256);
        if ( !v35 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v35 = *(_QWORD *)(v34 + 256);
        }
        v36 = *(_QWORD *)(*(_QWORD *)(v35 + 992) + 320LL);
        XdbServerGlobals = GetXdbServerGlobals(v33, ThreadLocalStoragePointer);
        AzureKeyVaultClientId = GetAzureKeyVaultClientId(XdbServerGlobals + 21544, &Source, v36, v105);
        v13 = AzureKeyVaultClientId;
        if ( AzureKeyVaultClientId < 0 )
        {
          _mm_lfence();
          LogSystemMetadata(
            L"[%s]:Call to get AKV client Id fabric property failed with result: %d",
            v2,
            (unsigned int)AzureKeyVaultClientId);
          operator delete[](v105);
          HostReg_FreeElementData(3, v158);
          if ( lpMem )
          {
            v41 = GetProcessHeap();
            HeapFree(v41, 0, lpMem);
          }
          DeleteCriticalSection(&CriticalSection);
          if ( v102 )
            (**v102)(v102, 1);
LABEL_88:
          AutoMasterUsageContext::~AutoMasterUsageContext((AutoMasterUsageContext *)&v101);
          return (unsigned int)v13;
        }
        v43 = *(_DWORD *)(GetXdbServerGlobals(v40, v39) + 21544);
        v46 = *(_DWORD *)(GetXdbServerGlobals(v45, v44) + 21544);
        v49 = GetXdbServerGlobals(v48, v47);
        memcpy_s((void *const)(v49 + 21548), v46, Source, v43);
        operator delete[](v105);
      }
      if ( byte_102EDCD46 )
      {
        v104 = 0;
        v50 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v51 = *(_QWORD *)(v50 + 256);
        if ( !v51 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v51 = *(_QWORD *)(v50 + 256);
        }
        v52 = GetServerManagedIdentityTypeWinFabProperty(&v104, *(_QWORD *)(*(_QWORD *)(v51 + 992) + 320LL));
        if ( v52 < 0 )
        {
          _mm_lfence();
          LogSystemMetadata(
            L"[%s]:Call to get identity type fabric property failed with result: %d",
            v2,
            (unsigned int)v52);
          if ( v104 )
            operator delete[](v104);
          v104 = 0;
        }
        v53 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v54 = SystemThread_TlsIndex;
        v55 = v53[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v56 = *(_QWORD *)(v55 + 256);
        if ( !v56 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v56 = *(_QWORD *)(v55 + 256);
        }
        v57 = *(_QWORD *)(*(_QWORD *)(v56 + 992) + 320LL);
        v58 = GetXdbServerGlobals(v54, v53);
        ManagedIdentityRegionalAuthNEndpoint = GetManagedIdentityRegionalAuthNEndpoint(v58 + 21648, &v120, v57, v104);
        v13 = ManagedIdentityRegionalAuthNEndpoint;
        if ( ManagedIdentityRegionalAuthNEndpoint < 0 )
        {
          _mm_lfence();
          LogSystemMetadata(
            L"[%s]:Call to get AKV client Regional Authentication Endpoint fabric property failed with result: %d",
            v2,
            (unsigned int)ManagedIdentityRegionalAuthNEndpoint);
          operator delete[](v104);
          HostReg_FreeElementData(3, v158);
          if ( lpMem )
          {
            v62 = GetProcessHeap();
            HeapFree(v62, 0, lpMem);
          }
          DeleteCriticalSection(&CriticalSection);
          if ( v102 )
            (**v102)(v102, 1);
          AutoMasterUsageContext::~AutoMasterUsageContext((AutoMasterUsageContext *)&v101);
          return 0;
        }
        v63 = *(_DWORD *)(GetXdbServerGlobals(v61, v60) + 21648);
        v66 = *(_DWORD *)(GetXdbServerGlobals(v65, v64) + 21648);
        v69 = GetXdbServerGlobals(v68, v67);
        memcpy_s((void *const)(v69 + 21652), v66, v120, v63);
        operator delete[](v104);
      }
      if ( byte_102EDCE4D )
      {
        v70 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v71 = *(_QWORD *)(v70 + 256);
        if ( !v71 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v71 = *(_QWORD *)(v70 + 256);
        }
        v72 = (*(__int64 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))(*(_QWORD *)s_pServerConf + 528LL))(
                s_pServerConf,
                L"FederatedAuthentication",
                L"EstsAppOnlyOboDomain",
                *(_QWORD *)(*(_QWORD *)(v71 + 992) + 320LL),
                &v121,
                0);
        v75 = v121;
        if ( !v72 )
          v75 = 0;
        v141 = v75;
        if ( !v75 )
        {
          memset_0(v175, 0, sizeof(v175));
          v76 = StringCchPrintfW(
                  v175,
                  0x100u,
                  L"[%hs]  Call to get EstsAppOnlyOboDomain property failed",
                  "SetupMSICert");
          v77 = v76;
          if ( !v76 || (scierrlog(0x6F8Au, v76, L"SetupMSICert", 3787), v77 >= 0) )
            LogSystemMetadataNotSentToClient(L"%ls", v175);
          operator delete[](0);
          HostReg_FreeElementData(3, v158);
          if ( lpMem )
          {
            v78 = GetProcessHeap();
            HeapFree(v78, 0, lpMem);
          }
          DeleteCriticalSection(&CriticalSection);
          if ( v102 )
            (**v102)(v102, 1);
          AutoMasterUsageContext::~AutoMasterUsageContext((AutoMasterUsageContext *)&v101);
          return 2147942414LL;
        }
        v79 = GetXdbServerGlobals(v74, v73);
        v80 = -1;
        do
          ++v80;
        while ( *(_WORD *)(v79 + 2 * v80 + 1566) );
        v81 = -1;
        do
          ++v81;
        while ( v75[v81] );
        v82 = v81 + v80;
        v83 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v84 = *(_QWORD *)(v83 + 256);
        if ( !v84 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v84 = *(_QWORD *)(v83 + 256);
        }
        v85 = *(_QWORD *)(v84 + 992);
        v86 = 2LL * (unsigned int)(v82 + 1);
        if ( !is_mul_ok((unsigned int)(v82 + 1), 2u) )
          v86 = -1;
        v87 = (wchar_t *)operator new[](
                           v86,
                           *(struct IMemObj **)(v85 + 320),
                           1,
                           "Sql\\Ntdbms\\xdb\\sqllang\\xdbstartup.cpp",
                           3801,
                           6u);
        v88 = v87;
        if ( v87 )
        {
          memset_0(v87, 0, 2LL * (unsigned int)(v82 + 1));
          v91 = GetXdbServerGlobals(v90, v89);
          v13 = wmemcpy_s(v88, (unsigned int)v80, (const wchar_t *)(v91 + 1566), (unsigned int)v80);
          if ( v13 >= 0 )
          {
            _mm_lfence();
            v13 = wmemcpy_s(&v88[(unsigned int)v80], (unsigned int)v81, v75, (unsigned int)v81);
            if ( v13 >= 0 )
            {
              *(_DWORD *)(GetXdbServerGlobals(v93, v92) + 21852) = v82;
              *(_QWORD *)(GetXdbServerGlobals(v95, v94) + 21856) = v88;
            }
          }
        }
        else
        {
          v13 = -2147024882;
        }
        operator delete[](v75);
      }
      _mm_lfence();
      HostReg_FreeElementData(3, v158);
      if ( lpMem )
      {
        v96 = GetProcessHeap();
        HeapFree(v96, 0, lpMem);
      }
      DeleteCriticalSection(&CriticalSection);
      if ( v102 )
        (**v102)(v102, 1);
      goto LABEL_88;
    }
    _mm_lfence();
    LogSystemMetadata(
      L"[%s]:HostReg_GetSecretElements on '%s' failed with result: %d",
      v2,
      v5,
      (unsigned int)SecretElements);
    HostReg_FreeElementData(3, v158);
    if ( lpMem )
    {
      v97 = GetProcessHeap();
      HeapFree(v97, 0, lpMem);
    }
    DeleteCriticalSection(&CriticalSection);
    AutoMasterUsageContext::~AutoMasterUsageContext((AutoMasterUsageContext *)&v101);
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x101e96da0  mov     rax, rsp
0x101e96da3  push    rbp
0x101e96da4  push    r12
0x101e96da6  push    r13
0x101e96da8  push    r14
0x101e96daa  push    r15
0x101e96dac  lea     rbp, [rax-0EC8h]
0x101e96db3  sub     rsp, 0FA0h
0x101e96dba  mov     [rbp+0EC0h+var_DD0], 0FFFFFFFFFFFFFFFEh
0x101e96dc5  mov     [rax+8], rbx
0x101e96dc9  mov     [rax+10h], rsi
0x101e96dcd  mov     [rax+18h], rdi
0x101e96dd1  mov     rax, cs:__security_cookie
0x101e96dd8  xor     rax, rsp
0x101e96ddb  mov     [rbp+0EC0h+var_30], rax
0x101e96de2  movzx   esi, cl
0x101e96de5  mov     byte ptr [rsp+0FC0h+var_F70+4], sil
0x101e96dea  xor     r15d, r15d
0x101e96ded  mov     dword ptr [rsp+0FC0h+var_F60], r15d
0x101e96df2  lea     rcx, [rsp+0FC0h+var_F70]
0x101e96df7  call    cs:__imp_??0AutoForcePhysMaster@@QEAA@XZ; AutoForcePhysMaster::AutoForcePhysMaster(void)
0x101e96dfd  nop
0x101e96dfe  mov     [rsp+0FC0h+var_F68], r15
0x101e96e03  lea     rax, aSetupakvprinci_0; "SetupAkvPrincipalCert"
0x101e96e0a  lea     r13, aSetupusermanag; "SetupUserManagedIdentityCert"
0x101e96e11  test    sil, sil
0x101e96e14  cmovz   r13, rax
0x101e96e18  mov     eax, esi
0x101e96e1a  xor     eax, 1
0x101e96e1d  lea     eax, ds:3Ah[rax*2]
0x101e96e24  mov     [rbp+0EC0h+var_F0C], eax
0x101e96e27  lea     rcx, aMsAkvprincipal_1; "##MS_AkvPrincipalCertificate##"
0x101e96e2e  lea     rax, aMsUsermanagedc_1; "##MS_UserManagedCertificate##"
0x101e96e35  test    sil, sil
0x101e96e38  cmovz   rax, rcx
0x101e96e3c  mov     [rbp+0EC0h+var_ED0], rax
0x101e96e40  lea     rcx, aMsAkvprincipal; "MS_AkvPrincipalCertificate_%s"
0x101e96e47  lea     rax, aMsUsermanagedc; "MS_UserManagedCertificate_%s"
0x101e96e4e  cmovz   rax, rcx
0x101e96e52  mov     [rbp+0EC0h+var_EC8], rax
0x101e96e56  lea     rax, aAzurekeyvaultp; "AzureKeyVaultPrincipalCertificate"
0x101e96e5d  lea     rdi, aAzureusermanag; "AzureUserManagedIdentityCertificate"
0x101e96e64  cmovz   rdi, rax
0x101e96e68  mov     [rbp+0EC0h+lpMem], r15
0x101e96e6c  mov     [rbp+0EC0h+var_F18], r15d
0x101e96e70  lea     rcx, [rsp+0FC0h+CriticalSection]; lpCriticalSection
0x101e96e75  call    cs:__imp_InitializeCriticalSection
0x101e96e7b  nop
0x101e96e7c  mov     r8, rdi
0x101e96e7f  mov     rdx, r13
0x101e96e82  lea     rcx, aSRetrievingSql; "[%s]:Retrieving SQL Instance Fabric pro"...
0x101e96e89  call    ?LogSystemMetadata@@YAXPEB_WZZ; LogSystemMetadata(wchar_t const *,...)
0x101e96e8e  lea     edx, [r15+1]
0x101e96e92  lea     rcx, [rbp+0EC0h+var_EA0]
0x101e96e96  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x101e96e9b  nop
0x101e96e9c  lea     rax, [rbp+0EC0h+var_E90]
0x101e96ea0  mov     [rbp+0EC0h+var_F08], rax
0x101e96ea4  mov     [rbp+0EC0h+var_E80], 20000465h
0x101e96eab  mov     [rbp+0EC0h+var_E78], r15
0x101e96eaf  mov     [rbp+0EC0h+var_E68], r15
0x101e96eb3  mov     [rbp+0EC0h+var_E70], r15
0x101e96eb7  mov     [rbp+0EC0h+var_E60], r15
0x101e96ebb  mov     [rbp+0EC0h+var_E50], r15b
0x101e96ebf  mov     rdx, gs:58h
0x101e96ec8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101e96ecf  mov     ecx, [rax]
0x101e96ed1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101e96ed8  mov     ebx, [rax]
0x101e96eda  add     rbx, [rdx+rcx*8]
0x101e96ede  mov     rcx, [rbx+100h]
0x101e96ee5  test    rcx, rcx
0x101e96ee8  jnz     short loc_101E96EF7
0x101e96eea  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101e96ef0  mov     rcx, [rbx+100h]
0x101e96ef7  mov     rcx, [rcx+258h]
0x101e96efe  test    rcx, rcx
0x101e96f01  jz      short loc_101E96F13
0x101e96f03  lea     rdx, [rbp+0EC0h+var_E80]
0x101e96f07  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x101e96f0d  test    eax, eax
0x101e96f0f  setz    [rbp+0EC0h+var_E50]
0x101e96f13  mov     rdx, gs:58h
0x101e96f1c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101e96f23  mov     ecx, [rax]
0x101e96f25  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101e96f2c  mov     ebx, [rax]
0x101e96f2e  add     rbx, [rdx+rcx*8]
0x101e96f32  mov     rdx, [rbx+100h]
0x101e96f39  test    rdx, rdx
0x101e96f3c  jnz     short loc_101E96F4D
0x101e96f3e  xor     ecx, ecx
0x101e96f40  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101e96f46  mov     rdx, [rbx+100h]
0x101e96f4d  mov     [rbp+0EC0h+var_E88], rdx
0x101e96f51  mov     eax, [rdx+320h]
0x101e96f57  shr     eax, 0Bh
0x101e96f5a  and     eax, 1
0x101e96f5d  mov     [rbp+0EC0h+var_E8C], eax
0x101e96f60  jnz     short loc_101E96F71
0x101e96f62  test    byte ptr [rdx+320h], 4
0x101e96f69  jz      short loc_101E96F71
0x101e96f6b  mov     [rbp+0EC0h+var_E90], r15d
0x101e96f6f  jmp     short loc_101E96F86
0x101e96f71  mov     [rbp+0EC0h+var_E90], 1
0x101e96f78  mov     rcx, [rdx+260h]
0x101e96f7f  mov     rax, [rcx]
0x101e96f82  call    qword ptr [rax+8]
0x101e96f85  nop
0x101e96f86  mov     r8d, 0FFFFFFFFh
0x101e96f8c  lea     rdx, [rsp+0FC0h+CriticalSection]
0x101e96f91  mov     rcx, rdi
0x101e96f94  call    cs:__imp_HostReg_GetSecret
0x101e96f9a  mov     ebx, eax
0x101e96f9c  lea     rax, [rbp+0EC0h+var_E90]
0x101e96fa0  mov     [rbp+0EC0h+var_F08], rax
0x101e96fa4  cmp     [rbp+0EC0h+var_E90], 0
0x101e96fa8  jz      short loc_101E96FD4
0x101e96faa  mov     rdx, [rbp+0EC0h+var_E88]
0x101e96fae  mov     rcx, [rdx+260h]
0x101e96fb5  cmp     [rbp+0EC0h+var_E8C], 0
0x101e96fb9  jz      short loc_101E96FC7
0x101e96fbb  or      dword ptr [rdx+320h], 800h
0x101e96fc5  jmp     short loc_101E96FD4
0x101e96fc7  mov     rax, [rcx]
0x101e96fca  mov     r8d, 1
0x101e96fd0  call    qword ptr [rax+10h]
0x101e96fd3  nop
0x101e96fd4  lea     rcx, [rbp+0EC0h+var_E80]; this
0x101e96fd8  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x101e96fdd  nop
0x101e96fde  mov     ecx, [rbp+0EC0h+var_EA0]
0x101e96fe1  not     ecx
0x101e96fe3  mov     rax, [rbp+0EC0h+var_E98]
0x101e96fe7  and     [rax+268h], ecx
0x101e96fed  test    ebx, ebx
0x101e96fef  js      loc_101E97CE4
0x101e96ff5  cmp     ebx, 1
0x101e96ff8  jz      loc_101E97CE4
0x101e96ffe  mov     [rbp+0EC0h+var_AD0], 1
0x101e97008  mov     [rbp+0EC0h+var_ACC], 1
0x101e97012  mov     [rbp+0EC0h+var_AC8], r15
0x101e97019  lea     rax, aBase64encodedc; "Base64EncodedCertificate"
0x101e97020  mov     [rbp+0EC0h+var_AC0], rax
0x101e97027  xorps   xmm0, xmm0
0x101e9702a  movups  [rbp+0EC0h+var_AB8], xmm0
0x101e97031  mov     [rbp+0EC0h+var_AA8], 1
0x101e9703c  mov     [rbp+0EC0h+var_AA0], r15
0x101e97043  lea     rax, aThumbprint_0; "Thumbprint"
0x101e9704a  mov     [rbp+0EC0h+var_A98], rax
0x101e97051  movups  [rbp+0EC0h+var_A90], xmm0
0x101e97058  mov     [rbp+0EC0h+var_A80], 1
0x101e97062  mov     [rbp+0EC0h+var_A7C], 2
0x101e9706c  mov     [rbp+0EC0h+var_A78], r15
0x101e97073  lea     rax, aIsprimary; "IsPrimary"
0x101e9707a  mov     [rbp+0EC0h+var_A70], rax
0x101e97081  movups  [rbp+0EC0h+var_A68], xmm0
0x101e97088  lea     rax, [rbp+0EC0h+var_AD0]
0x101e9708f  mov     [rbp+0EC0h+var_E10], rax
0x101e97096  mov     [rbp+0EC0h+var_E08], 3
0x101e970a0  lea     r9, [rbp+0EC0h+var_AD0]
0x101e970a7  mov     r8d, 3
0x101e970ad  lea     rdx, aArrayofazureke; "/ArrayOfAzureKeyVaultPrincipalCertifica"...
0x101e970b4  lea     rcx, [rsp+0FC0h+CriticalSection]
0x101e970b9  call    cs:__imp_HostReg_GetSecretElements
0x101e970bf  mov     r14d, eax
0x101e970c2  test    eax, eax
0x101e970c4  js      loc_101E97C80
0x101e970ca  cmp     eax, 1
0x101e970cd  jz      loc_101E97C80
0x101e970d3  mov     r12, 0FFFFFFFFFFFFFFFFh
0x101e970da  test    eax, eax
0x101e970dc  jnz     loc_101E974EB
0x101e970e2  xor     edx, edx; Val
0x101e970e4  mov     r8d, 200h; Size
0x101e970ea  lea     rcx, [rbp+0EC0h+var_830]; void *
0x101e970f1  call    memset_0
0x101e970f6  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x101e970fc  mov     r9, rax; struct __crt_locale_pointers *
0x101e970ff  mov     edx, 100h; unsigned __int64
0x101e97104  lea     rcx, [rbp+0EC0h+var_830]; wchar_t *
0x101e9710b  mov     eax, dword ptr [rbp+0EC0h+var_AB8]
0x101e97111  mov     dword ptr [rsp+0FC0h+var_FA0], eax
0x101e97115  test    sil, sil
0x101e97118  lea     r8, aUserManagedIde; "user managed identity cert: Found %u Us"...
0x101e9711f  jnz     short loc_101E97128
0x101e97121  lea     r8, aAkvPrincipalCe; "AKV principal cert: Found %u AKV Princi"...
0x101e97128  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x101e9712d  xor     edi, edi
0x101e9712f  mov     r15d, edi
0x101e97132  mov     ecx, dword ptr [rbp+0EC0h+var_AB8]
0x101e97138  test    ecx, ecx
0x101e9713a  jz      loc_101E974EB
0x101e97140  mov     r12d, dword ptr [rsp+0FC0h+var_F60]
0x101e97145  nop     word ptr [rax+rax+00000000h]
0x101e97150  mov     ebx, r15d
0x101e97153  add     rbx, rbx
0x101e97156  mov     rax, qword ptr [rbp+0EC0h+var_AB8+8]
0x101e9715d  cmp     qword ptr [rax+rbx*8], 0
0x101e97162  jz      loc_101E974D8
0x101e97168  mov     [rbp+0EC0h+var_D00], 1
0x101e9716f  mov     [rbp+0EC0h+hProv], rdi
0x101e97176  mov     [rbp+0EC0h+var_CF0], edi
0x101e9717c  mov     [rbp+0EC0h+var_CE8], rdi
0x101e97183  mov     [rsp+0FC0h+var_FA0], rdi
0x101e97188  mov     r9d, 0F0000040h
0x101e9718e  mov     r8d, 3
0x101e97194  lea     rdx, [rbp+0EC0h+var_D28]
0x101e9719b  lea     rcx, [rbp+0EC0h+var_D00]
0x101e971a2  call    ?Init@CSECCryptoContext@@QEAA?AVCSECCryptoError@@W4ESECCryptoProvType@@KPEB_W@Z; CSECCryptoContext::Init(ESECCryptoProvType,ulong,wchar_t const *)
0x101e971a7  or      r12d, 1
0x101e971ab  mov     dword ptr [rsp+0FC0h+var_F60], r12d
0x101e971b0  and     r12d, 0FFFFFFFEh
0x101e971b4  mov     dword ptr [rsp+0FC0h+var_F60], r12d
0x101e971b9  mov     rcx, [rbp+0EC0h+var_D10]
0x101e971c0  test    rcx, rcx
0x101e971c3  jz      short loc_101E971CB
0x101e971c5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x101e971cb  xorps   xmm0, xmm0
0x101e971ce  movdqu  xmmword ptr [rbp+0EC0h+hCertStore], xmm0
0x101e971d3  mov     [rbp+0EC0h+var_EF0], edi
0x101e971d6  lea     rax, [rbp+0EC0h+var_D00]
0x101e971dd  mov     [rbp+0EC0h+var_EE8], rax
0x101e971e1  xor     eax, eax
0x101e971e3  mov     [rbp+0EC0h+pCertContext], rax
0x101e971e7  mov     [rbp+0EC0h+var_ED8], al
0x101e971ea  mov     rax, qword ptr [rbp+0EC0h+var_AB8+8]
0x101e971f1  mov     ecx, [rax+rbx*8+8]
0x101e971f5  mov     rax, [rax+rbx*8]
0x101e971f9  mov     [rbp+0EC0h+var_E40], rax
0x101e97200  mov     [rbp+0EC0h+var_E38], ecx
0x101e97206  xor     r9d, r9d
0x101e97209  lea     r8, [rbp+0EC0h+var_E40]
0x101e97210  lea     rdx, [rbp+0EC0h+var_DA0]
0x101e97217  lea     rcx, [rbp+0EC0h+hCertStore]
0x101e9721b  call    ?InitFromPFXBytes@CSECCertificate@@QEAA?AVCSECCryptoError@@AEAUSECBytes@@PEB_W@Z; CSECCertificate::InitFromPFXBytes(SECBytes &,wchar_t const *)
0x101e97220  nop
0x101e97221  cmp     [rbp+0EC0h+var_DA0], 0
0x101e97228  jz      short loc_101E9725E
0x101e9722a  lea     rax, [rbp+0EC0h+var_DC8]
0x101e97231  mov     [rbp+0EC0h+var_F08], rax
0x101e97235  mov     [rbp+0EC0h+var_DB0], rdi
0x101e9723c  lea     rdx, [rbp+0EC0h+var_DA0]; struct CSECCryptoError *
0x101e97243  lea     rcx, [rbp+0EC0h+var_DC8]; this
0x101e9724a  call    ?DeepCopyCSECCryptoError@CSECCryptoError@@AEAAXAEBV1@@Z; CSECCryptoError::DeepCopyCSECCryptoError(CSECCryptoError const &)
0x101e9724f  xor     edx, edx
0x101e97251  lea     rcx, [rbp+0EC0h+var_DC8]
0x101e97258  call    ?RaiseCryptoError@@YAXVCSECCryptoError@@W4SqlCpError@@@Z; RaiseCryptoError(CSECCryptoError,SqlCpError)
0x101e9725d  nop
0x101e9725e  mov     rcx, [rbp+0EC0h+var_D88]
0x101e97265  test    rcx, rcx
0x101e97268  jz      short loc_101E97270
0x101e9726a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x101e97270  xorps   xmm0, xmm0
0x101e97273  xor     eax, eax
0x101e97275  movups  [rbp+0EC0h+var_A50], xmm0
0x101e9727c  mov     [rbp+0EC0h+var_A40], eax
0x101e97282  mov     [rbp+0EC0h+var_F10], 14h
0x101e97289  lea     r9, [rbp+0EC0h+var_A50]
0x101e97290  lea     r8, [rbp+0EC0h+var_F10]
0x101e97294  lea     rdx, [rbp+0EC0h+var_D50]
0x101e9729b  lea     rcx, [rbp+0EC0h+hCertStore]
0x101e9729f  call    ?GetThumbprint@CSECCertificate@@QEBA?AVCSECCryptoError@@AEAKPEAE@Z; CSECCertificate::GetThumbprint(ulong &,uchar *)
0x101e972a4  nop
0x101e972a5  cmp     [rbp+0EC0h+var_D50], 0
0x101e972ac  jz      short loc_101E972E5
0x101e972ae  lea     rax, [rbp+0EC0h+var_D78]
0x101e972b5  mov     [rbp+0EC0h+var_DD8], rax
0x101e972bc  mov     [rbp+0EC0h+var_D60], rdi
0x101e972c3  lea     rdx, [rbp+0EC0h+var_D50]; struct CSECCryptoError *
0x101e972ca  lea     rcx, [rbp+0EC0h+var_D78]; this
0x101e972d1  call    ?DeepCopyCSECCryptoError@CSECCryptoError@@AEAAXAEBV1@@Z; CSECCryptoError::DeepCopyCSECCryptoError(CSECCryptoError const &)
0x101e972d6  xor     edx, edx
0x101e972d8  lea     rcx, [rbp+0EC0h+var_D78]
0x101e972df  call    ?RaiseCryptoError@@YAXVCSECCryptoError@@W4SqlCpError@@@Z; RaiseCryptoError(CSECCryptoError,SqlCpError)
0x101e972e4  nop
0x101e972e5  mov     rcx, [rbp+0EC0h+var_D38]
0x101e972ec  test    rcx, rcx
0x101e972ef  jz      short loc_101E972F7
0x101e972f1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x101e972f7  xor     edx, edx; Val
0x101e972f9  mov     r8d, 400h; Size
0x101e972ff  lea     rcx, [rbp+0EC0h+var_430]; void *
0x101e97306  call    memset_0
0x101e9730b  mov     rax, qword ptr [rbp+0EC0h+var_A68+8]
0x101e97312  mov     rcx, [rax+rbx*8]
0x101e97316  test    sil, sil
0x101e97319  mov     esi, [rcx]
0x101e9731b  lea     rdi, aCertificateUse; "Certificate: User managed cert %u, Is P"...
0x101e97322  jnz     short loc_101E9732B
0x101e97324  lea     rdi, aCertificateAkv; "Certificate: AKV principal cert %u, Is "...
0x101e9732b  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x101e97331  mov     dword ptr [rsp+0FC0h+var_F98], esi
0x101e97335  mov     dword ptr [rsp+0FC0h+var_FA0], r15d
0x101e9733a  mov     r9, rax; struct __crt_locale_pointers *
0x101e9733d  mov     r8, rdi; wchar_t *
0x101e97340  mov     edx, 200h; unsigned __int64
0x101e97345  lea     rcx, [rbp+0EC0h+var_430]; wchar_t *
0x101e9734c  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x101e97351  mov     rax, qword ptr [rbp+0EC0h+var_A68+8]
  ... truncated ...
```
