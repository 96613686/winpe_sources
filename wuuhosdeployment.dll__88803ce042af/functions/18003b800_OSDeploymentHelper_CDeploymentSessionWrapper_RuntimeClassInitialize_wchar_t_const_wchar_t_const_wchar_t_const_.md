# OSDeploymentHelper::CDeploymentSessionWrapper::RuntimeClassInitialize(wchar_t const *,wchar_t const *,wchar_t const *,ulong,tagDSFile * *,_GUID,ulong,void *,bool *)

- ea: `0x18003b800`
- end: `0x18003c0f3`
- name: `?RuntimeClassInitialize@CDeploymentSessionWrapper@OSDeploymentHelper@@QEAAJPEB_W00KPEAPEAUtagDSFile@@U_GUID@@KPEAXPEA_N@Z`
- size: `2291`
- prototype: `__int64 __fastcall(OSDeploymentHelper::CDeploymentSessionWrapper *this, wchar_t *, const wchar_t *, const wchar_t *, unsigned int, struct tagDSFile **, struct _GUID *, unsigned int, void *)`
- caller_count: `3`
- callee_count: `22`
- tags: `file_ops, reparse_path, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d604`
- `0x1800230c0`
- `0x180023404`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000956c`
- `0x18000af44`
- `0x18000c634`
- `0x18000c684`
- `0x18000cbc4`
- `0x18000d904`
- `0x18000dd4c`
- `0x18000e05c`
- `0x18000ed84`
- `0x18000f534`
- `0x18000fe08`
- `0x180010f54`
- `0x180015fc8`
- `0x18001a688`
- `0x18001b458`
- `0x18003b800`
- `0x18003c0fc`
- `0x180042630`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003baea`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003baea`

## string_xrefs

- `0x18003bb67`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x18003bbe8`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x18003b9a6`: `Using the inbox service stack dll file '%ws' `
- `0x18003ba11`: `Failed to find the service stack cab file '%ws'`
- `0x18003bb07`: `Using the update's service stack dll file '%ws' `
- `0x18003bbe1`: `AlternateServiceStackDLLPath`
- `0x18003bc33`: `Using test service stack dll file '%ws' for Update ID '%ws'`
- `0x18003bc7f`: `Failed to find the service stack dll file '%ws'`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OSDeploymentHelper::CDeploymentSessionWrapper::RuntimeClassInitialize(
        OSDeploymentHelper::CDeploymentSessionWrapper *this,
        wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        unsigned int a5,
        struct tagDSFile **a6,
        struct _GUID *a7,
        unsigned int a8,
        void *a9)
{
  wchar_t *v10; // rdi
  __int64 v12; // rdx
  int v13; // ebx
  struct tagOptionalSessionInfo6 *v15; // r9
  int CombinedPath; // eax
  unsigned __int64 v17; // rdx
  int SystemFilePath; // r15d
  WCHAR *v19; // r14
  WCHAR *v20; // rbx
  char v21; // r12
  __int64 v22; // rdx
  unsigned __int64 v23; // r9
  bool v24; // cl
  int v25; // eax
  WCHAR *v26; // rdi
  unsigned __int64 v27; // r9
  __int64 v28; // rdx
  int v29; // eax
  int v30; // esi
  int v31; // eax
  void *v32; // r8
  const wchar_t *v33; // r9
  int v34; // eax
  int v35; // eax
  const wchar_t *v36; // rsi
  __int64 v37; // rdx
  wchar_t *v38; // rcx
  const wchar_t *v39; // r8
  wchar_t v40; // ax
  wchar_t *v41; // rax
  __int64 v42; // rcx
  void *v43; // rcx
  void *v44; // rdi
  unsigned int v45; // edx
  void *v46; // r8
  int DirectoryW; // eax
  struct tagDSFile **v48; // rax
  WCHAR *v49; // rsi
  __int64 v50; // rdx
  __int64 v51; // rdx
  struct IDeploymentSession *v52; // rdi
  __int64 v53; // rcx
  __int64 v54; // rcx
  int v55; // eax
  void (__fastcall ***v56)(_QWORD, GUID *, char *); // rsi
  __int64 v57; // rcx
  void (__fastcall ***v58)(_QWORD, GUID *, char *); // rsi
  __int64 v59; // rcx
  void (__fastcall ***v60)(_QWORD, GUID *, char *); // rsi
  __int64 v61; // rcx
  void (__fastcall ***v62)(_QWORD, GUID *, char *); // rsi
  __int64 v63; // rcx
  void (__fastcall ***v64)(_QWORD, GUID *, char *); // rsi
  __int64 v65; // rcx
  void (__fastcall ***v66)(_QWORD, GUID *, char *); // rdi
  __int64 v67; // rcx
  void *v68; // [rsp+20h] [rbp-E0h]
  int v69; // [rsp+20h] [rbp-E0h]
  void *lpMem; // [rsp+40h] [rbp-C0h] BYREF
  PCNZWCH v71; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+50h] [rbp-B0h] BYREF
  struct tagDSFile **v73; // [rsp+58h] [rbp-A8h]
  wchar_t *v74; // [rsp+60h] [rbp-A0h]
  PCNZWCH lpString1; // [rsp+68h] [rbp-98h] BYREF
  void *v76; // [rsp+70h] [rbp-90h]
  struct _GUID *v77; // [rsp+78h] [rbp-88h]
  _QWORD v78[14]; // [rsp+80h] [rbp-80h] BYREF
  struct IDeploymentSession *v79; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v80[3]; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t v81[264]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  lpExistingFileName = a3;
  v10 = a2;
  v74 = a2;
  v73 = a6;
  v77 = a7;
  v76 = a9;
  if ( !a2 )
  {
    v12 = 26;
LABEL_3:
    v13 = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
      (const char *)(unsigned int)v13,
      (int)v68);
    return (unsigned int)v13;
  }
  if ( !a4 )
  {
    v12 = 27;
    goto LABEL_3;
  }
  memset(v78, 0, sizeof(v78));
  v13 = OSDeploymentHelper::BuildOptionalSessionInfo((OSDeploymentHelper *)a8, (unsigned int)a9, v78, v15);
  if ( v13 < 0 )
  {
    v12 = 39;
    goto LABEL_4;
  }
  if ( a9 )
  {
    if ( v78[6] )
      v10 = (wchar_t *)v78[6];
    v74 = v10;
  }
  lpString1 = 0;
  CombinedPath = CreateCombinedPath(v10, L"Metadata", (wchar_t **)&lpString1);
  SystemFilePath = CombinedPath;
  v19 = (WCHAR *)lpString1;
  if ( CombinedPath >= 0 )
  {
    v20 = 0;
    v71 = 0;
    memset(v80, 0, sizeof(v80));
    v21 = 1;
    if ( !lpExistingFileName )
    {
      SystemFilePath = GetSystemFilePath(v81, v17, a4);
      if ( SystemFilePath < 0 )
      {
        v22 = 152;
LABEL_20:
        v23 = (unsigned int)SystemFilePath;
LABEL_66:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
          (const char *)v23,
          (int)v68);
LABEL_113:
        SsShimInterface::~SsShimInterface((SsShimInterface *)v80);
        if ( v20 )
          CSusBaseAllocTag<942762101>::operator delete(v20);
        goto LABEL_115;
      }
      SystemFilePath = DuplicateString<wchar_t *,wchar_t *>(v81, &v71);
      v20 = (WCHAR *)v71;
      if ( SystemFilePath < 0 )
      {
        v22 = 154;
        goto LABEL_20;
      }
      v68 = 0;
      WUTrace(0, 0, 4096, 4);
LABEL_39:
      if ( (unsigned int)AreTestKeysAllowed(v24) )
      {
        v36 = L"Global";
        if ( v76 && v78[1] )
          v36 = (const wchar_t *)v78[1];
        v37 = 260;
        v38 = v81;
        v39 = (const wchar_t *)((char *)L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test"
                              - (char *)v81);
        do
        {
          if ( v37 == -2147483386 )
            break;
          v40 = *(wchar_t *)((char *)v38 + (_QWORD)v39);
          if ( !v40 )
            break;
          *v38++ = v40;
          --v37;
        }
        while ( v37 );
        v41 = v38 - 1;
        if ( v37 )
          v41 = v38;
        *v41 = 0;
        WUPathCchAppend(v81, v37, v39);
        lpMem = 0;
        if ( (int)RegQueryStringValue(v42, v81, v36, &lpMem) >= 0 )
          goto LABEL_54;
        v43 = lpMem;
        if ( lpMem )
        {
          CSusBaseAllocTag<942762101>::operator delete(lpMem);
          lpMem = 0;
        }
        if ( (int)RegQueryStringValue(
                    v43,
                    L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                    L"AlternateServiceStackDLLPath",
                    &lpMem) >= 0 )
        {
LABEL_54:
          if ( v20 )
          {
            CSusBaseAllocTag<942762101>::operator delete(v20);
            v71 = 0;
          }
          v44 = lpMem;
          if ( (int)DuplicateString<wchar_t *,wchar_t *>(lpMem, &v71) >= 0 )
          {
            v68 = 0;
            WUTrace(0, 0, 4096, 4);
          }
          v20 = (WCHAR *)v71;
        }
        else
        {
          v44 = lpMem;
        }
        if ( v44 )
          CSusBaseAllocTag<942762101>::operator delete(v44);
      }
      SystemFilePath = CheckIfFileExists(v20);
      if ( SystemFilePath < 0 )
      {
        LODWORD(v68) = SystemFilePath;
        WUTrace(0, 0, 4096, 1);
        v23 = (unsigned int)SystemFilePath;
        v22 = 280;
        goto LABEL_66;
      }
      if ( a5 )
      {
        DirectoryW = SusMakeDirectoryW(v19, v45, v46);
        SystemFilePath = DirectoryW;
        if ( DirectoryW < 0 )
        {
          v23 = (unsigned int)DirectoryW;
          v22 = 286;
          goto LABEL_66;
        }
        LODWORD(lpMem) = 0;
        v48 = v73;
        while ( 1 )
        {
          lpExistingFileName = 0;
          SystemFilePath = CreateCombinedPath(v74, *((const wchar_t **)*v48 + 9), (wchar_t **)&lpExistingFileName);
          v26 = (WCHAR *)lpExistingFileName;
          if ( SystemFilePath < 0 )
          {
            v28 = 294;
            goto LABEL_83;
          }
          lpExistingFileName = 0;
          SystemFilePath = CreateCombinedPath(v19, *((const wchar_t **)*v73 + 9), (wchar_t **)&lpExistingFileName);
          v49 = (WCHAR *)lpExistingFileName;
          if ( SystemFilePath < 0 )
            break;
          SystemFilePath = SusCopyFileRetryIfSharingViolation(v26, lpExistingFileName, 0, 0xAu, v68);
          if ( SystemFilePath < 0 )
          {
            v51 = 304;
            goto LABEL_80;
          }
          if ( v49 )
            CSusBaseAllocTag<942762101>::operator delete(v49);
          if ( v26 )
            CSusBaseAllocTag<942762101>::operator delete(v26);
          LODWORD(lpMem) = (_DWORD)lpMem + 1;
          v48 = ++v73;
          if ( (unsigned int)lpMem >= a5 )
            goto LABEL_76;
        }
        v51 = 299;
LABEL_80:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v51,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
          (const char *)(unsigned int)SystemFilePath,
          (int)v68);
        if ( v49 )
          CSusBaseAllocTag<942762101>::operator delete(v49);
LABEL_85:
        if ( v26 )
          CSusBaseAllocTag<942762101>::operator delete(v26);
        goto LABEL_113;
      }
