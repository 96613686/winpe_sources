# InstallInfSections

- ea: `0x180036aa0`
- end: `0x180036e6c`
- name: `InstallInfSections`
- size: `972`
- prototype: `__int64 __fastcall(HINSTANCE hModule)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180039aa4`
- `0x18003b2c8`
- `0x18003ef38`
- `0x180040650`
- `0x18004086c`

## callees

- `0x180007824`
- `0x180036544`
- `0x1800365bc`
- `0x180036928`
- `0x180036aa0`
- `0x18003abe4`
- `0x18004d030`
- `0x18004d350`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180036dd8`
- `KERNEL32!lstrlenW` at `0x180036dd8`
- `KERNEL32!Sleep` at `0x180036d3f`
- `KERNEL32!Sleep` at `0x180036d3f`
- `KERNEL32!CopyFileW` at `0x180036cc2`
- `KERNEL32!CopyFileW` at `0x180036cc2`
- `KERNEL32!DeleteFileW` at `0x180036e2d`
- `KERNEL32!DeleteFileW` at `0x180036e3a`
- `KERNEL32!DeleteFileW` at `0x180036e2d`
- `KERNEL32!DeleteFileW` at `0x180036e3a`
- `SETUPAPI!SetupInstallServicesFromInfSectionW` at `0x180036dcb`
- `SETUPAPI!SetupInstallServicesFromInfSectionW` at `0x180036dcb`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x180036db3`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x180036db3`
- `SETUPAPI!SetupCloseInfFile` at `0x180036e18`
- `SETUPAPI!SetupCloseInfFile` at `0x180036e18`
- `SETUPAPI!SetupOpenInfFileW` at `0x180036cfc`
- `SETUPAPI!SetupOpenInfFileW` at `0x180036d55`
- `SETUPAPI!SetupOpenInfFileW` at `0x180036cfc`
- `SETUPAPI!SetupOpenInfFileW` at `0x180036d55`

## string_xrefs

- `0x180036bb4`: `.wsdl,text/xml,.disco,text/xml,.xsd,text/xml,.wbmp,image/vnd.wap.wbmp,.png,image/png,.pnz,image/png,.smd,audio/x-smd,.smz,audio/x-smd,.smx,audio/x-smd,.mmf,application/x-smaf,.application,application/x-ms-application,.manifest,application/x-ms-manifest,.deploy,application/octet-stream,`
- `0x180036bca`: `.asax,1,.ascx,1,.ashx,0,.asmx,0,.aspx,0,.axd,0,.vsdisco,0,.rem,0,.soap,0,.config,1,.cs,1,.csproj,1,.vb,1,.vbproj,1,.webinfo,1,.licx,1,.resx,1,.resources,1,.master,1,.skin,1,.compiled,1,.browser,1,.mdb,1,.jsl,1,.vjsproj,1,.sitemap,1,.msgx,0,.ad,1,.dd,1,.ldd,1,.sd,1,.cd,1,.adprototype,1,.lddprototype,1,.sdm,1,.sdmDocument,1,.ldb,1,.svc,0,.mdf,1,.ldf,1,.java,1,.exclude,1,.refresh,1,.xoml,0,.xamlx,0,.rules,1,.aspq,1,.cshtm,1,.cshtml,1,.vbhtm,1,.vbhtml,1,`
- `0x180036b1f`: `XSP_INSTALL_DIR`
- `0x180036b43`: `XSP_INSTALL_DLL_FULLPATH`
- `0x180036b64`: `XSP_EVENT_DLL_FULLPATH`
- `0x180036b7d`: `XSP_INSTALLED_VER`
- `0x180036c28`: `InstallInfSections`
- `0x180036dfc`: `InstallInfSections`

## pseudocode

```c
__int64 __fastcall InstallInfSections(HINSTANCE hModule, char a2, const unsigned __int16 *a3, int a4)
{
  __int64 v8; // rsi
  unsigned int LastWin32Error; // ebx
  __int64 v10; // r8
  WCHAR *v11; // rcx
  WCHAR v12; // ax
  WCHAR *v13; // rax
  unsigned int v14; // r14d
  int v15; // ecx
  int v17; // [rsp+60h] [rbp-A0h] BYREF
  int v18; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v19; // [rsp+70h] [rbp-90h]
  _QWORD v20[2]; // [rsp+80h] [rbp-80h] BYREF
  int v21; // [rsp+90h] [rbp-70h]
  const wchar_t *v22; // [rsp+98h] [rbp-68h]
  __int64 v23; // [rsp+A0h] [rbp-60h]
  int v24; // [rsp+A8h] [rbp-58h]
  const wchar_t *v25; // [rsp+B0h] [rbp-50h]
  wchar_t *v26; // [rsp+B8h] [rbp-48h]
  int v27; // [rsp+C0h] [rbp-40h]
  const wchar_t *v28; // [rsp+C8h] [rbp-38h]
  wchar_t *v29; // [rsp+D0h] [rbp-30h]
  int v30; // [rsp+D8h] [rbp-28h]
  const wchar_t *v31; // [rsp+E0h] [rbp-20h]
  WCHAR *v32; // [rsp+E8h] [rbp-18h]
  int v33; // [rsp+F0h] [rbp-10h]
  const wchar_t *v34; // [rsp+F8h] [rbp-8h]
  const wchar_t *v35; // [rsp+100h] [rbp+0h]
  int v36; // [rsp+108h] [rbp+8h]
  const wchar_t *v37; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v38; // [rsp+118h] [rbp+18h]
  int v39; // [rsp+120h] [rbp+20h]
  const wchar_t *v40; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v41; // [rsp+130h] [rbp+30h]
  int v42; // [rsp+138h] [rbp+38h]
  const wchar_t *v43; // [rsp+140h] [rbp+40h]
  const wchar_t *v44; // [rsp+148h] [rbp+48h]
  int v45; // [rsp+150h] [rbp+50h]
  const wchar_t *v46; // [rsp+158h] [rbp+58h]
  const wchar_t *v47; // [rsp+160h] [rbp+60h]
  int v48; // [rsp+168h] [rbp+68h]
  WCHAR ExistingFileName[264]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR NewFileName[264]; // [rsp+380h] [rbp+280h] BYREF

  v18 = 10;
  v17 = 0;
  v20[0] = L"AspNet_StateDescription";
  v21 = 0;
  v20[1] = 3221226552LL;
  v27 = 1;
  v22 = L"AspNet_StateDisplayName";
  v30 = 1;
  v23 = 3221226553LL;
  v33 = 1;
  v25 = L"XSP_INSTALL_DIR";
  v36 = 1;
  v26 = &Names::s_wszInstallDirectory;
  v39 = 1;
  v28 = L"XSP_INSTALL_DLL_FULLPATH";
  v42 = 1;
  v29 = &Names::s_wszIsapiFullPath;
  v45 = 1;
  v31 = L"XSP_EVENT_DLL_FULLPATH";
  v32 = &Names::s_wszRcFullPath;
  v34 = L"XSP_INSTALLED_VER";
  v35 = L"4.0.30319.0";
  v37 = L"XSP_DEFAULT_DOC";
  v38 = L"Default.aspx";
  v40 = L"XSP_MIMEMAP";
  v41 = L".wsdl,text/xml,.disco,text/xml,.xsd,text/xml,.wbmp,image/vnd.wap.wbmp,.png,image/png,.pnz,image/png,.smd,audio/x"
         "-smd,.smz,audio/x-smd,.smx,audio/x-smd,.mmf,application/x-smaf,.application,application/x-ms-application,.manif"
         "est,application/x-ms-manifest,.deploy,application/octet-stream,";
  v43 = L"XSP_SUPPORTED_EXTS";
  v44 = L".asax,1,.ascx,1,.ashx,0,.asmx,0,.aspx,0,.axd,0,.vsdisco,0,.rem,0,.soap,0,.config,1,.cs,1,.csproj,1,.vb,1,.vbproj"
         ",1,.webinfo,1,.licx,1,.resx,1,.resources,1,.master,1,.skin,1,.compiled,1,.browser,1,.mdb,1,.jsl,1,.vjsproj,1,.s"
         "itemap,1,.msgx,0,.ad,1,.dd,1,.ldd,1,.sd,1,.cd,1,.adprototype,1,.lddprototype,1,.sdm,1,.sdmDocument,1,.ldb,1,.sv"
         "c,0,.mdf,1,.ldf,1,.java,1,.exclude,1,.refresh,1,.xoml,0,.xamlx,0,.rules,1,.aspq,1,.cshtm,1,.cshtml,1,.vbhtm,1,.vbhtml,1,";
  v46 = L"XSP_ASSEMBLY_VERSION";
  v47 = L"4.0.0.0";
  v48 = 1;
  v19 = v20;
  v24 = 0;
  memset_0(ExistingFileName, 0, 0x208u);
  memset_0(NewFileName, 0, 0x208u);
  v8 = -1;
  CSetupLogging::Log(1, "InstallInfSections", 0, "Executing inf section: ", a3);
  LastWin32Error = CreateInfFile(hModule, ExistingFileName, &v17);
  if ( !LastWin32Error )
  {
    v10 = 260;
    v11 = NewFileName;
    do
    {
      if ( v10 == -2147483386 )
        break;
      v12 = *(v11 - 264);
      if ( !v12 )
        break;
      *v11++ = v12;
      --v10;
    }
    while ( v10 );
    v13 = v11 - 1;
    if ( v10 )
      v13 = v11;
    *v13 = 0;
    StringCchCatW(NewFileName, 0x104u, L"-tmp");
    CopyFileW(ExistingFileName, NewFileName, 0);
    v14 = CalculateFileSize(ExistingFileName);
    LastWin32Error = WriteCallerStrings(ExistingFileName, hModule, (struct _StrTable *)&v18);
    if ( !LastWin32Error )
    {
      v8 = (__int64)SetupOpenInfFileW(ExistingFileName, 0, 2u, 0);
      if ( v8 != -1 )
        goto LABEL_14;
      if ( v14 <= CalculateFileSize(ExistingFileName) )
        goto LABEL_13;
      LastWin32Error = WriteCallerStrings(NewFileName, hModule, (struct _StrTable *)&v18);
      if ( LastWin32Error )
        goto LABEL_19;
      Sleep(0x3E8u);
      v8 = (__int64)SetupOpenInfFileW(NewFileName, 0, 2u, 0);
      if ( v8 == -1 )
      {
LABEL_13:
        LastWin32Error = GetLastWin32Error();
      }
      else
      {
LABEL_14:
        while ( *a3 )
        {
          if ( !SetupInstallFromInfSectionW(0, (HINF)v8, a3, 0x7FFu, 0, 0, 0, Locks_Cleanup, 0, 0, 0)
            || a2 && !SetupInstallServicesFromInfSectionW((HINF)v8, a3, 0) )
          {
            goto LABEL_13;
          }
          a3 += lstrlenW(a3) + 1;
        }
      }
    }
  }
LABEL_19:
  v15 = LastWin32Error;
  if ( a4 )
    v15 = 0;
  CSetupLogging::Log(v15, "InstallInfSections", 0, "Executing inf section: ", a3);
  if ( v8 != -1 )
    SetupCloseInfFile((HINF)v8);
  if ( v17 && !LastWin32Error )
  {
    DeleteFileW(ExistingFileName);
    DeleteFileW(NewFileName);
  }
  return LastWin32Error;
}

