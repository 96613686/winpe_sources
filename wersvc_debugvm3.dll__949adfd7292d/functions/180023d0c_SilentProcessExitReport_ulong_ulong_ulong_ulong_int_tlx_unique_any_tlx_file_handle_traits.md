# SilentProcessExitReport(ulong,ulong,ulong,ulong,int,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180023d0c`
- end: `0x1800243a3`
- name: `?SilentProcessExitReport@@YAJKKKKHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `1687`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18001a410`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180006134`
- `0x180006aa8`
- `0x180007cf8`
- `0x18000f528`
- `0x180011ef8`
- `0x180012004`
- `0x18001fb94`
- `0x180023d0c`
- `0x18002f04c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023f00`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023f19`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023f00`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023f19`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180024011`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180024011`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800241a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800241a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800241d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800241d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002433a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002433a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023f9e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023f9e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180023dfe`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180023dfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002434e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024364`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024378`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002434e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024364`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024378`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800241c7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800241c7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180023dcf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800240e2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180023dcf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800240e2`
- `ntdll!wcsrchr` at `0x180023e5e`
- `ntdll!wcsrchr` at `0x180023e5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SilentProcessExitReport(unsigned int a1, DWORD a2, DWORD a3, int a4, int a5, __int64 a6)
{
  wchar_t *v10; // rsi
  HANDLE v11; // rax
  signed int v12; // eax
  signed int IFEOKeyForProcessId; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  wchar_t *v16; // rax
  WCHAR *p_ExeName; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  WCHAR *v20; // r8
  WCHAR v21; // r9
  WCHAR *v22; // rcx
  signed int v23; // eax
  __int64 v24; // r9
  wchar_t v25; // ax
  unsigned int ForceNativeDumpById; // eax
  unsigned __int16 v27; // cx
  signed int v28; // eax
  HANDLE *v29; // rbx
  HANDLE v30; // rdi
  HANDLE CurrentProcess; // rax
  signed int v32; // eax
  signed int v33; // eax
  signed int LastError; // eax
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  PVOID pvData; // [rsp+28h] [rbp-D8h]
  LPDWORD pcbData; // [rsp+30h] [rbp-D0h]
  DWORD v39; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v40; // [rsp+44h] [rbp-BCh] BYREF
  DWORD dwSize; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h]
  HANDLE hSourceHandle; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *EndPtr; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v45; // [rsp+68h] [rbp-98h]
  HANDLE hObject; // [rsp+70h] [rbp-90h]
  wchar_t String[8]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v48; // [rsp+88h] [rbp-78h]
  __int16 v49; // [rsp+90h] [rbp-70h] BYREF
  char v50[526]; // [rsp+92h] [rbp-6Eh] BYREF
  WCHAR ExeName; // [rsp+2A0h] [rbp+1A0h] BYREF
  char v52[526]; // [rsp+2A2h] [rbp+1A2h] BYREF
  wchar_t v53; // [rsp+4B0h] [rbp+3B0h] BYREF
  char v54[526]; // [rsp+4B2h] [rbp+3B2h] BYREF

  v10 = 0;
  hSourceHandle = 0;
  v53 = 0;
  memset_0(v54, 0, 0x206u);
  ExeName = 0;
  memset_0(v52, 0, 0x206u);
  v49 = 0;
  memset_0(v50, 0, 0x206u);
  dwSize = 260;
  v39 = 0;
  hkey = 0;
  v40 = 0;
  *(_OWORD *)String = 0;
  v48 = 0;
  v11 = OpenProcess(0x400u, 0, a3);
  hObject = v11;
  v45 = (unsigned __int64)v11 + 1;
  if ( (unsigned __int64)v11 + 1 <= 1 )
  {
    LastError = GetLastError();
    IFEOKeyForProcessId = LastError;
    if ( LastError > 0 )
      IFEOKeyForProcessId = (unsigned __int16)LastError | 0x80070000;
    if ( IFEOKeyForProcessId >= 0 )
      IFEOKeyForProcessId = -2147467259;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 66;
      goto LABEL_89;
    }
  }
  else if ( QueryFullProcessImageNameW(v11, 0, &ExeName, &dwSize) )
  {
    v16 = wcsrchr(&ExeName, 0x5Cu);
    if ( v16 )
      p_ExeName = v16 + 1;
    else
      p_ExeName = &ExeName;
    v18 = 2147483646;
    v19 = 260;
    v20 = (WCHAR *)&v49;
    do
    {
      if ( !v18 )
        break;
      v21 = *p_ExeName;
      if ( !*p_ExeName )
        break;
      ++p_ExeName;
      *v20++ = v21;
      --v18;
      --v19;
    }
    while ( v19 );
    IFEOKeyForProcessId = v19 == 0 ? 0x8007007A : 0;
    v22 = v20 - 1;
    if ( v19 )
      v22 = v20;
    *v22 = 0;
    if ( v19 )
    {
      if ( !(unsigned int)_o__wcsicmp(&v49, L"werfault.exe") || !(unsigned int)_o__wcsicmp(&v49, L"werfaultsecure.exe") )
      {
        IFEOKeyForProcessId = -2147020579;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            69,
            (unsigned int)WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids,
            (unsigned int)&v49,
            221);
        goto LABEL_91;
      }
      IFEOKeyForProcessId = UtilGetIFEOKeyForProcessId(a3);
      if ( IFEOKeyForProcessId >= 0 )
      {
        v39 = 24;
        IFEOKeyForProcessId = 0;
        if ( RegGetValueW(hkey, 0, L"GlobalFlag", 0xFFFFu, &v40, String, &v39) )
        {
          v23 = GetLastError();
          IFEOKeyForProcessId = v23;
          if ( v23 > 0 )
            IFEOKeyForProcessId = (unsigned __int16)v23 | 0x80070000;
          if ( IFEOKeyForProcessId >= 0 )
            IFEOKeyForProcessId = -2147467259;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v15 = 71;
            goto LABEL_89;
          }
        }
        else
        {
          v24 = v40;
          if ( v40 == 1 )
          {
            EndPtr = 0;
            v25 = wcstol(String, &EndPtr, 0);
            if ( *EndPtr )
            {
              IFEOKeyForProcessId = -2147024883;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  72,
                  WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids,
                  String);
              goto LABEL_91;
            }
          }
          else
          {
            if ( v40 != 4 )
            {
              IFEOKeyForProcessId = -2147024883;
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v15 = 73;
LABEL_90:
                WPP_SF_d(v14[2], v15, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, v24);
                goto LABEL_91;
              }
              goto LABEL_91;
            }
            v25 = String[0];
          }
          if ( (v25 & 0x200) == 0 )
            goto LABEL_91;
          LODWORD(pcbData) = a4;
          LODWORD(pvData) = a3;
          LODWORD(pdwType) = a2;
          IFEOKeyForProcessId = StringCchPrintfW(
                                  &v53,
                                  0x104u,
                                  L"-s -t %u -i %u -e %u -c %u",
                                  a1,
                                  pdwType,
                                  pvData,
                                  pcbData);
          if ( IFEOKeyForProcessId >= 0 )
          {
            v10 = (wchar_t *)OpenProcess(0x440u, 0, a2);
            EndPtr = v10;
            if ( v10 == (wchar_t *)-1LL || (wchar_t *)((char *)v10 + 1) == (wchar_t *)1 )
            {
              v33 = GetLastError();
              IFEOKeyForProcessId = v33;
              if ( v33 > 0 )
                IFEOKeyForProcessId = (unsigned __int16)v33 | 0x80070000;
              if ( IFEOKeyForProcessId >= 0 )
                IFEOKeyForProcessId = -2147467259;
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v15 = 75;
                goto LABEL_89;
              }
            }
            else
            {
              ForceNativeDumpById = UtilGetForceNativeDumpById(a3);
              v27 = (a5 != 0 ? 9 : 1) | 0x20;
              if ( ForceNativeDumpById )
                v27 = a5 != 0 ? 9 : 1;
              if ( (int)CreateElevatedProcessAsUser(v10, (__int64)&v53, 0, 0, 0, &hSourceHandle, v27) >= 0 )
              {
                v29 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(a6);
                v30 = hSourceHandle;
                CurrentProcess = GetCurrentProcess();
                if ( DuplicateHandle(CurrentProcess, v30, v10, v29, 0x100000u, 0, 0) )
                {
                  IFEOKeyForProcessId = 0;
                  goto LABEL_91;
                }
                v32 = GetLastError();
                IFEOKeyForProcessId = v32;
                if ( v32 > 0 )
                  IFEOKeyForProcessId = (unsigned __int16)v32 | 0x80070000;
                if ( IFEOKeyForProcessId >= 0 )
                  IFEOKeyForProcessId = -2147467259;
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v15 = 77;
                  goto LABEL_89;
                }
              }
              else
              {
                v28 = GetLastError();
                IFEOKeyForProcessId = v28;
                if ( v28 > 0 )
                  IFEOKeyForProcessId = (unsigned __int16)v28 | 0x80070000;
                if ( IFEOKeyForProcessId >= 0 )
                  IFEOKeyForProcessId = -2147467259;
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v15 = 76;
                  goto LABEL_89;
                }
              }
            }
          }
          else
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v15 = 74;
              goto LABEL_89;
            }
          }
        }
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 70;
          goto LABEL_89;
        }
      }
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 68;
        goto LABEL_89;
      }
    }
  }
  else
  {
    v12 = GetLastError();
    IFEOKeyForProcessId = v12;
    if ( v12 > 0 )
      IFEOKeyForProcessId = (unsigned __int16)v12 | 0x80070000;
    if ( IFEOKeyForProcessId >= 0 )
      IFEOKeyForProcessId = -2147467259;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 67;
LABEL_89:
      v24 = (unsigned int)IFEOKeyForProcessId;
      goto LABEL_90;
    }
  }
LABEL_91:
  if ( hkey )
    RegCloseKey(hkey);
  if ( v45 > 1 )
    CloseHandle(hObject);
  if ( (unsigned __int64)hSourceHandle + 1 > 1 )
    CloseHandle(hSourceHandle);
  if ( (unsigned __int64)v10 + 1 > 1 )
    CloseHandle(v10);
  return (unsigned int)IFEOKeyForProcessId;
}

```

