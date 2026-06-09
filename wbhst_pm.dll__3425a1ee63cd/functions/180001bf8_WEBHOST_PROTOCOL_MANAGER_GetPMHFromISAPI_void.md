# WEBHOST_PROTOCOL_MANAGER::GetPMHFromISAPI(void)

- ea: `0x180001bf8`
- end: `0x18000206e`
- name: `?GetPMHFromISAPI@WEBHOST_PROTOCOL_MANAGER@@AEAAJXZ`
- size: `1142`
- prototype: `__int64 __fastcall(WEBHOST_PROTOCOL_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002230`

## callees

- `0x180001bf8`
- `0x180004842`
- `0x180004880`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001de4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001dfe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001de4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001dfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001e81`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001e81`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180001dcd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180001dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eae`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180001d3e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180001d3e`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180001d12`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180001d12`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001d27`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001d27`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001d6a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000204b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001d6a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000204b`
- `iisutil!PuDbgPrint` at `0x180001fd7`
- `iisutil!PuDbgPrint` at `0x180002041`
- `iisutil!PuDbgPrint` at `0x180001fd7`
- `iisutil!PuDbgPrint` at `0x180002041`
- `iisutil!PuDbgPrintError` at `0x180001dac`
- `iisutil!PuDbgPrintError` at `0x180001e69`
- `iisutil!PuDbgPrintError` at `0x180001dac`
- `iisutil!PuDbgPrintError` at `0x180001e69`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001c3f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001c6b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001c3f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001c6b`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180001cde`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180001cde`

## string_xrefs

- `0x180001da1`: `servercommon\inetsrv\iis\iisrearc\core\webhost_pm\webhost_protocol_manager.cxx`
- `0x180001e5e`: `servercommon\inetsrv\iis\iisrearc\core\webhost_pm\webhost_protocol_manager.cxx`
- `0x180001fbe`: `servercommon\inetsrv\iis\iisrearc\core\webhost_pm\webhost_protocol_manager.cxx`
- `0x180002035`: `servercommon\inetsrv\iis\iisrearc\core\webhost_pm\webhost_protocol_manager.cxx`
- `0x180001d33`: `\webengine.dll`
- `0x180001d81`: `Error getting the file name for asp net isapi dll.\n`
- `0x180001d95`: `WEBHOST_PROTOCOL_MANAGER::GetPMHFromISAPI`
- `0x180001e50`: `WEBHOST_PROTOCOL_MANAGER::GetPMHFromISAPI`
- `0x180001fb3`: `WEBHOST_PROTOCOL_MANAGER::GetPMHFromISAPI`
- `0x18000202e`: `WEBHOST_PROTOCOL_MANAGER::GetPMHFromISAPI`
- `0x180001dc6`: `webengine4.dll`
- `0x180001ddd`: `webengine.dll`
- `0x180001e39`: `Error loading aspnet_isapi service dll '%ws'.\n`
- `0x180001f33`: `Error getting the process host manager (IProcessProtocolManager interface).  hr = %x\n`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::GetPMHFromISAPI(WEBHOST_PROTOCOL_MANAGER *this)
{
  __int64 v2; // rcx
  signed int v3; // edi
  const char *v4; // rax
  __int64 v5; // r8
  HMODULE *v6; // rdi
  HMODULE Library; // rax
  signed int v8; // eax
  DWORD v9; // eax
  const char *v10; // rcx
  __int64 v11; // r8
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  _QWORD *v14; // rsi
  __int64 v15; // r8
  const char *v16; // rax
  __int64 (__fastcall ***v17)(_QWORD, GUID *, char *); // rcx
  _QWORD *v18; // rsi
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v22[32]; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v23; // [rsp+70h] [rbp-90h]
  unsigned int v24; // [rsp+78h] [rbp-88h]
  int v25; // [rsp+80h] [rbp-80h]
  _BYTE v26[32]; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpLibFileName; // [rsp+A8h] [rbp-58h]
  int v28; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v29[264]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v30[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  memset_0(v29, 0, 0x208u);
  STRU::STRU((STRU *)v26, v29, 0x104u);
  memset_0(v30, 0, 0x20Au);
  STRU::STRU((STRU *)v22, v30, 0x105u);
  v2 = *((_QWORD *)this + 8);
  v20 = v24 >> 1;
  v21 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v2 + 16LL))(v2, 3, &v21);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *, unsigned int *))(*(_QWORD *)v21 + 32LL))(
           v21,
           5,
           v23,
           &v20);
    if ( v3 == -2147024774 )
    {
      v3 = STRU::Resize((STRU *)v22, 2 * v20);
      if ( v3 < 0 )
        goto LABEL_9;
      v3 = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *, unsigned int *))(*(_QWORD *)v21 + 32LL))(
             v21,
             5,
             v23,
             &v20);
    }
    if ( v3 >= 0 )
    {
      STRU::SyncWithBuffer((STRU *)v22);
      if ( v25 )
      {
        v3 = STRU::Copy((STRU *)v26, v23);
        if ( v3 >= 0 )
          v3 = STRU::Append((STRU *)v26, L"\\webengine.dll");
      }
    }
  }