LABEL_76:
      v79 = 0;
      SystemFilePath = OSDeploymentHelper::CDeploymentSessionWrapper::CreateDeploymentSessionFromLibrary(
                         this,
                         v20,
                         v74,
                         v77,
                         a8,
                         (struct tagOptionalSessionInfo6 *)v78,
                         v76,
                         &v79);
      if ( SystemFilePath >= 0 )
      {
        v52 = v79;
        if ( v79 )
        {
          v79 = 0;
          v53 = *((_QWORD *)this + 11);
          if ( v53 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
          *((_QWORD *)this + 11) = v52;
          v54 = *((_QWORD *)this + 13);
          if ( v54 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
            *((_QWORD *)this + 13) = 0;
          }
          v55 = (**(__int64 (__fastcall ***)(struct IDeploymentSession *, GUID *, char *))v52)(
                  v52,
                  &GUID_3e309b3c_494d_4429_a607_fd4098ae813f,
                  (char *)this + 104);
          SystemFilePath = v55;
          if ( v55 < 0 )
          {
            if ( (unsigned int)(v55 + 2147467263) > 1 )
            {
              v69 = v55;
              WUTrace(0, 0, 4096, 1);
              v50 = 332;
              goto LABEL_96;
            }
            v21 = 0;
          }
          *((_BYTE *)this + 96) = v21;
          v56 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 11);
          v57 = *((_QWORD *)this + 14);
          if ( v57 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
            *((_QWORD *)this + 14) = 0;
          }
          (**v56)(v56, &GUID_36fb071a_6dc5_48bf_a6f3_d4f6751d39dc, (char *)this + 112);
          v58 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 11);
          v59 = *((_QWORD *)this + 15);
          if ( v59 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
            *((_QWORD *)this + 15) = 0;
          }
          (**v58)(v58, &GUID_09110432_1aee_49f8_9c1c_0f7d203777bf, (char *)this + 120);
          v60 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 11);
          v61 = *((_QWORD *)this + 16);
          if ( v61 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
            *((_QWORD *)this + 16) = 0;
          }
          (**v60)(v60, &GUID_347c6b31_7d10_4ada_9ede_ae9288f35f47, (char *)this + 128);
          v62 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 11);
          v63 = *((_QWORD *)this + 17);
          if ( v63 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
            *((_QWORD *)this + 17) = 0;
          }
          (**v62)(v62, &GUID_7d79e71d_36c6_4a20_bab0_0e44763c8ba9, (char *)this + 136);
          v64 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 11);
          v65 = *((_QWORD *)this + 18);
          if ( v65 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
            *((_QWORD *)this + 18) = 0;
          }
          (**v64)(v64, &GUID_68aaa5b1_d95c_482d_8967_41c07caa2adc, (char *)this + 144);
          v66 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 11);
          v67 = *((_QWORD *)this + 19);
          if ( v67 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
            *((_QWORD *)this + 19) = 0;
          }
          (**v66)(v66, &GUID_57816c47_d685_423a_89c6_feefbd90ed47, (char *)this + 152);
          SystemFilePath = 0;
          goto LABEL_111;
        }
        SystemFilePath = -2145112065;
        v50 = 317;
      }
      else
      {
        v50 = 315;
      }
