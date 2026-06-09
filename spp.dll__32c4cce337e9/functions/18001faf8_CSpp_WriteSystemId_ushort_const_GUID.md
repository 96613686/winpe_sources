# CSpp::_WriteSystemId(ushort const *,_GUID *)

- ea: `0x18001faf8`
- end: `0x18001ff44`
- name: `?_WriteSystemId@CSpp@@AEAAJPEBGPEAU_GUID@@@Z`
- size: `1100`
- prototype: `__int64 __fastcall(CSpp *__hidden this, const unsigned __int16 *, struct _GUID *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000e660`
- `0x180018844`

## callees

- `0x180014c48`
- `0x18001faf8`
- `0x180020908`
- `0x1800268b4`
- `0x1800269ac`
- `0x180027eac`
- `0x18002b6ec`
- `0x18002b8cc`
- `0x18002d408`
- `0x18002d6e8`
- `0x18002eb80`
- `0x180034de0`
- `0x18003532c`
- `0x180035390`
- `0x1800353c4`
- `0x180035b00`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001feb5`
- `KERNEL32!LocalFree` at `0x18001feb5`
- `KERNEL32!CreateFileW` at `0x18001fe01`
- `KERNEL32!CreateFileW` at `0x18001fe01`
- `KERNEL32!WriteFile` at `0x18001fe5a`
- `KERNEL32!WriteFile` at `0x18001fe5a`
- `KERNEL32!CloseHandle` at `0x18001fef7`
- `KERNEL32!CloseHandle` at `0x18001ff0a`
- `KERNEL32!CloseHandle` at `0x18001fef7`
- `KERNEL32!CloseHandle` at `0x18001ff0a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001fced`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001fced`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001fd17`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001fd17`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001fd4f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001fd4f`

## string_xrefs

- `0x18001fb64`: `CSpp::_WriteSystemId`
- `0x18001fc42`: `System32\Restore`

## pseudocode

```c
__int64 __fastcall CSpp::_WriteSystemId(CSpp *this, const unsigned __int16 *a2, struct _GUID *a3)
{
  __int64 v5; // rsi
  char *v6; // rbx
  __int64 v7; // rdi
  __int16 v8; // ax
  unsigned __int16 v9; // dx
  bool v10; // zf
  __int64 v11; // rcx
  int v12; // eax
  const unsigned __int16 *v13; // rdx
  unsigned int v14; // r9d
  bool v15; // sf
  __int64 v16; // rcx
  DWORD v17; // esi
  __int64 v18; // rcx
  unsigned int v19; // esi
  __int64 v20; // rdx
  __int64 v21; // r8
  const unsigned __int16 *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v25; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v26; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v27; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v28; // [rsp+50h] [rbp-B0h]
  int SpecialDirectory; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v30; // [rsp+64h] [rbp-9Ch]
  __int16 v31; // [rsp+66h] [rbp-9Ah]
  DWORD NumberOfBytesWritten; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+A0h] [rbp-60h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE TokenHandle; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v36[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v37[2]; // [rsp+D0h] [rbp-30h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+E0h] [rbp-20h] BYREF
  GUID pguid; // [rsp+F8h] [rbp-8h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+108h] [rbp+8h] BYREF
  OLECHAR sz; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v42[78]; // [rsp+122h] [rbp+22h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, 0);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&SpecialDirectory, "CSpp::_WriteSystemId", 2792, 1);
  v5 = -1;
  lpFileName[0] = &FileName;
  v6 = 0;
  lpFileName[1] = 0;
  TokenHandle = 0;
  v37[0] = (unsigned __int16 *)&FileName;
  v37[1] = 0;
  v7 = -1;
  v36[0] = (unsigned __int16 *)&FileName;
  v36[1] = 0;
  pguid = GUID_NULL;
  sz = 0;
  memset_0(v42, 0, 0x4Cu);
  NumberOfBytesWritten = 0;
  SecurityDescriptor = 0;
  v8 = 2807;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  NewState = 0;
  if ( !a3 )
  {
    SpecialDirectory = -2147024809;
LABEL_6:
    v31 = v8;
    goto LABEL_29;
  }
  SpecialDirectory = 0;
  v30 = 2807;
  SpecialDirectory = CBsString::Set((CBsString *)lpFileName, L"%SystemRoot%\\");
  v8 = 2820;
  if ( SpecialDirectory < 0 )
    goto LABEL_6;
  v30 = 2820;
  SpecialDirectory = CBsString::Trailing((CBsString *)lpFileName, v9);
  v8 = 2821;
  if ( SpecialDirectory < 0 )
    goto LABEL_6;
  v30 = 2821;
  SpecialDirectory = CBsString::Append((CBsString *)lpFileName, L"System32\\Restore");
  v8 = 2822;
  if ( SpecialDirectory < 0 )
    goto LABEL_6;
  v30 = 2822;
  SpecialDirectory = SxCrackPath(lpFileName[0], (struct CBsString *)v36, (struct CBsString *)v37);
  v8 = 2828;
  if ( SpecialDirectory < 0 )
    goto LABEL_6;
  v30 = 2828;
  SpecialDirectory = CSpp::_CreateSpecialDirectory(this, v36[0], v37[0]);
  v8 = 2829;
  if ( SpecialDirectory < 0 )
    goto LABEL_6;
  v30 = 2829;
  SpecialDirectory = CBsString::SetPath(
                       (CBsString *)lpFileName,
                       v36[0],
                       v37[0],
                       L"MachineGuid.txt",
                       0,
                       dwFlagsAndAttributes,
                       hTemplateFile,
                       v25,
                       v26,
                       v27,
                       v28);
  v8 = 2834;
  if ( SpecialDirectory < 0 )
    goto LABEL_6;
  v30 = 2834;
  SpecialDirectory = CoCreateGuid(&pguid);
  v8 = 2836;
  if ( SpecialDirectory < 0 )
    goto LABEL_6;
  v30 = 2836;
  v10 = StringFromGUID2(&pguid, &sz, 39) == 0;
  v8 = 2837;
  if ( v10 )
  {
    SpecialDirectory = -2147418113;
    goto LABEL_6;
  }
  SpecialDirectory = 0;
  v30 = 2837;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:SYG:SYD:P(A;OICI;GA;;;SY)(A;OICI;GR;;;BA)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    SpecialDirectory = GetLastFailureAsHRESULT(v11);
    v8 = 2846;
    goto LABEL_6;
  }
  SpecialDirectory = 0;
  v30 = 2846;
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 0;
  SecurityDescriptor = 0;
  v12 = SxOpenThreadOrProcessToken(v11, &TokenHandle);
  v6 = (char *)TokenHandle;
  v15 = v12 < 0;
  SpecialDirectory = v12;
  v8 = 2856;
  if ( v15 )
    goto LABEL_6;
  v30 = 2856;
  SpecialDirectory = AssertPrivilegeOnTokenPreserveOrig(TokenHandle, v13, &NewState, v14);
  v8 = 2861;
  if ( SpecialDirectory < 0 )
    goto LABEL_6;
  v30 = 2861;
  SxDeleteFile(lpFileName[0]);
  v7 = (__int64)CreateFileW(lpFileName[0], 2u, 0, &SecurityAttributes, 2u, 5u, 0);
  if ( ((v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    SpecialDirectory = GetLastFailureAsHRESULT(v16);
    v8 = 2878;
    goto LABEL_6;
  }
  SpecialDirectory = 0;
  v30 = 2878;
  do
    ++v5;
  while ( *(_WORD *)&v42[2 * v5 - 2] );
  v17 = 2 * v5;
  if ( !WriteFile((HANDLE)v7, &sz, v17, &NumberOfBytesWritten, 0) )
  {
    SpecialDirectory = GetLastFailureAsHRESULT(v18);
    v8 = 2881;
    goto LABEL_6;
  }
  SpecialDirectory = 0;
  v30 = 2881;
  if ( NumberOfBytesWritten != v17 )
  {
    SpecialDirectory = GetLastFailureAsHRESULT(v18);
    v8 = 2882;
    goto LABEL_6;
  }
  v30 = 2882;
  *a3 = pguid;
LABEL_29:
  LocalFree(SecurityAttributes.lpSecurityDescriptor);
  SecurityAttributes.lpSecurityDescriptor = 0;
  RestoreOrigPrivilegeOnToken(v6, &NewState);
  v19 = SpecialDirectory;
  CBsString::_Release(v36);
  CBsString::_Release(v37);
  CBsString::_Release((unsigned __int16 **)lpFileName);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v7);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&SpecialDirectory, v20, v21);
  return v19;
}