```

## disassembly

```asm
0x180036aa0  mov     [rsp-8+arg_8], rbx
0x180036aa5  push    rbp
0x180036aa6  push    rsi
0x180036aa7  push    rdi
0x180036aa8  push    r12
0x180036aaa  push    r13
0x180036aac  push    r14
0x180036aae  push    r15
0x180036ab0  lea     rbp, [rsp-4A0h]
0x180036ab8  sub     rsp, 5A0h
0x180036abf  mov     rax, cs:__security_cookie
0x180036ac6  xor     rax, rsp
0x180036ac9  mov     [rbp+4D0h+var_40], rax
0x180036ad0  xor     r14d, r14d
0x180036ad3  mov     [rsp+5D0h+var_568], 0Ah
0x180036adb  lea     rax, aAspnetStatedes; "AspNet_StateDescription"
0x180036ae2  mov     [rsp+5D0h+var_570], r14d
0x180036ae7  mov     [rbp+4D0h+var_550], rax
0x180036aeb  mov     r15, rcx
0x180036aee  mov     eax, 0C0000438h
0x180036af3  mov     [rbp+4D0h+var_540], r14d
0x180036af7  mov     [rbp+4D0h+var_548], rax
0x180036afb  lea     ecx, [r14+1]
0x180036aff  lea     rax, aAspnetStatedis; "AspNet_StateDisplayName"
0x180036b06  mov     [rbp+4D0h+var_510], ecx
0x180036b09  mov     [rbp+4D0h+var_538], rax
0x180036b0d  mov     rdi, r8
0x180036b10  mov     eax, 0C0000439h
0x180036b15  mov     [rbp+4D0h+var_4F8], ecx
0x180036b18  mov     [rbp+4D0h+var_530], rax
0x180036b1c  mov     r12b, dl
0x180036b1f  lea     rax, aXspInstallDir; "XSP_INSTALL_DIR"
0x180036b26  mov     [rbp+4D0h+var_4E0], ecx
0x180036b29  mov     [rbp+4D0h+var_520], rax
0x180036b2d  mov     ebx, 208h
0x180036b32  lea     rax, ?s_wszInstallDirectory@Names@@0PAGA; ushort near * Names::s_wszInstallDirectory
0x180036b39  mov     [rbp+4D0h+var_4C8], ecx
0x180036b3c  mov     [rbp+4D0h+var_518], rax
0x180036b40  mov     r8d, ebx; Size
0x180036b43  lea     rax, aXspInstallDllF; "XSP_INSTALL_DLL_FULLPATH"
0x180036b4a  mov     [rbp+4D0h+var_4B0], ecx
0x180036b4d  mov     [rbp+4D0h+var_508], rax
0x180036b51  xor     edx, edx; Val
0x180036b53  lea     rax, ?s_wszIsapiFullPath@Names@@0PAGA; ushort near * Names::s_wszIsapiFullPath
0x180036b5a  mov     [rbp+4D0h+var_498], ecx
0x180036b5d  mov     [rbp+4D0h+var_500], rax
0x180036b61  mov     r13d, r9d
0x180036b64  lea     rax, aXspEventDllFul; "XSP_EVENT_DLL_FULLPATH"
0x180036b6b  mov     [rbp+4D0h+var_480], ecx
0x180036b6e  mov     [rbp+4D0h+var_4F0], rax
0x180036b72  lea     rax, ?s_wszRcFullPath@Names@@0PAGA; ushort near * Names::s_wszRcFullPath
0x180036b79  mov     [rbp+4D0h+var_4E8], rax
0x180036b7d  lea     rax, aXspInstalledVe; "XSP_INSTALLED_VER"
0x180036b84  mov     [rbp+4D0h+var_4D8], rax
0x180036b88  lea     rax, a40303190; "4.0.30319.0"
0x180036b8f  mov     [rbp+4D0h+var_4D0], rax
0x180036b93  lea     rax, aXspDefaultDoc; "XSP_DEFAULT_DOC"
0x180036b9a  mov     [rbp+4D0h+var_4C0], rax
0x180036b9e  lea     rax, aDefaultAspx_0; "Default.aspx"
0x180036ba5  mov     [rbp+4D0h+var_4B8], rax
0x180036ba9  lea     rax, aXspMimemap; "XSP_MIMEMAP"
0x180036bb0  mov     [rbp+4D0h+var_4A8], rax
0x180036bb4  lea     rax, aWsdlTextXmlDis; ".wsdl,text/xml,.disco,text/xml,.xsd,tex"...
0x180036bbb  mov     [rbp+4D0h+var_4A0], rax
0x180036bbf  lea     rax, aXspSupportedEx; "XSP_SUPPORTED_EXTS"
0x180036bc6  mov     [rbp+4D0h+var_490], rax
0x180036bca  lea     rax, aAsax1Ascx1Ashx; ".asax,1,.ascx,1,.ashx,0,.asmx,0,.aspx,0"...
0x180036bd1  mov     [rbp+4D0h+var_488], rax
0x180036bd5  lea     rax, aXspAssemblyVer; "XSP_ASSEMBLY_VERSION"
0x180036bdc  mov     [rbp+4D0h+var_478], rax
0x180036be0  lea     rax, a4000; "4.0.0.0"
0x180036be7  mov     [rbp+4D0h+var_470], rax
0x180036beb  lea     rax, [rbp+4D0h+var_550]
0x180036bef  mov     [rbp+4D0h+var_468], ecx
0x180036bf2  lea     rcx, [rbp+4D0h+ExistingFileName]; void *
0x180036bf6  mov     [rsp+5D0h+var_560], rax
0x180036bfb  mov     [rbp+4D0h+var_528], r14d
0x180036bff  call    memset_0
0x180036c04  mov     r8d, ebx; Size
0x180036c07  lea     rcx, [rbp+4D0h+NewFileName]; void *
0x180036c0e  xor     edx, edx; Val
0x180036c10  call    memset_0
0x180036c15  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180036c19  mov     [rsp+5D0h+RelativeKeyRoot], rdi; unsigned __int16 *
0x180036c1e  lea     r9, aExecutingInfSe; "Executing inf section: "
0x180036c25  xor     r8d, r8d; unsigned int
0x180036c28  lea     rdx, aInstallinfsect; "InstallInfSections"
0x180036c2f  lea     ecx, [rsi+2]; int
0x180036c32  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180036c37  lea     r8, [rsp+5D0h+var_570]; int *
0x180036c3c  mov     rcx, r15; hModule
0x180036c3f  lea     rdx, [rbp+4D0h+ExistingFileName]; lpFileName
0x180036c43  call    ?CreateInfFile@@YAJPEAUHINSTANCE__@@PEAGPEAH@Z; CreateInfFile(HINSTANCE__ *,ushort *,int *)
0x180036c48  mov     ebx, eax
0x180036c4a  test    eax, eax
0x180036c4c  jnz     loc_180036DEB
0x180036c52  mov     edx, 104h; unsigned __int64
0x180036c57  lea     r9, [rbp+4D0h+ExistingFileName]
0x180036c5b  lea     rax, [rbp+4D0h+NewFileName]
0x180036c62  mov     r8d, edx
0x180036c65  sub     r9, rax
0x180036c68  lea     rcx, [rbp+4D0h+NewFileName]
0x180036c6f  lea     rax, [r8+7FFFFEFAh]
0x180036c76  test    rax, rax
0x180036c79  jz      short loc_180036C92
0x180036c7b  movzx   eax, word ptr [r9+rcx]
0x180036c80  test    ax, ax
0x180036c83  jz      short loc_180036C92
0x180036c85  mov     [rcx], ax
0x180036c88  add     rcx, 2
0x180036c8c  sub     r8, 1
0x180036c90  jnz     short loc_180036C6F
0x180036c92  test    r8, r8
0x180036c95  lea     rax, [rcx-2]
0x180036c99  lea     r8, aTmp; "-tmp"
0x180036ca0  cmovnz  rax, rcx
0x180036ca4  lea     rcx, [rbp+4D0h+NewFileName]; unsigned __int16 *
0x180036cab  mov     [rax], r14w
0x180036caf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180036cb4  xor     r8d, r8d; bFailIfExists
0x180036cb7  lea     rdx, [rbp+4D0h+NewFileName]; lpNewFileName
0x180036cbe  lea     rcx, [rbp+4D0h+ExistingFileName]; lpExistingFileName
0x180036cc2  call    cs:__imp_CopyFileW
0x180036cc8  lea     rcx, [rbp+4D0h+ExistingFileName]; unsigned __int16 *
0x180036ccc  call    ?CalculateFileSize@@YAKPEBG@Z; CalculateFileSize(ushort const *)
0x180036cd1  lea     r8, [rsp+5D0h+var_568]; struct _StrTable *
0x180036cd6  mov     rdx, r15; HINSTANCE
0x180036cd9  lea     rcx, [rbp+4D0h+ExistingFileName]; unsigned __int16 *
0x180036cdd  mov     r14d, eax
0x180036ce0  call    ?WriteCallerStrings@@YAJPEAGPEAUHINSTANCE__@@PEAU_StrTable@@@Z; WriteCallerStrings(ushort *,HINSTANCE__ *,_StrTable *)
0x180036ce5  mov     ebx, eax
0x180036ce7  test    eax, eax
0x180036ce9  jnz     loc_180036DE8
0x180036cef  xor     r9d, r9d; ErrorLine
0x180036cf2  lea     r8d, [rax+2]; InfStyle
0x180036cf6  xor     edx, edx; InfClass
0x180036cf8  lea     rcx, [rbp+4D0h+ExistingFileName]; FileName
0x180036cfc  call    cs:__imp_SetupOpenInfFileW
0x180036d02  mov     rsi, rax
0x180036d05  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036d09  jnz     short loc_180036D72
0x180036d0b  lea     rcx, [rbp+4D0h+ExistingFileName]; unsigned __int16 *
0x180036d0f  call    ?CalculateFileSize@@YAKPEBG@Z; CalculateFileSize(ushort const *)
0x180036d14  cmp     r14d, eax
0x180036d17  jbe     short loc_180036D66
0x180036d19  lea     r8, [rsp+5D0h+var_568]; struct _StrTable *
0x180036d1e  mov     rdx, r15; HINSTANCE
0x180036d21  lea     rcx, [rbp+4D0h+NewFileName]; unsigned __int16 *
0x180036d28  call    ?WriteCallerStrings@@YAJPEAGPEAUHINSTANCE__@@PEAU_StrTable@@@Z; WriteCallerStrings(ushort *,HINSTANCE__ *,_StrTable *)
0x180036d2d  xor     r14d, r14d
0x180036d30  mov     ebx, eax
0x180036d32  test    eax, eax
0x180036d34  jnz     loc_180036DEB
0x180036d3a  mov     ecx, 3E8h; dwMilliseconds
0x180036d3f  call    cs:__imp_Sleep
0x180036d45  xor     r9d, r9d; ErrorLine
0x180036d48  lea     r8d, [rsi+3]; InfStyle
0x180036d4c  xor     edx, edx; InfClass
0x180036d4e  lea     rcx, [rbp+4D0h+NewFileName]; FileName
0x180036d55  call    cs:__imp_SetupOpenInfFileW
0x180036d5b  mov     rsi, rax
0x180036d5e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036d62  jnz     short loc_180036D75
0x180036d64  jmp     short loc_180036D69
0x180036d66  xor     r14d, r14d
0x180036d69  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180036d6e  mov     ebx, eax
0x180036d70  jmp     short loc_180036DEB
0x180036d72  xor     r14d, r14d
0x180036d75  cmp     [rdi], r14w
0x180036d79  jz      short loc_180036DEB
0x180036d7b  mov     [rsp+5D0h+DeviceInfoData], r14; DeviceInfoData
0x180036d80  lea     rax, Locks_Cleanup
0x180036d87  mov     [rsp+5D0h+DeviceInfoSet], r14; DeviceInfoSet
0x180036d8c  mov     r9d, 7FFh; Flags
0x180036d92  mov     [rsp+5D0h+Context], r14; Context
0x180036d97  mov     r8, rdi; SectionName
0x180036d9a  mov     [rsp+5D0h+MsgHandler], rax; MsgHandler
0x180036d9f  mov     rdx, rsi; InfHandle
0x180036da2  mov     [rsp+5D0h+CopyFlags], r14d; CopyFlags
0x180036da7  xor     ecx, ecx; Owner
0x180036da9  mov     [rsp+5D0h+SourceRootPath], r14; SourceRootPath
0x180036dae  mov     [rsp+5D0h+RelativeKeyRoot], r14; RelativeKeyRoot
0x180036db3  call    cs:__imp_SetupInstallFromInfSectionW
0x180036db9  test    eax, eax
0x180036dbb  jz      short loc_180036D69
0x180036dbd  test    r12b, r12b
0x180036dc0  jz      short loc_180036DD5
0x180036dc2  xor     r8d, r8d; Flags
0x180036dc5  mov     rdx, rdi; SectionName
0x180036dc8  mov     rcx, rsi; InfHandle
0x180036dcb  call    cs:__imp_SetupInstallServicesFromInfSectionW
0x180036dd1  test    eax, eax
0x180036dd3  jz      short loc_180036D69
0x180036dd5  mov     rcx, rdi; lpString
0x180036dd8  call    cs:__imp_lstrlenW
0x180036dde  inc     eax
0x180036de0  cdqe
0x180036de2  lea     rdi, [rdi+rax*2]
0x180036de6  jmp     short loc_180036D75
0x180036de8  xor     r14d, r14d
0x180036deb  mov     ecx, ebx
0x180036ded  mov     [rsp+5D0h+RelativeKeyRoot], rdi; unsigned __int16 *
0x180036df2  test    r13d, r13d
0x180036df5  lea     r9, aExecutingInfSe; "Executing inf section: "
0x180036dfc  lea     rdx, aInstallinfsect; "InstallInfSections"
0x180036e03  cmovnz  ecx, r14d; int
0x180036e07  xor     r8d, r8d; unsigned int
0x180036e0a  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180036e0f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180036e13  jz      short loc_180036E1E
0x180036e15  mov     rcx, rsi; InfHandle
0x180036e18  call    cs:__imp_SetupCloseInfFile
0x180036e1e  cmp     [rsp+5D0h+var_570], r14d
0x180036e23  jz      short loc_180036E40
0x180036e25  test    ebx, ebx
0x180036e27  jnz     short loc_180036E40
0x180036e29  lea     rcx, [rbp+4D0h+ExistingFileName]; lpFileName
0x180036e2d  call    cs:__imp_DeleteFileW
0x180036e33  lea     rcx, [rbp+4D0h+NewFileName]; lpFileName
0x180036e3a  call    cs:__imp_DeleteFileW
0x180036e40  mov     eax, ebx
0x180036e42  mov     rcx, [rbp+4D0h+var_40]
0x180036e49  xor     rcx, rsp; StackCookie
0x180036e4c  call    __security_check_cookie
0x180036e51  mov     rbx, [rsp+5D0h+arg_8]
0x180036e59  add     rsp, 5A0h
0x180036e60  pop     r15
0x180036e62  pop     r14
0x180036e64  pop     r13
0x180036e66  pop     r12
0x180036e68  pop     rdi
0x180036e69  pop     rsi
0x180036e6a  pop     rbp
0x180036e6b  retn
```
