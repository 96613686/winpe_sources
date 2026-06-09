# GetDriverDLLVersion(USDInfo *,ushort *,uint)

- ea: `0x180016ab8`
- end: `0x180016e82`
- name: `?GetDriverDLLVersion@@YAHPEAVUSDInfo@@PEAGI@Z`
- size: `970`
- prototype: `int(struct USDInfo *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015f90`
- `0x18002a448`

## callees

- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x180016ab8`
- `0x180016e88`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x180034658`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180016c8f`
- `ADVAPI32!RegCloseKey` at `0x180016c8f`
- `ADVAPI32!RegOpenKeyExW` at `0x180016b76`
- `ADVAPI32!RegOpenKeyExW` at `0x180016b76`
- `KERNEL32!LocalFree` at `0x180016c84`
- `KERNEL32!LocalFree` at `0x180016c84`
- `KERNEL32!LocalAlloc` at `0x180016bdb`
- `KERNEL32!LocalAlloc` at `0x180016bdb`
- `ole32!CLSIDFromString` at `0x180016b25`
- `ole32!CLSIDFromString` at `0x180016b25`
- `VERSION!GetFileVersionInfoW` at `0x180016c07`
- `VERSION!GetFileVersionInfoW` at `0x180016c07`
- `VERSION!GetFileVersionInfoSizeW` at `0x180016bc5`
- `VERSION!GetFileVersionInfoSizeW` at `0x180016bc5`
- `VERSION!VerQueryValueW` at `0x180016c33`
- `VERSION!VerQueryValueW` at `0x180016c33`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x180016ba8`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x180016ba8`

## string_xrefs

- `0x180016b3a`: `CLSID\%s\InProcServer32`
- `0x180016ccf`: `GetDriverDLLVersion`
- `0x180016cff`: `GetDriverDLLVersion`
- `0x180016d21`: `GetDriverDLLVersion`
- `0x180016d59`: `GetDriverDLLVersion`
- `0x180016d8a`: `GetDriverDLLVersion`
- `0x180016dba`: `GetDriverDLLVersion`
- `0x180016ddc`: `GetDriverDLLVersion`
- `0x180016e10`: `GetDriverDLLVersion`
- `0x180016e41`: `GetDriverDLLVersion`
- `0x180016e71`: `GetDriverDLLVersion`
- `0x180016cbe`: `GetDriverDLLVersion, Could not allocate memory for file version information`
- `0x180016ce6`: `GetDriverDLLVersion, Could not allocate memory for file version information`
- `0x180016d10`: `GetDriverDLLVersion, No InprocServer32`
- `0x180016d38`: `GetDriverDLLVersion, No InprocServer32`
- `0x180016d79`: `GetDriverDLLVersion, GetFileVersionInfoW Failed`
- `0x180016da1`: `GetDriverDLLVersion, GetFileVersionInfoW Failed`
- `0x180016d48`: `GetDriverDLLVersion, VerQueryValue Failed`
- `0x180016d70`: `GetDriverDLLVersion, VerQueryValue Failed`
- `0x180016dff`: `GetDriverDLLVersion, CLSID not registered`
- `0x180016e27`: `GetDriverDLLVersion, CLSID not registered`
- `0x180016dcb`: `GetDriverDLLVersion, File Version Information Size is < 0 (File may be missing version resource)`
- `0x180016df3`: `GetDriverDLLVersion, File Version Information Size is < 0 (File may be missing version resource)`
- `0x180016e30`: `GetDriverDLLVersion, Invalid CLSID string`
- `0x180016e58`: `GetDriverDLLVersion, Invalid CLSID string`

## pseudocode

```c
__int64 __fastcall GetDriverDLLVersion(struct USDInfo *a1, unsigned __int16 *a2)
{
  unsigned int v4; // r15d
  const OLECHAR *v5; // rcx
  __int64 v6; // r9
  DWORD FileVersionInfoSizeW; // eax
  DWORD v8; // ebx
  HLOCAL v9; // rax
  void *v10; // rdi
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  char *v17; // rbx
  void *v18; // rdx
  char *v19; // rbx
  void *v20; // rdx
  void **v21; // rax
  void *v22; // rdx
  __int64 v23; // rcx
  char *v24; // rbx
  void *v25; // rdx
  char *v26; // rbx
  void *v27; // rdx
  char *v28; // rbx
  void *v29; // rdx
  void **v30; // rax
  void *v31; // rdx
  __int64 v32; // rcx
  char *v33; // rbx
  void *v34; // rdx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  LONG cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwHandle; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int puLen; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID lpBuffer; // [rsp+58h] [rbp-A8h] BYREF
  GUID pclsid; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Data[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[304]; // [rsp+280h] [rbp+180h] BYREF

  if ( a2 && a1 )
  {
    v4 = 0;
    memset_0(a2, 0, 0x208u);
    v5 = (const OLECHAR *)*((_QWORD *)a1 + 113);
    pclsid = 0;
    if ( CLSIDFromString(v5, &pclsid) < 0 )
    {
      v33 = (char *)WiaTrace_TraceLogWithSubComp(0, "GetDriverDLLVersion, Invalid CLSID string");
      WriteDbgTraceWarningWI("GetDriverDLLVersion", v33);
      WiaTrcLib::Free((WiaTrcLib *)v33, v34);
      v30 = (void **)WiaTrace_TraceWithSubComp(0, "GetDriverDLLVersion, Invalid CLSID string");
    }
    else
    {
      v6 = *((_QWORD *)a1 + 113);
      hKey = 0;
      StringCchPrintfW(SubKey, 0x12Cu, L"CLSID\\%s\\InProcServer32", v6);
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, &hKey) )
      {
        memset_0(Data, 0, 0x208u);
        cbData = 520;
        if ( RegQueryValueW(hKey, 0, Data, &cbData) )
        {
          v17 = (char *)WiaTrace_TraceLogWithSubComp(0, "GetDriverDLLVersion, No InprocServer32");
          WriteDbgTraceWarningWI("GetDriverDLLVersion", v17);
          WiaTrcLib::Free((WiaTrcLib *)v17, v18);
          v14 = (void **)WiaTrace_TraceWithSubComp(0, "GetDriverDLLVersion, No InprocServer32");
        }
        else
        {
          dwHandle = 0;
          FileVersionInfoSizeW = GetFileVersionInfoSizeW(Data, &dwHandle);
          v8 = FileVersionInfoSizeW;
          if ( FileVersionInfoSizeW )
          {
            v9 = LocalAlloc(0x40u, FileVersionInfoSizeW);
            v10 = v9;
            if ( v9 )
            {
              memset_0(v9, 0, v8);
              if ( GetFileVersionInfoW(Data, 0, v8, v10) )
              {
                lpBuffer = 0;
                puLen = 0;
                if ( VerQueryValueW(v10, L"\\", &lpBuffer, &puLen) )
                {
                  LODWORD(phkResult) = *((unsigned __int16 *)lpBuffer + 4);
                  StringCchPrintfW(
                    a2,
                    0x104u,
                    L"%d.%d.%d.%d",
                    *((unsigned __int16 *)lpBuffer + 5),
                    phkResult,
                    *((unsigned __int16 *)lpBuffer + 7),
                    *((unsigned __int16 *)lpBuffer + 6));
                  v4 = 1;
LABEL_11:
                  LocalFree(v10);
LABEL_12:
                  RegCloseKey(hKey);
                  return v4;
                }
                v19 = (char *)WiaTrace_TraceLogWithSubComp(0, "GetDriverDLLVersion, VerQueryValue Failed");
                WriteDbgTraceWarningWI("GetDriverDLLVersion", v19);
                WiaTrcLib::Free((WiaTrcLib *)v19, v20);
                v21 = (void **)WiaTrace_TraceWithSubComp(0, "GetDriverDLLVersion, VerQueryValue Failed");
              }
              else
              {
                v24 = (char *)WiaTrace_TraceLogWithSubComp(0, "GetDriverDLLVersion, GetFileVersionInfoW Failed");
                WriteDbgTraceWarningWI("GetDriverDLLVersion", v24);
                WiaTrcLib::Free((WiaTrcLib *)v24, v25);
                v21 = (void **)WiaTrace_TraceWithSubComp(0, "GetDriverDLLVersion, GetFileVersionInfoW Failed");
              }
              WiaTrace_ProcessTrace_Ex(v23, v22, (void *)"GetDriverDLLVersion", 2, v21);
              goto LABEL_11;
            }
            v12 = (char *)WiaTrace_TraceLogWithSubComp(
                            0,
                            "GetDriverDLLVersion, Could not allocate memory for file version information");
            WriteDbgTraceWarningWI("GetDriverDLLVersion", v12);
            WiaTrcLib::Free((WiaTrcLib *)v12, v13);
            v14 = (void **)WiaTrace_TraceWithSubComp(
                             0,
                             "GetDriverDLLVersion, Could not allocate memory for file version information");
          }
          else
          {
            v26 = (char *)WiaTrace_TraceLogWithSubComp(
                            0,
                            "GetDriverDLLVersion, File Version Information Size is < 0 (File may be missing version resource)");
            WriteDbgTraceWarningWI("GetDriverDLLVersion", v26);
            WiaTrcLib::Free((WiaTrcLib *)v26, v27);
            v14 = (void **)WiaTrace_TraceWithSubComp(
                             0,
                             "GetDriverDLLVersion, File Version Information Size is < 0 (File may be missing version resource)");
          }
        }
        WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"GetDriverDLLVersion", 2, v14);
        goto LABEL_12;
      }
      v28 = (char *)WiaTrace_TraceLogWithSubComp(0, "GetDriverDLLVersion, CLSID not registered");
      WriteDbgTraceWarningWI("GetDriverDLLVersion", v28);
      WiaTrcLib::Free((WiaTrcLib *)v28, v29);
      v30 = (void **)WiaTrace_TraceWithSubComp(0, "GetDriverDLLVersion, CLSID not registered");
    }
    WiaTrace_ProcessTrace_Ex(v32, v31, (void *)"GetDriverDLLVersion", 2, v30);
    return v4;
  }
  return 0;
}