```

## disassembly

```asm
0x18001faf8  mov     [rsp-8+arg_8], rbx
0x18001fafd  mov     [rsp-8+arg_18], rsi
0x18001fb02  push    rbp
0x18001fb03  push    rdi
0x18001fb04  push    r12
0x18001fb06  push    r14
0x18001fb08  push    r15
0x18001fb0a  lea     rbp, [rsp-80h]
0x18001fb0f  sub     rsp, 180h
0x18001fb16  mov     rax, cs:__security_cookie
0x18001fb1d  xor     rax, rsp
0x18001fb20  mov     [rbp+0A0h+var_30], rax
0x18001fb24  mov     r15, r8
0x18001fb27  mov     r14, rcx
0x18001fb2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb31  lea     rax, WPP_GLOBAL_Control
0x18001fb38  cmp     rcx, rax
0x18001fb3b  jz      short loc_18001FB5E
0x18001fb3d  test    dword ptr [rcx+1Ch], 20000000h
0x18001fb44  jz      short loc_18001FB5E
0x18001fb46  mov     rcx, [rcx+10h]
0x18001fb4a  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001fb51  mov     edx, 1Ch
0x18001fb56  xor     r9d, r9d
0x18001fb59  call    WPP_SF_S
0x18001fb5e  mov     r9d, 1; unsigned __int16
0x18001fb64  lea     rdx, aCsppWritesyste; "CSpp::_WriteSystemId"
0x18001fb6b  mov     r8d, 0AE8h; unsigned __int16
0x18001fb71  lea     rcx, [rsp+1A0h+var_140]; this
0x18001fb76  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001fb7b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001fb82  xor     r12d, r12d
0x18001fb85  lea     rax, FileName
0x18001fb8c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001fb90  mov     [rbp+0A0h+lpFileName], rax
0x18001fb94  mov     ebx, r12d
0x18001fb97  mov     [rbp+0A0h+var_F8], r12
0x18001fb9b  xor     edx, edx; Val
0x18001fb9d  mov     [rbp+0A0h+TokenHandle], rbx
0x18001fba1  lea     rcx, [rbp+0A0h+var_7E]; void *
0x18001fba5  mov     [rbp+0A0h+var_D0], rax
0x18001fba9  lea     r8d, [rsi+4Dh]; Size
0x18001fbad  mov     [rbp+0A0h+var_C8], r12
0x18001fbb1  mov     rdi, rsi
0x18001fbb4  mov     [rbp+0A0h+var_E0], rax
0x18001fbb8  mov     [rbp+0A0h+var_D8], r12
0x18001fbbc  movdqu  xmmword ptr [rbp+0A0h+pguid.Data1], xmm0
0x18001fbc1  mov     [rbp+0A0h+sz], r12w
0x18001fbc6  call    memset_0
0x18001fbcb  xor     eax, eax
0x18001fbcd  mov     [rbp+0A0h+NumberOfBytesWritten], r12d
0x18001fbd1  mov     qword ptr [rbp+0A0h+SecurityAttributes.bInheritHandle], rax
0x18001fbd5  xorps   xmm0, xmm0
0x18001fbd8  mov     [rbp+0A0h+SecurityDescriptor], r12
0x18001fbdc  mov     eax, 0AF7h
0x18001fbe1  movups  xmmword ptr [rbp+0A0h+SecurityAttributes.nLength], xmm0
0x18001fbe5  movups  xmmword ptr [rbp+0A0h+NewState.PrivilegeCount], xmm0
0x18001fbe9  test    r15, r15
0x18001fbec  jnz     short loc_18001FC00
0x18001fbee  mov     [rsp+1A0h+var_140], 80070057h
0x18001fbf6  mov     [rsp+1A0h+var_13A], ax
0x18001fbfb  jmp     loc_18001FEB1
0x18001fc00  lea     rdx, aSystemroot; "%SystemRoot%\\"
0x18001fc07  mov     [rsp+1A0h+var_140], r12d
0x18001fc0c  lea     rcx, [rbp+0A0h+lpFileName]; this
0x18001fc10  mov     [rsp+1A0h+var_13C], ax
0x18001fc15  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001fc1a  mov     [rsp+1A0h+var_140], eax
0x18001fc1e  test    eax, eax
0x18001fc20  mov     eax, 0B04h
0x18001fc25  js      short loc_18001FBF6
0x18001fc27  lea     rcx, [rbp+0A0h+lpFileName]; this
0x18001fc2b  mov     [rsp+1A0h+var_13C], ax
0x18001fc30  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18001fc35  mov     [rsp+1A0h+var_140], eax
0x18001fc39  test    eax, eax
0x18001fc3b  mov     eax, 0B05h
0x18001fc40  js      short loc_18001FBF6
0x18001fc42  lea     rdx, aSystem32Restor; "System32\\Restore"
0x18001fc49  mov     [rsp+1A0h+var_13C], ax
0x18001fc4e  lea     rcx, [rbp+0A0h+lpFileName]; this
0x18001fc52  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18001fc57  mov     [rsp+1A0h+var_140], eax
0x18001fc5b  test    eax, eax
0x18001fc5d  mov     eax, 0B06h
0x18001fc62  js      short loc_18001FBF6
0x18001fc64  mov     rcx, [rbp+0A0h+lpFileName]; lpSrc
0x18001fc68  lea     r8, [rbp+0A0h+var_D0]; struct CBsString *
0x18001fc6c  lea     rdx, [rbp+0A0h+var_E0]; this
0x18001fc70  mov     [rsp+1A0h+var_13C], ax
0x18001fc75  call    ?SxCrackPath@@YAJPEBGPEAVCBsString@@1@Z; SxCrackPath(ushort const *,CBsString *,CBsString *)
0x18001fc7a  mov     [rsp+1A0h+var_140], eax
0x18001fc7e  test    eax, eax
0x18001fc80  mov     eax, 0B0Ch
0x18001fc85  js      loc_18001FBF6
0x18001fc8b  mov     r8, [rbp+0A0h+var_D0]; unsigned __int16 *
0x18001fc8f  mov     rcx, r14; this
0x18001fc92  mov     rdx, [rbp+0A0h+var_E0]; unsigned __int16 *
0x18001fc96  mov     [rsp+1A0h+var_13C], ax
0x18001fc9b  call    ?_CreateSpecialDirectory@CSpp@@AEAAJPEBG0@Z; CSpp::_CreateSpecialDirectory(ushort const *,ushort const *)
0x18001fca0  mov     [rsp+1A0h+var_140], eax
0x18001fca4  test    eax, eax
0x18001fca6  mov     eax, 0B0Dh
0x18001fcab  js      loc_18001FBF6
0x18001fcb1  mov     r8, [rbp+0A0h+var_D0]; unsigned __int16 *
0x18001fcb5  lea     r9, aMachineguidTxt; "MachineGuid.txt"
0x18001fcbc  mov     rdx, [rbp+0A0h+var_E0]; unsigned __int16 *
0x18001fcc0  lea     rcx, [rbp+0A0h+lpFileName]; this
0x18001fcc4  mov     [rsp+1A0h+var_13C], ax
0x18001fcc9  mov     qword ptr [rsp+1A0h+dwCreationDisposition], r12; unsigned __int16 *
0x18001fcce  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001fcd3  mov     [rsp+1A0h+var_140], eax
0x18001fcd7  test    eax, eax
0x18001fcd9  mov     eax, 0B12h
0x18001fcde  js      loc_18001FBF6
0x18001fce4  lea     rcx, [rbp+0A0h+pguid]; pguid
0x18001fce8  mov     [rsp+1A0h+var_13C], ax
0x18001fced  call    cs:__imp_CoCreateGuid
0x18001fcf3  mov     [rsp+1A0h+var_140], eax
0x18001fcf7  test    eax, eax
0x18001fcf9  mov     eax, 0B14h
0x18001fcfe  js      loc_18001FBF6
0x18001fd04  mov     r8d, 27h ; '''; cchMax
0x18001fd0a  mov     [rsp+1A0h+var_13C], ax
0x18001fd0f  lea     rdx, [rbp+0A0h+sz]; lpsz
0x18001fd13  lea     rcx, [rbp+0A0h+pguid]; rguid
0x18001fd17  call    cs:__imp_StringFromGUID2
0x18001fd1d  test    eax, eax
0x18001fd1f  mov     eax, 0B15h
0x18001fd24  jnz     short loc_18001FD33
0x18001fd26  mov     [rsp+1A0h+var_140], 8000FFFFh
0x18001fd2e  jmp     loc_18001FBF6
0x18001fd33  xor     r9d, r9d; SecurityDescriptorSize
0x18001fd36  mov     [rsp+1A0h+var_140], r12d
0x18001fd3b  lea     r8, [rbp+0A0h+SecurityDescriptor]; SecurityDescriptor
0x18001fd3f  mov     [rsp+1A0h+var_13C], ax
0x18001fd44  lea     rcx, aOSygSydPAOiciG; "O:SYG:SYD:P(A;OICI;GA;;;SY)(A;OICI;GR;;"...
0x18001fd4b  lea     edx, [r9+1]; StringSDRevision
0x18001fd4f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001fd55  test    eax, eax
0x18001fd57  jnz     short loc_18001FD6C
0x18001fd59  call    GetLastFailureAsHRESULT
0x18001fd5e  mov     [rsp+1A0h+var_140], eax
0x18001fd62  mov     eax, 0B1Eh
0x18001fd67  jmp     loc_18001FBF6
0x18001fd6c  mov     eax, 0B1Eh
0x18001fd71  mov     [rsp+1A0h+var_140], r12d
0x18001fd76  mov     [rsp+1A0h+var_13C], ax
0x18001fd7b  lea     rdx, [rbp+0A0h+TokenHandle]; void **
0x18001fd7f  mov     rax, [rbp+0A0h+SecurityDescriptor]
0x18001fd83  mov     [rbp+0A0h+SecurityAttributes.lpSecurityDescriptor], rax
0x18001fd87  mov     [rbp+0A0h+SecurityAttributes.nLength], 18h
0x18001fd8e  mov     [rbp+0A0h+SecurityAttributes.bInheritHandle], r12d
0x18001fd92  mov     [rbp+0A0h+SecurityDescriptor], r12
0x18001fd96  call    ?SxOpenThreadOrProcessToken@@YAJKPEAPEAX@Z; SxOpenThreadOrProcessToken(ulong,void * *)
0x18001fd9b  mov     rbx, [rbp+0A0h+TokenHandle]
0x18001fd9f  test    eax, eax
0x18001fda1  mov     [rsp+1A0h+var_140], eax
0x18001fda5  mov     eax, 0B28h
0x18001fdaa  js      loc_18001FBF6
0x18001fdb0  lea     r8, [rbp+0A0h+NewState]; struct _TOKEN_PRIVILEGES *
0x18001fdb4  mov     [rsp+1A0h+var_13C], ax
0x18001fdb9  mov     rcx, rbx; TokenHandle
0x18001fdbc  call    ?AssertPrivilegeOnTokenPreserveOrig@@YAJPEAXPEBGPEAU_TOKEN_PRIVILEGES@@K@Z; AssertPrivilegeOnTokenPreserveOrig(void *,ushort const *,_TOKEN_PRIVILEGES *,ulong)
0x18001fdc1  mov     [rsp+1A0h+var_140], eax
0x18001fdc5  test    eax, eax
0x18001fdc7  mov     eax, 0B2Dh
0x18001fdcc  js      loc_18001FBF6
0x18001fdd2  mov     rcx, [rbp+0A0h+lpFileName]; lpFileName
0x18001fdd6  mov     [rsp+1A0h+var_13C], ax
0x18001fddb  call    ?SxDeleteFile@@YAJPEBG@Z; SxDeleteFile(ushort const *)
0x18001fde0  mov     rcx, [rbp+0A0h+lpFileName]; lpFileName
0x18001fde4  lea     r9, [rbp+0A0h+SecurityAttributes]; lpSecurityAttributes
0x18001fde8  mov     edx, 2; dwDesiredAccess
0x18001fded  mov     [rsp+1A0h+hTemplateFile], r12; hTemplateFile
0x18001fdf2  mov     dword ptr [rsp+1A0h+dwFlagsAndAttributes], 5; dwFlagsAndAttributes
0x18001fdfa  xor     r8d, r8d; dwShareMode
0x18001fdfd  mov     [rsp+1A0h+dwCreationDisposition], edx; dwCreationDisposition
0x18001fe01  call    cs:__imp_CreateFileW
0x18001fe07  mov     rdi, rax
0x18001fe0a  inc     rax
0x18001fe0d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001fe13  jnz     short loc_18001FE28
0x18001fe15  call    GetLastFailureAsHRESULT
0x18001fe1a  mov     [rsp+1A0h+var_140], eax
0x18001fe1e  mov     eax, 0B3Eh
0x18001fe23  jmp     loc_18001FBF6
0x18001fe28  mov     eax, 0B3Eh
0x18001fe2d  mov     [rsp+1A0h+var_140], r12d
0x18001fe32  mov     [rsp+1A0h+var_13C], ax
0x18001fe37  lea     rax, [rbp+0A0h+sz]
0x18001fe3b  inc     rsi
0x18001fe3e  cmp     [rax+rsi*2], r12w
0x18001fe43  jnz     short loc_18001FE3B
0x18001fe45  add     esi, esi
0x18001fe47  mov     qword ptr [rsp+1A0h+dwCreationDisposition], r12; lpOverlapped
0x18001fe4c  mov     r8d, esi; nNumberOfBytesToWrite
0x18001fe4f  lea     r9, [rbp+0A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001fe53  lea     rdx, [rbp+0A0h+sz]; lpBuffer
0x18001fe57  mov     rcx, rdi; hFile
0x18001fe5a  call    cs:__imp_WriteFile
0x18001fe60  test    eax, eax
0x18001fe62  jnz     short loc_18001FE77
0x18001fe64  call    GetLastFailureAsHRESULT
0x18001fe69  mov     [rsp+1A0h+var_140], eax
0x18001fe6d  mov     eax, 0B41h
0x18001fe72  jmp     loc_18001FBF6
0x18001fe77  mov     eax, 0B41h
0x18001fe7c  mov     [rsp+1A0h+var_140], r12d
0x18001fe81  mov     [rsp+1A0h+var_13C], ax
0x18001fe86  cmp     [rbp+0A0h+NumberOfBytesWritten], esi
0x18001fe89  jz      short loc_18001FE9E
0x18001fe8b  call    GetLastFailureAsHRESULT
0x18001fe90  mov     [rsp+1A0h+var_140], eax
0x18001fe94  mov     eax, 0B42h
0x18001fe99  jmp     loc_18001FBF6
0x18001fe9e  movups  xmm0, xmmword ptr [rbp+0A0h+pguid.Data1]
0x18001fea2  mov     eax, 0B42h
0x18001fea7  mov     [rsp+1A0h+var_13C], ax
0x18001feac  movdqu  xmmword ptr [r15], xmm0
0x18001feb1  mov     rcx, [rbp+0A0h+SecurityAttributes.lpSecurityDescriptor]; hMem
0x18001feb5  call    cs:__imp_LocalFree
0x18001febb  lea     rdx, [rbp+0A0h+NewState]; NewState
0x18001febf  mov     [rbp+0A0h+SecurityAttributes.lpSecurityDescriptor], r12
0x18001fec3  mov     rcx, rbx; TokenHandle
0x18001fec6  call    ?RestoreOrigPrivilegeOnToken@@YAJPEAXPEAU_TOKEN_PRIVILEGES@@@Z; RestoreOrigPrivilegeOnToken(void *,_TOKEN_PRIVILEGES *)
0x18001fecb  mov     esi, [rsp+1A0h+var_140]
0x18001fecf  lea     rcx, [rbp+0A0h+var_E0]; this
0x18001fed3  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001fed8  lea     rcx, [rbp+0A0h+var_D0]; this
0x18001fedc  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001fee1  lea     rcx, [rbp+0A0h+lpFileName]; this
0x18001fee5  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001feea  lea     rax, [rbx-1]
0x18001feee  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001fef2  ja      short loc_18001FEFD
0x18001fef4  mov     rcx, rbx; hObject
0x18001fef7  call    cs:__imp_CloseHandle
0x18001fefd  lea     rcx, [rdi-1]
0x18001ff01  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001ff05  ja      short loc_18001FF10
0x18001ff07  mov     rcx, rdi; hObject
0x18001ff0a  call    cs:__imp_CloseHandle
0x18001ff10  lea     rcx, [rsp+1A0h+var_140]; this
0x18001ff15  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001ff1a  mov     eax, esi
0x18001ff1c  mov     rcx, [rbp+0A0h+var_30]
0x18001ff20  xor     rcx, rsp; StackCookie
0x18001ff23  call    __security_check_cookie
0x18001ff28  lea     r11, [rsp+1A0h+var_20]
0x18001ff30  mov     rbx, [r11+38h]
0x18001ff34  mov     rsi, [r11+48h]
0x18001ff38  mov     rsp, r11
0x18001ff3b  pop     r15
0x18001ff3d  pop     r14
0x18001ff3f  pop     r12
0x18001ff41  pop     rdi
0x18001ff42  pop     rbp
0x18001ff43  retn
```
