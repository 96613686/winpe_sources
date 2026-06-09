# CModelDownloadComponent::GetLatestVersionForThisEngine(ushort const *,ushort *)

- ea: `0x18000f310`
- end: `0x18000f674`
- name: `?GetLatestVersionForThisEngine@CModelDownloadComponent@@SAJPEBGPEAG@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000ebf0`
- `0x18000f96c`

## callees

- `0x18000f310`
- `0x18000f680`
- `0x18000f934`
- `0x180013ec0`
- `0x18003d0ec`
- `0x180079e30`
- `0x18007aae4`
- `0x18007aca8`
- `0x180100f44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18000f484`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18000f484`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x18000f4e2`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x18000f5cc`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x18000f5dd`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x18000f4e2`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x18000f5cc`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x18000f5dd`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000f498`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000f51f`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000f548`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000f580`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000f62b`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000f498`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000f51f`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000f548`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000f580`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000f62b`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18000f4bd`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18000f4bd`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000f570`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000f570`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f533`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3a7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f39d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f39d`

## string_xrefs

- `0x18000f396`: `%ProgramData%\Microsoft\Speech_OneCore`
- `0x18000f3bf`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1078)`
- `0x18000f3cb`: `CModelDownloadComponent::GetModelFilesRootPathExists`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::GetLatestVersionForThisEngine(
        const unsigned __int16 *a1,
        unsigned __int16 *a2)
{
  signed int ModelNameComponentsFromTokensFilename; // r14d
  signed int LastError; // eax
  wchar_t *v4; // rax
  unsigned __int16 *v6; // [rsp+20h] [rbp-E0h]
  FILE *Stream; // [rsp+40h] [rbp-C0h] BYREF
  struct _stat64i32 Stat; // [rsp+70h] [rbp-90h] BYREF
  struct _stat64i32 v9; // [rsp+A0h] [rbp-60h] BYREF
  struct _stat64i32 v10; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t Buffer[264]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v12; // [rsp+310h] [rbp+210h]
  wchar_t FileName[264]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v14[264]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v15[264]; // [rsp+740h] [rbp+640h] BYREF
  unsigned __int16 v16[264]; // [rsp+950h] [rbp+850h] BYREF
  WCHAR Dst[264]; // [rsp+B60h] [rbp+A60h] BYREF
  unsigned __int16 v18[264]; // [rsp+D70h] [rbp+C70h] BYREF

  ModelNameComponentsFromTokensFilename = CModelDownloadComponent::GetModelNameComponentsFromTokensFilename(
                                            &FullPath,
                                            v18,
                                            v16,
                                            v15,
                                            v14);
  if ( ModelNameComponentsFromTokensFilename < 0 )
  {
    SPTelemetry::ModelTokenLoad(&::FileName);
LABEL_33:
    swprintf_s(&::FileName, 0x104u, L"%s", &FullPath);
    return (unsigned int)ModelNameComponentsFromTokensFilename;
  }
  if ( !ExpandEnvironmentStringsW(L"%ProgramData%\\Microsoft\\Speech_OneCore", Dst, 0x104u) )
  {
    LastError = GetLastError();
    ModelNameComponentsFromTokensFilename = LastError;
    if ( LastError > 0 )
      ModelNameComponentsFromTokensFilename = (unsigned __int16)LastError | 0x80070000;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::GetModelFilesRootPathExists",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1078)",
      ModelNameComponentsFromTokensFilename);
    if ( ModelNameComponentsFromTokensFilename < 0 )
    {
LABEL_32:
      SPTelemetry::ModelTokenLoad(&::FileName);
      goto LABEL_33;
    }
  }
  swprintf_s<261>(FileName, L"%s\\%s\\%s-%s\\%s\\%s", Dst, v16, L"SV10", v15, v14, L"naspmodelcurrentversion.bin");
  memset_0(Buffer, 0, 0x218u);
  if ( !FileName[0] )
  {
LABEL_31:
    ModelNameComponentsFromTokensFilename = -2147024809;
    goto LABEL_32;
  }
  Stream = 0;
  if ( _wfopen_s(&Stream, FileName, L"rb") || fread(Buffer, 0x218u, 1u, Stream) != 1 )
  {
    if ( Stream )
      fclose(Stream);
    ModelNameComponentsFromTokensFilename = -2147024891;
    goto LABEL_32;
  }
  memset(&Stat, 0, sizeof(Stat));
  if ( _wstat64i32(Buffer, &Stat) || Stat.st_mtime != v12 )
  {
    if ( Stream )
      fclose(Stream);
    goto LABEL_31;
  }
  ModelNameComponentsFromTokensFilename = CModelDownloadComponent::ValidateModelFilesList(Buffer);
  if ( ModelNameComponentsFromTokensFilename < 0 )
  {
    if ( Stream )
      fclose(Stream);
    goto LABEL_32;
  }
  v4 = wcsrchr(Buffer, 0x5Cu);
  if ( !v4 )
  {
    if ( Stream )
      fclose(Stream);
    ModelNameComponentsFromTokensFilename = -2146697214;
    goto LABEL_32;
  }
  _o_wcsncpy_s(&::FileName, 260, Buffer, (int)(v4 - Buffer), v6);
  if ( Stream )
    fclose(Stream);
  swprintf_s(&::FileName, 0x104u, L"%s\\%s", &::FileName, v18);
  memset(&v9, 0, sizeof(v9));
  memset(&v10, 0, sizeof(v10));
  if ( _wstat64i32(&::FileName, &v10) || _wstat64i32(&FullPath, &v9) || v10.st_mtime <= v9.st_mtime )
  {
    SPTelemetry::ModelTokenLoad(&::FileName);
    swprintf_s(&::FileName, 0x104u, L"%s", &FullPath);
    return 2147942487LL;
  }
  else
  {
    SPTelemetry::ModelTokenLoad(&::FileName);
    return 0;
  }
}

