# WdcModuleMonitor::AddProcessModules(ulong)

- ea: `0x180029a78`
- end: `0x18002a093`
- name: `?AddProcessModules@WdcModuleMonitor@@AEAAJK@Z`
- size: `1563`
- prototype: `__int64 __fastcall(WdcModuleMonitor *this, const char *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180082230`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18000ff88`
- `0x180015060`
- `0x180029a78`
- `0x18002e440`
- `0x180039134`
- `0x18003a3c0`
- `0x18008200c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002a025`
- `KERNEL32!CloseHandle` at `0x18002a025`
- `KERNEL32!GetLastError` at `0x180029aee`
- `KERNEL32!GetLastError` at `0x180029b96`
- `KERNEL32!GetLastError` at `0x180029c87`
- `KERNEL32!GetLastError` at `0x180029cc1`
- `KERNEL32!GetLastError` at `0x180029f54`
- `KERNEL32!GetLastError` at `0x180029f8d`
- `KERNEL32!GetLastError` at `0x180029aee`
- `KERNEL32!GetLastError` at `0x180029b96`
- `KERNEL32!GetLastError` at `0x180029c87`
- `KERNEL32!GetLastError` at `0x180029cc1`
- `KERNEL32!GetLastError` at `0x180029f54`
- `KERNEL32!GetLastError` at `0x180029f8d`
- `KERNEL32!OpenProcess` at `0x180029ae0`
- `KERNEL32!OpenProcess` at `0x180029ae0`
- `KERNEL32!K32EnumDeviceDrivers` at `0x180029b88`
- `KERNEL32!K32EnumDeviceDrivers` at `0x180029b88`
- `KERNEL32!K32EnumProcessModulesEx` at `0x180029c1f`
- `KERNEL32!K32EnumProcessModulesEx` at `0x180029c1f`
- `KERNEL32!K32GetDeviceDriverBaseNameW` at `0x180029c7d`
- `KERNEL32!K32GetDeviceDriverBaseNameW` at `0x180029c7d`
- `KERNEL32!K32GetDeviceDriverFileNameW` at `0x180029cb7`
- `KERNEL32!K32GetDeviceDriverFileNameW` at `0x180029cb7`
- `KERNEL32!K32GetModuleBaseNameW` at `0x180029f4a`
- `KERNEL32!K32GetModuleBaseNameW` at `0x180029f4a`
- `KERNEL32!K32GetModuleFileNameExW` at `0x180029f7f`
- `KERNEL32!K32GetModuleFileNameExW` at `0x180029f7f`
- `OLEAUT32!__imp_SysAllocString` at `0x180029e07`
- `OLEAUT32!__imp_SysAllocString` at `0x180029e78`
- `OLEAUT32!__imp_SysAllocString` at `0x180029ed9`
- `OLEAUT32!__imp_SysAllocString` at `0x180029e07`
- `OLEAUT32!__imp_SysAllocString` at `0x180029e78`
- `OLEAUT32!__imp_SysAllocString` at `0x180029ed9`
- `OLEAUT32!__imp_SysFreeString` at `0x180029df3`
- `OLEAUT32!__imp_SysFreeString` at `0x180029e62`
- `OLEAUT32!__imp_SysFreeString` at `0x180029ec5`
- `OLEAUT32!__imp_SysFreeString` at `0x180029df3`
- `OLEAUT32!__imp_SysFreeString` at `0x180029e62`
- `OLEAUT32!__imp_SysFreeString` at `0x180029ec5`

## pseudocode

```c
__int64 __fastcall WdcModuleMonitor::AddProcessModules(WdcModuleMonitor *this, const char *a2, int a3)
{
  int v3; // ebp
  signed int v4; // ebx
  char *v5; // r13
  char *v6; // rax
  signed int LastError; // eax
  void *v8; // rsi
  void *v9; // r14
  WCHAR *v10; // r12
  DWORD v11; // eax
  WCHAR *v12; // r15
  SIZE_T v13; // rdi
  BOOL v14; // eax
  signed int v15; // eax
  int v16; // esi
  const char *v17; // rdx
  int v18; // r8d
  const char *v19; // rdx
  int v20; // r8d
  __int64 i; // rcx
  __int64 v22; // rdi
  signed int v23; // eax
  signed int v24; // eax
  unsigned int v25; // edi
  WdcModuleMonitor *v26; // rcx
  int v27; // eax
  WdcModuleMonitor *v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rax
  struct _WDC_MODULE_INFO *v31; // rdi
  char **v32; // r14
  int v33; // eax
  char *v34; // rbp
  char ***v35; // rax
  __int64 v36; // rcx
  _WORD *v37; // rcx
  int ImageName; // eax
  char ***v39; // rax
  __int64 v40; // rcx
  OLECHAR *v41; // rcx
  BSTR v42; // rax
  unsigned int v43; // r8d
  char ***v44; // rax
  __int64 v45; // rcx
  OLECHAR *v46; // rcx
  BSTR v47; // rax
  char ***v48; // rax
  __int64 v49; // rcx
  OLECHAR *v50; // rcx
  BSTR v51; // rax
  char ***v52; // rax
  __int64 v53; // rcx
  HMODULE *v54; // r14
  signed int v55; // eax
  signed int v56; // eax
  __int64 dwFilterFlag; // [rsp+20h] [rbp-C8h]
  DWORD cbNeeded; // [rsp+30h] [rbp-B8h] BYREF
  unsigned int v60; // [rsp+34h] [rbp-B4h]
  int v61; // [rsp+38h] [rbp-B0h]
  void *v62; // [rsp+40h] [rbp-A8h]
  void *v63; // [rsp+48h] [rbp-A0h]
  struct _WDC_MODULE_INFO *v64; // [rsp+50h] [rbp-98h] BYREF
  WdcModuleMonitor *v65; // [rsp+58h] [rbp-90h]
  OLECHAR psz[32]; // [rsp+60h] [rbp-88h] BYREF

  v60 = (unsigned int)a2;
  v3 = (int)a2;
  v65 = this;
  cbNeeded = 0;
  v64 = 0;
  if ( (_DWORD)a2 == 1 )
    return 0;
  v5 = 0;
  if ( (_DWORD)a2 == 4 )
    goto LABEL_13;
  v6 = (char *)OpenProcess(0x410u, 0, (DWORD)a2);
  v5 = v6;
  if ( v6 )
  {
    if ( v6 != (char *)-1LL )
      goto LABEL_13;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( !LastError )
  {
    v4 = -2147467259;
LABEL_11:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\module.cpp",
      "WdcModuleMonitor::AddProcessModules",
      0,
      L"FAILURE: 0x%08x",
      v4);
    return (unsigned int)v4;
  }
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 < 0 )
    goto LABEL_11;