LABEL_9:
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    v21 = 0;
  }
  STRU::~STRU((STRU *)v22);
  if ( v3 >= 0 )
  {
    if ( v28 )
    {
      Library = LoadLibraryExW(lpLibFileName, 0, 8u);
      *((_QWORD *)this + 7) = Library;
    }
    else
    {
      v6 = (HMODULE *)((char *)this + 56);
      if ( GetModuleHandleExW(0, L"webengine4.dll", (HMODULE *)this + 7) )
      {
        Library = *v6;
      }
      else
      {
        Library = LoadLibraryExW(L"webengine.dll", 0, 8u);
        *v6 = Library;
      }
    }
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "GetIsapiProcessHost");
      if ( ProcAddress )
      {
        v14 = (_QWORD *)((char *)this + 72);
        v3 = ((__int64 (__fastcall *)(_QWORD, char *))ProcAddress)(*((_QWORD *)this + 13), (char *)this + 72);
        if ( v3 < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_49;
          v4 = "Error getting the process host manager.  hr = %x\n";
          v5 = 1651;
          goto LABEL_14;
        }
        v3 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v14)(
               *v14,
               &GUID_1cc9099d_0a8d_41cb_87d6_845e4f8c4e91,
               (char *)this + 80);
        if ( v3 >= 0 )
        {
          v3 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v14)(
                 *v14,
                 &GUID_9d98b251_453e_44f6_9cec_8b5aed970129,
                 (char *)this + 88);
          if ( v3 >= 0 )
          {
            v17 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v14;
            v18 = (_QWORD *)((char *)this + 112);
            v3 = (**v17)(v17, &GUID_ae54f424_71bc_4da5_aa2f_8c0cd53496fc, (char *)this + 112);
            if ( v3 < 0 )
            {
              if ( (g_dwDebugFlags & 3) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\webhost_pm\\webhost_protocol_manager.cxx",
                  1710,
                  "WEBHOST_PROTOCOL_MANAGER::GetPMHFromISAPI",
                  "Unable to retrieve IApplicationPreloadManager interface (perhaps not available).  hr = %x\n");
              v3 = 0;
              *v18 = 0;
            }
            if ( !*v18 )
              goto LABEL_49;
            v3 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v18 + 24LL))(
                   *v18,
                   (*((_QWORD *)this + 13) + 8LL) & -(__int64)(*((_QWORD *)this + 13) != 0));
            if ( v3 >= 0 || (g_dwDebugFlags & 3) == 0 )
              goto LABEL_49;
            v15 = 1726;
            v16 = "Unable to set the IApplicationPreloadUtil pointer.  hr = %x\n";
          }
          else
          {
            if ( (g_dwDebugFlags & 3) == 0 )
              goto LABEL_49;
            v15 = 1691;
            v16 = "Error getting the process host manager (IProcessHostIdleAndHealthMonitor interface).  hr = %x\n";
          }
        }
        else
        {
          if ( (g_dwDebugFlags & 3) == 0 )
            goto LABEL_49;
          v15 = 1674;
          v16 = "Error getting the process host manager (IProcessProtocolManager interface).  hr = %x\n";
        }
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\webhost_pm\\webhost_protocol_manager.cxx",
          v15,
          "WEBHOST_PROTOCOL_MANAGER::GetPMHFromISAPI",
          v16);
        goto LABEL_49;
      }
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_49;
      v9 = GetLastError();
      v10 = "Could not find entry point '%s'.\n";
      v11 = 1640;
    }
    else
    {
      v8 = GetLastError();
      v3 = v8;
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_49;
      v9 = GetLastError();
      v10 = "Error loading aspnet_isapi service dll '%ws'.\n";
      v11 = 1625;
    }
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\webhost_pm\\webhost_protocol_manager.cxx",
      v11,
      "WEBHOST_PROTOCOL_MANAGER::GetPMHFromISAPI",
      v9,
      v10);
    goto LABEL_49;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v4 = "Error getting the file name for asp net isapi dll.\n";
    v5 = 1583;