```

## disassembly

```asm
0x18000f310  push    rbp
0x18000f312  push    rbx
0x18000f313  push    rsi
0x18000f314  push    rdi
0x18000f315  push    r14
0x18000f317  lea     rbp, [rsp-0E90h]
0x18000f31f  sub     rsp, 0F90h
0x18000f326  mov     rax, cs:__security_cookie
0x18000f32d  xor     rax, rsp
0x18000f330  mov     [rbp+0EB0h+var_30], rax
0x18000f337  lea     rax, [rbp+0EB0h+var_A80]
0x18000f33e  lea     rdi, FullPath
0x18000f345  mov     [rsp+0FB0h+var_F90], rax; unsigned __int16 *
0x18000f34a  mov     rcx, rdi; FullPath
0x18000f34d  lea     r9, [rbp+0EB0h+var_870]; unsigned __int16 *
0x18000f354  lea     r8, [rbp+0EB0h+var_660]; unsigned __int16 *
0x18000f35b  lea     rdx, [rbp+0EB0h+var_240]; unsigned __int16 *
0x18000f362  lea     rsi, FileName
0x18000f369  call    ?GetModelNameComponentsFromTokensFilename@CModelDownloadComponent@@CAJPEBGPEAG111@Z; CModelDownloadComponent::GetModelNameComponentsFromTokensFilename(ushort const *,ushort *,ushort *,ushort *,ushort *)
0x18000f36e  mov     r14d, eax
0x18000f371  test    eax, eax
0x18000f373  jns     short loc_18000F387
0x18000f375  mov     rcx, rsi; unsigned __int16 *
0x18000f378  call    ?ModelTokenLoad@SPTelemetry@@SAXPEBG@Z; SPTelemetry::ModelTokenLoad(ushort const *)
0x18000f37d  mov     edx, 104h
0x18000f382  jmp     loc_18000F642
0x18000f387  mov     ebx, 104h
0x18000f38c  lea     rdx, [rbp+0EB0h+Dst]; lpDst
0x18000f393  mov     r8d, ebx; nSize
0x18000f396  lea     rcx, Src; "%ProgramData%\\Microsoft\\Speech_OneCor"...
0x18000f39d  call    cs:__imp_ExpandEnvironmentStringsW
0x18000f3a3  test    eax, eax
0x18000f3a5  jnz     short loc_18000F3F8
0x18000f3a7  call    cs:__imp_GetLastError
0x18000f3ad  mov     r14d, eax
0x18000f3b0  test    eax, eax
0x18000f3b2  jle     short loc_18000F3BF
0x18000f3b4  movzx   r14d, ax
0x18000f3b8  or      r14d, 80070000h
0x18000f3bf  lea     rax, aOnecoreuapEndu_14; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18000f3c6  mov     dword ptr [rsp+0FB0h+var_F88], r14d
0x18000f3cb  lea     r9, aCmodeldownload_0; "CModelDownloadComponent::GetModelFilesR"...
0x18000f3d2  mov     [rsp+0FB0h+var_F90], rax
0x18000f3d7  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x18000f3de  mov     ecx, 2; int
0x18000f3e3  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x18000f3ea  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18000f3ef  test    r14d, r14d
0x18000f3f2  js      loc_18000F637
0x18000f3f8  lea     rax, aNaspmodelcurre; "naspmodelcurrentversion.bin"
0x18000f3ff  mov     [rsp+0FB0h+var_F78], rax
0x18000f404  lea     r9, [rbp+0EB0h+var_660]
0x18000f40b  lea     rax, [rbp+0EB0h+var_A80]
0x18000f412  mov     [rsp+0FB0h+var_F80], rax
0x18000f417  lea     r8, [rbp+0EB0h+Dst]
0x18000f41e  lea     rax, [rbp+0EB0h+var_870]
0x18000f425  mov     [rsp+0FB0h+var_F88], rax
0x18000f42a  lea     rdx, aSSSSSS; "%s\\%s\\%s-%s\\%s\\%s"
0x18000f431  lea     rax, aSv10; "SV10"
0x18000f438  lea     rcx, [rbp+0EB0h+FileName]
0x18000f43f  mov     [rsp+0FB0h+var_F90], rax
0x18000f444  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x18000f449  xor     edx, edx; Val
0x18000f44b  lea     rcx, [rbp+0EB0h+Buffer]; void *
0x18000f44f  mov     r8d, 218h; Size
0x18000f455  call    memset_0
0x18000f45a  cmp     [rbp+0EB0h+FileName], 0
0x18000f462  jz      loc_18000F631
0x18000f468  lea     r8, aRb; "rb"
0x18000f46f  mov     [rsp+0FB0h+Stream], 0
0x18000f478  lea     rdx, [rbp+0EB0h+FileName]; FileName
0x18000f47f  lea     rcx, [rsp+0FB0h+Stream]; Stream
0x18000f484  call    cs:__imp__wfopen_s
0x18000f48a  test    eax, eax
0x18000f48c  jz      short loc_18000F4A9
0x18000f48e  mov     rcx, [rsp+0FB0h+Stream]; Stream
0x18000f493  test    rcx, rcx
0x18000f496  jz      short loc_18000F49E
0x18000f498  call    cs:__imp_fclose
0x18000f49e  mov     r14d, 80070005h
0x18000f4a4  jmp     loc_18000F637
0x18000f4a9  mov     r9, [rsp+0FB0h+Stream]; Stream
0x18000f4ae  lea     rcx, [rbp+0EB0h+Buffer]; Buffer
0x18000f4b2  mov     edx, 218h; ElementSize
0x18000f4b7  mov     r8d, 1; ElementCount
0x18000f4bd  call    cs:__imp_fread
0x18000f4c3  cmp     rax, 1
0x18000f4c7  jnz     short loc_18000F48E
0x18000f4c9  xorps   xmm0, xmm0
0x18000f4cc  lea     rdx, [rsp+0FB0h+Stat]; Stat
0x18000f4d1  lea     rcx, [rbp+0EB0h+Buffer]; FileName
0x18000f4d5  movups  xmmword ptr [rsp+0FB0h+Stat.st_dev], xmm0
0x18000f4da  movups  xmmword ptr [rbp+0EB0h+Stat.st_rdev], xmm0
0x18000f4de  movups  xmmword ptr [rbp+0EB0h+Stat.st_mtime], xmm0
0x18000f4e2  call    cs:__imp__wstat64i32
0x18000f4e8  test    eax, eax
0x18000f4ea  jnz     loc_18000F621
0x18000f4f0  mov     rax, [rbp+0EB0h+var_CA0]
0x18000f4f7  cmp     [rbp+0EB0h+Stat.st_mtime], rax
0x18000f4fb  jnz     loc_18000F621
0x18000f501  lea     rcx, [rbp+0EB0h+Buffer]; FileName
0x18000f505  call    ?ValidateModelFilesList@CModelDownloadComponent@@CAJPEBG@Z; CModelDownloadComponent::ValidateModelFilesList(ushort const *)
0x18000f50a  mov     r14d, eax
0x18000f50d  test    eax, eax
0x18000f50f  jns     short loc_18000F52A
0x18000f511  mov     rcx, [rsp+0FB0h+Stream]; Stream
0x18000f516  test    rcx, rcx
0x18000f519  jz      loc_18000F637
0x18000f51f  call    cs:__imp_fclose
0x18000f525  jmp     loc_18000F637
0x18000f52a  mov     edx, 5Ch ; '\'; Ch
0x18000f52f  lea     rcx, [rbp+0EB0h+Buffer]; Str
0x18000f533  call    cs:__imp_wcsrchr
0x18000f539  test    rax, rax
0x18000f53c  jnz     short loc_18000F559
0x18000f53e  mov     rcx, [rsp+0FB0h+Stream]; Stream
0x18000f543  test    rcx, rcx
0x18000f546  jz      short loc_18000F54E
0x18000f548  call    cs:__imp_fclose
0x18000f54e  mov     r14d, 800C0002h
0x18000f554  jmp     loc_18000F637
0x18000f559  lea     rcx, [rbp+0EB0h+Buffer]
0x18000f55d  mov     rdx, rbx
0x18000f560  sub     rax, rcx
0x18000f563  lea     r8, [rbp+0EB0h+Buffer]
0x18000f567  sar     rax, 1
0x18000f56a  mov     rcx, rsi
0x18000f56d  movsxd  r9, eax
0x18000f570  call    cs:__imp__o_wcsncpy_s
0x18000f576  mov     rcx, [rsp+0FB0h+Stream]; Stream
0x18000f57b  test    rcx, rcx
0x18000f57e  jz      short loc_18000F586
0x18000f580  call    cs:__imp_fclose
0x18000f586  lea     rax, [rbp+0EB0h+var_240]
0x18000f58d  mov     r9, rsi
0x18000f590  lea     r8, aSS; "%s\\%s"
0x18000f597  mov     [rsp+0FB0h+var_F90], rax
0x18000f59c  mov     rdx, rbx; BufferCount
0x18000f59f  mov     rcx, rsi; Buffer
0x18000f5a2  call    swprintf_s
0x18000f5a7  xorps   xmm0, xmm0
0x18000f5aa  lea     rdx, [rbp+0EB0h+var_EE0]; Stat
0x18000f5ae  xorps   xmm1, xmm1
0x18000f5b1  mov     rcx, rsi; FileName
0x18000f5b4  movups  xmmword ptr [rbp+0EB0h+var_F10.st_dev], xmm0
0x18000f5b8  movups  xmmword ptr [rbp+0EB0h+var_F10.st_rdev], xmm0
0x18000f5bc  movups  xmmword ptr [rbp+0EB0h+var_F10.st_mtime], xmm0
0x18000f5c0  movups  xmmword ptr [rbp+0EB0h+var_EE0.st_dev], xmm1
0x18000f5c4  movups  xmmword ptr [rbp+0EB0h+var_EE0.st_rdev], xmm1
0x18000f5c8  movups  xmmword ptr [rbp+0EB0h+var_EE0.st_mtime], xmm1
0x18000f5cc  call    cs:__imp__wstat64i32
0x18000f5d2  test    eax, eax
0x18000f5d4  jnz     short loc_18000F5FD
0x18000f5d6  lea     rdx, [rbp+0EB0h+var_F10]; Stat
0x18000f5da  mov     rcx, rdi; FileName
0x18000f5dd  call    cs:__imp__wstat64i32
0x18000f5e3  test    eax, eax
0x18000f5e5  jnz     short loc_18000F5FD
0x18000f5e7  mov     rax, [rbp+0EB0h+var_F10.st_mtime]
0x18000f5eb  cmp     [rbp+0EB0h+var_EE0.st_mtime], rax
0x18000f5ef  jle     short loc_18000F5FD
0x18000f5f1  mov     rcx, rsi; unsigned __int16 *
0x18000f5f4  call    ?ModelTokenLoad@SPTelemetry@@SAXPEBG@Z; SPTelemetry::ModelTokenLoad(ushort const *)
0x18000f5f9  xor     eax, eax
0x18000f5fb  jmp     short loc_18000F657
0x18000f5fd  mov     rcx, rsi; unsigned __int16 *
0x18000f600  call    ?ModelTokenLoad@SPTelemetry@@SAXPEBG@Z; SPTelemetry::ModelTokenLoad(ushort const *)
0x18000f605  lea     r8, aS_4; "%s"
0x18000f60c  mov     r9, rdi
0x18000f60f  mov     rdx, rbx; BufferCount
0x18000f612  mov     rcx, rsi; Buffer
0x18000f615  call    swprintf_s
0x18000f61a  mov     eax, 80070057h
0x18000f61f  jmp     short loc_18000F657
0x18000f621  mov     rcx, [rsp+0FB0h+Stream]; Stream
0x18000f626  test    rcx, rcx
0x18000f629  jz      short loc_18000F631
0x18000f62b  call    cs:__imp_fclose
0x18000f631  mov     r14d, 80070057h
0x18000f637  mov     rcx, rsi; unsigned __int16 *
0x18000f63a  call    ?ModelTokenLoad@SPTelemetry@@SAXPEBG@Z; SPTelemetry::ModelTokenLoad(ushort const *)
0x18000f63f  mov     rdx, rbx; BufferCount
0x18000f642  mov     r9, rdi
0x18000f645  lea     r8, aS_4; "%s"
0x18000f64c  mov     rcx, rsi; Buffer
0x18000f64f  call    swprintf_s
0x18000f654  mov     eax, r14d
0x18000f657  mov     rcx, [rbp+0EB0h+var_30]
0x18000f65e  xor     rcx, rsp; StackCookie
0x18000f661  call    __security_check_cookie
0x18000f666  add     rsp, 0F90h
0x18000f66d  pop     r14
0x18000f66f  pop     rdi
0x18000f670  pop     rsi
0x18000f671  pop     rbx
0x18000f672  pop     rbp
0x18000f673  retn
```