LABEL_13:
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v62 = 0;
  v11 = 1024;
  v63 = 0;
  v12 = 0;
  cbNeeded = 1024;
  do
  {
    v13 = v11;
    if ( v3 == 4 )
    {
      if ( v9 )
        WdcFree(v9, a2, a3);
      v63 = WdcAlloc(v13, a2, a3);
      v9 = v63;
      v14 = K32EnumDeviceDrivers((LPVOID *)v63, v13, &cbNeeded);
    }
    else
    {
      if ( v8 )
        WdcFree(v8, a2, a3);
      v62 = WdcAlloc(v13, a2, a3);
      v8 = v62;
      v14 = K32EnumProcessModulesEx(v5, (HMODULE *)v62, v13, &cbNeeded, 3u);
    }
    if ( v14 )
    {
      v4 = 0;
    }
    else
    {
      v15 = GetLastError();
      v4 = v15;
      if ( !v15 )
      {
        v16 = -2147467259;
        v4 = -2147467259;
LABEL_96:
        LODWORD(dwFilterFlag) = v16;
        goto LABEL_97;
      }
      if ( v15 > 0 )
        v4 = (unsigned __int16)v15 | 0x80070000;
      v16 = v4;
      if ( v4 < 0 )
        goto LABEL_96;
      v8 = v62;
    }
    v11 = cbNeeded;
  }
  while ( (unsigned int)v13 < cbNeeded );
  v10 = (WCHAR *)WdcAlloc(0x800u, a2, a3);
  if ( v10 )
  {
    *v10 = 0;
    v12 = (WCHAR *)WdcAlloc(0x800u, v17, v18);
    if ( v12 )
    {
      *v12 = 0;
      for ( i = 0; ; i = (unsigned int)(v61 + 1) )
      {
        v61 = i;
        if ( (unsigned int)i >= cbNeeded >> 3 )
          goto LABEL_98;
        v22 = (unsigned int)i;
        if ( v3 == 4 )
        {
          if ( K32GetDeviceDriverBaseNameW(*((LPVOID *)v9 + i), v10, 0x400u) )
            goto LABEL_44;
          v23 = GetLastError();
          v4 = v23;
          if ( !v23 )
            goto LABEL_91;
          if ( v23 > 0 )
            v4 = (unsigned __int16)v23 | 0x80070000;
          if ( v4 >= 0 )
          {
LABEL_44:
            if ( K32GetDeviceDriverFileNameW(*((LPVOID *)v9 + v22), v12, 0x400u) )
              goto LABEL_45;
            v24 = GetLastError();
            v4 = v24;
            if ( !v24 )
              goto LABEL_91;
            if ( v24 > 0 )
              v4 = (unsigned __int16)v24 | 0x80070000;
            if ( v4 >= 0 )
            {
LABEL_45:
              WdcFixDeviceDriverFileName(v12, (unsigned int)v19);
LABEL_46:
              v25 = WdcHashString(v10);
              v27 = WdcModuleMonitor::CreateEntry(v26, &v64);
              v4 = v27;
              if ( v27 < 0 )
              {
                LODWORD(dwFilterFlag) = v27;
                goto LABEL_97;
              }
              v28 = v65;
              v29 = (__int64)v65 + 16 * (v25 % 0x1F7) + 104;
              v30 = *(_QWORD *)v29;
              if ( *(_QWORD *)(*(_QWORD *)v29 + 8LL) != v29 )
                goto LABEL_93;
              v31 = v64;
              *(_QWORD *)v64 = v30;
              v32 = (char **)((char *)v31 + 16);
              *((_QWORD *)v31 + 1) = v29;
              *(_QWORD *)(v30 + 8) = v31;
              *(_QWORD *)v29 = v31;
              v33 = v3;
              v34 = (char *)v31 + 16;
              *((double *)v31 + 14) = (double)v33;
              *((_DWORD *)v31 + 26) |= 1u;
              if ( *((struct _WDC_MODULE_INFO **)v31 + 2) == (struct _WDC_MODULE_INFO *)((char *)v31 + 16) )
              {
                v35 = (char ***)((char *)v28 + 88);
                v36 = *((_QWORD *)v28 + 11);
                if ( *(WdcModuleMonitor **)(v36 + 8) != (WdcModuleMonitor *)((char *)v28 + 88) )
                  goto LABEL_93;
                *v32 = (char *)v36;
                *((_QWORD *)v31 + 3) = v35;
                *(_QWORD *)(v36 + 8) = v32;
                *v35 = v32;
              }
              v37 = (_WORD *)*((_QWORD *)v31 + 12);
              if ( !v37 || !*v37 )
              {
                ImageName = WdcTraceControl::GetImageName(
                              *((WdcTraceControl **)v28 + 1019),
                              v60,
                              (unsigned __int16 **)v31 + 12,
                              1);
                if ( ImageName >= 0 && ImageName != 1 )
                {
                  *((_DWORD *)v31 + 22) |= 1u;
                  if ( *v32 == v34 )
                  {
                    v39 = (char ***)((char *)v28 + 88);
                    v40 = *((_QWORD *)v28 + 11);
                    if ( *(WdcModuleMonitor **)(v40 + 8) != (WdcModuleMonitor *)((char *)v28 + 88) )
                      goto LABEL_93;
                    *v32 = (char *)v40;
                    *((_QWORD *)v31 + 3) = v39;
                    *(_QWORD *)(v40 + 8) = v32;
                    *v39 = v32;
                  }
                }
              }
              v41 = (OLECHAR *)*((_QWORD *)v31 + 16);
              if ( v41 )
              {
                SysFreeString(v41);
                *((_QWORD *)v31 + 16) = 0;
              }
              v42 = SysAllocString(v10);
              if ( !v42 )
                goto LABEL_92;
              *((_QWORD *)v31 + 16) = v42;
              *((_DWORD *)v31 + 30) |= 1u;
              if ( *v32 == v34 )
              {
                v44 = (char ***)((char *)v28 + 88);
                v45 = *((_QWORD *)v28 + 11);
                if ( *(WdcModuleMonitor **)(v45 + 8) != (WdcModuleMonitor *)((char *)v28 + 88) )
                  goto LABEL_93;
                *v32 = (char *)v45;
                *((_QWORD *)v31 + 3) = v44;
                *(_QWORD *)(v45 + 8) = v32;
                *v44 = v32;
              }
              if ( (int)WdcGetFileVersionString(v12, psz, v43) >= 0 )
              {
                v46 = (OLECHAR *)*((_QWORD *)v31 + 18);
                if ( v46 )
                {
                  SysFreeString(v46);
                  *((_QWORD *)v31 + 18) = 0;
                }
                v47 = SysAllocString(psz);
                if ( !v47 )
                  goto LABEL_92;
                *((_QWORD *)v31 + 18) = v47;
              }
              *((_DWORD *)v31 + 34) |= 1u;
              if ( *v32 == v34 )
              {
                v48 = (char ***)((char *)v28 + 88);
                v49 = *((_QWORD *)v28 + 11);
                if ( *(WdcModuleMonitor **)(v49 + 8) != (WdcModuleMonitor *)((char *)v28 + 88) )
                  goto LABEL_93;
                *v32 = (char *)v49;
                *((_QWORD *)v31 + 3) = v48;
                *(_QWORD *)(v49 + 8) = v32;
                *v48 = v32;
              }
              v50 = (OLECHAR *)*((_QWORD *)v31 + 20);
              if ( v50 )
              {
                SysFreeString(v50);
                *((_QWORD *)v31 + 20) = 0;
              }
              v51 = SysAllocString(v12);
              if ( !v51 )
              {
LABEL_92:
                LODWORD(dwFilterFlag) = -2147024882;
                WdcDebugMessage(
                  "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
                  "WdcAssignString",
                  0,
                  L"FAILURE: 0x%08x",
                  dwFilterFlag);
                break;
              }
              *((_QWORD *)v31 + 20) = v51;
              *((_DWORD *)v31 + 38) |= 1u;
              v4 = 0;
              if ( *v32 == v34 )
              {
                v52 = (char ***)((char *)v65 + 88);
                v53 = *((_QWORD *)v65 + 11);
                if ( *(WdcModuleMonitor **)(v53 + 8) != (WdcModuleMonitor *)((char *)v65 + 88) )
LABEL_93:
                  __fastfail(3u);
                *v32 = (char *)v53;
                *((_QWORD *)v31 + 3) = v52;
                *(_QWORD *)(v53 + 8) = v32;
                *v52 = v32;
              }
              v3 = v60;
            }
          }
        }
        else
        {
          v54 = (HMODULE *)v62;
          if ( K32GetModuleBaseNameW(v5, *((HMODULE *)v62 + i), v10, 0x400u) )
            goto LABEL_89;
          v55 = GetLastError();
          v4 = v55;
          if ( !v55 )
            goto LABEL_91;
          if ( v55 > 0 )
            v4 = (unsigned __int16)v55 | 0x80070000;
          if ( v4 >= 0 )
          {
LABEL_89:
            if ( K32GetModuleFileNameExW(v5, v54[v22], v12, 0x400u) )
              goto LABEL_46;
            v56 = GetLastError();
            v4 = v56;
            if ( !v56 )
            {
LABEL_91:
              v4 = -2147467259;
              goto LABEL_79;
            }
            if ( v56 > 0 )
              v4 = (unsigned __int16)v56 | 0x80070000;
            if ( v4 >= 0 )
              goto LABEL_46;
          }
        }
LABEL_79:
        v9 = v63;
      }
    }
  }
  v4 = -2147024882;
  LODWORD(dwFilterFlag) = -2147024882;
