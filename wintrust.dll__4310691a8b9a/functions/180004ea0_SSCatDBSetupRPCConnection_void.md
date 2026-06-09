# _SSCatDBSetupRPCConnection(void * *)

- ea: `0x180004ea0`
- end: `0x180005416`
- name: `?_SSCatDBSetupRPCConnection@@YAKPEAPEAX@Z`
- size: `1398`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `6`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800018dc`
- `0x180004d30`
- `0x180025574`
- `0x180047a4c`
- `0x180047b2c`
- `0x180047c20`

## callees

- `0x180004ea0`
- `0x180005420`
- `0x180005920`
- `0x180005d00`
- `0x1800064a8`
- `0x180028398`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000538d`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000538d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800052a2`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800052a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000528f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000528f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800052c1`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000537f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800052c1`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000537f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800052f3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800052f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000532d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000532d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005114`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005114`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005333`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800053cd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800053cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005235`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005235`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800052fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005310`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800052fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005305`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005305`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005214`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000525e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005214`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000525e`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180005134`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180005134`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatA` at `0x180005155`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatA` at `0x180005155`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatA` at `0x180005195`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatA` at `0x180005195`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800050e8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800050e8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180005017`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180005017`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180005089`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180005089`
- `RPCRT4!RpcBindingFree` at `0x1800050c7`
- `RPCRT4!RpcBindingFree` at `0x1800050c7`
- `RPCRT4!RpcEpResolveBinding` at `0x180004fb5`
- `RPCRT4!RpcEpResolveBinding` at `0x180004fb5`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180004f99`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180004f99`
- `RPCRT4!RpcStringFreeW` at `0x1800050d9`
- `RPCRT4!RpcStringFreeW` at `0x1800050d9`
- `RPCRT4!RpcStringBindingComposeW` at `0x180004f7f`
- `RPCRT4!RpcStringBindingComposeW` at `0x180004f7f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180005053`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180005053`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180004f14`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180004f14`

## string_xrefs

- `0x18000520d`: `%SystemRoot%\System32\CatRoot2\dberr.txt`
- `0x18000524e`: `%SystemRoot%\System32\CatRoot2\dberr.txt`

## pseudocode

```c
__int64 __fastcall _SSCatDBSetupRPCConnection(void **a1)
{
  RPC_STATUS v2; // eax
  unsigned __int16 *v3; // rcx
  unsigned int v4; // ebx
  unsigned __int16 *v5; // rcx
  unsigned __int16 *v6; // rcx
  unsigned int v7; // r8d
  DWORD LastError; // eax
  signed int v10; // esi
  int TimeFormatA; // eax
  const char *v12; // r8
  DWORD v13; // r14d
  WCHAR *v14; // rax
  WCHAR *v15; // r15
  __int64 v16; // rbx
  __int64 v17; // rdi
  HANDLE FileW; // rax
  DWORD v19; // eax
  unsigned int v20; // ecx
  int v21; // eax
  int Options; // [rsp+20h] [rbp-E0h]
  int Optionsa; // [rsp+20h] [rbp-E0h]
  int Optionsb; // [rsp+20h] [rbp-E0h]
  CHAR *Optionsc; // [rsp+20h] [rbp-E0h]
  int StringBinding; // [rsp+28h] [rbp-D8h]
  int StringBindinga; // [rsp+28h] [rbp-D8h]
  int StringBindingb; // [rsp+28h] [rbp-D8h]
  RPC_WSTR *StringBindingc; // [rsp+28h] [rbp-D8h]
  int nSubAuthority4; // [rsp+30h] [rbp-D0h]
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid; // [rsp+68h] [rbp-98h] BYREF
  RPC_WSTR String; // [rsp+70h] [rbp-90h] BYREF
  _SID_NAME_USE peUse; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchReferencedDomainName; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD cchName; // [rsp+80h] [rbp-80h] BYREF
  PSID pSid; // [rsp+88h] [rbp-78h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp-70h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+98h] [rbp-68h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR Name[64]; // [rsp+C0h] [rbp-40h] BYREF
  CHAR TimeStr[256]; // [rsp+140h] [rbp+40h] BYREF
  CHAR Buffer[512]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR ReferencedDomainName[256]; // [rsp+440h] [rbp+340h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *a1 = 0;
  String = 0;
  Binding = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  SecurityQOS = 0;
  cchName = 64;
  cchReferencedDomainName = 256;
  peUse = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(L"S-1-5-80-242729624-280608522-2219052887-3187409060-2225943459", &Sid) )
  {
    _SSCatSetCryptSvcSidDaclAceOnSystemSubDir(Sid, L"catroot");
    _SSCatSetCryptSvcSidDaclAceOnSystemSubDir(Sid, L"catroot2");
    if ( Sid )
      LocalFree(Sid);
  }
  if ( (unsigned int)WaitForCryptService() )
  {
    v2 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"keysvc", 0, &String);
    v4 = v2;
    if ( v2 )
    {
      v7 = 375;
    }
    else
    {
      v2 = RpcBindingFromStringBindingW(String, &Binding);
      v4 = v2;
      if ( v2 )
      {
        v7 = 383;
      }
      else
      {
        v2 = RpcEpResolveBinding(Binding, qword_180052040);
        v4 = v2;
        if ( !v2 )
        {
          SecurityQOS.Version = 1;
          SecurityQOS.Capabilities = 1;
          SecurityQOS.IdentityTracking = 1;
          SecurityQOS.ImpersonationType = 3;
          if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
          {
            if ( LookupAccountSidW(0, pSid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
            {
              v2 = RpcBindingSetAuthInfoExW(Binding, Name, 4u, 0xAu, 0, 0, &SecurityQOS);
              v4 = v2;
              if ( !v2 )
              {
                *a1 = Binding;
                Binding = 0;
LABEL_16:
                if ( String )
                  RpcStringFreeW(&String);
                if ( pSid )
                  FreeSid(pSid);
                return v4;
              }
              v7 = 438;
              goto LABEL_13;
            }
            ErrLog_LogError(v6, 3u, 0x1A8u, 0, Optionsb, StringBindingb);
            v4 = 1766;
          }
          else
          {
            ErrLog_LogError(v5, 3u, 0x19Bu, 0, Optionsa, StringBindinga);
            v4 = 1766;
          }
LABEL_14:
          if ( Binding )
            RpcBindingFree(&Binding);
          goto LABEL_16;
        }
        v7 = 391;
      }
    }
LABEL_13:
    ErrLog_LogError(v3, 3u, v7, v2, Options, StringBinding);
    goto LABEL_14;
  }
  LastError = GetLastError();
  SystemTime = 0;
  v10 = LastError;
  if ( !g_fErrLogInitialized )
    ErrLog_Initialize();
  GetLocalTime(&SystemTime);
  TimeFormatA = GetTimeFormatA(0x400u, 0, &SystemTime, 0, TimeStr, 256);
  if ( (unsigned int)(TimeFormatA - 1) <= 0xFF )
  {
    Optionsc = &TimeStr[TimeFormatA];
    *(Optionsc - 1) = 32;
    GetDateFormatA(0x400u, 1u, &SystemTime, 0, Optionsc, 256 - TimeFormatA);
    if ( (v10 & 0x1FFF0000) == 0xE5E0000 )
    {
      v12 = "CatalogDB: %s: %s at line #%u encountered JET error %d\r\n";
      v21 = -(unsigned __int16)v10;
      if ( v10 >= 0 )
        v21 = (unsigned __int16)v10;
      nSubAuthority4 = v21;
    }
    else
    {
      nSubAuthority4 = v10;
      v12 = "CatalogDB: %s: %s at line #%u encountered error 0x%.8lx\r\n";
    }
    LODWORD(StringBindingc) = 352;
    StringCchPrintfA(Buffer, 0x200u, v12, TimeStr, "catdbcli.cpp", StringBindingc, nSubAuthority4);
    LODWORD(Sid) = 0;
    if ( g_fLogErrorsToDebugger )
      OutputDebugStringA(Buffer);
    if ( g_fLogErrorsToFile )
    {
      v13 = ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\CatRoot2\\dberr.txt", 0, 0);
      if ( v13 )
      {
        v14 = (WCHAR *)LocalAlloc(0, 2LL * v13);
        v15 = v14;
        if ( v14 )
        {
          v16 = -1;
          v17 = -1;
          if ( !ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\CatRoot2\\dberr.txt", v14, v13)
            || (FileW = CreateFileW(v15, 0xC0000000, 0, 0, 4u, 0x80u, 0), v17 = (__int64)FileW, FileW == (HANDLE)-1LL)
            || GetFileSize(FileW, 0) >= 0x30D40
            && (SetFilePointer((HANDLE)v17, 0, 0, 0) == -1 || !SetEndOfFile((HANDLE)v17))
            || SetFilePointer((HANDLE)v17, 0, 0, 2u) == -1 )
          {
            LocalFree(v15);
            if ( v17 == -1 )
              goto LABEL_39;
          }
          else
          {
            do
              ++v16;
            while ( Buffer[v16] );
            WriteFile((HANDLE)v17, Buffer, v16, (LPDWORD)&Sid, 0);
            LocalFree(v15);
          }
          CloseHandle((HANDLE)v17);
        }
      }
    }
  }
LABEL_39:
  SetLastError(v10);
  v19 = GetLastError();
  v20 = 1062;
  if ( v19 == 1058 )
    return 1058;
  return v20;
}