LABEL_96:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v50,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
        (const char *)(unsigned int)SystemFilePath,
        v69);
LABEL_111:
      if ( v79 )
      {
        (*(void (__fastcall **)(struct IDeploymentSession *))(*(_QWORD *)v79 + 16LL))(v79);
        v79 = 0;
      }
      goto LABEL_113;
    }
    lpMem = 0;
    v25 = CreateCombinedPath(v10, lpExistingFileName, (wchar_t **)&lpMem);
    SystemFilePath = v25;
    v26 = (WCHAR *)lpMem;
    if ( v25 >= 0 )
    {
      SystemFilePath = CheckIfFileExists((const wchar_t *)lpMem);
      if ( SystemFilePath >= 0 )
      {
        v29 = CreateCombinedPath(v19, a4, (wchar_t **)&v71);
        SystemFilePath = v29;
        v30 = 0;
        if ( v29 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB7,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
            (const char *)(unsigned int)v29,
            (int)v68);
          v20 = (WCHAR *)v71;
          goto LABEL_85;
        }
        v31 = CheckIfDirExists(v19);
        v20 = (WCHAR *)v71;
        if ( v31 < 0
          || (v34 = SusDeleteFileRetryIfSharingViolation(v71, 6u, v32), SystemFilePath = v34, v34 > -2147024895)
          && (unsigned int)(v34 + 2147024892) > 0x7FF8FFFB )
        {
          while ( 1 )
          {
            v35 = DecompressCabFile(v26, v19, (unsigned int)v32, v33, v68);
            SystemFilePath = v35;
            if ( v35 >= 0 )
              break;
            if ( v35 == -2147024864 )
            {
              Sleep(0x2710u);
              if ( (unsigned int)++v30 < 6 )
                continue;
            }
            v28 = 223;
            goto LABEL_83;
          }
          v68 = 0;
          WUTrace(0, 0, 4096, 4);
          if ( v26 )
            CSusBaseAllocTag<942762101>::operator delete(v26);
          goto LABEL_39;
        }
        v28 = 197;
      }
      else
      {
        LODWORD(v68) = SystemFilePath;
        WUTrace(0, 0, 4096, 1);
        if ( (unsigned int)(SystemFilePath + 2147024894) <= 1 )
          goto LABEL_85;
        v28 = 179;
      }