LABEL_97:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\module.cpp",
    "WdcModuleMonitor::AddProcessModules",
    0,
    L"FAILURE: 0x%08x",
    dwFilterFlag);
LABEL_98:
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  if ( v62 )
    WdcFree(v62, v19, v20);
  if ( v63 )
    WdcFree(v63, v19, v20);
  if ( v10 )
    WdcFree(v10, v19, v20);
  if ( v12 )
    WdcFree(v12, v19, v20);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180029a78  mov     [rsp+arg_10], rbx
0x180029a7d  push    rbp
0x180029a7e  push    rsi
0x180029a7f  push    rdi
0x180029a80  push    r12
0x180029a82  push    r13
0x180029a84  push    r14
0x180029a86  push    r15
0x180029a88  sub     rsp, 0B0h
0x180029a8f  mov     rax, cs:__security_cookie
0x180029a96  xor     rax, rsp
0x180029a99  mov     [rsp+0E8h+var_48], rax
0x180029aa1  mov     dword ptr [rsp+0E8h+var_B4], edx
0x180029aa5  mov     ebp, edx
0x180029aa7  mov     [rsp+0E8h+var_90], rcx
0x180029aac  mov     [rsp+0E8h+cbNeeded], 0
0x180029ab4  mov     [rsp+0E8h+var_98], 0
0x180029abd  cmp     edx, 1
0x180029ac0  jnz     short loc_180029AC9
0x180029ac2  xor     ebx, ebx
0x180029ac4  jmp     loc_18002A066
0x180029ac9  xor     r13d, r13d
0x180029acc  mov     edi, 80070000h
0x180029ad1  cmp     ebp, 4
0x180029ad4  jz      short loc_180029B38
0x180029ad6  mov     r8d, ebp; dwProcessId
0x180029ad9  xor     edx, edx; bInheritHandle
0x180029adb  mov     ecx, 410h; dwDesiredAccess
0x180029ae0  call    cs:__imp_OpenProcess
0x180029ae6  mov     r13, rax
0x180029ae9  test    rax, rax
0x180029aec  jnz     short loc_180029B32
0x180029aee  call    cs:__imp_GetLastError
0x180029af4  mov     ebx, eax
0x180029af6  test    eax, eax
0x180029af8  jz      short loc_180029B07
0x180029afa  jle     short loc_180029B01
0x180029afc  movzx   ebx, ax
0x180029aff  or      ebx, edi
0x180029b01  test    ebx, ebx
0x180029b03  jns     short loc_180029B38
0x180029b05  jmp     short loc_180029B0C
0x180029b07  mov     ebx, 80004005h
0x180029b0c  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180029b13  mov     [rsp+0E8h+dwFilterFlag], ebx
0x180029b17  xor     r8d, r8d; int
0x180029b1a  lea     rdx, aWdcmodulemonit_0; "WdcModuleMonitor::AddProcessModules"
0x180029b21  lea     rcx, aBaseDiagnosisP_44; "base\\diagnosis\\pdui\\perfmon\\mon\\mo"...
0x180029b28  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180029b2d  jmp     loc_18002A066
0x180029b32  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029b36  jz      short loc_180029AEE
0x180029b38  xor     esi, esi
0x180029b3a  xor     r14d, r14d
0x180029b3d  xor     r12d, r12d
0x180029b40  mov     [rsp+0E8h+var_A8], rsi
0x180029b45  mov     eax, 400h
0x180029b4a  mov     [rsp+0E8h+var_A0], r14
0x180029b4f  xor     r15d, r15d
0x180029b52  mov     [rsp+0E8h+cbNeeded], eax
0x180029b56  mov     edi, eax
0x180029b58  cmp     ebp, 4
0x180029b5b  jnz     loc_180029BEC
0x180029b61  test    r14, r14
0x180029b64  jz      short loc_180029B6E
0x180029b66  mov     rcx, r14; void *
0x180029b69  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180029b6e  mov     rcx, rdi; dwBytes
0x180029b71  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180029b76  lea     r8, [rsp+0E8h+cbNeeded]; lpcbNeeded
0x180029b7b  mov     [rsp+0E8h+var_A0], rax
0x180029b80  mov     edx, edi; cb
0x180029b82  mov     rcx, rax; lpImageBase
0x180029b85  mov     r14, rax
0x180029b88  call    cs:__imp_K32EnumDeviceDrivers
0x180029b8e  test    eax, eax
0x180029b90  jnz     loc_180029C2A
0x180029b96  call    cs:__imp_GetLastError
0x180029b9c  mov     ebx, eax
0x180029b9e  test    eax, eax
0x180029ba0  jz      loc_180029FF0
0x180029ba6  jle     short loc_180029BB1
0x180029ba8  movzx   ebx, ax
0x180029bab  or      ebx, 80070000h
0x180029bb1  mov     esi, ebx
0x180029bb3  test    ebx, ebx
0x180029bb5  js      loc_180029FF7
0x180029bbb  mov     rsi, [rsp+0E8h+var_A8]
0x180029bc0  mov     eax, [rsp+0E8h+cbNeeded]
0x180029bc4  cmp     edi, eax
0x180029bc6  jb      short loc_180029B56
0x180029bc8  mov     edi, 800h
0x180029bcd  mov     ecx, edi; dwBytes
0x180029bcf  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180029bd4  mov     r12, rax
0x180029bd7  test    rax, rax
0x180029bda  jnz     short loc_180029C2E
0x180029bdc  mov     edi, 8007000Eh
0x180029be1  mov     ebx, edi
0x180029be3  mov     [rsp+0E8h+dwFilterFlag], edi
0x180029be7  jmp     loc_180029FFB
0x180029bec  test    rsi, rsi
0x180029bef  jz      short loc_180029BF9
0x180029bf1  mov     rcx, rsi; void *
0x180029bf4  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180029bf9  mov     rcx, rdi; dwBytes
0x180029bfc  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180029c01  lea     r9, [rsp+0E8h+cbNeeded]; lpcbNeeded
0x180029c06  mov     [rsp+0E8h+var_A8], rax
0x180029c0b  mov     r8d, edi; cb
0x180029c0e  mov     [rsp+0E8h+dwFilterFlag], 3; dwFilterFlag
0x180029c16  mov     rdx, rax; lphModule
0x180029c19  mov     rcx, r13; hProcess
0x180029c1c  mov     rsi, rax
0x180029c1f  call    cs:__imp_K32EnumProcessModulesEx
0x180029c25  jmp     loc_180029B8E
0x180029c2a  xor     ebx, ebx
0x180029c2c  jmp     short loc_180029BC0
0x180029c2e  xor     eax, eax
0x180029c30  mov     rcx, rdi; dwBytes
0x180029c33  mov     [r12], ax
0x180029c38  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180029c3d  mov     r15, rax
0x180029c40  test    rax, rax
0x180029c43  jz      short loc_180029BDC
0x180029c45  xor     eax, eax
0x180029c47  mov     esi, 80004005h
0x180029c4c  mov     [r15], ax
0x180029c50  xor     ecx, ecx
0x180029c52  mov     eax, [rsp+0E8h+cbNeeded]
0x180029c56  shr     eax, 3
0x180029c59  mov     dword ptr [rsp+0E8h+var_B4+4], ecx
0x180029c5d  cmp     ecx, eax
0x180029c5f  jnb     loc_18002A018
0x180029c65  mov     edi, ecx
0x180029c67  cmp     ebp, 4
0x180029c6a  jnz     loc_180029F35
0x180029c70  mov     rcx, [r14+rcx*8]; ImageBase
0x180029c74  mov     r8d, 400h; nSize
0x180029c7a  mov     rdx, r12; lpBaseName
0x180029c7d  call    cs:__imp_K32GetDeviceDriverBaseNameW
0x180029c83  test    eax, eax
0x180029c85  jnz     short loc_180029CAA
0x180029c87  call    cs:__imp_GetLastError
0x180029c8d  mov     ebx, eax
0x180029c8f  test    eax, eax
0x180029c91  jz      loc_180029FB1
0x180029c97  jle     short loc_180029CA2
0x180029c99  movzx   ebx, ax
0x180029c9c  or      ebx, 80070000h
0x180029ca2  test    ebx, ebx
0x180029ca4  js      loc_180029F25
0x180029caa  mov     rcx, [r14+rdi*8]; ImageBase
0x180029cae  mov     r8d, 400h; nSize
0x180029cb4  mov     rdx, r15; lpFilename
0x180029cb7  call    cs:__imp_K32GetDeviceDriverFileNameW
0x180029cbd  test    eax, eax
0x180029cbf  jnz     short loc_180029CE4
0x180029cc1  call    cs:__imp_GetLastError
0x180029cc7  mov     ebx, eax
0x180029cc9  test    eax, eax
0x180029ccb  jz      loc_180029FB1
0x180029cd1  jle     short loc_180029CDC
0x180029cd3  movzx   ebx, ax
0x180029cd6  or      ebx, 80070000h
0x180029cdc  test    ebx, ebx
0x180029cde  js      loc_180029F25
0x180029ce4  mov     rcx, r15; Src
0x180029ce7  call    ?WdcFixDeviceDriverFileName@@YAJPEAGK@Z; WdcFixDeviceDriverFileName(ushort *,ulong)
0x180029cec  mov     rcx, r12; unsigned __int16 *
0x180029cef  call    ?WdcHashString@@YAKPEBG@Z; WdcHashString(ushort const *)
0x180029cf4  lea     rdx, [rsp+0E8h+var_98]; struct _WDC_MODULE_INFO **
0x180029cf9  mov     edi, eax
0x180029cfb  call    ?CreateEntry@WdcModuleMonitor@@AEAAJPEAPEAU_WDC_MODULE_INFO@@@Z; WdcModuleMonitor::CreateEntry(_WDC_MODULE_INFO * *)
0x180029d00  mov     ebx, eax
0x180029d02  test    eax, eax
0x180029d04  js      loc_180029FEA
0x180029d0a  mov     rbx, [rsp+0E8h+var_90]
0x180029d0f  mov     eax, 824A4E61h
0x180029d14  mul     edi
0x180029d16  lea     rcx, [rbx+68h]
0x180029d1a  shr     edx, 8
0x180029d1d  imul    eax, edx, 1F7h
0x180029d23  sub     edi, eax
0x180029d25  mov     eax, edi
0x180029d27  shl     rax, 4
0x180029d2b  add     rcx, rax
0x180029d2e  mov     rax, [rcx]
0x180029d31  cmp     [rax+8], rcx
0x180029d35  jnz     loc_180029FE3
0x180029d3b  mov     rdi, [rsp+0E8h+var_98]
0x180029d40  xorps   xmm0, xmm0
0x180029d43  mov     [rdi], rax
0x180029d46  lea     r14, [rdi+10h]
0x180029d4a  mov     [rdi+8], rcx
0x180029d4e  mov     [rax+8], rdi
0x180029d52  mov     [rcx], rdi
0x180029d55  mov     eax, ebp
0x180029d57  lea     rbp, [rdi+10h]
0x180029d5b  cvtsi2sd xmm0, rax
0x180029d60  movsd   qword ptr [rdi+70h], xmm0
0x180029d65  or      dword ptr [rdi+68h], 1
0x180029d69  cmp     [r14], rbp
0x180029d6c  jnz     short loc_180029D8D
0x180029d6e  lea     rax, [rbx+58h]
0x180029d72  mov     rcx, [rax]
0x180029d75  cmp     [rcx+8], rax
0x180029d79  jnz     loc_180029FE3
0x180029d7f  mov     [r14], rcx
0x180029d82  mov     [r14+8], rax
0x180029d86  mov     [rcx+8], r14
0x180029d8a  mov     [rax], r14
0x180029d8d  lea     r8, [rdi+60h]; unsigned __int16 **
0x180029d91  mov     rcx, [r8]
0x180029d94  test    rcx, rcx
0x180029d97  jz      short loc_180029DA0
0x180029d99  xor     eax, eax
0x180029d9b  cmp     ax, [rcx]
0x180029d9e  jnz     short loc_180029DE7
0x180029da0  mov     edx, dword ptr [rsp+0E8h+var_B4]; unsigned __int64
0x180029da4  mov     r9d, 1; int
0x180029daa  mov     rcx, [rbx+1FD8h]; this
0x180029db1  call    ?GetImageName@WdcTraceControl@@QEAAJ_KPEAPEAGH@Z; WdcTraceControl::GetImageName(unsigned __int64,ushort * *,int)
0x180029db6  test    eax, eax
0x180029db8  js      short loc_180029DE7
0x180029dba  cmp     eax, 1
0x180029dbd  jz      short loc_180029DE7
0x180029dbf  or      dword ptr [rdi+58h], 1
0x180029dc3  cmp     [r14], rbp
0x180029dc6  jnz     short loc_180029DE7
0x180029dc8  lea     rax, [rbx+58h]
0x180029dcc  mov     rcx, [rax]
0x180029dcf  cmp     [rcx+8], rax
0x180029dd3  jnz     loc_180029FE3
0x180029dd9  mov     [r14], rcx
0x180029ddc  mov     [r14+8], rax
0x180029de0  mov     [rcx+8], r14
0x180029de4  mov     [rax], r14
0x180029de7  mov     rcx, [rdi+80h]; bstrString
0x180029dee  test    rcx, rcx
0x180029df1  jz      short loc_180029E04
0x180029df3  call    cs:__imp_SysFreeString
0x180029df9  mov     qword ptr [rdi+80h], 0
0x180029e04  mov     rcx, r12; psz
0x180029e07  call    cs:__imp_SysAllocString
0x180029e0d  test    rax, rax
0x180029e10  jz      loc_180029FB8
0x180029e16  mov     [rdi+80h], rax
0x180029e1d  or      dword ptr [rdi+78h], 1
0x180029e21  cmp     [r14], rbp
0x180029e24  jnz     short loc_180029E45
0x180029e26  lea     rax, [rbx+58h]
0x180029e2a  mov     rcx, [rax]
0x180029e2d  cmp     [rcx+8], rax
0x180029e31  jnz     loc_180029FE3
0x180029e37  mov     [r14], rcx
0x180029e3a  mov     [r14+8], rax
0x180029e3e  mov     [rcx+8], r14
0x180029e42  mov     [rax], r14
0x180029e45  lea     rdx, [rsp+0E8h+psz]; unsigned __int16 *
0x180029e4a  mov     rcx, r15; lptstrFilename
0x180029e4d  call    ?WdcGetFileVersionString@@YAJPEBGPEAGK@Z; WdcGetFileVersionString(ushort const *,ushort *,ulong)
0x180029e52  test    eax, eax
0x180029e54  js      short loc_180029E8E
0x180029e56  mov     rcx, [rdi+90h]; bstrString
0x180029e5d  test    rcx, rcx
0x180029e60  jz      short loc_180029E73
0x180029e62  call    cs:__imp_SysFreeString
0x180029e68  mov     qword ptr [rdi+90h], 0
0x180029e73  lea     rcx, [rsp+0E8h+psz]; psz
0x180029e78  call    cs:__imp_SysAllocString
0x180029e7e  test    rax, rax
0x180029e81  jz      loc_180029FB8
0x180029e87  mov     [rdi+90h], rax
0x180029e8e  or      dword ptr [rdi+88h], 1
0x180029e95  cmp     [r14], rbp
0x180029e98  jnz     short loc_180029EB9
0x180029e9a  lea     rax, [rbx+58h]
0x180029e9e  mov     rcx, [rax]
0x180029ea1  cmp     [rcx+8], rax
0x180029ea5  jnz     loc_180029FE3
0x180029eab  mov     [r14], rcx
0x180029eae  mov     [r14+8], rax
0x180029eb2  mov     [rcx+8], r14
0x180029eb6  mov     [rax], r14
0x180029eb9  mov     rcx, [rdi+0A0h]; bstrString
0x180029ec0  test    rcx, rcx
0x180029ec3  jz      short loc_180029ED6
0x180029ec5  call    cs:__imp_SysFreeString
0x180029ecb  mov     qword ptr [rdi+0A0h], 0
0x180029ed6  mov     rcx, r15; psz
0x180029ed9  call    cs:__imp_SysAllocString
0x180029edf  test    rax, rax
0x180029ee2  jz      loc_180029FB8
0x180029ee8  mov     [rdi+0A0h], rax
0x180029eef  or      dword ptr [rdi+98h], 1
0x180029ef6  xor     ebx, ebx
0x180029ef8  cmp     [r14], rbp
0x180029efb  jnz     short loc_180029F21
0x180029efd  mov     rax, [rsp+0E8h+var_90]
  ... truncated ...
```