```

## disassembly

```asm
0x180004ea0  push    rbp
0x180004ea2  push    rbx
0x180004ea3  push    rdi
0x180004ea4  push    r12
0x180004ea6  lea     rbp, [rsp-558h]
0x180004eae  sub     rsp, 658h
0x180004eb5  mov     rax, cs:__security_cookie
0x180004ebc  xor     rax, rsp
0x180004ebf  mov     [rbp+570h+var_30], rax
0x180004ec6  xor     r12d, r12d
0x180004ec9  mov     word ptr [rbp+570h+pIdentifierAuthority.Value+4], 500h
0x180004ecf  mov     [rcx], r12
0x180004ed2  lea     rdx, [rsp+670h+Sid]; Sid
0x180004ed7  mov     rdi, rcx
0x180004eda  mov     [rsp+670h+String], r12
0x180004edf  xorps   xmm0, xmm0
0x180004ee2  mov     [rsp+670h+Binding], r12
0x180004ee7  mov     ebx, 100h
0x180004eec  mov     dword ptr [rbp+570h+pIdentifierAuthority.Value], r12d
0x180004ef0  lea     rcx, StringSid; "S-1-5-80-242729624-280608522-2219052887"...
0x180004ef7  mov     [rbp+570h+var_5E8], r12
0x180004efb  movups  xmmword ptr [rbp+570h+SecurityQOS.Version], xmm0
0x180004eff  mov     [rbp+570h+cchName], 40h ; '@'
0x180004f06  mov     [rsp+670h+cchReferencedDomainName], ebx
0x180004f0a  mov     [rsp+670h+peUse], r12d
0x180004f0f  mov     [rsp+670h+Sid], r12
0x180004f14  call    cs:__imp_ConvertStringSidToSidW
0x180004f1a  test    eax, eax
0x180004f1c  jz      short loc_180004F50
0x180004f1e  mov     rcx, [rsp+670h+Sid]; void *
0x180004f23  lea     rdx, aCatroot; "catroot"
0x180004f2a  call    ?_SSCatSetCryptSvcSidDaclAceOnSystemSubDir@@YAXPEAXPEBG@Z; _SSCatSetCryptSvcSidDaclAceOnSystemSubDir(void *,ushort const *)
0x180004f2f  mov     rcx, [rsp+670h+Sid]; void *
0x180004f34  lea     rdx, aCatroot2; "catroot2"
0x180004f3b  call    ?_SSCatSetCryptSvcSidDaclAceOnSystemSubDir@@YAXPEAXPEBG@Z; _SSCatSetCryptSvcSidDaclAceOnSystemSubDir(void *,ushort const *)
0x180004f40  mov     rcx, [rsp+670h+Sid]; hMem
0x180004f45  test    rcx, rcx
0x180004f48  jz      short loc_180004F50
0x180004f4a  call    cs:__imp_LocalFree
0x180004f50  call    WaitForCryptService
0x180004f55  test    eax, eax
0x180004f57  jz      loc_18000510C
0x180004f5d  lea     rax, [rsp+670h+String]
0x180004f62  xor     r8d, r8d; NetworkAddr
0x180004f65  mov     [rsp+670h+StringBinding], rax; int
0x180004f6a  lea     r9, Endpoint; "keysvc"
0x180004f71  lea     rdx, ProtSeq; "ncalrpc"
0x180004f78  mov     [rsp+670h+Options], r12; int
0x180004f7d  xor     ecx, ecx; ObjUuid
0x180004f7f  call    cs:__imp_RpcStringBindingComposeW
0x180004f85  mov     ebx, eax
0x180004f87  test    eax, eax
0x180004f89  jnz     loc_1800050A8
0x180004f8f  mov     rcx, [rsp+670h+String]; StringBinding
0x180004f94  lea     rdx, [rsp+670h+Binding]; Binding
0x180004f99  call    cs:__imp_RpcBindingFromStringBindingW
0x180004f9f  mov     ebx, eax
0x180004fa1  test    eax, eax
0x180004fa3  jnz     loc_1800053D8
0x180004fa9  mov     rcx, [rsp+670h+Binding]; Binding
0x180004fae  lea     rdx, qword_180052040; IfSpec
0x180004fb5  call    cs:__imp_RpcEpResolveBinding
0x180004fbb  mov     ebx, eax
0x180004fbd  test    eax, eax
0x180004fbf  jnz     loc_1800053E3
0x180004fc5  lea     rax, [rbp+570h+var_5E8]
0x180004fc9  mov     [rbp+570h+SecurityQOS.Version], 1
0x180004fd0  mov     [rsp+670h+pSid], rax; pSid
0x180004fd5  lea     rcx, [rbp+570h+pIdentifierAuthority]; pIdentifierAuthority
0x180004fd9  mov     [rsp+670h+nSubAuthority7], r12d; nSubAuthority7
0x180004fde  xor     r9d, r9d; nSubAuthority1
0x180004fe1  mov     [rsp+670h+nSubAuthority6], r12d; nSubAuthority6
0x180004fe6  mov     r8d, 14h; nSubAuthority0
0x180004fec  mov     [rsp+670h+nSubAuthority5], r12d; nSubAuthority5
0x180004ff1  mov     dl, 1; nSubAuthorityCount
0x180004ff3  mov     [rsp+670h+nSubAuthority4], r12d; nSubAuthority4
0x180004ff8  mov     dword ptr [rsp+670h+StringBinding], r12d; int
0x180004ffd  mov     dword ptr [rsp+670h+Options], r12d; int
0x180005002  mov     [rbp+570h+SecurityQOS.Capabilities], 1
0x180005009  mov     [rbp+570h+SecurityQOS.IdentityTracking], 1
0x180005010  mov     [rbp+570h+SecurityQOS.ImpersonationType], 3
0x180005017  call    cs:__imp_AllocateAndInitializeSid
0x18000501d  test    eax, eax
0x18000501f  jz      loc_1800053EE
0x180005025  mov     rdx, [rbp+570h+var_5E8]; Sid
0x180005029  lea     rax, [rsp+670h+peUse]
0x18000502e  mov     qword ptr [rsp+670h+nSubAuthority4], rax; peUse
0x180005033  lea     r9, [rbp+570h+cchName]; cchName
0x180005037  lea     rax, [rsp+670h+cchReferencedDomainName]
0x18000503c  xor     ecx, ecx; lpSystemName
0x18000503e  mov     [rsp+670h+StringBinding], rax; int
0x180005043  lea     r8, [rbp+570h+Name]; Name
0x180005047  lea     rax, [rbp+570h+ReferencedDomainName]
0x18000504e  mov     [rsp+670h+Options], rax; int
0x180005053  call    cs:__imp_LookupAccountSidW
0x180005059  test    eax, eax
0x18000505b  jz      loc_180005357
0x180005061  mov     rcx, [rsp+670h+Binding]; Binding
0x180005066  lea     rax, [rbp+570h+SecurityQOS]
0x18000506a  mov     qword ptr [rsp+670h+nSubAuthority4], rax; SecurityQOS
0x18000506f  lea     rdx, [rbp+570h+Name]; ServerPrincName
0x180005073  mov     dword ptr [rsp+670h+StringBinding], r12d; AuthzSvc
0x180005078  mov     r9d, 0Ah; AuthnSvc
0x18000507e  mov     r8d, 4; AuthnLevel
0x180005084  mov     [rsp+670h+Options], r12; AuthIdentity
0x180005089  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000508f  mov     ebx, eax
0x180005091  test    eax, eax
0x180005093  jnz     loc_18000540B
0x180005099  mov     rax, [rsp+670h+Binding]
0x18000509e  mov     [rdi], rax
0x1800050a1  mov     [rsp+670h+Binding], r12
0x1800050a6  jmp     short loc_1800050CD
0x1800050a8  mov     r8d, 177h; unsigned int
0x1800050ae  mov     r9d, eax; unsigned int
0x1800050b1  mov     edx, 3; unsigned int
0x1800050b6  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800050bb  cmp     [rsp+670h+Binding], r12
0x1800050c0  jz      short loc_1800050CD
0x1800050c2  lea     rcx, [rsp+670h+Binding]; Binding
0x1800050c7  call    cs:__imp_RpcBindingFree
0x1800050cd  cmp     [rsp+670h+String], r12
0x1800050d2  jz      short loc_1800050DF
0x1800050d4  lea     rcx, [rsp+670h+String]; String
0x1800050d9  call    cs:__imp_RpcStringFreeW
0x1800050df  mov     rcx, [rbp+570h+var_5E8]; pSid
0x1800050e3  test    rcx, rcx
0x1800050e6  jz      short loc_1800050EE
0x1800050e8  call    cs:__imp_FreeSid
0x1800050ee  mov     eax, ebx
0x1800050f0  mov     rcx, [rbp+570h+var_30]
0x1800050f7  xor     rcx, rsp; StackCookie
0x1800050fa  call    __security_check_cookie
0x1800050ff  add     rsp, 658h
0x180005106  pop     r12
0x180005108  pop     rdi
0x180005109  pop     rbx
0x18000510a  pop     rbp
0x18000510b  retn
0x18000510c  mov     [rsp+670h+arg_8], rsi
0x180005114  call    cs:__imp_GetLastError
0x18000511a  cmp     cs:?g_fErrLogInitialized@@3HA, r12d; int g_fErrLogInitialized
0x180005121  xorps   xmm0, xmm0
0x180005124  movups  xmmword ptr [rbp+570h+SystemTime.wYear], xmm0
0x180005128  mov     esi, eax
0x18000512a  jz      loc_1800053A0
0x180005130  lea     rcx, [rbp+570h+SystemTime]; lpSystemTime
0x180005134  call    cs:__imp_GetLocalTime
0x18000513a  lea     rax, [rbp+570h+TimeStr]
0x18000513e  mov     dword ptr [rsp+670h+StringBinding], ebx; cchTime
0x180005142  xor     r9d, r9d; lpFormat
0x180005145  mov     [rsp+670h+Options], rax; lpTimeStr
0x18000514a  lea     r8, [rbp+570h+SystemTime]; lpTime
0x18000514e  xor     edx, edx; dwFlags
0x180005150  mov     ecx, 400h; Locale
0x180005155  call    cs:__imp_GetTimeFormatA
0x18000515b  lea     edx, [rax-1]
0x18000515e  cmp     edx, 0FFh
0x180005164  ja      loc_18000532B
0x18000516a  movsxd  rdx, eax
0x18000516d  lea     r8, [rbp+570h+TimeStr]
0x180005171  add     r8, rdx
0x180005174  sub     ebx, eax
0x180005176  mov     dword ptr [rsp+670h+StringBinding], ebx; cchDate
0x18000517a  xor     r9d, r9d; lpFormat
0x18000517d  mov     [rsp+670h+Options], r8; lpDateStr
0x180005182  mov     edx, 1; dwFlags
0x180005187  mov     ecx, 400h; Locale
0x18000518c  mov     byte ptr [r8-1], 20h ; ' '
0x180005191  lea     r8, [rbp+570h+SystemTime]; lpDate
0x180005195  call    cs:__imp_GetDateFormatA
0x18000519b  mov     eax, esi
0x18000519d  lea     r9, [rbp+570h+TimeStr]
0x1800051a1  and     eax, 1FFF0000h
0x1800051a6  mov     edx, 200h; unsigned __int64
0x1800051ab  cmp     eax, 0E5E0000h
0x1800051b0  jz      loc_1800053AA
0x1800051b6  mov     [rsp+670h+nSubAuthority4], esi
0x1800051ba  lea     r8, aCatalogdbSSAtL_0; "CatalogDB: %s: %s at line #%u encounter"...
0x1800051c1  lea     rax, aCatdbcliCpp; "catdbcli.cpp"
0x1800051c8  mov     dword ptr [rsp+670h+StringBinding], 160h
0x1800051d0  lea     rcx, [rbp+570h+Buffer]; char *
0x1800051d7  mov     [rsp+670h+Options], rax
0x1800051dc  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800051e1  cmp     cs:?g_fLogErrorsToDebugger@@3HA, r12d; int g_fLogErrorsToDebugger
0x1800051e8  mov     dword ptr [rsp+670h+Sid], r12d
0x1800051ed  jnz     loc_1800053C6
0x1800051f3  cmp     cs:?g_fLogErrorsToFile@@3HA, r12d; int g_fLogErrorsToFile
0x1800051fa  jz      loc_18000532B
0x180005200  xor     r8d, r8d; nSize
0x180005203  mov     [rsp+670h+arg_10], r14
0x18000520b  xor     edx, edx; lpDst
0x18000520d  lea     rcx, Src; "%SystemRoot%\\System32\\CatRoot2\\dberr"...
0x180005214  call    cs:__imp_ExpandEnvironmentStringsW
0x18000521a  mov     r14d, eax
0x18000521d  test    eax, eax
0x18000521f  jz      loc_180005323
0x180005225  mov     edx, r14d
0x180005228  mov     [rsp+670h+var_20], r15
0x180005230  add     rdx, rdx; uBytes
0x180005233  xor     ecx, ecx; uFlags
0x180005235  call    cs:__imp_LocalAlloc
0x18000523b  mov     r15, rax
0x18000523e  test    rax, rax
0x180005241  jz      loc_18000531B
0x180005247  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000524e  lea     rcx, Src; "%SystemRoot%\\System32\\CatRoot2\\dberr"...
0x180005255  mov     r8d, r14d; nSize
0x180005258  mov     rdx, rax; lpDst
0x18000525b  mov     rdi, rbx
0x18000525e  call    cs:__imp_ExpandEnvironmentStringsW
0x180005264  test    eax, eax
0x180005266  jz      loc_18000530D
0x18000526c  mov     qword ptr [rsp+670h+nSubAuthority4], r12; hTemplateFile
0x180005271  xor     r9d, r9d; lpSecurityAttributes
0x180005274  mov     dword ptr [rsp+670h+StringBinding], 80h; dwFlagsAndAttributes
0x18000527c  xor     r8d, r8d; dwShareMode
0x18000527f  mov     edx, 0C0000000h; dwDesiredAccess
0x180005284  mov     dword ptr [rsp+670h+Options], 4; dwCreationDisposition
0x18000528c  mov     rcx, r15; lpFileName
0x18000528f  call    cs:__imp_CreateFileW
0x180005295  mov     rdi, rax
0x180005298  cmp     rax, rbx
0x18000529b  jz      short loc_18000530D
0x18000529d  xor     edx, edx; lpFileSizeHigh
0x18000529f  mov     rcx, rax; hFile
0x1800052a2  call    cs:__imp_GetFileSize
0x1800052a8  cmp     eax, 30D40h
0x1800052ad  jnb     loc_180005374
0x1800052b3  mov     r9d, 2; dwMoveMethod
0x1800052b9  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800052bc  xor     edx, edx; lDistanceToMove
0x1800052be  mov     rcx, rdi; hFile
0x1800052c1  call    cs:__imp_SetFilePointer
0x1800052c7  cmp     eax, 0FFFFFFFFh
0x1800052ca  jz      short loc_18000530D
0x1800052cc  lea     rax, [rbp+570h+Buffer]
0x1800052d3  inc     rbx
0x1800052d6  cmp     [rax+rbx], r12b
0x1800052da  jnz     short loc_1800052D3
0x1800052dc  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800052df  mov     [rsp+670h+Options], r12; lpOverlapped
0x1800052e4  lea     r9, [rsp+670h+Sid]; lpNumberOfBytesWritten
0x1800052e9  mov     rcx, rdi; hFile
0x1800052ec  lea     rdx, [rbp+570h+Buffer]; lpBuffer
0x1800052f3  call    cs:__imp_WriteFile
0x1800052f9  mov     rcx, r15; hMem
0x1800052fc  call    cs:__imp_LocalFree
0x180005302  mov     rcx, rdi; hObject
0x180005305  call    cs:__imp_CloseHandle
0x18000530b  jmp     short loc_18000531B
0x18000530d  mov     rcx, r15; hMem
0x180005310  call    cs:__imp_LocalFree
0x180005316  cmp     rdi, rbx
0x180005319  jnz     short loc_180005302
0x18000531b  mov     r15, [rsp+670h+var_20]
0x180005323  mov     r14, [rsp+670h+arg_10]
0x18000532b  mov     ecx, esi; dwErrCode
0x18000532d  call    cs:__imp_SetLastError
0x180005333  call    cs:__imp_GetLastError
0x180005339  mov     rsi, [rsp+670h+arg_8]
0x180005341  mov     edx, 422h
0x180005346  cmp     eax, edx
0x180005348  mov     ecx, 426h
0x18000534d  cmovz   ecx, edx
0x180005350  mov     eax, ecx
0x180005352  jmp     loc_1800050F0
0x180005357  xor     r9d, r9d; unsigned int
0x18000535a  mov     edx, 3; unsigned int
0x18000535f  mov     r8d, 1A8h; unsigned int
0x180005365  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18000536a  mov     ebx, 6E6h
0x18000536f  jmp     loc_1800050BB
0x180005374  xor     r9d, r9d; dwMoveMethod
0x180005377  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000537a  xor     edx, edx; lDistanceToMove
0x18000537c  mov     rcx, rdi; hFile
0x18000537f  call    cs:__imp_SetFilePointer
0x180005385  cmp     eax, 0FFFFFFFFh
0x180005388  jz      short loc_18000530D
0x18000538a  mov     rcx, rdi; hFile
0x18000538d  call    cs:__imp_SetEndOfFile
0x180005393  test    eax, eax
0x180005395  jnz     loc_1800052B3
0x18000539b  jmp     loc_18000530D
0x1800053a0  call    ?ErrLog_Initialize@@YAXXZ; ErrLog_Initialize(void)
0x1800053a5  jmp     loc_180005130
0x1800053aa  movzx   ecx, si
0x1800053ad  lea     r8, aCatalogdbSSAtL; "CatalogDB: %s: %s at line #%u encounter"...
0x1800053b4  mov     eax, ecx
0x1800053b6  neg     eax
0x1800053b8  test    esi, esi
0x1800053ba  cmovns  eax, ecx
0x1800053bd  mov     [rsp+670h+nSubAuthority4], eax
0x1800053c1  jmp     loc_1800051C1
0x1800053c6  lea     rcx, [rbp+570h+Buffer]; lpOutputString
0x1800053cd  call    cs:__imp_OutputDebugStringA
0x1800053d3  jmp     loc_1800051F3
0x1800053d8  mov     r8d, 17Fh
0x1800053de  jmp     loc_1800050AE
  ... truncated ...
```