LABEL_14:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\webhost_pm\\webhost_protocol_manager.cxx",
      v5,
      "WEBHOST_PROTOCOL_MANAGER::GetPMHFromISAPI",
      v3,
      v4);
  }
LABEL_49:
  STRU::~STRU((STRU *)v26);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180001bf8  push    rbp
0x180001bfa  push    rbx
0x180001bfb  push    rsi
0x180001bfc  push    rdi
0x180001bfd  lea     rbp, [rsp-3F8h]
0x180001c05  sub     rsp, 4F8h
0x180001c0c  mov     rax, cs:__security_cookie
0x180001c13  xor     rax, rsp
0x180001c16  mov     [rbp+410h+var_30], rax
0x180001c1d  mov     rbx, rcx
0x180001c20  xor     edx, edx; Val
0x180001c22  lea     rcx, [rbp+410h+var_450]; void *
0x180001c26  mov     r8d, 208h; Size
0x180001c2c  call    memset_0
0x180001c31  mov     r8d, 104h
0x180001c37  lea     rdx, [rbp+410h+var_450]
0x180001c3b  lea     rcx, [rbp+410h+var_488]
0x180001c3f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001c45  xor     edx, edx; Val
0x180001c47  lea     rcx, [rbp+410h+var_240]; void *
0x180001c4e  mov     r8d, 20Ah; Size
0x180001c54  call    memset_0
0x180001c59  mov     r8d, 105h
0x180001c5f  lea     rdx, [rbp+410h+var_240]
0x180001c66  lea     rcx, [rsp+510h+var_4C0]
0x180001c6b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001c71  mov     eax, [rsp+510h+var_498]
0x180001c75  lea     r8, [rsp+510h+var_4C8]
0x180001c7a  mov     rcx, [rbx+40h]
0x180001c7e  mov     edx, 3
0x180001c83  shr     eax, 1
0x180001c85  mov     [rsp+510h+var_4D0], eax
0x180001c89  mov     [rsp+510h+var_4C8], 0
0x180001c92  mov     rax, [rcx]
0x180001c95  mov     rax, [rax+10h]
0x180001c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c9e  mov     edi, eax
0x180001ca0  test    eax, eax
0x180001ca2  js      loc_180001D46
0x180001ca8  mov     rcx, [rsp+510h+var_4C8]
0x180001cad  lea     r9, [rsp+510h+var_4D0]
0x180001cb2  mov     r8, [rsp+510h+var_4A0]
0x180001cb7  mov     esi, 5
0x180001cbc  mov     edx, esi
0x180001cbe  mov     rax, [rcx]
0x180001cc1  mov     rax, [rax+20h]
0x180001cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cca  mov     edi, eax
0x180001ccc  cmp     eax, 8007007Ah
0x180001cd1  jnz     short loc_180001D09
0x180001cd3  mov     edx, [rsp+510h+var_4D0]
0x180001cd7  lea     rcx, [rsp+510h+var_4C0]
0x180001cdc  add     edx, edx
0x180001cde  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180001ce4  mov     edi, eax
0x180001ce6  test    eax, eax
0x180001ce8  js      short loc_180001D46
0x180001cea  mov     rcx, [rsp+510h+var_4C8]
0x180001cef  lea     r9, [rsp+510h+var_4D0]
0x180001cf4  mov     r8, [rsp+510h+var_4A0]
0x180001cf9  mov     edx, esi
0x180001cfb  mov     rax, [rcx]
0x180001cfe  mov     rax, [rax+20h]
0x180001d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d07  mov     edi, eax
0x180001d09  test    edi, edi
0x180001d0b  js      short loc_180001D46
0x180001d0d  lea     rcx, [rsp+510h+var_4C0]
0x180001d12  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180001d18  cmp     [rbp+410h+var_490], 0
0x180001d1c  jz      short loc_180001D46
0x180001d1e  mov     rdx, [rsp+510h+var_4A0]
0x180001d23  lea     rcx, [rbp+410h+var_488]
0x180001d27  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001d2d  mov     edi, eax
0x180001d2f  test    eax, eax
0x180001d31  js      short loc_180001D46
0x180001d33  lea     rdx, aWebengineDll_0; "\\webengine.dll"
0x180001d3a  lea     rcx, [rbp+410h+var_488]
0x180001d3e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180001d44  mov     edi, eax
0x180001d46  mov     rcx, [rsp+510h+var_4C8]
0x180001d4b  test    rcx, rcx
0x180001d4e  jz      short loc_180001D65
0x180001d50  mov     rax, [rcx]
0x180001d53  mov     rax, [rax+8]
0x180001d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d5c  mov     [rsp+510h+var_4C8], 0
0x180001d65  lea     rcx, [rsp+510h+var_4C0]
0x180001d6a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001d70  test    edi, edi
0x180001d72  jns     short loc_180001DB7
0x180001d74  test    cs:g_dwDebugFlags, 0Fh
0x180001d7b  jz      loc_180002047
0x180001d81  lea     rax, aErrorGettingTh; "Error getting the file name for asp net"...
0x180001d88  mov     r8d, 62Fh
0x180001d8e  mov     rcx, cs:g_pDebug
0x180001d95  lea     r9, aWebhostProtoco_1; "WEBHOST_PROTOCOL_MANAGER::GetPMHFromISA"...
0x180001d9c  mov     [rsp+510h+var_4E8], rax
0x180001da1  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180001da8  mov     dword ptr [rsp+510h+var_4F0], edi
0x180001dac  call    cs:__imp_PuDbgPrintError
0x180001db2  jmp     loc_180002047
0x180001db7  cmp     [rbp+410h+var_458], 0
0x180001dbb  jnz     short loc_180001DF4
0x180001dbd  lea     rdi, [rbx+38h]
0x180001dc1  xor     ecx, ecx; dwFlags
0x180001dc3  mov     r8, rdi; phModule
0x180001dc6  lea     rdx, ModuleName; "webengine4.dll"
0x180001dcd  call    cs:__imp_GetModuleHandleExW
0x180001dd3  test    eax, eax
0x180001dd5  jnz     short loc_180001DEF
0x180001dd7  xor     edx, edx; hFile
0x180001dd9  lea     r8d, [rax+8]; dwFlags
0x180001ddd  lea     rcx, LibFileName; "webengine.dll"
0x180001de4  call    cs:__imp_LoadLibraryExW
0x180001dea  mov     [rdi], rax
0x180001ded  jmp     short loc_180001E08
0x180001def  mov     rax, [rdi]
0x180001df2  jmp     short loc_180001E08
0x180001df4  mov     rcx, [rbp+410h+lpLibFileName]; lpLibFileName
0x180001df8  xor     edx, edx; hFile
0x180001dfa  lea     r8d, [rdx+8]; dwFlags
0x180001dfe  call    cs:__imp_LoadLibraryExW
0x180001e04  mov     [rbx+38h], rax
0x180001e08  test    rax, rax
0x180001e0b  jnz     short loc_180001E74
0x180001e0d  call    cs:__imp_GetLastError
0x180001e13  mov     edi, eax
0x180001e15  test    eax, eax
0x180001e17  jle     short loc_180001E22
0x180001e19  movzx   edi, ax
0x180001e1c  or      edi, 80070000h
0x180001e22  test    cs:g_dwDebugFlags, 0Fh
0x180001e29  jz      loc_180002047
0x180001e2f  mov     rbx, [rbp+410h+lpLibFileName]
0x180001e33  call    cs:__imp_GetLastError
0x180001e39  lea     rcx, aErrorLoadingAs; "Error loading aspnet_isapi service dll "...
0x180001e40  mov     [rsp+510h+var_4E0], rbx
0x180001e45  mov     r8d, 659h
0x180001e4b  mov     [rsp+510h+var_4E8], rcx
0x180001e50  lea     r9, aWebhostProtoco_1; "WEBHOST_PROTOCOL_MANAGER::GetPMHFromISA"...
0x180001e57  mov     rcx, cs:g_pDebug
0x180001e5e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180001e65  mov     dword ptr [rsp+510h+var_4F0], eax
0x180001e69  call    cs:__imp_PuDbgPrintError
0x180001e6f  jmp     loc_180002047
0x180001e74  lea     rsi, ProcName; "GetIsapiProcessHost"
0x180001e7b  mov     rcx, rax; hModule
0x180001e7e  mov     rdx, rsi; lpProcName
0x180001e81  call    cs:__imp_GetProcAddress
0x180001e87  test    rax, rax
0x180001e8a  jnz     short loc_180001EC8
0x180001e8c  call    cs:__imp_GetLastError
0x180001e92  mov     edi, eax
0x180001e94  test    eax, eax
0x180001e96  jle     short loc_180001EA1
0x180001e98  movzx   edi, ax
0x180001e9b  or      edi, 80070000h
0x180001ea1  test    cs:g_dwDebugFlags, 0Fh
0x180001ea8  jz      loc_180002047
0x180001eae  call    cs:__imp_GetLastError
0x180001eb4  lea     rcx, aCouldNotFindEn; "Could not find entry point '%s'.\n"
0x180001ebb  mov     [rsp+510h+var_4E0], rsi
0x180001ec0  mov     r8d, 668h
0x180001ec6  jmp     short loc_180001E4B
0x180001ec8  mov     rcx, [rbx+68h]
0x180001ecc  lea     rsi, [rbx+48h]
0x180001ed0  mov     rdx, rsi
0x180001ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ed8  mov     edi, eax
0x180001eda  test    eax, eax
0x180001edc  jns     short loc_180001EFD
0x180001ede  test    cs:g_dwDebugFlags, 0Fh
0x180001ee5  jz      loc_180002047
0x180001eeb  lea     rax, aErrorGettingTh_1; "Error getting the process host manager."...
0x180001ef2  mov     r8d, 673h
0x180001ef8  jmp     loc_180001D8E
0x180001efd  mov     rcx, [rsi]
0x180001f00  lea     r8, [rbx+50h]
0x180001f04  lea     rdx, _GUID_1cc9099d_0a8d_41cb_87d6_845e4f8c4e91
0x180001f0b  mov     rax, [rcx]
0x180001f0e  mov     rax, [rax]
0x180001f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f16  mov     edi, eax
0x180001f18  test    eax, eax
0x180001f1a  jns     short loc_180001F3F
0x180001f1c  test    cs:g_dwDebugFlags, 3
0x180001f23  jz      loc_180002047
0x180001f29  mov     dword ptr [rsp+510h+var_4E8], eax
0x180001f2d  mov     r8d, 68Ah
0x180001f33  lea     rax, aErrorGettingTh_2; "Error getting the process host manager "...
0x180001f3a  jmp     loc_180002027
0x180001f3f  mov     rcx, [rsi]
0x180001f42  lea     r8, [rbx+58h]
0x180001f46  lea     rdx, _GUID_9d98b251_453e_44f6_9cec_8b5aed970129
0x180001f4d  mov     rax, [rcx]
0x180001f50  mov     rax, [rax]
0x180001f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f58  mov     edi, eax
0x180001f5a  test    eax, eax
0x180001f5c  jns     short loc_180001F81
0x180001f5e  test    cs:g_dwDebugFlags, 3
0x180001f65  jz      loc_180002047
0x180001f6b  mov     dword ptr [rsp+510h+var_4E8], eax
0x180001f6f  mov     r8d, 69Bh
0x180001f75  lea     rax, aErrorGettingTh_0; "Error getting the process host manager "...
0x180001f7c  jmp     loc_180002027
0x180001f81  mov     rcx, [rsi]
0x180001f84  lea     rdx, _GUID_ae54f424_71bc_4da5_aa2f_8c0cd53496fc
0x180001f8b  lea     rsi, [rbx+70h]
0x180001f8f  mov     r8, rsi
0x180001f92  mov     rax, [rcx]
0x180001f95  mov     rax, [rax]
0x180001f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f9d  mov     edi, eax
0x180001f9f  test    eax, eax
0x180001fa1  jns     short loc_180001FE2
0x180001fa3  test    cs:g_dwDebugFlags, 3
0x180001faa  jz      short loc_180001FDD
0x180001fac  mov     rcx, cs:g_pDebug
0x180001fb3  lea     r9, aWebhostProtoco_1; "WEBHOST_PROTOCOL_MANAGER::GetPMHFromISA"...
0x180001fba  mov     dword ptr [rsp+510h+var_4E8], eax
0x180001fbe  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180001fc5  lea     rax, aUnableToRetrie; "Unable to retrieve IApplicationPreloadM"...
0x180001fcc  mov     r8d, 6AEh
0x180001fd2  mov     [rsp+510h+var_4F0], rax
0x180001fd7  call    cs:__imp_PuDbgPrint
0x180001fdd  xor     edi, edi
0x180001fdf  mov     [rsi], rdi
0x180001fe2  mov     rcx, [rsi]
0x180001fe5  test    rcx, rcx
0x180001fe8  jz      short loc_180002047
0x180001fea  mov     rdx, [rbx+68h]
0x180001fee  mov     r8, [rcx]
0x180001ff1  lea     rax, [rdx+8]
0x180001ff5  neg     rdx
0x180001ff8  sbb     rdx, rdx
0x180001ffb  and     rdx, rax
0x180001ffe  mov     rax, [r8+18h]
0x180002002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002007  mov     edi, eax
0x180002009  test    eax, eax
0x18000200b  jns     short loc_180002047
0x18000200d  test    cs:g_dwDebugFlags, 3
0x180002014  jz      short loc_180002047
0x180002016  mov     dword ptr [rsp+510h+var_4E8], eax
0x18000201a  mov     r8d, 6BEh
0x180002020  lea     rax, aUnableToSetThe; "Unable to set the IApplicationPreloadUt"...
0x180002027  mov     rcx, cs:g_pDebug
0x18000202e  lea     r9, aWebhostProtoco_1; "WEBHOST_PROTOCOL_MANAGER::GetPMHFromISA"...
0x180002035  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000203c  mov     [rsp+510h+var_4F0], rax
0x180002041  call    cs:__imp_PuDbgPrint
0x180002047  lea     rcx, [rbp+410h+var_488]
0x18000204b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002051  mov     eax, edi
0x180002053  mov     rcx, [rbp+410h+var_30]
0x18000205a  xor     rcx, rsp; StackCookie
0x18000205d  call    __security_check_cookie
0x180002062  add     rsp, 4F8h
0x180002069  pop     rdi
0x18000206a  pop     rsi
0x18000206b  pop     rbx
0x18000206c  pop     rbp
0x18000206d  retn
```