## disassembly

```asm
0x180023d0c  push    rbp
0x180023d0e  push    rbx
0x180023d0f  push    rsi
0x180023d10  push    rdi
0x180023d11  push    r12
0x180023d13  push    r13
0x180023d15  push    r14
0x180023d17  push    r15
0x180023d19  lea     rbp, [rsp-5D8h]
0x180023d21  sub     rsp, 6D8h
0x180023d28  mov     rax, cs:__security_cookie
0x180023d2f  xor     rax, rsp
0x180023d32  mov     [rbp+610h+var_50], rax
0x180023d39  mov     r12d, r9d
0x180023d3c  mov     edi, r8d
0x180023d3f  mov     r14d, edx
0x180023d42  mov     r15d, ecx
0x180023d45  mov     r13, [rbp+610h+arg_28]
0x180023d4c  xor     eax, eax
0x180023d4e  mov     esi, eax
0x180023d50  mov     [rsp+710h+hSourceHandle], rax
0x180023d55  mov     [rbp+610h+var_260], ax
0x180023d5c  mov     ebx, 206h
0x180023d61  mov     r8d, ebx; Size
0x180023d64  xor     edx, edx; Val
0x180023d66  lea     rcx, [rbp+610h+var_25E]; void *
0x180023d6d  call    memset_0
0x180023d72  xor     eax, eax
0x180023d74  mov     [rbp+610h+ExeName], ax
0x180023d7b  mov     r8d, ebx; Size
0x180023d7e  xor     edx, edx; Val
0x180023d80  lea     rcx, [rbp+610h+var_46E]; void *
0x180023d87  call    memset_0
0x180023d8c  xor     eax, eax
0x180023d8e  mov     [rbp+610h+var_680], ax
0x180023d92  mov     r8d, ebx; Size
0x180023d95  xor     edx, edx; Val
0x180023d97  lea     rcx, [rbp+610h+var_67E]; void *
0x180023d9b  call    memset_0
0x180023da0  mov     [rsp+710h+dwSize], 104h
0x180023da8  xor     ebx, ebx
0x180023daa  mov     [rsp+710h+var_6D0], ebx
0x180023dae  mov     [rsp+710h+hkey], rbx
0x180023db3  mov     [rsp+710h+var_6CC], ebx
0x180023db7  xorps   xmm0, xmm0
0x180023dba  xor     eax, eax
0x180023dbc  movups  xmmword ptr [rsp+710h+String], xmm0
0x180023dc1  mov     [rbp+610h+var_688], rax
0x180023dc5  mov     r8d, edi; dwProcessId
0x180023dc8  xor     edx, edx; bInheritHandle
0x180023dca  mov     ecx, 400h; dwDesiredAccess
0x180023dcf  call    cs:__imp_OpenProcess
0x180023dd5  mov     [rsp+710h+hObject], rax
0x180023dda  lea     rcx, [rax+1]
0x180023dde  mov     [rsp+710h+var_6A8], rcx
0x180023de3  cmp     rcx, 1
0x180023de7  jbe     loc_1800242DF
0x180023ded  lea     r9, [rsp+710h+dwSize]; lpdwSize
0x180023df2  lea     r8, [rbp+610h+ExeName]; lpExeName
0x180023df9  xor     edx, edx; dwFlags
0x180023dfb  mov     rcx, rax; hProcess
0x180023dfe  call    cs:__imp_QueryFullProcessImageNameW
0x180023e04  test    eax, eax
0x180023e06  jnz     short loc_180023E52
0x180023e08  call    cs:__imp_GetLastError
0x180023e0e  mov     ebx, eax
0x180023e10  test    eax, eax
0x180023e12  jle     short loc_180023E1D
0x180023e14  movzx   ebx, ax
0x180023e17  or      ebx, 80070000h
0x180023e1d  mov     eax, 80004005h
0x180023e22  test    ebx, ebx
0x180023e24  cmovns  ebx, eax
0x180023e27  lea     rax, WPP_GLOBAL_Control
0x180023e2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e35  cmp     rcx, rax
0x180023e38  jz      loc_180024330
0x180023e3e  test    byte ptr [rcx+1Ch], 1
0x180023e42  jz      loc_180024330
0x180023e48  mov     edx, 43h ; 'C'
0x180023e4d  jmp     loc_18002431C
0x180023e52  mov     edx, 5Ch ; '\'; Ch
0x180023e57  lea     rcx, [rbp+610h+ExeName]; Str
0x180023e5e  call    cs:__imp_wcsrchr
0x180023e64  test    rax, rax
0x180023e67  jz      short loc_180023E6F
0x180023e69  add     rax, 2
0x180023e6d  jmp     short loc_180023E76
0x180023e6f  lea     rax, [rbp+610h+ExeName]
0x180023e76  mov     ecx, 7FFFFFFEh
0x180023e7b  mov     edx, 104h
0x180023e80  lea     r8, [rbp+610h+var_680]
0x180023e84  test    rcx, rcx
0x180023e87  jz      short loc_180023EA8
0x180023e89  movzx   r9d, word ptr [rax]
0x180023e8d  test    r9w, r9w
0x180023e91  jz      short loc_180023EA8
0x180023e93  add     rax, 2
0x180023e97  mov     [r8], r9w
0x180023e9b  add     r8, 2
0x180023e9f  dec     rcx
0x180023ea2  sub     rdx, 1
0x180023ea6  jnz     short loc_180023E84
0x180023ea8  mov     rax, rdx
0x180023eab  neg     rax
0x180023eae  sbb     ebx, ebx
0x180023eb0  not     ebx
0x180023eb2  and     ebx, 8007007Ah
0x180023eb8  lea     rcx, [r8-2]
0x180023ebc  xor     eax, eax
0x180023ebe  test    rdx, rdx
0x180023ec1  cmovnz  rcx, r8
0x180023ec5  mov     [rcx], ax
0x180023ec8  jnz     short loc_180023EF5
0x180023eca  lea     rax, WPP_GLOBAL_Control
0x180023ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ed8  cmp     rcx, rax
0x180023edb  jz      loc_180024330
0x180023ee1  test    byte ptr [rcx+1Ch], 1
0x180023ee5  jz      loc_180024330
0x180023eeb  mov     edx, 44h ; 'D'
0x180023ef0  jmp     loc_18002431C
0x180023ef5  lea     rdx, aWerfaultExe_1; "werfault.exe"
0x180023efc  lea     rcx, [rbp+610h+var_680]
0x180023f00  call    cs:__imp__o__wcsicmp
0x180023f06  test    eax, eax
0x180023f08  jz      loc_18002429E
0x180023f0e  lea     rdx, aWerfaultsecure_0; "werfaultsecure.exe"
0x180023f15  lea     rcx, [rbp+610h+var_680]
0x180023f19  call    cs:__imp__o__wcsicmp
0x180023f1f  test    eax, eax
0x180023f21  jz      loc_18002429E
0x180023f27  lea     r9, [rsp+710h+hkey]
0x180023f2c  mov     ecx, edi; dwProcessId
0x180023f2e  call    ?UtilGetIFEOKeyForProcessId@@YAJKKKPEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; UtilGetIFEOKeyForProcessId(ulong,ulong,ulong,tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> *)
0x180023f33  mov     ebx, eax
0x180023f35  test    eax, eax
0x180023f37  jns     short loc_180023F64
0x180023f39  lea     rax, WPP_GLOBAL_Control
0x180023f40  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f47  cmp     rcx, rax
0x180023f4a  jz      loc_180024330
0x180023f50  test    byte ptr [rcx+1Ch], 1
0x180023f54  jz      loc_180024330
0x180023f5a  mov     edx, 46h ; 'F'
0x180023f5f  jmp     loc_18002431C
0x180023f64  mov     [rsp+710h+var_6D0], 18h
0x180023f6c  lea     rax, [rsp+710h+var_6D0]
0x180023f71  mov     [rsp+710h+pcbData], rax; pcbData
0x180023f76  lea     rax, [rsp+710h+String]
0x180023f7b  mov     [rsp+710h+pvData], rax; pvData
0x180023f80  lea     rax, [rsp+710h+var_6CC]
0x180023f85  mov     [rsp+710h+pdwType], rax; pdwType
0x180023f8a  mov     r9d, 0FFFFh; dwFlags
0x180023f90  lea     r8, aGlobalflag; "GlobalFlag"
0x180023f97  xor     edx, edx; lpSubKey
0x180023f99  mov     rcx, [rsp+710h+hkey]; hkey
0x180023f9e  call    cs:__imp_RegGetValueW
0x180023fa4  xor     ebx, ebx
0x180023fa6  test    eax, eax
0x180023fa8  jz      short loc_180023FF4
0x180023faa  call    cs:__imp_GetLastError
0x180023fb0  mov     ebx, eax
0x180023fb2  test    eax, eax
0x180023fb4  jle     short loc_180023FBF
0x180023fb6  movzx   ebx, ax
0x180023fb9  or      ebx, 80070000h
0x180023fbf  mov     eax, 80004005h
0x180023fc4  test    ebx, ebx
0x180023fc6  cmovns  ebx, eax
0x180023fc9  lea     rax, WPP_GLOBAL_Control
0x180023fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180023fd7  cmp     rcx, rax
0x180023fda  jz      loc_180024330
0x180023fe0  test    byte ptr [rcx+1Ch], 1
0x180023fe4  jz      loc_180024330
0x180023fea  mov     edx, 47h ; 'G'
0x180023fef  jmp     loc_18002431C
0x180023ff4  mov     r9d, [rsp+710h+var_6CC]
0x180023ff9  cmp     r9d, 1
0x180023ffd  jnz     short loc_180024066
0x180023fff  mov     [rsp+710h+EndPtr], rbx
0x180024004  xor     r8d, r8d; Radix
0x180024007  lea     rdx, [rsp+710h+EndPtr]; EndPtr
0x18002400c  lea     rcx, [rsp+710h+String]; String
0x180024011  call    cs:__imp_wcstol
0x180024017  mov     rcx, [rsp+710h+EndPtr]
0x18002401c  cmp     [rcx], bx
0x18002401f  jz      short loc_180024074
0x180024021  mov     ebx, 8007000Dh
0x180024026  lea     rax, WPP_GLOBAL_Control
0x18002402d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024034  cmp     rcx, rax
0x180024037  jz      loc_180024330
0x18002403d  test    byte ptr [rcx+1Ch], 1
0x180024041  jz      loc_180024330
0x180024047  mov     edx, 48h ; 'H'
0x18002404c  lea     r9, [rsp+710h+String]
0x180024051  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x180024058  mov     rcx, [rcx+10h]
0x18002405c  call    WPP_SF_S
0x180024061  jmp     loc_180024330
0x180024066  cmp     r9d, 4
0x18002406a  jnz     loc_18002426E
0x180024070  mov     eax, dword ptr [rsp+710h+String]
0x180024074  bt      eax, 9
0x180024078  jnb     loc_180024330
0x18002407e  mov     dword ptr [rsp+710h+pcbData], r12d
0x180024083  mov     dword ptr [rsp+710h+pvData], edi
0x180024087  mov     dword ptr [rsp+710h+pdwType], r14d
0x18002408c  mov     r9d, r15d
0x18002408f  lea     r8, aSTUIUEUCU; "-s -t %u -i %u -e %u -c %u"
0x180024096  mov     edx, 104h; unsigned __int64
0x18002409b  lea     rcx, [rbp+610h+var_260]; wchar_t *
0x1800240a2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800240a7  mov     ebx, eax
0x1800240a9  test    eax, eax
0x1800240ab  jns     short loc_1800240D8
0x1800240ad  lea     rax, WPP_GLOBAL_Control
0x1800240b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800240bb  cmp     rcx, rax
0x1800240be  jz      loc_180024330
0x1800240c4  test    byte ptr [rcx+1Ch], 1
0x1800240c8  jz      loc_180024330
0x1800240ce  mov     edx, 4Ah ; 'J'
0x1800240d3  jmp     loc_18002431C
0x1800240d8  mov     r8d, r14d; dwProcessId
0x1800240db  xor     edx, edx; bInheritHandle
0x1800240dd  mov     ecx, 440h; dwDesiredAccess
0x1800240e2  call    cs:__imp_OpenProcess
0x1800240e8  mov     rsi, rax
0x1800240eb  mov     [rsp+710h+EndPtr], rax
0x1800240f0  inc     rax
0x1800240f3  cmp     rax, 1
0x1800240f7  jbe     loc_180024224
0x1800240fd  neg     [rbp+610h+arg_20]
0x180024103  sbb     ebx, ebx
0x180024105  and     ebx, 8
0x180024108  inc     ebx
0x18002410a  mov     ecx, edi; unsigned int
0x18002410c  call    ?UtilGetForceNativeDumpById@@YAKK@Z; UtilGetForceNativeDumpById(ulong)
0x180024111  mov     ecx, ebx
0x180024113  or      ecx, 20h
0x180024116  xor     edi, edi
0x180024118  test    eax, eax
0x18002411a  cmovnz  ecx, ebx
0x18002411d  mov     dword ptr [rsp+710h+pcbData], ecx
0x180024121  lea     rcx, [rsp+710h+hSourceHandle]
0x180024126  mov     [rsp+710h+pvData], rcx
0x18002412b  mov     word ptr [rsp+710h+pdwType], di
0x180024130  xor     r9d, r9d
0x180024133  xor     r8d, r8d
0x180024136  lea     rdx, [rbp+610h+var_260]
0x18002413d  mov     rcx, rsi
0x180024140  call    ?CreateElevatedProcessAsUser@@YAJPEAXPEA_WPEAPEAXKGPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K@Z; CreateElevatedProcessAsUser(void *,wchar_t *,void * *,ulong,ushort,tlx::unique_any<tlx::file_handle_traits> *,ulong)
0x180024145  test    eax, eax
0x180024147  jns     short loc_180024193
0x180024149  call    cs:__imp_GetLastError
0x18002414f  mov     ebx, eax
0x180024151  test    eax, eax
0x180024153  jle     short loc_18002415E
0x180024155  movzx   ebx, ax
0x180024158  or      ebx, 80070000h
0x18002415e  mov     eax, 80004005h
0x180024163  test    ebx, ebx
0x180024165  cmovns  ebx, eax
0x180024168  lea     rax, WPP_GLOBAL_Control
0x18002416f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024176  cmp     rcx, rax
0x180024179  jz      loc_180024330
0x18002417f  test    byte ptr [rcx+1Ch], 1
0x180024183  jz      loc_180024330
0x180024189  mov     edx, 4Ch ; 'L'
0x18002418e  jmp     loc_18002431C
0x180024193  mov     rcx, r13
0x180024196  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18002419b  mov     rbx, rax
0x18002419e  mov     rdi, [rsp+710h+hSourceHandle]
0x1800241a3  call    cs:__imp_GetCurrentProcess
0x1800241a9  xor     ecx, ecx
0x1800241ab  mov     dword ptr [rsp+710h+pcbData], ecx; dwOptions
0x1800241af  mov     dword ptr [rsp+710h+pvData], ecx; bInheritHandle
0x1800241b3  mov     dword ptr [rsp+710h+pdwType], 100000h; dwDesiredAccess
0x1800241bb  mov     r9, rbx; lpTargetHandle
0x1800241be  mov     r8, rsi; hTargetProcessHandle
0x1800241c1  mov     rdx, rdi; hSourceHandle
0x1800241c4  mov     rcx, rax; hSourceProcessHandle
0x1800241c7  call    cs:__imp_DuplicateHandle
0x1800241cd  xor     ecx, ecx
0x1800241cf  test    eax, eax
0x1800241d1  jnz     short loc_18002421D
0x1800241d3  call    cs:__imp_GetLastError
0x1800241d9  mov     ebx, eax
0x1800241db  test    eax, eax
0x1800241dd  jle     short loc_1800241E8
0x1800241df  movzx   ebx, ax
0x1800241e2  or      ebx, 80070000h
0x1800241e8  mov     eax, 80004005h
0x1800241ed  test    ebx, ebx
0x1800241ef  cmovns  ebx, eax
  ... truncated ...
```