```

## disassembly

```asm
0x180016ab8  mov     [rsp-8+arg_10], rbx
0x180016abd  push    rbp
0x180016abe  push    rsi
0x180016abf  push    rdi
0x180016ac0  push    r14
0x180016ac2  push    r15
0x180016ac4  lea     rbp, [rsp-3F0h]
0x180016acc  sub     rsp, 4F0h
0x180016ad3  mov     rax, cs:__security_cookie
0x180016ada  xor     rax, rsp
0x180016add  mov     [rbp+410h+var_30], rax
0x180016ae4  mov     rsi, rdx
0x180016ae7  mov     rbx, rcx
0x180016aea  test    rdx, rdx
0x180016aed  jz      loc_180016D41
0x180016af3  test    rcx, rcx
0x180016af6  jz      loc_180016D41
0x180016afc  mov     edi, 208h
0x180016b01  xor     edx, edx; Val
0x180016b03  mov     r8d, edi; Size
0x180016b06  mov     rcx, rsi; void *
0x180016b09  xor     r15d, r15d
0x180016b0c  call    memset_0
0x180016b11  mov     rcx, [rbx+388h]; lpsz
0x180016b18  lea     rdx, [rsp+510h+pclsid]; pclsid
0x180016b1d  xorps   xmm0, xmm0
0x180016b20  movups  xmmword ptr [rsp+510h+pclsid.Data1], xmm0
0x180016b25  call    cs:__imp_CLSIDFromString
0x180016b2b  test    eax, eax
0x180016b2d  js      loc_180016E30
0x180016b33  mov     r9, [rbx+388h]
0x180016b3a  lea     r8, aClsidSInprocse; "CLSID\\%s\\InProcServer32"
0x180016b41  mov     edx, 12Ch; unsigned __int64
0x180016b46  mov     [rsp+510h+hKey], r15
0x180016b4b  lea     rcx, [rbp+410h+SubKey]; unsigned __int16 *
0x180016b52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016b57  lea     rax, [rsp+510h+hKey]
0x180016b5c  xor     r8d, r8d; ulOptions
0x180016b5f  lea     r9d, [r15+1]; samDesired
0x180016b63  mov     [rsp+510h+phkResult], rax; phkResult
0x180016b68  lea     rdx, [rbp+410h+SubKey]; lpSubKey
0x180016b6f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180016b76  call    cs:__imp_RegOpenKeyExW
0x180016b7c  test    eax, eax
0x180016b7e  jnz     loc_180016DFF
0x180016b84  mov     r8d, edi; Size
0x180016b87  lea     rcx, [rsp+510h+Data]; void *
0x180016b8c  xor     edx, edx; Val
0x180016b8e  call    memset_0
0x180016b93  mov     rcx, [rsp+510h+hKey]; hKey
0x180016b98  lea     r9, [rsp+510h+cbData]; lpcbData
0x180016b9d  lea     r8, [rsp+510h+Data]; lpData
0x180016ba2  mov     [rsp+510h+cbData], edi
0x180016ba6  xor     edx, edx; lpSubKey
0x180016ba8  call    cs:__imp_RegQueryValueW
0x180016bae  test    eax, eax
0x180016bb0  jnz     loc_180016D10
0x180016bb6  lea     rdx, [rsp+510h+dwHandle]; lpdwHandle
0x180016bbb  mov     [rsp+510h+dwHandle], r15d
0x180016bc0  lea     rcx, [rsp+510h+Data]; lptstrFilename
0x180016bc5  call    cs:__imp_GetFileVersionInfoSizeW
0x180016bcb  mov     ebx, eax
0x180016bcd  test    eax, eax
0x180016bcf  jz      loc_180016DCB
0x180016bd5  mov     edx, ebx; uBytes
0x180016bd7  lea     ecx, [r15+40h]; uFlags
0x180016bdb  call    cs:__imp_LocalAlloc
0x180016be1  mov     rdi, rax
0x180016be4  test    rax, rax
0x180016be7  jz      loc_180016CBE
0x180016bed  mov     r8d, ebx; Size
0x180016bf0  xor     edx, edx; Val
0x180016bf2  mov     rcx, rax; void *
0x180016bf5  call    memset_0
0x180016bfa  mov     r9, rdi; lpData
0x180016bfd  lea     rcx, [rsp+510h+Data]; lptstrFilename
0x180016c02  mov     r8d, ebx; dwLen
0x180016c05  xor     edx, edx; dwHandle
0x180016c07  call    cs:__imp_GetFileVersionInfoW
0x180016c0d  test    eax, eax
0x180016c0f  jz      loc_180016D79
0x180016c15  lea     r9, [rsp+510h+puLen]; puLen
0x180016c1a  mov     [rsp+510h+lpBuffer], r15
0x180016c1f  lea     r8, [rsp+510h+lpBuffer]; lplpBuffer
0x180016c24  mov     [rsp+510h+puLen], r15d
0x180016c29  lea     rdx, SubBlock; "\\"
0x180016c30  mov     rcx, rdi; pBlock
0x180016c33  call    cs:__imp_VerQueryValueW
0x180016c39  test    eax, eax
0x180016c3b  jz      loc_180016D48
0x180016c41  mov     r9, [rsp+510h+lpBuffer]
0x180016c46  mov     rcx, rsi; unsigned __int16 *
0x180016c49  movzx   edx, word ptr [r9+0Eh]
0x180016c4e  movzx   r8d, word ptr [r9+8]
0x180016c53  movzx   eax, word ptr [r9+0Ch]
0x180016c58  movzx   r9d, word ptr [r9+0Ah]
0x180016c5d  mov     [rsp+510h+var_4E0], eax
0x180016c61  mov     [rsp+510h+var_4E8], edx
0x180016c65  mov     edx, 104h; unsigned __int64
0x180016c6a  mov     dword ptr [rsp+510h+phkResult], r8d
0x180016c6f  lea     r8, aDDDD; "%d.%d.%d.%d"
0x180016c76  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016c7b  mov     r15d, 1
0x180016c81  mov     rcx, rdi; hMem
0x180016c84  call    cs:__imp_LocalFree
0x180016c8a  mov     rcx, [rsp+510h+hKey]; hKey
0x180016c8f  call    cs:__imp_RegCloseKey
0x180016c95  mov     eax, r15d
0x180016c98  mov     rcx, [rbp+410h+var_30]
0x180016c9f  xor     rcx, rsp; StackCookie
0x180016ca2  call    __security_check_cookie
0x180016ca7  mov     rbx, [rsp+510h+arg_10]
0x180016caf  add     rsp, 4F0h
0x180016cb6  pop     r15
0x180016cb8  pop     r14
0x180016cba  pop     rdi
0x180016cbb  pop     rsi
0x180016cbc  pop     rbp
0x180016cbd  retn
0x180016cbe  lea     rdx, aGetdriverdllve_6; "GetDriverDLLVersion, Could not allocate"...
0x180016cc5  xor     ecx, ecx
0x180016cc7  call    WiaTrace_TraceLogWithSubComp
0x180016ccc  mov     rdx, rax; char *
0x180016ccf  lea     rcx, aGetdriverdllve_1; "GetDriverDLLVersion"
0x180016cd6  mov     rbx, rax
0x180016cd9  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180016cde  mov     rcx, rbx; this
0x180016ce1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180016ce6  lea     rdx, aGetdriverdllve_6; "GetDriverDLLVersion, Could not allocate"...
0x180016ced  xor     ecx, ecx
0x180016cef  call    WiaTrace_TraceWithSubComp
0x180016cf4  mov     r9d, 2; int
0x180016cfa  mov     [rsp+510h+phkResult], rax; lpMem
0x180016cff  lea     r8, aGetdriverdllve_1; "GetDriverDLLVersion"
0x180016d06  call    WiaTrace_ProcessTrace_Ex
0x180016d0b  jmp     loc_180016C8A
0x180016d10  lea     rdx, aGetdriverdllve_2; "GetDriverDLLVersion, No InprocServer32"
0x180016d17  xor     ecx, ecx
0x180016d19  call    WiaTrace_TraceLogWithSubComp
0x180016d1e  mov     rdx, rax; char *
0x180016d21  lea     rcx, aGetdriverdllve_1; "GetDriverDLLVersion"
0x180016d28  mov     rbx, rax
0x180016d2b  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180016d30  mov     rcx, rbx; this
0x180016d33  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180016d38  lea     rdx, aGetdriverdllve_2; "GetDriverDLLVersion, No InprocServer32"
0x180016d3f  jmp     short loc_180016CED
0x180016d41  xor     eax, eax
0x180016d43  jmp     loc_180016C98
0x180016d48  lea     rdx, aGetdriverdllve_0; "GetDriverDLLVersion, VerQueryValue Fail"...
0x180016d4f  xor     ecx, ecx
0x180016d51  call    WiaTrace_TraceLogWithSubComp
0x180016d56  mov     rdx, rax; char *
0x180016d59  lea     rcx, aGetdriverdllve_1; "GetDriverDLLVersion"
0x180016d60  mov     rbx, rax
0x180016d63  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180016d68  mov     rcx, rbx; this
0x180016d6b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180016d70  lea     rdx, aGetdriverdllve_0; "GetDriverDLLVersion, VerQueryValue Fail"...
0x180016d77  jmp     short loc_180016DA8
0x180016d79  lea     rdx, aGetdriverdllve_7; "GetDriverDLLVersion, GetFileVersionInfo"...
0x180016d80  xor     ecx, ecx
0x180016d82  call    WiaTrace_TraceLogWithSubComp
0x180016d87  mov     rdx, rax; char *
0x180016d8a  lea     rcx, aGetdriverdllve_1; "GetDriverDLLVersion"
0x180016d91  mov     rbx, rax
0x180016d94  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180016d99  mov     rcx, rbx; this
0x180016d9c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180016da1  lea     rdx, aGetdriverdllve_7; "GetDriverDLLVersion, GetFileVersionInfo"...
0x180016da8  xor     ecx, ecx
0x180016daa  call    WiaTrace_TraceWithSubComp
0x180016daf  mov     r9d, 2; int
0x180016db5  mov     [rsp+510h+phkResult], rax; lpMem
0x180016dba  lea     r8, aGetdriverdllve_1; "GetDriverDLLVersion"
0x180016dc1  call    WiaTrace_ProcessTrace_Ex
0x180016dc6  jmp     loc_180016C81
0x180016dcb  lea     rdx, aGetdriverdllve; "GetDriverDLLVersion, File Version Infor"...
0x180016dd2  xor     ecx, ecx
0x180016dd4  call    WiaTrace_TraceLogWithSubComp
0x180016dd9  mov     rdx, rax; char *
0x180016ddc  lea     rcx, aGetdriverdllve_1; "GetDriverDLLVersion"
0x180016de3  mov     rbx, rax
0x180016de6  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180016deb  mov     rcx, rbx; this
0x180016dee  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180016df3  lea     rdx, aGetdriverdllve; "GetDriverDLLVersion, File Version Infor"...
0x180016dfa  jmp     loc_180016CED
0x180016dff  lea     rdx, aGetdriverdllve_4; "GetDriverDLLVersion, CLSID not register"...
0x180016e06  xor     ecx, ecx
0x180016e08  call    WiaTrace_TraceLogWithSubComp
0x180016e0d  mov     rdx, rax; char *
0x180016e10  lea     rcx, aGetdriverdllve_1; "GetDriverDLLVersion"
0x180016e17  mov     rbx, rax
0x180016e1a  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180016e1f  mov     rcx, rbx; this
0x180016e22  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180016e27  lea     rdx, aGetdriverdllve_4; "GetDriverDLLVersion, CLSID not register"...
0x180016e2e  jmp     short loc_180016E5F
0x180016e30  lea     rdx, aGetdriverdllve_3; "GetDriverDLLVersion, Invalid CLSID stri"...
0x180016e37  xor     ecx, ecx
0x180016e39  call    WiaTrace_TraceLogWithSubComp
0x180016e3e  mov     rdx, rax; char *
0x180016e41  lea     rcx, aGetdriverdllve_1; "GetDriverDLLVersion"
0x180016e48  mov     rbx, rax
0x180016e4b  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180016e50  mov     rcx, rbx; this
0x180016e53  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180016e58  lea     rdx, aGetdriverdllve_3; "GetDriverDLLVersion, Invalid CLSID stri"...
0x180016e5f  xor     ecx, ecx
0x180016e61  call    WiaTrace_TraceWithSubComp
0x180016e66  mov     r9d, 2; int
0x180016e6c  mov     [rsp+510h+phkResult], rax; lpMem
0x180016e71  lea     r8, aGetdriverdllve_1; "GetDriverDLLVersion"
0x180016e78  call    WiaTrace_ProcessTrace_Ex
0x180016e7d  jmp     loc_180016C95
```