LABEL_83:
      v27 = (unsigned int)SystemFilePath;
    }
    else
    {
      v27 = (unsigned int)v25;
      v28 = 165;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
      (const char *)v27,
      (int)v68);
    goto LABEL_85;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x33,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
    (const char *)(unsigned int)CombinedPath,
    (int)v68);
LABEL_115:
  if ( v19 )
    CSusBaseAllocTag<942762101>::operator delete(v19);
  return (unsigned int)SystemFilePath;
}

```

## disassembly

```asm
0x18003b800  push    rbp
0x18003b802  push    rbx
0x18003b803  push    rsi
0x18003b804  push    rdi
0x18003b805  push    r12
0x18003b807  push    r13
0x18003b809  push    r14
0x18003b80b  push    r15
0x18003b80d  lea     rbp, [rsp-258h]
0x18003b815  sub     rsp, 358h
0x18003b81c  mov     rax, cs:__security_cookie
0x18003b823  xor     rax, rsp
0x18003b826  mov     [rbp+290h+var_50], rax
0x18003b82d  mov     rsi, r9
0x18003b830  mov     [rsp+390h+lpExistingFileName], r8
0x18003b835  mov     rdi, rdx
0x18003b838  mov     [rsp+390h+var_330], rdx
0x18003b83d  mov     r13, rcx
0x18003b840  mov     rdx, [rbp+290h+arg_28]
0x18003b847  mov     [rsp+390h+var_338], rdx
0x18003b84c  mov     rax, [rbp+290h+arg_30]
0x18003b853  mov     [rsp+390h+var_318], rax
0x18003b858  mov     r14, [rbp+290h+arg_40]
0x18003b85f  mov     [rsp+390h+var_320], r14
0x18003b864  xor     r12d, r12d
0x18003b867  test    rdi, rdi
0x18003b86a  jnz     short loc_18003B891
0x18003b86c  lea     edx, [rdi+1Ah]; void *
0x18003b86f  mov     ebx, 80004003h
0x18003b874  mov     rcx, [rbp+298h]; this
0x18003b87b  mov     r9d, ebx; char *
0x18003b87e  lea     r8, aCW1SSrcClientE_19; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003b885  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b88a  mov     eax, ebx
0x18003b88c  jmp     loc_18003C0D0
0x18003b891  test    rsi, rsi
0x18003b894  jnz     short loc_18003B89B
0x18003b896  lea     edx, [rsi+1Bh]
0x18003b899  jmp     short loc_18003B86F
0x18003b89b  xor     edx, edx; Val
0x18003b89d  lea     r8d, [rdx+70h]; Size
0x18003b8a1  lea     rcx, [rbp+290h+var_310]; void *
0x18003b8a5  call    memset
0x18003b8aa  lea     r8, [rbp+290h+var_310]; void *
0x18003b8ae  mov     rdx, r14; unsigned int
0x18003b8b1  mov     ecx, dword ptr [rbp+290h+arg_38]; this
0x18003b8b7  call    ?BuildOptionalSessionInfo@OSDeploymentHelper@@YAJKPEAXAEAUtagOptionalSessionInfo6@@@Z; OSDeploymentHelper::BuildOptionalSessionInfo(ulong,void *,tagOptionalSessionInfo6 &)
0x18003b8bc  mov     ebx, eax
0x18003b8be  test    eax, eax
0x18003b8c0  jns     short loc_18003B8C9
0x18003b8c2  mov     edx, 27h ; '''
0x18003b8c7  jmp     short loc_18003B874
0x18003b8c9  test    r14, r14
0x18003b8cc  jz      short loc_18003B8DE
0x18003b8ce  mov     rax, [rbp+290h+var_2E0]
0x18003b8d2  test    rax, rax
0x18003b8d5  cmovnz  rdi, rax
0x18003b8d9  mov     [rsp+390h+var_330], rdi
0x18003b8de  mov     [rsp+390h+lpString1], r12
0x18003b8e3  lea     r8, [rsp+390h+lpString1]; wchar_t **
0x18003b8e8  lea     rdx, ?c_szUUPMetaDataSubFolder@CDeploymentSessionWrapper@OSDeploymentHelper@@2QB_WB; "Metadata"
0x18003b8ef  mov     rcx, rdi; wchar_t *
0x18003b8f2  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x18003b8f7  mov     r15d, eax
0x18003b8fa  mov     r14, [rsp+390h+lpString1]
0x18003b8ff  test    eax, eax
0x18003b901  jns     short loc_18003B923
0x18003b903  mov     rcx, [rbp+298h]; this
0x18003b90a  mov     r9d, eax; char *
0x18003b90d  lea     r8, aCW1SSrcClientE_19; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003b914  mov     edx, 33h ; '3'; void *
0x18003b919  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b91e  jmp     loc_18003C0C0
0x18003b923  mov     rbx, r12
0x18003b926  mov     [rsp+390h+var_348], rbx
0x18003b92b  xorps   xmm0, xmm0
0x18003b92e  movups  [rbp+290h+var_288], xmm0
0x18003b932  movups  [rbp+290h+var_278], xmm0
0x18003b936  movdqu  [rbp+290h+var_298], xmm0
0x18003b93b  mov     word ptr [rbp+290h+var_288], r12w
0x18003b940  mov     qword ptr [rbp+290h+var_288+8], r12
0x18003b944  mov     qword ptr [rbp+290h+var_278], r12
0x18003b948  mov     qword ptr [rbp+290h+var_278+8], r12
0x18003b94c  mov     r12d, 1
0x18003b952  mov     rax, [rsp+390h+lpExistingFileName]
0x18003b957  xor     ecx, ecx
0x18003b959  test    rax, rax
0x18003b95c  jnz     short loc_18003B9CF
0x18003b95e  mov     r8, rsi; wchar_t *
0x18003b961  lea     rcx, [rbp+290h+var_260]; wchar_t *
0x18003b965  call    ?GetSystemFilePath@@YAJPEA_W_KPEB_W@Z; GetSystemFilePath(wchar_t *,unsigned __int64,wchar_t const *)
0x18003b96a  mov     r15d, eax
0x18003b96d  xor     edi, edi
0x18003b96f  test    eax, eax
0x18003b971  jns     short loc_18003B97A
0x18003b973  mov     edx, 98h
0x18003b978  jmp     short loc_18003B999
0x18003b97a  lea     rdx, [rsp+390h+var_348]
0x18003b97f  lea     rcx, [rbp+290h+var_260]
0x18003b983  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18003b988  mov     r15d, eax
0x18003b98b  mov     rbx, [rsp+390h+var_348]
0x18003b990  test    eax, eax
0x18003b992  jns     short loc_18003B9A1
0x18003b994  mov     edx, 9Ah
0x18003b999  mov     r9d, r15d
0x18003b99c  jmp     loc_18003BCCF
0x18003b9a1  mov     [rsp+390h+var_360], rbx
0x18003b9a6  lea     rax, aUsingTheInboxS; "Using the inbox service stack dll file "...
0x18003b9ad  mov     [rsp+390h+var_368], rax
0x18003b9b2  mov     [rsp+390h+var_370], rdi
0x18003b9b7  xor     edx, edx
0x18003b9b9  xor     ecx, ecx
0x18003b9bb  lea     r9d, [rdx+4]
0x18003b9bf  mov     r8d, 1000h
0x18003b9c5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003b9ca  jmp     loc_18003BB38
0x18003b9cf  mov     [rsp+390h+lpMem], rcx
0x18003b9d4  lea     r8, [rsp+390h+lpMem]; wchar_t **
0x18003b9d9  mov     rdx, rax; wchar_t *
0x18003b9dc  mov     rcx, rdi; wchar_t *
0x18003b9df  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x18003b9e4  mov     r15d, eax
0x18003b9e7  mov     rdi, [rsp+390h+lpMem]
0x18003b9ec  test    eax, eax
0x18003b9ee  jns     short loc_18003B9FD
0x18003b9f0  mov     r9d, eax
0x18003b9f3  mov     edx, 0A5h
0x18003b9f8  jmp     loc_18003BE38
0x18003b9fd  mov     rcx, rdi; wchar_t *
0x18003ba00  call    ?CheckIfFileExists@@YAJPEB_W@Z; CheckIfFileExists(wchar_t const *)
0x18003ba05  mov     r15d, eax
0x18003ba08  test    eax, eax
0x18003ba0a  jns     short loc_18003BA4E
0x18003ba0c  mov     [rsp+390h+var_360], rdi
0x18003ba11  lea     rax, aFailedToFindTh_0; "Failed to find the service stack cab fi"...
0x18003ba18  mov     [rsp+390h+var_368], rax
0x18003ba1d  mov     dword ptr [rsp+390h+var_370], r15d
0x18003ba22  mov     r9d, r12d
0x18003ba25  xor     edx, edx
0x18003ba27  xor     ecx, ecx
0x18003ba29  mov     r8d, 1000h
0x18003ba2f  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003ba34  lea     eax, [r15+7FF8FFFEh]
0x18003ba3b  cmp     eax, r12d
0x18003ba3e  jbe     loc_18003BE4B
0x18003ba44  mov     edx, 0B3h
0x18003ba49  jmp     loc_18003BE35
0x18003ba4e  lea     r8, [rsp+390h+var_348]; wchar_t **
0x18003ba53  mov     rdx, rsi; wchar_t *
0x18003ba56  mov     rcx, r14; wchar_t *
0x18003ba59  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x18003ba5e  mov     r15d, eax
0x18003ba61  xor     esi, esi
0x18003ba63  test    eax, eax
0x18003ba65  jns     short loc_18003BA8C
0x18003ba67  mov     rcx, [rbp+298h]; this
0x18003ba6e  mov     r9d, eax; char *
0x18003ba71  lea     r8, aCW1SSrcClientE_19; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003ba78  mov     edx, 0B7h; void *
0x18003ba7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ba82  mov     rbx, [rsp+390h+var_348]
0x18003ba87  jmp     loc_18003BE4B
0x18003ba8c  mov     rcx, r14; wchar_t *
0x18003ba8f  call    ?CheckIfDirExists@@YAJPEB_W@Z; CheckIfDirExists(wchar_t const *)
0x18003ba94  mov     rbx, [rsp+390h+var_348]
0x18003ba99  test    eax, eax
0x18003ba9b  js      short loc_18003BACA
0x18003ba9d  mov     edx, 6; unsigned int
0x18003baa2  mov     rcx, rbx; lpString1
0x18003baa5  call    ?SusDeleteFileRetryIfSharingViolation@@YAJPEB_WKPEAX@Z; SusDeleteFileRetryIfSharingViolation(wchar_t const *,ulong,void *)
0x18003baaa  mov     r15d, eax
0x18003baad  cmp     eax, 80070001h
0x18003bab2  jle     short loc_18003BAC0
0x18003bab4  add     eax, 7FF8FFFCh
0x18003bab9  cmp     eax, 7FF8FFFBh
0x18003babe  ja      short loc_18003BACA
0x18003bac0  mov     edx, 0C5h
0x18003bac5  jmp     loc_18003BE35
0x18003baca  mov     rdx, r14; wchar_t *
0x18003bacd  mov     rcx, rdi; wchar_t *
0x18003bad0  call    ?DecompressCabFile@@YAJPEB_W0K0PEAX@Z; DecompressCabFile(wchar_t const *,wchar_t const *,ulong,wchar_t const *,void *)
0x18003bad5  mov     r15d, eax
0x18003bad8  xor     ecx, ecx
0x18003bada  test    eax, eax
0x18003badc  jns     short loc_18003BB02
0x18003bade  cmp     eax, 80070020h
0x18003bae3  jnz     short loc_18003BAF8
0x18003bae5  mov     ecx, 2710h; dwMilliseconds
0x18003baea  call    cs:__imp_Sleep
0x18003baf0  add     esi, r12d
0x18003baf3  cmp     esi, 6
0x18003baf6  jb      short loc_18003BACA
0x18003baf8  mov     edx, 0DFh
0x18003bafd  jmp     loc_18003BE35
0x18003bb02  mov     [rsp+390h+var_360], rbx
0x18003bb07  lea     rax, aUsingTheUpdate; "Using the update's service stack dll fi"...
0x18003bb0e  mov     [rsp+390h+var_368], rax
0x18003bb13  mov     [rsp+390h+var_370], rcx
0x18003bb18  xor     edx, edx
0x18003bb1a  lea     r9d, [rdx+4]
0x18003bb1e  mov     r8d, 1000h
0x18003bb24  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003bb29  test    rdi, rdi
0x18003bb2c  jz      short loc_18003BB36
0x18003bb2e  mov     rcx, rdi; lpMem
0x18003bb31  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18003bb36  xor     edi, edi
0x18003bb38  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x18003bb3d  test    eax, eax
0x18003bb3f  jz      loc_18003BC6B
0x18003bb45  lea     rsi, aGlobal; "Global"
0x18003bb4c  cmp     [rsp+390h+var_320], rdi
0x18003bb51  jz      short loc_18003BB5E
0x18003bb53  mov     rax, [rbp+290h+var_308]
0x18003bb57  test    rax, rax
0x18003bb5a  cmovnz  rsi, rax
0x18003bb5e  mov     edx, 104h
0x18003bb63  lea     rcx, [rbp+290h+var_260]
0x18003bb67  lea     r8, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003bb6e  lea     rax, [rbp+290h+var_260]
0x18003bb72  sub     r8, rax; wchar_t *
0x18003bb75  lea     rax, [rdx+7FFFFEFAh]
0x18003bb7c  test    rax, rax
0x18003bb7f  jz      short loc_18003BB97
0x18003bb81  movzx   eax, word ptr [r8+rcx]
0x18003bb86  test    ax, ax
0x18003bb89  jz      short loc_18003BB97
0x18003bb8b  mov     [rcx], ax
0x18003bb8e  add     rcx, 2
0x18003bb92  sub     rdx, r12; unsigned int
0x18003bb95  jnz     short loc_18003BB75
0x18003bb97  lea     rax, [rcx-2]
0x18003bb9b  test    rdx, rdx
0x18003bb9e  cmovnz  rax, rcx
0x18003bba2  mov     [rax], di
0x18003bba5  lea     rcx, [rbp+290h+var_260]; wchar_t *
0x18003bba9  call    ?WUPathCchAppend@@YAJPEA_WKPEB_W@Z; WUPathCchAppend(wchar_t *,ulong,wchar_t const *)
0x18003bbae  mov     [rsp+390h+lpMem], rdi
0x18003bbb3  lea     r9, [rsp+390h+lpMem]
0x18003bbb8  mov     r8, rsi
0x18003bbbb  lea     rdx, [rbp+290h+var_260]
0x18003bbbf  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEAPEA_WW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,RegistryHiveType)
0x18003bbc4  test    eax, eax
0x18003bbc6  jns     short loc_18003BBFF
0x18003bbc8  mov     rcx, [rsp+390h+lpMem]; lpMem
0x18003bbcd  test    rcx, rcx
0x18003bbd0  jz      short loc_18003BBDC
0x18003bbd2  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18003bbd7  mov     [rsp+390h+lpMem], rdi
0x18003bbdc  lea     r9, [rsp+390h+lpMem]
0x18003bbe1  lea     r8, aAlternateservi; "AlternateServiceStackDLLPath"
0x18003bbe8  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003bbef  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEAPEA_WW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,RegistryHiveType)
0x18003bbf4  test    eax, eax
0x18003bbf6  jns     short loc_18003BBFF
0x18003bbf8  mov     rdi, [rsp+390h+lpMem]
0x18003bbfd  jmp     short loc_18003BC5C
0x18003bbff  test    rbx, rbx
0x18003bc02  jz      short loc_18003BC11
0x18003bc04  mov     rcx, rbx; lpMem
0x18003bc07  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18003bc0c  mov     [rsp+390h+var_348], rdi
0x18003bc11  lea     rdx, [rsp+390h+var_348]
0x18003bc16  mov     rdi, [rsp+390h+lpMem]
0x18003bc1b  mov     rcx, rdi
0x18003bc1e  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18003bc23  xor     ebx, ebx
0x18003bc25  test    eax, eax
0x18003bc27  js      short loc_18003BC57
0x18003bc29  mov     [rsp+390h+var_358], rsi
0x18003bc2e  mov     [rsp+390h+var_360], rdi
0x18003bc33  lea     rax, aUsingTestServi; "Using test service stack dll file '%ws'"...
0x18003bc3a  mov     [rsp+390h+var_368], rax
0x18003bc3f  mov     [rsp+390h+var_370], rbx; int
0x18003bc44  xor     edx, edx
0x18003bc46  xor     ecx, ecx
0x18003bc48  lea     r9d, [rbx+4]
0x18003bc4c  mov     r8d, 1000h
0x18003bc52  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003bc57  mov     rbx, [rsp+390h+var_348]
0x18003bc5c  test    rdi, rdi
0x18003bc5f  jz      short loc_18003BC69
0x18003bc61  mov     rcx, rdi; lpMem
0x18003bc64  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18003bc69  xor     edi, edi
0x18003bc6b  mov     rcx, rbx; wchar_t *
0x18003bc6e  call    ?CheckIfFileExists@@YAJPEB_W@Z; CheckIfFileExists(wchar_t const *)
0x18003bc73  mov     r15d, eax
0x18003bc76  test    eax, eax
0x18003bc78  jns     short loc_18003BCAC
0x18003bc7a  mov     [rsp+390h+var_360], rbx
0x18003bc7f  lea     rax, aFailedToFindTh; "Failed to find the service stack dll fi"...
0x18003bc86  mov     [rsp+390h+var_368], rax
0x18003bc8b  mov     dword ptr [rsp+390h+var_370], r15d
0x18003bc90  mov     r9d, r12d
0x18003bc93  xor     edx, edx
0x18003bc95  xor     ecx, ecx
0x18003bc97  mov     r8d, 1000h
0x18003bc9d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
  ... truncated ...
```
